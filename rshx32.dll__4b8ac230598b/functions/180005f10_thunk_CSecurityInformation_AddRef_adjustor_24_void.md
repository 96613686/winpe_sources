# [thunk]:CSecurityInformation::AddRef`adjustor{24}' (void)

- ea: `0x180005f10`
- end: `0x180005f19`
- name: `?AddRef@CSecurityInformation@@WBI@EAAKXZ`
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
  return CSecurityInformation::AddRef((CSecurityInformation *)(a1 - 24));
}

```

## disassembly

```asm
0x180005f10  sub     rcx, 18h; this
0x180005f14  jmp     ?AddRef@CSecurityInformation@@UEAAKXZ; CSecurityInformation::AddRef(void)
```
