# _ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idPurchaseAntivirus__

- ea: `0x18000b290`
- end: `0x18000b2a0`
- name: `_ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idPurchaseAntivirus__`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b90`

## pseudocode

```c
void __fastcall ExecuteSecurityActionHandlerById_::_2_::_dynamic_atexit_destructor_for__idPurchaseAntivirus__()
{
  ATL::CStringData::Release((ATL::CStringData *)(String1 - 12));
}

```

## disassembly

```asm
0x18000b290  mov     rcx, cs:String1
0x18000b297  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b29b  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
