# NtUserWaitForRedirectionStartComplete

- ea: `0x18000cc40`
- end: `0x18000cc58`
- name: `NtUserWaitForRedirectionStartComplete`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cc40`

## pseudocode

```c
__int64 NtUserWaitForRedirectionStartComplete()
{
  __int64 result; // rax

  result = 5581;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000cc40  mov     r10, rcx
0x18000cc43  mov     eax, 15CDh
0x18000cc48  test    byte ptr ds:7FFE0308h, 1
0x18000cc50  jnz     short loc_18000CC55
0x18000cc52  syscall; Low latency system call
0x18000cc54  retn
0x18000cc55  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000cc57  retn
```
