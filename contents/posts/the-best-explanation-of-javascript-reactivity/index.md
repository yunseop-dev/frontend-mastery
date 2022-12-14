---
title: "The Best Explanation of JavaScript Reactivity"
description: "The Best Explanation of JavaScript Reactivity"
date: 2018-08-08
update: 2018-08-08
tags:
  - javascript
  - reactivity
---


## The Best Explanation of JavaScript Reactivity π

---

> μ΄ κΈμ μμμμ νλ½μ λ°μ λ²μ­νμμΌλ©°, κΈμ μΆμ²λΒ https://medium.com/vue-mastery/the-best-explanation-of-javascript-reactivity-fea6112dd80dΒ μλλ€.
> 
> 
> κΈ°μ μ΄λ λ²μ­μ λν΄ μκ²¬μ΄ μμΌμλ©΄ λκΈμ λ¨κ²¨μ£Όμλ©΄ λ°μνλλ‘ νκ² μ΅λλ€. κ°μ¬ν©λλ€.
> 

λ§μ νλ‘ νΈμλ μλ°μ€ν¬λ¦½νΈ νλ μμν¬ (μ : Angular, React, and Vue)μλ μμ²΄ λ°μν μμ§μ΄ μμ΅λλ€. λ°μνμ μλ μλ¦¬λ₯Ό μ΄ν΄νλ©΄ κ°λ° κΈ°μ μ ν₯μμν¬ μ μκ³  JavaScript νλ μμν¬λ₯Όλ³΄λ€ ν¨κ³Όμ μΌλ‘ μ¬μ© ν  μ μμ΅λλ€. μλμ μμκ³Ό μν°ν΄μμλ Vue μμ€ μ½λμμ λ³Ό μ μλ κ²κ³Ό λμΌν μ’λ₯μ λ°μν(Reactivity)μ λΉλν©λλ€.

