# _ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor$4

- ea: `0x18001c7d0`
- end: `0x18001c7dc`
- name: `_ATL::CComObject_CSrmSink_CFciPropertiesShellExt_&_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005024`

## pseudocode

```c
void __fastcall ATL::CComObject_CSrmSink_CFciPropertiesShellExt___GUID_26942db0_dabf_41d8_bbdd_b129a9f70424___::CreateInstance_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(*(ATL::CComSafeDeleteCriticalSection **)(a2 + 40));
}

```

## disassembly

```asm
0x18001c7d0  mov     rcx, [rdx+28h]; this
0x18001c7d7  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
