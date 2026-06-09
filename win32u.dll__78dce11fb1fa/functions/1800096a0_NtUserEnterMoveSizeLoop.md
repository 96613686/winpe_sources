# NtUserEnterMoveSizeLoop

- ea: `0x1800096a0`
- end: `0x1800096b8`
- name: `NtUserEnterMoveSizeLoop`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800096a0`

## pseudocode

```c
__int64 NtUserEnterMoveSizeLoop()
{
  __int64 result; // rax

  result = 5152;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800096a0  mov     r10, rcx
0x1800096a3  mov     eax, 1420h
0x1800096a8  test    byte ptr ds:7FFE0308h, 1
0x1800096b0  jnz     short loc_1800096B5
0x1800096b2  syscall; Low latency system call
0x1800096b4  retn
0x1800096b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800096b7  retn
```
