# CWdsMetadata::~CWdsMetadata(void)

- ea: `0x18000d100`
- end: `0x18000d12d`
- name: `??1CWdsMetadata@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(CWdsMetadata *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180006020`
- `0x180007c28`
- `0x180008f9c`
- `0x1800096e8`
- `0x1800133c4`
- `0x180013508`

## callees

- `0x18000dc40`
- `0x18000dce8`
- `0x18000f8fc`

## pseudocode

```c
void __fastcall CWdsMetadata::~CWdsMetadata(CWdsMetadata *this)
{
  CWdsMetadata::Shutdown(this);
  CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear((char *)this + 48);
  CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear((char *)this + 24);
  CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(this);
}

```

## disassembly

```asm
0x18000d100  push    rbx
0x18000d102  sub     rsp, 20h
0x18000d106  mov     rbx, rcx
0x18000d109  call    ?Shutdown@CWdsMetadata@@QEAAXXZ; CWdsMetadata::Shutdown(void)
0x18000d10e  lea     rcx, [rbx+30h]
0x18000d112  call    ?Clear@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear(void)
0x18000d117  lea     rcx, [rbx+18h]
0x18000d11b  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x18000d120  mov     rcx, rbx
0x18000d123  add     rsp, 20h
0x18000d127  pop     rbx
0x18000d128  jmp     ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
```
