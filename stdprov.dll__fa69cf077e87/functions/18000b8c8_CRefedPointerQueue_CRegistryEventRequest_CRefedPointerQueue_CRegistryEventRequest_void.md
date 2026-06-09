# CRefedPointerQueue<CRegistryEventRequest>::~CRefedPointerQueue<CRegistryEventRequest>(void)

- ea: `0x18000b8c8`
- end: `0x18000b8da`
- name: `??1?$CRefedPointerQueue@VCRegistryEventRequest@@@@QEAA@XZ`
- size: `18`
- prototype: `void __fastcall(CFlexQueue *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800161d3`

## callees

- `0x18000b8e0`

## pseudocode

```c
void __fastcall CRefedPointerQueue<CRegistryEventRequest>::~CRefedPointerQueue<CRegistryEventRequest>(CFlexQueue *a1)
{
  CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>::~CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>(a1);
}

```

## disassembly

```asm
0x18000b8c8  mov     [rsp+arg_0], rcx
0x18000b8cd  sub     rsp, 28h
0x18000b8d1  add     rsp, 28h
0x18000b8d5  jmp     ??1?$CPointerQueue@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@@@QEAA@XZ; CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>::~CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>(void)
```
