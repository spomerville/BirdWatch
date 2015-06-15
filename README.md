#BirdWatch  

This is a fork of mathiasn's <a target="_blank" href="https://github.com/matthiasn/BirdWatch"><strong>BirdWatch</strong></a>. It adds a couple of minor tweaks to help visualizing existing tweet data easier. These changes are only made to the Scala-Play-SSE app and not the Clojure app.

The use case is if you already have an elastic index populated with some tweet data and the tweets are stored as an object in some larger document.

For example you may want to visualize your tweets that are stored like this:

    {
        <some tweet level metadata>,
        "raw": {
            <the original tweet>
        }
    }


To do that:
+ The configuration to register to the twitter stream was made optional (it won't register to listen on the stream if the config is absent)
+ A new configuration item was added to application.conf, `elastic.defaultSearchField`, that specifies the field to be searched (e.g. raw.text instead of just text)
+ The angular client was updated to also look for the `raw` field in addition to the other fields it already looked for


## Licence
Copyright © 2013 **[Matthias Nehlsen](http://www.matthiasnehlsen.com)**. Distributed under the **GNU GENERAL PUBLIC LICENSE**, Version 3. See separate LICENSE file.