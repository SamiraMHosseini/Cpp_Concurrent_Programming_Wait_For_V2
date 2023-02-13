# C++ Concurrent Programming
In this example I'm not using lambda.

The wait_for method of the condition_variable class in C++ is a blocking function that waits for a specific condition to be met, 
or until the specified time duration has elapsed.

When a thread calls wait_for on a std::condition_variable, it releases the lock on the associated mutex and waits for a notification from another thread. 
The thread will be blocked until either the condition specified in the wait_for method is met, or the specified time duration has elapsed.

In the wait_for method, the first argument is a std::unique_lock on the mutex that protects the shared data. The second argument is the time duration for which the thread should wait, specified as a std::chrono::duration object. The third argument is a predicate function, which is used to specify the condition that the waiting thread is waiting for. The predicate function should return a bool value indicating whether the condition has been met or not.

When the condition specified by the predicate function is met, the waiting thread is awakened and the lock on the associated mutex is reacquired. The wait_for method then returns true to indicate that the condition was met. If the specified time duration has elapsed without the condition being met, the wait_for method returns false.

It is important to note that wait_for should always be used in conjunction with a std::unique_lock on a mutex, as this ensures that the lock is properly managed and released when the waiting thread is blocked.
