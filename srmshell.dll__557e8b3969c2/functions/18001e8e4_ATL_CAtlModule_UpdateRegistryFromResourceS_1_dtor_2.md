# _ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$2

- ea: `0x18001e8e4`
- end: `0x18001e8f4`
- name: `_ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180011f90`

## pseudocode

```c
void __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ATL::CExpansionVector::~CExpansionVector((ATL::CExpansionVector *)(a2 + 72));
}

```

## disassembly

```asm
0x18001e8e4  lea     rcx, [rdx+40h]
0x18001e8eb  add     rcx, 8; this
0x18001e8ef  jmp     ??1CExpansionVector@ATL@@QEAA@XZ; ATL::CExpansionVector::~CExpansionVector(void)
```
