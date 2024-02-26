# Giraffe 🦒 

experimental graphing library in go

## Usage

> The public API doesn't really exist as of now as a lot of the base stuff is being re-built every
> commit, consider running the tests or [taking the look at the source](./giraffe/giraffe.go)

```shell
go test .\giraffe\
```

or run the example

```
go run .\example
```

## Example

> Taken from [./examples/main.go](./examples/main.go)

```go
func main() {
    var g giraffe.Graph

    v0 := &giraffe.Vertex{Index: 0}
    v1 := &giraffe.Vertex{Index: 1}

    g.AddVertex(v0)
    g.AddVertex(v1)

    g.AddEdge(&giraffe.Edge{Start: v0, End: v1})
    
		// Find the provided index using Breadth-First Search 
    found, visited := g.FindVertex(1)

    fmt.Printf("Found: %d\n", found.Index)

		// Returns an array of visited vertices
    fmt.Print("Visited: { ")
    for i, vtx := range visited {
			if i == len(visited) - 1 {
				fmt.Printf("%d }\n", vtx.Index)
				continue
			}
      fmt.Printf("%d, ", vtx.Index)
    }
}
```
