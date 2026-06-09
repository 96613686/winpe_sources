# FreeDC

- ea: `0x18001d4b4`
- end: `0x18001d4df`
- name: `FreeDC`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019a88`
- `0x180019f9c`

## callees

- `0x18001d4b4`

## import_xrefs

- `GDI32!DeleteDC` at `0x18001d4d4`
- `GDI32!DeleteDC` at `0x18001d4d4`
- `USER32!ReleaseDC` at `0x18001d4c7`

## pseudocode

```c
int __fastcall FreeDC(HDC a1, __int16 a2)
{
  int result; // eax

  if ( a2 == 1 )
    return ReleaseDC(0, a1);
  if ( a2 == 2 )
    return DeleteDC(a1);
  return result;
}

```

## disassembly

```asm
0x18001d4b4  sub     rsp, 28h
0x18001d4b8  cmp     dx, 1
0x18001d4bc  jnz     short loc_18001D4CE
0x18001d4be  mov     rdx, rcx
0x18001d4c1  xor     ecx, ecx; hdc
0x18001d4c3  add     rsp, 28h
0x18001d4c7  jmp     cs:__imp_ReleaseDC
0x18001d4ce  cmp     dx, 2
0x18001d4d2  jnz     short loc_18001D4DA
0x18001d4d4  call    cs:__imp_DeleteDC
0x18001d4da  add     rsp, 28h
0x18001d4de  retn
```
