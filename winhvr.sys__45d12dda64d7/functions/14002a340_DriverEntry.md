# DriverEntry

- ea: `0x14002a340`
- end: `0x14002a350`
- name: `DriverEntry`
- size: `16`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14002a010`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  __debugbreak();
  return WinHvpHypervisorDriverInitialization(DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x14002a340  int     3; Trap to Debugger
0x14002a341  int     3; Trap to Debugger
0x14002a342  int     3; Trap to Debugger
0x14002a343  int     3; Trap to Debugger
0x14002a344  int     3; Trap to Debugger
0x14002a345  int     3; Trap to Debugger
0x14002a346  int     3; Trap to Debugger
0x14002a347  int     3; Trap to Debugger
0x14002a348  int     3; Trap to Debugger
0x14002a349  int     3; Trap to Debugger
0x14002a34a  int     3; Trap to Debugger
0x14002a34b  int     3; Trap to Debugger
0x14002a34c  int     3; Trap to Debugger
0x14002a34d  int     3; Trap to Debugger
0x14002a34e  int     3; Trap to Debugger
0x14002a34f  int     3; Trap to Debugger
```
