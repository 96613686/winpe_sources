# NtDCompositionSetChannelCommitCompletionEvent

- ea: `0x180003a00`
- end: `0x180003a18`
- name: `NtDCompositionSetChannelCommitCompletionEvent`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003a00`

## pseudocode

```c
__int64 NtDCompositionSetChannelCommitCompletionEvent()
{
  __int64 result; // rax

  result = 4411;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003a00  mov     r10, rcx
0x180003a03  mov     eax, 113Bh
0x180003a08  test    byte ptr ds:7FFE0308h, 1
0x180003a10  jnz     short loc_180003A15
0x180003a12  syscall; Low latency system call
0x180003a14  retn
0x180003a15  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003a17  retn
```
