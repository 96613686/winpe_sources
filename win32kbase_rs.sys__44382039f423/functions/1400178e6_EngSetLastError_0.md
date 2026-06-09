# EngSetLastError_0

- ea: `0x1400178e6`
- end: `0x1400178ed`
- name: `EngSetLastError_0`
- size: `7`
- prototype: `void __stdcall(ULONG iError)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140001500`
- `0x140002000`
- `0x140002150`
- `0x1400022a0`
- `0x1400023c0`
- `0x140002500`
- `0x140003210`
- `0x140004890`
- `0x140004ab0`

## import_xrefs

- `win32kbase!EngSetLastError` at `0x1400178e6`

## pseudocode

```c
// attributes: thunk
void __stdcall EngSetLastError_0(ULONG iError)
{
  EngSetLastError(iError);
}

```

## disassembly

```asm
0x1400178e6  jmp     cs:__imp_EngSetLastError
```
