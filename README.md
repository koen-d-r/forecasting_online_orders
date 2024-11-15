In this file, a forecast for the expected number of online orders is generated for the next 364 days. This process runs weekly on Monday morning, where our logistics colleagues have a fresh numbers on the start of their workweek.

**Blokker calendar**\
A Blokker calendar is being used, where each year has 364 days with a leap year every 7 to 8 years. This leap year contains one extra week. Using 364 days per year has the benefit of having exactly 52 weeks, 13 periods and 4 quarters, each of the exact same length.

**Holidays**\
A separate table with holidays us being maintained, with days like Christmas, Easter and other local holidays. In some cases, there is a pretty major impact on the number of online orders

**Magazines**\
4 to 5 times a year, Blokker distributed a magazine door-to-door to around 4 million households in the Netherlands. This had a impact on the number of online orders.

**Trend**\
A trend is being calculated by calculating the growth of rolling sums with lookback windows of 28, 91 and 364 days for this year and last year. This corresponds to respectively 4, 13 and 52 weeks.

**Logic**\
- If this year is a holiday, grab the number of orders from last years holiday and multiply by 1 + trend
- If this year has a magazine, grab the number of orders from last years magazine and multiply by 1 + trend
- If months are January or December, grab last years orders multiply by 1 + trend
- Else grab the average of last years orders and the average of the last 4 weeks on that specific day of the week (e.g. last four Tuesdays) and multiply by 1 + trend

**Shifting**\
Since the distribution center is always closed on Saturdays, orders generated on Saturday will be picked, packed and sent out the next day. This is the reason why orders are shifted to the next day.
