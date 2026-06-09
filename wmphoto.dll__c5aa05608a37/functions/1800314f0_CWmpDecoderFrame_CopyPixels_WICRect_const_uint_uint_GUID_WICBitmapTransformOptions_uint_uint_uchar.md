# CWmpDecoderFrame::CopyPixels(WICRect const *,uint,uint,_GUID *,WICBitmapTransformOptions,uint,uint,uchar *)

- ea: `0x1800314f0`
- end: `0x180031fa3`
- name: `?CopyPixels@CWmpDecoderFrame@@UEAAJPEBUWICRect@@IIPEAU_GUID@@W4WICBitmapTransformOptions@@IIPEAE@Z`
- size: `2739`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this, const struct WICRect *, unsigned int, unsigned int, struct _GUID *, WICBitmapTransformOptions, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180031490`
- `0x180039770`

## callees

- `0x180028e94`
- `0x18002aec8`
- `0x18002da80`
- `0x18002db00`
- `0x18002db34`
- `0x18002dbd0`
- `0x18002de74`
- `0x18002e56c`
- `0x1800314f0`
- `0x1800320d8`
- `0x180033930`
- `0x18003599c`
- `0x180035e50`
- `0x180036ba4`
- `0x180038960`
- `0x1800392b0`
- `0x180039560`
- `0x18003b7b0`
- `0x18003d950`
- `0x18003db70`
- `0x180043630`
- `0x180044010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180031dfb`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180031dfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031579`

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
        UINT a8,
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
                    (struct ID2D1ColorContext **)this + 35,
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
    v56 = (*(__int64 (__fastcall **)(ULONGLONG, const struct WICRect *, __int64, __int64, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, UINT, unsigned __int8 *))(*(_QWORD *)v51 + 24LL))(
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
    v59 = (*(__int64 (__fastcall **)(__int64, const struct WICRect *, _QWORD, _QWORD, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, UINT, unsigned __int8 *))(*(_QWORD *)v58 + 24LL))(
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
    v59 = CWmpDecoderFrame::CopyPixels_Core(v62, (__m128i *)&v97, v60, v61, v10, v40, Size_4, a8, v98);
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
                  (__m128i *)this + 14,
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
0x1800314f0  mov     rax, rsp
0x1800314f3  push    rbp
0x1800314f4  push    rbx
0x1800314f5  push    rsi
0x1800314f6  push    rdi
0x1800314f7  push    r12
0x1800314f9  push    r13
0x1800314fb  push    r14
0x1800314fd  push    r15
0x1800314ff  lea     rbp, [rax-68h]
0x180031503  sub     rsp, 128h
0x18003150a  movaps  xmmword ptr [rax-58h], xmm6
0x18003150e  movaps  xmmword ptr [rax-68h], xmm7
0x180031512  mov     rax, cs:__security_cookie
0x180031519  xor     rax, rsp
0x18003151c  mov     [rbp+60h+var_70], rax
0x180031520  mov     eax, [rbp+60h+arg_30]
0x180031526  mov     rdi, rcx
0x180031529  mov     r14, [rbp+60h+arg_20]
0x180031530  mov     esi, r8d
0x180031533  mov     dword ptr [rsp+160h+Size+4], eax
0x180031537  xor     r15d, r15d
0x18003153a  lea     rax, [rcx-10318h]
0x180031541  mov     [rsp+160h+var_110], r8d
0x180031546  mov     r8, [rbp+60h+arg_40]
0x18003154d  mov     ebx, r9d
0x180031550  mov     [rbp+60h+var_90], rax
0x180031554  mov     rax, [rax+104B8h]
0x18003155b  add     rax, 18h
0x18003155f  mov     [rbp+60h+var_A8], rdx
0x180031563  mov     [rsp+160h+var_108], ebx
0x180031567  mov     [rbp+60h+var_B0], r8
0x18003156b  mov     [rbp+60h+var_88], rax
0x18003156f  lea     rcx, [rax+8]; lpCriticalSection
0x180031573  cmp     [rcx+28h], r15b
0x180031577  jz      short loc_180031587
0x180031579  call    cs:__imp_EnterCriticalSection
0x18003157f  mov     rdx, [rbp+60h+var_A8]
0x180031583  mov     r8, [rbp+60h+var_B0]
0x180031587  mov     qword ptr [rbp+60h+var_C0.X], r15
0x18003158b  xorps   xmm0, xmm0
0x18003158e  mov     [rbp+60h+var_C0.Width], esi
0x180031591  mov     [rbp+60h+var_C0.Height], ebx
0x180031594  mov     dword ptr [rsp+160h+Size], r15d
0x180031599  mov     dword ptr [rsp+160h+pullResult], r15d
0x18003159e  movups  xmmword ptr [rbp+60h+var_80.Data1], xmm0
0x1800315a2  test    esi, esi
0x1800315a4  jz      loc_180031EE2
0x1800315aa  test    ebx, ebx
0x1800315ac  jz      loc_180031EE2
0x1800315b2  test    r8, r8
0x1800315b5  jz      loc_180031EE2
0x1800315bb  mov     ecx, [rbp+60h+arg_28]; enum WICBitmapTransformOptions
0x1800315c1  lea     rax, [rbp+60h+var_C0]
0x1800315c5  test    rdx, rdx
0x1800315c8  cmovnz  rax, rdx
0x1800315cc  lea     rdx, [rsp+160h+Size]; enum ORIENTATION *
0x1800315d1  movups  xmm0, xmmword ptr [rax]
0x1800315d4  movdqu  xmmword ptr [rbp+60h+var_C0.X], xmm0
0x1800315d9  call    ?TransformWICToWMPhoto@@YAJW4WICBitmapTransformOptions@@PEAW4ORIENTATION@@@Z; TransformWICToWMPhoto(WICBitmapTransformOptions,ORIENTATION *)
0x1800315de  mov     ebx, eax
0x1800315e0  test    eax, eax
0x1800315e2  js      short loc_180031643
0x1800315e4  mov     ecx, dword ptr [rsp+160h+Size]
0x1800315e8  lea     rax, [rsp+160h+pullResult]
0x1800315ed  lea     r9, [rsp+160h+var_108]
0x1800315f2  mov     [rsp+160h+var_140], rax
0x1800315f7  lea     r8, [rsp+160h+var_110]
0x1800315fc  lea     rdx, [rbp+60h+var_C0]
0x180031600  call    ?TransformConsolidate@@YAJW4ORIENTATION@@PEAUWICRect@@PEAI2PEAW41@@Z; TransformConsolidate(ORIENTATION,WICRect *,uint *,uint *,ORIENTATION *)
0x180031605  mov     ebx, eax
0x180031607  test    eax, eax
0x180031609  js      short loc_180031643
0x18003160b  mov     r11d, [rsp+160h+var_110]
0x180031610  mov     eax, [rbp+60h+var_C0.X]
0x180031613  cmp     eax, r11d
0x180031616  jnb     short loc_18003163E
0x180031618  mov     r15d, [rbp+60h+var_C0.Width]
0x18003161c  add     r15d, eax
0x18003161f  cmp     r15d, r11d
0x180031622  ja      short loc_18003163E
0x180031624  movsxd  r12, [rsp+160h+var_108]
0x180031629  mov     esi, [rbp+60h+var_C0.Y]
0x18003162c  cmp     esi, r12d
0x18003162f  jnb     short loc_18003163E
0x180031631  mov     r9d, [rbp+60h+var_C0.Height]
0x180031635  lea     r13d, [r9+rsi]
0x180031639  cmp     r13d, r12d
0x18003163c  jbe     short loc_180031685
0x18003163e  mov     ebx, 88982F49h
0x180031643  mov     rcx, [rbp+60h+var_90]; this
0x180031647  call    ?HrClearCache@CWmpDecoderFrame@@MEAAJXZ; CWmpDecoderFrame::HrClearCache(void)
0x18003164c  lea     rcx, [rbp+60h+var_88]
0x180031650  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180031655  mov     eax, ebx
0x180031657  mov     rcx, [rbp+60h+var_70]
0x18003165b  xor     rcx, rsp; StackCookie
0x18003165e  call    __security_check_cookie
0x180031663  lea     r11, [rsp+160h+var_38]
0x18003166b  movaps  xmm6, xmmword ptr [r11-18h]
0x180031670  movaps  xmm7, xmmword ptr [r11-28h]
0x180031675  mov     rsp, r11
0x180031678  pop     r15
0x18003167a  pop     r14
0x18003167c  pop     r13
0x18003167e  pop     r12
0x180031680  pop     rdi
0x180031681  pop     rsi
0x180031682  pop     rbx
0x180031683  pop     rbp
0x180031684  retn
0x180031685  test    r14, r14
0x180031688  jnz     short loc_1800316AA
0x18003168a  lea     rcx, [rdi-8]; this
0x18003168e  lea     rdx, [rbp+60h+var_80]; struct _GUID *
0x180031692  call    ?GetPixelFormat@CWmpDecoderFrame@@UEAAJPEAU_GUID@@@Z; CWmpDecoderFrame::GetPixelFormat(_GUID *)
0x180031697  mov     ebx, eax
0x180031699  test    eax, eax
0x18003169b  js      short loc_180031643
0x18003169d  mov     r11d, [rsp+160h+var_110]
0x1800316a2  lea     r14, [rbp+60h+var_80]
0x1800316a6  mov     r9d, [rbp+60h+var_C0.Height]
0x1800316aa  mov     r10d, [rbp+60h+arg_28]
0x1800316b1  lea     rdx, [rsp+160h+Size]; enum ORIENTATION *
0x1800316b6  mov     ecx, r10d; enum WICBitmapTransformOptions
0x1800316b9  call    ?TransformWICToWMPhoto@@YAJW4WICBitmapTransformOptions@@PEAW4ORIENTATION@@@Z; TransformWICToWMPhoto(WICBitmapTransformOptions,ORIENTATION *)
0x1800316be  mov     ebx, eax
0x1800316c0  test    eax, eax
0x1800316c2  js      loc_180031643
0x1800316c8  xor     ebx, ebx
0x1800316ca  lea     rcx, [rdi-10318h]; this
0x1800316d1  cmp     dword ptr [rsp+160h+Size], 4
0x1800316d6  mov     rdx, r14; struct _GUID *
0x1800316d9  mov     [rsp+160h+pullResult], rbx
0x1800316de  mov     [rbp+60h+ullMultiplicand], rbx
0x1800316e2  mov     [rbp+60h+var_A0], rbx
0x1800316e6  mov     [rbp+60h+ullMultiplier], rbx
0x1800316ea  jge     loc_1800317AB
0x1800316f0  movsxd  r9, [rbp+60h+var_C0.Width]
0x1800316f4  call    ?GetPixelSize@CWmpDecoderFrame@@IEBA_KAEBU_GUID@@@Z; CWmpDecoderFrame::GetPixelSize(_GUID const &)
0x1800316f9  mov     rcx, rax
0x1800316fc  lea     r8, [rbp+60h+ullMultiplicand]
0x180031700  mov     rdx, r9
0x180031703  call    Bit2ByteSafe
0x180031708  test    eax, eax
0x18003170a  jnz     loc_180031DCB
0x180031710  mov     r11, [rbp+60h+ullMultiplicand]
0x180031714  lea     r8, [rsp+160h+pullResult]; pullResult
0x180031719  mov     rcx, r11; ullMultiplicand
0x18003171c  mov     rdx, r12; ullMultiplier
0x18003171f  call    ULongLongMult
0x180031724  mov     ebx, eax
0x180031726  test    eax, eax
0x180031728  js      loc_180031643
0x18003172e  mov     eax, 1000000h
0x180031733  mov     r9d, r12d
0x180031736  cmp     [rsp+160h+pullResult], rax
0x18003173b  jbe     short loc_18003174A
0x18003173d  xor     edx, edx
0x18003173f  div     r11
0x180031742  lea     r12d, [rax+10h]
0x180031746  and     r12d, 0FFFFFFF0h
0x18003174a  movaps  xmm0, xmmword ptr [rbp+60h+var_C0.X]
0x18003174e  lea     ecx, [r13-1]
0x180031752  mov     eax, esi
0x180031754  movdqa  xmmword ptr [rsp+160h+Size+8], xmm0
0x18003175a  cdq
0x18003175b  idiv    r12d
0x18003175e  mov     r8d, eax
0x180031761  mov     eax, ecx
0x180031763  imul    r8d, r12d
0x180031767  cdq
0x180031768  idiv    r12d
0x18003176b  mov     dword ptr [rsp+160h+Size+0Ch], r8d
0x180031770  sub     ecx, edx
0x180031772  add     ecx, r12d
0x180031775  mov     edx, ecx
0x180031777  sub     edx, r8d
0x18003177a  mov     [rbp+60h+var_D8], edx
0x18003177d  mov     dword ptr [rsp+160h+var_E8+4], edx
0x180031781  cmp     r9d, ecx
0x180031784  jnb     short loc_18003179F
0x180031786  mov     ecx, r9d
0x180031789  sub     ecx, r8d
0x18003178c  mov     [rbp+60h+var_D8], ecx
0x18003178f  mov     dword ptr [rsp+160h+var_E8+4], ecx
0x180031793  mov     ecx, dword ptr [rsp+160h+var_E8]
0x180031797  mov     [rbp+60h+var_D0], ecx
0x18003179a  jmp     loc_180031861
0x18003179f  mov     eax, dword ptr [rsp+160h+var_E8]
0x1800317a3  mov     [rbp+60h+var_D0], eax
0x1800317a6  jmp     loc_180031861
0x1800317ab  movsxd  r9, r9d
0x1800317ae  call    ?GetPixelSize@CWmpDecoderFrame@@IEBA_KAEBU_GUID@@@Z; CWmpDecoderFrame::GetPixelSize(_GUID const &)
0x1800317b3  mov     rcx, rax
0x1800317b6  lea     r8, [rbp+60h+ullMultiplicand]
0x1800317ba  mov     rdx, r9
0x1800317bd  call    Bit2ByteSafe
0x1800317c2  test    eax, eax
0x1800317c4  jnz     loc_180031DCB
0x1800317ca  movsxd  r12, r11d
0x1800317cd  lea     r8, [rsp+160h+pullResult]; pullResult
0x1800317d2  mov     r11, [rbp+60h+ullMultiplicand]
0x1800317d6  mov     rdx, r12; ullMultiplier
0x1800317d9  mov     rcx, r11; ullMultiplicand
0x1800317dc  call    ULongLongMult
0x1800317e1  mov     ebx, eax
0x1800317e3  test    eax, eax
0x1800317e5  js      loc_180031643
0x1800317eb  mov     eax, 1000000h
0x1800317f0  mov     r9d, r12d
0x1800317f3  cmp     [rsp+160h+pullResult], rax
0x1800317f8  jbe     short loc_180031807
0x1800317fa  xor     edx, edx
0x1800317fc  div     r11
0x1800317ff  lea     r12d, [rax+10h]
0x180031803  and     r12d, 0FFFFFFF0h
0x180031807  mov     eax, [rbp+60h+var_C0.X]
0x18003180a  lea     ecx, [r15-1]
0x18003180e  movaps  xmm0, xmmword ptr [rbp+60h+var_C0.X]
0x180031812  cdq
0x180031813  idiv    r12d
0x180031816  movdqa  xmmword ptr [rsp+160h+Size+8], xmm0
0x18003181c  mov     r8d, eax
0x18003181f  mov     eax, ecx
0x180031821  imul    r8d, r12d
0x180031825  cdq
0x180031826  idiv    r12d
0x180031829  mov     dword ptr [rsp+160h+Size+8], r8d
0x18003182e  sub     ecx, edx
0x180031830  add     ecx, r12d; this
0x180031833  mov     edx, ecx
0x180031835  sub     edx, r8d
0x180031838  mov     [rbp+60h+var_D0], edx
0x18003183b  mov     dword ptr [rsp+160h+var_E8], edx
0x18003183f  cmp     r9d, ecx
0x180031842  jnb     short loc_18003185A
0x180031844  mov     ecx, dword ptr [rsp+160h+var_E8+4]
0x180031848  mov     edx, r9d
0x18003184b  sub     edx, r8d
0x18003184e  mov     [rbp+60h+var_D8], ecx
0x180031851  mov     [rbp+60h+var_D0], edx
0x180031854  mov     dword ptr [rsp+160h+var_E8], edx
0x180031858  jmp     short loc_180031861
0x18003185a  mov     eax, dword ptr [rsp+160h+var_E8+4]
0x18003185e  mov     [rbp+60h+var_D8], eax
0x180031861  mov     rax, [rsp+160h+Size+8]
0x180031866  lea     r8, [rdi+0E0h]
0x18003186d  cmp     rax, [r8]
0x180031870  jnz     short loc_18003189F
0x180031872  mov     rax, [rsp+160h+var_E8]
0x180031877  cmp     rax, [r8+8]
0x18003187b  jnz     short loc_18003189F
0x18003187d  mov     rax, [r14]
0x180031880  cmp     rax, [rdi+0F0h]
0x180031887  jnz     short loc_18003189F
0x180031889  mov     rax, [r14+8]
0x18003188d  cmp     rax, [rdi+0F8h]
0x180031894  jnz     short loc_18003189F
0x180031896  cmp     r10d, [rdi+100h]
0x18003189d  jz      short loc_1800318B7
0x18003189f  lea     rbx, [rdi-10318h]
0x1800318a6  mov     rcx, rbx; this
0x1800318a9  call    ?HrClearCache@CWmpDecoderFrame@@MEAAJXZ; CWmpDecoderFrame::HrClearCache(void)
0x1800318ae  lea     r8, [rdi+0E0h]
0x1800318b5  jmp     short loc_1800318BE
0x1800318b7  lea     rbx, [rdi-10318h]
0x1800318be  cmp     qword ptr [rdi+178h], 0
0x1800318c6  movaps  xmm7, xmmword ptr [rsp+160h+Size+8]
0x1800318cb  jnz     loc_1800319ED
0x1800318d1  cmp     qword ptr [rdi+188h], 0
0x1800318d9  jnz     loc_1800319ED
0x1800318df  mov     rcx, qword ptr cs:GUID_WICPixelFormat32bppBGR101010.Data1
0x1800318e6  lea     r13, [rdi+94h]
0x1800318ed  cmp     [r13+0], rcx
0x1800318f1  jnz     loc_1800319ED
0x1800318f7  mov     rdx, qword ptr cs:GUID_WICPixelFormat32bppBGR101010.Data4
0x1800318fe  cmp     [r13+8], rdx
0x180031902  jnz     loc_1800319ED
0x180031908  lea     r15, [rdi-10300h]
0x18003190f  mov     rax, [r15]
0x180031912  cmp     rax, qword ptr cs:GUID_WICPixelFormat64bppRGBHalf.Data1
0x180031919  jnz     loc_1800319ED
0x18003191f  mov     rax, [r15+8]
0x180031923  cmp     rax, qword ptr cs:GUID_WICPixelFormat64bppRGBHalf.Data4
0x18003192a  jnz     loc_1800319ED
0x180031930  cmp     [r14], rcx
0x180031933  jnz     short loc_18003193F
0x180031935  cmp     [r14+8], rdx
0x180031939  jz      loc_1800319ED
0x18003193f  mov     rax, rbx
0x180031942  mov     [rsp+160h+Size+8], 0
0x18003194b  neg     rax
0x18003194e  mov     [rsp+160h+pullResult], 0
0x180031957  lea     rcx, [rdi-8]
0x18003195b  sbb     rbx, rbx
0x18003195e  and     rbx, rcx
0x180031961  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x180031966  mov     rdx, rax; struct IWICComponentFactory *
0x180031969  lea     rcx, [rdi+118h]; this
  ... truncated ...
```
