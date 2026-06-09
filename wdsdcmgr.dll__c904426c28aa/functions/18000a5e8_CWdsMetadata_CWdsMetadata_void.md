# CWdsMetadata::~CWdsMetadata(void)

- ea: `0x18000a5e8`
- end: `0x18000a63d`
- name: `??1CWdsMetadata@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CWdsMetadata *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e14`
- `0x180002268`
- `0x180002bd8`
- `0x180003398`
- `0x1800042f4`
- `0x180004dbc`
- `0x180004f98`
- `0x180005818`
- `0x18000600c`
- `0x1800078b0`
- `0x18000b47c`
- `0x18000e4c4`
- `0x180016070`

## callees

- `0x18000d2f0`
- `0x18000d40c`

## pseudocode

```c
void __fastcall CWdsMetadata::~CWdsMetadata(CWdsMetadata *this)
{
  CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear((char *)this + 48);
  CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(this);
  CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear((char *)this + 24);
  CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear((char *)this + 48);
  CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear((char *)this + 24);
  CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(this);
}

```

## disassembly

```asm
0x18000a5e8  mov     [rsp+arg_0], rbx
0x18000a5ed  mov     [rsp+arg_8], rsi
0x18000a5f2  push    rdi
0x18000a5f3  sub     rsp, 20h
0x18000a5f7  mov     rsi, rcx
0x18000a5fa  add     rcx, 30h ; '0'
0x18000a5fe  call    ?Clear@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear(void)
0x18000a603  mov     rcx, rsi
0x18000a606  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x18000a60b  lea     rcx, [rsi+18h]
0x18000a60f  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x18000a614  lea     rcx, [rsi+30h]
0x18000a618  call    ?Clear@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear(void)
0x18000a61d  lea     rcx, [rsi+18h]
0x18000a621  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x18000a626  mov     rcx, rsi
0x18000a629  mov     rbx, [rsp+28h+arg_0]
0x18000a62e  mov     rsi, [rsp+28h+arg_8]
0x18000a633  add     rsp, 20h
0x18000a637  pop     rdi
0x18000a638  jmp     ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
```
