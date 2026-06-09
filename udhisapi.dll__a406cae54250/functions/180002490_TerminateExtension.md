# TerminateExtension

- ea: `0x180002490`
- end: `0x180002496`
- name: `TerminateExtension`
- size: `6`
- prototype: `BOOL __stdcall(DWORD dwFlags)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001598`

## pseudocode

```c
BOOL __stdcall TerminateExtension(DWORD dwFlags)
{
  return 1;
}

```

## disassembly

```asm
0x180002490  mov     eax, 1
0x180002495  retn
```
