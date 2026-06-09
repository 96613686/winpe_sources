# _ATL::CComClassFactory::_CComClassFactory_::_1_::dtor$2

- ea: `0x18001c0fd`
- end: `0x18001c109`
- name: `_ATL::CComClassFactory::_CComClassFactory_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005024`

## pseudocode

```c
void __fastcall ATL::CComClassFactory::_CComClassFactory_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(*(ATL::CComSafeDeleteCriticalSection **)(a2 + 64));
}

```

## disassembly

```asm
0x18001c0fd  mov     rcx, [rdx+40h]; this
0x18001c104  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
