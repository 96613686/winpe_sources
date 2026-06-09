# CXmlContentFilter::UpdateRegistry(int)

- ea: `0x180013240`
- end: `0x180013256`
- name: `?UpdateRegistry@CXmlContentFilter@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18001325c`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x65u, a1, 0);
}

```

## disassembly

```asm
0x180013240  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180013243  mov     r8d, ecx; int
0x180013246  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18001324d  lea     edx, [r9+65h]; unsigned int
0x180013251  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
