# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18001b6f0`
- end: `0x18001b77d`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800199d0`
- `0x18001b53c`
- `0x18001c980`

## callees

- `0x180019a58`
- `0x180019fbc`
- `0x18001b430`
- `0x18001b6f0`
- `0x18001c7b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b75a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b75a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b709`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b709`

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
0x18001b6f0  push    rbx
0x18001b6f2  sub     rsp, 0E0h
0x18001b6f9  mov     rbx, rcx
0x18001b6fc  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001b701  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001b706  mov     rcx, rbx; SRWLock
0x18001b709  call    cs:__imp_AcquireSRWLockExclusive
0x18001b70f  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18001b713  cmp     byte ptr [rdx+38h], 0
0x18001b717  jz      short loc_18001B723
0x18001b719  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001b71e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001b723  cmp     byte ptr [rbx+80h], 0
0x18001b72a  jz      short loc_18001B73A
0x18001b72c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18001b730  lea     rcx, [rsp+0E8h+var_88]; this
0x18001b735  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001b73a  cmp     byte ptr [rbx+0C0h], 0
0x18001b741  jz      short loc_18001B757
0x18001b743  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18001b74a  lea     rcx, [rsp+0E8h+var_48]; this
0x18001b752  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001b757  mov     rcx, rbx; SRWLock
0x18001b75a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b760  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001b765  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18001b76a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001b76f  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001b774  add     rsp, 0E0h
0x18001b77b  pop     rbx
0x18001b77c  retn
```
