# [thunk]:CSecurityInformation::AddRef`adjustor{8}' (void)

- ea: `0x180005ef0`
- end: `0x180005ef9`
- name: `?AddRef@CSecurityInformation@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bf80`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::AddRef(__int64 a1)
{
  return CSecurityInformation::AddRef((CSecurityInformation *)(a1 - 8));
}

```

## disassembly

```asm
0x180005ef0  sub     rcx, 8; this
0x180005ef4  jmp     ?AddRef@CSecurityInformation@@UEAAKXZ; CSecurityInformation::AddRef(void)
```
