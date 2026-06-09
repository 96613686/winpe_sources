# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180004414`
- end: `0x1800044e4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000406c`

## callees

- `0x180003d24`
- `0x180004414`
- `0x180004888`
- `0x180008314`
- `0x18000b6b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800044c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800044c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044b4`

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
0x180004414  mov     [rsp+arg_0], rbx
0x180004419  mov     [rsp+arg_8], rsi
0x18000441e  push    rdi
0x18000441f  sub     rsp, 0E0h
0x180004426  mov     rbx, rcx
0x180004429  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000442e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004433  cmp     byte ptr [rbx+40h], 0
0x180004437  jz      short loc_180004447
0x180004439  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000443d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004442  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004447  cmp     byte ptr [rbx+80h], 0
0x18000444e  jz      short loc_18000445E
0x180004450  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180004454  lea     rcx, [rsp+0E8h+var_88]; this
0x180004459  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000445e  cmp     byte ptr [rbx+0C0h], 0
0x180004465  jz      short loc_18000447B
0x180004467  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000446e  lea     rcx, [rsp+0E8h+var_48]; this
0x180004476  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000447b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004480  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180004485  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000448a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000448f  mov     rsi, [rbx+108h]
0x180004496  mov     qword ptr [rbx+108h], 0
0x1800044a1  test    rsi, rsi
0x1800044a4  jz      short loc_1800044BA
0x1800044a6  call    cs:__imp_GetProcessHeap
0x1800044ac  mov     rcx, rax; hHeap
0x1800044af  mov     r8, rsi; lpMem
0x1800044b2  xor     edx, edx; dwFlags
0x1800044b4  call    cs:__imp_HeapFree
0x1800044ba  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800044c1  call    cs:__imp_DeleteCriticalSection
0x1800044c7  lea     rcx, [rbx+8]; this
0x1800044cb  lea     r11, [rsp+0E8h+var_8]
0x1800044d3  mov     rbx, [r11+10h]
0x1800044d7  mov     rsi, [r11+18h]
0x1800044db  mov     rsp, r11
0x1800044de  pop     rdi
0x1800044df  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
