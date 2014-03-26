Phonetic Analysis for Elasticsearch
===================================

The Phonetic Analysis plugin integrates phonetic token filter analysis with elasticsearch.

In order to install the plugin, simply run: `bin/plugin -install elasticsearch/elasticsearch-analysis-phonetic/1.8.0`.

* For master elasticsearch versions, look at [master branch](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/tree/master).
* For 1.1.x elasticsearch versions, look at [es-1.1 branch](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/tree/es-1.1).
* For 1.0.x elasticsearch versions, look at [es-1.0 branch](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/tree/es-1.0).
* For 0.90.x elasticsearch versions, look at [es-0.90 branch](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/tree/es-0.90).

|    Phonetic Analysis Plugin   |    elasticsearch    | Release date |
|-------------------------------|---------------------|:------------:|
| 1.9.0-SNAPSHOT                | 0.90.11 -> 0.90     |  XXXX-XX-XX  |
| 1.8.0                         | 0.90.8 -> 0.90      |  2013-12-19  |
| 1.7.0                         | 0.90.6 -> 0.90.7    |  2013-11-06  |
| 1.6.0                         | 0.90.3 -> 0.90.5    |  2013-08-08  |
| 1.5.0                         | 0.90.1 -> 0.90.2    |  2013-05-30  |
| 1.4.0                         | 0.90.0              |  2013-04-29  |
| 1.3.0                         | 0.90.0              |  2013-02-26  |
| 1.2.0                         | 0.19.2 -> 0.20      |  2012-05-09  |
| 1.1.0                         | 0.19.0 -> 0.19.1    |  2012-02-07  |
| 1.0.0                         | 0.18                |  2012-01-07  |

Please read documentation relative to the version you are using:

* [1.9.0-SNAPSHOT](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/es-0.90/README.md)
* [1.8.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.8.0/README.md)
* [1.7.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.7.0/README.md)
* [1.6.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.6.0/README.md)
* [1.5.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.5.0/README.md)
* [1.4.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.4.0/README.md)
* [1.3.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.3.0/README.md)
* [1.2.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.2.0/README.md)
* [1.1.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.1.0/README.md)
* [1.0.0](https://github.com/elasticsearch/elasticsearch-analysis-phonetic/blob/v1.0.0/README.md)


A `phonetic` token filter that can be configured with different `encoder` types: 
`metaphone`, `doublemetaphone`, `soundex`, `refinedsoundex`, 
`caverphone1`, `caverphone2`, `cologne`, `nysiis`,
`koelnerphonetik`, `haasephonetik`, `beidermorse`

The `replace` parameter (defaults to `true`) controls if the token processed 
should be replaced with the encoded one (set it to `true`), or added (set it to `false`).

    {
        "index" : {
            "analysis" : {
                "analyzer" : {
                    "my_analyzer" : {
                        "tokenizer" : "standard",
                        "filter" : ["standard", "lowercase", "my_metaphone"]
                    }
                },
                "filter" : {
                    "my_metaphone" : {
                        "type" : "phonetic",
                        "encoder" : "metaphone",
                        "replace" : false
                    }
                }
            }
        }
    }

Questions
---------

If you have questions or comments please use the [mailing list](https://groups.google.com/group/elasticsearch) instead
of Github Issues tracker.

License
-------

    This software is licensed under the Apache 2 license, quoted below.

    Copyright 2009-2014 Elasticsearch <http://www.elasticsearch.org>

    Licensed under the Apache License, Version 2.0 (the "License"); you may not
    use this file except in compliance with the License. You may obtain a copy of
    the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
    WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
    License for the specific language governing permissions and limitations under
    the License.
