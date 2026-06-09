# CWmpDecoderFrame::CopyPixels(WICRect const *,uint,uint,_GUID *,WICBitmapTransformOptions,uint,uint,uchar *)

- ea: `0x180031850`
- end: `0x180032310`
- name: `?CopyPixels@CWmpDecoderFrame@@UEAAJPEBUWICRect@@IIPEAU_GUID@@W4WICBitmapTransformOptions@@IIPEAE@Z`
- size: `2752`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *this, const struct WICRect *, unsigned int, INT, struct _GUID *, WICBitmapTransformOptions, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800317f0`
- `0x180039e90`

## callees

- `0x180028f18`
- `0x18002b078`
- `0x18002dd70`
- `0x18002ddfc`
- `0x18002de30`
- `0x18002ded0`
- `0x18002df00`
- `0x18002e8bc`
- `0x180031850`
- `0x180032470`
- `0x180033ee0`
- `0x180035f6c`
- `0x180036420`
- `0x180037174`
- `0x180038fd0`
- `0x1800399a0`
- `0x180039c70`
- `0x18003c0a0`
- `0x18003e0d0`
- `0x18003e2f0`
- `0x180043e40`
- `0x180045010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180032162`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180032162`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800318d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800318d9`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::CopyPixels(
        CWmpDecoderFrame *this,
        const struct WICRect *a2,
        unsigned int a3,
        INT a4,
        struct _GUID *a5,
        WICBitmapTransformOptions a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int8 *a9)
{
  struct _GUID *v10; // r14
  unsigned __int8 *v12; // r8
  __int64 v14; // rax
  const struct WICRect *v15; // rax
  int PixelFormat; // ebx
  int v17; // r15d
  ULONGLONG v18; // r12
  INT Y; // esi
  int v20; // r13d
  CWmpDecoderFrame *v22; // rcx
  unsigned __int64 v23; // rax
  __int64 v24; // r9
  int v25; // r10d
  unsigned __int64 v26; // r11
  unsigned int v27; // r9d
  int v28; // r8d
  unsigned __int64 v29; // rcx
  unsigned __int64 PixelSize; // rax
  __int64 v31; // r9
  int v32; // r11d
  unsigned __int64 v33; // r11
  unsigned int v34; // r9d
  int v35; // r8d
  _OWORD *v36; // r8
  CWmpDecoderFrame *v37; // rbx
  __int128 v38; // xmm7
  struct IWICComponentFactory *WICFactory; // rax
  enum WICBitmapTransformOptions v40; // r13d
  struct _GUID v41; // xmm0
  __int64 v42; // rax
  ToneMapper *v43; // rcx
  struct IWICBitmapSource *v44; // rbx
  struct IWICComponentFactory *v45; // rax
  ToneMapper *v46; // rcx
  float *v47; // r15
  struct IWICBitmapSource *v48; // rbx
  float v49; // xmm6_4
  struct IWICComponentFactory *v50; // rax
  ULONGLONG v51; // rcx
  float v52; // xmm6_4
  __int64 v53; // r9
  const struct WICRect *v54; // rdx
  __int64 v55; // r8
  int v56; // eax
  struct _GUID v57; // xmm0
  __int64 v58; // rcx
  int v59; // eax
  unsigned int v60; // edx
  unsigned int v61; // r9d
  CWmpDecoderFrame *v62; // rcx
  int v63; // ecx
  ULONGLONG v64; // r12
  CWmpDecoderFrame *v65; // r15
  int v66; // ecx
  int v67; // esi
  INT Width; // r15d
  struct _GUID v69; // xmm0
  unsigned __int64 v70; // rax
  __int64 v71; // r9
  ULONGLONG *v72; // r15
  int v73; // r10d
  ULONGLONG v74; // rdx
  unsigned __int64 v75; // rax
  __int64 v76; // r9
  int v77; // r11d
  size_t v78; // r9
  size_t v79; // rbx
  void *v80; // rax
  unsigned int v81; // eax
  ULONGLONG v82; // r10
  INT v83; // r14d
  size_t v84; // rbx
  unsigned __int8 *v85; // r12
  unsigned int v86; // [rsp+38h] [rbp-D0h]
  unsigned __int8 *v87; // [rsp+48h] [rbp-C0h]
  unsigned int v88; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v89[2]; // [rsp+60h] [rbp-A8h] BYREF
  ULONGLONG pullResult; // [rsp+68h] [rbp-A0h] BYREF
  int Size; // [rsp+70h] [rbp-98h] BYREF
  unsigned int Size_4; // [rsp+74h] [rbp-94h]
  ULONGLONG Size_8[2]; // [rsp+78h] [rbp-90h] BYREF
  ULONGLONG ullMultiplicand; // [rsp+88h] [rbp-80h] BYREF
  int v95; // [rsp+90h] [rbp-78h]
  int v96; // [rsp+98h] [rbp-70h]
  WICRect v97; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int8 *v98; // [rsp+B8h] [rbp-50h]
  const struct WICRect *v99; // [rsp+C0h] [rbp-48h]
  ULONGLONG v100; // [rsp+C8h] [rbp-40h] BYREF
  ULONGLONG ullMultiplier; // [rsp+D0h] [rbp-38h] BYREF
  CWmpDecoderFrame *v102; // [rsp+D8h] [rbp-30h]
  __int64 v103; // [rsp+E0h] [rbp-28h] BYREF
  struct _GUID v104; // [rsp+E8h] [rbp-20h] BYREF

  v10 = a5;
  Size_4 = a7;
  v88 = a3;
  v12 = a9;
  v102 = (CWmpDecoderFrame *)((char *)this - 66328);
  v14 = *((_QWORD *)this + 52) + 24LL;
  v99 = a2;
  v89[0] = a4;
  v98 = a9;
  v103 = v14;
  if ( *(_BYTE *)(v14 + 48) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
    a2 = v99;
    v12 = v98;
  }
  *(_QWORD *)&v97.X = 0;
  v97.Width = a3;
  v97.Height = a4;
  Size = 0;
  LODWORD(pullResult) = 0;
  v104 = 0;
  if ( !a3 || !a4 || !v12 )
    goto LABEL_119;
  v15 = &v97;
  if ( a2 )
    v15 = a2;
  v97 = *v15;
  PixelFormat = TransformWICToWMPhoto(a6, (enum ORIENTATION *)&Size);
  if ( PixelFormat < 0 )
    goto LABEL_15;
  PixelFormat = TransformConsolidate((unsigned int)Size, &v97, &v88, v89, &pullResult);
  if ( PixelFormat < 0 )
    goto LABEL_15;
  if ( v97.X >= v88
    || (v17 = v97.X + v97.Width, v97.X + v97.Width > v88)
    || (v18 = (int)v89[0], Y = v97.Y, v97.Y >= v89[0])
    || (v20 = v97.Height + v97.Y, v97.Height + v97.Y > v89[0]) )
  {
    PixelFormat = -2003292343;
LABEL_15:
    CWmpDecoderFrame::HrClearCache(v102);
    goto LABEL_16;
  }
  if ( !a5 )
  {
    PixelFormat = CWmpDecoderFrame::GetPixelFormat((CWmpDecoderFrame *)((char *)this - 8), &v104);
    if ( PixelFormat < 0 )
      goto LABEL_15;
    v10 = &v104;
  }
  PixelFormat = TransformWICToWMPhoto(a6, (enum ORIENTATION *)&Size);
  if ( PixelFormat < 0 )
    goto LABEL_15;
  v22 = (CWmpDecoderFrame *)((char *)this - 66328);
  pullResult = 0;
  ullMultiplicand = 0;
  v100 = 0;
  ullMultiplier = 0;
  if ( Size >= 4 )
  {
    PixelSize = CWmpDecoderFrame::GetPixelSize(v22, v10);
    if ( (unsigned int)Bit2ByteSafe(PixelSize, v31, &ullMultiplicand) )
      goto LABEL_107;
    LODWORD(v18) = v32;
    PixelFormat = ULongLongMult(ullMultiplicand, v32, &pullResult);
    if ( PixelFormat < 0 )
      goto LABEL_15;
    v34 = v18;
    if ( pullResult > 0x1000000 )
      LODWORD(v18) = (0x1000000 / v33 + 16) & 0xFFFFFFF0;
    *(WICRect *)Size_8 = v97;
    v35 = v18 * (v97.X / (int)v18);
    LODWORD(Size_8[0]) = v35;
    v29 = (unsigned int)(v18 + v17 - 1 - (v17 - 1) % (int)v18);
    v96 = v18 + v17 - 1 - (v17 - 1) % (int)v18 - v35;
    LODWORD(Size_8[1]) = v96;
    if ( v34 >= (unsigned int)v29 )
    {
      v95 = HIDWORD(Size_8[1]);
    }
    else
    {
      v29 = HIDWORD(Size_8[1]);
      v95 = HIDWORD(Size_8[1]);
      v96 = v34 - v35;
      LODWORD(Size_8[1]) = v34 - v35;
    }
  }
  else
  {
    v23 = CWmpDecoderFrame::GetPixelSize(v22, v10);
    if ( (unsigned int)Bit2ByteSafe(v23, v24, &ullMultiplicand) )
      goto LABEL_107;
    PixelFormat = ULongLongMult(ullMultiplicand, v18, &pullResult);
    if ( PixelFormat < 0 )
      goto LABEL_15;
    v27 = v18;
    if ( pullResult > 0x1000000 )
      LODWORD(v18) = (0x1000000 / v26 + 16) & 0xFFFFFFF0;
    *(WICRect *)Size_8 = v97;
    v28 = v18 * (Y / (int)v18);
    HIDWORD(Size_8[0]) = v28;
    v29 = (unsigned int)(v18 + v20 - 1 - (v20 - 1) % (int)v18);
    v95 = v18 + v20 - 1 - (v20 - 1) % (int)v18 - v28;
    HIDWORD(Size_8[1]) = v95;
    if ( v27 < (unsigned int)v29 )
    {
      v95 = v27 - v28;
      HIDWORD(Size_8[1]) = v27 - v28;
      v29 = LODWORD(Size_8[1]);
    }
    v96 = Size_8[1];
  }
  v36 = (_OWORD *)((char *)this + 224);
  if ( Size_8[0] == *((_QWORD *)this + 28)
    && __PAIR128__(*(_QWORD *)&v10->Data1, Size_8[1]) == *(_OWORD *)((char *)this + 232)
    && *(_QWORD *)v10->Data4 == *((_QWORD *)this + 31)
    && v25 == *((_DWORD *)this + 64) )
  {
    v37 = (CWmpDecoderFrame *)((char *)this - 66328);
  }
  else
  {
    v37 = (CWmpDecoderFrame *)((char *)this - 66328);
    CWmpDecoderFrame::HrClearCache((CWmpDecoderFrame *)((char *)this - 66328));
    v36 = (_OWORD *)((char *)this + 224);
  }
  v38 = *(_OWORD *)Size_8;
  if ( *((_QWORD *)this + 47)
    || *((_QWORD *)this + 49)
    || (v29 = *(_QWORD *)&GUID_WICPixelFormat32bppBGR101010.Data1,
        *(_QWORD *)((char *)this + 148) != *(_QWORD *)&GUID_WICPixelFormat32bppBGR101010.Data1)
    || *(_QWORD *)((char *)this + 156) != *(_QWORD *)GUID_WICPixelFormat32bppBGR101010.Data4
    || *((_QWORD *)this - 8288) != *(_QWORD *)&GUID_WICPixelFormat64bppRGBHalf.Data1
    || *((_QWORD *)this - 8287) != *(_QWORD *)GUID_WICPixelFormat64bppRGBHalf.Data4
    || *(_QWORD *)&v10->Data1 == *(_QWORD *)&GUID_WICPixelFormat32bppBGR101010.Data1
    && *(_QWORD *)v10->Data4 == *(_QWORD *)GUID_WICPixelFormat32bppBGR101010.Data4 )
  {
    v40 = a6;
  }
  else
  {
    Size_8[0] = 0;
    pullResult = 0;
    WICFactory = GetWICFactory();
    PixelFormat = HDRConverter::Convert(
                    (CWmpDecoderFrame *)((char *)this + 280),
                    WICFactory,
                    (struct IWICBitmapSource *)(((unsigned __int64)this - 8) & -(__int64)(v37 != 0)),
                    (const struct _GUID *)((char *)this + 148),
                    (const struct _GUID *)this - 4144,
                    (struct IWICBitmapSource **)Size_8,
                    (struct IWICBitmapSourceTransform **)&pullResult);
    if ( PixelFormat < 0 )
      goto LABEL_15;
    v37 = (CWmpDecoderFrame *)((char *)this - 66328);
    CWmpDecoderFrame::HrClearCache((CWmpDecoderFrame *)((char *)this - 66328));
    v36 = (_OWORD *)((char *)this + 224);
    v40 = a6;
    *((_QWORD *)this + 46) = Size_8[0];
    *((_QWORD *)this + 47) = pullResult;
    *((_OWORD *)this + 14) = v38;
    v41 = *v10;
    *((_DWORD *)this + 64) = a6;
    *((struct _GUID *)this + 15) = v41;
  }
  if ( *((_DWORD *)this + 97) )
    goto LABEL_78;
  *((_DWORD *)this + 97) = 1;
  v42 = *(_QWORD *)&v10->Data1;
  Size_8[0] = 0;
  if ( (v42 != *(_QWORD *)((char *)this + 148) || *(_QWORD *)v10->Data4 != *(_QWORD *)((char *)this + 156))
    && ToneMapper::IsSupportedPixelFormat((ToneMapper *)v29, (const struct _GUID *)this - 4144)
    && !ToneMapper::IsSupportedPixelFormat(v43, v10) )
  {
    v44 = (struct IWICBitmapSource *)*((_QWORD *)this + 46);
    if ( !v44 )
    {
      if ( this == (CWmpDecoderFrame *)66328 )
        v44 = 0;
      else
        v44 = (struct IWICBitmapSource *)((char *)this - 8);
    }
    v45 = GetWICFactory();
    PixelFormat = ToneMapper::ToneMapImage(v46, v45, v44, (struct IWICBitmapSourceTransform **)Size_8);
    if ( PixelFormat < 0 )
      goto LABEL_15;
    v47 = (float *)((char *)this + 448);
    goto LABEL_73;
  }
  v47 = (float *)((char *)this + 448);
  if ( *((float *)this + 112) >= 1000000.0 )
    goto LABEL_78;
  LODWORD(pullResult) = 0;
  if ( (int)CWmpDecoderFrame::DoesSupportChangingMaxLuminance(
              (CWmpDecoderFrame *)((char *)this + 24),
              v10,
              (int *)&pullResult) >= 0
    && (_DWORD)pullResult )
  {
    v48 = (struct IWICBitmapSource *)*((_QWORD *)this + 46);
    if ( !v48 )
    {
      if ( this == (CWmpDecoderFrame *)66328 )
        v48 = 0;
      else
        v48 = (struct IWICBitmapSource *)((char *)this - 8);
    }
    v49 = *v47;
    v50 = GetWICFactory();
    PixelFormat = ToneMapper::ToneMapImageForHDRDisplay(
                    (ToneMapper *)Size_8,
                    v50,
                    v48,
                    v49,
                    (struct IWICBitmapSourceTransform **)Size_8);
    if ( PixelFormat < 0 )
      goto LABEL_15;
LABEL_73:
    v37 = (CWmpDecoderFrame *)((char *)this - 66328);
  }
  v51 = Size_8[0];
  if ( Size_8[0] )
  {
    v52 = *v47;
    v53 = v89[0];
    v54 = v99;
    v87 = v98;
    v86 = Size_4;
    v55 = v88;
    *v47 = 1000000.0;
    v56 = (*(__int64 (__fastcall **)(ULONGLONG, const struct WICRect *, __int64, __int64, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, unsigned int, unsigned __int8 *))(*(_QWORD *)v51 + 24LL))(
            v51,
            v54,
            v55,
            v53,
            v10,
            v40,
            v86,
            a8,
            v87);
    *v47 = v52;
    PixelFormat = v56;
    if ( v56 >= 0 )
    {
      CWmpDecoderFrame::HrClearCache((CWmpDecoderFrame *)((char *)this - 66328));
      *((_QWORD *)this + 49) = Size_8[0];
      *((_DWORD *)this + 97) = 1;
      *((_OWORD *)this + 14) = v38;
      v57 = *v10;
      *((_DWORD *)this + 64) = v40;
      *((struct _GUID *)this + 15) = v57;
      goto LABEL_16;
    }
    goto LABEL_15;
  }
  v36 = (_OWORD *)((char *)this + 224);
LABEL_78:
  v58 = *((_QWORD *)this + 49);
  if ( v58 || (v58 = *((_QWORD *)this + 47)) != 0 )
  {
    v59 = (*(__int64 (__fastcall **)(__int64, const struct WICRect *, _QWORD, _QWORD, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, unsigned int, unsigned __int8 *))(*(_QWORD *)v58 + 24LL))(
            v58,
            v99,
            v88,
            v89[0],
            v10,
            v40,
            Size_4,
            a8,
            v98);
    goto LABEL_80;
  }
  v60 = v88;
  if ( v88 == *((_DWORD *)this - 16557)
    && v89[0] == *((_DWORD *)this - 16556)
    && v99
    && v97.Width != v88
    && v99->Height > 1 )
  {
    v61 = v89[0];
    v62 = v37;
LABEL_127:
    v59 = CWmpDecoderFrame::CopyPixels_Core(v62, &v97, v60, v61, v10, v40, Size_4, a8, v98);
LABEL_80:
    PixelFormat = v59;
    if ( v59 >= 0 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v63 = Size;
  if ( *((_QWORD *)this + 33) )
    goto LABEL_92;
  if ( Size >= 4 )
  {
    if ( v96 > (int)v18 )
      goto LABEL_92;
  }
  else if ( v95 > (int)v18 )
  {
LABEL_92:
    v64 = ullMultiplicand;
    v65 = (CWmpDecoderFrame *)((char *)this - 66328);
    goto LABEL_93;
  }
  *v36 = v38;
  Size_8[0] = 0;
  v69 = *v10;
  *((_DWORD *)this + 64) = v40;
  *((struct _GUID *)this + 15) = v69;
  if ( v63 >= 4 )
  {
    v75 = CWmpDecoderFrame::GetPixelSize(v37, v10);
    if ( !(unsigned int)Bit2ByteSafe(v75, v76, &ullMultiplicand) )
    {
      v64 = ullMultiplicand;
      v72 = (ULONGLONG *)((char *)this + 272);
      if ( !(unsigned int)PadupSafe(ullMultiplicand, 128, (char *)this + 272)
        && !(unsigned int)PadupSafe(v77, 16, &ullMultiplier) )
      {
        v74 = ullMultiplier;
        goto LABEL_109;
      }
    }
LABEL_107:
    PixelFormat = -2147024362;
    goto LABEL_15;
  }
  v70 = CWmpDecoderFrame::GetPixelSize(v37, v10);
  if ( (unsigned int)Bit2ByteSafe(v70, v71, &ullMultiplicand) )
    goto LABEL_107;
  v64 = ullMultiplicand;
  v72 = (ULONGLONG *)((char *)this + 272);
  if ( (unsigned int)PadupSafe(ullMultiplicand, 128, (char *)this + 272) || (unsigned int)PadupSafe(v73, 16, &v100) )
    goto LABEL_107;
  v74 = v100;
LABEL_109:
  PixelFormat = ULongLongMult(*v72, v74, Size_8);
  if ( PixelFormat < 0 )
    goto LABEL_15;
  v79 = Size_8[0];
  v80 = _aligned_malloc(Size_8[0], v78);
  *((_QWORD *)this + 33) = v80;
  if ( !v80 )
    goto LABEL_125;
  memset_0(v80, 0, v79);
  v81 = *(_DWORD *)v72;
  v65 = (CWmpDecoderFrame *)((char *)this - 66328);
  PixelFormat = CWmpDecoderFrame::CopyPixels_Core(
                  (CWmpDecoderFrame *)((char *)this - 66328),
                  (const struct WICRect *)this + 14,
                  v88,
                  v89[0],
                  v10,
                  v40,
                  v81,
                  v79,
                  *((unsigned __int8 **)this + 33));
  if ( PixelFormat < 0 )
    goto LABEL_15;
  v63 = Size;
  v60 = v88;
LABEL_93:
  if ( !*((_QWORD *)this + 33) )
  {
    v61 = v89[0];
    v62 = v65;
    goto LABEL_127;
  }
  LODWORD(pullResult) = 0;
  if ( v63 >= 4 )
  {
    Width = v97.Width;
    if ( ((v63 - 5) & 0xFFFFFFFD) != 0 )
      v67 = v97.X - *((_DWORD *)this + 56);
    else
      v67 = *((_DWORD *)this + 56) + *((_DWORD *)this + 58) - v97.Width - v97.X;
  }
  else
  {
    v66 = v63 - 1;
    if ( !v66 || v66 == 2 )
    {
      Width = v97.Height;
      v67 = *((_DWORD *)this + 57) + *((_DWORD *)this + 59) - v97.Height - Y;
    }
    else
    {
      v67 = Y - *((_DWORD *)this + 57);
      Width = v97.Height;
    }
  }
  PixelFormat = -2147024362;
  if ( ULongLongToUInt(Size_4 * (unsigned __int64)(unsigned int)Width, (UINT *)&pullResult) == -2147024362 )
    goto LABEL_15;
  if ( v82 < v64 )
  {
LABEL_119:
    PixelFormat = -2147024809;
    goto LABEL_15;
  }
  if ( v64 + (unsigned int)(pullResult - v82) > a8 )
  {
LABEL_125:
    PixelFormat = -2147024882;
    goto LABEL_15;
  }
  PixelFormat = 0;
  v83 = 0;
  LODWORD(pullResult) = 0;
  if ( Width > 0 )
  {
    v84 = ullMultiplicand;
    v85 = v98;
    do
    {
      memcpy_0(
        &v85[(unsigned int)(v83 * v82)],
        (const void *)(*((_QWORD *)this + 33) + *((_QWORD *)this + 34) * (v83 + v67)),
        v84);
      LODWORD(v82) = Size_4;
      ++v83;
    }
    while ( v83 < Width );
    PixelFormat = pullResult;
  }
LABEL_16:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v103);
  return (unsigned int)PixelFormat;
}

```

