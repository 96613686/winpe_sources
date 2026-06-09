# ZwDCompositionUpdatePointerCapture

- ea: `0x180003b00`
- end: `0x180003b18`
- name: `ZwDCompositionUpdatePointerCapture`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003b00`

## pseudocode

```c
__int64 ZwDCompositionUpdatePointerCapture()
{
  __int64 result; // rax

  result = 4419;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003b00  mov     r10, rcx
0x180003b03  mov     eax, 1143h
0x180003b08  test    byte ptr ds:7FFE0308h, 1
0x180003b10  jnz     short loc_180003B15
0x180003b12  syscall; Low latency system call
0x180003b14  retn
0x180003b15  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003b17  retn
```
