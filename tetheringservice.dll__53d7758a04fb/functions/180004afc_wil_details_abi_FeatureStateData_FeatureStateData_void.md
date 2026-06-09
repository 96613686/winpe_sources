# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180004afc`
- end: `0x180004bcc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004884`

## callees

- `0x1800046b8`
- `0x180004afc`
- `0x180004f70`
- `0x1800075e4`
- `0x180009828`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004ba9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004ba9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b9c`

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
0x180004afc  mov     [rsp+arg_0], rbx
0x180004b01  mov     [rsp+arg_8], rsi
0x180004b06  push    rdi
0x180004b07  sub     rsp, 0E0h
0x180004b0e  mov     rbx, rcx
0x180004b11  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004b16  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004b1b  cmp     byte ptr [rbx+40h], 0
0x180004b1f  jz      short loc_180004B2F
0x180004b21  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180004b25  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004b2a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004b2f  cmp     byte ptr [rbx+80h], 0
0x180004b36  jz      short loc_180004B46
0x180004b38  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180004b3c  lea     rcx, [rsp+0E8h+var_88]; this
0x180004b41  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004b46  cmp     byte ptr [rbx+0C0h], 0
0x180004b4d  jz      short loc_180004B63
0x180004b4f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180004b56  lea     rcx, [rsp+0E8h+var_48]; this
0x180004b5e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004b63  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004b68  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180004b6d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004b72  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180004b77  mov     rsi, [rbx+108h]
0x180004b7e  mov     qword ptr [rbx+108h], 0
0x180004b89  test    rsi, rsi
0x180004b8c  jz      short loc_180004BA2
0x180004b8e  call    cs:__imp_GetProcessHeap
0x180004b94  mov     rcx, rax; hHeap
0x180004b97  mov     r8, rsi; lpMem
0x180004b9a  xor     edx, edx; dwFlags
0x180004b9c  call    cs:__imp_HeapFree
0x180004ba2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180004ba9  call    cs:__imp_DeleteCriticalSection
0x180004baf  lea     rcx, [rbx+8]; this
0x180004bb3  lea     r11, [rsp+0E8h+var_8]
0x180004bbb  mov     rbx, [r11+10h]
0x180004bbf  mov     rsi, [r11+18h]
0x180004bc3  mov     rsp, r11
0x180004bc6  pop     rdi
0x180004bc7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
