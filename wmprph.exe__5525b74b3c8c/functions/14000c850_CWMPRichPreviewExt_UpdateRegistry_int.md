# CWMPRichPreviewExt::UpdateRegistry(int)

- ea: `0x14000c850`
- end: `0x14000c858`
- name: `?UpdateRegistry@CWMPRichPreviewExt@@SAJH@Z`
- size: `8`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000c860`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewExt::UpdateRegistry(
        ATL::CComModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CComModule::UpdateRegistryFromResourceS(a1, a2, (int)a1, a4);
}

```

## disassembly

```asm
0x14000c850  mov     r8d, ecx; int
0x14000c853  jmp     ?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
