# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003914`
- end: `0x1800039e4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800036d4`

## callees

- `0x180003540`
- `0x180003914`
- `0x180003c64`
- `0x180006a34`
- `0x18000836c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800039c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800039c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039a6`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(wil::details_abi::FeatureStateData *this)
{
  void *v2; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE v4[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v5[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v6[64]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  if ( *((_BYTE *)this + 64) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (wil::details_abi::FeatureStateData *)((char *)this + 8));
  if ( *((_BYTE *)this + 128) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (wil::details_abi::FeatureStateData *)((char *)this + 72));
  if ( *((_BYTE *)this + 192) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (wil::details_abi::FeatureStateData *)((char *)this + 136));
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  v2 = (void *)*((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::FeatureStateData *)((char *)this + 8));
}

```

## disassembly

```asm
0x180003914  mov     [rsp+arg_0], rbx
0x180003919  mov     [rsp+arg_8], rsi
0x18000391e  push    rdi
0x18000391f  sub     rsp, 0E0h
0x180003926  mov     rbx, rcx
0x180003929  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000392e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003933  cmp     byte ptr [rbx+40h], 0
0x180003937  jz      short loc_180003947
0x180003939  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000393d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003942  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003947  cmp     byte ptr [rbx+80h], 0
0x18000394e  jz      short loc_18000395E
0x180003950  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003954  lea     rcx, [rsp+0E8h+var_88]; this
0x180003959  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000395e  cmp     byte ptr [rbx+0C0h], 0
0x180003965  jz      short loc_18000397B
0x180003967  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000396e  lea     rcx, [rsp+0E8h+var_48]; this
0x180003976  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000397b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003980  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003985  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000398a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000398f  mov     rsi, [rbx+108h]
0x180003996  mov     qword ptr [rbx+108h], 0
0x1800039a1  test    rsi, rsi
0x1800039a4  jz      short loc_1800039BA
0x1800039a6  call    cs:__imp_GetProcessHeap
0x1800039ac  mov     r8, rsi; lpMem
0x1800039af  xor     edx, edx; dwFlags
0x1800039b1  mov     rcx, rax; hHeap
0x1800039b4  call    cs:__imp_HeapFree
0x1800039ba  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800039c1  call    cs:__imp_DeleteCriticalSection
0x1800039c7  lea     rcx, [rbx+8]; this
0x1800039cb  lea     r11, [rsp+0E8h+var_8]
0x1800039d3  mov     rbx, [r11+10h]
0x1800039d7  mov     rsi, [r11+18h]
0x1800039db  mov     rsp, r11
0x1800039de  pop     rdi
0x1800039df  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
