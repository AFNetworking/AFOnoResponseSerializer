AFOnoResponseSerializer
=======================

`AFOnoResponseSerializer` is an XML and HTML response serializer for AFNetworking 2.0, using [Ono](https://github.com/mattt/ono).

## Usage

### XML

```objective-c
AFHTTPRequestOperationManager *manager = [AFHTTPRequestOperationManager manager];
manager.responseSerializer = [AFOnoResponseSerializer XMLResponseSerializer];
[manager GET:@"http://example.com/foo.xml" parameters:nil success:^(NSHTTPURLResponse *response, ONOXMLDocument *responseDocument) {
    for (ONOXMLElement *element in [responseDocument XPath:@"//item"]) {
        NSLog(@"%@", element);
    }
} failure:nil];
```

### HTML

```objective-c
AFHTTPRequestOperationManager *manager = [AFHTTPRequestOperationManager manager];
manager.responseSerializer = [AFOnoResponseSerializer HTMLResponseSerializer];
[manager GET:@"http://example.com/bar.html" parameters:nil success:^(NSHTTPURLResponse *response, ONOXMLDocument *responseDocument) {
    for (ONOXMLElement *element in [responseDocument CSS:@"body ul li"]) {
        NSLog(@"%@", element);
    }
} failure:nil];
```

---

## Contact

Mattt Thompson

- http://github.com/mattt
- http://twitter.com/mattt
- m@mattt.me

## License

AFOnoResponseSerializer is available under the MIT license. See the LICENSE file for more info.
