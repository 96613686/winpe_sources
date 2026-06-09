# NtUserGetDisplayAutoRotationPreferencesByProcessId

- ea: `0x180009a60`
- end: `0x180009a78`
- name: `NtUserGetDisplayAutoRotationPreferencesByProcessId`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009a60`

## pseudocode

```c
__int64 NtUserGetDisplayAutoRotationPreferencesByProcessId()
{
  __int64 result; // rax

  result = 5182;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009a60  mov     r10, rcx
0x180009a63  mov     eax, 143Eh
0x180009a68  test    byte ptr ds:7FFE0308h, 1
0x180009a70  jnz     short loc_180009A75
0x180009a72  syscall; Low latency system call
0x180009a74  retn
0x180009a75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009a77  retn
```
