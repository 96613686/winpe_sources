# _DrawPie(HDC__ *,tagRECT const *,uint,uint,ulong const *)

- ea: `0x180032a58`
- end: `0x180032bb8`
- name: `?_DrawPie@@YAXPEAUHDC__@@PEBUtagRECT@@IIPEBK@Z`
- size: `352`
- prototype: `void __fastcall(HDC, const struct tagRECT *, unsigned int, unsigned int, const unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180069430`

## callees

- `0x18002ea3c`
- `0x18002ed60`
- `0x180032a58`
- `0x180032bc0`
- `0x1800334a0`
- `0x1800685e0`
- `0x180068644`
- `0x1800688a8`

## import_xrefs

- `gdiplus!GdipDeleteGraphics` at `0x180032b90`
- `gdiplus!GdipDeleteGraphics` at `0x180032b9a`
- `gdiplus!GdipDeleteGraphics` at `0x180032b90`
- `gdiplus!GdipDeleteGraphics` at `0x180032b9a`
- `gdiplus!GdipDisposeImage` at `0x180032ba4`
- `gdiplus!GdipDisposeImage` at `0x180032ba4`
- `gdiplus!GdipSetInterpolationMode` at `0x180032b48`
- `gdiplus!GdipSetInterpolationMode` at `0x180032b48`

## pseudocode

```c
void __fastcall _DrawPie(HDC a1, const struct tagRECT *a2, int a3, int a4)
{
  int v8; // r9d
  LONG v9; // r8d
  int v10; // eax
  int v11; // eax
  int v12; // eax
  LONG top; // edx
  int v14; // eax
  int v15; // eax
  struct tagRECT v16; // [rsp+60h] [rbp-31h] BYREF
  __int64 v17; // [rsp+70h] [rbp-21h] BYREF
  int v18; // [rsp+78h] [rbp-19h]
  __int64 v19; // [rsp+80h] [rbp-11h] BYREF
  int v20; // [rsp+88h] [rbp-9h]
  _DWORD v21[4]; // [rsp+90h] [rbp-1h] BYREF
  _BYTE v22[8]; // [rsp+A0h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+A8h] [rbp+17h]
  int v24; // [rsp+B0h] [rbp+1Fh]

  if ( (int)StartGdiPlus() >= 0 )
  {
    v9 = 2 * (a2->bottom - a2->top);
    v16.right = 2 * (a2->right - a2->left);
    v16.bottom = v9;
    *(_QWORD *)&v16.left = 0;
    Gdiplus::Bitmap::Bitmap((Gdiplus::Bitmap *)v22, v16.right, v9, v8);
    v10 = v24;
    v24 = 0;
    if ( !v10 )
    {
      Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v19, (struct Image *)v22);
      v11 = v20;
      v20 = 0;
      if ( !v11 && !(unsigned int)Gdiplus::Graphics::SetCompositingMode(&v19) )
      {
        _DrawPieActual((struct Gdiplus::Graphics *)&v19, &v16, a3, 2 * a4);
        Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v17, a1);
        v12 = v18;
        v18 = 0;
        if ( !v12
          && !(unsigned int)Gdiplus::Graphics::SetCompositingMode(&v17)
          && !(unsigned int)GdipSetInterpolationMode(v17, 7) )
        {
          top = a2->top;
          v14 = a2->right - a2->left;
          v21[0] = a2->left;
          v21[2] = v14;
          v15 = a2->bottom - top;
          v21[1] = top;
          v21[3] = v15;
          Gdiplus::Graphics::DrawImage(&v17, v22, v21);
        }
        GdipDeleteGraphics(v17);
      }
      GdipDeleteGraphics(v19);
    }
    GdipDisposeImage(v23);
  }
}

```

## disassembly

