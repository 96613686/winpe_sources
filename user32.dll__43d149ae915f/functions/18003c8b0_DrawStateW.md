# DrawStateW

- ea: `0x18003c8b0`
- end: `0x18003d047`
- name: `DrawStateW`
- size: `1943`
- prototype: `BOOL __stdcall(HDC hdc, HBRUSH hbrFore, DRAWSTATEPROC qfnCallBack, LPARAM lData, WPARAM wData, int x, int y, int cx, int cy, UINT uFlags)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18003bfac`
- `0x18003d348`
- `0x18003e644`
- `0x180066ae0`

## callees

- `0x180005d48`
- `0x18003c8b0`
- `0x18003dfa0`
- `0x18003e370`
- `0x18003e49c`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserBitBltSysBmp` at `0x18003cf87`
- `win32u!NtUserBitBltSysBmp` at `0x18003cf87`
- `win32u!NtUserGetOemBitmapSize` at `0x18003ce82`
- `win32u!NtUserGetOemBitmapSize` at `0x18003ce82`
- `win32u!NtUserGetIconSize` at `0x18003ce18`
- `win32u!NtUserGetIconSize` at `0x18003ce18`
- `ntdll!RtlLeaveCriticalSection` at `0x18003ca4c`
- `ntdll!RtlLeaveCriticalSection` at `0x18003ca4c`
- `GDI32!SetBkMode` at `0x18003ceea`
- `GDI32!SetBkMode` at `0x18003ceea`
- `GDI32!SelectObject` at `0x18003ca7b`
- `GDI32!SelectObject` at `0x18003cac8`
- `GDI32!SelectObject` at `0x18003cce5`
- `GDI32!SelectObject` at `0x18003cdd2`
- `GDI32!SelectObject` at `0x18003cde2`
- `GDI32!SelectObject` at `0x18003cdf2`
- `GDI32!SelectObject` at `0x18003ced8`
- `GDI32!SelectObject` at `0x18003cfc7`
- `GDI32!SelectObject` at `0x18009da06`
- `GDI32!SelectObject` at `0x18003ca7b`
- `GDI32!SelectObject` at `0x18003cac8`
- `GDI32!SelectObject` at `0x18003cce5`
- `GDI32!SelectObject` at `0x18003cdd2`
- `GDI32!SelectObject` at `0x18003cde2`
- `GDI32!SelectObject` at `0x18003cdf2`
- `GDI32!SelectObject` at `0x18003ced8`
- `GDI32!SelectObject` at `0x18003cfc7`
- `GDI32!SelectObject` at `0x18009da06`
- `GDI32!SetTextAlign` at `0x18003cc33`
- `GDI32!SetTextAlign` at `0x18003cd91`
- `GDI32!SetTextAlign` at `0x18003cc33`
- `GDI32!SetTextAlign` at `0x18003cd91`
- `GDI32!GetTextAlign` at `0x18003cd6b`
- `GDI32!GetTextAlign` at `0x18003cd79`
- `GDI32!GetTextAlign` at `0x18003cd6b`
- `GDI32!GetTextAlign` at `0x18003cd79`
- `GDI32!GetStockObject` at `0x18003ccd5`
- `GDI32!GetStockObject` at `0x18003cda6`
- `GDI32!GetStockObject` at `0x18003cec8`
- `GDI32!GetStockObject` at `0x18003ccd5`
- `GDI32!GetStockObject` at `0x18003cda6`
- `GDI32!GetStockObject` at `0x18003cec8`
- `GDI32!SetBkColor` at `0x18003ceae`
- `GDI32!SetBkColor` at `0x18003ceae`
- `GDI32!SetTextColor` at `0x18003cebd`
- `GDI32!SetTextColor` at `0x18003cebd`
- `GDI32!GetObjectW` at `0x18003cb5c`
- `GDI32!GetObjectW` at `0x18003cb5c`
- `GDI32!GetLayout` at `0x18003ccfe`
- `GDI32!GetLayout` at `0x18003ccfe`
- `GDI32!PolyPatBlt` at `0x18003d008`
- `GDI32!PolyPatBlt` at `0x18003d008`
- `GDI32!SetViewportOrgEx` at `0x18003c9a8`
- `GDI32!SetViewportOrgEx` at `0x18003ca2c`
- `GDI32!SetViewportOrgEx` at `0x18003c9a8`
- `GDI32!SetViewportOrgEx` at `0x18003ca2c`
- `GDI32!GetViewportOrgEx` at `0x18003c98e`
- `GDI32!GetViewportOrgEx` at `0x18003c98e`
- `GDI32!GetCurrentObject` at `0x18003cdba`
- `GDI32!GetCurrentObject` at `0x18003cdba`
- `GDI32!GetTextCharacterExtra` at `0x18003cd53`
- `GDI32!GetTextCharacterExtra` at `0x18003cd53`
- `GDI32!SetTextCharacterExtra` at `0x18003cd62`
- `GDI32!SetTextCharacterExtra` at `0x18003cd62`
- `GDI32!SetLayoutWidth` at `0x18003ccba`
- `GDI32!SetLayoutWidth` at `0x18003ccf4`
- `GDI32!SetLayoutWidth` at `0x18003cf6b`
- `GDI32!SetLayoutWidth` at `0x18003ccba`
- `GDI32!SetLayoutWidth` at `0x18003ccf4`
- `GDI32!SetLayoutWidth` at `0x18003cf6b`
- `GDI32!TextOutW` at `0x18003cfb2`
- `GDI32!TextOutW` at `0x18003cfb2`
- `GDI32!GetTextExtentPointW` at `0x18009d9b4`
- `GDI32!GetTextExtentPointW` at `0x18009d9b4`
- `GDI32!GetObjectType` at `0x18003cb23`
- `GDI32!GetObjectType` at `0x18003cb23`
- `GDI32!CreateBitmap` at `0x18009d9f1`
- `GDI32!CreateBitmap` at `0x18009d9f1`
- `GDI32!PatBlt` at `0x18003cd49`
- `GDI32!PatBlt` at `0x18003cd49`
- `GDI32!BitBlt` at `0x18003cab8`
- `GDI32!BitBlt` at `0x18003cab8`
- `GDI32!DeleteObject` at `0x18009da0f`
- `GDI32!DeleteObject` at `0x18009da0f`

## pseudocode

```c
BOOL __stdcall DrawStateW(
        HDC hdc,
        HBRUSH hbrFore,
        DRAWSTATEPROC qfnCallBack,
        LPARAM lData,
        WPARAM wData,
        int x,
        int y,
        int cx,
        int cy,
        UINT uFlags)
{
  __int16 v11; // r15
  HDC v12; // rbx
  unsigned int v13; // r13d
  int v14; // esi
  unsigned int v15; // edi
  WPARAM v16; // r14
  unsigned int v17; // r13d
  unsigned int v18; // r13d
  unsigned int v19; // r13d
  unsigned int v20; // r13d
  HGDIOBJ v22; // rbx
  int v23; // esi
  int v24; // eax
  HDC v25; // r8
  HDC v26; // r8
  HGDIOBJ StockObject; // rax
  DWORD Layout; // eax
  int v29; // r9d
  int v30; // ecx
  int TextCharacterExtra; // eax
  unsigned __int16 v32; // ax
  HGDIOBJ v33; // rbx
  HGDIOBJ v34; // rax
  HGDIOBJ v35; // rax
  int v36; // edx
  int v37; // ecx
  HBITMAP Bitmap; // rax
  HGDIOBJ v39; // rax
  int y1; // [rsp+40h] [rbp-A1h]
  int y1a; // [rsp+40h] [rbp-A1h]
  int v42; // [rsp+48h] [rbp-99h]
  int v43; // [rsp+48h] [rbp-99h]
  unsigned int v44; // [rsp+50h] [rbp-91h]
  unsigned int v45; // [rsp+50h] [rbp-91h]
  int h; // [rsp+58h] [rbp-89h]
  HGDIOBJ ha; // [rsp+58h] [rbp-89h]
  UINT TextAlign; // [rsp+60h] [rbp-81h]
  unsigned int v49; // [rsp+64h] [rbp-7Dh] BYREF
  int v50; // [rsp+68h] [rbp-79h] BYREF
  int v51; // [rsp+6Ch] [rbp-75h]
  struct tagPOINT point; // [rsp+70h] [rbp-71h] BYREF
  HDC v53; // [rsp+78h] [rbp-69h]
  int v54; // [rsp+80h] [rbp-61h]
  __int64 v55; // [rsp+88h] [rbp-59h] BYREF
  __int64 v56; // [rsp+90h] [rbp-51h]
  struct tagSIZE sz; // [rsp+98h] [rbp-49h] BYREF
  HGDIOBJ v58; // [rsp+A0h] [rbp-41h]
  __int64 v59; // [rsp+A8h] [rbp-39h] BYREF
  unsigned int v60; // [rsp+B0h] [rbp-31h]
  int v61; // [rsp+B4h] [rbp-2Dh]
  __int64 v62; // [rsp+B8h] [rbp-29h]
  _OWORD pv[5]; // [rsp+C0h] [rbp-21h] BYREF

  point = 0;
  if ( (unsigned int)AcquireGlobalGdiResources() && ghdcGray )
  {
    v11 = uFlags;
    h = 0;
    v12 = 0;
    v51 = -1;
    if ( (uFlags & 0x20) != 0 && (*(_WORD *)(gpsi + 6996) == 1 || *(_DWORD *)(gpsi + 2188)) )
      v11 = uFlags & 0xFFCF | 0x10;
    if ( (v11 & 0x70) != 0 )
      v11 |= 0x80u;
    v13 = v11 & 7;
    if ( (v11 & 7) == 0 )
    {
      v14 = cy;
      v15 = cx;
LABEL_8:
      v16 = wData;
      goto LABEL_9;
    }
    if ( (v11 & 7) == 1 )
    {
      v16 = wData;
      if ( !wData )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(lData + 2 * v16) );
      }
      v15 = cx;
      v14 = cy;
      if ( cx && cy )
        goto LABEL_11;
      sz = 0;
      GetTextExtentPointW(hdc, (LPCWSTR)lData, v16, &sz);
      if ( !cx )
        v15 = sz.cx;
      if ( !cy )
        v14 = sz.cy;
    }
    else
    {
      if ( (v11 & 7) != 2 )
      {
        if ( (v11 & 7) == 3 )
        {
          v15 = cx;
          v14 = cy;
          if ( !cx || !cy )
          {
            v49 = 0;
            v50 = 0;
            NtUserGetIconSize(lData, 0, &v49, &v50);
            if ( !cx )
              v15 = v49;
            if ( !cy )
              v14 = v50 / 2;
            goto LABEL_8;
          }
LABEL_31:
          v16 = wData;
          goto LABEL_10;
        }
        if ( (v11 & 7) == 4 )
        {
          if ( GetObjectType((HGDIOBJ)lData) == 7 )
          {
            v15 = cx;
            v14 = cy;
            if ( !cx || !cy )
            {
              memset(pv, 0, 32);
              GetObjectW((HANDLE)lData, 32, pv);
              if ( !cx )
                v15 = DWORD1(pv[0]);
              if ( !cy )
                v14 = DWORD2(pv[0]);
              goto LABEL_8;
            }
            goto LABEL_31;
          }
        }
        else if ( (v11 & 7) == 5 && (unsigned __int16)lData < 0x5Du )
        {
          v55 = 0;
          NtUserGetOemBitmapSize((unsigned __int16)lData, &v55);
          v15 = cx;
          v14 = cy;
          if ( !cx )
            v15 = v55;
          if ( !cy )
            v14 = HIDWORD(v55);
          goto LABEL_8;
        }
LABEL_23:
        if ( (v11 & 0x80u) == 0 )
          goto LABEL_24;
        goto LABEL_58;
      }
      if ( !lData )
        goto LABEL_23;
      v16 = wData;
      if ( !wData )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(lData + 2 * v16) );
      }
      v15 = cx;
      v23 = cy;
      if ( !cx || !cy )
      {
        v56 = 0;
        PSMGetTextExtent(hdc);
        if ( !cx )
          v15 = v56;
        if ( !cy )
          v23 = HIDWORD(v56);
      }
      v14 = v23 + 2;
    }
