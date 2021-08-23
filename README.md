# _ESSL_

_ESSL_, the _Extremely Simple Scripting Language_, is a dynamically typed scripting language designed for simplicity and consistency.

## Features:

* **Concise**. Use familiar UNIX commands directly. No need for a `subprocess` or `sub main`; just type `mkdir`, `cat` or `sleep` directly!
* **Familiar**. With a `C`-inspired syntax, you don't have to deal with Bash's idiosyncratic spaces and equality methods.
* **Portable**. Transcompile to `sh`, use it everywhere!

## Usage

Binaries are released for `Linux x86` systems, but also includes compiled `LLVM` source that you can assemble into your target architecture.

To use `essl`, simply run 

```
essl file.esl <args>
```

Putting the `essl` binary into `$PATH`, or in `/usr/bin` (or `/usr/local/bin`) is recommended.

## Example

```
#!/usr/bin/env essl
fun greet_user(name, hour) {
	if 0 <= hour < 6
		print("Late night, %s!" % name)
	else if 6 <= hour < 12
		print("Good morning, %s" % name)
	else if 12 <= hour < 18
		print("%s, how are you doing this afternoon?" %s name)
	else 
		print("Hello world!")
}
greet_user("Wonhyuk", date +"%H")
```



```
#!/usr/bin/env essl
git clone git@github.com:wonhyukchoi/essl.git
cd essl
errno = stack install
if errno
	print("Couldn't install, I received error %d" % errno)
else
	print("Great, you can use ESSL now!")
```



## Installation

Currently, the interpreter for ESSL is written in `Haskell`.

For a local build, you must first install the [Haskell Stack](https://docs.haskellstack.org/en/stable/README/), and run `stack install`.

For portability reasons, an implementation in `C` may also be planned in the future; for instance, the Haskell Stack does not support `FreeBSD`.



