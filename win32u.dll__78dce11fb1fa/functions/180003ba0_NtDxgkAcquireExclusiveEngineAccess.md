# NtDxgkAcquireExclusiveEngineAccess

- ea: `0x180003ba0`
- end: `0x180003bb8`
- name: `NtDxgkAcquireExclusiveEngineAccess`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003ba0`

## pseudocode

```c
__int64 NtDxgkAcquireExclusiveEngineAccess()
{
  __int64 result; // rax

  result = 4424;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003ba0  mov     r10, rcx
0x180003ba3  mov     eax, 1148h
0x180003ba8  test    byte ptr ds:7FFE0308h, 1
0x180003bb0  jnz     short loc_180003BB5
0x180003bb2  syscall; Low latency system call
0x180003bb4  retn
0x180003bb5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003bb7  retn
```
