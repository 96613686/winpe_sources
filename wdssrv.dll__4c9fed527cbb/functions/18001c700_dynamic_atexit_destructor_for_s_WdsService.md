# _dynamic_atexit_destructor_for__s_WdsService__

- ea: `0x18001c700`
- end: `0x18001c70c`
- name: `_dynamic_atexit_destructor_for__s_WdsService__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007148`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_WdsService__()
{
  CWdsService::~CWdsService((CWdsService *)&qword_180028BD0);
}

```

## disassembly

```asm
0x18001c700  lea     rcx, qword_180028BD0; this
0x18001c707  jmp     ??1CWdsService@@QEAA@XZ; CWdsService::~CWdsService(void)
```
