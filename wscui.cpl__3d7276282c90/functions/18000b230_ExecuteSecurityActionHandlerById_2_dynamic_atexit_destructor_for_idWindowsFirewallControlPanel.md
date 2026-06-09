# _ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idWindowsFirewallControlPanel__

- ea: `0x18000b230`
- end: `0x18000b240`
- name: `_ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idWindowsFirewallControlPanel__`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b90`

## pseudocode

```c
void __fastcall ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idWindowsFirewallControlPanel__()
{
  ATL::CStringData::Release((ATL::CStringData *)(qword_180014C10 - 12));
}

```

## disassembly

```asm
0x18000b230  mov     rcx, cs:qword_180014C10
0x18000b237  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b23b  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
