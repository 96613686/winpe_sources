# [thunk]:com::application_reputation_static::Release`adjustor{40}' (void)

- ea: `0x18000b520`
- end: `0x18000b529`
- name: `?Release@application_reputation_static@com@@WCI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b500`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::Release(__int64 a1)
{
  return com::application_reputation_static::Release((com::application_reputation_static *)(a1 - 40));
}

```

## disassembly

```asm
0x18000b520  sub     rcx, 28h ; '('; this
0x18000b524  jmp     ?Release@application_reputation_static@com@@UEAAKXZ; com::application_reputation_static::Release(void)
```
