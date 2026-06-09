# ZwDCompositionCommitSynchronizationObject

- ea: `0x180003580`
- end: `0x180003598`
- name: `ZwDCompositionCommitSynchronizationObject`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003580`

## pseudocode

```c
__int64 ZwDCompositionCommitSynchronizationObject()
{
  __int64 result; // rax

  result = 4375;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003580  mov     r10, rcx
0x180003583  mov     eax, 1117h
0x180003588  test    byte ptr ds:7FFE0308h, 1
0x180003590  jnz     short loc_180003595
0x180003592  syscall; Low latency system call
0x180003594  retn
0x180003595  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003597  retn
```
