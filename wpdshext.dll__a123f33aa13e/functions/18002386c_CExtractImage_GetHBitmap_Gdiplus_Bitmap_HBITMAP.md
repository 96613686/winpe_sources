# CExtractImage::_GetHBitmap(Gdiplus::Bitmap *,HBITMAP__ * *)

- ea: `0x18002386c`
- end: `0x180023b42`
- name: `?_GetHBitmap@CExtractImage@@AEAAJPEAVBitmap@Gdiplus@@PEAPEAUHBITMAP__@@@Z`
- size: `726`
- prototype: `int(CExtractImage *__hidden this, struct Gdiplus::Bitmap *, HBITMAP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180012cc0`

## callees

- `0x18002386c`
- `0x1800248ac`
- `0x1800273d4`
- `0x1800296dc`
- `0x18002ebf8`
- `0x18002ec80`
- `0x18002ed60`
- `0x18002ff5c`
- `0x18005b810`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800238c4`
- `GDI32!DeleteObject` at `0x1800238c4`
- `GDI32!GetDeviceCaps` at `0x1800238e5`
- `GDI32!GetDeviceCaps` at `0x1800238e5`
- `GDI32!DeleteDC` at `0x1800238fb`
- `GDI32!DeleteDC` at `0x1800238fb`
- `GDI32!CreateCompatibleDC` at `0x1800238cf`
- `GDI32!CreateCompatibleDC` at `0x1800238cf`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180023a99`
- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x180023a99`
- `gdiplus!GdipDrawImageRect` at `0x180023a84`
- `gdiplus!GdipDrawImageRect` at `0x180023a84`
- `gdiplus!GdipCreateBitmapFromGraphics` at `0x180023a22`
- `gdiplus!GdipCreateBitmapFromGraphics` at `0x180023a22`
- `gdiplus!GdipDeleteGraphics` at `0x180023a00`
- `gdiplus!GdipDeleteGraphics` at `0x180023aa3`
- `gdiplus!GdipDeleteGraphics` at `0x180023ab5`
- `gdiplus!GdipDeleteGraphics` at `0x180023a00`
- `gdiplus!GdipDeleteGraphics` at `0x180023aa3`
- `gdiplus!GdipDeleteGraphics` at `0x180023ab5`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180023987`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180023a37`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180023987`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180023a37`
- `gdiplus!GdipDisposeImage` at `0x180023aac`
- `gdiplus!GdipDisposeImage` at `0x180023aac`

## pseudocode

```c
__int64 __fastcall CExtractImage::_GetHBitmap(CExtractImage *this, struct Gdiplus::Bitmap *a2, HBITMAP *a3)
{
  unsigned int v6; // ebx
  unsigned int SysGdiplusColor; // r14d
  HDC CompatibleDC; // rax
  HDC v9; // r15
  unsigned __int8 v10; // dl
  int v11; // ecx
  float Width; // xmm9_4
  int Height; // eax
  float v14; // xmm1_4
  __m128i v15; // xmm0
  __int64 v16; // rcx
  float v17; // xmm6_4
  float v18; // xmm8_4
  float v19; // xmm6_4
  float v20; // xmm8_4
  int v21; // eax
  bool v22; // zf
  __int64 v23; // r12
  int v24; // esi
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r15
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v33; // [rsp+38h] [rbp-39h] BYREF
  int v34; // [rsp+40h] [rbp-31h]
  Image v35[8]; // [rsp+48h] [rbp-29h] BYREF
  __int64 v36; // [rsp+50h] [rbp-21h]
  __int64 v37; // [rsp+E0h] [rbp+6Fh] BYREF
  __int64 v38; // [rsp+F0h] [rbp+7Fh]

  if ( a2 && a3 )
  {
    v6 = 0;
    SysGdiplusColor = 0xFFFFFF;
    if ( *a3 )
    {
      DeleteObject(*a3);
      *a3 = 0;
    }
    CompatibleDC = CreateCompatibleDC(0);
    v9 = CompatibleDC;
    if ( CompatibleDC )
    {
      if ( GetDeviceCaps(CompatibleDC, 12) < 32 )
        SysGdiplusColor = GetSysGdiplusColor(v11, v10);
      DeleteDC(v9);
    }
    if ( (*((_DWORD *)this + 6) & 0x100) == 0 )
    {
      LODWORD(v37) = SysGdiplusColor;
      Gdiplus::Bitmap::GetHBITMAP(a2, &v37, a3);
      return v6;
    }
    Width = (float)(int)Gdiplus::Image::GetWidth(a2);
    Height = Gdiplus::Image::GetHeight(a2);
    if ( Width <= 0.0 || (v14 = (float)Height, (float)Height <= 0.0) )
    {
      v24 = 0;
      v6 = -2147467259;
    }
    else
    {
      v15 = _mm_cvtsi32_si128(*((_DWORD *)this + 4));
      v16 = *((_QWORD *)a2 + 1);
      v17 = (float)*((int *)this + 3);
      v37 = 0;
      v18 = fminf(v17 / Width, _mm_cvtepi32_ps(v15).m128_f32[0] / v14);
      v19 = v18 * v14;
      v20 = v18 * Width;
      v21 = ((__int64 (__fastcall *)(__int64, __int64 *))GdipGetImageGraphicsContext)(v16, &v37);
      v22 = (*((_BYTE *)this + 24) & 0x40) == 0;
      v23 = v37;
      v34 = v21;
      v33 = v37;
      if ( v22 )
      {
        v26 = *((unsigned int *)this + 4);
        v27 = *((unsigned int *)this + 3);
        v28 = v37;
        v37 = 0;
        GdipCreateBitmapFromGraphics(v27, v26, v28, &v37);
        v29 = v37;
        v30 = v37;
        v37 = 0;
        GdipGetImageGraphicsContext(v30, &v37);
        v31 = *((_QWORD *)a2 + 1);
        v38 = v37;
        v24 = GdipDrawImageRect(v37, v31);
        if ( !v24 )
          GdipCreateHBITMAPFromBitmap(v29, a3, SysGdiplusColor);
        GdipDeleteGraphics(v38);
        v25 = v29;
      }
      else
      {
        Gdiplus::Bitmap::Bitmap((Gdiplus::Bitmap *)v35, (int)v20, (int)v19, (struct Gdiplus::Graphics *)&v33);
        Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v33, (struct Image *)v35);
        v24 = Gdiplus::Graphics::DrawImage(&v33, a2);
        if ( !v24 )
        {
          LODWORD(v37) = SysGdiplusColor;
          Gdiplus::Bitmap::GetHBITMAP(v35, &v37, a3);
        }
        GdipDeleteGraphics(v33);
        v25 = v36;
      }
      GdipDisposeImage(v25);
      GdipDeleteGraphics(v23);
    }
    if ( v24 )
    {
      v6 = -2147467259;
    }
    else if ( (v6 & 0x80000000) == 0 )
    {
      return v6;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_2bf1e1e543723493952e6379efc1215e_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18002386c  mov     rax, rsp
0x18002386f  mov     [rax+8], rbx
0x180023873  push    rbp
0x180023874  push    rsi
0x180023875  push    rdi
0x180023876  push    r12
0x180023878  push    r13
0x18002387a  push    r14
0x18002387c  push    r15
0x18002387e  lea     rbp, [rax-5Fh]
0x180023882  sub     rsp, 90h
0x180023889  movaps  xmmword ptr [rax-48h], xmm6
0x18002388d  mov     rdi, r8
0x180023890  movaps  xmmword ptr [rax-58h], xmm8
0x180023895  mov     rsi, rdx
0x180023898  movaps  xmmword ptr [rax-68h], xmm9
0x18002389d  mov     r13, rcx
0x1800238a0  test    rdx, rdx
0x1800238a3  jnz     short loc_1800238AF
0x1800238a5  mov     ebx, 80070057h
0x1800238aa  jmp     loc_180023AD3
0x1800238af  test    rdi, rdi
0x1800238b2  jz      short loc_1800238A5
0x1800238b4  mov     rcx, [r8]; ho
0x1800238b7  xor     ebx, ebx
0x1800238b9  mov     r14d, 0FFFFFFh
0x1800238bf  test    rcx, rcx
0x1800238c2  jz      short loc_1800238CD
0x1800238c4  call    cs:__imp_DeleteObject
0x1800238ca  mov     [rdi], rbx
0x1800238cd  xor     ecx, ecx; hdc
0x1800238cf  call    cs:__imp_CreateCompatibleDC
0x1800238d5  mov     r15, rax
0x1800238d8  test    rax, rax
0x1800238db  jz      short loc_180023901
0x1800238dd  mov     edx, 0Ch; index
0x1800238e2  mov     rcx, rax; hdc
0x1800238e5  call    cs:__imp_GetDeviceCaps
0x1800238eb  cmp     eax, 20h ; ' '
0x1800238ee  jge     short loc_1800238F8
0x1800238f0  call    ?GetSysGdiplusColor@@YAKHE@Z; GetSysGdiplusColor(int,uchar)
0x1800238f5  mov     r14d, eax
0x1800238f8  mov     rcx, r15; hdc
0x1800238fb  call    cs:__imp_DeleteDC
0x180023901  test    dword ptr [r13+18h], 100h
0x180023909  mov     rcx, rsi; this
0x18002390c  jz      loc_180023B06
0x180023912  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180023917  mov     eax, eax
0x180023919  xorps   xmm9, xmm9
0x18002391d  mov     rcx, rsi; this
0x180023920  cvtsi2ss xmm9, rax
0x180023925  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x18002392a  comiss  xmm9, cs:__real@00000000
0x180023932  jbe     loc_180023ABD
0x180023938  mov     eax, eax
0x18002393a  xorps   xmm1, xmm1
0x18002393d  cvtsi2ss xmm1, rax
0x180023942  comiss  xmm1, cs:__real@00000000
0x180023949  jbe     loc_180023ABD
0x18002394f  movd    xmm6, dword ptr [r13+0Ch]
0x180023955  lea     rdx, [rbp+57h+arg_8]
0x180023959  movd    xmm0, dword ptr [r13+10h]
0x18002395f  mov     rcx, [rsi+8]
0x180023963  cvtdq2ps xmm6, xmm6
0x180023966  mov     [rbp+57h+arg_8], rbx
0x18002396a  cvtdq2ps xmm0, xmm0
0x18002396d  divss   xmm6, xmm9
0x180023972  divss   xmm0, xmm1
0x180023976  minss   xmm6, xmm0
0x18002397a  movaps  xmm8, xmm6
0x18002397e  mulss   xmm6, xmm1
0x180023982  mulss   xmm8, xmm9
0x180023987  call    cs:__imp_GdipGetImageGraphicsContext
0x18002398d  test    byte ptr [r13+18h], 40h
0x180023992  mov     r12, [rbp+57h+arg_8]
0x180023996  mov     [rbp+57h+var_88], eax
0x180023999  mov     [rbp+57h+var_90], r12
0x18002399d  jz      short loc_180023A0F
0x18002399f  cvttss2si r8d, xmm6; int
0x1800239a4  lea     r9, [rbp+57h+var_90]; struct Gdiplus::Graphics *
0x1800239a8  lea     rcx, [rbp+57h+var_80]; this
0x1800239ac  cvttss2si edx, xmm8; int
0x1800239b1  call    ??0Bitmap@Gdiplus@@QEAA@HHPEAVGraphics@1@@Z; Gdiplus::Bitmap::Bitmap(int,int,Gdiplus::Graphics *)
0x1800239b6  lea     rdx, [rbp+57h+var_80]; struct Image *
0x1800239ba  lea     rcx, [rbp+57h+var_90]; this
0x1800239be  call    ??0Graphics@Gdiplus@@QEAA@PEAVImage@1@@Z; Gdiplus::Graphics::Graphics(Gdiplus::Image *)
0x1800239c3  movss   [rsp+0C0h+var_98], xmm6
0x1800239c9  lea     rcx, [rbp+57h+var_90]
0x1800239cd  xorps   xmm3, xmm3
0x1800239d0  movss   [rsp+0C0h+var_A0], xmm8
0x1800239d7  xorps   xmm2, xmm2
0x1800239da  mov     rdx, rsi
0x1800239dd  call    ?DrawImage@Graphics@Gdiplus@@QEAA?AW4Status@2@PEAVImage@2@MMMM@Z; Gdiplus::Graphics::DrawImage(Gdiplus::Image *,float,float,float,float)
0x1800239e2  mov     esi, eax
0x1800239e4  test    eax, eax
0x1800239e6  jnz     short loc_1800239FC
0x1800239e8  mov     r8, rdi
0x1800239eb  mov     dword ptr [rbp+57h+arg_8], r14d
0x1800239ef  lea     rdx, [rbp+57h+arg_8]
0x1800239f3  lea     rcx, [rbp+57h+var_80]
0x1800239f7  call    ?GetHBITMAP@Bitmap@Gdiplus@@QEAA?AW4Status@2@AEBVColor@2@PEAPEAUHBITMAP__@@@Z; Gdiplus::Bitmap::GetHBITMAP(Gdiplus::Color const &,HBITMAP__ * *)
0x1800239fc  mov     rcx, [rbp+57h+var_90]
0x180023a00  call    cs:__imp_GdipDeleteGraphics
0x180023a06  mov     rcx, [rbp+57h+var_78]
0x180023a0a  jmp     loc_180023AAC
0x180023a0f  mov     edx, [r13+10h]
0x180023a13  lea     r9, [rbp+57h+arg_8]
0x180023a17  mov     ecx, [r13+0Ch]
0x180023a1b  mov     r8, r12
0x180023a1e  mov     [rbp+57h+arg_8], rbx
0x180023a22  call    cs:__imp_GdipCreateBitmapFromGraphics
0x180023a28  mov     r15, [rbp+57h+arg_8]
0x180023a2c  lea     rdx, [rbp+57h+arg_8]
0x180023a30  mov     rcx, r15
0x180023a33  mov     [rbp+57h+arg_8], rbx
0x180023a37  call    cs:__imp_GdipGetImageGraphicsContext
0x180023a3d  mov     rax, [rbp+57h+arg_8]
0x180023a41  movd    xmm3, dword ptr [r13+10h]
0x180023a47  mov     rcx, rax
0x180023a4a  movd    xmm2, dword ptr [r13+0Ch]
0x180023a50  mov     rdx, [rsi+8]
0x180023a54  cvtdq2ps xmm3, xmm3
0x180023a57  mov     [rbp+57h+arg_18], rax
0x180023a5b  cvtdq2ps xmm2, xmm2
0x180023a5e  subss   xmm3, xmm6
0x180023a62  movss   [rsp+0C0h+var_98], xmm6
0x180023a68  subss   xmm2, xmm8
0x180023a6d  movss   [rsp+0C0h+var_A0], xmm8
0x180023a74  mulss   xmm3, cs:__real@3f000000
0x180023a7c  mulss   xmm2, cs:__real@3f000000
0x180023a84  call    cs:__imp_GdipDrawImageRect
0x180023a8a  mov     esi, eax
0x180023a8c  test    eax, eax
0x180023a8e  jnz     short loc_180023A9F
0x180023a90  mov     r8d, r14d
0x180023a93  mov     rdx, rdi
0x180023a96  mov     rcx, r15
0x180023a99  call    cs:__imp_GdipCreateHBITMAPFromBitmap
0x180023a9f  mov     rcx, [rbp+57h+arg_18]
0x180023aa3  call    cs:__imp_GdipDeleteGraphics
0x180023aa9  mov     rcx, r15
0x180023aac  call    cs:__imp_GdipDisposeImage
0x180023ab2  mov     rcx, r12
0x180023ab5  call    cs:__imp_GdipDeleteGraphics
0x180023abb  jmp     short loc_180023AC4
0x180023abd  xor     esi, esi
0x180023abf  mov     ebx, 80004005h
0x180023ac4  test    esi, esi
0x180023ac6  jz      short loc_180023ACF
0x180023ac8  mov     ebx, 80004005h
0x180023acd  jmp     short loc_180023AD3
0x180023acf  test    ebx, ebx
0x180023ad1  jns     short loc_180023B16
0x180023ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ada  lea     rax, WPP_GLOBAL_Control
0x180023ae1  cmp     rcx, rax
0x180023ae4  jz      short loc_180023B16
0x180023ae6  test    byte ptr [rcx+1Ch], 2
0x180023aea  jz      short loc_180023B16
0x180023aec  mov     rcx, [rcx+10h]
0x180023af0  lea     r8, WPP_2bf1e1e543723493952e6379efc1215e_Traceguids
0x180023af7  mov     edx, 12h
0x180023afc  mov     r9d, ebx
0x180023aff  call    WPP_SF_d
0x180023b04  jmp     short loc_180023B16
0x180023b06  mov     r8, rdi
0x180023b09  mov     dword ptr [rbp+57h+arg_8], r14d
0x180023b0d  lea     rdx, [rbp+57h+arg_8]
0x180023b11  call    ?GetHBITMAP@Bitmap@Gdiplus@@QEAA?AW4Status@2@AEBVColor@2@PEAPEAUHBITMAP__@@@Z; Gdiplus::Bitmap::GetHBITMAP(Gdiplus::Color const &,HBITMAP__ * *)
0x180023b16  lea     r11, [rsp+0C0h+var_30]
0x180023b1e  mov     eax, ebx
0x180023b20  mov     rbx, [r11+40h]
0x180023b24  movaps  xmm6, xmmword ptr [r11-10h]
0x180023b29  movaps  xmm8, xmmword ptr [r11-20h]
0x180023b2e  movaps  xmm9, xmmword ptr [r11-30h]
0x180023b33  mov     rsp, r11
0x180023b36  pop     r15
0x180023b38  pop     r14
0x180023b3a  pop     r13
0x180023b3c  pop     r12
0x180023b3e  pop     rdi
0x180023b3f  pop     rsi
0x180023b40  pop     rbp
0x180023b41  retn
```
