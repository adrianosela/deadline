# deadline
Add deadlines to anything in Go.

[![Go Report Card](https://goreportcard.com/badge/github.com/adrianosela/deadline)](https://goreportcard.com/report/github.com/adrianosela/deadline)
[![Documentation](https://godoc.org/github.com/adrianosela/deadline?status.svg)](https://godoc.org/github.com/adrianosela/deadline)
[![GitHub issues](https://img.shields.io/github/issues/adrianosela/deadline.svg)](https://github.com/adrianosela/deadline/issues)
[![license](https://img.shields.io/github/license/adrianosela/deadline.svg)](https://github.com/adrianosela/deadline/blob/master/LICENSE)

## Usage

### Create a Deadline Object

```
dl := deadline.New()
```

### Set Fire-Time on a Deadline Object

```
dl.Set(time.Now().Add(10 * time.Second))
```

> Note: you can make a deadline object not fire by passing a zero-time to `Set()`:
>
> ```
> dl.Set(time.Time{})
> ```

### Use Deadline Object

```
select {
case <-dl.Done():
	// handle deadline exceeded
case x := <-otherChannel:
	// do thing with x
}
```
