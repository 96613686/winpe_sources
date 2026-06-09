# CAnalogClock::_ClockPaint(HDC__ *)

- ea: `0x180023a70`
- end: `0x180023de4`
- name: `?_ClockPaint@CAnalogClock@@AEAAXPEAUHDC__@@@Z`
- size: `884`
- prototype: `void __fastcall(CAnalogClock *__hidden this, HDC)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180023dec`
- `0x1800244d0`

## callees

- `0x180023a70`
- `0x1800240ac`
- `0x1800240fc`
- `0x18002a010`

## import_xrefs

- `gdiplus!GdipGetImageHeight` at `0x180023c67`
- `gdiplus!GdipGetImageHeight` at `0x180023c67`
- `gdiplus!GdipDeleteGraphics` at `0x180023dc3`
- `gdiplus!GdipDeleteGraphics` at `0x180023dcc`
- `gdiplus!GdipDeleteGraphics` at `0x180023dc3`
- `gdiplus!GdipDeleteGraphics` at `0x180023dcc`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180023b4a`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180023b4a`
- `gdiplus!GdipCreateFromHDC` at `0x180023aaf`
- `gdiplus!GdipCreateFromHDC` at `0x180023aaf`
- `gdiplus!GdipAddPathEllipseI` at `0x180023bfd`
- `gdiplus!GdipAddPathEllipseI` at `0x180023bfd`
- `gdiplus!GdipDeletePath` at `0x180023cea`
- `gdiplus!GdipDeletePath` at `0x180023cea`
- `gdiplus!GdipCreatePath` at `0x180023be0`
- `gdiplus!GdipCreatePath` at `0x180023be0`
- `gdiplus!GdipSetCompositingMode` at `0x180023b78`
- `gdiplus!GdipSetCompositingMode` at `0x180023b78`
- `gdiplus!GdipSetCompositingQuality` at `0x180023b8f`
- `gdiplus!GdipSetCompositingQuality` at `0x180023b8f`
- `gdiplus!GdipSetSmoothingMode` at `0x180023ba0`
- `gdiplus!GdipSetSmoothingMode` at `0x180023ba0`
- `gdiplus!GdipCreateRegionPath` at `0x180023c1b`
- `gdiplus!GdipCreateRegionPath` at `0x180023c1b`
- `gdiplus!GdipBitmapSetPixel` at `0x180023ca5`
- `gdiplus!GdipBitmapSetPixel` at `0x180023ca5`
- `gdiplus!GdipGraphicsClear` at `0x180023b68`
- `gdiplus!GdipGraphicsClear` at `0x180023b68`
- `gdiplus!GdipGetImageWidth` at `0x180023c4e`
- `gdiplus!GdipGetImageWidth` at `0x180023c4e`
- `gdiplus!GdipGetRegionHRgn` at `0x180023c38`
- `gdiplus!GdipGetRegionHRgn` at `0x180023c38`
- `gdiplus!GdipCloneBitmapAreaI` at `0x180023aeb`
- `gdiplus!GdipCloneBitmapAreaI` at `0x180023aeb`
- `gdiplus!GdipAlloc` at `0x180023b02`
- `gdiplus!GdipAlloc` at `0x180023b02`
- `gdiplus!GdipDeleteRegion` at `0x180023cd9`
- `gdiplus!GdipDeleteRegion` at `0x180023cd9`
- `gdiplus!GdipDisposeImage` at `0x180023b2c`
- `gdiplus!GdipDisposeImage` at `0x180023b2c`
- `GDI32!PtInRegion` at `0x180023c8f`
- `GDI32!PtInRegion` at `0x180023c8f`
- `GDI32!DeleteObject` at `0x180023cd0`
- `GDI32!DeleteObject` at `0x180023cd0`

## pseudocode

