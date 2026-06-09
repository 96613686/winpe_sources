# CContainer::UpdateRegistry(int)

- ea: `0x1400054e0`
- end: `0x1400054f6`
- name: `?UpdateRegistry@CContainer@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14000550c`

## pseudocode

```c
__int64 __fastcall CContainer::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x64u, a1, 0);
}

```

## disassembly

```asm
0x1400054e0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1400054e3  mov     r8d, ecx; int
0x1400054e6  lea     rcx, ?_Module@@3VCServerAppModule@WTL@@A; this
0x1400054ed  lea     edx, [r9+64h]; unsigned int
0x1400054f1  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
