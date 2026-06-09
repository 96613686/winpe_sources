# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1400087d4`
- end: `0x1400088a4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400086e0`

## callees

- `0x14000854c`
- `0x1400087d4`
- `0x140008b24`
- `0x14000afc8`
- `0x14000c504`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140008881`
- `KERNEL32!DeleteCriticalSection` at `0x140008881`
- `KERNEL32!HeapFree` at `0x140008874`
- `KERNEL32!HeapFree` at `0x140008874`
- `KERNEL32!GetProcessHeap` at `0x140008866`
- `KERNEL32!GetProcessHeap` at `0x140008866`

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
0x1400087d4  mov     [rsp+arg_0], rbx
0x1400087d9  mov     [rsp+arg_8], rsi
0x1400087de  push    rdi
0x1400087df  sub     rsp, 0E0h
0x1400087e6  mov     rbx, rcx
0x1400087e9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400087ee  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400087f3  cmp     byte ptr [rbx+40h], 0
0x1400087f7  jz      short loc_140008807
0x1400087f9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400087fd  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008802  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008807  cmp     byte ptr [rbx+80h], 0
0x14000880e  jz      short loc_14000881E
0x140008810  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140008814  lea     rcx, [rsp+0E8h+var_88]; this
0x140008819  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000881e  cmp     byte ptr [rbx+0C0h], 0
0x140008825  jz      short loc_14000883B
0x140008827  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000882e  lea     rcx, [rsp+0E8h+var_48]; this
0x140008836  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000883b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008840  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140008845  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000884a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000884f  mov     rsi, [rbx+108h]
0x140008856  mov     qword ptr [rbx+108h], 0
0x140008861  test    rsi, rsi
0x140008864  jz      short loc_14000887A
0x140008866  call    cs:__imp_GetProcessHeap
0x14000886c  mov     r8, rsi; lpMem
0x14000886f  xor     edx, edx; dwFlags
0x140008871  mov     rcx, rax; hHeap
0x140008874  call    cs:__imp_HeapFree
0x14000887a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140008881  call    cs:__imp_DeleteCriticalSection
0x140008887  lea     rcx, [rbx+8]; this
0x14000888b  lea     r11, [rsp+0E8h+var_8]
0x140008893  mov     rbx, [r11+10h]
0x140008897  mov     rsi, [r11+18h]
0x14000889b  mov     rsp, r11
0x14000889e  pop     rdi
0x14000889f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
