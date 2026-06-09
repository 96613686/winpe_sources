# [thunk]:CSecurityInformation::Release`adjustor{16}' (void)

- ea: `0x180006170`
- end: `0x180006179`
- name: `?Release@CSecurityInformation@@WBA@EAAKXZ`
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
  return CSecurityInformation::Release((CSecurityInformation *)(a1 - 16));
}

```

## disassembly

```asm
0x180006170  sub     rcx, 10h; this
0x180006174  jmp     ?Release@CSecurityInformation@@UEAAKXZ; CSecurityInformation::Release(void)
```
