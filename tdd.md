# 第一個 spec：使用者登入程序

``` javascript
describe.only('auth', () => {

  describe('local login spec', () => {

    // 開始執行  spec 之前，先進行測試資料建立
    before(async (done) => {

      let testUser = {
        'username': 'test',
        'password': 'test',
        'gender': 'male',
        'email': 'test@test.com',
        'phone': '(951)-385-6121',
        'cell': '(657)-919-3511',
        'picture': ''
      }
      await models.User.create(testUser);
      done();

    });

    // 測試資料準備好之後，開始執行 spec
    it('do login should be success.', async (done) => {
      // 假設的 input params
      let loginUserFormData = {
        'username': 'test',
        'password': 'test'
      };

      // 透過 rest api 進行使用者登入
      let doLogin = await new Promise((resolve, reject) => {
        request.post('/auth/login')
        .send(loginUserFormData)
        .expect(302)
        .end((error, res) => {
          if (error) return reject(error);
          return resolve("OK");
        })
      });

      // 一旦登入完成，可以取得登入資訊，確認登入程序正確完成
      let authResult = await new Promise((resolve, reject) => {
        request.get('/auth/status')
        .expect(200)
        .end((error, res) => {
          if (error) return reject(error);
          return resolve(res.body);
        })
      });

      let sessionUser = authResult.sessionUser;
      let isAuthenticated = authResult.isAuthenticated;

      isAuthenticated.should.be.true;

      // 取得登入所回傳的結果後，確認 output 是否跟預期的相同
      try {
        sessionUser.should.be.Object;
        sessionUser.should.have.contain.keys('id', 'username', 'email');
        done();
      } catch (e) {
        done(e);
      }
    });
  });
});

```


## 運行失敗的情形

``` bash
1) auth local login spec do login should be success.:

    AssertionError: expected { id: 1, username: 'test' } to contain keys 'id', 'username', and 'email'
    + expected - actual

     [
    +  "email"
       "id"
       "username"
     ]

    at Object.callee$2$0$ (test/server/controllers/auth.spec.js:53:41)
```

## 運行成功的情形

``` bash

✓ do login should be success. (56ms)


1 passing (145ms)

```
˘
## 練習


* [使用者可以使用帳號密碼登入（後端 api 實作）](https://trello.com/c/Mu7z2kFo)

> 只有用環境好像有點不好玩，我有規劃好一個規格，相關說明可以看看 連結中 gitbook 最後的練習，我把相關說明都寫在 trello
> 大家可以 fork mobious 這個專案，試著運行以及完成我所要求的規格
> 一旦真的完成就可以發  pull request

> 可以初步熟悉一下 TDD 的開發方式，一開始不強求看得懂，有任何問題都可以提出

> 透過實作並且看到問題，學習才會快，已有把變數縮到一定範圍
> 一方面也是藉由這樣的練習，把 nodejs 的開發環境建置起來。
