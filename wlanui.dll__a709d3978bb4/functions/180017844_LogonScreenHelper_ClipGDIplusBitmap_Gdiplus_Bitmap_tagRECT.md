# LogonScreenHelper::ClipGDIplusBitmap(Gdiplus::Bitmap *,tagRECT)

- ea: `0x180017844`
- end: `0x180017a3c`
- name: `?ClipGDIplusBitmap@LogonScreenHelper@@QEAAPEAVBitmap@Gdiplus@@PEAV23@UtagRECT@@@Z`
- size: `504`
- prototype: `struct Gdiplus::Bitmap *__fastcall(LogonScreenHelper *__hidden this, struct Gdiplus::Bitmap *, struct tagRECT *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017bc0`

## callees

- `0x180017844`
- `0x18001d010`

## import_xrefs

- `gdiplus!GdipDisposeImageAttributes` at `0x1800179dc`
- `gdiplus!GdipDisposeImageAttributes` at `0x1800179dc`
- `gdiplus!GdipSetInterpolationMode` at `0x18001791f`
- `gdiplus!GdipSetInterpolationMode` at `0x18001791f`
- `gdiplus!GdipCreateImageAttributes` at `0x180017949`
- `gdiplus!GdipCreateImageAttributes` at `0x180017949`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x180017962`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x180017962`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180017908`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180017908`
- `gdiplus!GdipDeleteGraphics` at `0x1800179fa`
- `gdiplus!GdipDeleteGraphics` at `0x1800179fa`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800178ca`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800178ca`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800179c4`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800179c4`
- `gdiplus!GdipAlloc` at `0x18001786a`
- `gdiplus!GdipAlloc` at `0x1800178e2`
- `gdiplus!GdipAlloc` at `0x180017931`
- `gdiplus!GdipAlloc` at `0x18001786a`
- `gdiplus!GdipAlloc` at `0x1800178e2`
- `gdiplus!GdipAlloc` at `0x180017931`
- `gdiplus!GdipFree` at `0x1800179e5`
- `gdiplus!GdipFree` at `0x180017a03`
- `gdiplus!GdipFree` at `0x1800179e5`
- `gdiplus!GdipFree` at `0x180017a03`

## pseudocode

```c
struct Gdiplus::Bitmap *__fastcall LogonScreenHelper::ClipGDIplusBitmap(
        LogonScreenHelper *this,
        struct Gdiplus::Bitmap *a2,
        struct tagRECT *a3)
{
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned int v8; // r12d
  LONG left; // r13d
  unsigned int v10; // r15d
  _QWORD *v11; // rdi
  __int64 v12; // rcx
  int ImageGraphicsContext; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  _QWORD *v17; // rsi
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v21; // r14d
  LONG top; // [rsp+B0h] [rbp+8h]
  __int64 v24; // [rsp+C0h] [rbp+18h] BYREF

  v5 = 0;
  v6 = GdipAlloc(24);
  v7 = v6;
  if ( v6 )
  {
    v8 = a3->bottom - a3->top;
    left = a3->left;
    top = a3->top;
    v10 = a3->right - a3->left;
    v24 = 0;
    *(_QWORD *)v6 = &Gdiplus::Image::`vftable';
    *(_DWORD *)(v6 + 16) = GdipCreateBitmapFromScan0(v10, v8, 0, 925707, 0, &v24);
    *(_QWORD *)(v7 + 8) = v24;
    v11 = (_QWORD *)GdipAlloc(16);
    if ( !v11 )
      goto LABEL_17;
    v12 = *(_QWORD *)(v7 + 8);
    v24 = 0;
    ImageGraphicsContext = GdipGetImageGraphicsContext(v12, &v24);
    v14 = v24;
    *v11 = v24;
    *((_DWORD *)v11 + 2) = ImageGraphicsContext;
    v15 = GdipSetInterpolationMode(v14, 7);
    if ( v15 )
      *((_DWORD *)v11 + 2) = v15;
    v16 = GdipAlloc(16);
    v17 = (_QWORD *)v16;
    if ( v16 )
    {
      *(_QWORD *)v16 = 0;
      *(_DWORD *)(v16 + 8) = GdipCreateImageAttributes(v16);
      v18 = GdipSetImageAttributesWrapMode(*v17, 3, 4278190080LL);
      if ( v18 )
        *((_DWORD *)v17 + 2) = v18;
      if ( a2 )
        v19 = *((_QWORD *)a2 + 1);
      else
        v19 = 0;
      v20 = GdipDrawImageRectRectI(*v11, v19, 0, 0, v10, v8, left, top, v10, v8, 2, *v17, 0, 0);
      v21 = v20;
      if ( v20 )
        *((_DWORD *)v11 + 2) = v20;
      else
        v21 = 0;
      GdipDisposeImageAttributes(*v17);
      GdipFree(v17);
      v5 = v7;
      if ( v21 )
        v5 = 0;
    }
    GdipDeleteGraphics(*v11);
    GdipFree(v11);
    if ( !v5 )
