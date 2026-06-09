# NtDxgkUpdateTrackedWorkload

- ea: `0x180004120`
- end: `0x180004138`
- name: `NtDxgkUpdateTrackedWorkload`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004120`

## pseudocode

```c
__int64 NtDxgkUpdateTrackedWorkload()
{
  __int64 result; // rax

  result = 4468;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004120  mov     r10, rcx
0x180004123  mov     eax, 1174h
0x180004128  test    byte ptr ds:7FFE0308h, 1
0x180004130  jnz     short loc_180004135
0x180004132  syscall; Low latency system call
0x180004134  retn
0x180004135  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004137  retn
```
