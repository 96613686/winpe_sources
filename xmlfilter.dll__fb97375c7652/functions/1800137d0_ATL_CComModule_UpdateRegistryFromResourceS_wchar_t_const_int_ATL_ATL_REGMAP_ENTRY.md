# ATL::CComModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800137d0`
- end: `0x1800137d5`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@UEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `5`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const wchar_t *, int, const wchar_t **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800134f8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const wchar_t *a2,
        int a3,
        const wchar_t **a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(this, a2, a3, a4);
}

```

## disassembly

```asm
0x1800137d0  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)
```
