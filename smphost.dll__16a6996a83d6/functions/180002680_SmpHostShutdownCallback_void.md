# SmpHostShutdownCallback(void)

- ea: `0x180002680`
- end: `0x18000268a`
- name: `?SmpHostShutdownCallback@@YAXXZ`
- size: `10`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002000`

## pseudocode

```c
void __fastcall SmpHostShutdownCallback(__int64 a1, __int64 a2)
{
  ServiceCtrlHandler(1u, a2);
}

```

## disassembly

```asm
0x180002680  mov     ecx, 1; dwControl
0x180002685  jmp     ?ServiceCtrlHandler@@YAXK@Z; ServiceCtrlHandler(ulong)
```