```asm
0x180032a58  push    rbp
0x180032a5a  push    rbx
0x180032a5b  push    rsi
0x180032a5c  push    rdi
0x180032a5d  push    r14
0x180032a5f  lea     rbp, [rsp-2Fh]
0x180032a64  sub     rsp, 0C0h
0x180032a6b  mov     edi, r9d
0x180032a6e  mov     esi, r8d
0x180032a71  mov     rbx, rdx
0x180032a74  mov     r14, rcx
0x180032a77  call    ?StartGdiPlus@@YAJXZ; StartGdiPlus(void)
0x180032a7c  test    eax, eax
0x180032a7e  js      loc_180032BAA
0x180032a84  mov     edx, [rbx+8]
0x180032a87  lea     rcx, [rbp+4Fh+var_40]; this
0x180032a8b  mov     r8d, [rbx+0Ch]
0x180032a8f  sub     edx, [rbx]
0x180032a91  sub     r8d, [rbx+4]
0x180032a95  add     edx, edx; int
0x180032a97  add     r8d, r8d; int
0x180032a9a  mov     qword ptr [rbp+4Fh+var_80.right], 0
0x180032aa2  mov     [rbp+4Fh+var_80.right], edx
0x180032aa5  mov     [rbp+4Fh+var_80.bottom], r8d
0x180032aa9  mov     qword ptr [rbp+4Fh+var_80.left], 0
0x180032ab1  call    ??0Bitmap@Gdiplus@@QEAA@HHH@Z; Gdiplus::Bitmap::Bitmap(int,int,int)
0x180032ab6  mov     eax, [rbp+4Fh+var_30]
0x180032ab9  mov     [rbp+4Fh+var_30], 0
0x180032ac0  test    eax, eax
0x180032ac2  jnz     loc_180032BA0
0x180032ac8  lea     rdx, [rbp+4Fh+var_40]; struct Image *
0x180032acc  lea     rcx, [rbp+4Fh+var_60]; this
0x180032ad0  call    ??0Graphics@Gdiplus@@QEAA@PEAVImage@1@@Z; Gdiplus::Graphics::Graphics(Gdiplus::Image *)
0x180032ad5  mov     eax, [rbp+4Fh+var_58]
0x180032ad8  mov     [rbp+4Fh+var_58], 0
0x180032adf  test    eax, eax
0x180032ae1  jnz     loc_180032B96
0x180032ae7  lea     rcx, [rbp+4Fh+var_60]
0x180032aeb  call    ?SetCompositingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4CompositingMode@2@@Z; Gdiplus::Graphics::SetCompositingMode(Gdiplus::CompositingMode)
0x180032af0  test    eax, eax
0x180032af2  jnz     loc_180032B96
0x180032af8  movss   xmm0, cs:__real@3f800000
0x180032b00  lea     r9d, [rdi+rdi]; unsigned int
0x180032b04  mov     r8d, esi; unsigned int
0x180032b07  movss   [rsp+0E0h+var_C0], xmm0; float
0x180032b0d  lea     rdx, [rbp+4Fh+var_80]; struct tagRECT *
0x180032b11  lea     rcx, [rbp+4Fh+var_60]; struct Gdiplus::Graphics *
0x180032b15  call    ?_DrawPieActual@@YAXPEAVGraphics@Gdiplus@@PEBUtagRECT@@IIMPEBK@Z; _DrawPieActual(Gdiplus::Graphics *,tagRECT const *,uint,uint,float,ulong const *)
0x180032b1a  mov     rdx, r14; HDC
0x180032b1d  lea     rcx, [rbp+4Fh+var_70]; this
0x180032b21  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x180032b26  mov     eax, [rbp+4Fh+var_68]
0x180032b29  mov     [rbp+4Fh+var_68], 0
0x180032b30  test    eax, eax
0x180032b32  jnz     short loc_180032B8C
0x180032b34  lea     rcx, [rbp+4Fh+var_70]
0x180032b38  call    ?SetCompositingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4CompositingMode@2@@Z; Gdiplus::Graphics::SetCompositingMode(Gdiplus::CompositingMode)
0x180032b3d  test    eax, eax
0x180032b3f  jnz     short loc_180032B8C
0x180032b41  mov     rcx, [rbp+4Fh+var_70]
0x180032b45  lea     edx, [rax+7]
0x180032b48  call    cs:__imp_GdipSetInterpolationMode
0x180032b4e  test    eax, eax
0x180032b50  jnz     short loc_180032B8C
0x180032b52  mov     ecx, [rbx]
0x180032b54  lea     r8, [rbp+4Fh+var_50]
0x180032b58  mov     edx, [rbx+4]
0x180032b5b  mov     eax, [rbx+8]
0x180032b5e  sub     eax, ecx
0x180032b60  mov     [rbp+4Fh+var_50], ecx
0x180032b63  mov     [rbp+4Fh+var_48], eax
0x180032b66  lea     rcx, [rbp+4Fh+var_70]
0x180032b6a  mov     eax, [rbx+0Ch]
0x180032b6d  sub     eax, edx
0x180032b6f  mov     [rbp+4Fh+var_4C], edx
0x180032b72  mov     [rbp+4Fh+var_44], eax
0x180032b75  lea     rdx, [rbp+4Fh+var_40]
0x180032b79  mov     eax, [rbp+4Fh+var_80.bottom]
0x180032b7c  mov     [rsp+0E0h+var_B0], eax
0x180032b80  mov     eax, [rbp+4Fh+var_80.right]
0x180032b83  mov     [rsp+0E0h+var_B8], eax
0x180032b87  call    ?DrawImage@Graphics@Gdiplus@@QEAA?AW4Status@2@PEAVImage@2@AEBVRect@2@HHHHW4Unit@2@PEBVImageAttributes@2@P6AHPEAX@Z4@Z; Gdiplus::Graphics::DrawImage(Gdiplus::Image *,Gdiplus::Rect const &,int,int,int,int,Gdiplus::Unit,Gdiplus::ImageAttributes const *,int (*)(void *),void *)
0x180032b8c  mov     rcx, [rbp+4Fh+var_70]
0x180032b90  call    cs:__imp_GdipDeleteGraphics
0x180032b96  mov     rcx, [rbp+4Fh+var_60]
0x180032b9a  call    cs:__imp_GdipDeleteGraphics
0x180032ba0  mov     rcx, [rbp+4Fh+var_38]
0x180032ba4  call    cs:__imp_GdipDisposeImage
0x180032baa  add     rsp, 0C0h
0x180032bb1  pop     r14
0x180032bb3  pop     rdi
0x180032bb4  pop     rsi
0x180032bb5  pop     rbx
0x180032bb6  pop     rbp
0x180032bb7  retn
```
