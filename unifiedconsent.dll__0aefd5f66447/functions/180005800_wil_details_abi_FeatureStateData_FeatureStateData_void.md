# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005800`
- end: `0x1800058d0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800054cc`

## callees

- `0x180005184`
- `0x180005800`
- `0x180005c74`
- `0x18000a9b8`
- `0x18000d720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800058ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800058ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005892`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005892`

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
0x180005800  mov     [rsp+arg_0], rbx
0x180005805  mov     [rsp+arg_8], rsi
0x18000580a  push    rdi
0x18000580b  sub     rsp, 0E0h
0x180005812  mov     rbx, rcx
0x180005815  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000581a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000581f  cmp     byte ptr [rbx+40h], 0
0x180005823  jz      short loc_180005833
0x180005825  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005829  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000582e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005833  cmp     byte ptr [rbx+80h], 0
0x18000583a  jz      short loc_18000584A
0x18000583c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005840  lea     rcx, [rsp+0E8h+var_88]; this
0x180005845  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000584a  cmp     byte ptr [rbx+0C0h], 0
0x180005851  jz      short loc_180005867
0x180005853  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000585a  lea     rcx, [rsp+0E8h+var_48]; this
0x180005862  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005867  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000586c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005871  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005876  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000587b  mov     rsi, [rbx+108h]
0x180005882  mov     qword ptr [rbx+108h], 0
0x18000588d  test    rsi, rsi
0x180005890  jz      short loc_1800058A6
0x180005892  call    cs:__imp_GetProcessHeap
0x180005898  mov     rcx, rax; hHeap
0x18000589b  mov     r8, rsi; lpMem
0x18000589e  xor     edx, edx; dwFlags
0x1800058a0  call    cs:__imp_HeapFree
0x1800058a6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800058ad  call    cs:__imp_DeleteCriticalSection
0x1800058b3  lea     rcx, [rbx+8]; this
0x1800058b7  lea     r11, [rsp+0E8h+var_8]
0x1800058bf  mov     rbx, [r11+10h]
0x1800058c3  mov     rsi, [r11+18h]
0x1800058c7  mov     rsp, r11
0x1800058ca  pop     rdi
0x1800058cb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
