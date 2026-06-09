# _ATL::CComCreator_ATL::CComAggObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor$2

- ea: `0x18001c292`
- end: `0x18001c29e`
- name: `_ATL::CComCreator_ATL::CComAggObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000505c`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  CFciPropertiesShellExt::~CFciPropertiesShellExt(*(CFciPropertiesShellExt **)(a2 + 48));
}

```

## disassembly

```asm
0x18001c292  mov     rcx, [rdx+30h]; this
0x18001c299  jmp     ??1CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::~CFciPropertiesShellExt(void)
```
