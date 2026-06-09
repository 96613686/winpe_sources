# ATL::AtlHresultFromWin32(ulong)

- ea: `0x140002fec`
- end: `0x140002ffc`
- name: `?AtlHresultFromWin32@ATL@@YAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400028bc`
- `0x140004190`

## callees

- `0x140002fec`

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
0x140002fec  test    ecx, ecx
0x140002fee  jle     short loc_140002FF9
0x140002ff0  movzx   ecx, cx
0x140002ff3  or      ecx, 80070000h
0x140002ff9  mov     eax, ecx
0x140002ffb  retn
```
