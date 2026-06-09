# ZwGdiDdDDIConfigureSharedResource

- ea: `0x180004c40`
- end: `0x180004c58`
- name: `ZwGdiDdDDIConfigureSharedResource`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004c40`

## pseudocode

```c
__int64 ZwGdiDdDDIConfigureSharedResource()
{
  __int64 result; // rax

  result = 4557;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004c40  mov     r10, rcx
0x180004c43  mov     eax, 11CDh
0x180004c48  test    byte ptr ds:7FFE0308h, 1
0x180004c50  jnz     short loc_180004C55
0x180004c52  syscall; Low latency system call
0x180004c54  retn
0x180004c55  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004c57  retn
```
