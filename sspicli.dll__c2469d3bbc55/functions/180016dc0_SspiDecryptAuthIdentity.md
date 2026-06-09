# SspiDecryptAuthIdentity

- ea: `0x180016dc0`
- end: `0x180016dcd`
- name: `SspiDecryptAuthIdentity`
- size: `13`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE EncryptedAuthData)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800090e0`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiDecryptAuthIdentity(PSEC_WINNT_AUTH_IDENTITY_OPAQUE EncryptedAuthData)
{
  return SspiDecryptAuthIdentityEx(2u, EncryptedAuthData);
}

```

## disassembly

```asm
0x180016dc0  mov     rdx, rcx
0x180016dc3  mov     ecx, 2
0x180016dc8  jmp     SspiDecryptAuthIdentityEx
```
