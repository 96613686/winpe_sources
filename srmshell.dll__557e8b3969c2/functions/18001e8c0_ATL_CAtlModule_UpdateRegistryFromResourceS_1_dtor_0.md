# _ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$0

- ea: `0x18001e8c0`
- end: `0x18001e8cc`
- name: `_ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18001202c`

## pseudocode

```c
void __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)(a2 + 64));
}

```

## disassembly

```asm
0x18001e8c0  lea     rcx, [rdx+40h]; this
0x18001e8c7  jmp     ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
```
