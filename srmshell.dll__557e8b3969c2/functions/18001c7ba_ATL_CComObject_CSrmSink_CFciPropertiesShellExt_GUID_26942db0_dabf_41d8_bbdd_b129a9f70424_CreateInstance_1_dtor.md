# _ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor$3

- ea: `0x18001c7ba`
- end: `0x18001c7ca`
- name: `_ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor$3`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004ffc`

## pseudocode

```c
void __fastcall ATL::CComObject_CSrmSink_CFciPropertiesShellExt___GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(*(_QWORD *)(a2 + 104) + 8LL));
}

```

## disassembly

```asm
0x18001c7ba  mov     rcx, [rdx+68h]
0x18001c7c1  add     rcx, 8; this
0x18001c7c5  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
