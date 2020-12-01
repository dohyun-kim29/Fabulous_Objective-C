## Hello, Objective-C

이제부터 SwiftUI를 공부해야하는 마당에 Objective-C를 공부하는 트렌드를 역행하는 사람의 발로 쓴 글이 시작된다.

처음 Xcode에서 Objective-C Commend Line Tool을 생성하면

이러한 코드를 볼 수 있다.

```objective-c
#import <Foundation/Foundation.h>

int main(int argc, const char * argv[]) {
    @autoreleasepool {
        // insert code here...
        NSLog(@"Hello, World!");
    }
    return 0;
}
```

물론 그동안 여러 언어를 배워왔던 짬이 있으므로 NSLog가 출력을 해주는 함수라는것은 바로 알아챌 수 있다.

 그리고 출력을 할때 @를 넣어줘야하는것 같다..

**기존에 쓰던 Swift와는 달리 Objective-C는 세미콜론을 꼭 붙여주어야 한다**

```objective-c
//주석이당
        
/*
이거도 주석이당
*/
        
```

주석은 Swift와 별 다를 것 없다.



## 자료형

Objective-C의 자료형은 C언어와 유사하다. (그냥 C언어다)

```objective-c
#import <Foundation/Foundation.h>

int main(int argc, const char * argv[]) {
    @autoreleasepool {
        int val_integer = 0;
        float val_float = 0.0f;
        double val_double = 0.0;
        char val_char = 'C';

        
        NSLog(@"int %d", val_integer);
        NSLog(@"float %f", val_float);
        NSLog(@"double %lf", val_double);
        NSLog(@"char %c", val_char);
        
        NSLog(@"int -> char %c", val_integer);
        NSLog(@"char -> int %d", val_char);
        
    }
    
    return 0;
}

```

C언어와 같다 그냥.

**정수형과 문자를 서로 바꿔도 아스키 코드 형태로 출력이 된다.**

**unsigned라는놈을 앞에 붙여주면 양의 정수만 두배의 길이로 사용이 가능하다 ( Swift의 UInt가 여기서 온것 같다 )**

Swift는 카멜 표기법을 쓰지만, Objective-C는 스네이크 방식을 선호하는 것 같다.

소수점 출력할때 %.nlf 이런식으로 출력 형식 지정자를 입력해주면 n자리까지 찍히는 편리한 기능이 있다.

**\0** 은 NULL, 즉 nill이다.



## 클래스

Objective-C가 기존 C언어와 다른 점이 바로 여기서 나온다. 

기존 C언어는 절차지향 언어이지만, Objective-C는 객체지향언어이다.

따라서 객체의 개념과, 클래스가 있다. 



```objective-c
@interface myClass : NSObject

{
    int num;
    NSString *name;
    NSString *secret;
}

@property (nonatomic, assign)   int num;
@property (nonatomic, retain)   NSString *name;

- (void) myMethod;
- (void) setSecret:(NSString *)secret;
- (NSString *) getmySecert;

+ (void) myClassMethod;

@end
```

기본적인 헤더파일에서의 **클래스** 선언이다.

중괄호 안에 들어가있는 부분은 **인스턴스 변수** 이고

```objective-c
{
    int num;
    NSString *name;
    NSString *secret;
} 
//인스턴스 변수
```

중괄호 밑에는 **프로퍼티** 들이 있다.

```objective-c
@property (nonatomic, assign)   int num;
@property (nonatomic, retain)   NSString *name;
//프로퍼티
```

이 프로퍼티들은 나중에 나올 **@synthesize** 라는 친구와 짝을 이루어서 자동으로 접근자 메소드를 생성해주는 역할을 한다고 한다.

프로퍼티 선언부 옆에 있는 **nonatomic, assign, retain** 등의 친구들은 이 프로퍼티들을 어떻게 관리할지 알려주는 아이들인데, 나중에 다시 알아보겠다.



-로 시작하는 메소드들은 **인스턴스 메소드** 라고 한다.

```objective-c
- (void) myMethod;
- (void) setSecret:(NSString *)secret;
- (NSString *) getmySecert;
//인스턴스 메소드
```

얘네들은 **인스턴스 상태에서만 동작**한다.



+로 시작하는 메소드들은 **클래스 메소드** 라는 친구들이다.

```objective-c
+ (void) myClassMethod;
//클래스 메소드
```

이친구들은 좀 특이한데, **인스턴스를 찍어내기도 전에 뭔가를 할 수 있는** 친구다.



일단 클래스에 대한 헤더에서의 선언은 이정도 해주고 자세한건 구현파일에서 해주도록 하자.



