# NtQueryCompositionSurfaceStatistics

- ea: `0x180008360`
- end: `0x180008378`
- name: `NtQueryCompositionSurfaceStatistics`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008360`

## pseudocode

```c
__int64 NtQueryCompositionSurfaceStatistics()
{
  __int64 result; // rax

  result = 4998;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008360  mov     r10, rcx
0x180008363  mov     eax, 1386h
0x180008368  test    byte ptr ds:7FFE0308h, 1
0x180008370  jnz     short loc_180008375
0x180008372  syscall; Low latency system call
0x180008374  retn
0x180008375  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008377  retn
```
