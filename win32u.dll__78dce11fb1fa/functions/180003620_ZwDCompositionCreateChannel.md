# ZwDCompositionCreateChannel

- ea: `0x180003620`
- end: `0x180003638`
- name: `ZwDCompositionCreateChannel`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003620`

## pseudocode

```c
__int64 ZwDCompositionCreateChannel()
{
  __int64 result; // rax

  result = 4380;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003620  mov     r10, rcx
0x180003623  mov     eax, 111Ch
0x180003628  test    byte ptr ds:7FFE0308h, 1
0x180003630  jnz     short loc_180003635
0x180003632  syscall; Low latency system call
0x180003634  retn
0x180003635  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003637  retn
```
