# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180008c2c`
- end: `0x180008cc6`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800027f0`
- `0x180008a34`
- `0x18000b3e0`

## callees

- `0x1800032a0`
- `0x180003998`
- `0x1800088e4`
- `0x180008c2c`
- `0x18000af14`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008c9c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008c9c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008c45`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008c45`

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
0x180008c2c  push    rbx
0x180008c2e  sub     rsp, 0E0h
0x180008c35  mov     rbx, rcx
0x180008c38  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008c3d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008c42  mov     rcx, rbx; SRWLock
0x180008c45  call    cs:__imp_AcquireSRWLockExclusive
0x180008c4c  nop     dword ptr [rax+rax+00h]
0x180008c51  cmp     byte ptr [rbx+40h], 0
0x180008c55  jz      short loc_180008C65
0x180008c57  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008c5b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008c60  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c65  cmp     byte ptr [rbx+80h], 0
0x180008c6c  jz      short loc_180008C7C
0x180008c6e  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008c72  lea     rcx, [rsp+0E8h+var_88]; this
0x180008c77  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c7c  cmp     byte ptr [rbx+0C0h], 0
0x180008c83  jz      short loc_180008C99
0x180008c85  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180008c8c  lea     rcx, [rsp+0E8h+var_48]; this
0x180008c94  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c99  mov     rcx, rbx; SRWLock
0x180008c9c  call    cs:__imp_ReleaseSRWLockExclusive
0x180008ca3  nop     dword ptr [rax+rax+00h]
0x180008ca8  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008cad  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180008cb2  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008cb7  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008cbc  add     rsp, 0E0h
0x180008cc3  pop     rbx
0x180008cc4  retn
```
