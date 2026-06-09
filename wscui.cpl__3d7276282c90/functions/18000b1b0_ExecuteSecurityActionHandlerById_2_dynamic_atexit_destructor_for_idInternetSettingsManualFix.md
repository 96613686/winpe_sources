# _ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idInternetSettingsManualFix__

- ea: `0x18000b1b0`
- end: `0x18000b1c0`
- name: `_ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idInternetSettingsManualFix__`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001b90`

## pseudocode

```c
void __fastcall ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idInternetSettingsManualFix__()
{
  ATL::CStringData::Release((ATL::CStringData *)(qword_180014C00 - 12));
}

```

## disassembly

```asm
0x18000b1b0  mov     rcx, cs:qword_180014C00
0x18000b1b7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b1bb  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
