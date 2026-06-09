# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140004f94`
- end: `0x140005064`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004ce4`

## callees

- `0x140004c1c`
- `0x140004f94`
- `0x140005260`
- `0x140009284`
- `0x14000aef0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005034`
- `KERNEL32!HeapFree` at `0x140005034`
- `KERNEL32!DeleteCriticalSection` at `0x140005041`
- `KERNEL32!DeleteCriticalSection` at `0x140005041`
- `KERNEL32!GetProcessHeap` at `0x140005026`
- `KERNEL32!GetProcessHeap` at `0x140005026`

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
0x140004f94  mov     [rsp+arg_0], rbx
0x140004f99  mov     [rsp+arg_8], rsi
0x140004f9e  push    rdi
0x140004f9f  sub     rsp, 0E0h
0x140004fa6  mov     rbx, rcx
0x140004fa9  lea     rcx, [rsp+0E8h+var_C8]; this
0x140004fae  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140004fb3  cmp     byte ptr [rbx+40h], 0
0x140004fb7  jz      short loc_140004FC7
0x140004fb9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140004fbd  lea     rcx, [rsp+0E8h+var_C8]; this
0x140004fc2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140004fc7  cmp     byte ptr [rbx+80h], 0
0x140004fce  jz      short loc_140004FDE
0x140004fd0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140004fd4  lea     rcx, [rsp+0E8h+var_88]; this
0x140004fd9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140004fde  cmp     byte ptr [rbx+0C0h], 0
0x140004fe5  jz      short loc_140004FFB
0x140004fe7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140004fee  lea     rcx, [rsp+0E8h+var_48]; this
0x140004ff6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140004ffb  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005000  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140005005  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000500a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000500f  mov     rsi, [rbx+108h]
0x140005016  mov     qword ptr [rbx+108h], 0
0x140005021  test    rsi, rsi
0x140005024  jz      short loc_14000503A
0x140005026  call    cs:__imp_GetProcessHeap
0x14000502c  mov     r8, rsi; lpMem
0x14000502f  xor     edx, edx; dwFlags
0x140005031  mov     rcx, rax; hHeap
0x140005034  call    cs:__imp_HeapFree
0x14000503a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140005041  call    cs:__imp_DeleteCriticalSection
0x140005047  lea     rcx, [rbx+8]; this
0x14000504b  lea     r11, [rsp+0E8h+var_8]
0x140005053  mov     rbx, [r11+10h]
0x140005057  mov     rsi, [r11+18h]
0x14000505b  mov     rsp, r11
0x14000505e  pop     rdi
0x14000505f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
