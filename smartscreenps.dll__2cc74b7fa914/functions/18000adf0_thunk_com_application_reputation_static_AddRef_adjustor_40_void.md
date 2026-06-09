# [thunk]:com::application_reputation_static::AddRef`adjustor{40}' (void)

- ea: `0x18000adf0`
- end: `0x18000adf9`
- name: `?AddRef@application_reputation_static@com@@WCI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000add0`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::AddRef(__int64 a1)
{
  return com::application_reputation_static::AddRef(a1 - 40);
}

```

## disassembly

```asm
0x18000adf0  sub     rcx, 28h ; '('; this
0x18000adf4  jmp     ?AddRef@application_reputation_static@com@@UEAAKXZ; com::application_reputation_static::AddRef(void)
```
