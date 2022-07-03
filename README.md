# Writing React JS

1. Introduction React JS
2. React Component
3. React State
4. React useEffect
5. Reach Router

## 1. Introduction React JS
---
### **Apa itu React JS ?**
React JS adalah sebuah library JavaScript yang dibuat untuk membangun user interface

**Bagaiman langkah-langkah ingin menggunakan React JS ?**
1. Pertama diwajibkan menginstal [note.js](https://nodejs.org/en/) terlebih dahulu.
2. Buatlah folder baru untuk meletakan file react Js nantinya.
3. buka CMD Ketik format untuk menginstall react: **npm install -g create-react-app nama-folder**
4. Untuk mengecek kesuksesan proses instalasinya, Anda bisa cek versi reactnya dengan mengetik:
**create-react-app –version** 
5. lalu ketik **cd nama-folder** lalu jalankan react js dengan format **npm start**
---
   
![](https://lh4.googleusercontent.com/6zWPjk-LerhmW5tC2tjyG_V5M2nw3BOvQ3kfTiHzIZC0uCsN50WtYO3iewCsw-yj_8ZwLe37_4t429PKVt2D14aVNZa4a2ZZguj80Ew5ZXn3nxWNceLKLoe0uyT9rRccp9Rg1I1i)

### **Cara kerja React JS**

- index.js
```js
// import file css
import './App.css';
// Penggunaan Export dam Import
import ExportHalaman from './components/ExportHalaman';
// Import local img
import BurungHatu from "./img/burung-hantu.jpg"
function App() {
  // tempat membuat Variabel sebelum return
  let pulang = "ke kampung halaman";
  const perkalian = 9 * 9;
  // event internal
  const handleClick = () => {
    console.log("burung hantu")
  };
  // conditional
  const isLogin = true
  // Map
  const data = [
    {
      orang: "Arrie",
    },
    {
      orang: "Baharudin",
    },
    {
      orang: "Mirza"
    }];

  return (
    // JSX
    // react membutuhkan pembunggkus untuk parentnya
    <div className="App">
      <header className="App-header">
        {/* import halaman */}
        <ExportHalaman />

        {/* url image */}
        <img width={200} src="https://rimbakita.com/wp-content/uploads/2019/01/burung-hantu.jpg" alt='Burung Hantu' />

        {/* local image */}
        <br />
        <img width={200} src={BurungHatu} alt='Burung Hantu' />


        {/* Penggunaan class pada React yaitu menggunakan ClassName */}
        <h3 className='nama'>Baharudin</h3>

        {/* Curly Braces in JSX */}
        <h2> {7 + 7} </h2>

        {/* Variabel harus dipanggil Terlebih dahulu */}
        <h4> {pulang} </h4>
        <h3> {perkalian} </h3>
        <p> {"surabaya".toUpperCase()} </p>

        {/* Event */}
        {/* Pembuatan Button secara inlane */}
        <button onClick={() => console.log("inlane Button")}>Inlane Button</button>
        <br />
        <button onClick={() => console.log("ayam goreng")}>tekan</button>

        {/* pembuattan button secara internal */}
        <br />
        <button onClick={handleClick}>Tes</button>

        {/* checkbox */}
        <br />
        <input type={"checkbox"} onChange={() => console.log("ayam")} />

        {/* input form */}
        <br />
        <input type={"text"} onChange={(event) => console.log(event.target.value)} />


        <br />
        {/* conditional */}
        {/* satu - satunya codisional yang bisa dipakai pada React Js Ternary operator */}
        {isLogin ? <p>sudah login</p> : <p>belum login</p>}


        {/* maping menampilkan Array of object */}
        {data.map((item, index) => (
          <h1 key={index}>{item.orang}</h1>
        ))}
      </header>
    </div>
  );
}

export default App;

```
- ExportHalaman.jsx
```js
import React from 'react'

function ExportHalaman() {
    return (
        <div>
            <h2>ExportHalaman</h2>
        </div>
    )
}

export default ExportHalaman
```

- Tampilan pada Browser
  
![](./image/React%20App.png)

![](./image/Event.jpeg)

## 2. React Component
---

### **Apa sih react component itu ?**

Component adalah potongan kode kecil yang dapat di gunakan kembali (reusable) yang bertujuan agar user interface terpisah menjadi bagian-bagian kecil dan di satukan dan di render menjadi sebuah kode HTML.


**Penggunan Component**

*ilustrasi*
![](./image/component.png)

### **Membuat sebuah komponen**
Membuat sebuah component pada React kita memerlukan sebuah folder component bertujuan agar file component nantinya tersusun rapi 

Dalam pembuatan folder,file,dan function component harus menggunakan huruf besar diawal

![](./image/penulisanComponent.jpeg)


### **Stateful dan Stateless Component**


**Stateless Component**

Web atau aplikasi yang tidak membutuhkan perubahan state/ keadaan seperti pengunaan  table dan button.

**Stateful Component**

web atau aplikasi yang membutuhkan perubahan state/keaadaan seperti benner dan form


### **State & Props**
Ada 2 unsur penting dalam component yaitu UI (User Interface) & Data.

Type data pada component react itu cuma dua yaitu **Prop dan State**.Dari sisi programming component react itu dibuat dengan function atau class

**lalu apa bedanya function dan class pada component?**

- Untuk sekarang ingat saja functional component tidak memiliki state, itu sebabnya biasa disebut stateless component.
- Sedangkan class component bisa memiliki prop dan state.



### **Props Component**

App.js
```jsx
import "./App.css";
import Course from "./component/Course/Course";
const App = () => {
  return (
    // JSX
    <div className="App">
      <header className="App-header">
        // data dipanggil
        <Course />

      </header>
    </div>
  );
};

export default App;
```
CourseCard.jsx
```js
import React from 'react'

// pemberian props pada parameter sebagai jalur sebuah data yang dikirim dari file lain
// props berfungsi untuk mengoper sebuah data seperti (title,detail)
const CourseCard = (props) => {
    return (
        <div style={{ display: "flex" }}>
            <div>
                <iframe width="400" 
                height="200" src={`https://www.youtube.com/embed/${props.embedId}`} 
                title="YouTube video player" 
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" />
            </div>
            <div style={{ textAlign: "left", marginLeft: "20px" }}>
                <h4>{props.title}</h4>
                <p>{props.detail}</p>
            </div>
        </div>
    )
}

