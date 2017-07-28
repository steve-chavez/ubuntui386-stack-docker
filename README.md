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
# -v /source/.stack-work can be added to ignore the host .stack-work
# -v $HOME/.stack:/root/.stack can be added to cache dependencies on the host
# After this the binary will be in /tmp/bin
``` 
