# PHP - patika.dev - Soru ve Cevapları
>**[patika.dev](https://app.patika.dev/courses/php-temel) platformu PHP öğrenme amaçlı soruların cevaplanması projesidir.** \
> **Profil için tıklayınız: [app.patika.dev/nmelihkutlu](https://app.patika.dev/nmelihkutlu)**


![](https://github.com/nmelihkutlu/patikaPHP/blob/main/patikaPHP.png)



[Ödev1](#ödev-1) - [Ödev2](#ödev-2) - [Ödev3](#ödev-3)

## Ödev 1

### Soru
Parametre olarak aldığı değer kadar satırı olan bir üçgen çizen bir fonksiyon yazın. Fonksiyon içerisinde while ve for döngülerinin her ikisini de kullanın.

ucgen(15);
15 sayısı için örnek ekren çıktısı;

O

O O

O O O

O O O O

O O O O O

O O O O O O

O O O O O O O

O O O O O O O O

O O O O O O O O O

O O O O O O O O O O

O O O O O O O O O O O

O O O O O O O O O O O O

O O O O O O O O O O O O O

O O O O O O O O O O O O O O

O O O O O O O O O O O O O O O

O O O O O O O O O O O O O O O O

### Cevap

```html
<?php
    function ucgen($x){
        for ($i=0; $i < $x; $i++) { 
            $a=0;
            while ($a <= $i) {
                $a++;
                echo "*";
            }
            echo "<br>";
        } 
    }
    ucgen(15);
?>
```



## Ödev 2

### Soru

### Cevap

## Ödev 3

### Soru

### Cevap
