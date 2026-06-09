# xxxStaticPaint(tagSTAT *,HDC__ *,int)

- ea: `0x18003bfac`
- end: `0x18003c414`
- name: `?xxxStaticPaint@@YAXPEAUtagSTAT@@PEAUHDC__@@H@Z`
- size: `1128`
- prototype: `void(struct tagSTAT *, HDC, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18003b448`
- `0x180051d40`

## callees

- `0x180005d48`
- `0x18000cf20`
- `0x18003bfac`
- `0x18003c41c`
- `0x18003c588`
- `0x18003c8b0`
- `0x18003dfa0`
- `0x18003ed00`
- `0x18003f5d0`
- `0x1800651f0`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserGetIconSize` at `0x18009d597`
- `win32u!NtUserGetIconSize` at `0x18009d597`
- `win32u!NtUserGetControlBrush` at `0x18003c06d`
- `win32u!NtUserGetControlBrush` at `0x18003c06d`
- `ntdll!RtlLeaveCriticalSection` at `0x18009d828`
- `ntdll!RtlLeaveCriticalSection` at `0x18009d828`
- `GDI32!SetBkMode` at `0x18003c05b`
- `GDI32!SetBkMode` at `0x18003c05b`
- `GDI32!SelectObject` at `0x18003c1a1`
- `GDI32!SelectObject` at `0x18003c253`
- `GDI32!SelectObject` at `0x18009d718`
- `GDI32!SelectObject` at `0x18009d81b`
- `GDI32!SelectObject` at `0x18003c1a1`
- `GDI32!SelectObject` at `0x18003c253`
- `GDI32!SelectObject` at `0x18009d718`
- `GDI32!SelectObject` at `0x18009d81b`
- `GDI32!IntersectClipRect` at `0x18003c037`
- `GDI32!IntersectClipRect` at `0x18003c037`
- `GDI32!SetTextAlign` at `0x18003c31e`
- `GDI32!SetTextAlign` at `0x18003c409`
- `GDI32!SetTextAlign` at `0x18003c31e`
- `GDI32!SetTextAlign` at `0x18003c409`
- `GDI32!GetTextAlign` at `0x18003bff6`
- `GDI32!GetTextAlign` at `0x18003bff6`
- `GDI32!GetObjectW` at `0x18009d6ae`
- `GDI32!GetObjectW` at `0x18009d6ae`
- `GDI32!PlayEnhMetaFile` at `0x18003c3c6`
- `GDI32!PlayEnhMetaFile` at `0x18003c3c6`
- `GDI32!ExcludeClipRect` at `0x18009d7bc`
- `GDI32!ExcludeClipRect` at `0x18009d7bc`
- `GDI32!StretchBlt` at `0x18009d76a`
- `GDI32!StretchBlt` at `0x18009d76a`
- `GDI32!PolyPatBlt` at `0x18009d7fd`
- `GDI32!PolyPatBlt` at `0x18009d7fd`
- `GDI32!SetLayoutWidth` at `0x18003c38c`
- `GDI32!SetLayoutWidth` at `0x18009d67d`
- `GDI32!SetLayoutWidth` at `0x18003c38c`
- `GDI32!SetLayoutWidth` at `0x18009d67d`
- `GDI32!CreateSolidBrush` at `0x18009d78c`
- `GDI32!CreateSolidBrush` at `0x18009d78c`
- `GDI32!GetPixel` at `0x18009d784`
- `GDI32!GetPixel` at `0x18009d784`
- `GDI32!SetBrushOrgEx` at `0x18009d613`
- `GDI32!SetBrushOrgEx` at `0x18009d664`
- `GDI32!SetBrushOrgEx` at `0x18009d613`
- `GDI32!SetBrushOrgEx` at `0x18009d664`
- `GDI32!ExtTextOutW` at `0x18009d876`
- `GDI32!ExtTextOutW` at `0x18009d876`
- `GDI32!DeleteObject` at `0x18009d806`
- `GDI32!DeleteObject` at `0x18009d806`

## pseudocode

```c
void __fastcall xxxStaticPaint(struct tagSTAT *a1, HDC a2, int a3)
{
  LPARAM v3; // rdi
  HWND v5; // r12
  UINT TextAlign; // eax
  bool v9; // zf
  unsigned __int8 v10; // r15
  HBRUSH ControlBrush; // rax
  LPARAM v12; // rsi
  HBRUSH v13; // rdx
  HWND v14; // rcx
  __int64 v15; // r9
  void *v16; // rdx
  unsigned int v17; // ecx
  WPARAM v18; // rdx
  unsigned int v19; // ecx
  HWND v20; // rcx
  __int64 v21; // rcx
  HWND v22; // rcx
  HBRUSH v23; // r9
  unsigned int v24; // eax
  unsigned int v25; // r15d
  HENHMETAFILE v26; // rdx
  unsigned int v27; // ecx
  __int64 v28; // r9
  const WCHAR *v29; // r9
  int v30; // r8d
  int v31; // eax
  int v32; // r8d
  int v33; // edx
  void *v34; // rcx
  int v35; // esi
  HGDIOBJ v36; // r14
  COLORREF Pixel; // eax
  HBRUSH SolidBrush; // rsi
  UINT v39; // ecx
  int v40; // eax
  int cyWidth; // [rsp+60h] [rbp-A0h] BYREF
  int cxWidth; // [rsp+64h] [rbp-9Ch] BYREF
  struct tagPOINT pt; // [rsp+68h] [rbp-98h] BYREF
  UINT align; // [rsp+70h] [rbp-90h]
  HGDIOBJ h; // [rsp+78h] [rbp-88h]
  _QWORD v46[4]; // [rsp+80h] [rbp-80h] BYREF
  LPARAM lParam[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v48; // [rsp+B0h] [rbp-50h]
  HDC v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+C8h] [rbp-38h]
  int v51; // [rsp+CCh] [rbp-34h]
  int v52; // [rsp+D0h] [rbp-30h]
  int v53; // [rsp+D4h] [rbp-2Ch]
  __int64 v54; // [rsp+D8h] [rbp-28h]
  int left[4]; // [rsp+E0h] [rbp-20h] BYREF
  RECT rect; // [rsp+F0h] [rbp-10h] BYREF

  v3 = *(_QWORD *)a1;
  *(_OWORD *)left = 0;
  h = 0;
  v5 = *(HWND *)v3;
  TextAlign = GetTextAlign(a2);
  v9 = (*(_BYTE *)(v3 + 25) & 0x20) == 0;
  align = TextAlign;
  if ( !v9 )
    SetTextAlign(a2, TextAlign | 0x100);
  v10 = *(_BYTE *)(v3 + 28) & 0x1F;
  GetClientRect(v3, left);
  if ( a3 )
    IntersectClipRect(a2, left[0], left[1], left[2], left[3]);
  if ( (*((_BYTE *)qword_1800AA410 + v10) & 8) != 0 )
  {
    v16 = (void *)*((_QWORD *)a1 + 1);
    if ( v16 )
      h = SelectObject(a2, v16);
  }
  SetBkMode(a2, 2);
  ControlBrush = (HBRUSH)NtUserGetControlBrush(v5, a2, 312);
  v12 = *(_QWORD *)(v3 + 48);
  v13 = ControlBrush;
  *(_QWORD *)&rect.left = ControlBrush;
  if ( v12 )
    v12 = v3 + v12 - *(_QWORD *)(v3 + 8);
  if ( (*((_BYTE *)qword_1800AA410 + v10) & 4) != 0 && (*((_BYTE *)a1 + 32) & 1) == 0 )
  {
    v14 = 0;
    if ( v12 )
      v14 = *(HWND *)v12;
    PaintRect(v14, v5, a2, ControlBrush, (struct tagRECT *)left);
    v13 = *(HBRUSH *)&rect.left;
  }
  if ( v10 > 8u )
  {
    if ( v10 != 9 )
    {
      if ( v10 == 11 )
      {
        v27 = *(_DWORD *)(v3 + 184);
        if ( v27 )
        {
          v28 = *(_QWORD *)(v3 + 192);
          if ( v28 )
            v29 = (const WCHAR *)(v3 + v28 - *(_QWORD *)(v3 + 8));
          else
            v29 = 0;
          v39 = v27 >> 1;
        }
        else
        {
          v29 = (const WCHAR *)&szNull;
          v39 = 0;
        }
        if ( *(char *)(v3 + 28) >= 0 )
        {
          if ( (*(_BYTE *)(v3 + 27) & 0x40) != 0 )
            v40 = 0x100000;
          else
            v40 = (*((_BYTE *)a1 + 32) & 1) << 21;
          PSMTextOut((_DWORD)a2, left[0], left[1], (_DWORD)v29, v39, v40);
        }
        else
        {
          ExtTextOutW(a2, left[0], left[1], 6u, (const RECT *)left, v29, v39, 0);
        }
        goto LABEL_24;
      }
      if ( v10 != 12 )
      {
        switch ( v10 )
        {
          case 0xDu:
            v17 = *(unsigned __int8 *)(v3 + 31);
            v18 = *(unsigned int *)(v3 + 320);
            v50 = left[0];
            v51 = left[1];
            v19 = (v17 >> 1) & 4;
            v9 = (*(_BYTE *)(v3 + 27) & 0x40) == 0;
            v52 = left[2];
            v53 = left[3];
            lParam[1] = 0x100000000LL;
            LODWORD(lParam[0]) = 5;
            HIDWORD(lParam[0]) = v18;
            *(_QWORD *)&v48 = v19;
            *((_QWORD *)&v48 + 1) = v5;
            v49 = a2;
            v54 = 0;
            if ( !v9 )
              LODWORD(v48) = v19 | 0x100;
            v20 = 0;
            if ( v12 )
              v20 = *(HWND *)v12;
            SendMessageW(v20, 0x2Bu, v18, (LPARAM)lParam);
            break;
          case 0xEu:
            v34 = (void *)*((_QWORD *)a1 + 2);
            if ( v34 )
            {
              *(_OWORD *)lParam = 0;
              v48 = 0;
              rect = 0;
              if ( GetObjectW(v34, 32, lParam) )
              {
                if ( (*(_BYTE *)(v3 + 29) & 2) != 0 )
                {
                  if ( SHIDWORD(lParam[0]) < left[2] || (v35 = 0, SLODWORD(lParam[1]) < left[3]) )
                    v35 = 1;
                  left[0] = (left[2] - HIDWORD(lParam[0])) >> 1;
                  left[2] = HIDWORD(lParam[0]) + left[0];
                  left[1] = (left[3] - LODWORD(lParam[1])) >> 1;
                  left[3] = left[1] + LODWORD(lParam[1]);
                }
                else
                {
                  v35 = 0;
                }
                if ( (unsigned int)AcquireGlobalGdiResources() )
                {
                  v36 = SelectObject(ghdcBits2, *((HGDIOBJ *)a1 + 2));
                  StretchBlt(
                    a2,
                    left[0],
                    left[1],
                    left[2] - left[0],
                    left[3] - left[1],
                    ghdcBits2,
                    0,
                    0,
                    SHIDWORD(lParam[0]),
                    lParam[1],
                    0x80CC0020);
                  if ( v35 )
                  {
                    Pixel = GetPixel(ghdcBits2, 0, 0);
                    SolidBrush = CreateSolidBrush(Pixel);
                    if ( SolidBrush )
                    {
                      ExcludeClipRect(a2, left[0], left[1], left[2], left[3]);
                      GetClientRect(v3, &rect);
                      v46[1] = *(_QWORD *)&rect.right;
                      v46[0] = 0;
                      v46[2] = SolidBrush;
                      PolyPatBlt(a2, 15728673, v46, 1, 0);
                      DeleteObject(SolidBrush);
                    }
                  }
                  if ( v36 )
                    SelectObject(ghdcBits2, v36);
                  RtlLeaveCriticalSection(&gcsHdc);
                }
              }
            }
            break;
          case 0xFu:
            v26 = (HENHMETAFILE)*((_QWORD *)a1 + 2);
            if ( v26 )
            {
              rect = *(RECT *)left;
              PlayEnhMetaFile(a2, v26, &rect);
            }
            break;
          case 0x12u:
            DrawEdge(a2, (LPRECT)left, 6u, 0xFu);
            break;
        }
        goto LABEL_24;
      }
      goto LABEL_22;
    }
    v15 = 160;
LABEL_38:
    DrawFrame(a2, left, 1, v15);
    goto LABEL_24;
  }
  if ( v10 == 8 )
  {
    v15 = 128;
    goto LABEL_38;
  }
  if ( !v10 || v10 == 1 || v10 == 2 )
  {
LABEL_22:
    if ( *(_DWORD *)(v3 + 184) )
      DrawStateW(
        a2,
        *(HBRUSH *)(gpsi + 4760),
        StaticCallback,
        v3,
        1u,
        left[0],
        left[1],
        left[2] - left[0],
        left[3] - left[1],
        4 * (*(_BYTE *)(v3 + 31) & 8));
    goto LABEL_24;
  }
  if ( v10 != 3 )
  {
    switch ( v10 )
    {
      case 4u:
        v23 = *(HBRUSH *)(gpsi + 4864);
        break;
      case 5u:
        v23 = *(HBRUSH *)(gpsi + 4824);
        break;
      case 6u:
        v23 = *(HBRUSH *)(gpsi + 4856);
        break;
      case 7u:
        v15 = 168;
        goto LABEL_38;
      default:
        goto LABEL_24;
    }
    v22 = 0;
    if ( v12 )
      v22 = *(HWND *)v12;
LABEL_51:
    PaintRect(v22, v5, a2, v23, (struct tagRECT *)left);
    goto LABEL_24;
  }
  v21 = *((_QWORD *)a1 + 2);
  if ( !v21 )
  {
    v22 = 0;
    if ( v12 )
      v22 = *(HWND *)v12;
    v23 = v13;
    goto LABEL_51;
  }
  v9 = (*(_BYTE *)(v3 + 26) & 0x40) == 0;
  cxWidth = 0;
  cyWidth = 0;
  pt = 0;
  if ( v9 )
  {
    v25 = 0;
  }
  else
  {
    v24 = SetLayoutWidth(a2, 0xFFFFFFFFLL, 0);
    v21 = *((_QWORD *)a1 + 2);
    v25 = v24;
  }
  if ( (*(_BYTE *)(v3 + 29) & 2) != 0 )
  {
    NtUserGetIconSize(v21, *((unsigned int *)a1 + 7), &cxWidth, &cyWidth);
    v30 = cyWidth >> 1;
    left[0] = (left[2] - cxWidth) / 2;
    left[2] = cxWidth + left[0];
    left[1] = (left[3] - (cyWidth >> 1)) / 2;
    left[3] = (cyWidth >> 1) + left[1];
  }
  else
  {
    v30 = left[3] - left[1];
    cxWidth = left[2] - left[0];
  }
  v31 = *(_WORD *)(v12 + 42) & 0x2FFF;
  cyWidth = v30;
  if ( v31 == 669 )
  {
    v32 = 0;
    v33 = 0;
  }
  else
  {
    v32 = *(_DWORD *)(v12 + 108) - *(_DWORD *)(v3 + 108);
    v33 = *(_DWORD *)(v12 + 104) - *(_DWORD *)(v3 + 104);
  }
  SetBrushOrgEx(a2, v33, v32, &pt);
  DrawIconEx(a2, left[0], left[1], *((HICON *)a1 + 2), cxWidth, cyWidth, *((_DWORD *)a1 + 7), *(HBRUSH *)&rect.left, 3u);
  SetBrushOrgEx(a2, pt.x, pt.y, 0);
  if ( (*(_BYTE *)(v3 + 26) & 0x40) != 0 )
    SetLayoutWidth(a2, 0xFFFFFFFFLL, v25);
LABEL_24:
  if ( h )
    SelectObject(a2, h);
  if ( (*(_BYTE *)(v3 + 25) & 0x20) != 0 )
    SetTextAlign(a2, align);
}

