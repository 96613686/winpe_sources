# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180007384`
- end: `0x180007463`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c620`

## callees

- `0x180006f88`
- `0x180007384`
- `0x180007770`
- `0x18000b4e4`
- `0x18000ddcc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000743a`
- `KERNEL32!DeleteCriticalSection` at `0x18000743a`
- `KERNEL32!GetProcessHeap` at `0x180007413`
- `KERNEL32!GetProcessHeap` at `0x180007413`
- `KERNEL32!HeapFree` at `0x180007427`
- `KERNEL32!HeapFree` at `0x180007427`

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
0x180007384  mov     [rsp+arg_0], rbx
0x180007389  mov     [rsp+arg_8], rsi
0x18000738e  push    rdi
0x18000738f  sub     rsp, 0E0h
0x180007396  mov     rbx, rcx
0x180007399  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000739e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800073a3  cmp     byte ptr [rbx+40h], 0
0x1800073a7  jz      short loc_1800073B7
0x1800073a9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800073ad  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800073b2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800073b7  cmp     byte ptr [rbx+80h], 0
0x1800073be  jz      short loc_1800073CE
0x1800073c0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800073c4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800073c9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800073ce  cmp     byte ptr [rbx+0C0h], 0
0x1800073d5  jz      short loc_1800073EB
0x1800073d7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800073de  lea     rcx, [rsp+0E8h+var_48]; this
0x1800073e6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800073eb  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800073f0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800073f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800073fa  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800073ff  mov     rsi, [rbx+108h]
0x180007406  and     qword ptr [rbx+108h], 0
0x18000740e  test    rsi, rsi
0x180007411  jz      short loc_180007433
0x180007413  call    cs:__imp_GetProcessHeap
0x18000741a  nop     dword ptr [rax+rax+00h]
0x18000741f  mov     r8, rsi; lpMem
0x180007422  xor     edx, edx; dwFlags
0x180007424  mov     rcx, rax; hHeap
0x180007427  call    cs:__imp_HeapFree
0x18000742e  nop     dword ptr [rax+rax+00h]
0x180007433  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000743a  call    cs:__imp_DeleteCriticalSection
0x180007441  nop     dword ptr [rax+rax+00h]
0x180007446  lea     rcx, [rbx+8]; this
0x18000744a  lea     r11, [rsp+0E8h+var_8]
0x180007452  mov     rbx, [r11+10h]
0x180007456  mov     rsi, [r11+18h]
0x18000745a  mov     rsp, r11
0x18000745d  pop     rdi
0x18000745e  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
