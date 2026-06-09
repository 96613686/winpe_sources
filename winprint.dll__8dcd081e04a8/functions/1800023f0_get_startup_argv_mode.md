# _get_startup_argv_mode

- ea: `0x1800023f0`
- end: `0x1800023f6`
- name: `_get_startup_argv_mode`
- size: `6`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004af4`
- `0x180004dec`

## pseudocode

```c
BOOL __stdcall get_startup_argv_mode(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  return 1;
}

```

## disassembly

```asm
0x1800023f0  mov     eax, 1
0x1800023f5  retn
```
