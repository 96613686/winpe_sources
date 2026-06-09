# WerUIpTaskDialogIndirect

- ea: `0x1800038b0`
- end: `0x1800038bf`
- name: `WerUIpTaskDialogIndirect`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## import_xrefs

- `COMCTL32!TaskDialogIndirect` at `0x1800038b8`

## pseudocode

```c
HRESULT __fastcall WerUIpTaskDialogIndirect(const TASKDIALOGCONFIG *a1)
{
  return TaskDialogIndirect(a1, 0, 0, 0);
}

```

## disassembly

```asm
0x1800038b0  xor     r9d, r9d
0x1800038b3  xor     r8d, r8d
0x1800038b6  xor     edx, edx
0x1800038b8  jmp     cs:__imp_TaskDialogIndirect
```
