# NtDCompositionSuspendAnimations

- ea: `0x180003a80`
- end: `0x180003a98`
- name: `NtDCompositionSuspendAnimations`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003a80`

## pseudocode

```c
__int64 NtDCompositionSuspendAnimations()
{
  __int64 result; // rax

  result = 4415;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003a80  mov     r10, rcx
0x180003a83  mov     eax, 113Fh
0x180003a88  test    byte ptr ds:7FFE0308h, 1
0x180003a90  jnz     short loc_180003A95
0x180003a92  syscall; Low latency system call
0x180003a94  retn
0x180003a95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003a97  retn
```
