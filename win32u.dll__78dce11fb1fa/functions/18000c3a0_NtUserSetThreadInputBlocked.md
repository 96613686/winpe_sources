# NtUserSetThreadInputBlocked

- ea: `0x18000c3a0`
- end: `0x18000c3b8`
- name: `NtUserSetThreadInputBlocked`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c3a0`

## pseudocode

```c
__int64 NtUserSetThreadInputBlocked()
{
  __int64 result; // rax

  result = 5512;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000c3a0  mov     r10, rcx
0x18000c3a3  mov     eax, 1588h
0x18000c3a8  test    byte ptr ds:7FFE0308h, 1
0x18000c3b0  jnz     short loc_18000C3B5
0x18000c3b2  syscall; Low latency system call
0x18000c3b4  retn
0x18000c3b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000c3b7  retn
```
