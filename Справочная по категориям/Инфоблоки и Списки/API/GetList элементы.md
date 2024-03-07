
```
CModule::IncludeModule("iblock");

$arSelect = Array("ID", "IBLOCK_ID", "*", "catalog_PRICE_1", "PROPERTY_*");
$arFilter = Array("IBLOCK_ID"=>2, "ID"=>7);

$arProducts = CIBlockElement::GetList(Array(), $arFilter, false, false, $arSelect);

while($ob = $arProducts->GetNextElement())
{
$fields = $ob->GetFields();
// Записываем цену
    $arPrice[] = $fields['CATALOG_PRICE_1'];

// Записываем поля
    $arFields[] = $fields;

// Записываем свойства
    $props = $ob->GetProperties();
    $arProps[] = $props;
}
```

- Если нужно вывести данные с пустым полем, добавь в фильтр значения =false
- Для документооборота - "SHOW_HISTORY" => "Y" или SHOW_NEW' => 'Y'(не проверено)