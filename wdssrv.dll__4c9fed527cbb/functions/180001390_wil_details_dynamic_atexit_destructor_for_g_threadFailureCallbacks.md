# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180001390`
- end: `0x18000139c`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001a28`

## pseudocode

```c
int wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  return atexit((void (__cdecl *)())wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks___0);
}

```

## disassembly

```asm
0x180001390  lea     rcx, wil__details___dynamic_atexit_destructor_for__g_threadFailureCallbacks___0
0x180001397  jmp     atexit
```
