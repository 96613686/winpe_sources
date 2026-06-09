# _ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idShowWindowsSecurityProviders__

- ea: `0x18000b210`
- end: `0x18000b220`
- name: `_ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idShowWindowsSecurityProviders__`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b90`

## pseudocode

```c
void __fastcall ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idShowWindowsSecurityProviders__()
{
  ATL::CStringData::Release((ATL::CStringData *)(qword_180014C40 - 12));
}

```

## disassembly

```asm
0x18000b210  mov     rcx, cs:qword_180014C40
0x18000b217  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b21b  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