```c
void __fastcall CAnalogClock::_ClockPaint(CAnalogClock *this, HDC a2)
{
  int v3; // eax
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r9
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  int ImageGraphicsContext; // eax
  unsigned int *v13; // rdx
  int v14; // esi
  __int64 v15; // r14
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // r8
  _DWORD *v21; // rsi
  int v22; // eax
  __int64 v23; // r9
  int v24; // eax
  __int64 v25; // rsi
  __int64 v26; // rcx
  HRGN v27; // r15
  int ImageWidth; // eax
  __int64 v29; // rcx
  int ImageHeight; // eax
  int v31; // r12d
  int v32; // r14d
  int i; // esi
  int v34; // eax
  int v35; // eax
  __int64 v36; // [rsp+28h] [rbp-41h]
  __int64 v37; // [rsp+40h] [rbp-29h] BYREF
  __int64 v38; // [rsp+48h] [rbp-21h] BYREF
  HRGN hrgn; // [rsp+50h] [rbp-19h] BYREF
  __int64 v40; // [rsp+58h] [rbp-11h]
  __int64 v41; // [rsp+60h] [rbp-9h] BYREF
  int v42; // [rsp+68h] [rbp-1h]
  __int64 v43; // [rsp+70h] [rbp+7h] BYREF
  int v44; // [rsp+78h] [rbp+Fh]
  __int64 v45; // [rsp+80h] [rbp+17h] BYREF
  int v46; // [rsp+88h] [rbp+1Fh]
  __int64 v47; // [rsp+D0h] [rbp+67h] BYREF
  int v48; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v49; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( *((_DWORD *)this + 22) && *((_QWORD *)this + 4) )
  {
    v49 = 0;
    v3 = GdipCreateFromHDC(a2, &v49);
    v4 = *((_QWORD *)this + 4);
    v5 = v49;
    v6 = *((unsigned int *)this + 21);
    v7 = *((unsigned int *)this + 20);
    v46 = v3;
    v36 = *(_QWORD *)(v4 + 8);
    v45 = v49;
    v37 = 0;
    v8 = GdipCloneBitmapAreaI(0, 0, v7, v6, 0, v36, &v37);
    if ( v8 )
    {
      *(_DWORD *)(v4 + 16) = v8;
LABEL_47:
      GdipDeleteGraphics(v5);
      return;
    }
    v9 = GdipAlloc(24);
    if ( v9 )
    {
      v10 = v37;
      *(_QWORD *)v9 = &Gdiplus::Image::`vftable';
      *(_QWORD *)(v9 + 8) = v10;
      *(_DWORD *)(v9 + 16) = 0;
    }
    else
    {
      GdipDisposeImage(v37);
      v9 = 0;
    }
    if ( !v9 )
      goto LABEL_47;
    v11 = *(_QWORD *)(v9 + 8);
    v47 = 0;
    ImageGraphicsContext = GdipGetImageGraphicsContext(v11, &v47);
    v13 = (unsigned int *)*((_QWORD *)this + 8);
    v14 = ImageGraphicsContext;
    v15 = v47;
    v41 = v47;
    if ( v13 )
    {
      v16 = GdipGraphicsClear(v47, *v13);
      if ( v16 )
        v14 = v16;
    }
    v17 = GdipSetCompositingMode(v15, 0);
    if ( v17 )
      v14 = v17;
    v18 = GdipSetCompositingQuality(v15, 2);
    if ( v18 )
      v14 = v18;
    v19 = GdipSetSmoothingMode(v15, 2);
    v20 = *((_QWORD *)this + 4);
    if ( v19 )
      v14 = v19;
    v42 = v14;
    if ( (unsigned int)CAnalogClock::_DrawClockImage(this, &v41, v20) )
      goto LABEL_45;
    v21 = (_DWORD *)((char *)this + 132);
    if ( *((_DWORD *)this + 33) )
    {
      v43 = 0;
      v22 = GdipCreatePath(0, &v43);
      v23 = *((unsigned int *)this + 20);
      v44 = v22;
      v24 = GdipAddPathEllipseI(v43, 0, 0, v23, *((_DWORD *)this + 21));
      if ( v24 )
      {
        v44 = v24;
      }
      else
      {
        v38 = 0;
        GdipCreateRegionPath(v43, &v38);
        v25 = v38;
        v40 = v38;
        hrgn = 0;
        GdipGetRegionHRgn(v38, v41, &hrgn);
        v26 = *(_QWORD *)(v9 + 8);
        v27 = hrgn;
        LODWORD(v47) = 0;
        ImageWidth = GdipGetImageWidth(v26, &v47);
        if ( ImageWidth )
          *(_DWORD *)(v9 + 16) = ImageWidth;
        v29 = *(_QWORD *)(v9 + 8);
        v48 = 0;
        ImageHeight = GdipGetImageHeight(v29, &v48);
        if ( ImageHeight )
          *(_DWORD *)(v9 + 16) = ImageHeight;
        v31 = v48;
        v32 = 0;
        if ( v48 > 0 )
        {
          do
          {
            for ( i = 0; i < (int)v47; ++i )
            {
              if ( !PtInRegion(v27, i, v32) )
              {
                v34 = GdipBitmapSetPixel(*(_QWORD *)(v9 + 8), (unsigned int)i, (unsigned int)v32, 0);
                if ( v34 )
                  *(_DWORD *)(v9 + 16) = v34;
              }
            }
            ++v32;
          }
          while ( v32 < v31 );
          v25 = v40;
        }
        if ( v27 )
          DeleteObject(v27);
        GdipDeleteRegion(v25);
        v21 = (_DWORD *)((char *)this + 132);
      }
      GdipDeletePath(v43);
    }
    if ( (unsigned int)CAnalogClock::_DrawHand(
                         this,
                         &v41,
                         *((unsigned int *)this + 24),
                         (char *)this + 168,
                         *((_QWORD *)this + 7)) )
      goto LABEL_45;
    v35 = CAnalogClock::_DrawHand(
            this,
            &v41,
            (unsigned int)(*((_DWORD *)this + 24) / 2 + 5 * *((_DWORD *)this + 23)),
            (char *)this + 156,
            *((_QWORD *)this + 7));
    if ( !*v21 && !*((_DWORD *)this + 31) )
    {
      if ( v35 )
        goto LABEL_45;
      v35 = CAnalogClock::_DrawHand(this, &v41, *((unsigned int *)this + 25), (char *)this + 180, *((_QWORD *)this + 6));
    }
    if ( !v35 )
    {
      CAnalogClock::_DrawClockImage(this, &v41, *((_QWORD *)this + 5));
      CAnalogClock::_DrawClockImage(this, &v45, v9);
      v5 = v45;
LABEL_46:
      (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
      GdipDeleteGraphics(v41);
      goto LABEL_47;
    }
LABEL_45:
    v5 = v49;
    goto LABEL_46;
  }
}

