# NtGdiCombineTransform

- ea: `0x180002e40`
- end: `0x180002e58`
- name: `NtGdiCombineTransform`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e40`

## pseudocode

```c
__int64 NtGdiCombineTransform()
{
  __int64 result; // rax

  result = 4317;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002e40  mov     r10, rcx
0x180002e43  mov     eax, 10DDh
0x180002e48  test    byte ptr ds:7FFE0308h, 1
0x180002e50  jnz     short loc_180002E55
0x180002e52  syscall; Low latency system call
0x180002e54  retn
0x180002e55  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002e57  retn
```
