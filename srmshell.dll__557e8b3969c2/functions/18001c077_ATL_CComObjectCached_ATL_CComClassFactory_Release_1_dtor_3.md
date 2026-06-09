# _ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor$3

- ea: `0x18001c077`
- end: `0x18001c083`
- name: `_ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005024`

## pseudocode

```c
void __fastcall ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(*(ATL::CComSafeDeleteCriticalSection **)(a2 + 56));
}

```

## disassembly

```asm
0x18001c077  mov     rcx, [rdx+38h]; this
0x18001c07e  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
