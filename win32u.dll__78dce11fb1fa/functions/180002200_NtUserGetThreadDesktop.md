# NtUserGetThreadDesktop

- ea: `0x180002200`
- end: `0x180002218`
- name: `NtUserGetThreadDesktop`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002200`

## pseudocode

```c
__int64 NtUserGetThreadDesktop()
{
  __int64 result; // rax

  result = 4219;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002200  mov     r10, rcx
0x180002203  mov     eax, 107Bh
0x180002208  test    byte ptr ds:7FFE0308h, 1
0x180002210  jnz     short loc_180002215
0x180002212  syscall; Low latency system call
0x180002214  retn
0x180002215  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002217  retn
```
