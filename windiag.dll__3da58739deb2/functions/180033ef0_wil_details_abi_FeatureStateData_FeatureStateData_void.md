# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180033ef0`
- end: `0x180033fc0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180037c90`

## callees

- `0x180033b68`
- `0x180033ef0`
- `0x1800343cc`
- `0x180036c6c`
- `0x180038d04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033f9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033f90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033f82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033f82`

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
0x180033ef0  mov     [rsp+arg_0], rbx
0x180033ef5  mov     [rsp+arg_8], rsi
0x180033efa  push    rdi
0x180033efb  sub     rsp, 0E0h
0x180033f02  mov     rbx, rcx
0x180033f05  lea     rcx, [rsp+0E8h+var_C8]; this
0x180033f0a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180033f0f  cmp     byte ptr [rbx+40h], 0
0x180033f13  jz      short loc_180033F23
0x180033f15  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180033f19  lea     rcx, [rsp+0E8h+var_C8]; this
0x180033f1e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180033f23  cmp     byte ptr [rbx+80h], 0
0x180033f2a  jz      short loc_180033F3A
0x180033f2c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180033f30  lea     rcx, [rsp+0E8h+var_88]; this
0x180033f35  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180033f3a  cmp     byte ptr [rbx+0C0h], 0
0x180033f41  jz      short loc_180033F57
0x180033f43  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180033f4a  lea     rcx, [rsp+0E8h+var_48]; this
0x180033f52  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180033f57  lea     rcx, [rsp+0E8h+var_C8]; this
0x180033f5c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180033f61  lea     rcx, [rsp+0E8h+var_C8]; this
0x180033f66  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180033f6b  mov     rsi, [rbx+108h]
0x180033f72  mov     qword ptr [rbx+108h], 0
0x180033f7d  test    rsi, rsi
0x180033f80  jz      short loc_180033F96
0x180033f82  call    cs:__imp_GetProcessHeap
0x180033f88  mov     rcx, rax; hHeap
0x180033f8b  mov     r8, rsi; lpMem
0x180033f8e  xor     edx, edx; dwFlags
0x180033f90  call    cs:__imp_HeapFree
0x180033f96  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180033f9d  call    cs:__imp_DeleteCriticalSection
0x180033fa3  lea     rcx, [rbx+8]; this
0x180033fa7  lea     r11, [rsp+0E8h+var_8]
0x180033faf  mov     rbx, [r11+10h]
0x180033fb3  mov     rsi, [r11+18h]
0x180033fb7  mov     rsp, r11
0x180033fba  pop     rdi
0x180033fbb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
