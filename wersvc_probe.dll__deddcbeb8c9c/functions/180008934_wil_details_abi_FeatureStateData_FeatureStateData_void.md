# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180008934`
- end: `0x180008a04`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800085a8`

## callees

- `0x180008414`
- `0x180008934`
- `0x180008cfc`
- `0x18000b3d4`
- `0x18000d25c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800089e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800089e1`

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
0x180008934  mov     [rsp+arg_0], rbx
0x180008939  mov     [rsp+arg_8], rsi
0x18000893e  push    rdi
0x18000893f  sub     rsp, 0E0h
0x180008946  mov     rbx, rcx
0x180008949  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000894e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008953  cmp     byte ptr [rbx+40h], 0
0x180008957  jz      short loc_180008967
0x180008959  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000895d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008962  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008967  cmp     byte ptr [rbx+80h], 0
0x18000896e  jz      short loc_18000897E
0x180008970  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008974  lea     rcx, [rsp+0E8h+var_88]; this
0x180008979  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000897e  cmp     byte ptr [rbx+0C0h], 0
0x180008985  jz      short loc_18000899B
0x180008987  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000898e  lea     rcx, [rsp+0E8h+var_48]; this
0x180008996  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000899b  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800089a0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800089a5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800089aa  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800089af  mov     rsi, [rbx+108h]
0x1800089b6  mov     qword ptr [rbx+108h], 0
0x1800089c1  test    rsi, rsi
0x1800089c4  jz      short loc_1800089DA
0x1800089c6  call    cs:__imp_GetProcessHeap
0x1800089cc  mov     rcx, rax; hHeap
0x1800089cf  mov     r8, rsi; lpMem
0x1800089d2  xor     edx, edx; dwFlags
0x1800089d4  call    cs:__imp_HeapFree
0x1800089da  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800089e1  call    cs:__imp_DeleteCriticalSection
0x1800089e7  lea     rcx, [rbx+8]; this
0x1800089eb  lea     r11, [rsp+0E8h+var_8]
0x1800089f3  mov     rbx, [r11+10h]
0x1800089f7  mov     rsi, [r11+18h]
0x1800089fb  mov     rsp, r11
0x1800089fe  pop     rdi
0x1800089ff  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
