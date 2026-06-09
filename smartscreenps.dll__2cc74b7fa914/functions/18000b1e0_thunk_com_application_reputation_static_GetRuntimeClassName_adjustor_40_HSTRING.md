# [thunk]:com::application_reputation_static::GetRuntimeClassName`adjustor{40}' (HSTRING__ * *)

- ea: `0x18000b1e0`
- end: `0x18000b1e9`
- name: `?GetRuntimeClassName@application_reputation_static@com@@WCI@EAAJPEAPEAUHSTRING__@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b1c0`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  return com::application_reputation_static::GetRuntimeClassName((com::application_reputation_static *)(a1 - 40), a2);
}

```

## disassembly

```asm
0x18000b1e0  sub     rcx, 28h ; '('; this
0x18000b1e4  jmp     ?GetRuntimeClassName@application_reputation_static@com@@UEAAJPEAPEAUHSTRING__@@@Z; com::application_reputation_static::GetRuntimeClassName(HSTRING__ * *)
```
