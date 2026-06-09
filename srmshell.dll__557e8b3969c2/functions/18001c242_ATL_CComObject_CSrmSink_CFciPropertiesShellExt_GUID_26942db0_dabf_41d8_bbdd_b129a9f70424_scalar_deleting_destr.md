# _ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor$0

- ea: `0x18001c242`
- end: `0x18001c24e`
- name: `_ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004e4c`

## pseudocode

```c
void __fastcall ATL::CComObject_CSrmSink_CFciPropertiesShellExt___GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::~CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>(*(_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x18001c242  mov     rcx, [rdx+40h]
0x18001c249  jmp     ??1?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@QEAA@XZ; CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::~CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>(void)
```
