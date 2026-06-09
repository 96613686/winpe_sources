# InterlockedAutoRef<ITaskHandler>::~InterlockedAutoRef<ITaskHandler>(void)

- ea: `0x140006c80`
- end: `0x140006c8f`
- name: `??1?$InterlockedAutoRef@UITaskHandler@@@@QEAA@XZ`
- size: `15`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x14000ae80`

## callees

- `0x140006ca0`

## pseudocode

```c
__int64 InterlockedAutoRef<ITaskHandler>::~InterlockedAutoRef<ITaskHandler>()
{
  return InterlockedAutoRef<ITaskHandler>::operator=();
}

```

## disassembly

```asm
0x140006c80  sub     rsp, 28h
0x140006c84  call    ??4?$InterlockedAutoRef@UITaskHandler@@@@QEAAAEAV0@PEAUITaskHandler@@@Z; InterlockedAutoRef<ITaskHandler>::operator=(ITaskHandler *)
0x140006c89  nop
0x140006c8a  add     rsp, 28h
0x140006c8e  retn
```
