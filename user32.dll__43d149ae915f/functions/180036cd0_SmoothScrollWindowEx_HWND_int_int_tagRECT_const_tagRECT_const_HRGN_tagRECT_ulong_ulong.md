# SmoothScrollWindowEx(HWND__ *,int,int,tagRECT const *,tagRECT const *,HRGN__ *,tagRECT *,ulong,ulong)

- ea: `0x180036cd0`
- end: `0x18003747f`
- name: `?SmoothScrollWindowEx@@YAHPEAUHWND__@@HHPEBUtagRECT@@1PEAUHRGN__@@PEAU2@KK@Z`
- size: `1967`
- prototype: `__int64 __fastcall(HWND, int, int, const struct tagRECT *, const struct tagRECT *, HRGN, struct tagRECT *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180057320`

## callees

- `0x180009e20`
- `0x18000ae90`
- `0x18000cf20`
- `0x18000d210`
- `0x180036cd0`
- `0x180037490`
- `0x1800374d0`
- `0x180037530`
- `0x180096da1`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserMsgWaitForMultipleObjectsEx` at `0x180036fd7`
- `win32u!NtUserMsgWaitForMultipleObjectsEx` at `0x180036fd7`
- `win32u!NtUserScrollWindowEx` at `0x18003702b`
- `win32u!NtUserScrollWindowEx` at `0x18009c617`
- `win32u!NtUserScrollWindowEx` at `0x18003702b`
- `win32u!NtUserScrollWindowEx` at `0x18009c617`
- `win32u!NtUserRedrawWindow` at `0x18003715c`
- `win32u!NtUserRedrawWindow` at `0x18003715c`
- `win32u!NtUserGetDCEx` at `0x180036ddd`
- `win32u!NtUserGetDCEx` at `0x180036ddd`
- `GDI32!SelectObject` at `0x180036e54`
- `GDI32!SelectObject` at `0x18009c4dd`
- `GDI32!SelectObject` at `0x18009c526`
- `GDI32!SelectObject` at `0x180036e54`
- `GDI32!SelectObject` at `0x18009c4dd`
- `GDI32!SelectObject` at `0x18009c526`
- `GDI32!GetClipBox` at `0x180036e09`
- `GDI32!GetClipBox` at `0x180036e09`
- `GDI32!SetRectRgn` at `0x18003712f`
- `GDI32!SetRectRgn` at `0x180037457`
- `GDI32!SetRectRgn` at `0x18003712f`
- `GDI32!SetRectRgn` at `0x180037457`
- `GDI32!CombineRgn` at `0x180037146`
- `GDI32!CombineRgn` at `0x180037146`
- `GDI32!CreateRectRgn` at `0x180036ec7`
- `GDI32!CreateRectRgn` at `0x180036ee4`
- `GDI32!CreateRectRgn` at `0x180036ec7`
- `GDI32!CreateRectRgn` at `0x180036ee4`
- `GDI32!GetBoundsRect` at `0x180036eaf`
- `GDI32!GetBoundsRect` at `0x180036eaf`
- `GDI32!SetBoundsRect` at `0x180036e67`
- `GDI32!SetBoundsRect` at `0x180036e67`
- `GDI32!CreateCompatibleBitmap` at `0x180036e22`
- `GDI32!CreateCompatibleBitmap` at `0x18009c50e`
- `GDI32!CreateCompatibleBitmap` at `0x180036e22`
- `GDI32!CreateCompatibleBitmap` at `0x18009c50e`
- `GDI32!DeleteDC` at `0x1800371a1`
- `GDI32!DeleteDC` at `0x1800371a1`
- `GDI32!BitBlt` at `0x18003710c`
- `GDI32!BitBlt` at `0x18003710c`
- `GDI32!CreateCompatibleDC` at `0x180036e38`
- `GDI32!CreateCompatibleDC` at `0x180036e38`
- `GDI32!DeleteObject` at `0x1800372f5`
- `GDI32!DeleteObject` at `0x180037303`
- `GDI32!DeleteObject` at `0x18003746d`
- `GDI32!DeleteObject` at `0x18009c4e6`
- `GDI32!DeleteObject` at `0x1800372f5`
- `GDI32!DeleteObject` at `0x180037303`
- `GDI32!DeleteObject` at `0x18003746d`
- `GDI32!DeleteObject` at `0x18009c4e6`

## pseudocode

```c
__int64 __fastcall SmoothScrollWindowEx(
        HWND a1,
        int a2,
        int a3,
        __m128i *a4,
        const struct tagRECT *a5,
        HRGN a6,
        struct tagRECT *a7,
        unsigned int a8,
        unsigned int a9)
{
  struct tagWND *v13; // rax
  struct tagWND *v14; // rsi
  int v15; // edi
  int v16; // ebx
  int v17; // r12d
  int v18; // r13d
  HDC DCEx; // rax
  unsigned int v20; // r14d
  HRGN v21; // r15
  HBITMAP CompatibleBitmap; // r15
  HDC CompatibleDC; // rax
  HDC v24; // r14
  HDC v25; // rsi
  char BoundsRect; // al
  struct tagRECT v27; // xmm6
  int v28; // eax
  unsigned int v29; // r14d
  unsigned int v30; // esi
  unsigned int v31; // ecx
  int v32; // r8d
  int v33; // r10d
  unsigned int v34; // edx
  unsigned int v35; // r11d
  unsigned int v36; // eax
  __int64 v37; // r8
  __int64 v38; // rdx
  LONG v39; // r11d
  BOOL v40; // ecx
  BOOL v41; // eax
  LONG v42; // ecx
  LONG top; // eax
  LONG v44; // eax
  struct tagRECT v46; // xmm1
  struct tagRECT v47; // xmm0
  struct tagWND *v48; // rax
  _WORD *v49; // rcx
  int v50; // r8d
  struct tagRECT v51; // xmm6
  HBITMAP v52; // rax
  int v53; // r10d
  LONG bottom; // [rsp+58h] [rbp-B0h]
  LONG right; // [rsp+60h] [rbp-A8h]
  LONG v56; // [rsp+68h] [rbp-A0h]
  LONG left; // [rsp+78h] [rbp-90h]
  int y; // [rsp+88h] [rbp-80h]
  int x; // [rsp+8Ch] [rbp-7Ch]
  int v60; // [rsp+90h] [rbp-78h]
  int cy; // [rsp+98h] [rbp-70h]
  int v62; // [rsp+9Ch] [rbp-6Ch]
  int v63; // [rsp+A0h] [rbp-68h]
  unsigned int v64; // [rsp+A4h] [rbp-64h]
  HDC wParam; // [rsp+B0h] [rbp-58h]
  HRGN hrgnSrc1; // [rsp+B8h] [rbp-50h]
  __m128i Buf1; // [rsp+C8h] [rbp-40h] BYREF
  int v69; // [rsp+D8h] [rbp-30h]
  int y1; // [rsp+DCh] [rbp-2Ch]
  int x1; // [rsp+E0h] [rbp-28h]
  HDC hdc; // [rsp+E8h] [rbp-20h]
  HWND hWnd; // [rsp+F0h] [rbp-18h]
  HRGN hrgn; // [rsp+F8h] [rbp-10h]
  HGDIOBJ h; // [rsp+100h] [rbp-8h]
  __m128i *v76; // [rsp+108h] [rbp+0h]
  struct tagRECT *v77; // [rsp+110h] [rbp+8h]
  HRGN v78; // [rsp+118h] [rbp+10h]
  const struct tagRECT *v79; // [rsp+120h] [rbp+18h]
  struct tagMSG Msg; // [rsp+128h] [rbp+20h] BYREF
  struct tagRECT rect; // [rsp+158h] [rbp+50h] BYREF
  struct tagRECT v82; // [rsp+168h] [rbp+60h] BYREF

  v79 = a5;
  v78 = a6;
  v77 = a7;
  v76 = a4;
  v69 = a3;
  hWnd = a1;
  Buf1 = 0;
  rect = 0;
  v13 = ValidateHwnd(a1);
  v14 = v13;
  memset(&Msg, 0, sizeof(Msg));
  v82 = 0;
  if ( !v13 )
    return 0;
  v15 = -a2;
  if ( a2 >= 0 )
    v15 = a2;
  v16 = -a3;
  if ( a3 >= 0 )
    v16 = a3;
  if ( a4 )
  {
    Buf1 = *a4;
    v17 = _mm_cvtsi128_si32(_mm_srli_si128(Buf1, 12));
    v18 = _mm_cvtsi128_si32(_mm_srli_si128(Buf1, 8));
  }
  else
  {
    v18 = *((_DWORD *)v13 + 28) - *((_DWORD *)v13 + 26);
    v17 = *((_DWORD *)v13 + 29) - *((_DWORD *)v13 + 27);
    Buf1.m128i_i64[1] = __PAIR64__(v17, v18);
  }
  if ( !*((_QWORD *)v13 + 17) )
  {
    if ( v15 )
    {
      if ( v15 > v18 )
        goto LABEL_88;
      if ( !v16 )
        goto LABEL_12;
    }
    else if ( !v16 )
    {
      goto LABEL_88;
    }
    if ( v16 <= v17 )
    {
LABEL_12:
      DCEx = (HDC)NtUserGetDCEx(a1, 0, 65538);
      hdc = DCEx;
      if ( DCEx )
      {
        v20 = 0;
        v21 = 0;
        v64 = 0;
        hrgnSrc1 = 0;
        hrgn = 0;
        if ( (unsigned int)GetClipBox(DCEx, &rect) <= 1 )
        {
LABEL_63:
          ReleaseDC(hWnd, hdc);
          if ( hrgn )
            DeleteObject(hrgn);
          if ( v21 )
            DeleteObject(v21);
          return v20;
        }
        CompatibleBitmap = CreateCompatibleBitmap(hdc, v18, v17);
        if ( !CompatibleBitmap )
        {
          v21 = 0;
          goto LABEL_63;
        }
        CompatibleDC = CreateCompatibleDC(hdc);
        wParam = CompatibleDC;
        v24 = CompatibleDC;
        if ( !CompatibleDC )
          goto LABEL_80;
        h = SelectObject(CompatibleDC, CompatibleBitmap);
        SetBoundsRect(v24, 0, 5u);
        SendMessageW(hWnd, 0x317u, (WPARAM)wParam, (16LL * (a8 & 1)) | 0xC);
        if ( v76 )
        {
          v25 = wParam;
        }
        else
        {
          *(_QWORD *)&rect.left = 0;
          rect.right = *((_DWORD *)v14 + 28) - *((_DWORD *)v14 + 26);
          rect.bottom = *((_DWORD *)v14 + 29) - *((_DWORD *)v14 + 27);
          v25 = wParam;
          if ( memcmp_0(&Buf1, &rect, 0x10u) )
          {
            v51 = rect;
            SelectObject(wParam, h);
            DeleteObject(CompatibleBitmap);
            v17 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v51, 12));
            v18 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v51, 8));
            v52 = CreateCompatibleBitmap(hdc, v18, v17);
            CompatibleBitmap = v52;
            if ( !v52 )
              goto LABEL_61;
            SelectObject(wParam, v52);
            SendMessageW(hWnd, 0x317u, (WPARAM)wParam, (16LL * (a8 & 1)) | 0xC);
          }
        }
        BoundsRect = GetBoundsRect(v25, &v82, 0);
        if ( (BoundsRect & 1) == 0 || (BoundsRect & 2) != 0 )
        {
          hrgnSrc1 = CreateRectRgn(0, 0, 0, 0);
          if ( hrgnSrc1 )
          {
            hrgn = CreateRectRgn(0, 0, 0, 0);
            if ( hrgn )
            {
              x1 = 0;
              v27 = 0;
              Buf1 = 0;
              v28 = v17;
              cy = v17;
              x = 0;
              y1 = 0;
              y = 0;
              v62 = v18;
              if ( v15 )
              {
                v63 = 0;
                if ( v15 < 20 )
                {
                  v29 = 1;
                }
                else
                {
                  v29 = v15 / 10;
                  v28 = v17;
                }
              }
              else
              {
                v29 = 0;
                v63 = v18;
              }
              if ( v16 )
              {
                v60 = 0;
                if ( v16 < 20 )
                  v30 = 1;
                else
                  v30 = v16 / 10;
              }
              else
              {
                v30 = 0;
                v60 = v28;
              }
              v31 = 200;
              if ( a9 )
                v31 = a9;
              LODWORD(h) = v31 / 0xA;
              AdjustQsBits(2u);
              bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
              v56 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
              right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
              left = 0;
              while ( 1 )
              {
                if ( v15 )
                {
                  if ( (int)(v33 + v29) > v15 )
                    v29 = v15 - v33;
                  v53 = v29 + v33;
                  v63 = v53;
                  x = v15 - v53;
                  v62 = v18 - (v15 - v53);
                  if ( a2 >= 0 )
                  {
                    x1 = v15 - v53;
                    x = 0;
                  }
                }
                if ( v16 )
                {
                  if ( (int)(v32 + v30) > v16 )
                    v30 = v16 - v32;
                  v50 = v30 + v32;
                  v60 = v50;
                  y = v16 - v50;
                  cy = v17 - (v16 - v50);
                  if ( v69 >= 0 )
                  {
                    y1 = v16 - v50;
                    y = 0;
                  }
                }
                if ( (unsigned int)IsInsideMessagePumpHook() )
                  v36 = off_1800C8020(0, 0, v34, v35, 0);
                else
                  v36 = NtUserMsgWaitForMultipleObjectsEx(0, 0, v34, v35, 0);
                if ( !v36 )
                {
                  if ( PeekMessageW(&Msg, 0, 0x200u, 0x200u, 0x1C070000u) )
                  {
                    v48 = ValidateHwnd(Msg.hwnd);
                    if ( v48 )
                    {
                      v49 = (_WORD *)*((_QWORD *)v48 + 16);
                      if ( v49 )
                        v49 = (_WORD *)((char *)v49 + (_QWORD)v48 - *((_QWORD *)v48 + 1));
                      if ( *v49 == gatomReaderMode && PeekMessageW(&Msg, Msg.hwnd, 0x200u, 0x200u, 0x1C070001u) )
                        DispatchMessageWorker(&Msg, 0);
                    }
                  }
                }
                v37 = v30;
                if ( v69 < 0 )
                  v37 = -v30;
                v38 = v29;
                if ( a2 < 0 )
                  v38 = -v29;
                v64 = NtUserScrollWindowEx(hWnd, v38, v37, v76, v79, hrgnSrc1, &rect, a8);
                if ( !v64 )
                  break;
                v39 = bottom;
                v40 = left >= right || v56 >= bottom;
                v41 = rect.left >= rect.right || rect.top >= rect.bottom;
                if ( v40 )
                {
                  if ( v41 )
                  {
                    v27 = 0;
                    v46 = 0;
                    bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
                    v47 = 0;
                  }
                  else
                  {
                    v27 = rect;
                    v46 = rect;
                    bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)rect, 12));
                    v47 = rect;
                  }
                  right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v46, 8));
                  v56 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v47, 4));
                  Buf1 = (__m128i)v27;
                  left = v27.left;
                }
                else if ( !v41 )
                {
                  v42 = rect.left;
                  top = v56;
                  if ( left < rect.left )
                    v42 = left;
                  Buf1.m128i_i32[0] = v42;
                  if ( v56 >= rect.top )
                    top = rect.top;
                  left = v42;
                  Buf1.m128i_i32[1] = top;
                  v56 = top;
                  v44 = right;
                  if ( right <= rect.right )
                    v44 = rect.right;
                  Buf1.m128i_i32[2] = v44;
                  if ( bottom <= rect.bottom )
                    v39 = rect.bottom;
                  right = v44;
                  Buf1.m128i_i32[3] = v39;
                  v27 = (struct tagRECT)Buf1;
                  bottom = v39;
                }
                BitBlt(hdc, x, y, v62, cy, wParam, x1, y1, 0x80CC0020);
                SetRectRgn(hrgn, x, y, x + v62, y + cy);
                CombineRgn(hrgn, hrgnSrc1, hrgn, 4);
                NtUserRedrawWindow(hWnd, 0, hrgn, 517);
                v33 = v63;
                v32 = v60;
                if ( v63 >= v15 && v60 >= v16 )
                {
                  if ( v77 )
                    *v77 = v27;
                  if ( v78 )
                    SetRectRgn(v78, left, v56, right, bottom);
                  break;
                }
              }
            }
          }
        }
