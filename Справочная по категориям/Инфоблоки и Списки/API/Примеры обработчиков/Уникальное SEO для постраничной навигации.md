
```
<?
AddEventHandler("main", "OnEndBufferContent", "uniqueSEO");
function uniqueSEO(&$content)
{
    if(isset($_GET['PAGEN_1']))
   {
       $page=(int)$_GET['PAGEN_1'];
        # title
       $pattern = '/(.*?)<title[^>]*>(.*?)\n?\n?<\/title>(.*)/s';
       $replacement = '$1<title>$2'.' страница - '.$page.'</title>$3';
       $content= preg_replace($pattern, $replacement, $content);
        # description
       $pattern = '/(.*?)<meta name="description" content="(.*?)\n?\n?"\s?\/>(.*)/s';
       $replacement = '$1<meta name="description" content="$2'.' страница - '.$page.'" />$3';
       $content= preg_replace($pattern, $replacement, $content);
   }
}
?>
```