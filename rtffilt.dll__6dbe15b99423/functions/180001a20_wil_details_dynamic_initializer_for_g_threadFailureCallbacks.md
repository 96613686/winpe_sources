# wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__

- ea: `0x180001a20`
- end: `0x180001a2c`
- name: `wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002284`

## pseudocode

```c
int wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__()
{
  return atexit((void (__cdecl *)())wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__);
}

```

## disassembly

```asm
0x180001a20  lea     rcx, wil__details___dynamic_atexit_destructor_for__g_threadFailureCallbacks__
0x180001a27  jmp     atexit
```
