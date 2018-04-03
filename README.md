# kotlin-tips

1. 仿C#中的`Action`和`Func`委托

   ```kotlin
   //Action
   typealias Action1<T1> = (t1: T1) -> Unit
   typealias Action2<T1, T2> = (t1: T1, t2: T2) -> Unit
   typealias Action3<T1, T2, T3> = (t1: T1, t2: T2, t3: T3) -> Unit
   typealias Action4<T1, T2, T3, T4> = (t1: T1, t2: T2, t3: T3, t4: T4) -> Unit
   typealias Action5<T1, T2, T3, T4, T5> = (t1: T1, t2: T2, t3: T3, t4: T4, t5: T5) -> Unit
   typealias Action6<T1, T2, T3, T4, T5, T6> = (t1: T1, t2: T2, t3: T3, t4: T4, t5: T5, t6: T6) -> Unit
   typealias Action7<T1, T2, T3, T4, T5, T6, T7> = (t1: T1, t2: T2, t3: T3, t4: T4, t5: T5, t6: T6, t7: T7) -> Unit
   ```

   ```kotlin
   //Func
   typealias Func1<T1, R> = (t1: T1) -> R
   typealias Func2<T1, T2, R> = (t1: T1, t2: T2) -> R
   typealias Func3<T1, T2, T3, R> = (t1: T1, t2: T2, t3: T3) -> R
   typealias Func4<T1, T2, T3, T4, R> = (t1: T1, t2: T2, t3: T3, t4: T4) -> R
   typealias Func5<T1, T2, T3, T4, T5, R> = (t1: T1, t2: T2, t3: T3, t4: T4, t5: T5) -> R
   typealias Func6<T1, T2, T3, T4, T5, T6, R> = (t1: T1, t2: T2, t3: T3, t4: T4, t5: T5, t6: T6) -> R
   typealias Func7<T1, T2, T3, T4, T5, T6, T7, R> = (t1: T1, t2: T2, t3: T3, t4: T4, t5: T5, t6: T6, t7: T7) -> R
   ```

   使用

   ```kotlin
   fun mian(args: Array<String>) {
       actionUsage { t1, t2 ->
           run {
               println(t1)
               println(t2)
           }
       }

       val printAction2: Action2<String, String> = { t1, t2 ->
           run {
               println(t1)
               println(t2)
           }
       }

       printAction2("hello", "world")

       val addFunc2: Func2<Int, Int, Int> = { t1, t2 ->
           run { t1 + t2 }
       }
       var t = addFunc2.invoke(1, 2)
   }

   fun actionUsage(action2: Action2<Int, String>) {
       action2.invoke(123, "hello world")
   }
   ```

   ​