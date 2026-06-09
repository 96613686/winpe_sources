# WdcGraph::Draw(HWND__ *,HDC__ *)

- ea: `0x180017fa0`
- end: `0x180018942`
- name: `?Draw@WdcGraph@@QEAAJPEAUHWND__@@PEAUHDC__@@@Z`
- size: `2466`
- prototype: `__int64 __fastcall(WdcGraph *__hidden this, HWND hWnd, HDC hdc)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180017e70`

## callees

- `0x18000b7d0`
- `0x18000b854`
- `0x180015100`
- `0x180017fa0`
- `0x180018948`
- `0x180018bf4`
- `0x18003a3c0`
- `0x18003b064`
- `0x180086010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180018613`
- `GDI32!DeleteObject` at `0x18001862b`
- `GDI32!DeleteObject` at `0x1800186f2`
- `GDI32!DeleteObject` at `0x18001891d`
- `GDI32!DeleteObject` at `0x180018928`
- `GDI32!DeleteObject` at `0x180018613`
- `GDI32!DeleteObject` at `0x18001862b`
- `GDI32!DeleteObject` at `0x1800186f2`
- `GDI32!DeleteObject` at `0x18001891d`
- `GDI32!DeleteObject` at `0x180018928`
- `GDI32!CreatePen` at `0x1800180f5`
- `GDI32!CreatePen` at `0x1800184bb`
- `GDI32!CreatePen` at `0x1800180f5`
- `GDI32!CreatePen` at `0x1800184bb`
- `GDI32!SelectObject` at `0x18001808d`
- `GDI32!SelectObject` at `0x180018106`
- `GDI32!SelectObject` at `0x1800184ca`
- `GDI32!SelectObject` at `0x1800184f4`
- `GDI32!SelectObject` at `0x18001808d`
- `GDI32!SelectObject` at `0x180018106`
- `GDI32!SelectObject` at `0x1800184ca`
- `GDI32!SelectObject` at `0x1800184f4`
- `GDI32!MoveToEx` at `0x180018167`
- `GDI32!MoveToEx` at `0x1800181c0`
- `GDI32!MoveToEx` at `0x180018167`
- `GDI32!MoveToEx` at `0x1800181c0`
- `GDI32!CreateCompatibleDC` at `0x18001800e`
- `GDI32!CreateCompatibleDC` at `0x18001800e`
- `GDI32!CreateCompatibleBitmap` at `0x180018886`
- `GDI32!CreateCompatibleBitmap` at `0x180018886`
- `GDI32!CreateSolidBrush` at `0x1800180cd`
- `GDI32!CreateSolidBrush` at `0x1800184e3`
- `GDI32!CreateSolidBrush` at `0x1800180cd`
- `GDI32!CreateSolidBrush` at `0x1800184e3`
- `GDI32!LineTo` at `0x180018176`
- `GDI32!LineTo` at `0x1800181cf`
- `GDI32!LineTo` at `0x180018176`
- `GDI32!LineTo` at `0x1800181cf`
- `GDI32!SetROP2` at `0x180018502`
- `GDI32!SetROP2` at `0x180018527`
- `GDI32!SetROP2` at `0x180018502`
- `GDI32!SetROP2` at `0x180018527`
- `GDI32!Polygon` at `0x180018514`
- `GDI32!Polygon` at `0x180018514`
- `GDI32!BitBlt` at `0x1800185c0`
- `GDI32!BitBlt` at `0x1800185c0`
- `KERNEL32!GetLastError` at `0x1800186fd`
- `KERNEL32!GetLastError` at `0x180018790`
- `KERNEL32!GetLastError` at `0x1800187b8`
- `KERNEL32!GetLastError` at `0x180018804`
- `KERNEL32!GetLastError` at `0x180018850`
- `KERNEL32!GetLastError` at `0x1800186fd`
- `KERNEL32!GetLastError` at `0x180018790`
- `KERNEL32!GetLastError` at `0x1800187b8`
- `KERNEL32!GetLastError` at `0x180018804`
- `KERNEL32!GetLastError` at `0x180018850`
- `USER32!FillRect` at `0x1800180e2`
- `USER32!FillRect` at `0x1800180e2`
- `USER32!GetClientRect` at `0x180018027`
- `USER32!GetClientRect` at `0x180018027`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001868d`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001868d`

