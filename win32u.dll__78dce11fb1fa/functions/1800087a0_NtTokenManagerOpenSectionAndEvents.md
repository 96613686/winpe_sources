# NtTokenManagerOpenSectionAndEvents

- ea: `0x1800087a0`
- end: `0x1800087b8`
- name: `NtTokenManagerOpenSectionAndEvents`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800087a0`

## pseudocode

```c
__int64 NtTokenManagerOpenSectionAndEvents()
{
  __int64 result; // rax

  result = 5032;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800087a0  mov     r10, rcx
0x1800087a3  mov     eax, 13A8h
0x1800087a8  test    byte ptr ds:7FFE0308h, 1
0x1800087b0  jnz     short loc_1800087B5
0x1800087b2  syscall; Low latency system call
0x1800087b4  retn
0x1800087b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800087b7  retn
```
