# ATL::AtlHresultFromWin32(ulong)

- ea: `0x140002a3c`
- end: `0x140002a4c`
- name: `?AtlHresultFromWin32@ATL@@YAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002424`
- `0x140004954`

## callees

- `0x140002a3c`

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
0x140002a3c  test    ecx, ecx
0x140002a3e  jle     short loc_140002A49
0x140002a40  movzx   ecx, cx
0x140002a43  or      ecx, 80070000h
0x140002a49  mov     eax, ecx
0x140002a4b  retn
```
