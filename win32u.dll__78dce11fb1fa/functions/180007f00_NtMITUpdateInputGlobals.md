# NtMITUpdateInputGlobals

- ea: `0x180007f00`
- end: `0x180007f18`
- name: `NtMITUpdateInputGlobals`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007f00`

## pseudocode

```c
__int64 NtMITUpdateInputGlobals()
{
  __int64 result; // rax

  result = 4963;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007f00  mov     r10, rcx
0x180007f03  mov     eax, 1363h
0x180007f08  test    byte ptr ds:7FFE0308h, 1
0x180007f10  jnz     short loc_180007F15
0x180007f12  syscall; Low latency system call
0x180007f14  retn
0x180007f15  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007f17  retn
```
