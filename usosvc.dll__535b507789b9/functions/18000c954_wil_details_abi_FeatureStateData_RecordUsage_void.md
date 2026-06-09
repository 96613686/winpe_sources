# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18000c954`
- end: `0x18000c9e3`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ab10`
- `0x18000c7d0`
- `0x18000dc00`

## callees

- `0x18000ab98`
- `0x18000b158`
- `0x18000c6c4`
- `0x18000c954`
- `0x18000dab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c96e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c96e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c9bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c9bf`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  const struct wil::details_abi::RawUsageIndex *v4; // r9
  _BYTE v5[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v6[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v7[72]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v5);
  AcquireSRWLockExclusive(SRWLock);
  if ( LOBYTE(SRWLock[8].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[1]);
  if ( LOBYTE(SRWLock[16].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[9]);
  if ( LOBYTE(SRWLock[24].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v7,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[17]);
  ReleaseSRWLockExclusive(SRWLock);
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v5, v2, v3, v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v5);
}

```

## disassembly

```asm
0x18000c954  push    rbx
0x18000c956  sub     rsp, 0E0h
0x18000c95d  mov     rbx, rcx
0x18000c960  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000c965  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000c96a  nop
0x18000c96b  mov     rcx, rbx; SRWLock
0x18000c96e  call    cs:__imp_AcquireSRWLockExclusive
0x18000c974  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000c978  cmp     byte ptr [rdx+38h], 0
0x18000c97c  jz      short loc_18000C988
0x18000c97e  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000c983  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000c988  cmp     byte ptr [rbx+80h], 0
0x18000c98f  jz      short loc_18000C99F
0x18000c991  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000c995  lea     rcx, [rsp+0E8h+var_88]; this
0x18000c99a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000c99f  cmp     byte ptr [rbx+0C0h], 0
0x18000c9a6  jz      short loc_18000C9BC
0x18000c9a8  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000c9af  lea     rcx, [rsp+0E8h+var_48]; this
0x18000c9b7  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000c9bc  mov     rcx, rbx; SRWLock
0x18000c9bf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c9c5  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000c9ca  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000c9cf  nop
0x18000c9d0  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000c9d5  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000c9da  add     rsp, 0E0h
0x18000c9e1  pop     rbx
0x18000c9e2  retn
```
