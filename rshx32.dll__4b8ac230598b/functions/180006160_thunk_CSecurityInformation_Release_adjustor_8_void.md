# [thunk]:CSecurityInformation::Release`adjustor{8}' (void)

- ea: `0x180006160`
- end: `0x180006169`
- name: `?Release@CSecurityInformation@@W7EAAKXZ`
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
  return CSecurityInformation::Release((CSecurityInformation *)(a1 - 8));
}

```

## disassembly

```asm
0x180006160  sub     rcx, 8; this
0x180006164  jmp     ?Release@CSecurityInformation@@UEAAKXZ; CSecurityInformation::Release(void)
```
