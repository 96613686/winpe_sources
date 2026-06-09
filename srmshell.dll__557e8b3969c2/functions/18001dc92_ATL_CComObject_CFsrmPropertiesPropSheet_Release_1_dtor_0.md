# _ATL::CComObject_CFsrmPropertiesPropSheet_::Release_::_1_::dtor$0

- ea: `0x18001dc92`
- end: `0x18001dc9e`
- name: `_ATL::CComObject_CFsrmPropertiesPropSheet_::Release_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005204`

## pseudocode

```c
void __fastcall ATL::CComObject_CFsrmPropertiesPropSheet_::Release_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::ModuleLockHelper::~ModuleLockHelper((ATL::ModuleLockHelper *)(a2 + 32));
}

```

## disassembly

```asm
0x18001dc92  lea     rcx, [rdx+20h]; this
0x18001dc99  jmp     ??1ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::~ModuleLockHelper(void)
```
