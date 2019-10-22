### mathgl
---
https://github.com/go-gl/mathgl

```go
// mgl64/project_test.go

func TestProject(t *testing.T) {
  t.Parallel()
  
  obj := Vec3(1002, 960, 0)
  modelview := Mat4(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 203, 1, 0, 1)
  projection := Mat4(0.000, 0, 0, 0, ...)
  initialX, initialY, width, height := 0, 0, 1536, 960
  win := Project(obj, modelview, projection, initialX, initialY, widht, height)
  
  if !win.ApproxEqualThreshold(answer, 1e-4) {
    t.Errorf("Project does something weird, differs from expected by of %v", win.Sub(answer).Len())
  }
  
  objr, err := UnProject(win, modelview, projection, initialX, initialY, width, height)
  if err != nil {
    t.Errorf("UnProject returned error: %v", err)
  }
  if !objr.ApproxEqualThreashold(obj, 1d-4) {
    t.Errorf("UnProject(%v) != %v (got %v)", win, obj, objr)
  }
}





```

```
```

```
```


