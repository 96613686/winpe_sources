# _ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAvPurchaseAndSelfMonitor__

- ea: `0x18000b270`
- end: `0x18000b280`
- name: `_ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAvPurchaseAndSelfMonitor__`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b90`

## pseudocode

```c
void __fastcall ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idcldAvPurchaseAndSelfMonitor__()
{
  ATL::CStringData::Release((ATL::CStringData *)(qword_180014C60 - 24));
}

```

## disassembly

```asm
0x18000b270  mov     rcx, cs:qword_180014C60
0x18000b277  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b27b  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
