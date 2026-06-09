# _ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor$1

- ea: `0x18001c0d1`
- end: `0x18001c0e1`
- name: `_ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor$1`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004c18`

## pseudocode

```c
void __fastcall ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 48) + 8LL);
}

```

## disassembly

```asm
0x18001c0d1  mov     rcx, [rdx+30h]
0x18001c0d8  add     rcx, 8
0x18001c0dc  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