## disassembly

```asm
0x180031850  mov     rax, rsp
0x180031853  push    rbp
0x180031854  push    rbx
0x180031855  push    rsi
0x180031856  push    rdi
0x180031857  push    r12
0x180031859  push    r13
0x18003185b  push    r14
0x18003185d  push    r15
0x18003185f  lea     rbp, [rax-68h]
0x180031863  sub     rsp, 128h
0x18003186a  movaps  xmmword ptr [rax-58h], xmm6
0x18003186e  movaps  xmmword ptr [rax-68h], xmm7
0x180031872  mov     rax, cs:__security_cookie
0x180031879  xor     rax, rsp
0x18003187c  mov     [rbp+60h+var_70], rax
0x180031880  mov     eax, [rbp+60h+arg_30]
0x180031886  mov     rdi, rcx
0x180031889  mov     r14, [rbp+60h+arg_20]
0x180031890  mov     esi, r8d
0x180031893  mov     dword ptr [rsp+160h+Size+4], eax
0x180031897  xor     r15d, r15d
0x18003189a  lea     rax, [rcx-10318h]
0x1800318a1  mov     [rsp+160h+var_110], r8d
0x1800318a6  mov     r8, [rbp+60h+arg_40]
0x1800318ad  mov     ebx, r9d
0x1800318b0  mov     [rbp+60h+var_90], rax
0x1800318b4  mov     rax, [rax+104B8h]
0x1800318bb  add     rax, 18h
0x1800318bf  mov     [rbp+60h+var_A8], rdx
0x1800318c3  mov     [rsp+160h+var_108], ebx
0x1800318c7  mov     [rbp+60h+var_B0], r8
0x1800318cb  mov     [rbp+60h+var_88], rax
0x1800318cf  lea     rcx, [rax+8]; lpCriticalSection
0x1800318d3  cmp     [rcx+28h], r15b
0x1800318d7  jz      short loc_1800318ED
0x1800318d9  call    cs:__imp_EnterCriticalSection
0x1800318e0  nop     dword ptr [rax+rax+00h]
0x1800318e5  mov     rdx, [rbp+60h+var_A8]
0x1800318e9  mov     r8, [rbp+60h+var_B0]
0x1800318ed  mov     qword ptr [rbp+60h+var_C0.X], r15
0x1800318f1  xorps   xmm0, xmm0
0x1800318f4  mov     [rbp+60h+var_C0.Width], esi
0x1800318f7  mov     [rbp+60h+var_C0.Height], ebx
0x1800318fa  mov     dword ptr [rsp+160h+Size], r15d
0x1800318ff  mov     dword ptr [rsp+160h+pullResult], r15d
0x180031904  movups  xmmword ptr [rbp+60h+var_80.Data1], xmm0
0x180031908  test    esi, esi
0x18003190a  jz      loc_18003224F
0x180031910  test    ebx, ebx
0x180031912  jz      loc_18003224F
0x180031918  test    r8, r8
0x18003191b  jz      loc_18003224F
0x180031921  mov     ecx, [rbp+60h+arg_28]; enum WICBitmapTransformOptions
0x180031927  lea     rax, [rbp+60h+var_C0]
0x18003192b  test    rdx, rdx
0x18003192e  cmovnz  rax, rdx
0x180031932  lea     rdx, [rsp+160h+Size]; enum ORIENTATION *
0x180031937  movups  xmm0, xmmword ptr [rax]
0x18003193a  movdqu  xmmword ptr [rbp+60h+var_C0.X], xmm0
0x18003193f  call    ?TransformWICToWMPhoto@@YAJW4WICBitmapTransformOptions@@PEAW4ORIENTATION@@@Z; TransformWICToWMPhoto(WICBitmapTransformOptions,ORIENTATION *)
0x180031944  mov     ebx, eax
0x180031946  test    eax, eax
0x180031948  js      short loc_1800319A9
0x18003194a  mov     ecx, dword ptr [rsp+160h+Size]
0x18003194e  lea     rax, [rsp+160h+pullResult]
0x180031953  lea     r9, [rsp+160h+var_108]
0x180031958  mov     [rsp+160h+var_140], rax
0x18003195d  lea     r8, [rsp+160h+var_110]
0x180031962  lea     rdx, [rbp+60h+var_C0]
0x180031966  call    ?TransformConsolidate@@YAJW4ORIENTATION@@PEAUWICRect@@PEAI2PEAW41@@Z; TransformConsolidate(ORIENTATION,WICRect *,uint *,uint *,ORIENTATION *)
0x18003196b  mov     ebx, eax
0x18003196d  test    eax, eax
0x18003196f  js      short loc_1800319A9
0x180031971  mov     r11d, [rsp+160h+var_110]
0x180031976  mov     eax, [rbp+60h+var_C0.X]
0x180031979  cmp     eax, r11d
0x18003197c  jnb     short loc_1800319A4
0x18003197e  mov     r15d, [rbp+60h+var_C0.Width]
0x180031982  add     r15d, eax
0x180031985  cmp     r15d, r11d
0x180031988  ja      short loc_1800319A4
0x18003198a  movsxd  r12, [rsp+160h+var_108]
0x18003198f  mov     esi, [rbp+60h+var_C0.Y]
0x180031992  cmp     esi, r12d
0x180031995  jnb     short loc_1800319A4
0x180031997  mov     r9d, [rbp+60h+var_C0.Height]
0x18003199b  lea     r13d, [r9+rsi]
0x18003199f  cmp     r13d, r12d
0x1800319a2  jbe     short loc_1800319EC
0x1800319a4  mov     ebx, 88982F49h
0x1800319a9  mov     rcx, [rbp+60h+var_90]; this
0x1800319ad  call    ?HrClearCache@CWmpDecoderFrame@@MEAAJXZ; CWmpDecoderFrame::HrClearCache(void)
0x1800319b2  lea     rcx, [rbp+60h+var_88]
0x1800319b6  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800319bb  mov     eax, ebx
0x1800319bd  mov     rcx, [rbp+60h+var_70]
0x1800319c1  xor     rcx, rsp; StackCookie
0x1800319c4  call    __security_check_cookie
0x1800319c9  lea     r11, [rsp+160h+var_38]
0x1800319d1  movaps  xmm6, xmmword ptr [r11-18h]
0x1800319d6  movaps  xmm7, xmmword ptr [r11-28h]
0x1800319db  mov     rsp, r11
0x1800319de  pop     r15
0x1800319e0  pop     r14
0x1800319e2  pop     r13
0x1800319e4  pop     r12
0x1800319e6  pop     rdi
0x1800319e7  pop     rsi
0x1800319e8  pop     rbx
0x1800319e9  pop     rbp
0x1800319ea  retn
0x1800319ec  test    r14, r14
0x1800319ef  jnz     short loc_180031A11
0x1800319f1  lea     rcx, [rdi-8]; this
0x1800319f5  lea     rdx, [rbp+60h+var_80]; struct _GUID *
0x1800319f9  call    ?GetPixelFormat@CWmpDecoderFrame@@UEAAJPEAU_GUID@@@Z; CWmpDecoderFrame::GetPixelFormat(_GUID *)
0x1800319fe  mov     ebx, eax
0x180031a00  test    eax, eax
0x180031a02  js      short loc_1800319A9
0x180031a04  mov     r11d, [rsp+160h+var_110]
0x180031a09  lea     r14, [rbp+60h+var_80]
0x180031a0d  mov     r9d, [rbp+60h+var_C0.Height]
0x180031a11  mov     r10d, [rbp+60h+arg_28]
0x180031a18  lea     rdx, [rsp+160h+Size]; enum ORIENTATION *
0x180031a1d  mov     ecx, r10d; enum WICBitmapTransformOptions
0x180031a20  call    ?TransformWICToWMPhoto@@YAJW4WICBitmapTransformOptions@@PEAW4ORIENTATION@@@Z; TransformWICToWMPhoto(WICBitmapTransformOptions,ORIENTATION *)
0x180031a25  mov     ebx, eax
0x180031a27  test    eax, eax
0x180031a29  js      loc_1800319A9
0x180031a2f  xor     ebx, ebx
0x180031a31  lea     rcx, [rdi-10318h]; this
0x180031a38  cmp     dword ptr [rsp+160h+Size], 4
0x180031a3d  mov     rdx, r14; struct _GUID *
0x180031a40  mov     [rsp+160h+pullResult], rbx
0x180031a45  mov     [rbp+60h+ullMultiplicand], rbx
0x180031a49  mov     [rbp+60h+var_A0], rbx
0x180031a4d  mov     [rbp+60h+ullMultiplier], rbx
0x180031a51  jge     loc_180031B12
0x180031a57  movsxd  r9, [rbp+60h+var_C0.Width]
0x180031a5b  call    ?GetPixelSize@CWmpDecoderFrame@@IEBA_KAEBU_GUID@@@Z; CWmpDecoderFrame::GetPixelSize(_GUID const &)
0x180031a60  mov     rcx, rax
0x180031a63  lea     r8, [rbp+60h+ullMultiplicand]
0x180031a67  mov     rdx, r9
0x180031a6a  call    Bit2ByteSafe
0x180031a6f  test    eax, eax
0x180031a71  jnz     loc_180032132
0x180031a77  mov     r11, [rbp+60h+ullMultiplicand]
0x180031a7b  lea     r8, [rsp+160h+pullResult]; pullResult
0x180031a80  mov     rcx, r11; ullMultiplicand
0x180031a83  mov     rdx, r12; ullMultiplier
0x180031a86  call    ULongLongMult
0x180031a8b  mov     ebx, eax
0x180031a8d  test    eax, eax
0x180031a8f  js      loc_1800319A9
0x180031a95  mov     eax, 1000000h
0x180031a9a  mov     r9d, r12d
0x180031a9d  cmp     [rsp+160h+pullResult], rax
0x180031aa2  jbe     short loc_180031AB1
0x180031aa4  xor     edx, edx
0x180031aa6  div     r11
0x180031aa9  lea     r12d, [rax+10h]
0x180031aad  and     r12d, 0FFFFFFF0h
0x180031ab1  movaps  xmm0, xmmword ptr [rbp+60h+var_C0.X]
0x180031ab5  lea     ecx, [r13-1]
0x180031ab9  mov     eax, esi
0x180031abb  movdqa  xmmword ptr [rsp+160h+Size+8], xmm0
0x180031ac1  cdq
0x180031ac2  idiv    r12d
0x180031ac5  mov     r8d, eax
0x180031ac8  mov     eax, ecx
0x180031aca  imul    r8d, r12d
0x180031ace  cdq
0x180031acf  idiv    r12d
0x180031ad2  mov     dword ptr [rsp+160h+Size+0Ch], r8d
0x180031ad7  sub     ecx, edx
0x180031ad9  add     ecx, r12d
0x180031adc  mov     edx, ecx
0x180031ade  sub     edx, r8d
0x180031ae1  mov     [rbp+60h+var_D8], edx
0x180031ae4  mov     dword ptr [rsp+160h+var_E8+4], edx
0x180031ae8  cmp     r9d, ecx
0x180031aeb  jnb     short loc_180031B06
0x180031aed  mov     ecx, r9d
0x180031af0  sub     ecx, r8d
0x180031af3  mov     [rbp+60h+var_D8], ecx
0x180031af6  mov     dword ptr [rsp+160h+var_E8+4], ecx
0x180031afa  mov     ecx, dword ptr [rsp+160h+var_E8]
0x180031afe  mov     [rbp+60h+var_D0], ecx
0x180031b01  jmp     loc_180031BC8
0x180031b06  mov     eax, dword ptr [rsp+160h+var_E8]
0x180031b0a  mov     [rbp+60h+var_D0], eax
0x180031b0d  jmp     loc_180031BC8
0x180031b12  movsxd  r9, r9d
0x180031b15  call    ?GetPixelSize@CWmpDecoderFrame@@IEBA_KAEBU_GUID@@@Z; CWmpDecoderFrame::GetPixelSize(_GUID const &)
0x180031b1a  mov     rcx, rax
0x180031b1d  lea     r8, [rbp+60h+ullMultiplicand]
0x180031b21  mov     rdx, r9
0x180031b24  call    Bit2ByteSafe
0x180031b29  test    eax, eax
0x180031b2b  jnz     loc_180032132
0x180031b31  movsxd  r12, r11d
0x180031b34  lea     r8, [rsp+160h+pullResult]; pullResult
0x180031b39  mov     r11, [rbp+60h+ullMultiplicand]
0x180031b3d  mov     rdx, r12; ullMultiplier
0x180031b40  mov     rcx, r11; ullMultiplicand
0x180031b43  call    ULongLongMult
0x180031b48  mov     ebx, eax
0x180031b4a  test    eax, eax
0x180031b4c  js      loc_1800319A9
0x180031b52  mov     eax, 1000000h
0x180031b57  mov     r9d, r12d
0x180031b5a  cmp     [rsp+160h+pullResult], rax
0x180031b5f  jbe     short loc_180031B6E
0x180031b61  xor     edx, edx
0x180031b63  div     r11
0x180031b66  lea     r12d, [rax+10h]
0x180031b6a  and     r12d, 0FFFFFFF0h
0x180031b6e  mov     eax, [rbp+60h+var_C0.X]
0x180031b71  lea     ecx, [r15-1]
0x180031b75  movaps  xmm0, xmmword ptr [rbp+60h+var_C0.X]
0x180031b79  cdq
0x180031b7a  idiv    r12d
0x180031b7d  movdqa  xmmword ptr [rsp+160h+Size+8], xmm0
0x180031b83  mov     r8d, eax
0x180031b86  mov     eax, ecx
0x180031b88  imul    r8d, r12d
0x180031b8c  cdq
0x180031b8d  idiv    r12d
0x180031b90  mov     dword ptr [rsp+160h+Size+8], r8d
0x180031b95  sub     ecx, edx
0x180031b97  add     ecx, r12d; this
0x180031b9a  mov     edx, ecx
0x180031b9c  sub     edx, r8d
0x180031b9f  mov     [rbp+60h+var_D0], edx
0x180031ba2  mov     dword ptr [rsp+160h+var_E8], edx
0x180031ba6  cmp     r9d, ecx
0x180031ba9  jnb     short loc_180031BC1
0x180031bab  mov     ecx, dword ptr [rsp+160h+var_E8+4]
0x180031baf  mov     edx, r9d
0x180031bb2  sub     edx, r8d
0x180031bb5  mov     [rbp+60h+var_D8], ecx
0x180031bb8  mov     [rbp+60h+var_D0], edx
0x180031bbb  mov     dword ptr [rsp+160h+var_E8], edx
0x180031bbf  jmp     short loc_180031BC8
0x180031bc1  mov     eax, dword ptr [rsp+160h+var_E8+4]
0x180031bc5  mov     [rbp+60h+var_D8], eax
0x180031bc8  mov     rax, [rsp+160h+Size+8]
0x180031bcd  lea     r8, [rdi+0E0h]
0x180031bd4  cmp     rax, [r8]
0x180031bd7  jnz     short loc_180031C06
0x180031bd9  mov     rax, [rsp+160h+var_E8]
0x180031bde  cmp     rax, [r8+8]
0x180031be2  jnz     short loc_180031C06
0x180031be4  mov     rax, [r14]
0x180031be7  cmp     rax, [rdi+0F0h]
0x180031bee  jnz     short loc_180031C06
0x180031bf0  mov     rax, [r14+8]
0x180031bf4  cmp     rax, [rdi+0F8h]
0x180031bfb  jnz     short loc_180031C06
0x180031bfd  cmp     r10d, [rdi+100h]
0x180031c04  jz      short loc_180031C1E
0x180031c06  lea     rbx, [rdi-10318h]
0x180031c0d  mov     rcx, rbx; this
0x180031c10  call    ?HrClearCache@CWmpDecoderFrame@@MEAAJXZ; CWmpDecoderFrame::HrClearCache(void)
0x180031c15  lea     r8, [rdi+0E0h]
0x180031c1c  jmp     short loc_180031C25
0x180031c1e  lea     rbx, [rdi-10318h]
0x180031c25  cmp     qword ptr [rdi+178h], 0
0x180031c2d  movaps  xmm7, xmmword ptr [rsp+160h+Size+8]
0x180031c32  jnz     loc_180031D54
0x180031c38  cmp     qword ptr [rdi+188h], 0
0x180031c40  jnz     loc_180031D54
0x180031c46  mov     rcx, qword ptr cs:GUID_WICPixelFormat32bppBGR101010.Data1
0x180031c4d  lea     r13, [rdi+94h]
0x180031c54  cmp     [r13+0], rcx
0x180031c58  jnz     loc_180031D54
0x180031c5e  mov     rdx, qword ptr cs:GUID_WICPixelFormat32bppBGR101010.Data4
0x180031c65  cmp     [r13+8], rdx
0x180031c69  jnz     loc_180031D54
0x180031c6f  lea     r15, [rdi-10300h]
0x180031c76  mov     rax, [r15]
0x180031c79  cmp     rax, qword ptr cs:GUID_WICPixelFormat64bppRGBHalf.Data1
0x180031c80  jnz     loc_180031D54
0x180031c86  mov     rax, [r15+8]
0x180031c8a  cmp     rax, qword ptr cs:GUID_WICPixelFormat64bppRGBHalf.Data4
0x180031c91  jnz     loc_180031D54
0x180031c97  cmp     [r14], rcx
0x180031c9a  jnz     short loc_180031CA6
0x180031c9c  cmp     [r14+8], rdx
0x180031ca0  jz      loc_180031D54
0x180031ca6  mov     rax, rbx
0x180031ca9  mov     [rsp+160h+Size+8], 0
0x180031cb2  neg     rax
0x180031cb5  mov     [rsp+160h+pullResult], 0
0x180031cbe  lea     rcx, [rdi-8]
0x180031cc2  sbb     rbx, rbx
0x180031cc5  and     rbx, rcx
0x180031cc8  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x180031ccd  mov     rdx, rax; struct IWICComponentFactory *
  ... truncated ...
```
