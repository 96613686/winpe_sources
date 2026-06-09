# _ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor$0

- ea: `0x18001e8ae`
- end: `0x18001e8ba`
- name: `_ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011f4c`

## pseudocode

```c
void __fastcall ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComClassFactory::~CComClassFactory(*(ATL::CComClassFactory **)(a2 + 48));
}

```

## disassembly

```asm
0x18001e8ae  mov     rcx, [rdx+30h]; this
0x18001e8b5  jmp     ??1CComClassFactory@ATL@@QEAA@XZ; ATL::CComClassFactory::~CComClassFactory(void)
```
