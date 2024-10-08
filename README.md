# DateExtension

`DateExtension` is a little Swift Library for formatting date strings or different dates, such as those returned by (REST) APIs. It can process and automatically recognize different date formats and convert date strings into the desired format.d format.

## Features

- Convert `Date` `Strings` to user readable formats to use them in a `Text("")` for example
- Convert `Date` `Strings` to use them in a func, for example for an `API` call
  
## Installation

To install this package, follow these steps:

1. Go to `General` -> `Frameworks, Libraries, and Embedded Content`.
2. Click on the `+` button.
3. Click on the "Add More" dropdown and select `Add Package Dependency...`.
4. Paste the following URL in the top right: `https://github.com/johannesxdev/DateExtension.git`.
5. Click on `Add Package` and then again on `Add Package` in the next window.


Then, import the library in your Swift files:

```swift
import DateExtension
```

## Usage

### Example Text() : Convert ISO 8601 Date to dd.MM.yyyy Format (31.12.2024)

```swift
import SwiftUI
import DateExtension

struct ContentView: View {
    var body: some View {
        
        let time = "2023-12-31T14:35:50Z"
        Text(time.formattedDate(.ddMMyyyy))
        
    }
}
```

In this example, a date in ISO 8601 format `Text("2023-12-31T14:35:50Z")` within a text is automatically detected and converted into the format `dd.MM.yyyy` `Text("31.12.2023")`.


### Example func() : Convert Date + Time to ISO 8601 Format (2023-12-31T14:35:50Z)

```swift
import SwiftUI
import DateExtension

struct ContentView: View {
    var body: some View {
        
        Button("func"){
            fetchFunc()
        }
    }
    
    func fetchFunc() {
        let time = "12:23:00"
        let date = "12.09.2024"
        let iso8601 = "\(date) \(time)".formattedDate(.iso8601)
        
        print(iso8601)
    }
}
```

In this example, a date and time within a text are automatically detected and converted into the ISO 8601 format `2023-12-31T14:35:50Z`.
