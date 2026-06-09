# _ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor$2

- ea: `0x18001c7a4`
- end: `0x18001c7b4`
- name: `_ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004c18`

## pseudocode

```c
void __fastcall ATL::CComObject_CSrmSink_CFciPropertiesShellExt___GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 96) + 8LL);
}

```

## disassembly

```asm
0x18001c7a4  mov     rcx, [rdx+60h]
0x18001c7ab  add     rcx, 8
0x18001c7af  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
