# [thunk]:com::application_reputation_static::GetTrustLevel`adjustor{40}' (TrustLevel *)

- ea: `0x18000b500`
- end: `0x18000b509`
- name: `?GetTrustLevel@application_reputation_static@com@@WCI@EAAJPEAW4TrustLevel@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b4f0`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::GetTrustLevel(__int64 a1, enum TrustLevel *a2)
{
  return com::application_reputation_static::GetTrustLevel((com::application_reputation_static *)(a1 - 40), a2);
}

```

## disassembly

```asm
0x18000b500  sub     rcx, 28h ; '('; this
0x18000b504  jmp     ?GetTrustLevel@application_reputation_static@com@@UEAAJPEAW4TrustLevel@@@Z; com::application_reputation_static::GetTrustLevel(TrustLevel *)
```