LABEL_9:
    if ( !v15 )
    {
LABEL_22:
      h = 1;
      goto LABEL_23;
    }
LABEL_10:
    if ( v14 )
    {
LABEL_11:
      v58 = 0;
      v54 = v11 & 0x80;
      if ( (v11 & 0x80) != 0 )
      {
        v12 = ghdcGray;
        v53 = ghdcGray;
        StockObject = GetStockObject(13);
        SelectObject(ghdcGray, StockObject);
        SetLayoutWidth(v12, 0xFFFFFFFFLL, 0);
        Layout = GetLayout(hdc);
        v51 = Layout;
        if ( Layout != -1 )
          SetLayoutWidth(v12, v15, Layout);
        v29 = gcxGray;
        v30 = gcyGray;
        if ( gcxGray < (int)(v15 + 1) || gcyGray < v14 )
        {
          v36 = v14;
          if ( gcyGray > v14 )
            v36 = gcyGray;
          v37 = v15 + 1;
          if ( gcxGray > (int)(v15 + 1) )
            v37 = gcxGray;
          Bitmap = CreateBitmap(v37, v36, 1u, 1u, 0);
          if ( Bitmap )
          {
            v39 = SelectObject(ghdcGray, Bitmap);
            DeleteObject(v39);
            v29 = gcxGray;
            if ( gcxGray <= (int)(v15 + 1) )
            {
              v29 = v15 + 1;
              gcxGray = v15 + 1;
            }
            v30 = gcyGray;
            if ( gcyGray <= v14 )
            {
              v30 = v14;
              gcyGray = v14;
            }
          }
          else
          {
            v29 = gcxGray;
            v30 = gcyGray;
            v14 = gcyGray;
            v15 = gcxGray - 1;
          }
        }
        PatBlt(ghdcGray, 0, 0, v29, v30, 0xFF0062u);
        TextCharacterExtra = GetTextCharacterExtra(hdc);
        SetTextCharacterExtra(ghdcGray, TextCharacterExtra);
        TextAlign = GetTextAlign(v12);
        v32 = GetTextAlign(hdc);
        SetTextAlign(v12, TextAlign ^ ((unsigned __int16)TextAlign ^ v32) & 0x106);
        if ( v13 <= 2 )
        {
          ha = GetStockObject(13);
          if ( GetCurrentObject(hdc, 6u) != ha )
          {
            v33 = SelectObject(hdc, ha);
            SelectObject(hdc, v33);
            v34 = SelectObject(ghdcGray, v33);
            v12 = v53;
            v58 = v34;
          }
        }
      }
      else
      {
        TextAlign = 0;
        v12 = hdc;
        v53 = hdc;
        GetViewportOrgEx(hdc, &point);
        SetViewportOrgEx(hdc, x + point.x, y + point.y, 0);
      }
      h = 1;
      v17 = v13 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              if ( v20 == 1 )
              {
                NtUserBitBltSysBmp(v12, 0, 0, (unsigned __int16)lData, 13369376);
              }
              else
              {
                h = ((__int64 (__fastcall *)(HDC, LPARAM, WPARAM, _QWORD, int))qfnCallBack)(v12, lData, v16, v15, v14);
                if ( v12 == ghdcGray )
                {
                  SetBkColor(ghdcGray, 0xFFFFFFu);
                  SetTextColor(ghdcGray, 0);
                  v35 = GetStockObject(4);
                  SelectObject(ghdcGray, v35);
                  SetBkMode(ghdcGray, 2);
                }
              }
            }
            else
            {
              v22 = SelectObject(ghdcBits2, (HGDIOBJ)lData);
              BitBlt(v53, 0, 0, v15, v14, ghdcBits2, 0, 0, 0xCC0020u);
              SelectObject(ghdcBits2, v22);
              v12 = v53;
            }
          }
          else
          {
            DrawIconEx(v12, 0, 0, (HICON)lData, 0, 0, 0, 0, 3u);
          }
        }
        else
        {
          if ( (v11 & 0x200) != 0 )
            v24 = 0x100000;
          else
            v24 = (v11 & 0x400) << 11;
          ((void (__fastcall *)(HDC, _QWORD, _QWORD, LPARAM, _DWORD, int))fpLpkPSMTextOut)(v12, 0, 0, lData, v16, v24);
        }
      }
      else
      {
        h = TextOutW(v12, 0, 0, (LPCWSTR)lData, v16);
      }
      if ( !v54 )
      {
        SetViewportOrgEx(v12, point.x, point.y, 0);
LABEL_24:
        RtlLeaveCriticalSection(&gcsHdc);
        return h;
      }
      if ( v58 )
        SelectObject(v12, v58);
      SetTextAlign(v12, TextAlign);
      if ( (v11 & 0x10) != 0 )
      {
        v60 = v15;
        v59 = 0;
        v62 = *(_QWORD *)(gpsi + 4944);
        v61 = v14;
        PolyPatBlt(ghdcGray, 16384137, &v59, 1, 0);
      }
      if ( (v11 & 0x20) != 0 )
      {
        BltColor(hdc, *(HBRUSH *)(gpsi + 4856), v25, x + 1, y + 1, v15, v14, y1, v42, v44);
        BltColor(hdc, *(HBRUSH *)(gpsi + 4824), v26, x, y, v15, v14, y1a, v43, v45);
      }
      else
      {
        if ( (v11 & 0x40) != 0 )
          BltColor(hdc, *(HBRUSH *)(gpsi + 4824), v25, x + 1, y + 1, v15, v14, y1, v42, v44);
        BltColor(hdc, hbrFore, v25, x, y, v15, v14, y1, v42, v44);
      }
