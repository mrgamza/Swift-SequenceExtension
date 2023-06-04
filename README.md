# Swift-SequenceExtension
- support async map, async forEach
- support concurrent map, concurrent forEach

```
func asyncMapTest() {
  Task {
    let result = await [1, 2, 3, 4].asyncMap { value in
      return value + 1
    }
    
    print(result)
  }
}

asyncMapTest()

func concurrentMapTest() async {
  do {
    let result = try await [1, 2, 3, 4].concurrentMap { value in
      return value + 1
    }
    
    print(result)
  } catch {
    
  }
}

Task {
  await concurrentMapTest()
}
```
