# GetLogSessionId(void)

- ea: `0x140002604`
- end: `0x14000260c`
- name: `?GetLogSessionId@@YAPEBU_UNICODE_STRING@@XZ`
- size: `8`
- prototype: `const struct _UNICODE_STRING *(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14001e808`
- `0x14001f130`
- `0x14001f288`

## pseudocode

```c
const struct _UNICODE_STRING *GetLogSessionId(void)
{
  return &stru_1400195F8;
}

```

## disassembly

```asm
0x140002604  lea     rax, stru_1400195F8
0x14000260b  retn
```
