# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000c13c`
- end: `0x18000c20c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bec4`

## callees

- `0x18000bdfc`
- `0x18000c13c`
- `0x18000c440`
- `0x18000d430`
- `0x18000e844`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c1e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c1e9`

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
0x18000c13c  mov     [rsp+arg_0], rbx
0x18000c141  mov     [rsp+arg_8], rsi
0x18000c146  push    rdi
0x18000c147  sub     rsp, 0E0h
0x18000c14e  mov     rbx, rcx
0x18000c151  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000c156  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000c15b  cmp     byte ptr [rbx+40h], 0
0x18000c15f  jz      short loc_18000C16F
0x18000c161  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000c165  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000c16a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000c16f  cmp     byte ptr [rbx+80h], 0
0x18000c176  jz      short loc_18000C186
0x18000c178  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000c17c  lea     rcx, [rsp+0E8h+var_88]; this
0x18000c181  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000c186  cmp     byte ptr [rbx+0C0h], 0
0x18000c18d  jz      short loc_18000C1A3
0x18000c18f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000c196  lea     rcx, [rsp+0E8h+var_48]; this
0x18000c19e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000c1a3  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000c1a8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000c1ad  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000c1b2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000c1b7  mov     rsi, [rbx+108h]
0x18000c1be  mov     qword ptr [rbx+108h], 0
0x18000c1c9  test    rsi, rsi
0x18000c1cc  jz      short loc_18000C1E2
0x18000c1ce  call    cs:__imp_GetProcessHeap
0x18000c1d4  mov     rcx, rax; hHeap
0x18000c1d7  mov     r8, rsi; lpMem
0x18000c1da  xor     edx, edx; dwFlags
0x18000c1dc  call    cs:__imp_HeapFree
0x18000c1e2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000c1e9  call    cs:__imp_DeleteCriticalSection
0x18000c1ef  lea     rcx, [rbx+8]; this
0x18000c1f3  lea     r11, [rsp+0E8h+var_8]
0x18000c1fb  mov     rbx, [r11+10h]
0x18000c1ff  mov     rsi, [r11+18h]
0x18000c203  mov     rsp, r11
0x18000c206  pop     rdi
0x18000c207  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
