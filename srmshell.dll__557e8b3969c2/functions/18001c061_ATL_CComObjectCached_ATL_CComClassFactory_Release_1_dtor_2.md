# _ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor$2

- ea: `0x18001c061`
- end: `0x18001c071`
- name: `_ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ffc`

## pseudocode

```c
void __fastcall ATL::CComObjectCached_ATL::CComClassFactory_::Release_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(*(_QWORD *)(a2 + 48) + 8LL));
}

```

## disassembly

```asm
0x18001c061  mov     rcx, [rdx+30h]
0x18001c068  add     rcx, 8; this
0x18001c06c  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
