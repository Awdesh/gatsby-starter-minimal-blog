---
date: "2018-07-01"
title: Try with resource.
category: Coding, Programming, Computer science, java
---
Java 7 provides the functionality of “try with resource” which essentially means resource will be closed as soon as try block finishes executing. 

```
    static String readFromFile(String path) throws IOException {
        try (BufferedReader br = new BufferedReader(new FileReader(path))) {
            return br.readLine();
        }
    }
```


Here BufferedReader is the resource and it gets closed as soon as try finishes. In old try-catch approach, resource still remain open even for catch block, which doesn’t seem safe. 

