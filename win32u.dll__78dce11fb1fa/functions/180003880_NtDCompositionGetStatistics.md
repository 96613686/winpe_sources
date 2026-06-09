# NtDCompositionGetStatistics

- ea: `0x180003880`
- end: `0x180003898`
- name: `NtDCompositionGetStatistics`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003880`

## pseudocode

```c
__int64 NtDCompositionGetStatistics()
{
  __int64 result; // rax

  result = 4399;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003880  mov     r10, rcx
0x180003883  mov     eax, 112Fh
0x180003888  test    byte ptr ds:7FFE0308h, 1
0x180003890  jnz     short loc_180003895
0x180003892  syscall; Low latency system call
0x180003894  retn
0x180003895  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003897  retn
```
