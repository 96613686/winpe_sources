# _ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor$1

- ea: `0x18001c792`
- end: `0x18001c79e`
- name: `_ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004e4c`

## pseudocode

```c
void __fastcall ATL::CComObject_CSrmSink_CFciPropertiesShellExt___GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::~CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>(*(_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x18001c792  mov     rcx, [rdx+60h]
0x18001c799  jmp     ??1?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@QEAA@XZ; CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::~CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>(void)
```
