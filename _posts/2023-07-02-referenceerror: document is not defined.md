---
layout: post
title:  "document is not defined"
---
node.js 사용도중 referenceerror: document is not defined 오류가 나왔다.
이 오류는 html의 <script> 실행할경우 document 객체를 javascript 실행해 준다. 
그럼으로 브라우저에서 제공하는 API에 접근할 수 있다.
하지만 node.js 환경에서는 document 객체와 같은 브라우저 API가 제공되지 않는다.
Node.js의 서버 측 코드 형식으로 작성해야 한다.
```
<!DOCTYPE html>
<html>
<head>

</head>
<body>
<script>
  const images = document.querySelectorAll('#image-container img');

// addEventListener로 클릭 이벤트를 등록합니다.
images.forEach((image, index) => {
  image.addEventListener('click', () => {
    selectImage(index);
  });
});
</script>
</body>
</html>
```
html의 사용이면 정상작동 한다.
```
ReferenceError: document is not defined
```
하지만 js파일에서 html의 코드를 실행시 위 코드가 터미널에 나오는 것을 볼 수 있다.
