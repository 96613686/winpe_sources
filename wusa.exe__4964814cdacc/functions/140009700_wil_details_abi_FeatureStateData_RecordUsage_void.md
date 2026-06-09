# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x140009700`
- end: `0x14000978d`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140004b00`
- `0x14000954c`
- `0x14000bce0`

## callees

- `0x140004c1c`
- `0x140005260`
- `0x140009284`
- `0x140009700`
- `0x14000aef0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140009719`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009719`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000976a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000976a`

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
0x140009700  push    rbx
0x140009702  sub     rsp, 0E0h
0x140009709  mov     rbx, rcx
0x14000970c  lea     rcx, [rsp+0E8h+var_C8]; this
0x140009711  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140009716  mov     rcx, rbx; SRWLock
0x140009719  call    cs:__imp_AcquireSRWLockExclusive
0x14000971f  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140009723  cmp     byte ptr [rdx+38h], 0
0x140009727  jz      short loc_140009733
0x140009729  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000972e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140009733  cmp     byte ptr [rbx+80h], 0
0x14000973a  jz      short loc_14000974A
0x14000973c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140009740  lea     rcx, [rsp+0E8h+var_88]; this
0x140009745  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000974a  cmp     byte ptr [rbx+0C0h], 0
0x140009751  jz      short loc_140009767
0x140009753  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000975a  lea     rcx, [rsp+0E8h+var_48]; this
0x140009762  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140009767  mov     rcx, rbx; SRWLock
0x14000976a  call    cs:__imp_ReleaseSRWLockExclusive
0x140009770  lea     rcx, [rsp+0E8h+var_C8]; this
0x140009775  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000977a  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000977f  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140009784  add     rsp, 0E0h
0x14000978b  pop     rbx
0x14000978c  retn
```
