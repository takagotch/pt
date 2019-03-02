### pt
---
https://github.com/fogleman/pt

```go
package main

import . "github.com/fogleman/pt/pt"

func main() {
  scene := Scene{}
  
  material := DiffuseMaterial(White)
  
  plane := NewPlane(V(0, 0, 0), V(0, 0, 1), material)
  scene.Add(plane)
  
  sphere := NewSphere(V(0, 0, 1), 1, material)
  scene.Add(sphere)
  
  light := NewSphere(V(0, 0, 5), 1, LightMaterial(White, 8))
  scene.Add(light)
  
  camera := LookAt(V(3, 3, 3), V(0, 0, 0.5), V(0, 0, 1), 50)
  
  sampler := NewSampler(4, 4)
  renderer := NewRenderer(&scene, &camera, sampler, 960, 540)
  renderer.AdaptiveSamples = 128
  renderer.IterativeRender("out%03d.png", 1000)
}

```

```
go get -u github.com/gogleman/pt/pt

cd go/src/github.com/fogleman/pt
go run examples/gopher.go

git checkout embree
go get -u github.com/fogleman/go-embree
```

```
```


