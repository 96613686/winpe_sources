# ZwDCompositionSyncWait

- ea: `0x180003aa0`
- end: `0x180003ab8`
- name: `ZwDCompositionSyncWait`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003aa0`

## pseudocode

```c
__int64 ZwDCompositionSyncWait()
{
  __int64 result; // rax

  result = 4416;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003aa0  mov     r10, rcx
0x180003aa3  mov     eax, 1140h
0x180003aa8  test    byte ptr ds:7FFE0308h, 1
0x180003ab0  jnz     short loc_180003AB5
0x180003ab2  syscall; Low latency system call
0x180003ab4  retn
0x180003ab5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003ab7  retn
```
