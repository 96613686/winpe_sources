# CWdsMetadata::~CWdsMetadata(void)

- ea: `0x180008d44`
- end: `0x180008d99`
- name: `??1CWdsMetadata@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CWdsMetadata *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800055b0`
- `0x180005b10`
- `0x180005c80`
- `0x180006210`
- `0x180006320`
- `0x180006460`
- `0x180006598`
- `0x1800068d0`
- `0x180007214`

## callees

- `0x180009278`
- `0x180009300`

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
0x180008d44  mov     [rsp+arg_0], rbx
0x180008d49  mov     [rsp+arg_8], rsi
0x180008d4e  push    rdi
0x180008d4f  sub     rsp, 20h
0x180008d53  mov     rsi, rcx
0x180008d56  add     rcx, 30h ; '0'
0x180008d5a  call    ?Clear@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear(void)
0x180008d5f  mov     rcx, rsi
0x180008d62  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x180008d67  lea     rcx, [rsi+18h]
0x180008d6b  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x180008d70  lea     rcx, [rsi+30h]
0x180008d74  call    ?Clear@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::Clear(void)
0x180008d79  lea     rcx, [rsi+18h]
0x180008d7d  call    ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
0x180008d82  mov     rcx, rsi
0x180008d85  mov     rbx, [rsp+28h+arg_0]
0x180008d8a  mov     rsi, [rsp+28h+arg_8]
0x180008d8f  add     rsp, 20h
0x180008d93  pop     rdi
0x180008d94  jmp     ?Clear@?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer>::Clear(void)
```
