# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180010304`
- end: `0x1800103d4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010210`

## callees

- `0x18001007c`
- `0x180010304`
- `0x180010654`
- `0x180012b9c`
- `0x1800140e4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800103b1`
- `KERNEL32!DeleteCriticalSection` at `0x1800103b1`
- `KERNEL32!HeapFree` at `0x1800103a4`
- `KERNEL32!HeapFree` at `0x1800103a4`
- `KERNEL32!GetProcessHeap` at `0x180010396`
- `KERNEL32!GetProcessHeap` at `0x180010396`

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
0x180010304  mov     [rsp+arg_0], rbx
0x180010309  mov     [rsp+arg_8], rsi
0x18001030e  push    rdi
0x18001030f  sub     rsp, 0E0h
0x180010316  mov     rbx, rcx
0x180010319  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001031e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010323  cmp     byte ptr [rbx+40h], 0
0x180010327  jz      short loc_180010337
0x180010329  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18001032d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010332  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010337  cmp     byte ptr [rbx+80h], 0
0x18001033e  jz      short loc_18001034E
0x180010340  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180010344  lea     rcx, [rsp+0E8h+var_88]; this
0x180010349  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001034e  cmp     byte ptr [rbx+0C0h], 0
0x180010355  jz      short loc_18001036B
0x180010357  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18001035e  lea     rcx, [rsp+0E8h+var_48]; this
0x180010366  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001036b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010370  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180010375  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001037a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001037f  mov     rsi, [rbx+108h]
0x180010386  mov     qword ptr [rbx+108h], 0
0x180010391  test    rsi, rsi
0x180010394  jz      short loc_1800103AA
0x180010396  call    cs:__imp_GetProcessHeap
0x18001039c  mov     r8, rsi; lpMem
0x18001039f  xor     edx, edx; dwFlags
0x1800103a1  mov     rcx, rax; hHeap
0x1800103a4  call    cs:__imp_HeapFree
0x1800103aa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800103b1  call    cs:__imp_DeleteCriticalSection
0x1800103b7  lea     rcx, [rbx+8]; this
0x1800103bb  lea     r11, [rsp+0E8h+var_8]
0x1800103c3  mov     rbx, [r11+10h]
0x1800103c7  mov     rsi, [r11+18h]
0x1800103cb  mov     rsp, r11
0x1800103ce  pop     rdi
0x1800103cf  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
