# [thunk]:CSecurityInformation::AddRef`adjustor{16}' (void)

- ea: `0x180005f00`
- end: `0x180005f09`
- name: `?AddRef@CSecurityInformation@@WBA@EAAKXZ`
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
  return CSecurityInformation::AddRef((CSecurityInformation *)(a1 - 16));
}

```

## disassembly

```asm
0x180005f00  sub     rcx, 10h; this
0x180005f04  jmp     ?AddRef@CSecurityInformation@@UEAAKXZ; CSecurityInformation::AddRef(void)
```
