# Hindu festival dates, 2026 and 2027

Open data on 73 Hindu festivals and vrats in 2026 and 2027: dates, tithi times and puja windows, as CSV, JSON and an ICS calendar. Everything is computed for Delhi (IST).

The data comes from [Bela](https://bela.so/festivals/), where each festival has a page explaining how its date is fixed.

## Major festivals

| Festival | 2026 | 2027 |
| --- | --- | --- |
| Makar Sankranti | [14 Jan 2026](https://bela.so/festivals/makar-sankranti/2026/) | [15 Jan 2027](https://bela.so/festivals/makar-sankranti/2027/) |
| Vasant Panchami | [23 Jan 2026](https://bela.so/festivals/vasant-panchami/2026/) | [11 Feb 2027](https://bela.so/festivals/vasant-panchami/2027/) |
| Maha Shivaratri | [15 Feb 2026](https://bela.so/festivals/maha-shivaratri/2026/) | [6 Mar 2027](https://bela.so/festivals/maha-shivaratri/2027/) |
| Holi | [4 Mar 2026](https://bela.so/festivals/holi/2026/) | [22 Mar 2027](https://bela.so/festivals/holi/2027/) |
| Chaitra Navratri | [19 Mar 2026](https://bela.so/festivals/chaitra-navratri/2026/) | [7 Apr 2027](https://bela.so/festivals/chaitra-navratri/2027/) |
| Ugadi / Gudi Padwa | [19 Mar 2026](https://bela.so/festivals/ugadi-gudi-padwa/2026/) | [7 Apr 2027](https://bela.so/festivals/ugadi-gudi-padwa/2027/) |
| Ram Navami | [26 Mar 2026](https://bela.so/festivals/ram-navami/2026/) | [15 Apr 2027](https://bela.so/festivals/ram-navami/2027/) |
| Hanuman Jayanti | [2 Apr 2026](https://bela.so/festivals/hanuman-jayanti/2026/) | [20 Apr 2027](https://bela.so/festivals/hanuman-jayanti/2027/) |
| Akshaya Tritiya | [19 Apr 2026](https://bela.so/festivals/akshaya-tritiya/2026/) | [9 May 2027](https://bela.so/festivals/akshaya-tritiya/2027/) |
| Guru Purnima | [29 Jul 2026](https://bela.so/festivals/guru-purnima/2026/) | [18 Jul 2027](https://bela.so/festivals/guru-purnima/2027/) |
| Raksha Bandhan | [28 Aug 2026](https://bela.so/festivals/raksha-bandhan/2026/) | [17 Aug 2027](https://bela.so/festivals/raksha-bandhan/2027/) |
| Krishna Janmashtami | [4 Sep 2026](https://bela.so/festivals/janmashtami/2026/) | [25 Aug 2027](https://bela.so/festivals/janmashtami/2027/) |
| Ganesh Chaturthi | [14 Sep 2026](https://bela.so/festivals/ganesh-chaturthi/2026/) | [4 Sep 2027](https://bela.so/festivals/ganesh-chaturthi/2027/) |
| Onam (Thiruvonam) | [26 Aug 2026](https://bela.so/festivals/onam/2026/) | [12 Sep 2027](https://bela.so/festivals/onam/2027/) |
| Sharad Navratri | [11 Oct 2026](https://bela.so/festivals/sharad-navratri/2026/) | [30 Sep 2027](https://bela.so/festivals/sharad-navratri/2027/) |
| Dussehra (Vijayadashami) | [20 Oct 2026](https://bela.so/festivals/dussehra/2026/) | [9 Oct 2027](https://bela.so/festivals/dussehra/2027/) |
| Karwa Chauth | [29 Oct 2026](https://bela.so/festivals/karwa-chauth/2026/) | [18 Oct 2027](https://bela.so/festivals/karwa-chauth/2027/) |
| Dhanteras (Dhantrayodashi) | [6 Nov 2026](https://bela.so/festivals/dhanteras/2026/) | [27 Oct 2027](https://bela.so/festivals/dhanteras/2027/) |
| Diwali (Lakshmi Puja) | [8 Nov 2026](https://bela.so/festivals/diwali/2026/) | [29 Oct 2027](https://bela.so/festivals/diwali/2027/) |
| Govardhan Puja | [10 Nov 2026](https://bela.so/festivals/govardhan-puja/2026/) | [30 Oct 2027](https://bela.so/festivals/govardhan-puja/2027/) |
| Bhai Dooj | [11 Nov 2026](https://bela.so/festivals/bhai-dooj/2026/) | [31 Oct 2027](https://bela.so/festivals/bhai-dooj/2027/) |
| Chhath Puja | [15 Nov 2026](https://bela.so/festivals/chhath-puja/2026/) | [4 Nov 2027](https://bela.so/festivals/chhath-puja/2027/) |

Every festival is in [`data/`](data/). Each date links to the festival's page for that year.

## Files

| File | What it holds |
| --- | --- |
| `data/festivals-<year>.csv` | One row per festival: date, weekday, name, slug, rule, tithi with its start and end, the next-day Vaishnava fast date for Ekadashis (`gauna_date`), the labelled days of multi-day festivals, and a link to the festival's page. |
| `data/festival-windows-<year>.csv` | One row per puja window: festival, city, kind (`puja`, `pradosh`, `nishita`, `lagna`, `snan`, `abhijit`), window name, start and end. Diwali, Dhanteras and Raksha Bandhan also have times for 21 cities. |
| `data/festivals-<year>.json` | Both of the above in one file, plus `no_date_festivals`, Chhath Puja's sunrise and sunset by city, and notes on method. |
| `calendar/hindu-festivals-2026-2027.ics` | Calendar file with one all-day event per festival day. |

## Add the calendar

- **Subscribe by URL:** in Google Calendar, use Settings, then Add calendar, then From URL, and paste `https://raw.githubusercontent.com/anshulkulhari7/hindu-festival-dates/main/calendar/hindu-festivals-2026-2027.ics`. Apple Calendar and Outlook have the same option.
- **Import once:** download the `.ics` file and import it into your calendar app.

## How the dates are computed

- **Calculation:** deterministic classical panchang computation (drik ganit) with Swiss Ephemeris positions, Lahiri ayanamsa and mean nodes.
- **Rule:** the `rule` column names the moment the festival's tithi must prevail at: `udaya` (sunrise), `pradosh`, `nishita`, `madhyahna`, `aparahna`, `purvahna`, `sayankala` or `moonrise`. Nakshatra and sankranti rows are fixed by the Moon's star or the Sun's sign.
- **When the tithi misses that moment:** `rule_holds: false` in the JSON marks a date where the tithi does not cover the rule's moment that year, so the date is the day the tithi falls.

The [methodology page](https://bela.so/methodology/) has the details, and [this article](https://bela.so/blog/why-panchang-sites-show-different-dates/) explains why panchang sites can disagree.

## Limits

- **Place:** dates and times are for Delhi. A tithi-based observance can fall a day apart at another longitude, and window times change by city.
- **Tradition:** regional and family traditions can follow different rules, so a local calendar may show a different day.
- **Years with no date:** some festivals have no date in a given year. For example, no Vaikuntha Ekadashi falls in 2027: the dates either side are 20 December 2026 and 8 January 2028. `no_date_festivals` in the JSON lists these with the previous and next date.

## License and citation

The data is released under [CC BY 4.0](LICENSE). A credit like this is enough:

> Festival dates: Bela (bela.so), computed for Delhi (IST).

## Related data

[Muhurat dates by event](https://bela.so/datasets/) for 2026 and 2027, also CC BY 4.0, are published on bela.so.

## Corrections

If a date looks wrong, open an issue with the festival, the year and your source, or write to support@bela.so.
