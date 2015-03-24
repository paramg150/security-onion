Dr. Johannes Ullrich of the SANS Internet Storm Center posted a <a href='http://isc.sans.edu/diary.html?storyid=13918'>great DNS Anomaly Detection script</a> based on the query logs coming from his DNS server.  We can do the same thing with Bro's dns.log (where Bro captures all the DNS queries it sees on the network).

```
#!/bin/bash

export PATH=/opt/bro/bin:$PATH
BRO_LOGS="/nsm/bro/logs"
TODAY=`date +%Y-%m-%d`
YESTERDAY=`date -d yesterday +%Y-%m-%d`
OLD_DIRS=`ls $BRO_LOGS |egrep -v "current|stats|$TODAY|$YESTERDAY"`
TMPDIR=/tmp
OLDLOG=$TMPDIR/oldlog
NEWLOG=$TMPDIR/newlog
SUSPECTS=$TMPDIR/suspects

for DIR in $OLD_DIRS; do zcat $BRO_LOGS/$DIR/dns* |bro-cut query; done | sort | uniq -c | sort -k2 > $OLDLOG
zcat $BRO_LOGS/$YESTERDAY/dns* |bro-cut query | sort | uniq -c | sort -k2 > $NEWLOG
join -1 2 -2 2  -a 2 $OLDLOG $NEWLOG | egrep -v '.* [0-9]+ [0-9]+$' | sort -nr -k2 | head -10 > $SUSPECTS
```