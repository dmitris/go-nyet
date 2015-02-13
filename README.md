# go-nyet
More aggressive `go vet`

## Why?

I've been bitten by too many bugs caused by the shadowing of Go variables within subblocks. The time has come to end them once and for all.

## What does it do?

It checks for shadowed variables anywhere they appear in the code. Helpfully, it also type checks these variables and ignores anything of type `error`. This is because it's very common practice to shadow `err` and, well, shadowing `error` typed things hasn't hurt me nearly as much in the past.

Other aggressive checks may come in the future.

## How do I get it?

```
go get github.com/barakmich/go-nyet
```

And run

```
go-nyet ./
go-nyet ./subpackage
```

In the root of your project. If it complains about packages, you may need to `go install` them first.

Still working out the kinks, and eventually fixing `./...` like most tools, but give it a shot.

## License

BSD