*κΈ°μ¬λ₯Ό μ½λ λμ μ΄ λΉλμ€λ₯Ό λ³΄λ κ²½μ°*Β *[μ΄ μλ¦¬μ¦ μμ](https://www.vuemastery.com/courses/advanced-components/evan-you-on-proxies/)*Β μ λ³΄μΈμ.Β *Vueμ μ°½μμ μΈ Evan Youμ λ°μν λ° νλ‘μλ₯Ό λΌμν©λλ€.*

#### π‘ λ°μν μμ€ν

Vueμ λ°μν μμ€νμ μ²μ μλμν¬ λ λ§μ μ²λΌ λ³΄μΌ μ μμ΅λλ€. μ΄ Vue μ±μ μ΄ν΄λ΄μλ€.

![https://cdn-images-1.medium.com/max/1600/1*aLjr0oQBzX7PoUF6oL7yfQ.png](https://cdn-images-1.medium.com/max/1600/1*aLjr0oQBzX7PoUF6oL7yfQ.png)

![https://cdn-images-1.medium.com/max/1600/1*neR2Y-0zJseWT8oY1JukXA.png](https://cdn-images-1.medium.com/max/1600/1*neR2Y-0zJseWT8oY1JukXA.png)

VueλΒ `price`Β κ°μ΄ λ°λλ©΄ μΈ κ°μ§ μμμ νκ² λ©λλ€.

- μΉ νμ΄μ§μμΒ `price`κ°μ μλ°μ΄νΈ
- `price`Β ``Β `quantity`λ₯Ό κ³±νλ ννμμ λ€μ κ³μ°νκ³  νμ΄μ§λ₯Ό μλ°μ΄νΈ
- `totalPriceWithTax`Β ν¨μλ₯Ό λ€μ νΈμΆνκ³  νμ΄μ§λ₯Ό μλ°μ΄νΈ

μ¬κΈ°μ κΆκΈμ¦μ΄ μκΈ°μ€νλ°μ,Β `price`κ° λ°λλ©΄ Vueλ λ¬΄μμ μλ°μ΄νΈ ν΄μΌ νλμ§λ₯Ό μ΄λ»κ² μ μ μμΌλ©°, μ΄λ»κ² μ λΆ μΆμ  ν  μ μμκΉμ?

![https://cdn-images-1.medium.com/max/1600/1*t8enMn6h0gjY6HNKoSVC1g.jpeg](https://cdn-images-1.medium.com/max/1600/1*t8enMn6h0gjY6HNKoSVC1g.jpeg)

**μ΄λ μλ°μ€ν¬λ¦½νΈ νλ‘κ·Έλλ°μ΄ μ μμ μΌλ‘ μλνλ λ°©μμ΄ μλλλ€**

μ΄ λ§μ΄ λͺννκ² λκ»΄μ§μ§ μμΌμλ€λ©΄, μ°λ¦¬κ° λ€λ£° μμ μ νλ‘κ·Έλλ°μ΄ λκ° μ΄λ° μμΌλ‘ μλνμ§ μλλ€λ μ μλλ€. μλ₯Ό λ€μ΄μ μλ μ½λλ₯Ό μ€ννλ©΄ λ€μκ³Ό κ°μ΅λλ€.

![https://cdn-images-1.medium.com/max/1600/1*RrDCv_fUYnOl34Eq0afgYw.png](https://cdn-images-1.medium.com/max/1600/1*RrDCv_fUYnOl34Eq0afgYw.png)

μ΄λ€ κ°μ΄ λμ¬κ±° κ°λμ? Vueλ₯Ό μ¬μ©νλκ²μ΄ μλλ―λ‘Β `10`μ λνλΌ κ²λλ€.

![https://cdn-images-1.medium.com/max/1600/1*q7nHV9seYErboH1DDiEdUg.png](https://cdn-images-1.medium.com/max/1600/1*q7nHV9seYErboH1DDiEdUg.png)

VueμμλΒ `total`Β λλΒ `quantity`κ° μλ°μ΄νΈ λ  λλ§λ€Β `total`μ΄ μλ°μ΄νΈ λκΈ°λ₯Ό λ°λλλ€.

![https://cdn-images-1.medium.com/max/1600/1*aFGF-Go7ONnOtWjfyzytig.png](https://cdn-images-1.medium.com/max/1600/1*aFGF-Go7ONnOtWjfyzytig.png)

μνκΉκ²λ JavaScriptλ μ μ°¨νμ΄μ§, λ°μνμ΄ μλλ―λ‘ μ€μ λ‘λ λμνμ§ μμ΅λλ€.Β `total`μ λ°μνμΌλ‘ λ§λ€κΈ° μν΄μ JavaScriptλ₯Ό μ¬μ©νμ¬ λ€λ₯΄κ² μλνκ² ν©λλ€.

#### β οΈ λ¬Έμ 

`total`μ κ³μ°ν΄μΌνκΈ° λλ¬ΈμΒ `price`Β λλΒ `quantity`κ° λ³κ²½ λ  λλ§λ€ μ¬μ€νν΄μΌ νλ€.

#### β μλ£¨μ

μ°μ μ μΌλ‘λ μ±μ μλ¦΄ μ μλ λ°©λ²μ΄ νμν©λλ€. "λ΄κ° μ€ννλ €κ³  νλ μ½λλ₯ΌΒ **μ μ₯ν΄ λμλ€κ°**Β λ€λ₯Έ λ μ€νν  μλ μμ΅λλ€." κ·Έλ¬λ©΄ μν  λ μ½λλ₯Ό μ€ν ν  μ μκ² μ£ .Β `price`Β λλΒ `quantity`Β λ³μκ° μλ°μ΄νΈ λλ©΄, μ μ₯λ μ½λλ₯Ό λ€μ μ€ννκ² ν©λλ€.

![https://cdn-images-1.medium.com/max/1600/0*Nh-FQoHiDHncmQSi.png](https://cdn-images-1.medium.com/max/1600/0*Nh-FQoHiDHncmQSi.png)

ν¨μλ₯Ό λ€μ μ€ννκΈ° μν΄μ μ΄ ν¨μλ₯Ό κΈ°λ‘ν΄ λ‘λλ€.

![https://cdn-images-1.medium.com/max/1600/1*vD19ImKAK2WYySJGIvrKtQ.png](https://cdn-images-1.medium.com/max/1600/1*vD19ImKAK2WYySJGIvrKtQ.png)

μ΅λͺμ ν¨μλ₯ΌΒ `target`Β λ³μ μμ μ μ₯νκ³ ,`record`Β ν¨μλ₯Ό νΈμΆν©λλ€. ES6 νμ΄ν κ΅¬λ¬Έμ μ¬μ©νμ¬ λ€μκ³Ό κ°μ΄ μμ±ν  μλ μμ΅λλ€.

![https://cdn-images-1.medium.com/max/1600/1*z0E_bw1_XBjGdM0ab_pyDg.png](https://cdn-images-1.medium.com/max/1600/1*z0E_bw1_XBjGdM0ab_pyDg.png)

`record`μ μ μλ κ°λ¨ν©λλ€.

![https://cdn-images-1.medium.com/max/1600/1*6tRbHmwr7mzy5CNemhkTcg.png](https://cdn-images-1.medium.com/max/1600/1*6tRbHmwr7mzy5CNemhkTcg.png)

μ°λ¦¬λΒ `target`μ μ μ₯νκ³  μμ΅λλ€. (ν΄λΉ μ½λμ κ²½μ°Β `{ total = price * quantity }`). κΈ°λ‘ν λͺ¨λ  κ²μ μ€ννλΒ `replay`Β ν¨μλ₯Ό λμ€μ μ€νν  μλ μμ΅λλ€. .

![https://cdn-images-1.medium.com/max/1600/1*dyxkUSFl1S3m4dFCgc2jZw.png](https://cdn-images-1.medium.com/max/1600/1*dyxkUSFl1S3m4dFCgc2jZw.png)

μ΄κ²μ μ€ν λ¦¬μ§ λ°°μ΄ λ΄λΆμ μ μ₯λ λͺ¨λ  μ΅λͺ ν¨μμ κ±°μ³ κ°κ°μ μ€νν©λλ€.

κ·Έλ¬λ©΄ μ½λμμ λ€μκ³Ό κ°μ΄ ν  μ μμ΅λλ€.

![https://cdn-images-1.medium.com/max/1600/1*Fr8Oif-PkvmyFDKDt5Xm6w.png](https://cdn-images-1.medium.com/max/1600/1*Fr8Oif-PkvmyFDKDt5Xm6w.png)

κ°λ¨νμ£ ? μλλ μ μ²΄ μ½λμλλ€. μ²μλΆν° λκΉμ§ μ­ μ½κ³  μ΄ν΄νκ³ μ νλ κ²½μ° μ°Έκ³ νμΈμ.

![https://cdn-images-1.medium.com/max/1600/1*TpEBEstjfM4FNMYuh37BLA.png](https://cdn-images-1.medium.com/max/1600/1*TpEBEstjfM4FNMYuh37BLA.png)

![https://cdn-images-1.medium.com/max/1600/0*0a_165xKF15xL889.png](https://cdn-images-1.medium.com/max/1600/0*0a_165xKF15xL889.png)

#### β οΈ λ¬Έμ 

νμμ λ°λΌμ κΈ°λ‘ν  targetμ μ€νν  μλ μμ§λ§, μ±μΌλ‘ νμ₯ν  μ μλ λ κ°λ ₯ν μλ£¨μμ κ°λκ² μ’μ κ²μλλ€. μλ§λ μ¬μ€νμ μν  λ, μλ¦Όμ λ°λ νκ² λͺ©λ‘μ μ μ§ κ΄λ¦¬νλ ν΄λμ€μΌ κ²μλλ€.

#### β μλ£¨μ : μ’μ ν΄λμ€

μ΄ λ¬Έμ λ₯Ό ν΄κ²°νκΈ° μν΄ μμν  μ μλ ν κ°μ§ λ°©λ²μ μμ²΄ ν΄λμ€μ μ΄ λμμ μΊ‘μν ν¨μΌλ‘μ¨, κ΄μ°°μ ν¨ν΄(observer pattern)μΒ **μ’μ ν΄λμ€**λ‘ κ΅¬ννλ κ²μλλ€.

λ°λΌμ μ’μμ± (Vueκ° μΌμ μ²λ¦¬νλ λ°©λ²μ λ κ°κΉμ΅λλ€.)μ κ΄λ¦¬νκΈ° μν JavaScript ν΄λμ€λ₯Ό λ§λ λ€λ©΄ λ€μκ³Ό κ°μ κ²μλλ€.

![https://cdn-images-1.medium.com/max/1600/1*9NnQmGxZfmxhRJBUEs4Z7g.png](https://cdn-images-1.medium.com/max/1600/1*9NnQmGxZfmxhRJBUEs4Z7g.png)

`storage`Β λμ μ μ΅λͺ ν¨μλ₯ΌΒ `subscribers`μ μ μ₯νκ³  μμ΅λλ€.Β `record`Β ν¨μ λμ μΒ `depend`μ νΈμΆνκ³ Β `replay`Β λμ Β `notify`λ₯Ό μ¬μ©ν©λλ€. μ΄λ₯Ό μ€ννλ €λ©΄ λ€μ μ½λλ₯Ό μμ±νμΈμ.

![https://cdn-images-1.medium.com/max/1600/1*Y5XJpipq7-Po1mP_eJoCGw.png](https://cdn-images-1.medium.com/max/1600/1*Y5XJpipq7-Po1mP_eJoCGw.png)

μ¬μ ν μλνλ©° μ½λκ° λ μ¬μ¬μ© κ°λ₯ν΄ μ‘μ΅λλ€. μ‘°κΈ μ΄μν κ±΄Β `target`Β μ€μ κ³Ό μ€νλΏμλλ€.

#### β οΈ λ¬Έμ 

μμΌλ‘λ κ° λ³μμ λν΄ Dep ν΄λμ€λ₯Ό κ°κ² λ  κ²μ΄λ©°, μλ°μ΄νΈκ° νμν μ΅λͺ ν¨μλ₯Ό λ§λλ λμμ μΊ‘μννλ κ²μ΄ μ’μ΅λλ€. μλ§λΒ `κ°μμ (watcher)`Β κΈ°λ₯μ΄ μ΄λ¬ν νλμ μ²λ¦¬ν  κ²λλ€.

![https://cdn-images-1.medium.com/max/1600/1*mo9tPOcAy-qC1VZ6Bnz76A.png](https://cdn-images-1.medium.com/max/1600/1*mo9tPOcAy-qC1VZ6Bnz76A.png)

(μμμ μμ±ν μ½λμ κ°μ΅λλ€.)

μ μ½λλ₯Ό νΈμΆνλ λμ μ, λ€μμ νΈμΆνλλ‘ ν©μλ€.

![https://cdn-images-1.medium.com/max/1600/1*2TPYfKaV4UBEReN8PWwzbQ.png](https://cdn-images-1.medium.com/max/1600/1*2TPYfKaV4UBEReN8PWwzbQ.png)

#### β μλ£¨μ : κ°μμ (Watcher) ν¨μ

Watcher ν¨μμμ μ°λ¦¬λ λͺ κ°μ§ κ°λ¨ν μΌμ ν  μ μμ΅λλ€ :

![https://cdn-images-1.medium.com/max/1600/1*U7bJcE5Ad7lxbQUP-U68uw.png](https://cdn-images-1.medium.com/max/1600/1*U7bJcE5Ad7lxbQUP-U68uw.png)

λ³΄μλ€μνΌ,Β `watcher`Β ν¨μλΒ `myFunc`Β μΈμλ‘ μ·¨ν΄μ μ μ­Β `target`Β νλ‘νΌν°λ‘ μ€μ νκ³ Β `dep.depend()`λ₯Ό νΈμΆνμ¬ νκ²μ κ΅¬λμ(subscriber)λ‘ μΆκ°νκ³ `target`Β ν¨μλ₯Ό νΈμΆνκ³ ,Β `target`μ λ¦¬μν©λλ€.

μλλ μ€ν κ²°κ³Όμλλ€.

![https://cdn-images-1.medium.com/max/1600/1*vefCUnWyacq0GxC3TRI0Cw.png](https://cdn-images-1.medium.com/max/1600/1*vefCUnWyacq0GxC3TRI0Cw.png)

![https://cdn-images-1.medium.com/max/1600/0*D05AHN0_GUXoMVM8.png](https://cdn-images-1.medium.com/max/1600/0*D05AHN0_GUXoMVM8.png)

You might be wondering why we implementedΒ `target`Β as a global variable, rather than passing it into our functions where needed. There is a good reason for this, which will become obvious by the end of our article.

`target`μ μ μ­ λ³μλ‘ κ΅¬ν ν μ΄μ κ° κΆκΈνμ€νλ°μ, μ΄λ μ°λ¦¬ μν°ν΄μ λ§μ§λ§ λΆλΆ κ·Έ μ΄μ κ° λͺνν΄μ§ κ²λλ€.

#### β οΈ λ¬Έμ 

μ°λ¦¬λ νλμΒ `Dep class`λ₯Ό κ°μ§κ³  μμ§λ§, μ°λ¦¬κ° μ λ§λ‘ μνλ κ²μ κ°κ°μ λ³μκ° μμ μ Depλ₯Ό κ°λλ‘ νλ κ²μλλ€. μ§λλ₯Ό λ λκ°κΈ° μ μ νλ‘νΌν°λ₯Ό μ΄ν΄λ΄μλ€.

![https://cdn-images-1.medium.com/max/1600/1*YBknbJTkI-za0L9eMAFayQ.png](https://cdn-images-1.medium.com/max/1600/1*YBknbJTkI-za0L9eMAFayQ.png)

μ°λ¦¬μ κ° νλ‘νΌν° (`price`Β μΒ `quantity`)κ° κ·Έλ€ μμ μ λ΄λΆ Dep ν΄λμ€λ₯Ό κ°μ§κ³  μλ€κ³  κ°μ ν΄ λ΄μλ€.

![https://cdn-images-1.medium.com/max/1600/0*kV4iCRoguwO5C_JQ.png](https://cdn-images-1.medium.com/max/1600/0*kV4iCRoguwO5C_JQ.png)

μλ μ½λλ₯Ό μ€νμν΅μλ€.

![https://cdn-images-1.medium.com/max/1600/1*-rznzvwxr5clvYdPVq2MfA.png](https://cdn-images-1.medium.com/max/1600/1*-rznzvwxr5clvYdPVq2MfA.png)

`data.price`Β κ°μ μ κ·ΌνμΌλ―λ‘Β `price`Β νλ‘νΌν°μ Dep ν΄λμ€κ°Β `target`μ μ μ₯λμ΄ μλ μ΅λͺ ν¨μλ₯Ό subscriber λ°°μ΄μ pushνκ³ μ ν©λλ€(`dep.depend()`Β λ₯Ό νΈμΆν¨μΌλ‘μ).Β `data.quantity`μ μ κ·ΌνμΌλ―λ‘Β `amount`Β νλ‘νΌν°μ Dep ν΄λμ€κ° μ΄Β `target`μ μ μ₯λμ΄ μλ μ΅λͺ ν¨μλ₯Ό subscriber λ°°μ΄μ push νκ³ μ ν©λλ€.

![https://cdn-images-1.medium.com/max/1600/0*E-_YXfn3vJe7S_Ry.png](https://cdn-images-1.medium.com/max/1600/0*E-_YXfn3vJe7S_Ry.png)

`data.price`Β λ§ μ‘μΈμ€νλ λ λ€λ₯Έ μ΅λͺμ ν¨μκ° μμΌλ©΄Β `price`Β μμ± Dep ν΄λμ€μ κ·Έλ₯ pushνκ³ μ ν©λλ€.

![https://cdn-images-1.medium.com/max/1600/0*wefv6my2WWLW2385.png](https://cdn-images-1.medium.com/max/1600/0*wefv6my2WWLW2385.png)

μΈμ Β `dep.notify()`κ°Β `price`μ κ΅¬λμ(subscribers)μκ² νΈμΆλκ² ν κΉμ?Β `price`κ° μ ν΄μ§λ©΄ ν¨μκ° νΈμΆλκ² νκ³ μ ν©λλ€. μ΄ μν°ν΄μ λ λΆλΆμμ μ λ μ½μμ λ€μ΄κ°μ λ€μκ³Ό κ°μ΄ ν  μ μκ² νκ³ μ ν©λλ€.

![https://cdn-images-1.medium.com/max/1600/1*1XiVHkIOvqzIVOxNxYlsDA.png](https://cdn-images-1.medium.com/max/1600/1*1XiVHkIOvqzIVOxNxYlsDA.png)

μ°λ¦¬λ λ°μ΄ν° νλ‘νΌν° (`price`Β λΒ `quantity`μ κ°μ)μ μ κ·Όν  λ°©λ²μ΄ νμν©λλ€. κ·Έλμ μ κ·Ό ν  λΒ `target`μ κ΅¬λμ(subscriber) λ°°μ΄μ μ μ₯ν  μ μμ΅λλ€. κ·Έλ¦¬κ³  λ³κ²½λλ©΄ subscriber λ°°μ΄μ μ μ₯ν ν¨μλ₯Ό μ€νν©λλ€.

#### β μλ£¨μ : Object.defineProperty()

νμ€ ES5 JavaScript μΈΒ [Object.defineProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)Β ν¨μμ λν΄ μμμΌν©λλ€. μ΄λ νλ‘νΌν°μ λν getterμ setter ν¨μλ₯Ό μ μ ν  μ μκ² ν΄μ€λλ€. Dep ν΄λμ€μμ μ¬μ©νλ λ°©λ²μ λ³΄μ¬λλ¦¬κΈ° μ μ λ¨Όμ  μμ£Ό κΈ°λ³Έμ μΈ μ¬μ©λ²μ λ³΄μ¬ λλ¦¬κ² μ΅λλ€.

![https://cdn-images-1.medium.com/max/1600/1*KLPITQjsRSoGjOBRc6Y8zA.png](https://cdn-images-1.medium.com/max/1600/1*KLPITQjsRSoGjOBRc6Y8zA.png)

![https://cdn-images-1.medium.com/max/1600/0*i1g7DtASO4z1rOvk.png](https://cdn-images-1.medium.com/max/1600/0*i1g7DtASO4z1rOvk.png)

λ³΄μλ€μνΌ λ μ€μ λ‘κ·Έκ° μ°νλλ€. κ·Έλ¬λ μ°λ¦¬κ° μ€λ²λ‘λνκΈ° λλ¬Έμ μ€μ λ‘λ κ°μΒ `get`Β νκ±°λΒ `set`Β νμ§ μμ΅λλ€. λ€μ μ½λλ₯Ό μΆκ°ν©μλ€.Β `get()`μ κ°μ λ°ν ν  κ²μΌλ‘ κΈ°λνκ³ ,Β `set()`μ μ¬μ ν κ°μ κ°±μ  ν  νμκ° μμΌλ―λ‘, νμ¬μ`price`Β κ°μ μ μ₯νκΈ° μν΄Β `internalValue`Β λ³μλ₯Ό μΆκ°ν©μλ€.

![https://cdn-images-1.medium.com/max/1600/1*ek8RxCQ6pkLgbs-DJWteOg.png](https://cdn-images-1.medium.com/max/1600/1*ek8RxCQ6pkLgbs-DJWteOg.png)

μ΄μ  getκ³Ό setμ΄ μ λλ‘ μλνλ―λ‘ μ½μμ μ΄λ€ λ΄μ©μ΄ μΆλ ₯ λ κΉμ?

![https://cdn-images-1.medium.com/max/1600/0*lwD5BfrrNiiZjhyw.png](https://cdn-images-1.medium.com/max/1600/0*lwD5BfrrNiiZjhyw.png)

λ°λΌμ μ°λ¦¬λ κ°μ μ»κ³  μ€μ ν  λ ν΅λ³΄ λ°μ μ μλ λ°©λ²μ κ°μ§κ³  μμ΅λλ€. κ·Έλ¦¬κ³  μ¬κ·λ₯Ό ν΅ν΄ λ°μ΄ν° λ°°μ΄μ λͺ¨λ  ν­λͺ©μ λν΄ μ΄ μμμ μνν  μ μμ΅λλ€.

μ°Έκ³ λ‘,Β `Object.keys(data)`λ κ°μ²΄μ ν€ λ°°μ΄μ λ°νν©λλ€.

![https://cdn-images-1.medium.com/max/1600/1*56SYVD46rppSBl6mDzzsMg.png](https://cdn-images-1.medium.com/max/1600/1*56SYVD46rppSBl6mDzzsMg.png)

μ΄μ λ λͺ¨λ  getterμ setterκ° μμΌλ©° μ½μμμ λ³Ό μ μμ΅λλ€.

![https://cdn-images-1.medium.com/max/1600/0*VquzAf2KmijoTfbD.png](https://cdn-images-1.medium.com/max/1600/0*VquzAf2KmijoTfbD.png)

#### π  κ°λ(idea) λͺ¨μΌκΈ°

![https://cdn-images-1.medium.com/max/1600/1*2Nvu9DfFpp__k-HTMLSdYg.png](https://cdn-images-1.medium.com/max/1600/1*2Nvu9DfFpp__k-HTMLSdYg.png)

μμ κ°μ μ½λκ° μ€νλλ©΄Β `price`μ κ°μΒ **μ»μ΅λλ€.**Β `price`κ° μ΄ μ΅λͺμ ν¨μ (`target`)λ₯Ό κΈ°μ΅νκ³ μ ν©λλ€. μ΄λ°μμΌλ‘Β `price`κ° λ³κ²½λκ±°λΒ **set**μ΄ μλ‘μ΄ κ°μΌλ‘ μ€μ λλ©΄ μ΄ ν¨μλ μ΄ ν¨μκ° μ’μλμ΄ μλ€λ κ²μ μκ³  μκΈ° λλ¬Έμ μ΄ ν¨μκ° λ€μ μ€νλλλ‘ νΈλ¦¬κ±°ν©λλ€. κ·Έλμ μ΄λ κ² μκ°ν  μ μμ΅λλ€.

**Get**Β => μ΅λͺ ν¨μλ₯Ό κΈ°μ΅νλ€. κ°μ΄ λ³κ²½λλ©΄ λ€μ μ€ννλ€.

**Set**Β => μ μ₯λ μ΅λͺ ν¨μλ₯Ό μ€ννλ©΄ κ°μ΄ λ³κ²½λλ€.

Dep ν΄λμ€μ κ²½μ°

**Priceμ μ κ·Όμ (get)**Β =>Β `dep.depend()`λ₯Ό νΈμΆνμ¬ νμ¬Β `target`μ μ μ₯νλ€.

**Price μ€μ **Β =>Β `dep.notify()`λ₯Ό priceμ νΈμΆνκ³  λͺ¨λ  targetμ λ€μ μ€ννλ€.

μ΄ λ κ°μ§ κ°λ(idea)λ₯Ό κ²°ν©νμ¬ μ΅μ’ μ½λλ₯Ό μ΄ν΄ λ³΄κ² μ΅λλ€.

![https://cdn-images-1.medium.com/max/1600/1*bM-LGqWYYU3lCaazJ7cAew.png](https://cdn-images-1.medium.com/max/1600/1*bM-LGqWYYU3lCaazJ7cAew.png)

μ±μ κ°μ§κ³  λ λ μ½μμμ μ΄λ€ μΌμ΄ μΌμ΄λλμ§ λ³΄μΈμ.

![https://cdn-images-1.medium.com/max/1600/0*mgmRTNK_n0i2AFK2.png](https://cdn-images-1.medium.com/max/1600/0*mgmRTNK_n0i2AFK2.png)

μ°λ¦¬κ° μνλ λ°κ° νμ€ν μ΄λ€μ§λ€μ!Β `price`Β μΒ `quantity`λ λͺ¨λ λ°μνμλλ€! λͺ¨λ  μ½λλΒ `price`Β λλΒ `quantity`Β κ°μ΄ μλ°μ΄νΈ λ  λλ§λ€ μ¬μ€νλ©λλ€.

Vue λ¬Έμμ κ·Έλ¦Όμ΄ μ΄μ  μ΄ν΄κ° λμ€κ²λλ€.

![https://cdn-images-1.medium.com/max/1600/0*tB3MJCzh_cB6i3mS.png](https://cdn-images-1.medium.com/max/1600/0*tB3MJCzh_cB6i3mS.png)

getterμ setterκ° λ€μ΄μλ μμ λ³΄λΌμ λ°μ΄ν° λκ·ΈλΌλ―Έκ° λ³΄μ΄μλμ? μΉμν΄ λ³΄μ΄μμΌ ν©λλ€! λͺ¨λ  μ»΄ν¬λνΈ μΈμ€ν΄μ€μλ getter (λΉ¨κ°μ μ )μ μ’μμ±μ μμ§νλΒ `watcher`Β μΈμ€ν΄μ€(νλμ)κ° μμ΅λλ€. λμ€μ setterκ° νΈμΆλλ©΄ μ»΄ν¬λνΈκ° λ€μ λ λλ§ λλλ‘ νλ κ°μμμκ²Β **μλ¦Ό**μ λ³΄λλλ€. μλλ μ  μ€λͺμ΄ λ€μ΄κ° μ΄λ―Έμ§μλλ€.

![https://cdn-images-1.medium.com/max/1600/0*P268NBNs64Z-CERj.png](https://cdn-images-1.medium.com/max/1600/0*P268NBNs64Z-CERj.png)

μΌνΈ, μ΄μ  μ’ λ λͺνν΄μ‘μ£ ?

Vueκ° μ»€λ² μλμμ μ΄ μμμ νλ λ°©λ²μ λΆλͺ λ λ³΅μ‘νμ§λ§, μ΄μ λ μ¬λ¬λΆμ κΈ°λ³Έμ μΈ κ²μ μκ³  μμ΅λλ€.

#### βͺ μ°λ¦¬λ λ¬΄μμ λ°°μ λκ°?

- μ’μμ±(dependencies)μ μμ§νκ³  (depend) λͺ¨λ  μ’μμ±μ λ€μ μ€ννλ (notify)Β **Dep ν΄λμ€**λ₯Ό μμ±νλ λ°©λ².
- μ°λ¦¬κ° μ€νμ€μΈ μ½λλ₯Ό κ΄λ¦¬νκΈ°μνΒ **κ°μμ(watcher)**λ₯Ό λ§λλ λ°©λ². μ’μμ±μΌλ‘ μΆκ° (target) ν΄μΌ ν  μλ μμ΅λλ€.
- getter λ° setterλ₯Ό λ§λ€κΈ° μν΄Β **Object.defineProperty()**λ₯Ό μ¬μ©νλ λ°©λ².

#### λ€μμ?

μ΄ μν°ν΄μ΄ μ μ΅νμ¨λ€λ©΄, νμ΅ κ²½λ‘μ λ€μ λ¨κ³λΒ [νλ‘μμ λ°μν](https://www.vuemastery.com/courses/advanced-components/evan-you-on-proxies)μ λν΄ λ°°μ°λ κ²μλλ€. VueMastery.comμμ μ΄ μ£Όμ μ λνΒ [λ΄ λ¬΄λ£ λΉλμ€](https://www.vuemastery.com/courses/advanced-components/evan-you-on-proxies/)λ₯Ό κΌ­ νμΈνμ­μμ€. μ¬κΈ°μ λλ Vue.jsμ μ°½μμ Evan Youμ ν΄λΉ μ£Όμ μ λν΄ μ΄μΌκΈ°ν©λλ€.

---

*Originally published at*Β *[www.vuemastery.com](https://devtimothy.tistory.com/manage/newpost/www.vuemastery.com)*
