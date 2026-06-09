# _dynamic_initializer_for__CPlManager::m_listAppletsInSecurityCenter__

- ea: `0x180001240`
- end: `0x18000124c`
- name: `_dynamic_initializer_for__CPlManager::m_listAppletsInSecurityCenter__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800023f4`

## pseudocode

```c
int dynamic_initializer_for__CPlManager::m_listAppletsInSecurityCenter__()
{
  return atexit(dynamic_atexit_destructor_for__CPlManager::m_listAppletsInSecurityCenter__);
}

```

## disassembly

```asm
0x180001240  lea     rcx, _dynamic_atexit_destructor_for__CPlManager__m_listAppletsInSecurityCenter__
0x180001247  jmp     atexit
```
