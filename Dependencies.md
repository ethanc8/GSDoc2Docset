# Dependencies

## Golang

```bash
sudo apt install golang
```

## Dashing

```bash
go get -u -v github.com/technosophos/dashing
```

```{note}
Although the author didn't say to use `-v`, `-v` gets you output, so it doesn't look like nothing's happening.
```

## Add Dashing to `$PATH`

```bash
export PATH=$GOPATH/bin:$HOME/go/bin:$PATH
```