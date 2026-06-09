# _CTapiLuaLib::UpdateRegistry_::_1_::dtor$1

- ea: `0x18000516b`
- end: `0x180005177`
- name: `_CTapiLuaLib::UpdateRegistry_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180001f38`

## pseudocode

```c
void __fastcall CTapiLuaLib::UpdateRegistry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)(a2 + 48));
}

```

## disassembly

```asm
0x18000516b  lea     rcx, [rdx+30h]; this
0x180005172  jmp     ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
```
