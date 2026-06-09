# CRefedPointerArray<CRegistryEventRequest>::~CRefedPointerArray<CRegistryEventRequest>(void)

- ea: `0x18000ba28`
- end: `0x18000ba3a`
- name: `??1?$CRefedPointerArray@VCRegistryEventRequest@@@@QEAA@XZ`
- size: `18`
- prototype: `void __fastcall(CFlexArray *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001618b`

## callees

- `0x18000ba40`

## pseudocode

```c
void __fastcall CRefedPointerArray<CRegistryEventRequest>::~CRefedPointerArray<CRegistryEventRequest>(CFlexArray *a1)
{
  CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::~CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>(a1);
}

```

## disassembly

```asm
0x18000ba28  mov     [rsp+arg_0], rcx
0x18000ba2d  sub     rsp, 28h
0x18000ba31  add     rsp, 28h
0x18000ba35  jmp     ??1?$CPointerArray@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::~CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>(void)
```
