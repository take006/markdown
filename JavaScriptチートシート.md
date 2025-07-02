# クリックイベント
ボタンや特定のHTMLクラス要素などをマウスでクリックした場合の動作を指定する。
* クリックしたらバーガーメニューを表示する
* ポップアップ表示


## 「投稿」ボタンを押すとポップアップ表示される

### const 変数名 = document.querySelector(".クラス名");
まず動的に変更したい対象のHTMLクラス名を定数に格納する。

### 定数名.eventListener("click", function(){　処理内容　});
クリックイベントの定型文
querySelcetorで定義した定数（対象のHTMLクラス）に対して、クリックイベント処理を記述する。クリックしたら、『display:none;』⇒『display:block;』にするなどポップアップ表示などに使用できる。

### 定数名.forEach(定数名？) => {}
配列要素を個々に取り出して処理する定型文


```js
const topSections = document.querySelectorAll(".top-section");

topSections.forEach((topSection) => {
	topSection.addEventListener("click", function(){
		alert("テストです。");
	});
});
```

## トグルボタン(表示・非表示を切り替える)を押すと詳細文章が表示される
classList.toggle("クラス名");
HTMLクラスの付け外し定型文
### ①this.nextSiblig.classList.toggle("active");
『this=top-sectionクラス』それぞれを表します。
『nextSibling』はtop-sectionと並列の要素を表しています。
「『top-section』クラスの並列要素『～』にactiveクラスを付与する」という意味になります。

### ②this.children[1].classList.toggle("rotate");
『this=top-sectionクラス』それぞれを表します。
『children』はtop-sectionの子要素を表しています。
「『top-section』クラスの子要素『～』にrotateクラスを付与する」という意味になります。

```diff_javascript
topSections.forEach((topSection) => {
	topSection.addEventListener("click", function(){
		this.nextElementSibling.classList.toggle("active");
		this.children[1].classList.toggle("rotate");
	});
});
```

## ハンバーガーメニュー
nav-click-container⇒none
no-show⇒非表示のnoneが消されて、blockのように表示される

```diff_javascript
const navClickContainer = document.querySelector(".nav-click-container");

const navContentContainer = document.querySelector(".nav-content-container");

const navClickBorder1 = document.querySelector(".nav-click-container .nav-click-border-1");

const navClickBorder2 = document.querySelector(".nav-click-container .nav-click-border-2");

const navClickBorder3 = document.querySelector(".nav-click-container .nav-click-border-3");

console.log(navClickContainer);
console.log(navContentContainer);
console.log(navClickBorder1);
console.log(navClickBorder2);
console.log(navClickBorder3);
//document.querySelectorで指定した要素が正常に取得できているかconsole.logで出力して確認

navClickContainer.addEventListener("", function(){
	//alert("テストです");
	//動作確認を行う
	navContentContainer.classList.toggle("no-show");
	navClickBorder2.classList.toggle("no-show");
		navClickBorder1.classList.toggle("transform");
		navClickBorder3.classList.toggle("transform");
});
```

## スクロールすると「メルマガ登録」ボタンが画面下に表示される
window.addEventListener('scroll', function(){})
windowはブラウザを操作します。scrollを指定すると画面のスクロール量に応じた変化を定義できる。

```diff_javascript

const scrollContainer = document.querySelector('.scroll-container');

console.log(scrollContainer);

window.addEventListener('scroll', function() {
  if (window.scrollY > 200) {
    // alert('200px以上スクロールしました！');
    scrollContainer.classList.remove('no-show');//removeするので表示されるようになる
    //定数名orクラス名orID名.classList.remove('クラス名') = クラスを削除する動作を実行する
  } else {
    scrollContainer.classList.add('no-show');//no-showをadd（付与）するので非表示になる
  }
});
//windowはブラウザを操作する


```

## スクロールするとふわっと要素が表示される(scrollEvent)

```diff_javascript

content-container {}
content-container.active {}
```


# スクロール

## 要素が画面内に入った際にフェードインしてくる(scrollEvent_2)

if (window.scrollY > (value.getBoundingClientRect().top + 250) + window.scrollY - window.innerHeight)
『これで要素が画面に入って」から250px進んだ場合』として条件を設定

