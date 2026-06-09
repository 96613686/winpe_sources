# ZwDCompositionBeginFrame

- ea: `0x180003520`
- end: `0x180003538`
- name: `ZwDCompositionBeginFrame`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003520`

## pseudocode

```c
__int64 ZwDCompositionBeginFrame()
{
  __int64 result; // rax

  result = 4372;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003520  mov     r10, rcx
0x180003523  mov     eax, 1114h
0x180003528  test    byte ptr ds:7FFE0308h, 1
0x180003530  jnz     short loc_180003535
0x180003532  syscall; Low latency system call
0x180003534  retn
0x180003535  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003537  retn
```
