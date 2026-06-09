# SamiValidateComputerAccountReuseAttempt

- ea: `0x180014440`
- end: `0x180014445`
- name: `SamiValidateComputerAccountReuseAttempt`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008f5c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall SamiValidateComputerAccountReuseAttempt(__int64 a1, __int64 a2, unsigned int a3, _BYTE *a4)
{
  return SamClientValidateComputerAccountReuseAttempt(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180014440  jmp     ?SamClientValidateComputerAccountReuseAttempt@@YAJPEAU_UNICODE_STRING@@PEAXW4SAM_DOMAIN_JOIN_POLICY_LEVEL@@PEAE@Z; SamClientValidateComputerAccountReuseAttempt(_UNICODE_STRING *,void *,SAM_DOMAIN_JOIN_POLICY_LEVEL,uchar *)
```
