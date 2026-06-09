# _ATL::CComObject_CFciPropertiesShellExt_::CreateInstance_::_1_::dtor$1

- ea: `0x18001c806`
- end: `0x18001c812`
- name: `_ATL::CComObject_CFciPropertiesShellExt_::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000505c`

## pseudocode

```c
void __fastcall ATL::CComObject_CFciPropertiesShellExt_::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CFciPropertiesShellExt::~CFciPropertiesShellExt(*(CFciPropertiesShellExt **)(a2 + 96));
}

```

## disassembly

```asm
0x18001c806  mov     rcx, [rdx+60h]; this
0x18001c80d  jmp     ??1CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::~CFciPropertiesShellExt(void)
```
