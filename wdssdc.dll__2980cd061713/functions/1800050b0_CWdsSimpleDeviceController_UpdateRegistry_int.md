# CWdsSimpleDeviceController::UpdateRegistry(int)

- ea: `0x1800050b0`
- end: `0x1800050c0`
- name: `?UpdateRegistry@CWdsSimpleDeviceController@@SAJH@Z`
- size: `16`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800050c8`

## pseudocode

```c
__int64 __fastcall CWdsSimpleDeviceController::UpdateRegistry(ATL::CAtlModule *a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0xCAu, (int)a1, 0);
}

```

## disassembly

```asm
0x1800050b0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1800050b3  mov     r8d, ecx; int
0x1800050b6  mov     edx, 0CAh; unsigned int
0x1800050bb  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
