# SspiEncryptAuthIdentity

- ea: `0x18001fc10`
- end: `0x18001fc1d`
- name: `SspiEncryptAuthIdentity`
- size: `13`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800137a0`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiEncryptAuthIdentity(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData)
{
  return SspiEncryptAuthIdentityEx(2u, AuthData);
}

```

## disassembly

```asm
0x18001fc10  mov     rdx, rcx
0x18001fc13  mov     ecx, 2
0x18001fc18  jmp     SspiEncryptAuthIdentityEx
```
