# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800035ac`
- end: `0x18000368b`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800097c8`

## callees

- `0x1800032a0`
- `0x1800035ac`
- `0x180003998`
- `0x1800088e4`
- `0x18000af14`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000364f`
- `KERNEL32!HeapFree` at `0x18000364f`
- `KERNEL32!DeleteCriticalSection` at `0x180003662`
- `KERNEL32!DeleteCriticalSection` at `0x180003662`
- `KERNEL32!GetProcessHeap` at `0x18000363b`
- `KERNEL32!GetProcessHeap` at `0x18000363b`

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
0x1800035ac  mov     [rsp+arg_0], rbx
0x1800035b1  mov     [rsp+arg_8], rsi
0x1800035b6  push    rdi
0x1800035b7  sub     rsp, 0E0h
0x1800035be  mov     rbx, rcx
0x1800035c1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800035c6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800035cb  cmp     byte ptr [rbx+40h], 0
0x1800035cf  jz      short loc_1800035DF
0x1800035d1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800035d5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800035da  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035df  cmp     byte ptr [rbx+80h], 0
0x1800035e6  jz      short loc_1800035F6
0x1800035e8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800035ec  lea     rcx, [rsp+0E8h+var_88]; this
0x1800035f1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035f6  cmp     byte ptr [rbx+0C0h], 0
0x1800035fd  jz      short loc_180003613
0x1800035ff  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003606  lea     rcx, [rsp+0E8h+var_48]; this
0x18000360e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003613  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003618  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000361d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003622  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003627  mov     rsi, [rbx+108h]
0x18000362e  and     qword ptr [rbx+108h], 0
0x180003636  test    rsi, rsi
0x180003639  jz      short loc_18000365B
0x18000363b  call    cs:__imp_GetProcessHeap
0x180003642  nop     dword ptr [rax+rax+00h]
0x180003647  mov     r8, rsi; lpMem
0x18000364a  xor     edx, edx; dwFlags
0x18000364c  mov     rcx, rax; hHeap
0x18000364f  call    cs:__imp_HeapFree
0x180003656  nop     dword ptr [rax+rax+00h]
0x18000365b  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003662  call    cs:__imp_DeleteCriticalSection
0x180003669  nop     dword ptr [rax+rax+00h]
0x18000366e  lea     rcx, [rbx+8]; this
0x180003672  lea     r11, [rsp+0E8h+var_8]
0x18000367a  mov     rbx, [r11+10h]
0x18000367e  mov     rsi, [r11+18h]
0x180003682  mov     rsp, r11
0x180003685  pop     rdi
0x180003686  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
