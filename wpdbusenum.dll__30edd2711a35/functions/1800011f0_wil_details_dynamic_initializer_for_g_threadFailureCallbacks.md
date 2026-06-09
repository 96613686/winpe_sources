# wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__

- ea: `0x1800011f0`
- end: `0x1800011fc`
- name: `wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009b80`

## pseudocode

```c
int wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__()
{
  return atexit(wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__);
}

```

## disassembly

```asm
0x1800011f0  lea     rcx, wil__details___dynamic_atexit_destructor_for__g_threadFailureCallbacks__
0x1800011f7  jmp     atexit
```
