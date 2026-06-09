# NtDxgkCreateTrackedWorkload

- ea: `0x180003cc0`
- end: `0x180003cd8`
- name: `NtDxgkCreateTrackedWorkload`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003cc0`

## pseudocode

```c
__int64 NtDxgkCreateTrackedWorkload()
{
  __int64 result; // rax

  result = 4433;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003cc0  mov     r10, rcx
0x180003cc3  mov     eax, 1151h
0x180003cc8  test    byte ptr ds:7FFE0308h, 1
0x180003cd0  jnz     short loc_180003CD5
0x180003cd2  syscall; Low latency system call
0x180003cd4  retn
0x180003cd5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003cd7  retn
```
