# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180006f20`
- end: `0x180006fad`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b40`
- `0x180006d34`
- `0x1800087d0`

## callees

- `0x180003540`
- `0x180003c64`
- `0x180006a34`
- `0x180006f20`
- `0x18000836c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006f8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006f8a`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  _BYTE v2[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v3[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v4[72]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v2);
  AcquireSRWLockExclusive(SRWLock);
  if ( LOBYTE(SRWLock[8].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v2,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[1]);
  if ( LOBYTE(SRWLock[16].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v3,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[9]);
  if ( LOBYTE(SRWLock[24].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[17]);
  ReleaseSRWLockExclusive(SRWLock);
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v2);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v2);
}

```

## disassembly

```asm
0x180006f20  push    rbx
0x180006f22  sub     rsp, 0E0h
0x180006f29  mov     rbx, rcx
0x180006f2c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006f31  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006f36  mov     rcx, rbx; SRWLock
0x180006f39  call    cs:__imp_AcquireSRWLockExclusive
0x180006f3f  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180006f43  cmp     byte ptr [rdx+38h], 0
0x180006f47  jz      short loc_180006F53
0x180006f49  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006f4e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006f53  cmp     byte ptr [rbx+80h], 0
0x180006f5a  jz      short loc_180006F6A
0x180006f5c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180006f60  lea     rcx, [rsp+0E8h+var_88]; this
0x180006f65  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006f6a  cmp     byte ptr [rbx+0C0h], 0
0x180006f71  jz      short loc_180006F87
0x180006f73  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180006f7a  lea     rcx, [rsp+0E8h+var_48]; this
0x180006f82  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006f87  mov     rcx, rbx; SRWLock
0x180006f8a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006f90  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006f95  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006f9a  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006f9f  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180006fa4  add     rsp, 0E0h
0x180006fab  pop     rbx
0x180006fac  retn
```
