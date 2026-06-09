# _ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAsListAndSelfMonitor__

- ea: `0x18000b250`
- end: `0x18000b260`
- name: `_ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAsListAndSelfMonitor__`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b90`

## pseudocode

```c
void __fastcall ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAsListAndSelfMonitor__()
{
  ATL::CStringData::Release((ATL::CStringData *)(qword_180014C50 - 12));
}

```

## disassembly

```asm
0x18000b250  mov     rcx, cs:qword_180014C50
0x18000b257  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b25b  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
