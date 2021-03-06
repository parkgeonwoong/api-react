# ๐ ์ธ๋ถ API

- ์ธ๋ถ API๋ฅผ ์ฐ๋ํ์ฌ ๋ด์ค ๋ทฐ์ด ๋ง๋ค์ด๋ณด๊ธฐ
- ๋น๋๊ธฐ์์์ ๋ฐฐ์ ์ฐ์ตํด๋ณด๊ธฐ

<br>

## โ ๋น๋๊ธฐ์์

- ์ฝ๋ฐฑ ํจ์๋ฅผ ์ด์ฉ
- Promise
- async/await -> try/catch
- axios

<br>

## โ ์งํ๋

1. ๋น๋๊ธฐ ์์ ์ดํด
2. axios๋ก API ํธ์ถํด์ ๋ฐ์ดํฐ ๋ฐ์์ค๊ธฐ
3. newsapi ํค ๋ฐ๊ธ๋ฐ๊ธฐ (https://newsapi.org/)
4. ๋ด์ค ๋ทฐ์ด UI ๋ง๋ค๊ธฐ
5. ๋ฐ์ดํฐ ์ฐ๋ํ๊ธฐ
6. ์นดํ๊ณ ๋ฆฌ ๊ธฐ๋ฅ ๊ตฌํํ๊ธฐ
7. ๋ฆฌ์กํธ ๋ผ์ฐํฐ ์ ์ฉ

<br>

### Promise

```javascript
const promise = new Promise((resolve, reject) => {
    // resolve: ์ฑ๊ณต, reject: ์คํจ
    setTimeout(() => {
        ์ํ ๋ณํ
        if ( ์๋ฌ ์กฐ๊ฑด ){
            const e = new Error('error')
            return reject(e)
        }
        resolve(์ํ๋ณํ)
    }, 1000)
})

ํจ์().then(() => {
    // .then์ ์ฌ์ฉํ์ฌ ๊ทธ ๋ค์ ์์์ ์ค์ 
})
```

<br>

### async/await

- Promise๋ฅผ ์ ์ธํ๊ณ  ์ฌ์ฉํ  ๋ ํด๋น ํจ์ ์์ await ํค์๋ ์ฌ์ฉ

```javascript

const function = async () => {
    try {
        let result = await PromiseFunction()
        result = await PromiseFunction()
    } catch (e) {
        console.log(e)
    }
}

```

<br>

## axios

```bash
npm i axios
```

<br>

```javascript
const [data, setData] = useState(null);
const onClick = () => {
  axios.get("http://...").then((response) => {
    setData(response.data);
  });
};
```

```javascript
const [data, setData] = useState(null);
const onClick = async () => {
  try {
    await axios.get("http://...");
    setData(response.data);
  } catch (e) {
    console.log(e);
  }
};
```

<br>

## Context API

- ์ ์ญ์ ์ผ๋ก ์ฌ์ฉํ  ๋ฐ์ดํฐ๊ฐ ์์ ๋ ์ ์ฉํ๋ค
- ๋ ๋ง์ ์ปดํฌ๋ํธ๋ฅผ ๊ฑฐ์น  ๊ฒฝ์ฐ ๊ด๋ฆฌ๊ฐ ํ๋ค๋ค -> ๊ทธ๋ฌ๊ธฐ์ ์์ฝ๊ฒ ๊ด๋ฆฌ

<br>

- **์์ฑ**

```jsx
// color.js
import { createContext } from "react";

const ColorContext = createContext({ color: "black" });

export default color;
```