## pseudocode

```c
__int64 __fastcall WdcGraph::Draw(WdcGraph *this, HWND hWnd, HDC hdc)
{
  __int64 v3; // rax
  double *v7; // r12
  HDC hdcSrc; // rsi
  int v9; // r15d
  double v10; // xmm10_8
  double v11; // xmm8_8
  double v12; // xmm9_8
  int v13; // edi
  double v14; // xmm7_8
  double v15; // xmm0_8
  LONG bottom; // ebx
  int v17; // edi
  double v18; // xmm0_8
  double v19; // xmm0_8
  int v20; // ecx
  int v21; // ebx
  int v22; // edi
  int v23; // edx
  int v24; // r8d
  LONG v25; // r11d
  LONG right; // r15d
  double v27; // xmm1_8
  double v28; // xmm0_8
  double v29; // xmm0_8
  __int64 v30; // r10
  int v31; // edi
  double v32; // xmm0_8
  double v33; // xmm0_8
  double v34; // xmm0_8
  double v35; // xmm0_8
  double v36; // xmm0_8
  double v37; // xmm0_8
  double v38; // xmm0_8
  double v39; // xmm0_8
  int v40; // ecx
  double v41; // xmm0_8
  double v42; // xmm0_8
  unsigned int v43; // r12d
  int v44; // edx
  LONG v45; // ecx
  int v46; // edi
  __int64 v47; // rax
  HGDIOBJ v48; // r15
  HPEN Pen; // r15
  int v50; // ebx
  __int64 result; // rax
  signed int v52; // eax
  bool v53; // sf
  signed int LastError; // eax
  bool v55; // sf
  signed int v56; // eax
  bool v57; // sf
  signed int v58; // eax
  bool v59; // sf
  bool v60; // sf
  HBITMAP CompatibleBitmap; // rax
  int v62; // [rsp+50h] [rbp-B0h]
  HGDIOBJ v63[2]; // [rsp+60h] [rbp-A0h] BYREF
  HGDIOBJ ho; // [rsp+70h] [rbp-90h]
  struct tagRECT Rect; // [rsp+80h] [rbp-80h] BYREF
  POINT apt; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v67[126]; // [rsp+98h] [rbp-68h]

  v3 = *((_QWORD *)this + 41);
  Rect = 0;
  if ( !v3 )
    goto LABEL_80;
  v7 = (double *)*((_QWORD *)this + 44);
  v62 = *(_DWORD *)(v3 + 8172);
  if ( !hdc )
  {
    LastError = GetLastError();
    v55 = LastError < 0;
    if ( LastError )
    {
      if ( LastError > 0 )
        v55 = 1;
      if ( v55 )
      {
LABEL_80:
        v43 = 0;
        goto LABEL_61;
      }
    }
  }
  hdcSrc = CreateCompatibleDC(hdc);
  if ( !hdcSrc )
  {
    v56 = GetLastError();
    v57 = v56 < 0;
    if ( v56 )
    {
      if ( v56 > 0 )
      {
        v56 = (unsigned __int16)v56 | 0x80070000;
        v57 = v56 < 0;
      }
      if ( !v57 )
        goto LABEL_4;
    }
    else
    {
      v56 = -2147467259;
    }
    v43 = v56;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\graph.cpp", "WdcGraph::Draw", 0, L"FAILURE: 0x%08x", v56);
    goto LABEL_61;
  }
LABEL_4:
  GetClientRect(hWnd, &Rect);
  if ( *((_QWORD *)this + 40) )
    goto LABEL_5;
  CompatibleBitmap = CreateCompatibleBitmap(hdc, Rect.right - Rect.left, Rect.bottom - Rect.top);
  *((_QWORD *)this + 40) = CompatibleBitmap;
  if ( CompatibleBitmap )
    goto LABEL_5;
  v58 = GetLastError();
  v59 = v58 < 0;
  if ( v58 )
  {
    if ( v58 > 0 )
    {
      v58 = (unsigned __int16)v58 | 0x80070000;
      v59 = v58 < 0;
    }
    if ( v59 )
      goto LABEL_94;
LABEL_5:
    v9 = 10;
    v10 = 0.0;
    SelectObject(hdcSrc, *((HGDIOBJ *)this + 40));
    v11 = o_ceil_0();
    v12 = (double)(Rect.bottom - Rect.top) / 100.0;
    ho = CreateSolidBrush(0);
    FillRect(hdcSrc, &Rect, (HBRUSH)ho);
    v63[0] = CreatePen(0, 1, 0x108008u);
    SelectObject(hdcSrc, v63[0]);
    v13 = 0;
    v14 = o_ceil_0();
    do
    {
      v15 = o_ceil_0() - v14;
      MoveToEx(hdcSrc, (int)v15, Rect.top, 0);
      LineTo(hdcSrc, (int)v15, Rect.bottom);
      v13 += 5;
    }
    while ( v13 < 70 );
    if ( v12 * 10.0 < 4.0 )
      v9 = 20;
    bottom = Rect.bottom;
    if ( Rect.bottom > 0 )
    {
      v17 = v9;
      do
      {
        MoveToEx(hdcSrc, Rect.left, bottom, 0);
        LineTo(hdcSrc, Rect.right, bottom);
        v18 = (double)v17 * v12;
        if ( v18 <= 0.0 )
          v19 = v18 - 0.5;
        else
          v19 = v18 + 0.5;
        v17 += v9;
        bottom = Rect.bottom - (int)v19;
      }
      while ( bottom > 0 );
    }
    if ( !v7
      || (v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, double *, __int64))(**((_QWORD **)this + 41) + 24LL))(
                  *((_QWORD *)this + 41),
                  *((unsigned int *)this + 84),
                  v7,
                  60),
          v20 == 1) )
    {
      Pen = (HPEN)v63[0];
      v43 = 0;
    }
    else
    {
      v21 = 0;
      v22 = 60
          * (((int)((unsigned __int64)(2290649225LL * v62) >> 32) >> 5)
           + ((unsigned int)((unsigned __int64)(2290649225LL * v62) >> 32) >> 31)
           + 1)
          - v62;
      if ( v20 < 0 )
        v7[(v22 + 1) % 60] = 0.0;
      v23 = *((_DWORD *)this + 98);
      if ( v23 > 1 )
        WdcGraph::DataAutoScale(
          (WdcGraph *)((char *)this + 396),
          v7,
          v62,
          *((const struct _WDC_SCALE **)this + 48),
          v23,
          *((_DWORD *)this + 100),
          (int *)this + 99,
          (unsigned int *)this + 94);
      v24 = 0;
      v25 = Rect.bottom;
      right = Rect.right;
      v27 = WdcGraph::m_AccVal;
      v10 = *(double *)(32LL * *((int *)this + 99) + *((_QWORD *)this + 48));
      while ( 1 )
      {
        v28 = (double)v24 * v11;
        v29 = v28 <= 0.0 ? v28 - 0.5 : v28 + 0.5;
        *(&apt.x + 2 * v21) = right - (int)v29;
        if ( right - (int)v29 < 0 )
          break;
        v30 = v21;
        v31 = (v22 + 1) % 60;
        v32 = v10 * v7[v31] * v12;
        if ( v32 > 0.0 )
          v33 = v32 + 0.5;
        else
          v33 = v32 - 0.5;
        *(&apt.y + 2 * v21) = v25 - (int)v33;
        if ( v27 < 0.0 )
        {
          v27 = v7[v31];
          WdcGraph::m_AccVal = v27;
        }
        ++v21;
        v34 = (double)(v24 + 1) * v11;
        v35 = v34 <= 0.0 ? v34 - 0.5 : v34 + 0.5;
        v67[2 * v30] = right - (int)v35;
        if ( right - (int)v35 < 0 )
          break;
        v22 = (v31 + 1) % 60;
        v36 = v10 * v7[v22] * v12;
        if ( v36 > 0.0 )
          v37 = v36 + 0.5;
        else
          v37 = v36 - 0.5;
        v67[2 * v30 + 1] = v25 - (int)v37;
        if ( v27 < 0.0 )
        {
          v27 = v7[v22];
          WdcGraph::m_AccVal = v27;
        }
        v24 += 2;
        v21 = v30 + 2;
        if ( v24 >= 58 )
        {
          if ( v24 < 59 )
          {
            v38 = (double)v24 * v11;
            v39 = v38 <= 0.0 ? v38 - 0.5 : v38 + 0.5;
            *(&apt.x + 2 * v21) = right - (int)v39;
            if ( right - (int)v39 >= 0 )
            {
              v40 = (v22 + 1) % 60;
              v41 = v10 * v7[v40] * v12;
              if ( v41 > 0.0 )
                v42 = v41 + 0.5;
              else
                v42 = v41 - 0.5;
              *(&apt.y + 2 * v21) = v25 - (int)v42;
              if ( v27 < 0.0 )
                WdcGraph::m_AccVal = v7[v40];
              v21 = v30 + 3;
            }
          }
          break;
        }
      }
      v43 = 0;
      v44 = Rect.left - 1;
      *(&apt.x + 2 * v21) = Rect.left - 1;
      if ( v21 <= 0 )
        v45 = 0;
      else
        v45 = *(&Rect.bottom + 2 * v21);
      *(&apt.y + 2 * v21) = v45;
      v67[2 * v21] = v44;
      v46 = v21 + 3;
      v67[2 * v21 + 1] = v25;
      v47 = v21 + 2;
      *(&apt.x + 2 * v47) = right;
      v48 = v63[0];
      *(&apt.y + 2 * v47) = v25;
      if ( v48 )
        DeleteObject(v48);
      Pen = CreatePen(0, 1, 0xFF00u);
      SelectObject(hdcSrc, Pen);
      if ( ho )
        DeleteObject(ho);
      ho = CreateSolidBrush(0x6200u);
      SelectObject(hdcSrc, ho);
      v50 = SetROP2(hdcSrc, 15);
      if ( !Polygon(hdcSrc, &apt, v46) )
      {
        v52 = GetLastError();
        v53 = v52 < 0;
        if ( !v52 )
        {
          v43 = -2147467259;
          goto LABEL_55;
        }
        if ( v52 > 0 )
        {
          v52 = (unsigned __int16)v52 | 0x80070000;
          v53 = v52 < 0;
        }
        if ( v53 )
        {
LABEL_75:
          v43 = v52;
          goto LABEL_55;
        }
      }
      SetROP2(hdcSrc, v50);
    }
    *(struct tagRECT *)v63 = Rect;
    WdcGraph::DrawSupplemental(this, v11, v12, v62, (struct tagRECT *)v63, hdcSrc);
    *(struct tagRECT *)v63 = Rect;
    WdcGraph::DrawSelected(this, v11, v10, v12, v62, (struct tagRECT *)v63, hdcSrc);
    if ( BitBlt(hdc, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, hdcSrc, 0, 0, 0xCC0020u) )
    {
      v63[0] = 0;
      v43 = 0;
LABEL_55:
      if ( Pen )
        DeleteObject(Pen);
      if ( ho )
        DeleteObject(ho);
      goto LABEL_59;
    }
    v52 = GetLastError();
    v60 = v52 < 0;
    if ( !v52 )
      goto LABEL_55;
    if ( v52 > 0 )
    {
      v52 = (unsigned __int16)v52 | 0x80070000;
      v60 = v52 < 0;
    }
    if ( v60 )
      goto LABEL_55;
    goto LABEL_75;
  }
  v58 = -2147467259;
LABEL_94:
  v43 = v58;
  WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\graph.cpp", "WdcGraph::Draw", 0, L"FAILURE: 0x%08x", v58);
LABEL_59:
  if ( hdcSrc )
    DeleteObject(hdcSrc);
LABEL_61:
  StringCchPrintfW(
    &WdcGraph::m_AccValText,
    0x80u,
    L"%g,%g,%g",
    WdcGraph::m_AccVal,
    WdcGraph::m_AccValSupplemental,
    WdcGraph::m_AccValSelected);
  DirectUI::Element::SetAccValue(this, &WdcGraph::m_AccValText);
  result = v43;
  WdcGraph::m_AccValSelected = DOUBLE_N1_0;
  WdcGraph::m_AccValSupplemental = DOUBLE_N1_0;
  WdcGraph::m_AccVal = DOUBLE_N1_0;
  return result;
}

```

