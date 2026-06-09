# [thunk]:com::application_reputation_static::GetIids`adjustor{40}' (ulong *,_GUID * *)

- ea: `0x18000b380`
- end: `0x18000b389`
- name: `?GetIids@application_reputation_static@com@@WCI@EAAJPEAKPEAPEAU_GUID@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b310`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::GetIids(__int64 a1, unsigned int *a2, struct _GUID **a3)
{
  return com::application_reputation_static::GetIids((com::application_reputation_static *)(a1 - 40), a2, a3);
}

```

## disassembly

```asm
0x18000b380  sub     rcx, 28h ; '('; this
0x18000b384  jmp     ?GetIids@application_reputation_static@com@@UEAAJPEAKPEAPEAU_GUID@@@Z; com::application_reputation_static::GetIids(ulong *,_GUID * *)
```
