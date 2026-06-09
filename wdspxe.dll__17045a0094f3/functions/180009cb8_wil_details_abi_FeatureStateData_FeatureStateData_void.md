# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180009cb8`
- end: `0x180009d97`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e7dc`

## callees

- `0x180009a4c`
- `0x180009cb8`
- `0x18000a0a4`
- `0x18000d3c4`
- `0x18001002c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009d6e`
- `KERNEL32!DeleteCriticalSection` at `0x180009d6e`
- `KERNEL32!GetProcessHeap` at `0x180009d47`
- `KERNEL32!GetProcessHeap` at `0x180009d47`
- `KERNEL32!HeapFree` at `0x180009d5b`
- `KERNEL32!HeapFree` at `0x180009d5b`

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
0x180009cb8  mov     [rsp+arg_0], rbx
0x180009cbd  mov     [rsp+arg_8], rsi
0x180009cc2  push    rdi
0x180009cc3  sub     rsp, 0E0h
0x180009cca  mov     rbx, rcx
0x180009ccd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009cd2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009cd7  cmp     byte ptr [rbx+40h], 0
0x180009cdb  jz      short loc_180009CEB
0x180009cdd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180009ce1  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009ce6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009ceb  cmp     byte ptr [rbx+80h], 0
0x180009cf2  jz      short loc_180009D02
0x180009cf4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180009cf8  lea     rcx, [rsp+0E8h+var_88]; this
0x180009cfd  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009d02  cmp     byte ptr [rbx+0C0h], 0
0x180009d09  jz      short loc_180009D1F
0x180009d0b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180009d12  lea     rcx, [rsp+0E8h+var_48]; this
0x180009d1a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009d1f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009d24  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009d29  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009d2e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180009d33  mov     rsi, [rbx+108h]
0x180009d3a  and     qword ptr [rbx+108h], 0
0x180009d42  test    rsi, rsi
0x180009d45  jz      short loc_180009D67
0x180009d47  call    cs:__imp_GetProcessHeap
0x180009d4e  nop     dword ptr [rax+rax+00h]
0x180009d53  mov     r8, rsi; lpMem
0x180009d56  xor     edx, edx; dwFlags
0x180009d58  mov     rcx, rax; hHeap
0x180009d5b  call    cs:__imp_HeapFree
0x180009d62  nop     dword ptr [rax+rax+00h]
0x180009d67  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180009d6e  call    cs:__imp_DeleteCriticalSection
0x180009d75  nop     dword ptr [rax+rax+00h]
0x180009d7a  lea     rcx, [rbx+8]; this
0x180009d7e  lea     r11, [rsp+0E8h+var_8]
0x180009d86  mov     rbx, [r11+10h]
0x180009d8a  mov     rsi, [r11+18h]
0x180009d8e  mov     rsp, r11
0x180009d91  pop     rdi
0x180009d92  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
