# gostruct
A Runtime Struct Builder for Go


## Example

```go
func Example() {
	b := gostruct.New()
	b.AddField("Name", reflect.TypeOf(""))
	b.AddField("Age", reflect.TypeOf(int64(0)))
	person := b.Build()

	i := person.New()
	i.SetString("Name", "gopher")
	i.SetInt64("Age", 11)

	fmt.Printf(" %T:  %+v\n", i.Interface(), i.Interface())
	fmt.Printf("%T: %+v\n", i.Addr(), i.Addr())

	// Output:
	//  struct { Name string; Age int64 }:  {Name:gopher Age:11}
	// *struct { Name string; Age int64 }: &{Name:gopher Age:11}
}
```