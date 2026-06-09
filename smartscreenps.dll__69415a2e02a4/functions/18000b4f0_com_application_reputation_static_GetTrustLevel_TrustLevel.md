# com::application_reputation_static::GetTrustLevel(TrustLevel *)

- ea: `0x18000b4f0`
- end: `0x18000b4f9`
- name: `?GetTrustLevel@application_reputation_static@com@@UEAAJPEAW4TrustLevel@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(com::application_reputation_static *__hidden this, enum TrustLevel *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000b500`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::GetTrustLevel(
        com::application_reputation_static *this,
        enum TrustLevel *a2)
{
  *a2 = BaseTrust;
  return 0;
}

```

## disassembly

```asm
0x18000b4f0  mov     dword ptr [rdx], 0
0x18000b4f6  xor     eax, eax
0x18000b4f8  retn
```
