# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000927c`
- end: `0x18000934c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800090f4`

## callees

- `0x180008f60`
- `0x18000927c`
- `0x1800096e8`
- `0x18000e9d0`
- `0x1800110e8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009329`
- `KERNEL32!DeleteCriticalSection` at `0x180009329`
- `KERNEL32!GetProcessHeap` at `0x18000930e`
- `KERNEL32!GetProcessHeap` at `0x18000930e`
- `KERNEL32!HeapFree` at `0x18000931c`
- `KERNEL32!HeapFree` at `0x18000931c`

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
0x18000927c  mov     [rsp+arg_0], rbx
0x180009281  mov     [rsp+arg_8], rsi
0x180009286  push    rdi
0x180009287  sub     rsp, 0E0h
0x18000928e  mov     rbx, rcx
0x180009291  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009296  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000929b  cmp     byte ptr [rbx+40h], 0
0x18000929f  jz      short loc_1800092AF
0x1800092a1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800092a5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800092aa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800092af  cmp     byte ptr [rbx+80h], 0
0x1800092b6  jz      short loc_1800092C6
0x1800092b8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800092bc  lea     rcx, [rsp+0E8h+var_88]; this
0x1800092c1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800092c6  cmp     byte ptr [rbx+0C0h], 0
0x1800092cd  jz      short loc_1800092E3
0x1800092cf  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800092d6  lea     rcx, [rsp+0E8h+var_48]; this
0x1800092de  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800092e3  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800092e8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800092ed  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800092f2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800092f7  mov     rsi, [rbx+108h]
0x1800092fe  mov     qword ptr [rbx+108h], 0
0x180009309  test    rsi, rsi
0x18000930c  jz      short loc_180009322
0x18000930e  call    cs:__imp_GetProcessHeap
0x180009314  mov     rcx, rax; hHeap
0x180009317  mov     r8, rsi; lpMem
0x18000931a  xor     edx, edx; dwFlags
0x18000931c  call    cs:__imp_HeapFree
0x180009322  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180009329  call    cs:__imp_DeleteCriticalSection
0x18000932f  lea     rcx, [rbx+8]; this
0x180009333  lea     r11, [rsp+0E8h+var_8]
0x18000933b  mov     rbx, [r11+10h]
0x18000933f  mov     rsi, [r11+18h]
0x180009343  mov     rsp, r11
0x180009346  pop     rdi
0x180009347  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
