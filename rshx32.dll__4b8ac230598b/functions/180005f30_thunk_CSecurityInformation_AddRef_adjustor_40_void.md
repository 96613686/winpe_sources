# [thunk]:CSecurityInformation::AddRef`adjustor{40}' (void)

- ea: `0x180005f30`
- end: `0x180005f39`
- name: `?AddRef@CSecurityInformation@@WCI@EAAKXZ`
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
  return CSecurityInformation::AddRef((CSecurityInformation *)(a1 - 40));
}

```

## disassembly

```asm
0x180005f30  sub     rcx, 28h ; '('; this
0x180005f34  jmp     ?AddRef@CSecurityInformation@@UEAAKXZ; CSecurityInformation::AddRef(void)
```
