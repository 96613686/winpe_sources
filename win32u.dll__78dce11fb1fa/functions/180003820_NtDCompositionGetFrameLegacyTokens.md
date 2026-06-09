# NtDCompositionGetFrameLegacyTokens

- ea: `0x180003820`
- end: `0x180003838`
- name: `NtDCompositionGetFrameLegacyTokens`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003820`

## pseudocode

```c
__int64 NtDCompositionGetFrameLegacyTokens()
{
  __int64 result; // rax

  result = 4396;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003820  mov     r10, rcx
0x180003823  mov     eax, 112Ch
0x180003828  test    byte ptr ds:7FFE0308h, 1
0x180003830  jnz     short loc_180003835
0x180003832  syscall; Low latency system call
0x180003834  retn
0x180003835  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003837  retn
```
