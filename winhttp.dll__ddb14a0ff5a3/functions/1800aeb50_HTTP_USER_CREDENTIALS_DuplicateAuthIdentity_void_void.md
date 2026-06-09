# HTTP_USER_CREDENTIALS::_DuplicateAuthIdentity(void *,void * *)

- ea: `0x1800aeb50`
- end: `0x1800aebf8`
- name: `?_DuplicateAuthIdentity@HTTP_USER_CREDENTIALS@@AEAAKPEAXPEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(HTTP_USER_CREDENTIALS *this, void *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800305ec`
- `0x1800aea68`
- `0x1800b6c5c`

## callees

- `0x1800a1d10`
- `0x1800aeb50`

## import_xrefs

- `SspiCli!SspiCopyAuthIdentity` at `0x1800aeb84`
- `SspiCli!SspiCopyAuthIdentity` at `0x1800aeb84`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800aebd8`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800aebd8`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x1800aeb95`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x1800aeb95`
- `SspiCli!SspiEncryptAuthIdentity` at `0x1800aeba4`
- `SspiCli!SspiEncryptAuthIdentity` at `0x1800aeba4`
- `SspiCli!SspiZeroAuthIdentity` at `0x1800aebcd`
- `SspiCli!SspiZeroAuthIdentity` at `0x1800aebcd`

## pseudocode

```c

```
