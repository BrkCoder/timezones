# Timezones

This project uses [*moment-timezone*](http://momentjs.com/timezone)'s data utitlities to create compact but comprehensive lists of timezones for user interfaces.

## Usage

```javascript
import timezones from '@picter/timezones/data/select-list.json';
import moment from 'moment-timezone';
import momentData from '@picter/timezones/data/moment-timezones.json';

console.log(JSON.stringify(timezones, null, 2));

/*
output:

[
  {
    "label": "(UTC-11:00) Niue",
    "value": "Pacific/Niue"
  },
  {
    "label": "(UTC-11:00) Pago Pago, Midway, Samoa",
    "value": "Pacific/Pago_Pago"
  },
...
]

*/

// use pre-built moment data to base moment on the same data
moment.tz.add(momentData.zones);

```

The values are extracted from [iana's time zone database](https://www.iana.org/time-zones) and can safely be used by libraries like [*moment-timezone*](http://momentjs.com/timezone).

## Development

*iana* publishes database updates twice a year. As soon as [*moment-timezone*](http://momentjs.com/timezone) updated their data, we can update our *moment-timezone* dev-dependency and rebuild our lists with `yarn run build`.