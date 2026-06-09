# NtUserOpenWindowStation

- ea: `0x180002580`
- end: `0x180002598`
- name: `NtUserOpenWindowStation`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002580`

## pseudocode

```c
__int64 NtUserOpenWindowStation()
{
  __int64 result; // rax

  result = 4247;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002580  mov     r10, rcx
0x180002583  mov     eax, 1097h
0x180002588  test    byte ptr ds:7FFE0308h, 1
0x180002590  jnz     short loc_180002595
0x180002592  syscall; Low latency system call
0x180002594  retn
0x180002595  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002597  retn
```
