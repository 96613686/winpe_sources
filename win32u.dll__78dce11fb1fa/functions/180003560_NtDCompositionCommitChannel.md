# NtDCompositionCommitChannel

- ea: `0x180003560`
- end: `0x180003578`
- name: `NtDCompositionCommitChannel`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003560`

## pseudocode

```c
__int64 NtDCompositionCommitChannel()
{
  __int64 result; // rax

  result = 4374;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003560  mov     r10, rcx
0x180003563  mov     eax, 1116h
0x180003568  test    byte ptr ds:7FFE0308h, 1
0x180003570  jnz     short loc_180003575
0x180003572  syscall; Low latency system call
0x180003574  retn
0x180003575  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003577  retn
```
