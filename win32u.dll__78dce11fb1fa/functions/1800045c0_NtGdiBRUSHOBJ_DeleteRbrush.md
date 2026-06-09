# NtGdiBRUSHOBJ_DeleteRbrush

- ea: `0x1800045c0`
- end: `0x1800045d8`
- name: `NtGdiBRUSHOBJ_DeleteRbrush`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800045c0`

## pseudocode

```c
__int64 NtGdiBRUSHOBJ_DeleteRbrush()
{
  __int64 result; // rax

  result = 4505;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800045c0  mov     r10, rcx
0x1800045c3  mov     eax, 1199h
0x1800045c8  test    byte ptr ds:7FFE0308h, 1
0x1800045d0  jnz     short loc_1800045D5
0x1800045d2  syscall; Low latency system call
0x1800045d4  retn
0x1800045d5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800045d7  retn
```
