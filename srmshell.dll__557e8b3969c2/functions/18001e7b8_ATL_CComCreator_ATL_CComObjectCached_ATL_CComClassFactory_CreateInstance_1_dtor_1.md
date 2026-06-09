# _ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$1

- ea: `0x18001e7b8`
- end: `0x18001e7c4`
- name: `_ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011f4c`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  ATL::CComClassFactory::~CComClassFactory(*(ATL::CComClassFactory **)(a2 + 40));
}

```

## disassembly

```asm
0x18001e7b8  mov     rcx, [rdx+28h]; this
0x18001e7bf  jmp     ??1CComClassFactory@ATL@@QEAA@XZ; ATL::CComClassFactory::~CComClassFactory(void)
```
