# IsSelectedFontOpenType

- ea: `0x18001b4b0`
- end: `0x18001b52f`
- name: `IsSelectedFontOpenType`
- size: `127`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019a88`

## callees

- `0x18001b4b0`

## import_xrefs

- `GDI32!GetFontData` at `0x18001b4d3`
- `GDI32!GetFontData` at `0x18001b511`
- `GDI32!GetFontData` at `0x18001b4d3`
- `GDI32!GetFontData` at `0x18001b511`

## pseudocode

```c
__int64 __fastcall IsSelectedFontOpenType(HDC hdc, _DWORD *a2)
{
  if ( GetFontData(hdc, 0x66796C67u, 0, 0, 0) - 1 <= 0xFFFFFFFD )
  {
    if ( a2 )
      *a2 = 0x40000;
    return 1;
  }
  if ( GetFontData(hdc, 0x20464643u, 0, 0, 0) - 1 <= 0xFFFFFFFD )
  {
    if ( a2 )
      *a2 = 0x20000;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001b4b0  mov     [rsp+arg_0], rbx
0x18001b4b5  push    rdi
0x18001b4b6  sub     rsp, 30h
0x18001b4ba  mov     rbx, rdx
0x18001b4bd  mov     [rsp+38h+cjBuffer], 0; cjBuffer
0x18001b4c5  mov     edx, 66796C67h; dwTable
0x18001b4ca  xor     r9d, r9d; pvBuffer
0x18001b4cd  xor     r8d, r8d; dwOffset
0x18001b4d0  mov     rdi, rcx
0x18001b4d3  call    cs:__imp_GetFontData
0x18001b4d9  dec     eax
0x18001b4db  cmp     eax, 0FFFFFFFDh
0x18001b4de  ja      short loc_18001B4FB
0x18001b4e0  test    rbx, rbx
0x18001b4e3  jz      short loc_18001B4EB
0x18001b4e5  mov     dword ptr [rbx], 40000h
0x18001b4eb  mov     eax, 1
0x18001b4f0  mov     rbx, [rsp+38h+arg_0]
0x18001b4f5  add     rsp, 30h
0x18001b4f9  pop     rdi
0x18001b4fa  retn
0x18001b4fb  xor     r9d, r9d; pvBuffer
0x18001b4fe  mov     [rsp+38h+cjBuffer], 0; cjBuffer
0x18001b506  xor     r8d, r8d; dwOffset
0x18001b509  mov     edx, 20464643h; dwTable
0x18001b50e  mov     rcx, rdi; hdc
0x18001b511  call    cs:__imp_GetFontData
0x18001b517  dec     eax
0x18001b519  cmp     eax, 0FFFFFFFDh
0x18001b51c  ja      short loc_18001B52B
0x18001b51e  test    rbx, rbx
0x18001b521  jz      short loc_18001B4EB
0x18001b523  mov     dword ptr [rbx], 20000h
0x18001b529  jmp     short loc_18001B4EB
0x18001b52b  xor     eax, eax
0x18001b52d  jmp     short loc_18001B4F0
```
