# SecClientFree

- ea: `0x18001fc00`
- end: `0x18001fc05`
- name: `SecClientFree`
- size: `5`
- prototype: `SECURITY_STATUS __stdcall(PVOID pvContextBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d560`

## pseudocode

```c
// attributes: thunk
SECURITY_STATUS __stdcall SecClientFree(PVOID pvContextBuffer)
{
  return FreeContextBuffer(pvContextBuffer);
}

```

## disassembly

```asm
0x18001fc00  jmp     FreeContextBuffer
```
