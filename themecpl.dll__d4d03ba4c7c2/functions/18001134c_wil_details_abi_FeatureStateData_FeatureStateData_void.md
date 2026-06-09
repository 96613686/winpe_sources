# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18001134c`
- end: `0x18001142e`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001d8f8`

## callees

- `0x18001109c`
- `0x18001134c`
- `0x180011644`
- `0x18001ca40`
- `0x18001e8b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011405`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011405`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800113de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800113de`

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
0x18001134c  mov     [rsp+arg_0], rbx
0x180011351  mov     [rsp+arg_8], rsi
0x180011356  push    rdi
0x180011357  sub     rsp, 0E0h
0x18001135e  mov     rbx, rcx
0x180011361  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011366  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001136b  cmp     byte ptr [rbx+40h], 0
0x18001136f  jz      short loc_18001137F
0x180011371  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180011375  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001137a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001137f  cmp     byte ptr [rbx+80h], 0
0x180011386  jz      short loc_180011396
0x180011388  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18001138c  lea     rcx, [rsp+0E8h+var_88]; this
0x180011391  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011396  cmp     byte ptr [rbx+0C0h], 0
0x18001139d  jz      short loc_1800113B3
0x18001139f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800113a6  lea     rcx, [rsp+0E8h+var_48]; this
0x1800113ae  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800113b3  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800113b8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800113bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800113c2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800113c7  mov     rsi, [rbx+108h]
0x1800113ce  mov     qword ptr [rbx+108h], 0
0x1800113d9  test    rsi, rsi
0x1800113dc  jz      short loc_1800113FE
0x1800113de  call    cs:__imp_GetProcessHeap
0x1800113e5  nop     dword ptr [rax+rax+00h]
0x1800113ea  mov     rcx, rax; hHeap
0x1800113ed  mov     r8, rsi; lpMem
0x1800113f0  xor     edx, edx; dwFlags
0x1800113f2  call    cs:__imp_HeapFree
0x1800113f9  nop     dword ptr [rax+rax+00h]
0x1800113fe  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180011405  call    cs:__imp_DeleteCriticalSection
0x18001140c  nop     dword ptr [rax+rax+00h]
0x180011411  lea     rcx, [rbx+8]; this
0x180011415  lea     r11, [rsp+0E8h+var_8]
0x18001141d  mov     rbx, [r11+10h]
0x180011421  mov     rsi, [r11+18h]
0x180011425  mov     rsp, r11
0x180011428  pop     rdi
0x180011429  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
