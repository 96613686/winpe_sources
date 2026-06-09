# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800035b4`
- end: `0x180003684`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003374`

## callees

- `0x1800031e0`
- `0x1800035b4`
- `0x180003904`
- `0x1800060a8`
- `0x180007a6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003661`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003661`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003646`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003646`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003654`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003654`

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
0x1800035b4  mov     [rsp+arg_0], rbx
0x1800035b9  mov     [rsp+arg_8], rsi
0x1800035be  push    rdi
0x1800035bf  sub     rsp, 0E0h
0x1800035c6  mov     rbx, rcx
0x1800035c9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800035ce  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800035d3  cmp     byte ptr [rbx+40h], 0
0x1800035d7  jz      short loc_1800035E7
0x1800035d9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800035dd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800035e2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035e7  cmp     byte ptr [rbx+80h], 0
0x1800035ee  jz      short loc_1800035FE
0x1800035f0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800035f4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800035f9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035fe  cmp     byte ptr [rbx+0C0h], 0
0x180003605  jz      short loc_18000361B
0x180003607  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000360e  lea     rcx, [rsp+0E8h+var_48]; this
0x180003616  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000361b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003620  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003625  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000362a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000362f  mov     rsi, [rbx+108h]
0x180003636  mov     qword ptr [rbx+108h], 0
0x180003641  test    rsi, rsi
0x180003644  jz      short loc_18000365A
0x180003646  call    cs:__imp_GetProcessHeap
0x18000364c  mov     r8, rsi; lpMem
0x18000364f  xor     edx, edx; dwFlags
0x180003651  mov     rcx, rax; hHeap
0x180003654  call    cs:__imp_HeapFree
0x18000365a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003661  call    cs:__imp_DeleteCriticalSection
0x180003667  lea     rcx, [rbx+8]; this
0x18000366b  lea     r11, [rsp+0E8h+var_8]
0x180003673  mov     rbx, [r11+10h]
0x180003677  mov     rsi, [r11+18h]
0x18000367b  mov     rsp, r11
0x18000367e  pop     rdi
0x18000367f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