```

## disassembly

```asm
0x180023a70  push    rbp
0x180023a72  push    rbx
0x180023a73  push    rsi
0x180023a74  push    rdi
0x180023a75  push    r12
0x180023a77  push    r14
0x180023a79  push    r15
0x180023a7b  lea     rbp, [rsp-27h]
0x180023a80  sub     rsp, 90h
0x180023a87  xor     r12d, r12d
0x180023a8a  mov     rax, rdx
0x180023a8d  mov     rdi, rcx
0x180023a90  cmp     [rcx+58h], r12d
0x180023a94  jz      loc_180023DD2
0x180023a9a  cmp     [rcx+20h], r12
0x180023a9e  jz      loc_180023DD2
0x180023aa4  lea     rdx, [rbp+57h+arg_18]
0x180023aa8  mov     [rbp+57h+arg_18], r12
0x180023aac  mov     rcx, rax
0x180023aaf  call    cs:__imp_GdipCreateFromHDC
0x180023ab5  mov     rbx, [rdi+20h]
0x180023ab9  xor     edx, edx
0x180023abb  mov     rsi, [rbp+57h+arg_18]
0x180023abf  xor     ecx, ecx
0x180023ac1  mov     r9d, [rdi+54h]
0x180023ac5  mov     r8d, [rdi+50h]
0x180023ac9  mov     [rbp+57h+var_38], eax
0x180023acc  lea     rax, [rbp+57h+var_80]
0x180023ad0  mov     [rsp+0C0h+var_90], rax
0x180023ad5  mov     rax, [rbx+8]
0x180023ad9  mov     [rsp+0C0h+var_98], rax
0x180023ade  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x180023ae3  mov     [rbp+57h+var_40], rsi
0x180023ae7  mov     [rbp+57h+var_80], r12
0x180023aeb  call    cs:__imp_GdipCloneBitmapAreaI
0x180023af1  test    eax, eax
0x180023af3  jz      short loc_180023AFD
0x180023af5  mov     [rbx+10h], eax
0x180023af8  jmp     loc_180023DC9
0x180023afd  mov     ecx, 18h
0x180023b02  call    cs:__imp_GdipAlloc
0x180023b08  mov     rbx, rax
0x180023b0b  test    rax, rax
0x180023b0e  jz      short loc_180023B28
0x180023b10  mov     rax, [rbp+57h+var_80]
0x180023b14  lea     rcx, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180023b1b  mov     [rbx], rcx
0x180023b1e  mov     [rbx+8], rax
0x180023b22  mov     [rbx+10h], r12d
0x180023b26  jmp     short loc_180023B35
0x180023b28  mov     rcx, [rbp+57h+var_80]
0x180023b2c  call    cs:__imp_GdipDisposeImage
0x180023b32  mov     rbx, r12
0x180023b35  test    rbx, rbx
0x180023b38  jz      loc_180023DC9
0x180023b3e  mov     rcx, [rbx+8]
0x180023b42  lea     rdx, [rbp+57h+arg_0]
0x180023b46  mov     [rbp+57h+arg_0], r12
0x180023b4a  call    cs:__imp_GdipGetImageGraphicsContext
0x180023b50  mov     rdx, [rdi+40h]
0x180023b54  mov     esi, eax
0x180023b56  mov     r14, [rbp+57h+arg_0]
0x180023b5a  mov     [rbp+57h+var_60], r14
0x180023b5e  test    rdx, rdx
0x180023b61  jz      short loc_180023B73
0x180023b63  mov     edx, [rdx]
0x180023b65  mov     rcx, r14
0x180023b68  call    cs:__imp_GdipGraphicsClear
0x180023b6e  test    eax, eax
0x180023b70  cmovnz  esi, eax
0x180023b73  xor     edx, edx
0x180023b75  mov     rcx, r14
0x180023b78  call    cs:__imp_GdipSetCompositingMode
0x180023b7e  mov     r15d, 2
0x180023b84  mov     rcx, r14
0x180023b87  test    eax, eax
0x180023b89  mov     edx, r15d
0x180023b8c  cmovnz  esi, eax
0x180023b8f  call    cs:__imp_GdipSetCompositingQuality
0x180023b95  mov     edx, r15d
0x180023b98  mov     rcx, r14
0x180023b9b  test    eax, eax
0x180023b9d  cmovnz  esi, eax
0x180023ba0  call    cs:__imp_GdipSetSmoothingMode
0x180023ba6  mov     r8, [rdi+20h]
0x180023baa  lea     rdx, [rbp+57h+var_60]
0x180023bae  test    eax, eax
0x180023bb0  mov     rcx, rdi
0x180023bb3  cmovnz  esi, eax
0x180023bb6  mov     [rbp+57h+var_58], esi
0x180023bb9  call    ?_DrawClockImage@CAnalogClock@@AEAA?AW4Status@Gdiplus@@PEAVGraphics@3@PEAVImage@3@@Z; CAnalogClock::_DrawClockImage(Gdiplus::Graphics *,Gdiplus::Image *)
0x180023bbe  test    eax, eax
0x180023bc0  jnz     loc_180023DA8
0x180023bc6  lea     rsi, [rdi+84h]
0x180023bcd  cmp     [rsi], r12d
0x180023bd0  jz      loc_180023CF0
0x180023bd6  lea     rdx, [rbp+57h+var_50]
0x180023bda  mov     [rbp+57h+var_50], r12
0x180023bde  xor     ecx, ecx
0x180023be0  call    cs:__imp_GdipCreatePath
0x180023be6  mov     r9d, [rdi+50h]
0x180023bea  xor     r8d, r8d
0x180023bed  mov     rcx, [rbp+57h+var_50]
0x180023bf1  xor     edx, edx
0x180023bf3  mov     [rbp+57h+var_48], eax
0x180023bf6  mov     eax, [rdi+54h]
0x180023bf9  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180023bfd  call    cs:__imp_GdipAddPathEllipseI
0x180023c03  test    eax, eax
0x180023c05  jz      short loc_180023C0F
0x180023c07  mov     [rbp+57h+var_48], eax
0x180023c0a  jmp     loc_180023CE6
0x180023c0f  mov     rcx, [rbp+57h+var_50]
0x180023c13  lea     rdx, [rbp+57h+var_78]
0x180023c17  mov     [rbp+57h+var_78], r12
0x180023c1b  call    cs:__imp_GdipCreateRegionPath
0x180023c21  mov     rsi, [rbp+57h+var_78]
0x180023c25  lea     r8, [rbp+57h+hrgn]
0x180023c29  mov     rdx, [rbp+57h+var_60]
0x180023c2d  mov     rcx, rsi
0x180023c30  mov     [rbp+57h+var_68], rsi
0x180023c34  mov     [rbp+57h+hrgn], r12
0x180023c38  call    cs:__imp_GdipGetRegionHRgn
0x180023c3e  mov     rcx, [rbx+8]
0x180023c42  lea     rdx, [rbp+57h+arg_0]
0x180023c46  mov     r15, [rbp+57h+hrgn]
0x180023c4a  mov     dword ptr [rbp+57h+arg_0], r12d
0x180023c4e  call    cs:__imp_GdipGetImageWidth
0x180023c54  test    eax, eax
0x180023c56  jz      short loc_180023C5B
0x180023c58  mov     [rbx+10h], eax
0x180023c5b  mov     rcx, [rbx+8]
0x180023c5f  lea     rdx, [rbp+57h+arg_10]
0x180023c63  mov     [rbp+57h+arg_10], r12d
0x180023c67  call    cs:__imp_GdipGetImageHeight
0x180023c6d  test    eax, eax
0x180023c6f  jz      short loc_180023C74
0x180023c71  mov     [rbx+10h], eax
0x180023c74  mov     r12d, [rbp+57h+arg_10]
0x180023c78  xor     r14d, r14d
0x180023c7b  test    r12d, r12d
0x180023c7e  jle     short loc_180023CC5
0x180023c80  xor     esi, esi
0x180023c82  cmp     dword ptr [rbp+57h+arg_0], esi
0x180023c85  jle     short loc_180023CB9
0x180023c87  mov     r8d, r14d; y
0x180023c8a  mov     edx, esi; x
0x180023c8c  mov     rcx, r15; hrgn
0x180023c8f  call    cs:__imp_PtInRegion
0x180023c95  test    eax, eax
0x180023c97  jnz     short loc_180023CB2
0x180023c99  mov     rcx, [rbx+8]
0x180023c9d  xor     r9d, r9d
0x180023ca0  mov     r8d, r14d
0x180023ca3  mov     edx, esi
0x180023ca5  call    cs:__imp_GdipBitmapSetPixel
0x180023cab  test    eax, eax
0x180023cad  jz      short loc_180023CB2
0x180023caf  mov     [rbx+10h], eax
0x180023cb2  inc     esi
0x180023cb4  cmp     esi, dword ptr [rbp+57h+arg_0]
0x180023cb7  jl      short loc_180023C87
0x180023cb9  inc     r14d
0x180023cbc  cmp     r14d, r12d
0x180023cbf  jl      short loc_180023C80
0x180023cc1  mov     rsi, [rbp+57h+var_68]
0x180023cc5  xor     r12d, r12d
0x180023cc8  test    r15, r15
0x180023ccb  jz      short loc_180023CD6
0x180023ccd  mov     rcx, r15; ho
0x180023cd0  call    cs:__imp_DeleteObject
0x180023cd6  mov     rcx, rsi
0x180023cd9  call    cs:__imp_GdipDeleteRegion
0x180023cdf  lea     rsi, [rdi+84h]
0x180023ce6  mov     rcx, [rbp+57h+var_50]
0x180023cea  call    cs:__imp_GdipDeletePath
0x180023cf0  mov     rax, [rdi+38h]
0x180023cf4  lea     r9, [rdi+0A8h]
0x180023cfb  mov     r8d, [rdi+60h]
0x180023cff  lea     rdx, [rbp+57h+var_60]
0x180023d03  mov     rcx, rdi
0x180023d06  mov     [rsp+0C0h+var_A0], rax
0x180023d0b  call    ?_DrawHand@CAnalogClock@@AEAA?AW4Status@Gdiplus@@PEAVGraphics@3@HAEBUClockHand@@PEAVPen@3@@Z; CAnalogClock::_DrawHand(Gdiplus::Graphics *,int,ClockHand const &,Gdiplus::Pen *)
0x180023d10  test    eax, eax
0x180023d12  jnz     loc_180023DA8
0x180023d18  mov     eax, [rdi+5Ch]
0x180023d1b  lea     r9, [rdi+9Ch]
0x180023d22  lea     ecx, [rax+rax*4]
0x180023d25  mov     eax, 2AAAAAABh
0x180023d2a  imul    dword ptr [rdi+60h]
0x180023d2d  mov     rax, [rdi+38h]
0x180023d31  sar     edx, 1
0x180023d33  mov     r8d, edx
0x180023d36  mov     [rsp+0C0h+var_A0], rax
0x180023d3b  add     edx, ecx
0x180023d3d  shr     r8d, 1Fh
0x180023d41  add     r8d, edx
0x180023d44  mov     rcx, rdi
0x180023d47  lea     rdx, [rbp+57h+var_60]
0x180023d4b  call    ?_DrawHand@CAnalogClock@@AEAA?AW4Status@Gdiplus@@PEAVGraphics@3@HAEBUClockHand@@PEAVPen@3@@Z; CAnalogClock::_DrawHand(Gdiplus::Graphics *,int,ClockHand const &,Gdiplus::Pen *)
0x180023d50  cmp     [rsi], r12d
0x180023d53  jnz     short loc_180023D7F
0x180023d55  cmp     [rdi+7Ch], r12d
0x180023d59  jnz     short loc_180023D7F
0x180023d5b  test    eax, eax
0x180023d5d  jnz     short loc_180023DA8
0x180023d5f  mov     rax, [rdi+30h]
0x180023d63  lea     r9, [rdi+0B4h]
0x180023d6a  mov     r8d, [rdi+64h]
0x180023d6e  lea     rdx, [rbp+57h+var_60]
0x180023d72  mov     rcx, rdi
0x180023d75  mov     [rsp+0C0h+var_A0], rax
0x180023d7a  call    ?_DrawHand@CAnalogClock@@AEAA?AW4Status@Gdiplus@@PEAVGraphics@3@HAEBUClockHand@@PEAVPen@3@@Z; CAnalogClock::_DrawHand(Gdiplus::Graphics *,int,ClockHand const &,Gdiplus::Pen *)
0x180023d7f  test    eax, eax
0x180023d81  jnz     short loc_180023DA8
0x180023d83  mov     r8, [rdi+28h]
0x180023d87  lea     rdx, [rbp+57h+var_60]
0x180023d8b  mov     rcx, rdi
0x180023d8e  call    ?_DrawClockImage@CAnalogClock@@AEAA?AW4Status@Gdiplus@@PEAVGraphics@3@PEAVImage@3@@Z; CAnalogClock::_DrawClockImage(Gdiplus::Graphics *,Gdiplus::Image *)
0x180023d93  mov     r8, rbx
0x180023d96  lea     rdx, [rbp+57h+var_40]
0x180023d9a  mov     rcx, rdi
0x180023d9d  call    ?_DrawClockImage@CAnalogClock@@AEAA?AW4Status@Gdiplus@@PEAVGraphics@3@PEAVImage@3@@Z; CAnalogClock::_DrawClockImage(Gdiplus::Graphics *,Gdiplus::Image *)
0x180023da2  mov     rsi, [rbp+57h+var_40]
0x180023da6  jmp     short loc_180023DAC
0x180023da8  mov     rsi, [rbp+57h+arg_18]
0x180023dac  mov     rax, [rbx]
0x180023daf  mov     edx, 1
0x180023db4  mov     rcx, rbx
0x180023db7  mov     rax, [rax]
0x180023dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dbf  mov     rcx, [rbp+57h+var_60]
0x180023dc3  call    cs:__imp_GdipDeleteGraphics
0x180023dc9  mov     rcx, rsi
0x180023dcc  call    cs:__imp_GdipDeleteGraphics
0x180023dd2  add     rsp, 90h
0x180023dd9  pop     r15
0x180023ddb  pop     r14
0x180023ddd  pop     r12
0x180023ddf  pop     rdi
0x180023de0  pop     rsi
0x180023de1  pop     rbx
0x180023de2  pop     rbp
0x180023de3  retn
```
