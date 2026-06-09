# _ATL::CAtlComModule::UnregisterServer_::_1_::dtor$1

- ea: `0x18001df0c`
- end: `0x18001df18`
- name: `_ATL::CAtlComModule::UnregisterServer_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004c48`

## pseudocode

```c
__int64 __fastcall ATL::CAtlComModule::UnregisterServer_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IFsrmPropertiesPropSheet>::~CComPtr<IFsrmPropertiesPropSheet>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x18001df0c  lea     rcx, [rdx+60h]
0x18001df13  jmp     ??1?$CComPtr@UIFsrmPropertiesPropSheet@@@ATL@@QEAA@XZ; ATL::CComPtr<IFsrmPropertiesPropSheet>::~CComPtr<IFsrmPropertiesPropSheet>(void)
```
