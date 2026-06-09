# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180019cf0`
- end: `0x180019dc0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180019b20`

## callees

- `0x180019a58`
- `0x180019cf0`
- `0x180019fbc`
- `0x18001b430`
- `0x18001c7b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019d9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019d9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d90`

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
0x180019cf0  mov     [rsp+arg_0], rbx
0x180019cf5  mov     [rsp+arg_8], rsi
0x180019cfa  push    rdi
0x180019cfb  sub     rsp, 0E0h
0x180019d02  mov     rbx, rcx
0x180019d05  lea     rcx, [rsp+0E8h+var_C8]; this
0x180019d0a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180019d0f  cmp     byte ptr [rbx+40h], 0
0x180019d13  jz      short loc_180019D23
0x180019d15  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180019d19  lea     rcx, [rsp+0E8h+var_C8]; this
0x180019d1e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180019d23  cmp     byte ptr [rbx+80h], 0
0x180019d2a  jz      short loc_180019D3A
0x180019d2c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180019d30  lea     rcx, [rsp+0E8h+var_88]; this
0x180019d35  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180019d3a  cmp     byte ptr [rbx+0C0h], 0
0x180019d41  jz      short loc_180019D57
0x180019d43  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180019d4a  lea     rcx, [rsp+0E8h+var_48]; this
0x180019d52  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180019d57  lea     rcx, [rsp+0E8h+var_C8]; this
0x180019d5c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180019d61  lea     rcx, [rsp+0E8h+var_C8]; this
0x180019d66  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180019d6b  mov     rsi, [rbx+108h]
0x180019d72  mov     qword ptr [rbx+108h], 0
0x180019d7d  test    rsi, rsi
0x180019d80  jz      short loc_180019D96
0x180019d82  call    cs:__imp_GetProcessHeap
0x180019d88  mov     r8, rsi; lpMem
0x180019d8b  xor     edx, edx; dwFlags
0x180019d8d  mov     rcx, rax; hHeap
0x180019d90  call    cs:__imp_HeapFree
0x180019d96  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180019d9d  call    cs:__imp_DeleteCriticalSection
0x180019da3  lea     rcx, [rbx+8]; this
0x180019da7  lea     r11, [rsp+0E8h+var_8]
0x180019daf  mov     rbx, [r11+10h]
0x180019db3  mov     rsi, [r11+18h]
0x180019db7  mov     rsp, r11
0x180019dba  pop     rdi
0x180019dbb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
