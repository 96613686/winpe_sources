# _CRefedPointerQueue_CRegistryEventRequest_::_CRefedPointerQueue_CRegistryEventRequest__::_1_::dtor$0

- ea: `0x1800165b1`
- end: `0x1800165bd`
- name: `_CRefedPointerQueue_CRegistryEventRequest_::_CRefedPointerQueue_CRegistryEventRequest__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b8e0`

## pseudocode

```c
void __fastcall CRefedPointerQueue_CRegistryEventRequest_::_CRefedPointerQueue_CRegistryEventRequest__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>::~CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>(*(CFlexQueue **)(a2 + 48));
}

```

## disassembly

```asm
0x1800165b1  mov     rcx, [rdx+30h]
0x1800165b8  jmp     ??1?$CPointerQueue@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@@@QEAA@XZ; CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>::~CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>(void)
```
