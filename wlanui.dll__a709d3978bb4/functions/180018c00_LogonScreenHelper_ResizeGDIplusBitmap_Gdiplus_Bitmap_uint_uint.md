# LogonScreenHelper::ResizeGDIplusBitmap(Gdiplus::Bitmap *,uint,uint)

- ea: `0x180018c00`
- end: `0x180018e1b`
- name: `?ResizeGDIplusBitmap@LogonScreenHelper@@QEAAPEAVBitmap@Gdiplus@@PEAV23@II@Z`
- size: `539`
- prototype: `struct Gdiplus::Bitmap *__fastcall(LogonScreenHelper *__hidden this, struct Gdiplus::Bitmap *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017bc0`

## callees

- `0x180018c00`
- `0x18001d010`

## import_xrefs

- `gdiplus!GdipDisposeImageAttributes` at `0x180018dbb`
- `gdiplus!GdipDisposeImageAttributes` at `0x180018dbb`
- `gdiplus!GdipSetInterpolationMode` at `0x180018d0c`
- `gdiplus!GdipSetInterpolationMode` at `0x180018d0c`
- `gdiplus!GdipCreateImageAttributes` at `0x180018d34`
- `gdiplus!GdipCreateImageAttributes` at `0x180018d34`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x180018d4e`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x180018d4e`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180018cf9`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180018cf9`
- `gdiplus!GdipDeleteGraphics` at `0x180018dd9`
- `gdiplus!GdipDeleteGraphics` at `0x180018dd9`
- `gdiplus!GdipGetImageWidth` at `0x180018c3d`
- `gdiplus!GdipGetImageWidth` at `0x180018c3d`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180018cc3`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180018cc3`
- `gdiplus!GdipDrawImageRectRectI` at `0x180018da3`
- `gdiplus!GdipDrawImageRectRectI` at `0x180018da3`
- `gdiplus!GdipAlloc` at `0x180018c87`
- `gdiplus!GdipAlloc` at `0x180018cdb`
- `gdiplus!GdipAlloc` at `0x180018d1c`
- `gdiplus!GdipAlloc` at `0x180018c87`
- `gdiplus!GdipAlloc` at `0x180018cdb`
- `gdiplus!GdipAlloc` at `0x180018d1c`
- `gdiplus!GdipGetImageHeight` at `0x180018c5e`
- `gdiplus!GdipGetImageHeight` at `0x180018c5e`
- `gdiplus!GdipFree` at `0x180018dc4`
- `gdiplus!GdipFree` at `0x180018de2`
- `gdiplus!GdipFree` at `0x180018dc4`
- `gdiplus!GdipFree` at `0x180018de2`

## pseudocode

```c
struct Gdiplus::Bitmap *__fastcall LogonScreenHelper::ResizeGDIplusBitmap(
        LogonScreenHelper *this,
        struct Gdiplus::Bitmap *a2,
        unsigned int a3,
        unsigned int a4)
{
  int ImageWidth; // eax
  int v8; // r13d
  __int64 v9; // rcx
  int ImageHeight; // eax
  int v11; // r12d
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 v14; // rbx
  _QWORD *v15; // rdi
  __int64 v16; // rcx
  int ImageGraphicsContext; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  _QWORD *v21; // r14
  int v22; // eax
  int v23; // eax
  int v24; // r15d
  __int64 v26; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+C0h] [rbp+50h]
  unsigned int v28; // [rsp+C8h] [rbp+58h]

  v28 = a4;
  v27 = a3;
  HIDWORD(v26) = HIDWORD(this);
  LODWORD(v26) = 0;
  ImageWidth = GdipGetImageWidth(*((_QWORD *)a2 + 1), &v26);
  if ( ImageWidth )
    *((_DWORD *)a2 + 4) = ImageWidth;
  v8 = v26;
  v9 = *((_QWORD *)a2 + 1);
  LODWORD(v26) = 0;
  ImageHeight = GdipGetImageHeight(v9, &v26);
  if ( ImageHeight )
    *((_DWORD *)a2 + 4) = ImageHeight;
  v11 = v26;
  if ( a3 == v8 && a4 == (_DWORD)v26 )
    return a2;
  v12 = 0;
  v13 = GdipAlloc(24);
  v14 = v13;
  if ( v13 )
  {
    v26 = 0;
    *(_QWORD *)v13 = &Gdiplus::Image::`vftable';
    *(_DWORD *)(v13 + 16) = GdipCreateBitmapFromScan0(a3, a4, 0, 925707, 0, &v26);
    *(_QWORD *)(v14 + 8) = v26;
    v15 = (_QWORD *)GdipAlloc(16);
    if ( !v15 )
      goto LABEL_21;
    v16 = *(_QWORD *)(v14 + 8);
    v26 = 0;
    ImageGraphicsContext = GdipGetImageGraphicsContext(v16, &v26);
    v18 = v26;
    *v15 = v26;
    *((_DWORD *)v15 + 2) = ImageGraphicsContext;
    v19 = GdipSetInterpolationMode(v18, 7);
    if ( v19 )
      *((_DWORD *)v15 + 2) = v19;
    v20 = GdipAlloc(16);
    v21 = (_QWORD *)v20;
    if ( v20 )
    {
      *(_QWORD *)v20 = 0;
      *(_DWORD *)(v20 + 8) = GdipCreateImageAttributes(v20);
      v22 = GdipSetImageAttributesWrapMode(*v21, 3, 4278190080LL);
      if ( v22 )
        *((_DWORD *)v21 + 2) = v22;
      v23 = GdipDrawImageRectRectI(*v15, *((_QWORD *)a2 + 1), 0, 0, v27, v28, 0, 0, v8, v11, 2, *v21, 0, 0);
      v24 = v23;
      if ( v23 )
        *((_DWORD *)v15 + 2) = v23;
      else
        v24 = 0;
      GdipDisposeImageAttributes(*v21);
      GdipFree(v21);
      v12 = v14;
      if ( v24 )
        v12 = 0;
    }
    GdipDeleteGraphics(*v15);
    GdipFree(v15);
    if ( !v12 )
