# NtGdiFlattenPath

- ea: `0x180006960`
- end: `0x180006978`
- name: `NtGdiFlattenPath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006960`

## pseudocode

```c
__int64 NtGdiFlattenPath()
{
  __int64 result; // rax

  result = 4790;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006960  mov     r10, rcx
0x180006963  mov     eax, 12B6h
0x180006968  test    byte ptr ds:7FFE0308h, 1
0x180006970  jnz     short loc_180006975
0x180006972  syscall; Low latency system call
0x180006974  retn
0x180006975  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006977  retn
```