LABEL_17:
      (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
  }
  return (struct Gdiplus::Bitmap *)v5;
}

```

## disassembly

```asm
0x180017844  mov     [rsp+arg_8], rbx
0x180017849  mov     [rsp+arg_0], rcx
0x18001784e  push    rbp
0x18001784f  push    rsi
0x180017850  push    rdi
0x180017851  push    r12
0x180017853  push    r13
0x180017855  push    r14
0x180017857  push    r15
0x180017859  sub     rsp, 70h
0x18001785d  xor     esi, esi
0x18001785f  mov     rdi, r8
0x180017862  mov     r14, rdx
0x180017865  mov     ebp, esi
0x180017867  lea     ecx, [rsi+18h]
0x18001786a  call    cs:__imp_GdipAlloc
0x180017870  mov     rbx, rax
0x180017873  test    rax, rax
0x180017876  jz      loc_180017A21
0x18001787c  mov     eax, [rdi+4]
0x18001787f  mov     r9d, 0E200Bh
0x180017885  mov     r12d, [rdi+0Ch]
0x180017889  xor     r8d, r8d
0x18001788c  mov     r15d, [rdi+8]
0x180017890  sub     r12d, eax
0x180017893  mov     r13d, [rdi]
0x180017896  mov     edx, r12d
0x180017899  mov     dword ptr [rsp+0A8h+arg_0], eax
0x1800178a0  sub     r15d, r13d
0x1800178a3  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x1800178aa  mov     [rsp+0A8h+arg_10], rsi
0x1800178b2  mov     [rbx], rax
0x1800178b5  mov     ecx, r15d
0x1800178b8  lea     rax, [rsp+0A8h+arg_10]
0x1800178c0  mov     [rsp+0A8h+var_80], rax
0x1800178c5  mov     [rsp+0A8h+var_88], rsi
0x1800178ca  call    cs:__imp_GdipCreateBitmapFromScan0
0x1800178d0  mov     [rbx+10h], eax
0x1800178d3  lea     ecx, [rsi+10h]
0x1800178d6  mov     rax, [rsp+0A8h+arg_10]
0x1800178de  mov     [rbx+8], rax
0x1800178e2  call    cs:__imp_GdipAlloc
0x1800178e8  mov     rdi, rax
0x1800178eb  test    rax, rax
0x1800178ee  jz      loc_180017A0E
0x1800178f4  mov     rcx, [rbx+8]
0x1800178f8  lea     rdx, [rsp+0A8h+arg_10]
0x180017900  mov     [rsp+0A8h+arg_10], rsi
0x180017908  call    cs:__imp_GdipGetImageGraphicsContext
0x18001790e  mov     rcx, [rsp+0A8h+arg_10]
0x180017916  lea     edx, [rsi+7]
0x180017919  mov     [rdi], rcx
0x18001791c  mov     [rdi+8], eax
0x18001791f  call    cs:__imp_GdipSetInterpolationMode
0x180017925  test    eax, eax
0x180017927  jz      short loc_18001792C
0x180017929  mov     [rdi+8], eax
0x18001792c  mov     ecx, 10h
0x180017931  call    cs:__imp_GdipAlloc
0x180017937  mov     rsi, rax
0x18001793a  test    rax, rax
0x18001793d  jz      loc_1800179F7
0x180017943  mov     rcx, rax
0x180017946  mov     [rax], rbp
0x180017949  call    cs:__imp_GdipCreateImageAttributes
0x18001794f  xor     r9d, r9d
0x180017952  mov     [rsi+8], eax
0x180017955  mov     rcx, [rsi]
0x180017958  mov     r8d, 0FF000000h
0x18001795e  lea     edx, [r9+3]
0x180017962  call    cs:__imp_GdipSetImageAttributesWrapMode
0x180017968  test    eax, eax
0x18001796a  jz      short loc_18001796F
0x18001796c  mov     [rsi+8], eax
0x18001796f  mov     rax, [rsi]
0x180017972  test    r14, r14
0x180017975  jz      short loc_18001797D
0x180017977  mov     rdx, [r14+8]
0x18001797b  jmp     short loc_180017980
0x18001797d  mov     rdx, rbp
0x180017980  mov     rcx, [rdi]
0x180017983  xor     r9d, r9d
0x180017986  mov     [rsp+0A8h+var_40], rbp
0x18001798b  xor     r8d, r8d
0x18001798e  mov     [rsp+0A8h+var_48], rbp
0x180017993  mov     [rsp+0A8h+var_50], rax
0x180017998  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x18001799f  mov     [rsp+0A8h+var_58], 2
0x1800179a7  mov     [rsp+0A8h+var_60], r12d
0x1800179ac  mov     [rsp+0A8h+var_68], r15d
0x1800179b1  mov     [rsp+0A8h+var_70], eax
0x1800179b5  mov     [rsp+0A8h+var_78], r13d
0x1800179ba  mov     dword ptr [rsp+0A8h+var_80], r12d
0x1800179bf  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800179c4  call    cs:__imp_GdipDrawImageRectRectI
0x1800179ca  mov     r14d, eax
0x1800179cd  test    eax, eax
0x1800179cf  jz      short loc_1800179D6
0x1800179d1  mov     [rdi+8], eax
0x1800179d4  jmp     short loc_1800179D9
0x1800179d6  mov     r14d, ebp
0x1800179d9  mov     rcx, [rsi]
0x1800179dc  call    cs:__imp_GdipDisposeImageAttributes
0x1800179e2  mov     rcx, rsi
0x1800179e5  call    cs:__imp_GdipFree
0x1800179eb  xor     eax, eax
0x1800179ed  mov     rbp, rbx
0x1800179f0  test    r14d, r14d
0x1800179f3  cmovnz  rbp, rax
0x1800179f7  mov     rcx, [rdi]
0x1800179fa  call    cs:__imp_GdipDeleteGraphics
0x180017a00  mov     rcx, rdi
0x180017a03  call    cs:__imp_GdipFree
0x180017a09  test    rbp, rbp
0x180017a0c  jnz     short loc_180017A21
0x180017a0e  mov     rdx, [rbx]
0x180017a11  mov     rcx, rbx
0x180017a14  mov     rax, [rdx]
0x180017a17  mov     edx, 1
0x180017a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a21  mov     rbx, [rsp+0A8h+arg_8]
0x180017a29  mov     rax, rbp
0x180017a2c  add     rsp, 70h
0x180017a30  pop     r15
0x180017a32  pop     r14
0x180017a34  pop     r13
0x180017a36  pop     r12
0x180017a38  pop     rdi
0x180017a39  pop     rsi
0x180017a3a  pop     rbp
0x180017a3b  retn
```
