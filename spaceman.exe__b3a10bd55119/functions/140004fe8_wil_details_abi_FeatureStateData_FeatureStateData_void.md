# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140004fe8`
- end: `0x1400050b8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004ef4`

## callees

- `0x140004d60`
- `0x140004fe8`
- `0x140005374`
- `0x140007a6c`
- `0x140009770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005095`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005095`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005088`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005088`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000507a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000507a`

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
0x140004fe8  mov     [rsp+arg_0], rbx
0x140004fed  mov     [rsp+arg_8], rsi
0x140004ff2  push    rdi
0x140004ff3  sub     rsp, 0E0h
0x140004ffa  mov     rbx, rcx
0x140004ffd  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005002  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140005007  cmp     byte ptr [rbx+40h], 0
0x14000500b  jz      short loc_14000501B
0x14000500d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140005011  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005016  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000501b  cmp     byte ptr [rbx+80h], 0
0x140005022  jz      short loc_140005032
0x140005024  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140005028  lea     rcx, [rsp+0E8h+var_88]; this
0x14000502d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005032  cmp     byte ptr [rbx+0C0h], 0
0x140005039  jz      short loc_14000504F
0x14000503b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140005042  lea     rcx, [rsp+0E8h+var_48]; this
0x14000504a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000504f  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005054  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140005059  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000505e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140005063  mov     rsi, [rbx+108h]
0x14000506a  mov     qword ptr [rbx+108h], 0
0x140005075  test    rsi, rsi
0x140005078  jz      short loc_14000508E
0x14000507a  call    cs:__imp_GetProcessHeap
0x140005080  mov     r8, rsi; lpMem
0x140005083  xor     edx, edx; dwFlags
0x140005085  mov     rcx, rax; hHeap
0x140005088  call    cs:__imp_HeapFree
0x14000508e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140005095  call    cs:__imp_DeleteCriticalSection
0x14000509b  lea     rcx, [rbx+8]; this
0x14000509f  lea     r11, [rsp+0E8h+var_8]
0x1400050a7  mov     rbx, [r11+10h]
0x1400050ab  mov     rsi, [r11+18h]
0x1400050af  mov     rsp, r11
0x1400050b2  pop     rdi
0x1400050b3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
