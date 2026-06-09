# _DllMain_::_2_::_dynamic_atexit_destructor_for__cleanupLogging__

- ea: `0x18000c710`
- end: `0x18000c71c`
- name: `_DllMain_::_2_::_dynamic_atexit_destructor_for__cleanupLogging__`
- size: `12`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800060b8`

## pseudocode

```c
void __fastcall DllMain_::_2_::_dynamic_atexit_destructor_for__cleanupLogging__()
{
  std::_Optional_destruct_base<wil::details::lambda_call_log<void (*)(void)>,0>::~_Optional_destruct_base<wil::details::lambda_call_log<void (*)(void)>,0>(&qword_180013580);
}

```

## disassembly

```asm
0x18000c710  lea     rcx, qword_180013580
0x18000c717  jmp     ??1?$_Optional_destruct_base@V?$lambda_call_log@P6AXXZ@details@wil@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<wil::details::lambda_call_log<void (*)(void)>,0>::~_Optional_destruct_base<wil::details::lambda_call_log<void (*)(void)>,0>(void)
```
