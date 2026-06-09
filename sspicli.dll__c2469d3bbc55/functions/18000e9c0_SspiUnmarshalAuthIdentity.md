# SspiUnmarshalAuthIdentity

- ea: `0x18000e9c0`
- end: `0x18000e9c8`
- name: `SspiUnmarshalAuthIdentity`
- size: `8`
- prototype: `SECURITY_STATUS __stdcall(unsigned int AuthIdentityLength, char *AuthIdentityByteArray, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppAuthIdentity)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e9d0`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall SspiUnmarshalAuthIdentity(
        unsigned int AuthIdentityLength,
        char *AuthIdentityByteArray,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppAuthIdentity)
{
  return SspiUnmarshalAuthIdentityInternal(*(size_t *)&AuthIdentityLength, AuthIdentityByteArray, ppAuthIdentity, 0);
}

```

## disassembly

```asm
0x18000e9c0  xor     r9d, r9d; unsigned int *
0x18000e9c3  jmp     ?SspiUnmarshalAuthIdentityInternal@@YAJKPEADPEAPEAXPEAK@Z; SspiUnmarshalAuthIdentityInternal(ulong,char *,void * *,ulong *)
```
