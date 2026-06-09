# NtUserRemoteStopScreenUpdates

- ea: `0x18000b820`
- end: `0x18000b838`
- name: `NtUserRemoteStopScreenUpdates`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000b820`

## pseudocode

```c
__int64 NtUserRemoteStopScreenUpdates()
{
  __int64 result; // rax

  result = 5420;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000b820  mov     r10, rcx
0x18000b823  mov     eax, 152Ch
0x18000b828  test    byte ptr ds:7FFE0308h, 1
0x18000b830  jnz     short loc_18000B835
0x18000b832  syscall; Low latency system call
0x18000b834  retn
0x18000b835  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000b837  retn
```
