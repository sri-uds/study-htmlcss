# 11.1 @import 규칙

```HTML
<LINK> vs @import
구IE에서 @import 는 병렬이 아닌 직렬다운로드를 야기함 -> 속도저하 -> 망함
구IE에서 @import 는 다운로드 순서가 꼬임 -> 스크립트등 실행시 오류발생 가능성 있음 -> 망함

결론 : 걍 <LINK> 쓰자.
```



# 11.2 @font-face 규칙


  * woff를 제외하고 gzip으로 압축
  * 동기식
  
    ```HTML
    <script src="//ajax.googleapis.com/ajax/libs/webfont/1.4.10/webfont.js"></script>
    <script type="text/javascript">
      WebFont.load({
        google: { // For google fonts
          families: ['Droid Sans', 'Droid Serif']
        }
        custom: { // For early access or custom font
          families: ['Nanum Gothic'],
          urls: ['http://fonts.googleapis.com/earlyaccess/nanumgothic.css']
        }
      });
    </script>
    ```
  * 비동기식 - FOUT 발생할수 있음
  
    ```javascript
      WebFontConfig = {
        custom: {
            families: ['Nanum Gothic'],
            urls: ['http://fonts.googleapis.com/earlyaccess/nanumgothic.css']
        }
      };
      (function() {
        var wf = document.createElement('script');
        wf.src = ('https:' == document.location.protocol ? 'https' : 'http') +
          '://ajax.googleapis.com/ajax/libs/webfont/1.4.10/webfont.js';
        wf.type = 'text/javascript';
        wf.async = 'true';
        var s = document.getElementsByTagName('script')[0];
        s.parentNode.insertBefore(wf, s);
      })(); 
    ```
    
# 11.3 @media

## Media Type

<table class="w3-table-all notranslate">
  <tbody><tr>
    <th style="width:25%">Value</th>
    <th>Description</th>
  </tr>  
  <tr>
    <td>all</td>
    <td>Used for all media type devices</td>
  </tr>
  <tr>
    <td>aural</td>
    <td><span class="deprecated">Deprecated.</span> Used for speech and sound synthesizers</td>
  </tr>
  <tr>
    <td>braille</td>
    <td><span class="deprecated">Deprecated.</span> Used for braille tactile feedback devices</td>
  </tr>
  <tr>
    <td>embossed</td>
    <td><span class="deprecated">Deprecated.</span> Used for paged braille printers</td>
  </tr>
  <tr>
    <td>handheld</td>
    <td><span class="deprecated">Deprecated.</span> Used for small or handheld devices</td>
  </tr>
  <tr>
    <td>print</td>
    <td>Used for printers</td>
  </tr>
  <tr>
    <td>projection</td>
    <td><span class="deprecated">Deprecated.</span> Used for projected presentations, like slides</td>
  </tr>
    <tr>
    <td>screen</td>
    <td>Used for computer screens, tablets, smart-phones etc.</td>
    </tr>
  <tr>
    <td>speech</td>
    <td>Used for screenreaders that "reads" the page out loud</td>
  </tr>
  <tr>
    <td>tty</td>
    <td><span class="deprecated">Deprecated.</span> Used for media using a fixed-pitch character grid, like teletypes and terminals</td>
  </tr>
  <tr>
    <td>tv</td>
    <td><span class="deprecated">Deprecated.</span> Used for television-type devices</td>
  </tr>
</tbody></table>

## Media Features

