---
date: 2017-02-15T13:56:21-05:00
title: examples
---
Unless otherwise specified, the markup for examples below consists of just an input element, and flatpickr [invocation](/getting-started/#usage) with a given config.

## Basic

`flatpickr` without any config. Some features right off the bat:

- The year is scrollable and can be typed in
- The month name is scrollable

<input class=flatpickr type="text" placeholder="Select Date..">

## DateTime

```json
{
    enableTime: true
}
```

<input class=flatpickr type="text" placeholder="Select Date.." data-id="datetime">

## Human-friendly Dates

`altInput` hides your original input and creates a new one. 

Upon date selection, the original input will contain a `Y-m-d...` string, while the `altInput` will display the date in a more legible, customizable format.

Enabling this option is highly recommended.

```json
{
    altInput: true
}
```

<input class=flatpickr type="text" placeholder="Select Date.." data-id="altinput">

## Supplying Dates for flatpickr

flatpickr has numerous options that accept date values in a variety of formats. Those are:

- defaultDate
- minDate
- maxDate
- enable/disable

The values accepted by these options all follow the same guidelines. 

You may specify those dates in a variety of formats:

- [Date Objects](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Date) are always accepted
    + `new Date(2015, 0, 10)`
- [Timestamps](https://en.wikipedia.org/wiki/Unix_time) are always accepted
    + e.g. `1488136398547`
- ISO Date Strings are always accepted
    + e.g. `"2017-02-26T19:40:03.243Z"`
- Date Strings, which **must match the `dateFormat`** chronologically
    + `dateFormat` defaults to `YYYY-MM-DD HH:MM`
    + This means that `"2016"` `"2016-10"`, `"2016-10-20"`, `"2016-10-20 15"`, `"2016-10-20 15:30"` are all valid date strings
    
- The shortcut `"today"`



## Preloading a Date

The selected date will get parsed from the input's value or the `defaultDate` option.

See [supplying dates](#supplying-dates-for-flatpickr) for valid date examples.


## minDate and maxDate

`minDate` option specifies the **minimum/earliest** date (inclusively) allowed for selection.

`maxDate` option specifies the **maximum/latest** date (inclusively) allowed for selection.


```json
{
    minDate: "2017-04"
}
```

<input class=flatpickr type="text" placeholder="Select Date.." data-id="minDate2017">

```json
{
    dateFormat: "d.m.Y",
    maxDate: "15.12.2017"
}
```

<input class=flatpickr type="text" placeholder="Select Date.." data-id="maxDateStr">



```json
{
    minDate: "today"
}
```

<input class=flatpickr type="text" placeholder="Select Date.." data-id="minDateToday">

```js
{
    minDate: "today",
    maxDate: new Date().fp_incr(14) // 14 days from now
}
```

<input class=flatpickr type="text" placeholder="Select Date.." data-id="minMaxDateTwoWeeks">
