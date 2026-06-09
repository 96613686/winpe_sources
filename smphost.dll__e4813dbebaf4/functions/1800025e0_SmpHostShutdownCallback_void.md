# SmpHostShutdownCallback(void)

- ea: `0x1800025e0`
- end: `0x1800025ea`
- name: `?SmpHostShutdownCallback@@YAXXZ`
- size: `10`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001fb0`

## pseudocode

```c
void __fastcall SmpHostShutdownCallback(__int64 a1, unsigned int a2)
{
  ServiceCtrlHandler(1u, a2);
}

```

## disassembly

```asm
0x1800025e0  mov     ecx, 1; dwControl
0x1800025e5  jmp     ?ServiceCtrlHandler@@YAXK@Z; ServiceCtrlHandler(ulong)
```
