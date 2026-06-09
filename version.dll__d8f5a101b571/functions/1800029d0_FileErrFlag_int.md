# FileErrFlag(int)

- ea: `0x1800029d0`
- end: `0x1800029e9`
- name: `?FileErrFlag@@YAKH@Z`
- size: `25`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b00`

## callees

- `0x1800029d0`

## pseudocode

```c
__int64 __fastcall FileErrFlag(int a1)
{
  __int64 result; // rax

  if ( a1 == 5 )
    return 512;
  result = 1024;
  if ( a1 != 32 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800029d0  cmp     ecx, 5
0x1800029d3  jz      short loc_1800029E3
0x1800029d5  xor     edx, edx
0x1800029d7  mov     eax, 400h
0x1800029dc  cmp     ecx, 20h ; ' '
0x1800029df  cmovnz  eax, edx
0x1800029e2  retn
0x1800029e3  mov     eax, 200h
0x1800029e8  retn
```
