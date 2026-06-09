# AutodialHookCallback

- ea: `0x1800019a0`
- end: `0x1800019a7`
- name: `AutodialHookCallback`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `WININET!InternetAutodialCallback` at `0x1800019a0`

## pseudocode

```c
// attributes: thunk
__int64 AutodialHookCallback()
{
  return InternetAutodialCallback();
}

```

## disassembly

```asm
0x1800019a0  jmp     cs:__imp_InternetAutodialCallback
```
