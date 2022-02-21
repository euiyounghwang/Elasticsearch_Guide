
**PUT INDEX**  
```sh
GET /order/default/_mapping
{
  "order" : {
    "mappings" : {
      "default" : {
        "properties" : {
          "lines" : {
            "properties" : {
              "amount" : {
                "type" : "float"
              },
              "product_id" : {
                "type" : "long"
              },
              "quantity" : {
                "type" : "long"
              }
            }
          },
          "purchased_at" : {
            "type" : "date"
          },
          "sales_channel" : {
            "type" : "text",
            "fields" : {
              "keyword" : {
                "type" : "keyword",
                "ignore_above" : 256
              }
            }
          },
          "salesman" : {
            "properties" : {
              "id" : {
                "type" : "long"
              },
              "name" : {
                "type" : "text",
                "fields" : {
                  "keyword" : {
                    "type" : "keyword",
                    "ignore_above" : 256
                  }
                }
              }
            }
          },
          "status" : {
            "type" : "text",
            "fields" : {
              "keyword" : {
                "type" : "keyword",
                "ignore_above" : 256
              }
            }
          },
          "total_amount" : {
            "type" : "float"
          }
        }
      }
    }
  }
}
```

**Bulk JSON**  
```sh
{"index":{"_id":1}}
{"purchased_at":"2016-07-10T16:52:43Z","lines":[{"product_id":6,"amount":71.32,"quantity":1},{"product_id":3,"amount":58.96,"quantity":3},{"product_id":1,"amount":29.8,"quantity":3}],"total_amount":160.08,"salesman":{"id":11,"name":"Matthus Mitkcov"},"sales_channel":"store","status":"processed"}
{"index":{"_id":2}}
{"purchased_at":"2016-03-08T16:18:37Z","lines":[{"product_id":7,"amount":31.44,"quantity":2},{"product_id":4,"amount":74.82,"quantity":2}],"total_amount":106.26,"salesman":{"id":79,"name":"Ulberto Woodruff"},"sales_channel":"store","status":"completed"}
{"index":{"_id":3}}
{"purchased_at":"2016-01-04T02:46:54Z","lines":[{"product_id":9,"amount":38.89,"quantity":1}],"total_amount":38.89,"salesman":{"id":68,"name":"Thea Chidgey"},"sales_channel":"store","status":"completed"}
{"index":{"_id":4}}
{"purchased_at":"2016-04-14T11:44:29Z","lines":[{"product_id":4,"amount":26.18,"quantity":2},{"product_id":8,"amount":76.45,"quantity":1},{"product_id":1,"amount":65.59,"quantity":3}],"total_amount":168.22,"salesman":{"id":81,"name":"Melany Cerith"},"sales_channel":"store","status":"cancelled"}
{"index":{"_id":5}}
{"purchased_at":"2016-02-18T17:11:21Z","lines":[{"product_id":2,"amount":56.06,"quantity":3},{"product_id":5,"amount":79.75,"quantity":3}],"total_amount":135.81,"salesman":{"id":23,"name":"Flynn Dome"},"sales_channel":"web","status":"completed"}
{"index":{"_id":6}}
{"purchased_at":"2016-03-26T07:28:22Z","lines":[{"product_id":7,"amount":86.88,"quantity":1},{"product_id":5,"amount":27.34,"quantity":3},{"product_id":5,"amount":88.52,"quantity":2}],"total_amount":202.74,"salesman":{"id":16,"name":"Mirilla Penkman"},"sales_channel":"web","status":"completed"}
{"index":{"_id":7}}
{"purchased_at":"2016-05-06T18:37:33Z","lines":[{"product_id":3,"amount":25.27,"quantity":2}],"total_amount":25.27,"salesman":{"id":5,"name":"Modestia McCreadie"},"sales_channel":"app","status":"confirmed"}
{"index":{"_id":8}}
{"purchased_at":"2016-11-26T11:24:36Z","lines":[{"product_id":4,"amount":51.26,"quantity":1},{"product_id":8,"amount":72.41,"quantity":1}],"total_amount":123.67,"salesman":{"id":55,"name":"Grange Smiths"},"sales_channel":"phone","status":"cancelled"}
{"index":{"_id":9}}
{"purchased_at":"2016-12-26T08:29:47Z","lines":[{"product_id":2,"amount":98.87,"quantity":3}],"total_amount":98.87,"salesman":{"id":5,"name":"Carlyn Stegers"},"sales_channel":"web","status":"cancelled"}
{"index":{"_id":10}}
{"purchased_at":"2016-12-21T12:47:43Z","lines":[{"product_id":7,"amount":21.97,"quantity":3},{"product_id":10,"amount":19.26,"quantity":3}],"total_amount":41.23,"salesman":{"id":83,"name":"Kennie Gilks"},"sales_channel":"app","status":"cancelled"}
{"index":{"_id":11}}
{"purchased_at":"2016-04-02T04:42:31Z","lines":[{"product_id":6,"amount":86.89,"quantity":1},{"product_id":4,"amount":18.04,"quantity":3},{"product_id":10,"amount":18.61,"quantity":3}],"total_amount":123.54,"salesman":{"id":39,"name":"Ashely Rawnsley"},"sales_channel":"phone","status":"cancelled"}
{"index":{"_id":12}}
{"purchased_at":"2016-09-08T16:24:12Z","lines":[{"product_id":1,"amount":11.75,"quantity":1},{"product_id":5,"amount":77.33,"quantity":2},{"product_id":2,"amount":86.76,"quantity":1}],"total_amount":175.84,"salesman":{"id":40,"name":"Raynor Dennis"},"sales_channel":"web","status":"pending"}
{"index":{"_id":13}}
{"purchased_at":"2016-01-12T06:20:27Z","lines":[{"product_id":6,"amount":93.69,"quantity":2}],"total_amount":93.69,"salesman":{"id":62,"name":"Byran Gallihaulk"},"sales_channel":"app","status":"processed"}
{"index":{"_id":14}}
{"purchased_at":"2016-01-31T13:06:58Z","lines":[{"product_id":10,"amount":80.33,"quantity":2}],"total_amount":80.33,"salesman":{"id":43,"name":"Eveleen Ickovici"},"sales_channel":"store","status":"processed"}
{"index":{"_id":15}}
{"purchased_at":"2016-02-20T23:02:31Z","lines":[{"product_id":5,"amount":20.51,"quantity":1},{"product_id":10,"amount":93.35,"quantity":1}],"total_amount":113.86,"salesman":{"id":78,"name":"Erda Boyet"},"sales_channel":"store","status":"confirmed"}
{"index":{"_id":16}}
{"purchased_at":"2016-08-17T09:52:50Z","lines":[{"product_id":9,"amount":61.95,"quantity":1}],"total_amount":61.95,"salesman":{"id":91,"name":"Gherardo MattiCCI"},"sales_channel":"web","status":"confirmed"}
{"index":{"_id":17}}
{"purchased_at":"2016-06-05T18:59:23Z","lines":[{"product_id":8,"amount":32.46,"quantity":3},{"product_id":6,"amount":13.7,"quantity":2},{"product_id":8,"amount":28.74,"quantity":2}],"total_amount":74.9,"salesman":{"id":82,"name":"Shanon Eilhertsen"},"sales_channel":"phone","status":"confirmed"}
{"index":{"_id":18}}
{"purchased_at":"2016-07-26T12:10:15Z","lines":[{"product_id":3,"amount":23.16,"quantity":1},{"product_id":4,"amount":18.94,"quantity":1},{"product_id":10,"amount":38.65,"quantity":2}],"total_amount":80.75,"salesman":{"id":58,"name":"Thekla De Beauchemp"},"sales_channel":"phone","status":"processed"}
{"index":{"_id":19}}
{"purchased_at":"2016-05-08T19:54:44Z","lines":[{"product_id":9,"amount":29.8,"quantity":2},{"product_id":6,"amount":97.61,"quantity":3}],"total_amount":127.41,"salesman":{"id":96,"name":"Susannah Grigoryev"},"sales_channel":"phone","status":"cancelled"}
{"index":{"_id":20}}
{"purchased_at":"2016-06-19T21:34:51Z","lines":[{"product_id":2,"amount":23.3,"quantity":2},{"product_id":5,"amount":30.44,"quantity":2},{"product_id":6,"amount":22.15,"quantity":1}],"total_amount":75.89,"salesman":{"id":66,"name":"Janeta Crutchfield"},"sales_channel":"phone","status":"completed"}