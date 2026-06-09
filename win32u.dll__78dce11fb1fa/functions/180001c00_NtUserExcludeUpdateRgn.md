# NtUserExcludeUpdateRgn

- ea: `0x180001c00`
- end: `0x180001c18`
- name: `NtUserExcludeUpdateRgn`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001c00`

## pseudocode

```c
__int64 NtUserExcludeUpdateRgn()
{
  __int64 result; // rax

  result = 4171;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180001c00  mov     r10, rcx
0x180001c03  mov     eax, 104Bh
0x180001c08  test    byte ptr ds:7FFE0308h, 1
0x180001c10  jnz     short loc_180001C15
0x180001c12  syscall; Low latency system call
0x180001c14  retn
0x180001c15  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180001c17  retn
```
