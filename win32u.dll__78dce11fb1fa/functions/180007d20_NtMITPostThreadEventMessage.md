# NtMITPostThreadEventMessage

- ea: `0x180007d20`
- end: `0x180007d38`
- name: `NtMITPostThreadEventMessage`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007d20`

## pseudocode

```c
__int64 NtMITPostThreadEventMessage()
{
  __int64 result; // rax

  result = 4948;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007d20  mov     r10, rcx
0x180007d23  mov     eax, 1354h
0x180007d28  test    byte ptr ds:7FFE0308h, 1
0x180007d30  jnz     short loc_180007D35
0x180007d32  syscall; Low latency system call
0x180007d34  retn
0x180007d35  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007d37  retn
```
