# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x14001008c`
- end: `0x14001015c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140013248`

## callees

- `0x14000fe64`
- `0x14001008c`
- `0x140010568`
- `0x140012434`
- `0x140014018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140010139`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140010139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001011e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001011e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001012c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001012c`

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
0x14001008c  mov     [rsp+arg_0], rbx
0x140010091  mov     [rsp+arg_8], rsi
0x140010096  push    rdi
0x140010097  sub     rsp, 0E0h
0x14001009e  mov     rbx, rcx
0x1400100a1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400100a6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400100ab  cmp     byte ptr [rbx+40h], 0
0x1400100af  jz      short loc_1400100BF
0x1400100b1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400100b5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400100ba  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400100bf  cmp     byte ptr [rbx+80h], 0
0x1400100c6  jz      short loc_1400100D6
0x1400100c8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1400100cc  lea     rcx, [rsp+0E8h+var_88]; this
0x1400100d1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400100d6  cmp     byte ptr [rbx+0C0h], 0
0x1400100dd  jz      short loc_1400100F3
0x1400100df  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1400100e6  lea     rcx, [rsp+0E8h+var_48]; this
0x1400100ee  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400100f3  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400100f8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1400100fd  lea     rcx, [rsp+0E8h+var_C8]; this
0x140010102  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140010107  mov     rsi, [rbx+108h]
0x14001010e  mov     qword ptr [rbx+108h], 0
0x140010119  test    rsi, rsi
0x14001011c  jz      short loc_140010132
0x14001011e  call    cs:__imp_GetProcessHeap
0x140010124  mov     rcx, rax; hHeap
0x140010127  mov     r8, rsi; lpMem
0x14001012a  xor     edx, edx; dwFlags
0x14001012c  call    cs:__imp_HeapFree
0x140010132  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140010139  call    cs:__imp_DeleteCriticalSection
0x14001013f  lea     rcx, [rbx+8]; this
0x140010143  lea     r11, [rsp+0E8h+var_8]
0x14001014b  mov     rbx, [r11+10h]
0x14001014f  mov     rsi, [r11+18h]
0x140010153  mov     rsp, r11
0x140010156  pop     rdi
0x140010157  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
