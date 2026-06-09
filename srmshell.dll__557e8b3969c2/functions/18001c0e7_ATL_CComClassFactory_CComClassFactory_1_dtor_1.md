# _ATL::CComClassFactory::_CComClassFactory_::_1_::dtor$1

- ea: `0x18001c0e7`
- end: `0x18001c0f7`
- name: `_ATL::CComClassFactory::_CComClassFactory_::_1_::dtor$1`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ffc`

## pseudocode

```c
void __fastcall ATL::CComClassFactory::_CComClassFactory_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(*(_QWORD *)(a2 + 56) + 8LL));
}

```

## disassembly

```asm
0x18001c0e7  mov     rcx, [rdx+38h]
0x18001c0ee  add     rcx, 8; this
0x18001c0f2  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
