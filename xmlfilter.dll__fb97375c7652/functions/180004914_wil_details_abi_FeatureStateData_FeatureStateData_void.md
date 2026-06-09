# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180004914`
- end: `0x1800049e4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004474`

## callees

- `0x1800041f8`
- `0x180004914`
- `0x180004d88`
- `0x180009e5c`
- `0x18000c6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800049a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800049a6`

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
0x180004914  mov     [rsp+arg_0], rbx
0x180004919  mov     [rsp+arg_8], rsi
0x18000491e  push    rdi
0x18000491f  sub     rsp, 0E0h
0x180004926  mov     rbx, rcx
0x180004929  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000492e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004933  cmp     byte ptr [rbx+40h], 0
0x180004937  jz      short loc_180004947
0x180004939  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000493d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004942  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004947  cmp     byte ptr [rbx+80h], 0
0x18000494e  jz      short loc_18000495E
0x180004950  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180004954  lea     rcx, [rsp+0E8h+var_88]; this
0x180004959  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000495e  cmp     byte ptr [rbx+0C0h], 0
0x180004965  jz      short loc_18000497B
0x180004967  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000496e  lea     rcx, [rsp+0E8h+var_48]; this
0x180004976  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000497b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004980  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180004985  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000498a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000498f  mov     rsi, [rbx+108h]
0x180004996  mov     qword ptr [rbx+108h], 0
0x1800049a1  test    rsi, rsi
0x1800049a4  jz      short loc_1800049BA
0x1800049a6  call    cs:__imp_GetProcessHeap
0x1800049ac  mov     rcx, rax; hHeap
0x1800049af  mov     r8, rsi; lpMem
0x1800049b2  xor     edx, edx; dwFlags
0x1800049b4  call    cs:__imp_HeapFree
0x1800049ba  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800049c1  call    cs:__imp_DeleteCriticalSection
0x1800049c7  lea     rcx, [rbx+8]; this
0x1800049cb  lea     r11, [rsp+0E8h+var_8]
0x1800049d3  mov     rbx, [r11+10h]
0x1800049d7  mov     rsi, [r11+18h]
0x1800049db  mov     rsp, r11
0x1800049de  pop     rdi
0x1800049df  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