export default CourseCard;

```
Course.js
```jsx
import React from 'react'
import CourseCard from './CourseCard'
function Course() {
    return (
        <div>
            <h2>Course</h2>
            <div style={{ display: "flex", padding: '50px' }}>
                {/* Props adalah Properti */}
                {/* props disini sebagai pengirim sebuah data */}
                <CourseCard title="Warriors | Season 2020 Cinematic" 
                detail="League of Legends (ft. 2WEI and Edda Hayes)" 
                embedId="aR-KAldshAE" />

                <CourseCard title="Cara deploy aplikasi NodeJS ke HEROKU dari 0 sampai berhasil" 
                detail="Tutorial  NodeJS ke HEROKU"
                embedId="WY6eVl8FzTg" />
                {/* <CourseCard /> */}

            </div>

        </div>
    )
}

export default Course;
```
### hasil Props
![](./image/Props.jpeg)

## 3. React State
---
state adalah data yang dimiliki sebuah component dan data tersebut dapat berubah atau dapat di update kembali. 

Data apa saja yang berubah pada sebuah web atau aplikasi?

data yang selalu berubah yaitu benner,input form, card produk, contact dll, yang bersifat data 

### **useState**
useState, adalah fitur dari React untuk membuat sebuah state pada functional component

**cara sederhana useState Hooks**
1. import useState dari react 
   ```js
   import {useState} from "react";
   ```
2. menuliskan userState hooks
   ```js
    const [nama, setNama] = useState("Baharudin");
   ```
3. memanggil data useState
   ```js
   <h3>{nama}<h3>
   ```
**Membuat Menu keranjang nama produk dan Counter**

- App.js
```js
// import useState
import { useState } from 'react';
// import Cartitem
import Cartitem from './component/Cartitem';
function App() {
  // menuliskan useState hooks
  // fungsi penulisan (setNama) untuk mengubah data (nama)
  const [nama, setNama] = useState("Baharudin")
  // membuat data menjadi array agar mudah dibaca
  const [hewan] = useState([
    "Monyet", "Srigala", "Kura-Kura", "Hiu", "kucing"
  ])

  return (
    <div>
      {/* memanggil useState */}
      {/* bila di tekan akan berubah namanya */}
      <h2 onClick={() => setNama("Fahrul")}>{nama}</h2>

      {/* loping data dengan map colback */}
      {hewan.map((item, index) => (
        <Cartitem key={index} hewan={item} />
      ))}

      {/* perbanyak sebuah data manual */}
      <Cartitem hewan="Monyet" />
      <Cartitem hewan="Srigala" />
      <Cartitem hewan="Kura-Kura" />
    </div>
  );
}

export default App;

```
- Couter.js
```js
import React from 'react'
import { useState } from 'react';

function Counter() {
    /* membuat sebuah state */
    const [count, setCount] = useState(0)

    const decrement = () => {
        if (count > 0) {
            setCount(count - 1)
        }
    }

    return (

        <div>
            {/* membuat sebuah state */}
            {/* membuat sebuah couter bagaimana nantinya nilai yang dihasilkan tidak minus */}
            <button onClick={decrement}>-</button>
            <span> {count} </span>
            <button onClick={() => setCount(count + 1)}>+</button>
        </div>
    )
}

export default Counter
```

- Cartitem.js
```js
import React from 'react'
import Counter from './Counter'
function Cartitem(props) {
    return (

        /* membuat item cart */
        <div style={{ display: "flex" }}>
            <span>{props.hewan}</span>
            {/* Jumlah */}
            <Counter />
        </div>
    )
}

export default Cartitem

```

![](./image/State%20Hooks.jpeg)
## 4. React useEffect
---


## 5. Reach Router
---