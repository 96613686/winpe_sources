# [thunk]:com::application_reputation_static::AddRef`adjustor{8}' (void)

- ea: `0x18000b070`
- end: `0x18000b079`
- name: `?AddRef@application_reputation_static@com@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b060`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::AddRef(__int64 a1)
{
  return com::application_reputation_static::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000b070  sub     rcx, 8; this
0x18000b074  jmp     ?AddRef@application_reputation_static@com@@UEAAKXZ; com::application_reputation_static::AddRef(void)
```
