# _ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$4

- ea: `0x18001e910`
- end: `0x18001e91c`
- name: `_ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180011e2c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::~CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>(*(_QWORD *)(a2 + 144));
}

```

## disassembly

```asm
0x18001e910  mov     rcx, [rdx+90h]
0x18001e917  jmp     ??1?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::~CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>(void)
```