LABEL_58:
      if ( v51 != -1 )
        SetLayoutWidth(v12, 0xFFFFFFFFLL, 0);
      goto LABEL_24;
    }
    goto LABEL_22;
  }
  return 0;
}

```

## disassembly

```asm
0x18003c8b0  mov     rax, rsp
0x18003c8b3  mov     [rax+20h], rbx
0x18003c8b7  mov     [rax+18h], r8
0x18003c8bb  mov     [rax+10h], rdx
0x18003c8bf  mov     [rax+8], rcx
0x18003c8c3  push    rbp
0x18003c8c4  push    rsi
0x18003c8c5  push    rdi
0x18003c8c6  push    r12
0x18003c8c8  push    r13
0x18003c8ca  push    r14
0x18003c8cc  push    r15
0x18003c8ce  lea     rbp, [rax-3Fh]
0x18003c8d2  sub     rsp, 0E0h
0x18003c8d9  mov     r12, r9
0x18003c8dc  mov     qword ptr [rbp+37h+point.x], 0
0x18003c8e4  call    ?AcquireGlobalGdiResources@@YAHXZ; AcquireGlobalGdiResources(void)
0x18003c8e9  xor     ecx, ecx
0x18003c8eb  test    eax, eax
0x18003c8ed  jz      loc_18003CB10
0x18003c8f3  cmp     cs:?ghdcGray@@3PEAUHDC__@@EA, rcx; HDC__ * ghdcGray
0x18003c8fa  jz      loc_18003CB10
0x18003c900  mov     r15d, [rbp+37h+uFlags]
0x18003c907  lea     edx, [rcx+1]
0x18003c90a  mov     dword ptr [rsp+110h+h], ecx
0x18003c90e  mov     ebx, ecx
0x18003c910  mov     [rbp+37h+var_AC], 0FFFFFFFFh
0x18003c917  test    r15b, 20h
0x18003c91b  jnz     loc_18003CEF5
0x18003c921  test    r15b, 70h
0x18003c925  jnz     loc_18003CF1A
0x18003c92b  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18003c932  mov     r13d, r15d
0x18003c935  and     r13d, 7
0x18003c939  mov     eax, r13d
0x18003c93c  lea     r14d, [rdx+3]
0x18003c940  jnz     loc_18003CAD7
0x18003c946  mov     esi, [rbp+37h+cy]
0x18003c94c  mov     edi, [rbp+37h+arg_38]
0x18003c94f  mov     r14, [rbp+37h+wData]
0x18003c953  test    edi, edi
0x18003c955  jz      loc_18003CA34
0x18003c95b  test    esi, esi
0x18003c95d  jz      loc_18003CA34
0x18003c963  mov     eax, r15d
0x18003c966  mov     [rbp+37h+var_78], rcx
0x18003c96a  and     eax, 80h
0x18003c96f  mov     [rbp+37h+var_98], eax
0x18003c972  jnz     loc_18003CCC5
0x18003c978  mov     rax, [rbp+37h+hdc]
0x18003c97c  lea     rdx, [rbp+37h+point]; lppoint
0x18003c980  mov     [rsp+58h], ecx
0x18003c984  mov     rbx, rax
0x18003c987  mov     rcx, rax; hdc
0x18003c98a  mov     [rbp+37h+var_A0], rax
0x18003c98e  call    cs:__imp_GetViewportOrgEx
0x18003c994  mov     r8d, [rbp+37h+point.y]
0x18003c998  xor     r9d, r9d; lppt
0x18003c99b  mov     edx, [rbp+37h+point.x]
0x18003c99e  mov     rcx, rbx; hdc
0x18003c9a1  add     r8d, [rbp+37h+y]; y
0x18003c9a5  add     edx, [rbp+37h+x]; x
0x18003c9a8  call    cs:__imp_SetViewportOrgEx
0x18003c9ae  mov     dword ptr [rsp+110h+h], 1
0x18003c9b6  sub     r13d, 1
0x18003c9ba  jz      loc_18003CFA2
0x18003c9c0  sub     r13d, 1
0x18003c9c4  jz      loc_18003CBEA
0x18003c9ca  sub     r13d, 1
0x18003c9ce  jz      loc_18003CB7A
0x18003c9d4  sub     r13d, 1
0x18003c9d8  jz      loc_18003CA71
0x18003c9de  mov     rcx, rbx
0x18003c9e1  cmp     r13d, 1
0x18003c9e5  jz      loc_18003CF76
0x18003c9eb  mov     rax, [rbp+37h+arg_10]
0x18003c9ef  mov     r9d, edi
0x18003c9f2  mov     r8, r14
0x18003c9f5  mov     [rsp+110h+cxWidth], esi
0x18003c9f9  mov     rdx, r12
0x18003c9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca01  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x18003ca08  mov     dword ptr [rsp+110h+h], eax
0x18003ca0c  cmp     rbx, rcx
0x18003ca0f  jz      loc_18003CEA9
0x18003ca15  cmp     [rbp+37h+var_98], 0
0x18003ca19  jnz     loc_18003CC1F
0x18003ca1f  mov     r8d, [rbp+37h+point.y]; y
0x18003ca23  xor     r9d, r9d; lppt
0x18003ca26  mov     edx, [rbp+37h+point.x]; x
0x18003ca29  mov     rcx, rbx; hdc
0x18003ca2c  call    cs:__imp_SetViewportOrgEx
0x18003ca32  jmp     short loc_18003CA45
0x18003ca34  mov     dword ptr [rsp+110h+h], 1
0x18003ca3c  test    r15b, r15b
0x18003ca3f  js      loc_18003CCA7
0x18003ca45  lea     rcx, ?gcsHdc@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18003ca4c  call    cs:__imp_RtlLeaveCriticalSection
0x18003ca52  mov     eax, dword ptr [rsp+110h+h]
0x18003ca56  mov     rbx, [rsp+110h+arg_18]
0x18003ca5e  add     rsp, 0E0h
0x18003ca65  pop     r15
0x18003ca67  pop     r14
0x18003ca69  pop     r13
0x18003ca6b  pop     r12
0x18003ca6d  pop     rdi
0x18003ca6e  pop     rsi
0x18003ca6f  pop     rbp
0x18003ca70  retn
0x18003ca71  mov     rcx, cs:ghdcBits2; hdc
0x18003ca78  mov     rdx, r12; h
0x18003ca7b  call    cs:__imp_SelectObject
0x18003ca81  mov     rcx, cs:ghdcBits2
0x18003ca88  mov     r9d, edi; cx
0x18003ca8b  mov     dword ptr [rsp+40h], 0CC0020h; rop
0x18003ca93  xor     r8d, r8d; y
0x18003ca96  mov     [rsp+110h+y1], 0; y1
0x18003ca9e  xor     edx, edx; x
0x18003caa0  mov     [rsp+110h+x1], 0; x1
0x18003caa8  mov     rbx, rax
0x18003caab  mov     [rsp+110h+hdcSrc], rcx; hdcSrc
0x18003cab0  mov     rcx, [rbp+37h+var_A0]; hdc
0x18003cab4  mov     [rsp+110h+cxWidth], esi; cy
0x18003cab8  call    cs:__imp_BitBlt
0x18003cabe  mov     rcx, cs:ghdcBits2; hdc
0x18003cac5  mov     rdx, rbx; h
0x18003cac8  call    cs:__imp_SelectObject
0x18003cace  mov     rbx, [rbp+37h+var_A0]
0x18003cad2  jmp     loc_18003CA15
0x18003cad7  sub     eax, 1
0x18003cada  jz      loc_18003CF4E
0x18003cae0  sub     eax, 1
0x18003cae3  jz      loc_18003CBAA
0x18003cae9  sub     eax, 1
0x18003caec  jnz     short loc_18003CB17
0x18003caee  mov     edi, [rbp+37h+arg_38]
0x18003caf1  mov     esi, [rbp+37h+cy]
0x18003caf7  test    edi, edi
0x18003caf9  jz      loc_18003CE05
0x18003caff  test    esi, esi
0x18003cb01  jz      loc_18003CE05
0x18003cb07  mov     r14, [rbp+37h+wData]
0x18003cb0b  jmp     loc_18003C95B
0x18003cb10  xor     eax, eax
0x18003cb12  jmp     loc_18003CA56
0x18003cb17  sub     eax, 1
0x18003cb1a  jnz     loc_18003CE62
0x18003cb20  mov     rcx, r12; h
0x18003cb23  call    cs:__imp_GetObjectType
0x18003cb29  cmp     eax, 7
0x18003cb2c  jnz     loc_18003CA3C
0x18003cb32  mov     edi, [rbp+37h+arg_38]
0x18003cb35  xor     ecx, ecx
0x18003cb37  mov     esi, [rbp+37h+cy]
0x18003cb3d  test    edi, edi
0x18003cb3f  jz      short loc_18003CB45
0x18003cb41  test    esi, esi
0x18003cb43  jnz     short loc_18003CB07
0x18003cb45  xorps   xmm0, xmm0
0x18003cb48  lea     r8, [rbp+37h+pv]; pv
0x18003cb4c  mov     edx, 20h ; ' '; c
0x18003cb51  mov     rcx, r12; h
0x18003cb54  movups  [rbp+37h+pv], xmm0
0x18003cb58  movups  [rbp+37h+var_48], xmm0
0x18003cb5c  call    cs:__imp_GetObjectW
0x18003cb62  xor     ecx, ecx
0x18003cb64  test    edi, edi
0x18003cb66  cmovz   edi, dword ptr [rbp+37h+pv+4]
0x18003cb6a  test    esi, esi
0x18003cb6c  jnz     loc_18003C94F
0x18003cb72  mov     esi, dword ptr [rbp+37h+pv+8]
0x18003cb75  jmp     loc_18003C94F
0x18003cb7a  xor     eax, eax
0x18003cb7c  mov     dword ptr [rsp+40h], 3; diFlags
0x18003cb84  mov     qword ptr [rsp+110h+y1], rax; hbrFlickerFreeDraw
0x18003cb89  mov     r9, r12; hIcon
0x18003cb8c  mov     [rsp+110h+x1], eax; istepIfAniCur
0x18003cb90  xor     r8d, r8d; yTop
0x18003cb93  mov     dword ptr [rsp+110h+hdcSrc], eax; cyWidth
0x18003cb97  xor     edx, edx; xLeft
0x18003cb99  mov     rcx, rbx; hdc
0x18003cb9c  mov     [rsp+110h+cxWidth], eax; cxWidth
0x18003cba0  call    DrawIconEx
0x18003cba5  jmp     loc_18003CA15
0x18003cbaa  test    r12, r12
0x18003cbad  jz      loc_18003CA3C
0x18003cbb3  mov     r14, [rbp+37h+wData]
0x18003cbb7  test    r14, r14
0x18003cbba  jnz     short loc_18003CBC9
0x18003cbbc  mov     r14, rdx
0x18003cbbf  inc     r14
0x18003cbc2  cmp     [r12+r14*2], cx
0x18003cbc7  jnz     short loc_18003CBBF
0x18003cbc9  mov     edi, [rbp+37h+arg_38]
0x18003cbcc  mov     esi, [rbp+37h+cy]
0x18003cbd2  test    edi, edi
0x18003cbd4  jz      loc_18003CF24
0x18003cbda  test    esi, esi
0x18003cbdc  jz      loc_18003CF24
0x18003cbe2  add     esi, 2
0x18003cbe5  jmp     loc_18003C953
0x18003cbea  bt      r15d, 9
0x18003cbef  jnb     loc_18003CF92
0x18003cbf5  mov     eax, 100000h
0x18003cbfa  mov     dword ptr [rsp+110h+hdcSrc], eax
0x18003cbfe  mov     r9, r12
0x18003cc01  mov     rax, cs:fpLpkPSMTextOut
0x18003cc08  xor     r8d, r8d
0x18003cc0b  xor     edx, edx
0x18003cc0d  mov     [rsp+110h+cxWidth], r14d
0x18003cc12  mov     rcx, rbx
0x18003cc15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc1a  jmp     loc_18003CA15
0x18003cc1f  mov     rax, [rbp+37h+var_78]
0x18003cc23  test    rax, rax
0x18003cc26  jnz     loc_18003CFC1
0x18003cc2c  mov     edx, [rsp+58h]; align
0x18003cc30  mov     rcx, rbx; hdc
0x18003cc33  call    cs:__imp_SetTextAlign
0x18003cc39  test    r15b, 10h
0x18003cc3d  jnz     loc_18003CFD2
0x18003cc43  test    r15b, 20h
0x18003cc47  jz      loc_18003CE3C
0x18003cc4d  mov     rdx, cs:gpsi
0x18003cc54  mov     r15d, [rbp+37h+y]
0x18003cc58  mov     r13d, [rbp+37h+x]
0x18003cc5c  mov     rcx, [rbp+37h+hdc]; hdc
0x18003cc60  mov     rdx, [rdx+12F8h]; h
0x18003cc67  lea     eax, [r15+1]
0x18003cc6b  mov     [rsp+110h+x1], esi; int
0x18003cc6f  lea     r9d, [r13+1]; int
0x18003cc73  mov     dword ptr [rsp+110h+hdcSrc], edi; int
0x18003cc77  mov     [rsp+110h+cxWidth], eax; y
0x18003cc7b  call    ?BltColor@@YAXPEAUHDC__@@PEAUHBRUSH__@@0HHHHHHI@Z; BltColor(HDC__ *,HBRUSH__ *,HDC__ *,int,int,int,int,int,int,uint)
0x18003cc80  mov     rdx, cs:gpsi
0x18003cc87  mov     r9d, r13d; int
0x18003cc8a  mov     [rsp+110h+x1], esi; int
0x18003cc8e  mov     dword ptr [rsp+110h+hdcSrc], edi; int
0x18003cc92  mov     [rsp+110h+cxWidth], r15d; y
0x18003cc97  mov     rdx, [rdx+12D8h]; h
0x18003cc9e  mov     rcx, [rbp+37h+hdc]; hdc
0x18003cca2  call    ?BltColor@@YAXPEAUHDC__@@PEAUHBRUSH__@@0HHHHHHI@Z; BltColor(HDC__ *,HBRUSH__ *,HDC__ *,int,int,int,int,int,int,uint)
0x18003cca7  cmp     [rbp+37h+var_AC], 0FFFFFFFFh
0x18003ccab  jz      loc_18003CA45
0x18003ccb1  xor     r8d, r8d
0x18003ccb4  or      edx, 0FFFFFFFFh
0x18003ccb7  mov     rcx, rbx
0x18003ccba  call    cs:__imp_SetLayoutWidth
0x18003ccc0  jmp     loc_18003CA45
0x18003ccc5  mov     rbx, cs:?ghdcGray@@3PEAUHDC__@@EA; HDC__ * ghdcGray
0x18003cccc  mov     ecx, 0Dh; i
0x18003ccd1  mov     [rbp+37h+var_A0], rbx
0x18003ccd5  call    cs:__imp_GetStockObject
0x18003ccdb  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x18003cce2  mov     rdx, rax; h
0x18003cce5  call    cs:__imp_SelectObject
0x18003cceb  xor     r8d, r8d
0x18003ccee  or      edx, 0FFFFFFFFh
0x18003ccf1  mov     rcx, rbx
0x18003ccf4  call    cs:__imp_SetLayoutWidth
0x18003ccfa  mov     rcx, [rbp+37h+hdc]; hdc
0x18003ccfe  call    cs:__imp_GetLayout
0x18003cd04  mov     [rbp+37h+var_AC], eax
0x18003cd07  cmp     eax, 0FFFFFFFFh
0x18003cd0a  jnz     loc_18003CF63
0x18003cd10  mov     r9d, cs:?gcxGray@@3HA; w
0x18003cd17  lea     eax, [rdi+1]
0x18003cd1a  mov     ecx, cs:?gcyGray@@3HA; int gcyGray
0x18003cd20  cmp     r9d, eax
0x18003cd23  jl      loc_18009D9CD
0x18003cd29  cmp     ecx, esi
0x18003cd2b  jl      loc_18009D9CD
0x18003cd31  mov     dword ptr [rsp+110h+hdcSrc], 0FF0062h; rop
0x18003cd39  xor     r8d, r8d; y
0x18003cd3c  mov     [rsp+110h+cxWidth], ecx; h
0x18003cd40  xor     edx, edx; x
0x18003cd42  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x18003cd49  call    cs:__imp_PatBlt
0x18003cd4f  mov     rcx, [rbp+37h+hdc]; hdc
0x18003cd53  call    cs:__imp_GetTextCharacterExtra
0x18003cd59  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x18003cd60  mov     edx, eax; extra
0x18003cd62  call    cs:__imp_SetTextCharacterExtra
0x18003cd68  mov     rcx, rbx; hdc
0x18003cd6b  call    cs:__imp_GetTextAlign
0x18003cd71  mov     rcx, [rbp+37h+hdc]; hdc
0x18003cd75  mov     [rsp+58h], eax
0x18003cd79  call    cs:__imp_GetTextAlign
0x18003cd7f  xor     eax, [rsp+58h]
0x18003cd83  mov     rcx, rbx; hdc
0x18003cd86  and     eax, 106h
0x18003cd8b  xor     eax, [rsp+58h]
0x18003cd8f  mov     edx, eax; align
0x18003cd91  call    cs:__imp_SetTextAlign
0x18003cd97  cmp     r13d, 2
0x18003cd9b  ja      loc_18003C9AE
0x18003cda1  mov     ecx, 0Dh; i
0x18003cda6  call    cs:__imp_GetStockObject
0x18003cdac  mov     rcx, [rbp+37h+hdc]; hdc
0x18003cdb0  mov     edx, 6; type
  ... truncated ...
```