<table class="w3-table-all notranslate">
  <tbody><tr>
    <th style="width:25%">Value</th>
    <th>Description</th>
  </tr>  
    <tr>
    <td>aspect-ratio</td>
    <td>The ratio between the width and the height of the viewport</td>
    </tr>
	<tr>
    <td>color</td>
    <td>The number of bits per color component for the output device</td>
    </tr>
	<tr>
    <td>color-index</td>
    <td>The number of colors the device can display</td>
    </tr>
	<tr>
    <td>device-aspect-ratio</td>
    <td>The ratio between the width and the height of the device</td>
    </tr>
	<tr>
    <td>device-height</td>
    <td>The height of the device, such as a computer screen</td>
    </tr>
	<tr>
    <td>device-width</td>
    <td>The width of the device, such as a computer screen</td>
    </tr>
	<tr>
    <td>grid</td>
    <td>Whether the device is a grid or bitmap</td>
    </tr>
	<tr>
    <td>height</td>
    <td>The viewport height</td>
    </tr>
	<tr>
    <td>max-aspect-ratio</td>
    <td>The maximum ratio between the width and the height of the 
	display area</td>
    </tr>
	<tr>
    <td>max-color</td>
    <td>The maximum number of bits per color component for the output device</td>
    </tr>
	<tr>
    <td>max-color-index</td>
    <td>The maximum number of colors the device can display</td>
    </tr>
	<tr>
    <td>max-device-aspect-ratio</td>
    <td>The maximum ratio between the width and the height of the 
	device</td>
    </tr>
	<tr>
    <td>max-device-height</td>
    <td>The maximum height of the device, such as a computer screen</td>
    </tr>
	<tr>
    <td>max-device-width</td>
    <td>The maximum width of the device, such as a computer screen</td>
    </tr>
	<tr>
    <td>max-height</td>
    <td>The maximum height of the display area, such as a browser 
	window</td>
    </tr>
	<tr>
    <td>max-monochrome</td>
    <td>The maximum number of bits per "color" on a monochrome (greyscale) device</td>
    </tr>
	<tr>
    <td>max-resolution</td>
    <td>The maximum resolution of the device, using dpi or dpcm</td>
    </tr>
	<tr>
    <td>max-width</td>
    <td>The maximum width of the display area, such as a browser 
	window</td>
    </tr>
	<tr>
    <td>min-aspect-ratio</td>
    <td>The minimum ratio between the width and the height of the 
	display area</td>
    </tr>
	<tr>
    <td>min-color</td>
    <td>The minimum number of bits per color component for the output device</td>
    </tr>
	<tr>
    <td>min-color-index</td>
    <td>The minimum number of colors the device can display</td>
    </tr>
	<tr>
    <td>min-device-aspect-ratio</td>
    <td>The minimum ratio between the width and the height of the 
	device</td>
    </tr>
	<tr>
    <td>min-device-width</td>
    <td>The minimum width of the device, such as a computer screen</td>
    </tr>
	<tr>
    <td>min-device-height</td>
    <td>The minimum height of the device, such as a computer screen</td>
    </tr>
	<tr>
    <td>min-height</td>
    <td>The minimum height of the display area, such as a browser 
	window</td>
    </tr>
	<tr>
    <td>min-monochrome</td>
    <td>The minimum number of bits per "color" on a monochrome (greyscale) device</td>
    </tr>
	<tr>
    <td>min-resolution</td>
    <td>The minimum resolution of the device, using dpi or dpcm</td>
    </tr>
	<tr>
    <td>min-width</td>
    <td>The minimum width of the display area, such as a browser 
	window</td>
    </tr>
	<tr>
    <td>monochrome</td>
    <td>The number of bits per "color" on a monochrome (greyscale) device</td>
    </tr>
	<tr>
    <td>orientation</td>
    <td>The orientation of the viewport (landscape or portrait mode)</td>
    </tr>
	<tr>
    <td>overflow-block</td>
    <td>How does the output device handle content that overflows the viewport 
	along the block axis (added in Media Queries Level 4)</td>
    </tr>
	<tr>
    <td>overflow-inline</td>
    <td>Can content that overflows the viewport along the inline axis be 
	scrolled (added in Media Queries Level 4)</td>
    </tr>
	<tr>
    <td>resolution</td>
    <td>The resolution of the output device, using dpi or dpcm</td>
    </tr>
	<tr>
    <td>scan</td>
    <td>The scanning process of the output device</td>
    </tr>
	<tr>
    <td>update-frequency</td>
    <td>How quickly can the output device modify the appearance of the content 
	(added in Media Queries Level 4)</td>
    </tr>
	<tr>
    <td>width</td>
    <td>The viewport width</td>
    </tr>
</tbody></table>

# 11.4 반응형 웹

코드 11-18 과의 차이점
```css

/* 0 ~ 767 */
.box {display:block;}  

/* 768 ~ 959 */
@media screen and(min-width : 768px) {  
.box {float:left;background:red;}
}

/* 961 ~ */
@media screen and(min-width : 960px) {
.box {float:none;} 
}

```
