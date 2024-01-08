---
title: INstall Playstore on FireHD
---

# Current FireOS-Version
You can find the current Version by checking "System Updates" or here:
* [Fire Tablet Specifications: Fire HD Models](https://developer.amazon.com/docs/fire-tablets/ft-device-specifications-firehd-models.html?v=firehd10_2021)

Stats for my FireHD:
* Fire HD 10 (2021, 11th gen)
* FireOS7
* Android 9 „Pie“
* API-Level 28
* arm64-v8a
* nodpi&s
* do not load bundles


Install the following APK in exactly this order:

	
| #		| APK																																																			| Min API		| Architecture				| DPI	| Capabilities	| Latest installed Version		| Released		|
|---	|---																																																			|---			|---						|---	|---			|---							|---			|
| 1		| [Google Account Manager](		https://www.apkmirror.com/?post_type=app_release&searchtype=apk&sortby=date&sort=desc&minapi-min=23&minapi-max=28&dpi%5B%5D=nodpi&s=Google+Account+Manager)						| Android 6.0+	| {No Filter => noarch}		| nodpi	| {No Filter}	| 7.1.2							| 2017-04-04	|
| 2		| [Google Services Framework](	https://www.apkmirror.com/?post_type=app_release&searchtype=apk&sortby=date&sort=desc&minapi-min=28&minapi-max=28&dpi%5B%5D=nodpi&s=Google+Services+Framework)					| Android 9.0+	| {No Filter => noarch}		| nodpi	| {No Filter}	| 9-6957767 (2021-08-29)		| 2021-08-29	|
| 3		| [Google Play Services](		https://www.apkmirror.com/?post_type=app_release&searchtype=apk&sortby=date&sort=desc&minapi-min=28&minapi-max=28&dpi%5B%5D=nodpi&arch%5B%5D=arm64-v8a&s=Google+Play+Services)	| Android 9.0+	| arm64-v8a					| nodpi	| {No Filter}	| 23.49.14 (100400-590296185)	| 2023-12-20	|
| 4		| [Google Play Store](			https://www.apkmirror.com/?post_type=app_release&searchtype=apk&sortby=date&sort=desc&minapi-min=21&minapi-max=28&dpi%5B%5D=nodpi&arch%5B%5D=universal&s=Google+Play+Store)		| Android 5.0+	| universal					| nodpi	| {No Filter}	| 39.1.21-21 [0] [PR] 594053428	| 2024-01-04	|