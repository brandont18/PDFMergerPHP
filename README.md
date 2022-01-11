#PDFMerger for PHP (PHP >= 5/Laravel Compatible)

Original written by https://github.com/myokyawhtun/PDFMerger


### Example Usage
```php

$pdf = new PDFMerger();

$pdf->addPDF('samplepdfs/one.pdf', '1, 3, 4');
$pdf->addPDF('samplepdfs/two.pdf', '1-2');
$pdf->addPDF('samplepdfs/three.pdf', 'all');

$pdf->merge('file', 'samplepdfs/TEST2.pdf'); 

$pdf1 = public_path().'/images/prueba.pdf';
$stream = fopen($pdf1, "r");
$content = fread ($stream, filesize($pdf1));
if(!$stream || !$content) return 0; 
$count = 0;
$regex = "/\/Count\s+(\d+)/";
if(preg_match_all($regex, $content, $matches)) $count = max($matches); 
return $count[0];

$pdf = new PDFMerger();
$pdf->addPDF($pdf1, '1-5');
$pathForTheMergedPdf = public_path()."/result.pdf";
$pdf->merge('file', $pathForTheMergedPdf);
    
// REPLACE 'file' WITH 'browser', 'download', 'string', or 'file' for output options
```
