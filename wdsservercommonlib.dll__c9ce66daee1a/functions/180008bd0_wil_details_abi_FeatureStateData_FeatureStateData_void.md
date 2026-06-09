# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180008bd0`
- end: `0x180008caf`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c54c`

## callees

- `0x1800089b8`
- `0x180008bd0`
- `0x180008fbc`
- `0x18000b6fc`
- `0x18000d15c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008c86`
- `KERNEL32!DeleteCriticalSection` at `0x180008c86`
- `KERNEL32!GetProcessHeap` at `0x180008c5f`
- `KERNEL32!GetProcessHeap` at `0x180008c5f`
- `KERNEL32!HeapFree` at `0x180008c73`
- `KERNEL32!HeapFree` at `0x180008c73`

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
0x180008bd0  mov     [rsp+arg_0], rbx
0x180008bd5  mov     [rsp+arg_8], rsi
0x180008bda  push    rdi
0x180008bdb  sub     rsp, 0E0h
0x180008be2  mov     rbx, rcx
0x180008be5  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008bea  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008bef  cmp     byte ptr [rbx+40h], 0
0x180008bf3  jz      short loc_180008C03
0x180008bf5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008bf9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008bfe  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c03  cmp     byte ptr [rbx+80h], 0
0x180008c0a  jz      short loc_180008C1A
0x180008c0c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008c10  lea     rcx, [rsp+0E8h+var_88]; this
0x180008c15  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c1a  cmp     byte ptr [rbx+0C0h], 0
0x180008c21  jz      short loc_180008C37
0x180008c23  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180008c2a  lea     rcx, [rsp+0E8h+var_48]; this
0x180008c32  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c37  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008c3c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180008c41  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008c46  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008c4b  mov     rsi, [rbx+108h]
0x180008c52  and     qword ptr [rbx+108h], 0
0x180008c5a  test    rsi, rsi
0x180008c5d  jz      short loc_180008C7F
0x180008c5f  call    cs:__imp_GetProcessHeap
0x180008c66  nop     dword ptr [rax+rax+00h]
0x180008c6b  mov     r8, rsi; lpMem
0x180008c6e  xor     edx, edx; dwFlags
0x180008c70  mov     rcx, rax; hHeap
0x180008c73  call    cs:__imp_HeapFree
0x180008c7a  nop     dword ptr [rax+rax+00h]
0x180008c7f  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180008c86  call    cs:__imp_DeleteCriticalSection
0x180008c8d  nop     dword ptr [rax+rax+00h]
0x180008c92  lea     rcx, [rbx+8]; this
0x180008c96  lea     r11, [rsp+0E8h+var_8]
0x180008c9e  mov     rbx, [r11+10h]
0x180008ca2  mov     rsi, [r11+18h]
0x180008ca6  mov     rsp, r11
0x180008ca9  pop     rdi
0x180008caa  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
