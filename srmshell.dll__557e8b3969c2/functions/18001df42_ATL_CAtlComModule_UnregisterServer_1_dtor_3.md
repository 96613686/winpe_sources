# _ATL::CAtlComModule::UnregisterServer_::_1_::dtor$3

- ea: `0x18001df42`
- end: `0x18001df4e`
- name: `_ATL::CAtlComModule::UnregisterServer_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004c74`

## pseudocode

```c
__int64 __fastcall ATL::CAtlComModule::UnregisterServer_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x18001df42  lea     rcx, [rdx+60h]
0x18001df49  jmp     ??1?$CComPtrBase@UIFsrmPropertyDefinition2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>(void)
```
