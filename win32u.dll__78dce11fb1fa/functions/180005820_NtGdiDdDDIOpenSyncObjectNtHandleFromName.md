# NtGdiDdDDIOpenSyncObjectNtHandleFromName

- ea: `0x180005820`
- end: `0x180005838`
- name: `NtGdiDdDDIOpenSyncObjectNtHandleFromName`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005820`

## pseudocode

```c
__int64 NtGdiDdDDIOpenSyncObjectNtHandleFromName()
{
  __int64 result; // rax

  result = 4652;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180005820  mov     r10, rcx
0x180005823  mov     eax, 122Ch
0x180005828  test    byte ptr ds:7FFE0308h, 1
0x180005830  jnz     short loc_180005835
0x180005832  syscall; Low latency system call
0x180005834  retn
0x180005835  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180005837  retn
```
