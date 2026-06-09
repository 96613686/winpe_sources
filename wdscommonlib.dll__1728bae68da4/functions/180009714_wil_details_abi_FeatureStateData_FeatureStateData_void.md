# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180009714`
- end: `0x1800097f3`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d08c`

## callees

- `0x180009508`
- `0x180009714`
- `0x180009b00`
- `0x18000c23c`
- `0x18000dc9c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800097ca`
- `KERNEL32!DeleteCriticalSection` at `0x1800097ca`
- `KERNEL32!GetProcessHeap` at `0x1800097a3`
- `KERNEL32!GetProcessHeap` at `0x1800097a3`
- `KERNEL32!HeapFree` at `0x1800097b7`
- `KERNEL32!HeapFree` at `0x1800097b7`

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
0x180009714  mov     [rsp+arg_0], rbx
0x180009719  mov     [rsp+arg_8], rsi
0x18000971e  push    rdi
0x18000971f  sub     rsp, 0E0h
0x180009726  mov     rbx, rcx
0x180009729  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000972e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009733  cmp     byte ptr [rbx+40h], 0
0x180009737  jz      short loc_180009747
0x180009739  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000973d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009742  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009747  cmp     byte ptr [rbx+80h], 0
0x18000974e  jz      short loc_18000975E
0x180009750  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180009754  lea     rcx, [rsp+0E8h+var_88]; this
0x180009759  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000975e  cmp     byte ptr [rbx+0C0h], 0
0x180009765  jz      short loc_18000977B
0x180009767  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000976e  lea     rcx, [rsp+0E8h+var_48]; this
0x180009776  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000977b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009780  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009785  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000978a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000978f  mov     rsi, [rbx+108h]
0x180009796  and     qword ptr [rbx+108h], 0
0x18000979e  test    rsi, rsi
0x1800097a1  jz      short loc_1800097C3
0x1800097a3  call    cs:__imp_GetProcessHeap
0x1800097aa  nop     dword ptr [rax+rax+00h]
0x1800097af  mov     r8, rsi; lpMem
0x1800097b2  xor     edx, edx; dwFlags
0x1800097b4  mov     rcx, rax; hHeap
0x1800097b7  call    cs:__imp_HeapFree
0x1800097be  nop     dword ptr [rax+rax+00h]
0x1800097c3  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800097ca  call    cs:__imp_DeleteCriticalSection
0x1800097d1  nop     dword ptr [rax+rax+00h]
0x1800097d6  lea     rcx, [rbx+8]; this
0x1800097da  lea     r11, [rsp+0E8h+var_8]
0x1800097e2  mov     rbx, [r11+10h]
0x1800097e6  mov     rsi, [r11+18h]
0x1800097ea  mov     rsp, r11
0x1800097ed  pop     rdi
0x1800097ee  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
