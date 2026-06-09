# CFciPropertiesShellExt::UpdateRegistry(int)

- ea: `0x180015790`
- end: `0x180015798`
- name: `?UpdateRegistry@CFciPropertiesShellExt@@SAJH@Z`
- size: `8`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, unsigned int, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800157a0`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::UpdateRegistry(
        ATL::CAtlModule *a1,
        unsigned int a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, a2, (int)a1, a4);
}

```

## disassembly

```asm
0x180015790  mov     r8d, ecx; int
0x180015793  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
