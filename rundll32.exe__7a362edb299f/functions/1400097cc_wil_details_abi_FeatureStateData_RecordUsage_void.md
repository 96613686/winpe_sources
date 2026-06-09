# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x1400097cc`
- end: `0x140009859`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140008330`
- `0x14000964c`
- `0x14000a710`

## callees

- `0x1400083b8`
- `0x140008840`
- `0x140009540`
- `0x1400097cc`
- `0x14000a5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009836`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009836`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400097e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400097e5`

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
0x1400097cc  push    rbx
0x1400097ce  sub     rsp, 0E0h
0x1400097d5  mov     rbx, rcx
0x1400097d8  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400097dd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400097e2  mov     rcx, rbx; SRWLock
0x1400097e5  call    cs:__imp_AcquireSRWLockExclusive
0x1400097eb  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400097ef  cmp     byte ptr [rdx+38h], 0
0x1400097f3  jz      short loc_1400097FF
0x1400097f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400097fa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400097ff  cmp     byte ptr [rbx+80h], 0
0x140009806  jz      short loc_140009816
0x140009808  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14000980c  lea     rcx, [rsp+0E8h+var_88]; this
0x140009811  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140009816  cmp     byte ptr [rbx+0C0h], 0
0x14000981d  jz      short loc_140009833
0x14000981f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140009826  lea     rcx, [rsp+0E8h+var_48]; this
0x14000982e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140009833  mov     rcx, rbx; SRWLock
0x140009836  call    cs:__imp_ReleaseSRWLockExclusive
0x14000983c  lea     rcx, [rsp+0E8h+var_C8]; this
0x140009841  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140009846  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000984b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140009850  add     rsp, 0E0h
0x140009857  pop     rbx
0x140009858  retn
```
