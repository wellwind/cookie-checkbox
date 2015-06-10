# cookie-checkbox
Save cookie data when checkbox checked, or load cookie data to checkbox when page load.

See demo here: http://wellwind.github.io/cookie-checkbox/demo.html

## Installation

```HTML
<script src="jquery.js" />
<script src="jquery.cookie.js" />
<script src="cookie-checkbox.js" />
```

You can get jquery.cookie plugin here:
https://github.com/carhartl/jquery-cookie

## Usage

### Step 1. Set data-checkbox-* data-api to checkbox

All cookie checkbox shoud add data-checkbox-* data-api.

You need to set `data-cookie-checkbox="true"` to enable a cookie checkbox, then set `data-cookie-check-box-key="{key}"` and `data-cookie-checkbox-value="{value}"`.

```HTML
<input type="checkbox" data-cookie-checkbox="true" 
  data-cookie-checkbox-key="CookieCheckBoxSample1" data-cookie-checkbox-value="01"> Option 01
<input type="checkbox" data-cookie-checkbox="true" 
  data-cookie-checkbox-key="CookieCheckBoxSample1" data-cookie-checkbox-value="02"> Option 02
```

When check or uncheck the checkbox the {value} will be added or removed from cookie {key} (cookie name will be cookie-checkbox-{key}).

If you want a checkbox for check all. You can set `data-cookie-checkbox-check-all="true"` and `data-cookie-checkbox-key="{key}"` to a checkbox.

```HTML
<input type="checkbox" 
  data-cookie-checkbox-check-all="true" data-cookie-checkbox-key="CookieCheckBoxSample1"> Select All
```

When this check box check or uncheck, all checkboxes with same {key} will be checked / unchecked.

### Step 2. Use javascript to enable cookie checkbox

When page load, you need to call `enableCookieCheckBox();` to enable cookie checkbox.

```javascript
$(document).ready(function() {
  enableCookieCheckBox();
});
```

You can call `getCookieCheckboxValues('{key}')` to get the values checked.

```javascript
var result = JSON.stringify(getCookieCheckboxValues('CookieCheckBoxSample1'));
alert(result);
```

If you want to clear the cookie checkbox values stored to cookie, juse call `clearCookieCheckBox('{key}')`
