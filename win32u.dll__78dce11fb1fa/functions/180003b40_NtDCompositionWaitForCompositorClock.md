# NtDCompositionWaitForCompositorClock

- ea: `0x180003b40`
- end: `0x180003b58`
- name: `NtDCompositionWaitForCompositorClock`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003b40`

## pseudocode

```c
__int64 NtDCompositionWaitForCompositorClock()
{
  __int64 result; // rax

  result = 4421;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003b40  mov     r10, rcx
0x180003b43  mov     eax, 1145h
0x180003b48  test    byte ptr ds:7FFE0308h, 1
0x180003b50  jnz     short loc_180003B55
0x180003b52  syscall; Low latency system call
0x180003b54  retn
0x180003b55  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003b57  retn
```
