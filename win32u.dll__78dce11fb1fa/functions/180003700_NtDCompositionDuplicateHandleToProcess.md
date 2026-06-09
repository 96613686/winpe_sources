# NtDCompositionDuplicateHandleToProcess

- ea: `0x180003700`
- end: `0x180003718`
- name: `NtDCompositionDuplicateHandleToProcess`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003700`

## pseudocode

```c
__int64 NtDCompositionDuplicateHandleToProcess()
{
  __int64 result; // rax

  result = 4387;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003700  mov     r10, rcx
0x180003703  mov     eax, 1123h
0x180003708  test    byte ptr ds:7FFE0308h, 1
0x180003710  jnz     short loc_180003715
0x180003712  syscall; Low latency system call
0x180003714  retn
0x180003715  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003717  retn
```
