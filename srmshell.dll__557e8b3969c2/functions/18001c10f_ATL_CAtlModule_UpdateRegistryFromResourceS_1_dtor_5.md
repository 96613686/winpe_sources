# _ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$5

- ea: `0x18001c10f`
- end: `0x18001c11b`
- name: `_ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005024`

## pseudocode

```c
void __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(*(ATL::CComSafeDeleteCriticalSection **)(a2 + 48));
}

```

## disassembly

```asm
0x18001c10f  mov     rcx, [rdx+30h]; this
0x18001c116  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
