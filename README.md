# ts
typescript를 하면서 기억해놓으면 좋을 것들

## tool
- https://transform.tools/json-schema-to-typescript

## jest
- ts에서 jest를 사용하다 보면 import한 mocking된 의존성이 jest의 인터페이스를 알지 못하기 때문에 자동 완성이 되지 않는데 두 가지 방법이 있으나 최근 `ts-jest/utils`에 있는 `mocked`를 사용해서 형변환한 새로운 변수를 만드는 대신 편리하게 사용할 수 있다
  - ```ts
    import { mocked } from 'ts-jest/utils'
    
    test('test some', () => {
        mocked(useSelector).mockImplementationOnce((args) => {
          const f = args as Function
          return f({})
        })
    })
    ```
  - [mocking된 의존성 형변환 처리해서 사용하는 방법](https://stackoverflow.com/questions/48759035/mock-dependency-in-jest-with-typescript)

## [Nominal typing vs structural typing](https://lemoine-benoit.medium.com/why-does-typescript-sometimes-fails-to-type-check-extra-properties-fd230ebbc295)