LABEL_21:
      (**(void (__fastcall ***)(__int64, __int64))v14)(v14, 1);
  }
  return (struct Gdiplus::Bitmap *)v12;
}

```

## disassembly

```asm
0x180018c00  mov     rax, rsp
0x180018c03  mov     [rax+10h], rbx
0x180018c07  mov     [rax+20h], r9d
0x180018c0b  mov     [rax+18h], r8d
0x180018c0f  mov     [rax+8], rcx
0x180018c13  push    rbp
0x180018c14  push    rsi
0x180018c15  push    rdi
0x180018c16  push    r12
0x180018c18  push    r13
0x180018c1a  push    r14
0x180018c1c  push    r15
0x180018c1e  mov     rbp, rsp
0x180018c21  sub     rsp, 70h
0x180018c25  mov     r15, rdx
0x180018c28  mov     dword ptr [rbp+arg_0], 0
0x180018c2f  lea     rdx, [rbp+arg_0]
0x180018c33  mov     edi, r9d
0x180018c36  mov     r14d, r8d
0x180018c39  mov     rcx, [r15+8]
0x180018c3d  call    cs:__imp_GdipGetImageWidth
0x180018c43  test    eax, eax
0x180018c45  jz      short loc_180018C4B
0x180018c47  mov     [r15+10h], eax
0x180018c4b  mov     r13d, dword ptr [rbp+arg_0]
0x180018c4f  lea     rdx, [rbp+arg_0]
0x180018c53  mov     rcx, [r15+8]
0x180018c57  mov     dword ptr [rbp+arg_0], 0
0x180018c5e  call    cs:__imp_GdipGetImageHeight
0x180018c64  test    eax, eax
0x180018c66  jz      short loc_180018C6C
0x180018c68  mov     [r15+10h], eax
0x180018c6c  mov     r12d, dword ptr [rbp+arg_0]
0x180018c70  cmp     r14d, r13d
0x180018c73  jnz     short loc_180018C82
0x180018c75  cmp     edi, r12d
0x180018c78  jnz     short loc_180018C82
0x180018c7a  mov     rsi, r15
0x180018c7d  jmp     loc_180018E00
0x180018c82  xor     esi, esi
0x180018c84  lea     ecx, [rsi+18h]
0x180018c87  call    cs:__imp_GdipAlloc
0x180018c8d  mov     rbx, rax
0x180018c90  test    rax, rax
0x180018c93  jz      loc_180018E00
0x180018c99  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180018ca0  mov     [rbp+arg_0], rsi
0x180018ca4  mov     [rbx], rax
0x180018ca7  mov     r9d, 0E200Bh
0x180018cad  lea     rax, [rbp+arg_0]
0x180018cb1  xor     r8d, r8d
0x180018cb4  mov     [rsp+70h+var_48], rax
0x180018cb9  mov     edx, edi
0x180018cbb  mov     ecx, r14d
0x180018cbe  mov     [rsp+70h+var_50], rsi
0x180018cc3  call    cs:__imp_GdipCreateBitmapFromScan0
0x180018cc9  mov     [rbx+10h], eax
0x180018ccc  lea     r14d, [rsi+10h]
0x180018cd0  mov     rax, [rbp+arg_0]
0x180018cd4  mov     ecx, r14d
0x180018cd7  mov     [rbx+8], rax
0x180018cdb  call    cs:__imp_GdipAlloc
0x180018ce1  mov     rdi, rax
0x180018ce4  test    rax, rax
0x180018ce7  jz      loc_180018DED
0x180018ced  mov     rcx, [rbx+8]
0x180018cf1  lea     rdx, [rbp+arg_0]
0x180018cf5  mov     [rbp+arg_0], rsi
0x180018cf9  call    cs:__imp_GdipGetImageGraphicsContext
0x180018cff  mov     rcx, [rbp+arg_0]
0x180018d03  lea     edx, [rsi+7]
0x180018d06  mov     [rdi], rcx
0x180018d09  mov     [rdi+8], eax
0x180018d0c  call    cs:__imp_GdipSetInterpolationMode
0x180018d12  test    eax, eax
0x180018d14  jz      short loc_180018D19
0x180018d16  mov     [rdi+8], eax
0x180018d19  mov     rcx, r14
0x180018d1c  call    cs:__imp_GdipAlloc
0x180018d22  mov     r14, rax
0x180018d25  test    rax, rax
0x180018d28  jz      loc_180018DD6
0x180018d2e  mov     rcx, rax
0x180018d31  mov     [rax], rsi
0x180018d34  call    cs:__imp_GdipCreateImageAttributes
0x180018d3a  xor     r9d, r9d
0x180018d3d  mov     [r14+8], eax
0x180018d41  mov     rcx, [r14]
0x180018d44  mov     r8d, 0FF000000h
0x180018d4a  lea     edx, [r9+3]
0x180018d4e  call    cs:__imp_GdipSetImageAttributesWrapMode
0x180018d54  test    eax, eax
0x180018d56  jz      short loc_180018D5C
0x180018d58  mov     [r14+8], eax
0x180018d5c  mov     rax, [r14]
0x180018d5f  xor     r9d, r9d
0x180018d62  mov     rdx, [r15+8]
0x180018d66  xor     r8d, r8d
0x180018d69  mov     rcx, [rdi]
0x180018d6c  mov     [rsp+70h+var_8], rsi
0x180018d71  mov     [rsp+70h+var_10], rsi
0x180018d76  mov     [rsp+70h+var_18], rax
0x180018d7b  mov     eax, [rbp+arg_18]
0x180018d7e  mov     [rsp+70h+var_20], 2
0x180018d86  mov     [rsp+70h+var_28], r12d
0x180018d8b  mov     [rsp+70h+var_30], r13d
0x180018d90  mov     [rsp+70h+var_38], esi
0x180018d94  mov     [rsp+70h+var_40], esi
0x180018d98  mov     dword ptr [rsp+70h+var_48], eax
0x180018d9c  mov     eax, [rbp+arg_10]
0x180018d9f  mov     dword ptr [rsp+70h+var_50], eax
0x180018da3  call    cs:__imp_GdipDrawImageRectRectI
0x180018da9  mov     r15d, eax
0x180018dac  test    eax, eax
0x180018dae  jz      short loc_180018DB5
0x180018db0  mov     [rdi+8], eax
0x180018db3  jmp     short loc_180018DB8
0x180018db5  mov     r15d, esi
0x180018db8  mov     rcx, [r14]
0x180018dbb  call    cs:__imp_GdipDisposeImageAttributes
0x180018dc1  mov     rcx, r14
0x180018dc4  call    cs:__imp_GdipFree
0x180018dca  xor     eax, eax
0x180018dcc  mov     rsi, rbx
0x180018dcf  test    r15d, r15d
0x180018dd2  cmovnz  rsi, rax
0x180018dd6  mov     rcx, [rdi]
0x180018dd9  call    cs:__imp_GdipDeleteGraphics
0x180018ddf  mov     rcx, rdi
0x180018de2  call    cs:__imp_GdipFree
0x180018de8  test    rsi, rsi
0x180018deb  jnz     short loc_180018E00
0x180018ded  mov     rdx, [rbx]
0x180018df0  mov     rcx, rbx
0x180018df3  mov     rax, [rdx]
0x180018df6  mov     edx, 1
0x180018dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e00  mov     rbx, [rsp+70h+arg_8]
0x180018e08  mov     rax, rsi
0x180018e0b  add     rsp, 70h
0x180018e0f  pop     r15
0x180018e11  pop     r14
0x180018e13  pop     r13
0x180018e15  pop     r12
0x180018e17  pop     rdi
0x180018e18  pop     rsi
0x180018e19  pop     rbp
0x180018e1a  retn
```
