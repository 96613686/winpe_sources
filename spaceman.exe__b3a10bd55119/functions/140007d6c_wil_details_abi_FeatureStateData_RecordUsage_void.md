# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x140007d6c`
- end: `0x140007df9`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400043b0`
- `0x140007bb4`
- `0x140009b30`

## callees

- `0x140004d60`
- `0x140005374`
- `0x140007a6c`
- `0x140007d6c`
- `0x140009770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007dd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007dd6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007d85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007d85`

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
0x140007d6c  push    rbx
0x140007d6e  sub     rsp, 0E0h
0x140007d75  mov     rbx, rcx
0x140007d78  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007d7d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140007d82  mov     rcx, rbx; SRWLock
0x140007d85  call    cs:__imp_AcquireSRWLockExclusive
0x140007d8b  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140007d8f  cmp     byte ptr [rdx+38h], 0
0x140007d93  jz      short loc_140007D9F
0x140007d95  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007d9a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007d9f  cmp     byte ptr [rbx+80h], 0
0x140007da6  jz      short loc_140007DB6
0x140007da8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140007dac  lea     rcx, [rsp+0E8h+var_88]; this
0x140007db1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007db6  cmp     byte ptr [rbx+0C0h], 0
0x140007dbd  jz      short loc_140007DD3
0x140007dbf  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140007dc6  lea     rcx, [rsp+0E8h+var_48]; this
0x140007dce  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007dd3  mov     rcx, rbx; SRWLock
0x140007dd6  call    cs:__imp_ReleaseSRWLockExclusive
0x140007ddc  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007de1  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140007de6  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007deb  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140007df0  add     rsp, 0E0h
0x140007df7  pop     rbx
0x140007df8  retn
```
