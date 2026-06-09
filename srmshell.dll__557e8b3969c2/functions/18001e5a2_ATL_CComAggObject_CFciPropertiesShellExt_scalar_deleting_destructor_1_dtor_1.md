# _ATL::CComAggObject_CFciPropertiesShellExt_::_scalar_deleting_destructor__::_1_::dtor$1

- ea: `0x18001e5a2`
- end: `0x18001e5ae`
- name: `_ATL::CComAggObject_CFciPropertiesShellExt_::_scalar_deleting_destructor__::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000505c`

## pseudocode

```c
void __fastcall ATL::CComAggObject_CFciPropertiesShellExt_::_scalar_deleting_destructor__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  CFciPropertiesShellExt::~CFciPropertiesShellExt(*(CFciPropertiesShellExt **)(a2 + 64));
}

```

## disassembly

```asm
0x18001e5a2  mov     rcx, [rdx+40h]; this
0x18001e5a9  jmp     ??1CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::~CFciPropertiesShellExt(void)
```
