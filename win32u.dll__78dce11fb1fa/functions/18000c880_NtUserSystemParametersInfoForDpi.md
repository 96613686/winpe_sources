# NtUserSystemParametersInfoForDpi

- ea: `0x18000c880`
- end: `0x18000c898`
- name: `NtUserSystemParametersInfoForDpi`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c880`

## pseudocode

```c
__int64 NtUserSystemParametersInfoForDpi()
{
  __int64 result; // rax

  result = 5551;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000c880  mov     r10, rcx
0x18000c883  mov     eax, 15AFh
0x18000c888  test    byte ptr ds:7FFE0308h, 1
0x18000c890  jnz     short loc_18000C895
0x18000c892  syscall; Low latency system call
0x18000c894  retn
0x18000c895  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000c897  retn
```
