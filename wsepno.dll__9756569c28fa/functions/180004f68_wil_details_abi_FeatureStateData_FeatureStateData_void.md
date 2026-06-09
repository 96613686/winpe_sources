# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180004f68`
- end: `0x180005038`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004bf4`

## callees

- `0x180004a0c`
- `0x180004f68`
- `0x1800052fc`
- `0x180008f0c`
- `0x18000aa60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005008`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ffa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ffa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005015`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005015`

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
0x180004f68  mov     [rsp+arg_0], rbx
0x180004f6d  mov     [rsp+arg_8], rsi
0x180004f72  push    rdi
0x180004f73  sub     rsp, 0E0h
0x180004f7a  mov     rbx, rcx
0x180004f7d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004f82  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004f87  cmp     byte ptr [rbx+40h], 0
0x180004f8b  jz      short loc_180004F9B
0x180004f8d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180004f91  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004f96  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004f9b  cmp     byte ptr [rbx+80h], 0
0x180004fa2  jz      short loc_180004FB2
0x180004fa4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180004fa8  lea     rcx, [rsp+0E8h+var_88]; this
0x180004fad  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004fb2  cmp     byte ptr [rbx+0C0h], 0
0x180004fb9  jz      short loc_180004FCF
0x180004fbb  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180004fc2  lea     rcx, [rsp+0E8h+var_48]; this
0x180004fca  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004fcf  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004fd4  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180004fd9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004fde  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180004fe3  mov     rsi, [rbx+108h]
0x180004fea  mov     qword ptr [rbx+108h], 0
0x180004ff5  test    rsi, rsi
0x180004ff8  jz      short loc_18000500E
0x180004ffa  call    cs:__imp_GetProcessHeap
0x180005000  mov     rcx, rax; hHeap
0x180005003  mov     r8, rsi; lpMem
0x180005006  xor     edx, edx; dwFlags
0x180005008  call    cs:__imp_HeapFree
0x18000500e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180005015  call    cs:__imp_DeleteCriticalSection
0x18000501b  lea     rcx, [rbx+8]; this
0x18000501f  lea     r11, [rsp+0E8h+var_8]
0x180005027  mov     rbx, [r11+10h]
0x18000502b  mov     rsi, [r11+18h]
0x18000502f  mov     rsp, r11
0x180005032  pop     rdi
0x180005033  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
