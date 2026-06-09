# ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800137c0`
- end: `0x1800137c5`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@UEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `5`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, const wchar_t **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001325c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        const wchar_t **a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(this, a2, a3, a4);
}

```

## disassembly

```asm
0x1800137c0  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
