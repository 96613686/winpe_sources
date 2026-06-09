# _seh_filter_dll

- ea: `0x100419fa0`
- end: `0x100419fb3`
- name: `_seh_filter_dll`
- size: `19`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100416e08`

## callees

- `0x100419fa0`
- `0x100419fbc`

## pseudocode

```c
int __cdecl seh_filter_dll(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( ExceptionNum == -529697949 )
    return seh_filter_exe(0xE06D7363, ExceptionPtr);
  else
    return 0;
}

```

## disassembly

```asm
0x100419fa0  mov     eax, 0E06D7363h
0x100419fa5  cmp     ecx, eax
0x100419fa7  jz      short loc_100419FAC
0x100419fa9  xor     eax, eax
0x100419fab  retn
0x100419fac  mov     ecx, eax
0x100419fae  jmp     _seh_filter_exe
```
