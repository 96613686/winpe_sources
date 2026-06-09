# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18000d70c`
- end: `0x18000d7a6`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800090b0`
- `0x18000d514`
- `0x180010600`

## callees

- `0x180009a4c`
- `0x18000a0a4`
- `0x18000d3c4`
- `0x18000d70c`
- `0x18001002c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000d725`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000d725`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d77c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d77c`

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
0x18000d70c  push    rbx
0x18000d70e  sub     rsp, 0E0h
0x18000d715  mov     rbx, rcx
0x18000d718  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000d71d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000d722  mov     rcx, rbx; SRWLock
0x18000d725  call    cs:__imp_AcquireSRWLockExclusive
0x18000d72c  nop     dword ptr [rax+rax+00h]
0x18000d731  cmp     byte ptr [rbx+40h], 0
0x18000d735  jz      short loc_18000D745
0x18000d737  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000d73b  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000d740  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000d745  cmp     byte ptr [rbx+80h], 0
0x18000d74c  jz      short loc_18000D75C
0x18000d74e  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000d752  lea     rcx, [rsp+0E8h+var_88]; this
0x18000d757  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000d75c  cmp     byte ptr [rbx+0C0h], 0
0x18000d763  jz      short loc_18000D779
0x18000d765  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000d76c  lea     rcx, [rsp+0E8h+var_48]; this
0x18000d774  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000d779  mov     rcx, rbx; SRWLock
0x18000d77c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d783  nop     dword ptr [rax+rax+00h]
0x18000d788  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000d78d  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000d792  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000d797  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000d79c  add     rsp, 0E0h
0x18000d7a3  pop     rbx
0x18000d7a4  retn
```
