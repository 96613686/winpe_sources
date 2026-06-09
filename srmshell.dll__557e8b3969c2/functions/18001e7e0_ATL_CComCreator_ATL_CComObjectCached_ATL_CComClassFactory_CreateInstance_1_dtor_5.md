# _ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$5

- ea: `0x18001e7e0`
- end: `0x18001e7ec`
- name: `_ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011f4c`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor_5(
        __int64 a1,
        __int64 a2)
{
  ATL::CComClassFactory::~CComClassFactory(*(ATL::CComClassFactory **)(a2 + 144));
}

```

## disassembly

```asm
0x18001e7e0  mov     rcx, [rdx+90h]; this
0x18001e7e7  jmp     ??1CComClassFactory@ATL@@QEAA@XZ; ATL::CComClassFactory::~CComClassFactory(void)
```
