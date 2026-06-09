# ZwDCompositionSynchronize

- ea: `0x180003ac0`
- end: `0x180003ad8`
- name: `ZwDCompositionSynchronize`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003ac0`

## pseudocode

```c
__int64 ZwDCompositionSynchronize()
{
  __int64 result; // rax

  result = 4417;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003ac0  mov     r10, rcx
0x180003ac3  mov     eax, 1141h
0x180003ac8  test    byte ptr ds:7FFE0308h, 1
0x180003ad0  jnz     short loc_180003AD5
0x180003ad2  syscall; Low latency system call
0x180003ad4  retn
0x180003ad5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003ad7  retn
```
