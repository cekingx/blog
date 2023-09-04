---
tags:
  - todo
  - <language>
title: "Cara Setup Private Key Untuk Deploy Ke Jaringan Mumbai"
date: 2023-09-04T21:07:23+08:00
draft: false
author: "Dirga Yasa"
showToc: true
TocOpen: false
hidemeta: false
comments: true
hideSummary: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
summary:
---

## Pendahuluan
Jika kita melakukan pengambangan smart contract di local misalnya hardhat, maka kita bisa melakukan deployment smart contract ke local node dengan menjalankan perintah `npx hardhat node`. Selain disediakan node, kita juga telah disediakan account(private key) yang telah memiliki balance dalam jumlah besar yang bisa digunakan untuk membayar gas fee deployment. Namun bagaimana caranya mendapatkan account untuk melakukan deployment pada sebuah jaringan blockchain publik? 

Ada beberapa cara untuk mendapatkan private key, cara yang paling mudah adalah dengan menggunakan wallet sejuta umat yaitu [Metamask](https://metamask.io/). Metamask bisa memberikan kita random seed phrase yang digunakan untuk membuat sebuah private key.

### Download Metamask
Sesuaikan dengan browser yang kalian gunakan. Untuk chrome extension ada [disini](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn)
![1](./asset/1.png)

### Onboarding Metamask
![2](./asset/2.png)
![3](./asset/3.png)
![4](./asset/4.png)

### Buat Password
Pastikan menggunakan password yang kuat dan diingat dengan baik karena tidak ada fitur __Forgot Password__
![5](./asset/5.png)

### Catat Seed Phrase
_Seed Phrase_ adalah secret yang digunakan oleh wallet provider seperti Metamask untuk generate private key. Simpan dan jaga _Seed Phrase_ dengan baik karena jika sampai pihak lain mengetahuinya maka pihak tersebut memiliki akses penuh terhadap private key yang kita miliki.
![6](./asset/6.png)
![7](./asset/7.png)
![8](./asset/8.png)

>
> __Yey kita sudah punya wallet__
>

### Fresh Wallet
Tentu saja saldo kita masih 0 karena baru saja membuat wallet
![9](./asset/9.png)

### Menambahkan Jaringan Mumbai ke Metamask
Hal yang paling mudah menambahkan sebuah jaringan ke metamask adalah melalui block explorer jaringan tersebut. Explorer untuk jaringan Mumbai adalah [https://mumbai.polygonscan.com/](https://mumbai.polygonscan.com/)
![10](./asset/10.png)
Pada pojok kanan bawah biasanya terdapat tombol _Add ... Network_. Klik tombol tersebut, akan ada pop-up untuk konfirmasi apakah yakin menambahkan jaringan tersebut atau tidak
![11](./asset/11.png)
![12](./asset/12.png)
![13](./asset/13.png)
Metamask sudah berhasil menambahkan jaringan mumbai dan membaca balance MATIC yang kita miliki

>
> __Address yang kita miliki terdapat pada tombol `0x72F...478C`__
>

### Request Faucet
Karena kita hanya menggunakan testnet maka kita bisa mendapatkan balance MATIC melalui faucet. Jika kalian menggunakan mainnet maka kalian harus membeli MATIC di exchange dan mengirimnya ke address wallet yang baru saja dibuat.
Faucet Mumbai terdapat pada [https://faucet.polygon.technology/](https://faucet.polygon.technology/)
Ketentuan meminta balance pada faucet berbeda dan berubah seiring waktu, jadi sesuaikan dengan ketentuan yang sedang berlaku
![15](./asset/15.png)
Masukkan address yang kita miliki, konfirmasi dan tunggu beberapa saat
![16](./asset/16.png)
![17](./asset/17.png)
![18](./asset/18.png)
![19](./asset/19.png)

>
> __Yey kita sudah punya balance MATIC sebesar 0.2__
>

### Export Private Key
Untuk bisa menggunakan account tersebut pada hardhat maka kita harus melakukan export private key. Private key inilah yang bisa digunakan untuk melakukan deployment smart contract.
![20](./asset/20.png)
Pilih menu _Account details_
![21](./asset/21.png)
Pilih _Show private key_
![22](./asset/22.png)
Masukkan password
![23](./asset/23.png)

>
> __Selamat kita sudah bisa membuat account yang bisa digunakan untuk deployment smart contract melalui hardhat pada jaringan mumbai__
>

### Penutup
__Seed Phrase__ dan __Private Key__ adalah hal yang sangat rahasia, jaga sebaik-baiknya jangan sampai ada pihak lain yang mengetahuinya.
Semoga bermanfaat :)