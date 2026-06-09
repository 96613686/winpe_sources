# ZwDCompositionCreateSharedResourceHandle

- ea: `0x180003680`
- end: `0x180003698`
- name: `ZwDCompositionCreateSharedResourceHandle`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003680`

## pseudocode

```c
__int64 ZwDCompositionCreateSharedResourceHandle()
{
  __int64 result; // rax

  result = 4383;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003680  mov     r10, rcx
0x180003683  mov     eax, 111Fh
0x180003688  test    byte ptr ds:7FFE0308h, 1
0x180003690  jnz     short loc_180003695
0x180003692  syscall; Low latency system call
0x180003694  retn
0x180003695  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003697  retn
```
