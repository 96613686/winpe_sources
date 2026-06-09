# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140008dc4`
- end: `0x140008e94`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140008b84`

## callees

- `0x140008abc`
- `0x140008dc4`
- `0x140009090`
- `0x14000a5b8`
- `0x14000bc90`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008e64`
- `KERNEL32!HeapFree` at `0x140008e64`
- `KERNEL32!DeleteCriticalSection` at `0x140008e71`
- `KERNEL32!DeleteCriticalSection` at `0x140008e71`
- `KERNEL32!GetProcessHeap` at `0x140008e56`
- `KERNEL32!GetProcessHeap` at `0x140008e56`

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
0x140008dc4  mov     [rsp+arg_0], rbx
0x140008dc9  mov     [rsp+arg_8], rsi
0x140008dce  push    rdi
0x140008dcf  sub     rsp, 0E0h
0x140008dd6  mov     rbx, rcx
0x140008dd9  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008dde  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140008de3  cmp     byte ptr [rbx+40h], 0
0x140008de7  jz      short loc_140008DF7
0x140008de9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140008ded  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008df2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008df7  cmp     byte ptr [rbx+80h], 0
0x140008dfe  jz      short loc_140008E0E
0x140008e00  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140008e04  lea     rcx, [rsp+0E8h+var_88]; this
0x140008e09  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008e0e  cmp     byte ptr [rbx+0C0h], 0
0x140008e15  jz      short loc_140008E2B
0x140008e17  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140008e1e  lea     rcx, [rsp+0E8h+var_48]; this
0x140008e26  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008e2b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008e30  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140008e35  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008e3a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140008e3f  mov     rsi, [rbx+108h]
0x140008e46  mov     qword ptr [rbx+108h], 0
0x140008e51  test    rsi, rsi
0x140008e54  jz      short loc_140008E6A
0x140008e56  call    cs:__imp_GetProcessHeap
0x140008e5c  mov     r8, rsi; lpMem
0x140008e5f  xor     edx, edx; dwFlags
0x140008e61  mov     rcx, rax; hHeap
0x140008e64  call    cs:__imp_HeapFree
0x140008e6a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140008e71  call    cs:__imp_DeleteCriticalSection
0x140008e77  lea     rcx, [rbx+8]; this
0x140008e7b  lea     r11, [rsp+0E8h+var_8]
0x140008e83  mov     rbx, [r11+10h]
0x140008e87  mov     rsi, [r11+18h]
0x140008e8b  mov     rsp, r11
0x140008e8e  pop     rdi
0x140008e8f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
