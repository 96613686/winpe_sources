# _ComTaskHost::ComTaskHost_::_1_::dtor$2

- ea: `0x14000ae80`
- end: `0x14000ae90`
- name: `_ComTaskHost::ComTaskHost_::_1_::dtor$2`
- size: `16`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140006c80`

## pseudocode

```c
__int64 ComTaskHost::ComTaskHost_::_1_::dtor_2()
{
  return InterlockedAutoRef<ITaskHandler>::~InterlockedAutoRef<ITaskHandler>();
}

```

## disassembly

```asm
0x14000ae80  mov     rcx, [rdx+60h]
0x14000ae87  add     rcx, 48h ; 'H'
0x14000ae8b  jmp     ??1?$InterlockedAutoRef@UITaskHandler@@@@QEAA@XZ; InterlockedAutoRef<ITaskHandler>::~InterlockedAutoRef<ITaskHandler>(void)
```
