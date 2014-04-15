Browser-hack
============

To distinguish ie6 ie7 ie8 ie9 ie10
使用CSS Hack 来区分IE6,IE7,IE8,IE9,IE10

## 第一种简单点
#### 只能区分IE6,IE7,IE8,IE9+版本

````html
h4{
		background:cyan;  /*--ie11--*/
		background:green\9\0;  /*--ie9 ie10--*/
		background:yellow\0/;  /*--ie8--*/
		+background:orange;  /*--ie7--*/
		_background:red; /*--ie6--*/
	}
````

## 第二种复杂点
#### 可以精确区分IE6－IE10的每一个版本 by Dimox http://dimox.net/personal-css-hacks-for-ie6-ie7-ie8/

````css
/* IE 6 */
* html .notie {display: none}
* html .ie6 {display: block}

/* IE 7 */
*+html .notie {display: none}
*+html .ie7 {display: block}

/* IE 8 */
@media \0screen {
	.notie {display: none}
	.ie8 {display: block}
}

/* IE 9 */
:root .notie {display: none\9}
:root .ie9 {display: block\9}

/* IE 10 */
@media screen and (-ms-high-contrast: active), (-ms-high-contrast: none) {
	.notie, .ie9 {display: none !important}
	.ie10 {display: block}
}
````