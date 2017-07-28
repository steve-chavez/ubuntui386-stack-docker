# ubuntui386-stack

## Usage:

In your project directory: 

```bash 
docker run -it --rm -v $(pwd):/source stevechavez/ubuntui386-stack <stack_command>
``` 

## For building and obtaining a binary:

```bash 
docker run -it --rm -v $(pwd):/source -v /tmp/bin:/root/.local/bin/ \
           stevechavez/ubuntui386-stack build --copy-bins --install-ghc
# -v /source/.stack-work can be added to ignore a local .stack-work
# After this the binary will be in /tmp/bin
``` 

## For caching dependencies:

```bash
docker create -v /root --name stack_cache busybox
docker run -it --rm --volumes-from stack_cache -v $(pwd):/source -v /tmp/bin:/root/.local/bin/ \
           stevechavez/ubuntui386-stack build --copy-bins --install-ghc
```
