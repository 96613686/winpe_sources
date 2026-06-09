# _ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$6

- ea: `0x18001e7f2`
- end: `0x18001e802`
- name: `_ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$6`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004c18`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor_6(
        __int64 a1,
        __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 144) + 8LL);
}

```

## disassembly

```asm
0x18001e7f2  mov     rcx, [rdx+90h]
0x18001e7f9  add     rcx, 8
0x18001e7fd  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
