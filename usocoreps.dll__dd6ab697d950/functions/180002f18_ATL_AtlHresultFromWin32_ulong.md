# ATL::AtlHresultFromWin32(ulong)

- ea: `0x180002f18`
- end: `0x180002f28`
- name: `?AtlHresultFromWin32@ATL@@YAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000271c`
- `0x180003b5c`

## callees

- `0x180002f18`

## pseudocode

```c
__int64 __fastcall ATL::AtlHresultFromWin32(int a1)
{
  if ( a1 > 0 )
    return (unsigned __int16)a1 | 0x80070000;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180002f18  test    ecx, ecx
0x180002f1a  jle     short loc_180002F25
0x180002f1c  movzx   ecx, cx
0x180002f1f  or      ecx, 80070000h
0x180002f25  mov     eax, ecx
0x180002f27  retn
```