```

## disassembly

```asm
0x18003bfac  mov     [rsp-8+arg_10], rbx
0x18003bfb1  push    rbp
0x18003bfb2  push    rsi
0x18003bfb3  push    rdi
0x18003bfb4  push    r12
0x18003bfb6  push    r13
0x18003bfb8  push    r14
0x18003bfba  push    r15
0x18003bfbc  lea     rbp, [rsp-10h]
0x18003bfc1  sub     rsp, 110h
0x18003bfc8  mov     rax, cs:__security_cookie
0x18003bfcf  xor     rax, rsp
0x18003bfd2  mov     [rbp+40h+var_40], rax
0x18003bfd6  mov     rdi, [rcx]
0x18003bfd9  xorps   xmm0, xmm0
0x18003bfdc  mov     r14, rcx
0x18003bfdf  xor     eax, eax
0x18003bfe1  movups  xmmword ptr [rbp+40h+left], xmm0
0x18003bfe5  mov     rcx, rdx; hdc
0x18003bfe8  mov     [rsp+140h+h], rax
0x18003bfed  mov     r12, [rdi]
0x18003bff0  mov     esi, r8d
0x18003bff3  mov     rbx, rdx
0x18003bff6  call    cs:__imp_GetTextAlign
0x18003bffc  test    byte ptr [rdi+19h], 20h
0x18003c000  mov     [rsp+140h+align], eax
0x18003c004  jnz     loc_18003C315
0x18003c00a  mov     r15b, [rdi+1Ch]
0x18003c00e  lea     rdx, [rbp+40h+left]
0x18003c012  mov     rcx, rdi
0x18003c015  and     r15b, 1Fh
0x18003c019  call    _GetClientRect
0x18003c01e  test    esi, esi
0x18003c020  jz      short loc_18003C03D
0x18003c022  mov     eax, [rbp+40h+left+0Ch]
0x18003c025  mov     rcx, rbx; hdc
0x18003c028  mov     r9d, [rbp+40h+left+8]; right
0x18003c02c  mov     r8d, [rbp+40h+left+4]; top
0x18003c030  mov     edx, [rbp+40h+left]; left
0x18003c033  mov     [rsp+140h+bottom], eax; bottom
0x18003c037  call    cs:__imp_IntersectClipRect
0x18003c03d  movzx   r13d, r15b
0x18003c041  lea     rax, qword_1800AA410
0x18003c048  test    byte ptr [rax+r13], 8
0x18003c04d  jnz     loc_18003C243
0x18003c053  mov     edx, 2; mode
0x18003c058  mov     rcx, rbx; hdc
0x18003c05b  call    cs:__imp_SetBkMode
0x18003c061  mov     r8d, 138h
0x18003c067  mov     rdx, rbx
0x18003c06a  mov     rcx, r12
0x18003c06d  call    cs:__imp_NtUserGetControlBrush
0x18003c073  mov     rsi, [rdi+30h]
0x18003c077  mov     rdx, rax
0x18003c07a  mov     qword ptr [rbp+40h+rect.left], rax
0x18003c07e  test    rsi, rsi
0x18003c081  jz      loc_18003C2E0
0x18003c087  sub     rsi, [rdi+8]
0x18003c08b  add     rsi, rdi
0x18003c08e  lea     rax, qword_1800AA410
0x18003c095  test    byte ptr [rax+r13], 4
0x18003c09a  jz      loc_18003C329
0x18003c0a0  xor     r13d, r13d
0x18003c0a3  test    byte ptr [r14+20h], 1
0x18003c0a8  jnz     short loc_18003C0D0
0x18003c0aa  mov     ecx, r13d
0x18003c0ad  test    rsi, rsi
0x18003c0b0  jz      short loc_18003C0B5
0x18003c0b2  mov     rcx, [rsi]; HWND
0x18003c0b5  lea     rax, [rbp+40h+left]
0x18003c0b9  mov     r9, rdx; HBRUSH
0x18003c0bc  mov     rdx, r12; HWND
0x18003c0bf  mov     qword ptr [rsp+140h+bottom], rax; struct tagRECT *
0x18003c0c4  mov     r8, rbx; HDC
0x18003c0c7  call    ?PaintRect@@YAHPEAUHWND__@@0PEAUHDC__@@PEAUHBRUSH__@@PEAUtagRECT@@@Z; PaintRect(HWND__ *,HWND__ *,HDC__ *,HBRUSH__ *,tagRECT *)
0x18003c0cc  mov     rdx, qword ptr [rbp+40h+rect.left]
0x18003c0d0  movzx   ecx, r15b
0x18003c0d4  cmp     ecx, 8
0x18003c0d7  jbe     loc_18003C1D8
0x18003c0dd  sub     ecx, 9
0x18003c0e0  jz      loc_18003C3F7
0x18003c0e6  sub     ecx, 2
0x18003c0e9  jz      loc_18003C3D1
0x18003c0ef  sub     ecx, 1
0x18003c0f2  jz      short loc_18003C12A
0x18003c0f4  sub     ecx, 1
0x18003c0f7  jz      loc_18003C263
0x18003c0fd  sub     ecx, 1
0x18003c100  jz      loc_18009D689
0x18003c106  sub     ecx, 1
0x18003c109  jz      loc_18003C3A9
0x18003c10f  cmp     ecx, 3
0x18003c112  jnz     short loc_18003C191
0x18003c114  lea     r9d, [rcx+0Ch]; grfFlags
0x18003c118  lea     r8d, [rcx+3]; edge
0x18003c11c  mov     rcx, rbx; hdc
0x18003c11f  lea     rdx, [rbp+40h+left]; qrc
0x18003c123  call    DrawEdge
0x18003c128  jmp     short loc_18003C191
0x18003c12a  cmp     [rdi+0B8h], r13d
0x18003c131  jz      short loc_18003C191
0x18003c133  mov     r8d, [rbp+40h+left+4]
0x18003c137  mov     ecx, [rbp+40h+left]
0x18003c13a  movzx   r9d, byte ptr [rdi+1Fh]
0x18003c13f  mov     edx, [rbp+40h+left+0Ch]
0x18003c142  and     r9d, 8
0x18003c146  mov     eax, [rbp+40h+left+8]
0x18003c149  sub     edx, r8d
0x18003c14c  shl     r9d, 2
0x18003c150  sub     eax, ecx
0x18003c152  mov     [rsp+140h+uFlags], r9d; uFlags
0x18003c157  mov     r9, rdi; lData
0x18003c15a  mov     [rsp+140h+cy], edx; cy
0x18003c15e  mov     rdx, cs:gpsi
0x18003c165  mov     dword ptr [rsp+140h+hbrFlickerFreeDraw], eax; cx
0x18003c169  mov     [rsp+140h+y], r8d; y
0x18003c16e  lea     r8, ?StaticCallback@@YAHPEAUHDC__@@_J_KHH@Z; qfnCallBack
0x18003c175  mov     [rsp+140h+x], ecx; x
0x18003c179  mov     rcx, rbx; hdc
0x18003c17c  mov     rdx, [rdx+1298h]; hbrFore
0x18003c183  mov     qword ptr [rsp+140h+bottom], 1; wData
0x18003c18c  call    DrawStateW
0x18003c191  mov     rax, [rsp+140h+h]
0x18003c196  test    rax, rax
0x18003c199  jz      short loc_18003C1A7
0x18003c19b  mov     rdx, rax; h
0x18003c19e  mov     rcx, rbx; hdc
0x18003c1a1  call    cs:__imp_SelectObject
0x18003c1a7  test    byte ptr [rdi+19h], 20h
0x18003c1ab  jnz     loc_18003C402
0x18003c1b1  mov     rcx, [rbp+40h+var_40]
0x18003c1b5  xor     rcx, rsp; StackCookie
0x18003c1b8  call    __security_check_cookie
0x18003c1bd  mov     rbx, [rsp+140h+arg_10]
0x18003c1c5  add     rsp, 110h
0x18003c1cc  pop     r15
0x18003c1ce  pop     r14
0x18003c1d0  pop     r13
0x18003c1d2  pop     r12
0x18003c1d4  pop     rdi
0x18003c1d5  pop     rsi
0x18003c1d6  pop     rbp
0x18003c1d7  retn
0x18003c1d8  jz      loc_18003C39E
0x18003c1de  test    r15b, r15b
0x18003c1e1  jz      loc_18003C12A
0x18003c1e7  sub     ecx, 1
0x18003c1ea  jz      loc_18003C12A
0x18003c1f0  sub     ecx, 1
0x18003c1f3  jz      loc_18003C12A
0x18003c1f9  sub     ecx, 1
0x18003c1fc  jz      loc_18003C2E5
0x18003c202  sub     ecx, 1
0x18003c205  jz      loc_18003C357
0x18003c20b  sub     ecx, 1
0x18003c20e  jz      loc_18003C344
0x18003c214  sub     ecx, 1
0x18003c217  jz      loc_18003C331
0x18003c21d  cmp     ecx, 1
0x18003c220  jnz     loc_18003C191
0x18003c226  mov     r9d, 0A8h
0x18003c22c  mov     r8d, 1
0x18003c232  lea     rdx, [rbp+40h+left]
0x18003c236  mov     rcx, rbx
0x18003c239  call    DrawFrame
0x18003c23e  jmp     loc_18003C191
0x18003c243  mov     rdx, [r14+8]; h
0x18003c247  test    rdx, rdx
0x18003c24a  jz      loc_18003C053
0x18003c250  mov     rcx, rbx; hdc
0x18003c253  call    cs:__imp_SelectObject
0x18003c259  mov     [rsp+140h+h], rax
0x18003c25e  jmp     loc_18003C053
0x18003c263  mov     eax, [rbp+40h+left]
0x18003c266  movzx   ecx, byte ptr [rdi+1Fh]
0x18003c26a  mov     edx, [rdi+140h]
0x18003c270  mov     [rbp+40h+var_78], eax
0x18003c273  mov     eax, [rbp+40h+left+4]
0x18003c276  shr     ecx, 1
0x18003c278  mov     [rbp+40h+var_74], eax
0x18003c27b  and     ecx, 4
0x18003c27e  test    byte ptr [rdi+1Bh], 40h
0x18003c282  mov     eax, [rbp+40h+left+8]
0x18003c285  mov     [rbp+40h+var_70], eax
0x18003c288  mov     eax, [rbp+40h+left+0Ch]
0x18003c28b  mov     qword ptr [rbp+40h+var_90], r13
0x18003c28f  mov     [rbp+40h+var_6C], eax
0x18003c292  mov     dword ptr [rbp+40h+lParam+8], r13d
0x18003c296  mov     dword ptr [rbp+40h+lParam], 5
0x18003c29d  mov     dword ptr [rbp+40h+lParam+4], edx
0x18003c2a0  mov     dword ptr [rbp+40h+lParam+0Ch], 1
0x18003c2a7  mov     dword ptr [rbp+40h+var_90], ecx
0x18003c2aa  mov     qword ptr [rbp+40h+var_90+8], r12
0x18003c2ae  mov     [rbp+40h+var_80], rbx
0x18003c2b2  mov     [rbp+40h+var_68], r13
0x18003c2b6  jz      short loc_18003C2BF
0x18003c2b8  bts     ecx, 8
0x18003c2bc  mov     dword ptr [rbp+40h+var_90], ecx
0x18003c2bf  mov     r8, rdx; wParam
0x18003c2c2  mov     rcx, r13
0x18003c2c5  test    rsi, rsi
0x18003c2c8  jz      short loc_18003C2CD
0x18003c2ca  mov     rcx, [rsi]; hWnd
0x18003c2cd  lea     r9, [rbp+40h+lParam]; lParam
0x18003c2d1  mov     edx, 2Bh ; '+'; Msg
0x18003c2d6  call    SendMessageW
0x18003c2db  jmp     loc_18003C191
0x18003c2e0  jmp     loc_18003C08E
0x18003c2e5  mov     rcx, [r14+10h]
0x18003c2e9  test    rcx, rcx
0x18003c2ec  jnz     short loc_18003C36A
0x18003c2ee  mov     rcx, r13
0x18003c2f1  test    rsi, rsi
0x18003c2f4  jz      short loc_18003C2F9
0x18003c2f6  mov     rcx, [rsi]; HWND
0x18003c2f9  mov     r9, rdx; HBRUSH
0x18003c2fc  lea     rax, [rbp+40h+left]
0x18003c300  mov     r8, rbx; HDC
0x18003c303  mov     rdx, r12; HWND
0x18003c306  mov     qword ptr [rsp+140h+bottom], rax; struct tagRECT *
0x18003c30b  call    ?PaintRect@@YAHPEAUHWND__@@0PEAUHDC__@@PEAUHBRUSH__@@PEAUtagRECT@@@Z; PaintRect(HWND__ *,HWND__ *,HDC__ *,HBRUSH__ *,tagRECT *)
0x18003c310  jmp     loc_18003C191
0x18003c315  mov     edx, eax
0x18003c317  mov     rcx, rbx; hdc
0x18003c31a  bts     edx, 8; align
0x18003c31e  call    cs:__imp_SetTextAlign
0x18003c324  jmp     loc_18003C00A
0x18003c329  xor     r13d, r13d
0x18003c32c  jmp     loc_18003C0D0
0x18003c331  mov     rax, cs:gpsi
0x18003c338  mov     r9, [rax+12F8h]
0x18003c33f  jmp     loc_18009D566
0x18003c344  mov     rax, cs:gpsi
0x18003c34b  mov     r9, [rax+12D8h]
0x18003c352  jmp     loc_18009D566
0x18003c357  mov     rax, cs:gpsi
0x18003c35e  mov     r9, [rax+1300h]
0x18003c365  jmp     loc_18009D566
0x18003c36a  test    byte ptr [rdi+1Ah], 40h
0x18003c36e  mov     [rsp+140h+cxWidth], r13d
0x18003c373  mov     [rsp+140h+cyWidth], r13d
0x18003c378  mov     qword ptr [rsp+140h+pt.x], r13
0x18003c37d  jz      loc_18009D57A
0x18003c383  xor     r8d, r8d
0x18003c386  or      edx, 0FFFFFFFFh
0x18003c389  mov     rcx, rbx
0x18003c38c  call    cs:__imp_SetLayoutWidth
0x18003c392  mov     rcx, [r14+10h]
0x18003c396  mov     r15d, eax
0x18003c399  jmp     loc_18009D57D
0x18003c39e  mov     r9d, 80h
0x18003c3a4  jmp     loc_18003C22C
0x18003c3a9  mov     rdx, [r14+10h]; hmf
0x18003c3ad  test    rdx, rdx
0x18003c3b0  jz      loc_18003C191
0x18003c3b6  movaps  xmm0, xmmword ptr [rbp+40h+left]
0x18003c3ba  lea     r8, [rbp+40h+rect]; lprect
0x18003c3be  mov     rcx, rbx; hdc
0x18003c3c1  movdqa  xmmword ptr [rbp+40h+rect.left], xmm0
0x18003c3c6  call    cs:__imp_PlayEnhMetaFile
0x18003c3cc  jmp     loc_18003C191
0x18003c3d1  mov     ecx, [rdi+0B8h]
0x18003c3d7  test    ecx, ecx
0x18003c3d9  jz      loc_18009D83F
0x18003c3df  mov     r9, [rdi+0C0h]
0x18003c3e6  test    r9, r9
0x18003c3e9  jnz     loc_18009D834
0x18003c3ef  mov     r9, r13
0x18003c3f2  jmp     loc_18009D83B
0x18003c3f7  mov     r9d, 0A0h
0x18003c3fd  jmp     loc_18003C22C
0x18003c402  mov     edx, [rsp+140h+align]; align
0x18003c406  mov     rcx, rbx; hdc
0x18003c409  call    cs:__imp_SetTextAlign
0x18003c40f  jmp     loc_18003C1B1
0x18009d566  mov     rcx, r13
0x18009d569  test    rsi, rsi
0x18009d56c  jz      loc_18003C2FC
0x18009d572  mov     rcx, [rsi]
0x18009d575  jmp     loc_18003C2FC
0x18009d57a  mov     r15d, r13d
0x18009d57d  mov     r12d, 2
0x18009d583  test    [rdi+1Dh], r12b
0x18009d587  jz      short loc_18009D5CF
0x18009d589  mov     edx, [r14+1Ch]
0x18009d58d  lea     r9, [rsp+140h+cyWidth]
0x18009d592  lea     r8, [rsp+140h+cxWidth]
0x18009d597  call    cs:__imp_NtUserGetIconSize
0x18009d59d  mov     eax, [rbp+40h+left+8]
0x18009d5a0  sub     eax, [rsp+140h+cxWidth]
0x18009d5a4  mov     r8d, [rsp+140h+cyWidth]
0x18009d5a9  cdq
0x18009d5aa  idiv    r12d
0x18009d5ad  sar     r8d, 1
0x18009d5b0  mov     [rbp+40h+left], eax
0x18009d5b3  add     eax, [rsp+140h+cxWidth]
0x18009d5b7  mov     [rbp+40h+left+8], eax
0x18009d5ba  mov     eax, [rbp+40h+left+0Ch]
0x18009d5bd  sub     eax, r8d
0x18009d5c0  cdq
  ... truncated ...
```
