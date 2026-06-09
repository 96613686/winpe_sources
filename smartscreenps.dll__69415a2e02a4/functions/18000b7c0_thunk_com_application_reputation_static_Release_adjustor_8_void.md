# [thunk]:com::application_reputation_static::Release`adjustor{8}' (void)

- ea: `0x18000b7c0`
- end: `0x18000b7c9`
- name: `?Release@application_reputation_static@com@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b7b0`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::Release(__int64 a1)
{
  return com::application_reputation_static::Release((com::application_reputation_static *)(a1 - 8));
}

```

## disassembly

```asm
0x18000b7c0  sub     rcx, 8; this
0x18000b7c4  jmp     ?Release@application_reputation_static@com@@UEAAKXZ; com::application_reputation_static::Release(void)
```
