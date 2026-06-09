# _CPointerArray_CRegistryEventRequest_CReferenceManager_CRegistryEventRequest__CFlexArray_::_CPointerArray_CRegistryEventRequest_CReferenceManager_CRegistryEventRequest__CFlexArray__::_1_::dtor$0

- ea: `0x18001649e`
- end: `0x1800164ac`
- name: `_CPointerArray_CRegistryEventRequest_CReferenceManager_CRegistryEventRequest__CFlexArray_::_CPointerArray_CRegistryEventRequest_CReferenceManager_CRegistryEventRequest__CFlexArray__::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x1800164a5`

## pseudocode

```c
void __fastcall CPointerArray_CRegistryEventRequest_CReferenceManager_CRegistryEventRequest__CFlexArray_::_CPointerArray_CRegistryEventRequest_CReferenceManager_CRegistryEventRequest__CFlexArray__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  CFlexArray::~CFlexArray(*(CFlexArray **)(a2 + 48));
}

```

## disassembly

```asm
0x18001649e  mov     rcx, [rdx+30h]
0x1800164a5  jmp     cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
```
