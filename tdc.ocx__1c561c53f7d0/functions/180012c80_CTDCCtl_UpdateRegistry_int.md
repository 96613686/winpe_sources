# CTDCCtl::UpdateRegistry(int)

- ea: `0x180012c80`
- end: `0x180012c96`
- name: `?UpdateRegistry@CTDCCtl@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180012cac`

## pseudocode

```c
__int64 __fastcall CTDCCtl::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x65u, a1, 0);
}

```

## disassembly

```asm
0x180012c80  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180012c83  mov     r8d, ecx; int
0x180012c86  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x180012c8d  lea     edx, [r9+65h]; unsigned int
0x180012c91  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
