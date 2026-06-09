# NtDCompositionSetChannelConnectionId

- ea: `0x180003a20`
- end: `0x180003a38`
- name: `NtDCompositionSetChannelConnectionId`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003a20`

## pseudocode

```c
__int64 NtDCompositionSetChannelConnectionId()
{
  __int64 result; // rax

  result = 4412;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003a20  mov     r10, rcx
0x180003a23  mov     eax, 113Ch
0x180003a28  test    byte ptr ds:7FFE0308h, 1
0x180003a30  jnz     short loc_180003A35
0x180003a32  syscall; Low latency system call
0x180003a34  retn
0x180003a35  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003a37  retn
```
