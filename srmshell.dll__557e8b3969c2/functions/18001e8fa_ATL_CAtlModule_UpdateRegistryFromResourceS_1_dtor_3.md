# _ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$3

- ea: `0x18001e8fa`
- end: `0x18001e90a`
- name: `_ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$3`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004ffc`

## pseudocode

```c
void __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(a2 + 96));
}

```

## disassembly

```asm
0x18001e8fa  lea     rcx, [rdx+40h]
0x18001e901  add     rcx, 20h ; ' '; this
0x18001e905  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
