# Verify

## People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.

## The files are accessible via SSH here:
## ssh -p 59420 ctf-player@rhea.picoctf.net
## Using the password 1ad5be0d. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
## Checksum: 5848768e56185707f76c1d74f34f4e03fb0573ecc1ca7b11238007226654bcda
## To decrypt the file once you've verified the hash, run ./decrypt.sh files/<file>.

Through ssh access the files in the picoCTF webshell

Using the given password we can get connected

We have `checksum`, `decrypt.sh` and a lot of files, we need to find the correct one and decrypt it

The correct file will be the one, with which checksum matches and we also know that it has sha265 hash. So we can try `sha256sum files/* | grep "5848768e56185707f76c1d74f34f4e03fb0573ecc1ca7b11238007226654bcda"`

This gives us 1 file which is encrypted: `8eee7195`

to decrypt it we have `decrypt.sh`. So we can do `./decrypt.sh files/8eee7195`

And we have the flag: **picoCTF{trust_but_verify_8eee7195}**