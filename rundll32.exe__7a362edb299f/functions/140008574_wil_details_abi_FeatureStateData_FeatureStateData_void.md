# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140008574`
- end: `0x140008644`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140008480`

## callees

- `0x1400083b8`
- `0x140008574`
- `0x140008840`
- `0x140009540`
- `0x14000a5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008621`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008621`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008614`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008614`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008606`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008606`

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
0x140008574  mov     [rsp+arg_0], rbx
0x140008579  mov     [rsp+arg_8], rsi
0x14000857e  push    rdi
0x14000857f  sub     rsp, 0E0h
0x140008586  mov     rbx, rcx
0x140008589  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000858e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140008593  cmp     byte ptr [rbx+40h], 0
0x140008597  jz      short loc_1400085A7
0x140008599  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x14000859d  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400085a2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400085a7  cmp     byte ptr [rbx+80h], 0
0x1400085ae  jz      short loc_1400085BE
0x1400085b0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1400085b4  lea     rcx, [rsp+0E8h+var_88]; this
0x1400085b9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400085be  cmp     byte ptr [rbx+0C0h], 0
0x1400085c5  jz      short loc_1400085DB
0x1400085c7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1400085ce  lea     rcx, [rsp+0E8h+var_48]; this
0x1400085d6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400085db  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400085e0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1400085e5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400085ea  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1400085ef  mov     rsi, [rbx+108h]
0x1400085f6  mov     qword ptr [rbx+108h], 0
0x140008601  test    rsi, rsi
0x140008604  jz      short loc_14000861A
0x140008606  call    cs:__imp_GetProcessHeap
0x14000860c  mov     r8, rsi; lpMem
0x14000860f  xor     edx, edx; dwFlags
0x140008611  mov     rcx, rax; hHeap
0x140008614  call    cs:__imp_HeapFree
0x14000861a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140008621  call    cs:__imp_DeleteCriticalSection
0x140008627  lea     rcx, [rbx+8]; this
0x14000862b  lea     r11, [rsp+0E8h+var_8]
0x140008633  mov     rbx, [r11+10h]
0x140008637  mov     rsi, [r11+18h]
0x14000863b  mov     rsp, r11
0x14000863e  pop     rdi
0x14000863f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
