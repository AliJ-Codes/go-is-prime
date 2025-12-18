# Concurrent Prime Number Checker in Go  
This project serves as a practical exercise to learn about concurrency in Go using the Producer-Consumer pattern.

## Project Purpose  
This project offers hands-on learning of concurrency concepts:  

- Goroutines and WaitGroups  
- Buffered Channels  
- Worker Pool Pattern  
- Producer-Consumer coordination  

## Features  
- Worker Pool: Creates multiple goroutines based on CPU cores  
- Buffered Channel: Efficiently distributes tasks between workers  
- Synchronous Execution: Uses sync.WaitGroup for proper synchronization  
- Performance Timing: Measures execution time for comparison  

# Project Structure  
text  
go-is-prime/  
├── main.go              # Main implementation  
├── README.md            # This file  
└── go.mod               # Go module file  

## How It Works  
### 1. Worker Pool Creation  
```go  
for i := 1; i <= runtime.NumCPU(); i++ {
    wg.Add(1)
    go is_prime(numChan, i, &wg)
}
```  
### 2. Task Distribution  
- Producer sends 200 large numbers to the buffered channel  
- Workers consume numbers concurrently  
- Each worker checks for primality using an intentionally slow algorithm  

#### 3. Synchronization  
- WaitGroup ensures all workers complete  
- Closing the channel signals the end of tasks  
- The main thread waits for all processing to finish  

## Learning Objectives  
- Understand the goroutine lifecycle  
- Master channel communication  
- Implement worker pools  
- Handle concurrent task processing  
- Use synchronization tools  
