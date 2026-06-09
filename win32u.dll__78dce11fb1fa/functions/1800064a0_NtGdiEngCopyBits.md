# NtGdiEngCopyBits

- ea: `0x1800064a0`
- end: `0x1800064b8`
- name: `NtGdiEngCopyBits`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800064a0`

## pseudocode

```c
__int64 NtGdiEngCopyBits()
{
  __int64 result; // rax

  result = 4752;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800064a0  mov     r10, rcx
0x1800064a3  mov     eax, 1290h
0x1800064a8  test    byte ptr ds:7FFE0308h, 1
0x1800064b0  jnz     short loc_1800064B5
0x1800064b2  syscall; Low latency system call
0x1800064b4  retn
0x1800064b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800064b7  retn
```
