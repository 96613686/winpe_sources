# NtGdiRemoveFontMemResourceEx

- ea: `0x180003260`
- end: `0x180003278`
- name: `NtGdiRemoveFontMemResourceEx`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003260`

## pseudocode

```c
__int64 NtGdiRemoveFontMemResourceEx()
{
  __int64 result; // rax

  result = 4350;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003260  mov     r10, rcx
0x180003263  mov     eax, 10FEh
0x180003268  test    byte ptr ds:7FFE0308h, 1
0x180003270  jnz     short loc_180003275
0x180003272  syscall; Low latency system call
0x180003274  retn
0x180003275  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003277  retn
```
