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





