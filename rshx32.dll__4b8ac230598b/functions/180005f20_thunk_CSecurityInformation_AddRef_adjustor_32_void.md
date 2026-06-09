# [thunk]:CSecurityInformation::AddRef`adjustor{32}' (void)

- ea: `0x180005f20`
- end: `0x180005f29`
- name: `?AddRef@CSecurityInformation@@WCA@EAAKXZ`
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
  return CSecurityInformation::AddRef((CSecurityInformation *)(a1 - 32));
}

```

## disassembly

```asm
0x180005f20  sub     rcx, 20h ; ' '; this
0x180005f24  jmp     ?AddRef@CSecurityInformation@@UEAAKXZ; CSecurityInformation::AddRef(void)
```
