# [thunk]:CSecurityInformation::Release`adjustor{32}' (void)

- ea: `0x180006190`
- end: `0x180006199`
- name: `?Release@CSecurityInformation@@WCA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c710`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::Release(__int64 a1)
{
  return CSecurityInformation::Release((CSecurityInformation *)(a1 - 32));
}

```

## disassembly

```asm
0x180006190  sub     rcx, 20h ; ' '; this
0x180006194  jmp     ?Release@CSecurityInformation@@UEAAKXZ; CSecurityInformation::Release(void)
```
