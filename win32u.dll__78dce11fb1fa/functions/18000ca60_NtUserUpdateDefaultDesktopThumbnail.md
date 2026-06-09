# NtUserUpdateDefaultDesktopThumbnail

- ea: `0x18000ca60`
- end: `0x18000ca78`
- name: `NtUserUpdateDefaultDesktopThumbnail`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ca60`

## pseudocode

```c
__int64 NtUserUpdateDefaultDesktopThumbnail()
{
  __int64 result; // rax

  result = 5566;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000ca60  mov     r10, rcx
0x18000ca63  mov     eax, 15BEh
0x18000ca68  test    byte ptr ds:7FFE0308h, 1
0x18000ca70  jnz     short loc_18000CA75
0x18000ca72  syscall; Low latency system call
0x18000ca74  retn
0x18000ca75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000ca77  retn
```