```diff_javascript
const contentContainers = document.querySelectorAll('.content-container');

console.log(contentContainers);

window.addEventListener('scroll', function() {
  contentContainers.forEach(function(value) {
    if (window.scrollY > (value.getBoundingClientRect().top + 250) + window.scrollY - window.innerHeight) {
      value.classList.add("active");
    } else {
      value.classList.remove("active");
    }
  });
});

```
# スライドショー

## ボタンスライドショー
ボタンを押してスライドするタイプを実装します。ループ設定は無し。
※レスポンシブ対応

```diff_javascript

const buttonRight = document.querySelector('.button-right'); 
const buttonLeft = document.querySelector(.button-left'); 
それぞれボタンを押した際にCSSが変更されるようにしたいので、ボタンの要素を定数に格納する
const imgContainer = document.querySelector('.img-container'); 
const imgs = document.querySelectorAll('.img-container img'); 
画像の外側、画像の中身も変数に格納する
//containerは横移動に使用して、imgsは画像の数をlengthでカウントするのに使用する
let count = 0; 
// 変数countは「0」から数え始めるように定義する

console.log(buttonRight); 
console.log(buttonLeft); 
console.log(imgContainer); 
console.log(imgs);
console.log(count); 

buttonRight.addEventListener('click', function() { // 右ボタンをクリックした時
    count++; // カウントを1増やす
    imgContainer.style.transform = `translateX(${-count * 600}px)`; // 画像を移動する
    if (count >= imgs.length -1 ) { //imgs.lengthは画像の数を表す。１から開始される。変数countが０から数え始めるので、-1する。
        buttonRight.style.display = 'none'; // 右ボタンを非表示にする。今回は3以上になると非表示になる
    }
    buttonLeft.style.display = 'block'; // 左ボタンを表示する
    var windowWidth = window.innerWidth; // ウィンドウの幅を取得する
    if (windowWidth < 600) { // ウィンドウの幅が600px未満の場合、移動するpx数も異なるためレスポンシブ対応させる
        imgContainer.style.transform = `translateX(${-count * 250}px)`; // 画像を移動する
    }
});

buttonLeft.addEventListener('click', function() { // 左ボタンをクリックした時
  count--;//デクリメント演算子
  imgContainer.style.transform = `translateX(${-count * 600}px)`; // 画像を移動する
  if (count === 0) { //もし変数countの値が0になったら
    buttonLeft.style.display = 'none'; // 左ボタンを非表示にする
  }
  buttonRight.style.display = 'block'; //一番左にきたら右に行くしか無いので、右ボタンを表示する
  if (windowWidth < 600) { // ウィンドウの幅が600px未満の場合
    imgContainer.style.transform = `translateX(${-count * 250}px)`; // 画像を移動する
  }
});

```

## スライドショー
自動的に画像がスライドします。
setInterval＝繰り返し処理
forEach＝１つ１つに対して動作する
value＝
index＝要素の数？
count＝変数のため++すると１ずつ増加する。--は1ずつ減少する。


```diff_javascript
const slideShowContent = document.querySelectorAll(".slideshow-content");
//html要素を複数取得する
let count = 1;
//countを「１」として設定すると要素の計算が０から始まるので
//countを「０」として設定することもできるが、
//countを「１」として設定することで、activeが最初から付与されたcontentも最初から表示させることができる
//要は開始する際は、ループ処理の例外となるため、それを考慮してcountを1から始めるように設定している

console.log(slideShowContent);
console.log(count);

//setIntervalは動作を繰り返す（６０００＝6秒間隔で）
setInterval(function(){
  if(count > 2){
    count = 0;//countが2より上（3以上）になったら0に戻す
  }
  slideShowContent.forEach(function(value, index){//forEachでimgsの要素を1つ1つ取り出す
    console.log(value);
    console.log(index);
    //要素の番号は０～２
    slideShowContent[index].classList.remove("active");//removeは削除する
  });
  //3以上は画像枚数が足りない
  slideShowContent[count].classList.add("active");
  //一番最初に6秒を経過した時はslideShowContent[1]になる。countが1から始まるので。
  count++;//+1の省略表記
}, 6000);



```


## タイトル

```diff_javascript

source code

```