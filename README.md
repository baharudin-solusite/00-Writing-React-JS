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

### **State & Props**
Ada 2 unsur penting dalam component yaitu UI (User Interface) & Data.

Type data pada component react itu cuma dua yaitu Prop dan State.Dari sisi programming component react itu dibuat dengan function atau class

**lalu apa bedanya function dan class pada component?**

- Untuk sekarang ingat saja functional component tidak memiliki state, itu sebabnya barang ini biasa disebut stateless component.
- Sedangkan class component bisa memiliki prop dan state.

**Pembahasan State & Props**



## 3. React State
---


## 4. React useEffect
---
## 5. Reach Router
---