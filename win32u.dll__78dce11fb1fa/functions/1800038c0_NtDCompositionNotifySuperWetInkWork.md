# NtDCompositionNotifySuperWetInkWork

- ea: `0x1800038c0`
- end: `0x1800038d8`
- name: `NtDCompositionNotifySuperWetInkWork`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800038c0`

## pseudocode

```c
__int64 NtDCompositionNotifySuperWetInkWork()
{
  __int64 result; // rax

  result = 4401;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800038c0  mov     r10, rcx
0x1800038c3  mov     eax, 1131h
0x1800038c8  test    byte ptr ds:7FFE0308h, 1
0x1800038d0  jnz     short loc_1800038D5
0x1800038d2  syscall; Low latency system call
0x1800038d4  retn
0x1800038d5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800038d7  retn
```
