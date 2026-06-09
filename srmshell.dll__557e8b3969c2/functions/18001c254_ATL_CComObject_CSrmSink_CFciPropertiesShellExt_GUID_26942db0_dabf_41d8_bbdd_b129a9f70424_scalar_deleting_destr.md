# _ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor$1

- ea: `0x18001c254`
- end: `0x18001c264`
- name: `_ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor$1`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004c18`

## pseudocode

```c
void __fastcall ATL::CComObject_CSrmSink_CFciPropertiesShellExt___GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 64) + 8LL);
}

```

## disassembly

```asm
0x18001c254  mov     rcx, [rdx+40h]
0x18001c25b  add     rcx, 8
0x18001c25f  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
