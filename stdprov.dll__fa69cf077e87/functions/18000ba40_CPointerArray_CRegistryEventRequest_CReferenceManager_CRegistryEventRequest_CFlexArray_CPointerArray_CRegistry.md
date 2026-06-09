# CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::~CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>(void)

- ea: `0x18000ba40`
- end: `0x18000ba62`
- name: `??1?$CPointerArray@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@VCFlexArray@@@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(CFlexArray *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000840c`
- `0x18000ba28`
- `0x1800161fe`
- `0x18001641c`

## callees

- `0x180008508`

## import_xrefs

- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18000ba5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::~CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>(
        CFlexArray *a1)
{
  CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::RemoveAll();
  CFlexArray::~CFlexArray(a1);
}

```

## disassembly

```asm
0x18000ba40  mov     [rsp+arg_0], rcx
0x18000ba45  push    rbx
0x18000ba46  sub     rsp, 20h
0x18000ba4a  mov     rbx, rcx
0x18000ba4d  call    ?RemoveAll@?$CPointerArray@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@VCFlexArray@@@@QEAAXXZ; CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::RemoveAll(void)
0x18000ba52  nop
0x18000ba53  mov     rcx, rbx
0x18000ba56  add     rsp, 20h
0x18000ba5a  pop     rbx
0x18000ba5b  jmp     cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
```
