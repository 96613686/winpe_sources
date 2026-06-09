# _ATL::CAtlComModule::UnregisterServer_::_1_::dtor$0

- ea: `0x18001d140`
- end: `0x18001d14c`
- name: `_ATL::CAtlComModule::UnregisterServer_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800022b8`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::UnregisterServer_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSrmComBSTR::~CSrmComBSTR((BSTR *)(a2 + 104));
}

```

## disassembly

```asm
0x18001d140  lea     rcx, [rdx+68h]; this
0x18001d147  jmp     ??1CSrmComBSTR@@QEAA@XZ; CSrmComBSTR::~CSrmComBSTR(void)
```
