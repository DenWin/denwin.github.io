---
title: Calculate Date based on calendar week
---

# Problem
I’d like to know the date of calendar week 13 in 2023 (27th of march) or any other week that is.

A1=Year

A2=calendar week

=DATE(A1;1;5)-WEEKDAY(DATE(A1;1;4);11)+(A2-1)*7


| Date(5th Jan)	| Date(4th Jan)	| Weekday# of the 4th
returntype 11 (Mo-Su)	| Date of the 1st cal week
per year	| Date of the 1st day
per cal week |
| =DATE(Year;1;5)	| =DATE(Year;1;4)	| =WEEKDAY(
DATE(Year;1;4);11)	| =DATE(Year;1;5)
-WEEKDAY(DATE(Year;1;4);11)	| =DATE(A1;1;5)
-WEEKDAY(DATE(A1;1;4);11)
+(CalWeek-1)*7 |