# [thunk]:CSecurityInformation::Release`adjustor{24}' (void)

- ea: `0x180006180`
- end: `0x180006189`
- name: `?Release@CSecurityInformation@@WBI@EAAKXZ`
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
  return CSecurityInformation::Release((CSecurityInformation *)(a1 - 24));
}

```

## disassembly

```asm
0x180006180  sub     rcx, 18h; this
0x180006184  jmp     ?Release@CSecurityInformation@@UEAAKXZ; CSecurityInformation::Release(void)
```
