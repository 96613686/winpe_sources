# ZwDCompositionAddCrossDeviceVisualChild

- ea: `0x180003500`
- end: `0x180003518`
- name: `ZwDCompositionAddCrossDeviceVisualChild`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003500`

## pseudocode

```c
__int64 ZwDCompositionAddCrossDeviceVisualChild()
{
  __int64 result; // rax

  result = 4371;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003500  mov     r10, rcx
0x180003503  mov     eax, 1113h
0x180003508  test    byte ptr ds:7FFE0308h, 1
0x180003510  jnz     short loc_180003515
0x180003512  syscall; Low latency system call
0x180003514  retn
0x180003515  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003517  retn
```
