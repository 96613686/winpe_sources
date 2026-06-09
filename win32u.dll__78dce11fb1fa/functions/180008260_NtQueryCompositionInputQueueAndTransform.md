# NtQueryCompositionInputQueueAndTransform

- ea: `0x180008260`
- end: `0x180008278`
- name: `NtQueryCompositionInputQueueAndTransform`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008260`

## pseudocode

```c
__int64 NtQueryCompositionInputQueueAndTransform()
{
  __int64 result; // rax

  result = 4990;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008260  mov     r10, rcx
0x180008263  mov     eax, 137Eh
0x180008268  test    byte ptr ds:7FFE0308h, 1
0x180008270  jnz     short loc_180008275
0x180008272  syscall; Low latency system call
0x180008274  retn
0x180008275  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008277  retn
```
