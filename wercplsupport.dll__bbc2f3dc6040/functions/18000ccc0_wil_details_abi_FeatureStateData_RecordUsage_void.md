# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18000ccc0`
- end: `0x18000cd4d`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008180`
- `0x18000cb08`
- `0x18000eb10`

## callees

- `0x180008fb0`
- `0x180009704`
- `0x18000c9e0`
- `0x18000ccc0`
- `0x18000dfd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ccd9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ccd9`

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
0x18000ccc0  push    rbx
0x18000ccc2  sub     rsp, 0E0h
0x18000ccc9  mov     rbx, rcx
0x18000cccc  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ccd1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000ccd6  mov     rcx, rbx; SRWLock
0x18000ccd9  call    cs:__imp_AcquireSRWLockExclusive
0x18000ccdf  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000cce3  cmp     byte ptr [rdx+38h], 0
0x18000cce7  jz      short loc_18000CCF3
0x18000cce9  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ccee  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ccf3  cmp     byte ptr [rbx+80h], 0
0x18000ccfa  jz      short loc_18000CD0A
0x18000ccfc  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000cd00  lea     rcx, [rsp+0E8h+var_88]; this
0x18000cd05  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000cd0a  cmp     byte ptr [rbx+0C0h], 0
0x18000cd11  jz      short loc_18000CD27
0x18000cd13  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000cd1a  lea     rcx, [rsp+0E8h+var_48]; this
0x18000cd22  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000cd27  mov     rcx, rbx; SRWLock
0x18000cd2a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cd30  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000cd35  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000cd3a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000cd3f  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000cd44  add     rsp, 0E0h
0x18000cd4b  pop     rbx
0x18000cd4c  retn
```
