# PHP - patika.dev - Soru ve Cevapları
>**[patika.dev](https://app.patika.dev/courses/php-temel) platformu PHP öğrenme amaçlı soruların cevaplanması projesidir.** \
> **Profil için tıklayınız: [app.patika.dev/nmelihkutlu](https://app.patika.dev/nmelihkutlu)**


![](https://github.com/nmelihkutlu/patikaPHP/blob/main/patikaPHP.png)



[Ödev1 Fonksiyonlar](#ödev-1) - [Ödev2 Dizi Fonksiyonları](#ödev-2) - [Ödev3 Form İşlemleri](#ödev-3)

## Ödev 1
Fonksiyonlar

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
Dizi Fonksiyonları

### Soru

Verilen dizideki boş elemanları temizleyerek belirtilen adette rastgele değerlerden dizi oluşturan bir fonksiyon yazın. (array_map(), array_filter() ve array_rand() fonksiyonlarını kullanarak.)

Örnek:
```html
$planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune", "", "", NULL];

print_r(sizinFonksiyonunuz($planets, 2));
print_r(sizinFonksiyonunuz($planets, 3));
print_r(sizinFonksiyonunuz($planets, 2));
print_r(sizinFonksiyonunuz($planets, 4));
print_r(sizinFonksiyonunuz($planets, 5));
```

Ekran Çıktısı;
```html
Array
(
    [0] => Venus
    [1] => Mars
)
Array
(
    [0] => Earth
    [1] => Jupiter
    [2] => Uranus
)
Array
(
    [0] => Mars
    [1] => Uranus
)
Array
(
    [0] => Venus
    [1] => Earth
    [2] => Jupiter
    [3] => Neptune
)
Array
(
    [0] => Mercury
    [1] => Earth
    [2] => Saturn
    [3] => Uranus
    [4] => Neptune
)
```

### Cevap

Yazdığım kod:
```html
<?php
echo "<pre>";

$planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune", "", "", NULL];
print_r(planetSelector($planets,2));
print_r(planetSelector($planets,3));
print_r(planetSelector($planets,2));
print_r(planetSelector($planets,4));
print_r(planetSelector($planets,5));

function planetSelector($arr,$x=2){
    asort($arr);
    return array_slice(array_filter($arr),0,$x);
}
?>
```

Ekran çıktısı:
```html
Array
(
    [0] => Earth
    [1] => Jupiter
)
Array
(
    [0] => Earth
    [1] => Jupiter
    [2] => Mars
)
Array
(
    [0] => Earth
    [1] => Jupiter
)
Array
(
    [0] => Earth
    [1] => Jupiter
    [2] => Mars
    [3] => Mercury
)
Array
(
    [0] => Earth
    [1] => Jupiter
    [2] => Mars
    [3] => Mercury
    [4] => Neptune
)
```

## Ödev 3
Form İşlemleri

### Soru
1. Kullanıcıdan sayı değeri alabileceğiniz bir form hazırlayın.
2. Gelen sayı değerlerinin 3 ile bölümünden kalanın 0 olup olmadığını kontrol eden bir fonksiyon yazın.
3. Kullanıcıya girilen değerin 3 bölünebilirliğini, bölünemiyorsa bölünebilen ilk değeri kullanıcıya bildirin.
4. Boş değer gönderilirse değerin boş olmayacağını bildirin.

Örnek:
- Girilen Sayı : 4
- Girdiğiniz sayı 3'e bölünemez. Bölünebilecek ilk sayı 6'dır.


### Cevap

Yazılan kod aşağıdaki gibidir:

```html
<form action="<?= $_SERVER["PHP_SELF"]; ?>" method="get">
    <label for="number">Sayı Giriniz:</label>
    <input type="number" name="number">
    <input type="submit" value="Gönder">
</form>

<?php
if (!empty($_GET["number"])) {
    echo ucunkati($_GET["number"]);
} else echo "Boş değer girdiniz.";

function ucunkati($number)
{
    $r = $number % 3;
    if ($r == 0) {
        return "Girilen sayı: " . $number;
    } else {
        return "Girdiğiniz sayı 3'e bölünemez. Bölünebilecek ilk sayı " . $number + (3 - $r) . "'dir.";
    }
}
?>
```
