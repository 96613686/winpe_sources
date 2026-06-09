# CUserTile::_GetOverlay(int,int,Gdiplus::Bitmap * *)

- ea: `0x18006d0d8`
- end: `0x18006d180`
- name: `?_GetOverlay@CUserTile@@AEAAJHHPEAPEAVBitmap@Gdiplus@@@Z`
- size: `168`
- prototype: `int(CUserTile *__hidden this, int, int, struct Gdiplus::Bitmap **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006cda0`

## callees

- `0x180005d08`
- `0x18006d0d8`

## import_xrefs

- `USER32!LoadImageW` at `0x18006d10f`
- `USER32!LoadImageW` at `0x18006d10f`
- `gdiplus!GdipCreateBitmapFromHICON` at `0x18006d152`
- `gdiplus!GdipCreateBitmapFromHICON` at `0x18006d152`
- `gdiplus!GdipAlloc` at `0x18006d129`
- `gdiplus!GdipAlloc` at `0x18006d129`

## pseudocode

```c
__int64 __fastcall CUserTile::_GetOverlay(CUserTile *this, int a2, int a3, struct Gdiplus::Bitmap **a4)
{
  HANDLE ImageW; // rdi
  __int64 result; // rax
  __int64 v7; // rbx
  int v8; // eax
  CUserTile *v9; // rcx
  CUserTile *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = this;
  ImageW = LoadImageW(hinstMapiX, (LPCWSTR)0x787, 1u, a2, a3, 0x8000u);
  if ( !ImageW )
    return HrGetLastError();
  v7 = GdipAlloc(24);
  if ( !v7 )
    return 2147942414LL;
  v10 = 0;
  *(_QWORD *)v7 = &Gdiplus::Image::`vftable';
  v8 = GdipCreateBitmapFromHICON(ImageW, &v10);
  v9 = v10;
  *(_DWORD *)(v7 + 16) = v8;
  result = 0;
  *(_QWORD *)(v7 + 8) = v9;
  *a4 = (struct Gdiplus::Bitmap *)v7;
  return result;
}

```

## disassembly

```asm
0x18006d0d8  mov     rax, rsp
0x18006d0db  mov     [rax+10h], rbx
0x18006d0df  mov     [rax+18h], rsi
0x18006d0e3  mov     [rax+8], rcx
0x18006d0e7  push    rdi
0x18006d0e8  sub     rsp, 30h
0x18006d0ec  mov     rcx, cs:hinstMapiX; hInst
0x18006d0f3  mov     rsi, r9
0x18006d0f6  mov     dword ptr [rax-10h], 8000h
0x18006d0fd  mov     r9d, edx; cx
0x18006d100  mov     [rax-18h], r8d
0x18006d104  mov     edx, 787h; name
0x18006d109  mov     r8d, 1; type
0x18006d10f  call    cs:__imp_LoadImageW
0x18006d115  mov     rdi, rax
0x18006d118  test    rax, rax
0x18006d11b  jnz     short loc_18006D124
0x18006d11d  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18006d122  jmp     short loc_18006D170
0x18006d124  mov     ecx, 18h
0x18006d129  call    cs:__imp_GdipAlloc
0x18006d12f  mov     rbx, rax
0x18006d132  test    rax, rax
0x18006d135  jz      short loc_18006D16B
0x18006d137  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x18006d13e  mov     [rsp+38h+arg_0], 0
0x18006d147  lea     rdx, [rsp+38h+arg_0]
0x18006d14c  mov     [rbx], rax
0x18006d14f  mov     rcx, rdi
0x18006d152  call    cs:__imp_GdipCreateBitmapFromHICON
0x18006d158  mov     rcx, [rsp+38h+arg_0]
0x18006d15d  mov     [rbx+10h], eax
0x18006d160  xor     eax, eax
0x18006d162  mov     [rbx+8], rcx
0x18006d166  mov     [rsi], rbx
0x18006d169  jmp     short loc_18006D170
0x18006d16b  mov     eax, 8007000Eh
0x18006d170  mov     rbx, [rsp+38h+arg_8]
0x18006d175  mov     rsi, [rsp+38h+arg_10]
0x18006d17a  add     rsp, 30h
0x18006d17e  pop     rdi
0x18006d17f  retn
```
