# Game Analytics Data Engineer challenge

The purpose of this challenge is to test fundamental skills required for the Data Engineer role. There is no correct solution - your solution will serve as a basis for discussions in a follow-up interview.

You are not expected to spend more than **2 hours** on this assignment. Please note down the time you spend - we appreciate your honesty.

## Background

At Game Analytics we receive billions of events every day from a wide range of platforms. Most of the events have the following format:

```javascript
{
  "data": {
    "session_id": "{some-uuid}",
    "category": "{one of design, progression, resource or session_end}",
    "manufacturer": "{some-string}",
    "user_id": "{some-string}",
    ... (truncated)
  },
  "country_code": "{2-character-country-code}",
  "arrival_ts": {POSIX-timestamp},
  "user_meta": {
    ... (truncated)
  }
}
```

In the `data/` folder you will find a small data sample with line-delimited JSON in the format above. Note that the example has newlines for readability whereas the sample data is one JSON object per line.

The task is to read the *uncompressed data* from STDIN (something like `zcat data/*.gz | ./your_app` should work) and compute some simple metrics:

* the number of unique user_id's in the data set
* the mean, min and max number of sessions (unique session_id's) per user_id
* the top 3 manufacturers in the data set

Your program should output the results in the following JSON format:

```javascript
{
  "active_users": 2000,
  "manufacturers": ["samsung", "HUAWEI", "LGE"],
  "sessions": {
    "mean": 5.8,
    "min": 1,
    "max": 8
  }
}
```

You should provide source code with instructions to build and run the application along with its dependencies.

## Criteria

You should take the following points into consideration when working on the challenge:

* **Functionality:** does your application work according to the specifications?
* **Documentation:** is the code clear, well documented and structured?
* **Testing:** is the code tested or is a test strategy considered?
* **Code re-use/abstraction:** is the code made with re-use in mind? how easy would it be to extend with new, similar metrics?

Your application does not need to handle TB's of data, but you should be prepared for a discussion on that premise.

Good Luck!