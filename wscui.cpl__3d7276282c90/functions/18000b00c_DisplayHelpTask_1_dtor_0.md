# _DisplayHelpTask_::_1_::dtor$0

- ea: `0x18000b00c`
- end: `0x18000b018`
- name: `_DisplayHelpTask_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800035ac`

## pseudocode

```c
void __fastcall DisplayHelpTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 80));
}

```

## disassembly

```asm
0x18000b00c  lea     rcx, [rdx+50h]; this
0x18000b013  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
