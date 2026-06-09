# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000ae54`
- end: `0x18000af24`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ac60`

## callees

- `0x18000ab98`
- `0x18000ae54`
- `0x18000b158`
- `0x18000c6c4`
- `0x18000dab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aee6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aee6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aef4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aef4`

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
0x18000ae54  mov     [rsp+arg_0], rbx
0x18000ae59  mov     [rsp+arg_8], rsi
0x18000ae5e  push    rdi
0x18000ae5f  sub     rsp, 0E0h
0x18000ae66  mov     rbx, rcx
0x18000ae69  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ae6e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000ae73  cmp     byte ptr [rbx+40h], 0
0x18000ae77  jz      short loc_18000AE87
0x18000ae79  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000ae7d  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ae82  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ae87  cmp     byte ptr [rbx+80h], 0
0x18000ae8e  jz      short loc_18000AE9E
0x18000ae90  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000ae94  lea     rcx, [rsp+0E8h+var_88]; this
0x18000ae99  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ae9e  cmp     byte ptr [rbx+0C0h], 0
0x18000aea5  jz      short loc_18000AEBB
0x18000aea7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000aeae  lea     rcx, [rsp+0E8h+var_48]; this
0x18000aeb6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000aebb  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000aec0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000aec5  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000aeca  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000aecf  mov     rsi, [rbx+108h]
0x18000aed6  mov     qword ptr [rbx+108h], 0
0x18000aee1  test    rsi, rsi
0x18000aee4  jz      short loc_18000AEFA
0x18000aee6  call    cs:__imp_GetProcessHeap
0x18000aeec  mov     rcx, rax; hHeap
0x18000aeef  mov     r8, rsi; lpMem
0x18000aef2  xor     edx, edx; dwFlags
0x18000aef4  call    cs:__imp_HeapFree
0x18000aefa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000af01  call    cs:__imp_DeleteCriticalSection
0x18000af07  lea     rcx, [rbx+8]; this
0x18000af0b  lea     r11, [rsp+0E8h+var_8]
0x18000af13  mov     rbx, [r11+10h]
0x18000af17  mov     rsi, [r11+18h]
0x18000af1b  mov     rsp, r11
0x18000af1e  pop     rdi
0x18000af1f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
