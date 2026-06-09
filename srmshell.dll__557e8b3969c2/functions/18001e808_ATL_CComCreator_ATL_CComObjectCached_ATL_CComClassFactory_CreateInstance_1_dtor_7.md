# _ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$7

- ea: `0x18001e808`
- end: `0x18001e818`
- name: `_ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor$7`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ffc`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObjectCached_ATL::CComClassFactory___::CreateInstance_::_1_::dtor_7(
        __int64 a1,
        __int64 a2)
{
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(*(_QWORD *)(a2 + 152) + 8LL));
}

```

## disassembly

```asm
0x18001e808  mov     rcx, [rdx+98h]
0x18001e80f  add     rcx, 8; this
0x18001e813  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
