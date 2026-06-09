# ZwDCompositionSendDwmLpcMessage

- ea: `0x1800039c0`
- end: `0x1800039d8`
- name: `ZwDCompositionSendDwmLpcMessage`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800039c0`

## pseudocode

```c
__int64 ZwDCompositionSendDwmLpcMessage()
{
  __int64 result; // rax

  result = 4409;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800039c0  mov     r10, rcx
0x1800039c3  mov     eax, 1139h
0x1800039c8  test    byte ptr ds:7FFE0308h, 1
0x1800039d0  jnz     short loc_1800039D5
0x1800039d2  syscall; Low latency system call
0x1800039d4  retn
0x1800039d5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800039d7  retn
```
