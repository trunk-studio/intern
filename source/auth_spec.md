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
