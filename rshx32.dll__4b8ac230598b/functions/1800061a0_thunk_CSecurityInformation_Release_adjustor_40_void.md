# [thunk]:CSecurityInformation::Release`adjustor{40}' (void)

- ea: `0x1800061a0`
- end: `0x1800061a9`
- name: `?Release@CSecurityInformation@@WCI@EAAKXZ`
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
  return CSecurityInformation::Release((CSecurityInformation *)(a1 - 40));
}

```

## disassembly

```asm
0x1800061a0  sub     rcx, 28h ; '('; this
0x1800061a4  jmp     ?Release@CSecurityInformation@@UEAAKXZ; CSecurityInformation::Release(void)
```