## disassembly

```asm
0x180017fa0  push    rbp
0x180017fa2  push    rbx
0x180017fa3  push    r12
0x180017fa5  push    r13
0x180017fa7  push    r14
0x180017fa9  lea     rbp, [rsp-200h]
0x180017fb1  sub     rsp, 300h
0x180017fb8  mov     rax, cs:__security_cookie
0x180017fbf  xor     rax, rsp
0x180017fc2  mov     [rbp+220h+var_90], rax
0x180017fc9  mov     rax, [rcx+148h]
0x180017fd0  xorps   xmm0, xmm0
0x180017fd3  mov     r13, r8
0x180017fd6  mov     rbx, rdx
0x180017fd9  mov     r14, rcx
0x180017fdc  movups  xmmword ptr [rbp+220h+Rect.left], xmm0
0x180017fe0  test    rax, rax
0x180017fe3  jz      loc_1800187B0
0x180017fe9  mov     eax, [rax+1FECh]
0x180017fef  mov     r12, [rcx+160h]
0x180017ff6  mov     [rsp+320h+var_2D0], eax
0x180017ffa  test    r8, r8
0x180017ffd  jz      loc_180018790
0x180018003  mov     rcx, r13; hdc
0x180018006  mov     [rsp+320h+arg_18], rsi
0x18001800e  call    cs:__imp_CreateCompatibleDC
0x180018014  mov     rsi, rax
0x180018017  test    rax, rax
0x18001801a  jz      loc_1800187B8
0x180018020  lea     rdx, [rbp+220h+Rect]; lpRect
0x180018024  mov     rcx, rbx; hWnd
0x180018027  call    cs:__imp_GetClientRect
0x18001802d  cmp     qword ptr [r14+140h], 0
0x180018035  jz      loc_180018875
0x18001803b  mov     rdx, [r14+140h]; h
0x180018042  mov     rcx, rsi; hdc
0x180018045  mov     [rsp+320h+var_28], rdi
0x18001804d  mov     [rsp+320h+var_30], r15
0x180018055  mov     r15d, 0Ah
0x18001805b  movaps  [rsp+320h+var_40], xmm6
0x180018063  xorps   xmm6, xmm6
0x180018066  movaps  [rsp+320h+var_50], xmm7
0x18001806e  movaps  [rsp+320h+var_60], xmm8
0x180018077  movaps  [rsp+320h+var_70], xmm9
0x180018080  movaps  [rsp+320h+var_80], xmm10
0x180018089  xorps   xmm10, xmm10
0x18001808d  call    cs:__imp_SelectObject
0x180018093  mov     eax, [rbp+220h+Rect.right]
0x180018096  sub     eax, [rbp+220h+Rect.left]
0x180018099  movd    xmm0, eax
0x18001809d  cvtdq2pd xmm0, xmm0
0x1800180a1  divsd   xmm0, cs:__real@404d000000000000
0x1800180a9  call    _o_ceil_0
0x1800180ae  mov     eax, [rbp+220h+Rect.bottom]
0x1800180b1  xor     ecx, ecx; color
0x1800180b3  sub     eax, [rbp+220h+Rect.top]
0x1800180b6  movaps  xmm8, xmm0
0x1800180ba  movd    xmm9, eax
0x1800180bf  cvtdq2pd xmm9, xmm9
0x1800180c4  divsd   xmm9, cs:__real@4059000000000000
0x1800180cd  call    cs:__imp_CreateSolidBrush
0x1800180d3  lea     rdx, [rbp+220h+Rect]; lprc
0x1800180d7  mov     rcx, rsi; hDC
0x1800180da  mov     r8, rax; hbr
0x1800180dd  mov     [rsp+320h+ho], rax
0x1800180e2  call    cs:__imp_FillRect
0x1800180e8  mov     edx, 1; cWidth
0x1800180ed  xor     ecx, ecx; iStyle
0x1800180ef  mov     r8d, 108008h; color
0x1800180f5  call    cs:__imp_CreatePen
0x1800180fb  mov     rdx, rax; h
0x1800180fe  mov     [rsp+320h+var_2C0], rax
0x180018103  mov     rcx, rsi; hdc
0x180018106  call    cs:__imp_SelectObject
0x18001810c  mov     eax, 66666667h
0x180018111  xor     edi, edi
0x180018113  imul    [rsp+320h+var_2D0]
0x180018117  sar     edx, 2
0x18001811a  mov     eax, edx
0x18001811c  shr     eax, 1Fh
0x18001811f  add     edx, eax
0x180018121  mov     eax, [rsp+320h+var_2D0]
0x180018125  lea     ecx, [rdx+rdx*4]
0x180018128  add     ecx, ecx
0x18001812a  sub     eax, ecx
0x18001812c  movd    xmm0, eax
0x180018130  cvtdq2pd xmm0, xmm0
0x180018134  mulsd   xmm0, xmm8
0x180018139  call    _o_ceil_0
0x18001813e  movaps  xmm7, xmm0
0x180018141  movd    xmm0, edi
0x180018145  cvtdq2pd xmm0, xmm0
0x180018149  mulsd   xmm0, xmm8
0x18001814e  call    _o_ceil_0
0x180018153  mov     r8d, [rbp+220h+Rect.top]; y
0x180018157  subsd   xmm0, xmm7
0x18001815b  xor     r9d, r9d; lppt
0x18001815e  mov     rcx, rsi; hdc
0x180018161  cvttsd2si ebx, xmm0
0x180018165  mov     edx, ebx; x
0x180018167  call    cs:__imp_MoveToEx
0x18001816d  mov     r8d, [rbp+220h+Rect.bottom]; y
0x180018171  mov     edx, ebx; x
0x180018173  mov     rcx, rsi; hdc
0x180018176  call    cs:__imp_LineTo
0x18001817c  add     edi, 5
0x18001817f  cmp     edi, 46h ; 'F'
0x180018182  jl      short loc_180018141
0x180018184  movsd   xmm0, cs:__real@4010000000000000
0x18001818c  movaps  xmm1, xmm9
0x180018190  mulsd   xmm1, cs:__real@4024000000000000
0x180018198  comisd  xmm0, xmm1
0x18001819c  ja      loc_1800188A1
0x1800181a2  mov     ebx, [rbp+220h+Rect.bottom]
0x1800181a5  movsd   xmm7, cs:__real@3fe0000000000000
0x1800181ad  test    ebx, ebx
0x1800181af  jle     short loc_180018201
0x1800181b1  mov     edi, r15d
0x1800181b4  mov     edx, [rbp+220h+Rect.left]; x
0x1800181b7  xor     r9d, r9d; lppt
0x1800181ba  mov     r8d, ebx; y
0x1800181bd  mov     rcx, rsi; hdc
0x1800181c0  call    cs:__imp_MoveToEx
0x1800181c6  mov     edx, [rbp+220h+Rect.right]; x
0x1800181c9  mov     r8d, ebx; y
0x1800181cc  mov     rcx, rsi; hdc
0x1800181cf  call    cs:__imp_LineTo
0x1800181d5  movd    xmm0, edi
0x1800181d9  cvtdq2pd xmm0, xmm0
0x1800181dd  mulsd   xmm0, xmm9
0x1800181e2  comisd  xmm0, xmm6
0x1800181e6  jbe     loc_1800188AC
0x1800181ec  addsd   xmm0, xmm7
0x1800181f0  mov     ebx, [rbp+220h+Rect.bottom]
0x1800181f3  add     edi, r15d
0x1800181f6  cvttsd2si rax, xmm0
0x1800181fb  sub     ebx, eax
0x1800181fd  test    ebx, ebx
0x1800181ff  jg      short loc_1800181B4
0x180018201  test    r12, r12
0x180018204  jz      loc_180018712
0x18001820a  mov     rcx, [r14+148h]
0x180018211  mov     r9d, 3Ch ; '<'
0x180018217  mov     edx, [r14+150h]
0x18001821e  mov     r8, r12
0x180018221  mov     rax, [rcx]
0x180018224  mov     rax, [rax+18h]
0x180018228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001822d  mov     ecx, eax
0x18001822f  cmp     eax, 1
0x180018232  jz      loc_180018712
0x180018238  mov     r8d, [rsp+320h+var_2D0]; int
0x18001823d  xor     r10d, r10d
0x180018240  mov     eax, 88888889h
0x180018245  mov     ebx, r10d
0x180018248  imul    r8d
0x18001824b  add     edx, r8d
0x18001824e  sar     edx, 5
0x180018251  mov     eax, edx
0x180018253  shr     eax, 1Fh
0x180018256  inc     eax
0x180018258  add     eax, edx
0x18001825a  imul    edi, eax, 3Ch ; '<'
0x18001825d  sub     edi, r8d
0x180018260  test    ecx, ecx
0x180018262  js      loc_1800188B5
0x180018268  mov     edx, [r14+188h]
0x18001826f  cmp     edx, 1
0x180018272  jg      loc_1800188DC
0x180018278  movsxd  rcx, dword ptr [r14+18Ch]
0x18001827f  mov     r8d, r10d
0x180018282  mov     rax, [r14+180h]
0x180018289  mov     r11d, [rbp+220h+Rect.bottom]
0x18001828d  mov     r15d, [rbp+220h+Rect.right]
0x180018291  movsd   xmm1, cs:?m_AccVal@WdcGraph@@2NA; double WdcGraph::m_AccVal
0x180018299  shl     rcx, 5
0x18001829d  movsd   xmm10, qword ptr [rcx+rax]
0x1800182a3  nop     dword ptr [rax+00h]
0x1800182a7  nop     word ptr [rax+rax+00000000h]
0x1800182b0  movd    xmm0, r8d
0x1800182b5  cvtdq2pd xmm0, xmm0
0x1800182b9  mulsd   xmm0, xmm8
0x1800182be  comisd  xmm0, xmm6
0x1800182c2  jbe     loc_18001874E
0x1800182c8  addsd   xmm0, xmm7
0x1800182cc  cvttsd2si rax, xmm0
0x1800182d1  movsxd  r9, ebx
0x1800182d4  mov     ecx, r15d
0x1800182d7  sub     ecx, eax
0x1800182d9  mov     [rbp+r9*8+220h+apt.x], ecx
0x1800182de  js      loc_180018465
0x1800182e4  inc     edi
0x1800182e6  movsxd  r10, ebx
0x1800182e9  mov     eax, 88888889h
0x1800182ee  movaps  xmm0, xmm10
0x1800182f2  imul    edi
0x1800182f4  add     edx, edi
0x1800182f6  sar     edx, 5
0x1800182f9  mov     eax, edx
0x1800182fb  shr     eax, 1Fh
0x1800182fe  add     edx, eax
0x180018300  imul    eax, edx, 3Ch ; '<'
0x180018303  sub     edi, eax
0x180018305  movsxd  rdx, edi
0x180018308  mulsd   xmm0, qword ptr [r12+rdx*8]
0x18001830e  mulsd   xmm0, xmm9
0x180018313  comisd  xmm0, xmm6
0x180018317  ja      loc_1800186D5
0x18001831d  subsd   xmm0, xmm7
0x180018321  cvttsd2si rax, xmm0
0x180018326  mov     ecx, r11d
0x180018329  sub     ecx, eax
0x18001832b  comisd  xmm6, xmm1
0x18001832f  mov     [rbp+r9*8+220h+apt.y], ecx
0x180018334  ja      loc_180018728
0x18001833a  lea     eax, [r8+1]
0x18001833e  inc     ebx
0x180018340  movd    xmm0, eax
0x180018344  cvtdq2pd xmm0, xmm0
0x180018348  mulsd   xmm0, xmm8
0x18001834d  comisd  xmm0, xmm6
0x180018351  jbe     loc_180018757
0x180018357  addsd   xmm0, xmm7
0x18001835b  cvttsd2si rax, xmm0
0x180018360  mov     ecx, r15d
0x180018363  sub     ecx, eax
0x180018365  mov     [rbp+r10*8+220h+var_288], ecx
0x18001836a  js      loc_180018465
0x180018370  inc     edi
0x180018372  mov     eax, 88888889h
0x180018377  imul    edi
0x180018379  movaps  xmm0, xmm10
0x18001837d  add     edx, edi
0x18001837f  sar     edx, 5
0x180018382  mov     eax, edx
0x180018384  shr     eax, 1Fh
0x180018387  add     edx, eax
0x180018389  imul    eax, edx, 3Ch ; '<'
0x18001838c  sub     edi, eax
0x18001838e  movsxd  rdx, edi
0x180018391  mulsd   xmm0, qword ptr [r12+rdx*8]
0x180018397  mulsd   xmm0, xmm9
0x18001839c  comisd  xmm0, xmm6
0x1800183a0  ja      loc_1800186DE
0x1800183a6  subsd   xmm0, xmm7
0x1800183aa  cvttsd2si rax, xmm0
0x1800183af  mov     ecx, r11d
0x1800183b2  sub     ecx, eax
0x1800183b4  comisd  xmm6, xmm1
0x1800183b8  mov     [rbp+r10*8+220h+var_284], ecx
0x1800183bd  ja      loc_18001873B
0x1800183c3  add     r8d, 2
0x1800183c7  lea     ebx, [r10+2]
0x1800183cb  cmp     r8d, 3Ah ; ':'
0x1800183cf  jl      loc_1800182B0
0x1800183d5  cmp     r8d, 3Bh ; ';'
0x1800183d9  jge     loc_180018465
0x1800183df  movd    xmm0, r8d
0x1800183e4  cvtdq2pd xmm0, xmm0
0x1800183e8  mulsd   xmm0, xmm8
0x1800183ed  comisd  xmm0, xmm6
0x1800183f1  jbe     loc_180018773
0x1800183f7  addsd   xmm0, xmm7
0x1800183fb  cvttsd2si rax, xmm0
0x180018400  movsxd  r8, ebx
0x180018403  mov     ecx, r15d
0x180018406  sub     ecx, eax
0x180018408  mov     [rbp+r8*8+220h+apt.x], ecx
0x18001840d  js      short loc_180018465
0x18001840f  lea     ecx, [rdi+1]
0x180018412  mov     eax, 88888889h
0x180018417  imul    ecx
0x180018419  movaps  xmm0, xmm10
0x18001841d  add     edx, ecx
0x18001841f  sar     edx, 5
0x180018422  mov     eax, edx
0x180018424  shr     eax, 1Fh
0x180018427  add     edx, eax
0x180018429  imul    eax, edx, 3Ch ; '<'
0x18001842c  sub     ecx, eax
0x18001842e  movsxd  rdx, ecx
0x180018431  mulsd   xmm0, qword ptr [r12+rdx*8]
0x180018437  mulsd   xmm0, xmm9
0x18001843c  comisd  xmm0, xmm6
0x180018440  ja      loc_18001871F
0x180018446  subsd   xmm0, xmm7
0x18001844a  cvttsd2si rax, xmm0
0x18001844f  mov     ecx, r11d
0x180018452  sub     ecx, eax
0x180018454  comisd  xmm6, xmm1
0x180018458  mov     [rbp+r8*8+220h+apt.y], ecx
0x18001845d  ja      loc_180018760
0x180018463  inc     ebx
0x180018465  mov     edx, [rbp+220h+Rect.left]
0x180018468  xor     r12d, r12d
0x18001846b  dec     edx
0x18001846d  movsxd  rax, ebx
0x180018470  mov     [rbp+rax*8+220h+apt.x], edx
0x180018474  test    ebx, ebx
0x180018476  jle     loc_1800186E7
  ... truncated ...
```
