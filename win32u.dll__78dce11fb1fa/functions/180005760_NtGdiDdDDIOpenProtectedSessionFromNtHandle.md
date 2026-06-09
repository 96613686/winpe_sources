# NtGdiDdDDIOpenProtectedSessionFromNtHandle

- ea: `0x180005760`
- end: `0x180005778`
- name: `NtGdiDdDDIOpenProtectedSessionFromNtHandle`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005760`

## pseudocode

```c
__int64 NtGdiDdDDIOpenProtectedSessionFromNtHandle()
{
  __int64 result; // rax

  result = 4646;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180005760  mov     r10, rcx
0x180005763  mov     eax, 1226h
0x180005768  test    byte ptr ds:7FFE0308h, 1
0x180005770  jnz     short loc_180005775
0x180005772  syscall; Low latency system call
0x180005774  retn
0x180005775  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180005777  retn
```
