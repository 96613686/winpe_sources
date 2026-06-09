# RegUtil::_dynamic_initializer_for__g_PathCleanup__

- ea: `0x180001a80`
- end: `0x180001a8c`
- name: `RegUtil::_dynamic_initializer_for__g_PathCleanup__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010064`

## pseudocode

```c
int RegUtil::_dynamic_initializer_for__g_PathCleanup__()
{
  return atexit(RegUtil::_dynamic_atexit_destructor_for__g_PathCleanup__);
}

```

## disassembly

```asm
0x180001a80  lea     rcx, RegUtil___dynamic_atexit_destructor_for__g_PathCleanup__
0x180001a87  jmp     atexit
```
