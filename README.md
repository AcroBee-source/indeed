# Indeed
[![Build Status](https://travis-ci.org/stevesoltys/indeed.svg?branch=master)](https://travis-ci.org/stevesoltys/indeed)

An Indeed search API wrapper.

## Usage
Create an `Indeed` instance with your publisher ID, build a search query, and run it.

Here's an example:
```java
Indeed indeed = new Indeed("1234567890");

IndeedSearchResults searchResults = indeed.search()
    .query("Java").location("NYC")
    .radius(30).start(50).limit(100).run();

int total = searchResults.getTotalResults();

List<IndeedResult> results = searchResults.getResults();

// ...
```

You can also get an `IndeedResult` for a particular job, if you have the job key:
```java
Indeed indeed = new Indeed("1234567890");

IndeedResult result = indeed.getJob("1a2b3c4d5e6f7g8h9");
System.out.println(result.getTitle() + " at " + result.getCompany());
```


## Development
After checking out the repo, run `gradle build` to build the project. Then, run `gradle test` to run the tests.

## License
This application is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
