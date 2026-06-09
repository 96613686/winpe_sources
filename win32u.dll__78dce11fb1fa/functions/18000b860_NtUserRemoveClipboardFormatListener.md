# NtUserRemoveClipboardFormatListener

- ea: `0x18000b860`
- end: `0x18000b878`
- name: `NtUserRemoveClipboardFormatListener`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b860`

## pseudocode

```c
__int64 NtUserRemoveClipboardFormatListener()
{
  __int64 result; // rax

  result = 5422;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000b860  mov     r10, rcx
0x18000b863  mov     eax, 152Eh
0x18000b868  test    byte ptr ds:7FFE0308h, 1
0x18000b870  jnz     short loc_18000B875
0x18000b872  syscall; Low latency system call
0x18000b874  retn
0x18000b875  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000b877  retn
```
