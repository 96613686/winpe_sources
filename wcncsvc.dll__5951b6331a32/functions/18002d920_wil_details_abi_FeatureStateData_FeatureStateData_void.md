# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18002d920`
- end: `0x18002d9f0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002d6a8`

## callees

- `0x18002d514`
- `0x18002d920`
- `0x18002dd88`
- `0x1800313e4`
- `0x180033518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d9cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d9cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d9b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d9b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d9c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d9c0`

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
0x18002d920  mov     [rsp+arg_0], rbx
0x18002d925  mov     [rsp+arg_8], rsi
0x18002d92a  push    rdi
0x18002d92b  sub     rsp, 0E0h
0x18002d932  mov     rbx, rcx
0x18002d935  lea     rcx, [rsp+0E8h+var_C8]; this
0x18002d93a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18002d93f  cmp     byte ptr [rbx+40h], 0
0x18002d943  jz      short loc_18002D953
0x18002d945  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18002d949  lea     rcx, [rsp+0E8h+var_C8]; this
0x18002d94e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18002d953  cmp     byte ptr [rbx+80h], 0
0x18002d95a  jz      short loc_18002D96A
0x18002d95c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18002d960  lea     rcx, [rsp+0E8h+var_88]; this
0x18002d965  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18002d96a  cmp     byte ptr [rbx+0C0h], 0
0x18002d971  jz      short loc_18002D987
0x18002d973  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18002d97a  lea     rcx, [rsp+0E8h+var_48]; this
0x18002d982  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18002d987  lea     rcx, [rsp+0E8h+var_C8]; this
0x18002d98c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18002d991  lea     rcx, [rsp+0E8h+var_C8]; this
0x18002d996  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18002d99b  mov     rsi, [rbx+108h]
0x18002d9a2  mov     qword ptr [rbx+108h], 0
0x18002d9ad  test    rsi, rsi
0x18002d9b0  jz      short loc_18002D9C6
0x18002d9b2  call    cs:__imp_GetProcessHeap
0x18002d9b8  mov     rcx, rax; hHeap
0x18002d9bb  mov     r8, rsi; lpMem
0x18002d9be  xor     edx, edx; dwFlags
0x18002d9c0  call    cs:__imp_HeapFree
0x18002d9c6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18002d9cd  call    cs:__imp_DeleteCriticalSection
0x18002d9d3  lea     rcx, [rbx+8]; this
0x18002d9d7  lea     r11, [rsp+0E8h+var_8]
0x18002d9df  mov     rbx, [r11+10h]
0x18002d9e3  mov     rsi, [r11+18h]
0x18002d9e7  mov     rsp, r11
0x18002d9ea  pop     rdi
0x18002d9eb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
