---
title: 몽고 db 스키마 정의
description: mongoDB, 몽고 DB, mongoose, node.js
tags: node.js, mongoDB, 데이터베이스, 백엔드, mongoose

categories: [Back-End, mongoDB]
---

## 몽고 db와 연동하면, db에 입력할 데이터의 스키마를 정의해야한다.

<br/>
스키마란, 일반적인 관계형 데이터베이스에서 정의하는 entity와 비슷한 개념이다. <br/>
가령, MySQL로 User entity를 정의할 때, User 데이터는 각각 id, password 등의 데이터를 포함하고 있을 것이다. <br/>
이와 비슷한 개념으로, mongoDB는 node.js와 mongoose를 사용하여 User 스키마를 id와 password 등의 데이터를 포함하도록 정의할 수 있다.

```javascript
function getCurrentDate() {
  var date = new Date();
  var year = date.getFullYear();
  var month = date.getMonth();
  var today = date.getDate();
  var hours = date.getHours();
  var minutes = date.getMinutes();
  var seconds = date.getSeconds();
  return new Date(Date.UTC(year, month, today, hours, minutes, seconds));
}

const userSchema = mongoose.Schema(
  {
    _id: { type: String, required: true },
    password: { type: String, required: true },
    nickName: { type: String, required: true },
    createdAt: {
      // 글을 생성한 날짜
      type: Date,
      default: getCurrentDate(),
    },
  },
  { timestamps: true }
);
```

이 코드를 보면, \_id는 문자열 형태로 입력이 꼭 필요하다는 것을 알 수 있다. 이렇게 각 key값과 value값을 정의할 수 있다.<br/>
createdAt을 보면, 데이터베이스에 기록을 남길 때, 기록하는 시간을 자동으로 기록하게 한 것이다. default에 getCurrentDate()함수를 값으로 지정해줘서 함수를 사용할 수 있도록 하였다.
<br/>
<br/>

**_여기서 주의할 점은, 이 코드의 경우, 몽고 db에서 자동으로 할당하는 \_id의 값을 지정해줬다는 것이다. 반대로 말하면, \_id를 직접 정의하지 않은 경우 몽고 db에서 자동으로 값을 할당하는데 이 값이 그 데이터 객체의 키 값이므로, 자동으로 할당된 값을 그 객체의 다른 값으로 찾아내야 한다는 번거로운 절차를 거치게 된다. 그러므로 schema를 정의할 때 키 값을 일반적인 다른 데이터베이스처럼 id로 정의하는 것이 아닌, 웬만하면 \_id로 정의하도록 하자._**

## 전체 코드

```javascript
const mongoose = require("mongoose");
const express = require("express");

function getCurrentDate() {
  var date = new Date();
  var year = date.getFullYear();
  var month = date.getMonth();
  var today = date.getDate();
  var hours = date.getHours();
  var minutes = date.getMinutes();
  var seconds = date.getSeconds();
  return new Date(Date.UTC(year, month, today, hours, minutes, seconds));
}

const userSchema = mongoose.Schema(
  {
    _id: { type: String, required: true },
    password: { type: String, required: true },
    nickName: { type: String, required: true },
    createdAt: {
      // 글을 생성한 날짜
      type: Date,
      default: getCurrentDate(),
    },
  },
  { timestamps: true }
);

const User = mongoose.model("userList", userSchema);
module.exports = { User };
```

마지막에 userSchema를 userList라는 몽고db의 데이터셋으로 모델링하고, 이를 User로 export한다.
<br/>
<br/>
스키마에서 정의한 \_id, password, nickName을 postman으로 전송했을 때, 몽고 db에 저장되는 모습이다.

![mongo](/assets/img/mongoDB_schema.png)

~~시간이 저렇게 찍히는 것은 수정이 필요하다~~
