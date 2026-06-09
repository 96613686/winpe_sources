# _ATL::CComCreator_ATL::CComObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor$1

- ea: `0x18001e7a6`
- end: `0x18001e7b2`
- name: `_ATL::CComCreator_ATL::CComObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000505c`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  CFciPropertiesShellExt::~CFciPropertiesShellExt(*(CFciPropertiesShellExt **)(a2 + 120));
}

```

## disassembly

```asm
0x18001e7a6  mov     rcx, [rdx+78h]; this
0x18001e7ad  jmp     ??1CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::~CFciPropertiesShellExt(void)
```
