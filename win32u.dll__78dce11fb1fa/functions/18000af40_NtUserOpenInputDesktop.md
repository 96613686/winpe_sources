# NtUserOpenInputDesktop

- ea: `0x18000af40`
- end: `0x18000af58`
- name: `NtUserOpenInputDesktop`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000af40`

## pseudocode

```c
__int64 NtUserOpenInputDesktop()
{
  __int64 result; // rax

  result = 5349;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000af40  mov     r10, rcx
0x18000af43  mov     eax, 14E5h
0x18000af48  test    byte ptr ds:7FFE0308h, 1
0x18000af50  jnz     short loc_18000AF55
0x18000af52  syscall; Low latency system call
0x18000af54  retn
0x18000af55  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000af57  retn
```
