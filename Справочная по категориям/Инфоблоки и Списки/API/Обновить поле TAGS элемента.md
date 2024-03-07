
```
CModule::IncludeModule('iblock');

$el = new CIBlockElement;

$PRODUCT_ID = 135;
$arLoadProductArray = Array(
  "TAGS"    => "test",
);

$res = $el->Update($PRODUCT_ID, $arLoadProductArray);
```