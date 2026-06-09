# ZwDCompositionRemoveCrossDeviceVisualChild

- ea: `0x1800039a0`
- end: `0x1800039b8`
- name: `ZwDCompositionRemoveCrossDeviceVisualChild`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800039a0`

## pseudocode

```c
__int64 ZwDCompositionRemoveCrossDeviceVisualChild()
{
  __int64 result; // rax

  result = 4408;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800039a0  mov     r10, rcx
0x1800039a3  mov     eax, 1138h
0x1800039a8  test    byte ptr ds:7FFE0308h, 1
0x1800039b0  jnz     short loc_1800039B5
0x1800039b2  syscall; Low latency system call
0x1800039b4  retn
0x1800039b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800039b7  retn
```
