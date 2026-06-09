# DllMain

- ea: `0x180001ef8`
- end: `0x180001efe`
- name: `DllMain`
- size: `6`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001ae4`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  return 1;
}

```

## disassembly

```asm
0x180001ef8  mov     eax, 1
0x180001efd  retn
```
