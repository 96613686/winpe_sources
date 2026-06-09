# __uncaught_exception(void)

- ea: `0x180001e58`
- end: `0x180001e64`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `bool(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016bc`
- `0x1800016fc`
- `0x180001794`
- `0x1800017e4`
- `0x180001878`
- `0x1800019ac`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_180042130 != 0;
}

```

## disassembly

```asm
0x180001e58  xor     eax, eax
0x180001e5a  cmp     cs:dword_180042130, eax
0x180001e60  setnz   al
0x180001e63  retn
```
