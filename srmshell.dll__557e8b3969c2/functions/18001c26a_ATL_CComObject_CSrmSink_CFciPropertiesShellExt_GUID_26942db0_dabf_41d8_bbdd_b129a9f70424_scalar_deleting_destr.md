# _ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor$2

- ea: `0x18001c26a`
- end: `0x18001c27a`
- name: `_ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004ffc`

## pseudocode

```c
void __fastcall ATL::CComObject_CSrmSink_CFciPropertiesShellExt___GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::_scalar_deleting_destructor__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(*(_QWORD *)(a2 + 80) + 8LL));
}

```

## disassembly

```asm
0x18001c26a  mov     rcx, [rdx+50h]
0x18001c271  add     rcx, 8; this
0x18001c275  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ
```