LABEL_61:
        DeleteDC(wParam);
        if ( !CompatibleBitmap )
        {
LABEL_62:
          v20 = v64;
          v21 = hrgnSrc1;
          goto LABEL_63;
        }
LABEL_80:
        DeleteObject(CompatibleBitmap);
        goto LABEL_62;
      }
      return 0;
    }
  }
LABEL_88:
  if ( a3 < 0 )
    v16 = -v16;
  if ( a2 < 0 )
    v15 = -v15;
  return NtUserScrollWindowEx(a1, (unsigned int)v15, (unsigned int)v16, v76, v79, v78, v77, a8 | 6);
}

```

## disassembly

```asm
0x180036cd0  mov     rax, rsp
0x180036cd3  push    rbp
0x180036cd4  push    rbx
0x180036cd5  push    rsi
0x180036cd6  push    rdi
0x180036cd7  push    r12
0x180036cd9  push    r13
0x180036cdb  push    r14
0x180036cdd  push    r15
0x180036cdf  lea     rbp, [rax-0D8h]
0x180036ce6  sub     rsp, 198h
0x180036ced  movaps  xmmword ptr [rax-58h], xmm6
0x180036cf1  mov     rax, cs:__security_cookie
0x180036cf8  xor     rax, rsp
0x180036cfb  mov     [rbp+0D0h+var_60], rax
0x180036cff  mov     rax, [rbp+0D0h+arg_20]
0x180036d06  xorps   xmm0, xmm0
0x180036d09  mov     [rbp+0D0h+var_B8], rax
0x180036d0d  xorps   xmm1, xmm1
0x180036d10  mov     rax, [rbp+0D0h+arg_28]
0x180036d17  mov     r12, r9
0x180036d1a  mov     [rbp+0D0h+var_C0], rax
0x180036d1e  mov     r15d, r8d
0x180036d21  mov     rax, [rbp+0D0h+arg_30]
0x180036d28  mov     ebx, edx
0x180036d2a  mov     [rbp+0D0h+var_C8], rax
0x180036d2e  mov     r14, rcx
0x180036d31  mov     [rbp+0D0h+var_D0], r9
0x180036d35  mov     [rbp+0D0h+var_100], r8d
0x180036d39  mov     [rbp+0D0h+var_130], edx
0x180036d3c  mov     [rbp+0D0h+hWnd], rcx
0x180036d40  movups  [rbp+0D0h+Buf1], xmm0
0x180036d44  movups  xmmword ptr [rbp+0D0h+rect.left], xmm1
0x180036d48  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180036d4d  xorps   xmm0, xmm0
0x180036d50  mov     rsi, rax
0x180036d53  movups  xmmword ptr [rbp+0D0h+Msg.hwnd], xmm0
0x180036d57  movups  xmmword ptr [rbp+0D0h+Msg.wParam], xmm0
0x180036d5b  movups  xmmword ptr [rbp+0D0h+Msg.time], xmm0
0x180036d5f  movups  xmmword ptr [rbp+0D0h+var_70.left], xmm0
0x180036d63  test    rax, rax
0x180036d66  jz      loc_180037478
0x180036d6c  mov     edi, ebx
0x180036d6e  neg     edi
0x180036d70  test    ebx, ebx
0x180036d72  cmovns  edi, ebx
0x180036d75  mov     ebx, r15d
0x180036d78  neg     ebx
0x180036d7a  test    r15d, r15d
0x180036d7d  cmovns  ebx, r15d
0x180036d81  test    r12, r12
0x180036d84  jz      loc_180037206
0x180036d8a  movups  xmm1, xmmword ptr [r12]
0x180036d8f  movdqa  xmm0, xmm1
0x180036d93  movaps  [rbp+0D0h+Buf1], xmm1
0x180036d97  psrldq  xmm0, 0Ch
0x180036d9c  psrldq  xmm1, 8
0x180036da1  movd    r12d, xmm0
0x180036da6  movd    r13d, xmm1
0x180036dab  cmp     qword ptr [rax+88h], 0
0x180036db3  jnz     loc_18003738C
0x180036db9  test    edi, edi
0x180036dbb  jz      loc_180037388
0x180036dc1  cmp     edi, r13d
0x180036dc4  jg      loc_18003738C
0x180036dca  test    ebx, ebx
0x180036dcc  jnz     loc_1800373A5
0x180036dd2  xor     edx, edx
0x180036dd4  mov     r8d, 10002h
0x180036dda  mov     rcx, r14
0x180036ddd  call    cs:__imp_NtUserGetDCEx
0x180036de3  mov     [rbp+0D0h+hdc], rax
0x180036de7  test    rax, rax
0x180036dea  jz      loc_180037478
0x180036df0  xor     r14d, r14d
0x180036df3  lea     rdx, [rbp+0D0h+rect]; lprect
0x180036df7  xor     r15d, r15d
0x180036dfa  mov     [rbp+0D0h+var_134], r14d
0x180036dfe  mov     rcx, rax; hdc
0x180036e01  mov     [rbp+0D0h+hrgnSrc1], r15
0x180036e05  mov     [rbp+0D0h+hrgn], r14
0x180036e09  call    cs:__imp_GetClipBox
0x180036e0f  cmp     eax, 1
0x180036e12  jbe     loc_1800371B8
0x180036e18  mov     rcx, [rbp+0D0h+hdc]; hdc
0x180036e1c  mov     r8d, r12d; cy
0x180036e1f  mov     edx, r13d; cx
0x180036e22  call    cs:__imp_CreateCompatibleBitmap
0x180036e28  mov     r15, rax
0x180036e2b  test    rax, rax
0x180036e2e  jz      loc_180037462
0x180036e34  mov     rcx, [rbp+0D0h+hdc]; hdc
0x180036e38  call    cs:__imp_CreateCompatibleDC
0x180036e3e  mov     [rbp+0D0h+wParam], rax
0x180036e42  mov     r14, rax
0x180036e45  test    rax, rax
0x180036e48  jz      loc_1800372F2
0x180036e4e  mov     rdx, r15; h
0x180036e51  mov     rcx, rax; hdc
0x180036e54  call    cs:__imp_SelectObject
0x180036e5a  xor     edx, edx; lprect
0x180036e5c  mov     rcx, r14; hdc
0x180036e5f  mov     [rbp+0D0h+h], rax
0x180036e63  lea     r8d, [rdx+5]; flags
0x180036e67  call    cs:__imp_SetBoundsRect
0x180036e6d  mov     r14d, [rbp+0D0h+arg_38]
0x180036e74  mov     edx, 317h; Msg
0x180036e79  mov     r8, [rbp+0D0h+wParam]; wParam
0x180036e7d  and     r14d, 1
0x180036e81  mov     rcx, [rbp+0D0h+hWnd]; hWnd
0x180036e85  shl     r14, 4
0x180036e89  or      r14, 0Ch
0x180036e8d  mov     r9, r14; lParam
0x180036e90  call    SendMessageW
0x180036e95  xor     eax, eax
0x180036e97  cmp     [rbp+0D0h+var_D0], rax
0x180036e9b  jz      loc_18003734E
0x180036ea1  mov     rsi, [rbp+0D0h+wParam]
0x180036ea5  xor     r8d, r8d; flags
0x180036ea8  lea     rdx, [rbp+0D0h+var_70]; lprect
0x180036eac  mov     rcx, rsi; hdc
0x180036eaf  call    cs:__imp_GetBoundsRect
0x180036eb5  test    al, 1
0x180036eb7  jnz     loc_1800373AF
0x180036ebd  xor     r9d, r9d; y2
0x180036ec0  xor     r8d, r8d; x2
0x180036ec3  xor     edx, edx; y1
0x180036ec5  xor     ecx, ecx; x1
0x180036ec7  call    cs:__imp_CreateRectRgn
0x180036ecd  mov     [rbp+0D0h+hrgnSrc1], rax
0x180036ed1  test    rax, rax
0x180036ed4  jz      loc_18003719D
0x180036eda  xor     r9d, r9d; y2
0x180036edd  xor     r8d, r8d; x2
0x180036ee0  xor     edx, edx; y1
0x180036ee2  xor     ecx, ecx; x1
0x180036ee4  call    cs:__imp_CreateRectRgn
0x180036eea  mov     [rbp+0D0h+hrgn], rax
0x180036eee  test    rax, rax
0x180036ef1  jz      loc_18003719D
0x180036ef7  mov     [rbp+0D0h+var_F8], 0
0x180036efe  xorps   xmm6, xmm6
0x180036f01  movaps  [rbp+0D0h+Buf1], xmm6
0x180036f05  mov     eax, r12d
0x180036f08  mov     [rbp+0D0h+var_140], eax
0x180036f0b  mov     ecx, 66666667h
0x180036f10  mov     [rbp+0D0h+x], 0
0x180036f17  mov     [rbp+0D0h+var_FC], 0
0x180036f1e  mov     [rbp+0D0h+y], 0
0x180036f25  mov     [rbp+0D0h+var_13C], r13d
0x180036f29  test    edi, edi
0x180036f2b  jnz     loc_1800373BC
0x180036f31  xor     r14d, r14d
0x180036f34  mov     [rbp+0D0h+var_138], r13d
0x180036f38  mov     r10d, r13d
0x180036f3b  test    ebx, ebx
0x180036f3d  jnz     loc_1800373E8
0x180036f43  xor     esi, esi
0x180036f45  mov     [rbp+0D0h+var_148], eax
0x180036f48  mov     r8d, eax
0x180036f4b  mov     eax, [rbp+0D0h+arg_40]
0x180036f51  mov     ecx, 0C8h
0x180036f56  test    eax, eax
0x180036f58  cmovnz  ecx, eax
0x180036f5b  mov     eax, 0CCCCCCCDh
0x180036f60  mul     ecx
0x180036f62  mov     ecx, 2; unsigned int
0x180036f67  shr     edx, 3
0x180036f6a  mov     dword ptr [rbp+0D0h+h], edx
0x180036f6d  call    ?AdjustQsBits@@YAKK@Z; AdjustQsBits(ulong)
0x180036f72  xorps   xmm0, xmm0
0x180036f75  mov     [rbp+0D0h+var_144], eax
0x180036f78  psrldq  xmm0, 0Ch
0x180036f7d  xorps   xmm1, xmm1
0x180036f80  movd    [rsp+1D0h+bottom], xmm0
0x180036f86  mov     r11d, eax
0x180036f89  xorps   xmm0, xmm0
0x180036f8c  psrldq  xmm1, 8
0x180036f91  psrldq  xmm0, 4
0x180036f96  movd    dword ptr [rsp+60h], xmm0
0x180036f9c  movd    [rsp+1D0h+right], xmm1
0x180036fa2  movss   dword ptr [rsp+70h], xmm6
0x180036fa8  test    edi, edi
0x180036faa  jnz     loc_18003740D
0x180036fb0  test    ebx, ebx
0x180036fb2  jnz     loc_18003730E
0x180036fb8  call    ?IsInsideMessagePumpHook@@YAHXZ; IsInsideMessagePumpHook(void)
0x180036fbd  mov     r8d, edx
0x180036fc0  mov     [rsp+1D0h+cy], 0
0x180036fc8  xor     ecx, ecx
0x180036fca  xor     edx, edx
0x180036fcc  mov     r9d, r11d
0x180036fcf  test    eax, eax
0x180036fd1  jnz     loc_180037294
0x180036fd7  call    cs:__imp_NtUserMsgWaitForMultipleObjectsEx
0x180036fdd  test    eax, eax
0x180036fdf  jz      loc_1800372A5
0x180036fe5  cmp     [rbp+0D0h+var_100], 0
0x180036fe9  mov     r8d, esi
0x180036fec  jge     short loc_180036FF1
0x180036fee  neg     r8d
0x180036ff1  cmp     [rbp+0D0h+var_130], 0
0x180036ff5  mov     edx, r14d
0x180036ff8  jl      loc_18003742E
0x180036ffe  mov     eax, [rbp+0D0h+arg_38]
0x180037004  mov     r9, [rbp+0D0h+var_D0]
0x180037008  mov     rcx, [rbp+0D0h+hWnd]
0x18003700c  mov     [rsp+1D0h+y1], eax
0x180037010  lea     rax, [rbp+0D0h+rect]
0x180037014  mov     qword ptr [rsp+1D0h+x1], rax
0x180037019  mov     rax, [rbp+0D0h+hrgnSrc1]
0x18003701d  mov     [rsp+1D0h+hdcSrc], rax
0x180037022  mov     rax, [rbp+0D0h+var_B8]
0x180037026  mov     qword ptr [rsp+1D0h+cy], rax
0x18003702b  call    cs:__imp_NtUserScrollWindowEx
0x180037031  mov     [rbp+0D0h+var_134], eax
0x180037034  test    eax, eax
0x180037036  jz      loc_18003719D
0x18003703c  mov     eax, [rsp+70h]
0x180037040  mov     r11d, [rsp+1D0h+bottom]
0x180037045  cmp     eax, [rsp+1D0h+right]
0x180037049  jge     loc_180037223
0x18003704f  cmp     [rsp+60h], r11d
0x180037054  jge     loc_180037223
0x18003705a  xor     ecx, ecx
0x18003705c  mov     r9d, [rbp+0D0h+rect.left]
0x180037060  mov     r10d, [rbp+0D0h+rect.right]
0x180037064  mov     edx, [rbp+0D0h+rect.bottom]
0x180037067  mov     r8d, [rbp+0D0h+rect.top]
0x18003706b  cmp     r9d, r10d
0x18003706e  jge     loc_18003722D
0x180037074  cmp     r8d, edx
0x180037077  jge     loc_18003722D
0x18003707d  xor     eax, eax
0x18003707f  test    ecx, ecx
0x180037081  jnz     loc_180037237
0x180037087  test    eax, eax
0x180037089  jnz     short loc_1800370D7
0x18003708b  cmp     [rsp+70h], r9d
0x180037090  mov     ecx, r9d
0x180037093  mov     eax, [rsp+60h]
0x180037097  cmovl   ecx, [rsp+70h]
0x18003709c  cmp     eax, r8d
0x18003709f  mov     dword ptr [rbp+0D0h+Buf1], ecx
0x1800370a2  cmovge  eax, r8d
0x1800370a6  mov     [rsp+70h], ecx
0x1800370aa  mov     dword ptr [rbp+0D0h+Buf1+4], eax
0x1800370ad  mov     [rsp+60h], eax
0x1800370b1  mov     eax, [rsp+1D0h+right]
0x1800370b5  cmp     eax, r10d
0x1800370b8  cmovle  eax, r10d
0x1800370bc  cmp     r11d, edx
0x1800370bf  mov     dword ptr [rbp+0D0h+Buf1+8], eax
0x1800370c2  cmovle  r11d, edx
0x1800370c6  mov     [rsp+1D0h+right], eax
0x1800370ca  mov     dword ptr [rbp+0D0h+Buf1+0Ch], r11d
0x1800370ce  movaps  xmm6, [rbp+0D0h+Buf1]
0x1800370d2  mov     [rsp+1D0h+bottom], r11d
0x1800370d7  mov     eax, [rbp+0D0h+var_FC]
0x1800370da  mov     r9d, [rbp+0D0h+var_13C]; cx
0x1800370de  mov     r8d, [rbp+0D0h+y]; y
0x1800370e2  mov     edx, [rbp+0D0h+x]; x
0x1800370e5  mov     rcx, [rbp+0D0h+hdc]; hdc
0x1800370e9  mov     dword ptr [rsp+40h], 80CC0020h; rop
0x1800370f1  mov     [rsp+1D0h+y1], eax; y1
0x1800370f5  mov     eax, [rbp+0D0h+var_F8]
0x1800370f8  mov     [rsp+1D0h+x1], eax; x1
0x1800370fc  mov     rax, [rbp+0D0h+wParam]
0x180037100  mov     [rsp+1D0h+hdcSrc], rax; hdcSrc
0x180037105  mov     eax, [rbp+0D0h+var_140]
0x180037108  mov     [rsp+1D0h+cy], eax; cy
0x18003710c  call    cs:__imp_BitBlt
0x180037112  mov     eax, [rbp+0D0h+var_140]
0x180037115  mov     r9d, [rbp+0D0h+var_13C]
0x180037119  add     eax, [rbp+0D0h+y]
0x18003711c  add     r9d, [rbp+0D0h+x]; right
0x180037120  mov     r8d, [rbp+0D0h+y]; top
0x180037124  mov     edx, [rbp+0D0h+x]; left
0x180037127  mov     rcx, [rbp+0D0h+hrgn]; hrgn
0x18003712b  mov     [rsp+1D0h+cy], eax; bottom
0x18003712f  call    cs:__imp_SetRectRgn
0x180037135  mov     r8, [rbp+0D0h+hrgn]; hrgnSrc2
0x180037139  mov     r9d, 4; iMode
0x18003713f  mov     rdx, [rbp+0D0h+hrgnSrc1]; hrgnSrc1
0x180037143  mov     rcx, r8; hrgnDst
0x180037146  call    cs:__imp_CombineRgn
0x18003714c  mov     r8, [rbp+0D0h+hrgn]
0x180037150  mov     r9d, 205h
0x180037156  mov     rcx, [rbp+0D0h+hWnd]
0x18003715a  xor     edx, edx
0x18003715c  call    cs:__imp_NtUserRedrawWindow
0x180037162  mov     r10d, [rbp+0D0h+var_138]
0x180037166  mov     r8d, [rbp+0D0h+var_148]
0x18003716a  mov     edx, dword ptr [rbp+0D0h+h]
0x18003716d  mov     r11d, [rbp+0D0h+var_144]
0x180037171  cmp     r10d, edi
0x180037174  jl      loc_180036FA8
0x18003717a  cmp     r8d, ebx
0x18003717d  jl      loc_180036FA8
0x180037183  mov     rax, [rbp+0D0h+var_C8]
  ... truncated ...
```
