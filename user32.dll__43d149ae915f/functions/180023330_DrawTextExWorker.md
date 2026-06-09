# DrawTextExWorker

- ea: `0x180023330`
- end: `0x180024835`
- name: `DrawTextExWorker`
- size: `5381`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, unsigned int, __int64, int)`
- caller_count: `7`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022bac`
- `0x180022dd0`
- `0x180022f80`
- `0x180023240`
- `0x180023270`
- `0x18003d348`
- `0x1800739b0`

## callees

- `0x180023330`
- `0x180024840`
- `0x180024a88`
- `0x180024b50`
- `0x180025444`
- `0x1800255b0`
- `0x180025660`
- `0x180025a34`
- `0x180025c68`
- `0x180025e60`
- `0x1800961f0`
- `0x180096dad`
- `0x180096dc5`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180023543`
- `ntdll!RtlSetLastWin32Error` at `0x180023543`
- `ntdll!RtlFreeHeap` at `0x180023649`
- `ntdll!RtlFreeHeap` at `0x180023649`
- `ntdll!RtlAllocateHeap` at `0x1800242e4`
- `ntdll!RtlAllocateHeap` at `0x18002430f`
- `ntdll!RtlAllocateHeap` at `0x1800242e4`
- `ntdll!RtlAllocateHeap` at `0x18002430f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180023ff8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180023ff8`
- `GDI32!IntersectClipRect` at `0x1800234ad`
- `GDI32!IntersectClipRect` at `0x1800234ad`
- `GDI32!SetTextAlign` at `0x180023445`
- `GDI32!SetTextAlign` at `0x1800236aa`
- `GDI32!SetTextAlign` at `0x180023445`
- `GDI32!SetTextAlign` at `0x1800236aa`
- `GDI32!GetTextAlign` at `0x180023438`
- `GDI32!GetTextAlign` at `0x180023438`
- `GDI32!GetLayout` at `0x1800235bc`
- `GDI32!GetLayout` at `0x180023a72`
- `GDI32!GetLayout` at `0x180023ce9`
- `GDI32!GetLayout` at `0x1800235bc`
- `GDI32!GetLayout` at `0x180023a72`
- `GDI32!GetLayout` at `0x180023ce9`
- `GDI32!ExtSelectClipRgn` at `0x180023698`
- `GDI32!ExtSelectClipRgn` at `0x180023cca`
- `GDI32!ExtSelectClipRgn` at `0x180023698`
- `GDI32!ExtSelectClipRgn` at `0x180023cca`
- `GDI32!GetClipRgn` at `0x18002347a`
- `GDI32!GetClipRgn` at `0x18002347a`
- `GDI32!CreateRectRgn` at `0x180023462`
- `GDI32!CreateRectRgn` at `0x180023462`
- `GDI32!GdiGetCodePage` at `0x180023891`
- `GDI32!GdiGetCodePage` at `0x180023891`
- `GDI32!GetTextExtentPointW` at `0x180023e08`
- `GDI32!GetTextExtentPointW` at `0x180024465`
- `GDI32!GetTextExtentPointW` at `0x180024495`
- `GDI32!GetTextExtentPointW` at `0x180024629`
- `GDI32!GetTextExtentPointW` at `0x18002467f`
- `GDI32!GetTextExtentPointW` at `0x180023e08`
- `GDI32!GetTextExtentPointW` at `0x180024465`
- `GDI32!GetTextExtentPointW` at `0x180024495`
- `GDI32!GetTextExtentPointW` at `0x180024629`
- `GDI32!GetTextExtentPointW` at `0x18002467f`
- `GDI32!DeleteObject` at `0x180023488`
- `GDI32!DeleteObject` at `0x180023cd3`
- `GDI32!DeleteObject` at `0x180023488`
- `GDI32!DeleteObject` at `0x180023cd3`

## pseudocode

```c
__int64 __fastcall DrawTextExWorker(
        HDC hdc,
        unsigned __int16 *a2,
        unsigned int a3,
        struct tagRECT *a4,
        unsigned int a5,
        struct tagDRAWTEXTPARAMS *a6,
        int a7)
{
  __int64 v7; // rbx
  unsigned int v8; // r12d
  HDC v9; // r15
  unsigned __int16 *v10; // rdi
  struct tagRECT *v11; // r13
  UINT TextAlign; // eax
  HRGN RectRgn; // rax
  HRGN v14; // rsi
  int v15; // edx
  __int16 v16; // cx
  unsigned __int16 *v17; // r8
  unsigned __int64 v18; // r9
  int top; // r14d
  int v20; // eax
  int v21; // r8d
  int v22; // esi
  __int64 result; // rax
  int v24; // eax
  unsigned int v25; // edi
  unsigned int v26; // esi
  int v27; // r15d
  unsigned int v28; // r12d
  unsigned int v29; // r14d
  unsigned int v30; // edi
  HRGN v31; // rbx
  int v32; // eax
  void *v33; // r13
  int v34; // edi
  int v35; // r9d
  int v36; // r14d
  int v37; // edx
  __int16 *v38; // rcx
  int v39; // r8d
  __int16 v40; // ax
  int v41; // r8d
  bool v42; // cc
  const unsigned __int16 *v43; // rsi
  DWORD CodePage; // r10d
  WCHAR *v45; // r11
  WCHAR *v46; // r13
  char v47; // al
  WCHAR *v48; // rsi
  BOOL v49; // r14d
  WCHAR *v50; // r8
  char v51; // r15
  bool v52; // r12
  unsigned int v53; // ecx
  int v54; // eax
  __int64 v55; // rcx
  struct tagSIZE v56; // r11
  unsigned __int64 v57; // rsi
  unsigned __int64 v58; // r15
  unsigned int LongChar; // eax
  unsigned int v60; // r14d
  const WCHAR *v61; // r12
  int v62; // r13d
  unsigned __int64 v63; // r14
  unsigned int v64; // r15d
  unsigned int v65; // eax
  int v66; // r8d
  unsigned int v67; // r15d
  unsigned __int16 v68; // ax
  int i; // edx
  int v70; // ecx
  unsigned __int64 v71; // rax
  unsigned __int64 v72; // r9
  int v73; // r14d
  int v74; // eax
  __int16 v75; // ax
  int v76; // ecx
  __int16 v77; // ax
  unsigned int v78; // r14d
  int v79; // r12d
  unsigned int v80; // edi
  unsigned int v81; // eax
  int v82; // ecx
  unsigned int v83; // r15d
  unsigned __int16 *v84; // r10
  __int64 v85; // kr08_8
  int v86; // r12d
  int v87; // edi
  HDC v88; // rsi
  int v89; // r15d
  int v90; // r10d
  int v91; // kr00_4
  __int16 *v92; // rdx
  int v93; // r14d
  int v94; // r8d
  int v95; // r9d
  __int16 v96; // cx
  int v97; // eax
  unsigned int v98; // eax
  int v99; // eax
  _BYTE *v100; // rsi
  __int64 v101; // rbx
  unsigned __int16 v102; // ax
  int ExtentMinusPrefixes; // eax
  _BYTE *v104; // rdi
  __int16 v105; // cx
  PVOID Heap; // rax
  PVOID v107; // rax
  unsigned int v108; // r15d
  int v109; // r8d
  const WCHAR *v110; // rdx
  int v111; // r13d
  const WCHAR *v112; // r9
  unsigned int v113; // edi
  const WCHAR *v114; // r14
  int v115; // r13d
  int v116; // esi
  const WCHAR *v117; // rcx
  unsigned int v118; // eax
  unsigned int v119; // esi
  int v120; // r10d
  const WCHAR *v121; // r9
  int v122; // esi
  int v123; // esi
  int v124; // eax
  int v125; // eax
  unsigned __int64 v126; // rdi
  unsigned __int64 v127; // rdi
  __int16 v128; // ax
  int v129; // eax
  __int16 v130; // ax
  __int16 v131; // ax
  int v132; // eax
  int v133; // eax
  int v134; // eax
  int lpDefaultChar; // [rsp+30h] [rbp-D0h]
  int lpDefaultChara; // [rsp+30h] [rbp-D0h]
  unsigned int v137; // [rsp+68h] [rbp-98h]
  int v139; // [rsp+78h] [rbp-88h]
  unsigned int v140; // [rsp+78h] [rbp-88h]
  int v141; // [rsp+78h] [rbp-88h]
  int v142; // [rsp+78h] [rbp-88h]
  int v143; // [rsp+7Ch] [rbp-84h]
  unsigned int v144; // [rsp+7Ch] [rbp-84h]
  int v145; // [rsp+7Ch] [rbp-84h]
  int v146; // [rsp+80h] [rbp-80h]
  unsigned int v147; // [rsp+80h] [rbp-80h]
  int v148; // [rsp+80h] [rbp-80h]
  WCHAR String[2]; // [rsp+84h] [rbp-7Ch] BYREF
  struct tagSIZE v150; // [rsp+88h] [rbp-78h] BYREF
  tagSIZE sz; // [rsp+90h] [rbp-70h] BYREF
  struct tagSIZE v152; // [rsp+98h] [rbp-68h] BYREF
  WCHAR v153[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v154; // [rsp+A4h] [rbp-5Ch]
  unsigned int v155; // [rsp+A8h] [rbp-58h]
  PVOID P; // [rsp+B0h] [rbp-50h]
  WCHAR WideCharStr; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v158; // [rsp+C0h] [rbp-40h]
  __int16 v159; // [rsp+C2h] [rbp-3Eh]
  LPCWSTR lpString; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v161; // [rsp+D0h] [rbp-30h]
  UINT align; // [rsp+D8h] [rbp-28h]
  int v163; // [rsp+DCh] [rbp-24h]
  void *Src; // [rsp+E0h] [rbp-20h]
  int v165; // [rsp+E8h] [rbp-18h]
  unsigned int v166; // [rsp+ECh] [rbp-14h]
  unsigned __int64 v167; // [rsp+F0h] [rbp-10h]
  struct tagRECT *v168; // [rsp+F8h] [rbp-8h]
  HRGN hrgn; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v170; // [rsp+108h] [rbp+8h]
  const WCHAR *v171; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v172; // [rsp+118h] [rbp+18h]
  struct tagDRAWTEXTPARAMS *v173; // [rsp+120h] [rbp+20h]
  unsigned int v174; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v175[4]; // [rsp+134h] [rbp+34h] BYREF
  unsigned int v176; // [rsp+138h] [rbp+38h]
  int v177; // [rsp+140h] [rbp+40h]
  int v178; // [rsp+144h] [rbp+44h]
  int v179; // [rsp+148h] [rbp+48h]
  int v180; // [rsp+14Ch] [rbp+4Ch]
  int v181; // [rsp+150h] [rbp+50h]
  int v182; // [rsp+154h] [rbp+54h]
  int v183; // [rsp+158h] [rbp+58h]
  void (__fastcall *v184)(HDC, _QWORD, _QWORD, const WCHAR *, int, unsigned int); // [rsp+160h] [rbp+60h]
  int v185; // [rsp+168h] [rbp+68h]
  int v186; // [rsp+16Ch] [rbp+6Ch]
  int v187; // [rsp+170h] [rbp+70h]
  _BYTE v188[256]; // [rsp+180h] [rbp+80h] BYREF

  LODWORD(v7) = a3;
  v8 = a5;
  v9 = hdc;
  v10 = a2;
  Src = a2;
  v150 = (struct tagSIZE)a3;
  v173 = a6;
  v11 = a4;
  v168 = a4;
  v174 = 0;
  memset_0(v175, 0, 0x44u);
  if ( !v10 )
    return 0;
  if ( (_DWORD)v7 )
  {
    if ( (_DWORD)v7 == -1 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v10[v7] );
      v150 = (struct tagSIZE)v7;
    }
  }
  else if ( *v10 )
  {
    return 1;
  }
  if ( a6 && a6->cbSize != 20 )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  if ( !(unsigned int)DT_InitDrawTextInfo(v9, v11, a5, (struct DRAWTEXTDATA *)&v174, a6) )
    return 0;
  v187 = a7;
  if ( v181 <= 0 )
  {
    if ( LODWORD(NtCurrentTeb()->Win32ClientInfo[2]) < 0x400 )
    {
      if ( !v181 && (a5 & 0x400) == 0 )
        return 1;
    }
    else if ( (a5 & 0x10) != 0 )
    {
      return 1;
    }
  }
  align = 0;
  v166 = a5 & 0x20000;
  if ( (a5 & 0x20000) != 0 )
  {
    TextAlign = GetTextAlign(v9);
    align = SetTextAlign(v9, TextAlign | 0x100);
  }
  if ( (a5 & 0x100) != 0 )
  {
    hrgn = 0;
  }
  else
  {
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    hrgn = RectRgn;
    v14 = RectRgn;
    if ( RectRgn )
    {
      if ( GetClipRgn(v9, RectRgn) != 1 )
      {
        DeleteObject(v14);
        hrgn = (HRGN)-1LL;
      }
      IntersectClipRect(v9, v11->left, v11->top, v11->right, v11->bottom);
    }
  }
  v15 = v180;
  v16 = a5 & 0x20;
  v17 = v10;
  v170 = v10;
  v159 = v16;
  v18 = (unsigned __int64)&v10[(int)v7];
  v167 = v18;
  v158 = a5 & 0x400;
  while ( 1 )
  {
    top = v11->top;
    v137 = top;
    if ( v16 )
    {
      v32 = v8 & 0xC;
      v154 = 1;
      if ( v32 == 4 )
      {
        v85 = v11->bottom - top - v15;
        top += ((int)v85 - HIDWORD(v85)) >> 1;
        v137 = top;
      }
      else if ( v32 == 8 )
      {
        top = v11->bottom - v15;
        v137 = top;
      }
      v33 = Src;
      P = 0;
      v143 = 0;
      lpString = (LPCWSTR)Src;
      if ( (v8 & 0x4000) != 0 )
      {
        ExtentMinusPrefixes = DT_GetExtentMinusPrefixes(
                                v9,
                                (LPCWSTR)Src,
                                v7,
                                v8,
                                v185,
                                (struct DRAWTEXTDATA *)&v174,
                                a7);
        if ( ExtentMinusPrefixes > v181 )
        {
          if ( (v8 & 0x10000) == 0 )
          {
            if ( (int)v7 + 4 > 128 )
            {
              Heap = RtlAllocateHeap(pUserHeap, 8u, (unsigned int)(2 * v7 + 8));
              P = Heap;
              if ( !Heap )
              {
                LODWORD(v7) = 0;
                goto LABEL_38;
              }
              v104 = Heap;
            }
            else
            {
              v104 = v188;
            }
            memcpy_0(v104, v33, 2LL * (int)v7);
            v33 = v104;
            lpString = (LPCWSTR)v104;
            v143 = 1;
          }
          v7 = (unsigned int)AddPathEllipsis(
                               v9,
                               (unsigned __int16 *)v33,
                               v7,
                               v8,
                               v181,
                               v185,
                               (struct DRAWTEXTDATA *)&v174,
                               a7);
          v150 = (struct tagSIZE)v7;
        }
      }
      if ( (v8 & 0x48000) != 0 )
      {
        sz = 0;
        if ( (_DWORD)v7 )
        {
          v34 = v181;
          v35 = 0;
          v36 = v185;
          v139 = v181;
          v37 = v7;
          v148 = v185;
          v38 = (__int16 *)v33;
          String[0] = 38;
          v39 = v7;
          v152 = 0;
          while ( v37 > 0 )
          {
            v40 = *v38;
            if ( !*v38 || v39 <= 0 )
              break;
            --v37;
            --v39;
            ++v38;
            switch ( v40 )
            {
              case 38:
                ++v35;
                if ( *v38 == 38 )
                {
                  --v37;
                  ++v38;
                }
                break;
              case 30:
                ++v35;
                break;
              case 31:
                ++v35;
                if ( !v37 )
                  goto LABEL_24;
                ++v35;
                ++v38;
                --v37;
                break;
            }
          }
LABEL_24:
          if ( v186 )
          {
            v24 = ((__int64 (__fastcall *)(HDC, _QWORD, _QWORD, void *, _DWORD, _DWORD, unsigned int, unsigned int *, int, int))fpLpkDrawTextEx)(
                    v9,
                    0,
                    0,
                    v33,
                    v7,
                    0,
                    v8,
                    &v174,
                    1,
                    a7);
          }
          else
          {
            v122 = 0;
            if ( (v8 & 0x800) == 0 )
            {
              v126 = (unsigned __int64)((unsigned __int16)v35 << 16) >> 16;
              if ( (_WORD)v35 )
              {
                GetTextExtentPointW(v9, String, 1, &v152);
                v122 = (unsigned __int16)v126 * (v152.cx - v36);
              }
              v34 = v139;
            }
            GetTextExtentPointW(v9, (LPCWSTR)v33, v7, &v152);
            v24 = v152.cx - v122;
          }
          if ( v24 > v34 && GetTextExtentPointW(v9, L"...", 3, &sz) )
          {
            v86 = 1;
            v87 = v36 - sz.cx + v34;
            v141 = v87;
            if ( v87 > 0 )
            {
              v88 = hdc;
              v89 = 0;
              v86 = v7;
              while ( v89 < v86 )
              {
                v150 = 0;
                v90 = 0;
                v91 = v86 + v89 + 1;
                v92 = (__int16 *)v33;
                v93 = v91 / 2;
                v153[0] = 38;
                v94 = v91 / 2;
                v95 = v91 / 2;
                while ( v94 > 0 )
                {
                  v96 = *v92;
                  if ( !*v92 || v95 <= 0 )
                    break;
                  --v94;
                  --v95;
                  ++v92;
                  switch ( v96 )
                  {
                    case 38:
                      ++v90;
                      if ( *v92 == 38 )
                      {
                        --v94;
                        ++v92;
                      }
                      break;
                    case 30:
                      ++v90;
                      break;
                    case 31:
                      ++v90;
                      if ( !v94 )
                        goto LABEL_172;
                      ++v90;
                      ++v92;
                      --v94;
                      break;
                  }
                }
LABEL_172:
                if ( v186 )
                {
                  v97 = ((__int64 (__fastcall *)(HDC, _QWORD, _QWORD, void *, int, _DWORD, unsigned int, unsigned int *, int, int))fpLpkDrawTextEx)(
                          v88,
                          0,
                          0,
                          v33,
                          v91 / 2,
                          0,
                          a5,
                          &v174,
                          1,
                          a7);
                }
                else
                {
                  v123 = 0;
                  if ( (a5 & 0x800) == 0 )
                  {
                    v127 = (unsigned __int64)((unsigned __int16)v90 << 16) >> 16;
                    if ( (_WORD)v90 )
                    {
                      GetTextExtentPointW(hdc, v153, 1, &v150);
                      v123 = (unsigned __int16)v127 * (v150.cx - v148);
                    }
                    v87 = v141;
                  }
                  GetTextExtentPointW(hdc, (LPCWSTR)v33, v93, &v150);
                  v97 = v150.cx - v123;
                  v88 = hdc;
                }
                if ( v97 >= v87 )
                {
                  if ( v97 <= v87 )
                  {
                    v86 = v91 / 2;
                    break;
                  }
                  v86 = v93 - 1;
                }
                else
                {
                  v89 = v91 / 2;
                }
              }
              v9 = hdc;
              if ( v86 < 1 )
                v86 = 1;
            }
            v99 = DT_AdjustBreakForSurrogatesAndVariationSelectors((const unsigned __int16 *)v33, v86, v7);
            v8 = a5;
            v100 = v33;
            v101 = v99;
            if ( (a5 & 0x10000) == 0 && !v143 )
            {
              if ( v99 + 4 > 128 )
              {
                v107 = RtlAllocateHeap(pUserHeap, 8u, (unsigned int)(2 * (v99 + 4)));
                P = v107;
                if ( !v107 )
                {
                  LODWORD(v7) = 0;
LABEL_37:
                  top = v137;
LABEL_38:
                  v15 = v180;
                  LODWORD(v10) = (_DWORD)Src + 2 * v7;
LABEL_39:
                  top += v15;
                  goto LABEL_40;
                }
                v100 = v107;
              }
              else
              {
                v100 = v188;
              }
              memcpy_0(v100, v33, 2 * v101);
              lpString = (LPCWSTR)v100;
              *(_WORD *)&v100[2 * v101] = 0;
              v33 = v100;
            }
            *(_QWORD *)&v100[2 * v101] = 0x2E002E002ELL;
            v7 = (unsigned int)(v101 + 3);
            v150 = (struct tagSIZE)v7;
          }
        }
      }
      if ( (v8 & 3) != 0 )
      {
        v78 = v174;
        v79 = v177;
        v80 = v174 - 1;
        if ( (GetLayout(v9) & 1) == 0 )
          v80 = v78;
        v155 = v80;
        if ( v186 )
        {
          v81 = ((__int64 (__fastcall *)(HDC, _QWORD, _QWORD, void *, _DWORD, _DWORD, unsigned int, unsigned int *, int, int))fpLpkDrawTextEx)(
                  v9,
                  v80,
                  v137,
                  v33,
                  v7,
                  0,
                  a5,
                  &v174,
                  1,
                  a7);
          v82 = v185;
          v83 = v81;
          v26 = a5 & 0x40;
        }
        else
        {
          v26 = a5 & 0x40;
          if ( (a5 & 0x40) != 0 )
          {
            v82 = v185;
            v108 = v80;
            if ( (_DWORD)v7 )
            {
              v109 = v7;
              v110 = (const WCHAR *)v33;
              v145 = v7;
              do
              {
                v111 = 0;
                v112 = v110;
                if ( v109 > 0 )
                {
                  do
                  {
                    v128 = *v112++;
                    if ( v128 == 9 )
                      break;
                    ++v111;
                  }
                  while ( v111 < v109 );
                  sz = (tagSIZE)v112;
                  if ( !v111
                    || (v124 = DT_GetExtentMinusPrefixes(hdc, v110, v111, a5, v82, (struct DRAWTEXTDATA *)&v174, a7),
                        v82 = v185,
                        v109 = v145,
                        v108 += v124 - v185,
                        v112 = (const WCHAR *)sz,
                        v111 < v145) )
                  {
                    ++v111;
                    if ( v79 )
                      v108 = v79 + v108 - (int)(v108 - v78) % v79;
                  }
                }
                v109 -= v111;
                v110 = v112;
                v145 = v109;
              }
              while ( v109 );
              LODWORD(v7) = v150.cx;
              v26 = a5 & 0x40;
              v80 = v155;
            }
            v33 = (void *)lpString;
            v83 = v108 - v80;
          }
          else
          {
            v129 = DT_GetExtentMinusPrefixes(v9, (LPCWSTR)v33, v7, a5, v185, (struct DRAWTEXTDATA *)&v174, a7);
            v82 = v185;
            v83 = v129 - v185;
          }
        }
        v25 = v176 - (v82 + v83);
        if ( (a5 & 1) != 0 )
          v25 = v174 + ((int)(v25 - v174) >> 1);
      }
      else
      {
        v25 = v174;
        v26 = v8 & 0x40;
      }
      v27 = v177;
      v28 = v174;
      v29 = v25 - 1;
      if ( (GetLayout(hdc) & 1) == 0 )
        v29 = v25;
      v147 = v29;
      if ( v186 )
      {
        v8 = a5;
        v9 = hdc;
        v30 = ((__int64 (__fastcall *)(HDC, _QWORD, _QWORD, void *, _DWORD, int, unsigned int, unsigned int *, int, int))fpLpkDrawTextEx)(
                hdc,
                v29,
                v137,
                v33,
                v7,
                1,
                a5,
                &v174,
                1,
                a7);
      }
      else if ( v26 )
      {
        v113 = v29;
        if ( (_DWORD)v7 )
        {
          v114 = lpString;
          v115 = v7;
          do
          {
            v116 = 0;
            v117 = v114;
            if ( v115 > 0 )
            {
              do
              {
                v130 = *v117++;
                if ( v130 == 9 )
                  break;
                ++v116;
              }
              while ( v116 < v115 );
              sz = (tagSIZE)v117;
              if ( !v116 )
                goto LABEL_295;
              if ( (a5 & 0x400) == 0 )
                v184(hdc, v113, v137, v114, v116, a5);
              v133 = DT_GetExtentMinusPrefixes(hdc, v114, v116, a5, v185, (struct DRAWTEXTDATA *)&v174, a7);
              v117 = (const WCHAR *)sz;
              v113 += v133 - v185;
              if ( v116 < v115 )
              {
LABEL_295:
                ++v116;
                if ( v27 )
                  v113 = v27 + v113 - (int)(v113 - v28) % v27;
              }
            }
            v114 = v117;
            v115 -= v116;
          }
          while ( v115 );
          LODWORD(v7) = v150.cx;
          v29 = v147;
        }
        v8 = a5;
        v30 = v113 - v29;
        v9 = hdc;
      }
      else
      {
        v8 = a5;
        v9 = hdc;
        if ( (a5 & 0x400) == 0 )
          v184(hdc, v29, v137, (const WCHAR *)v33, v7, a5);
        v134 = DT_GetExtentMinusPrefixes(hdc, (LPCWSTR)v33, v7, a5, v185, (struct DRAWTEXTDATA *)&v174, a7);
        v30 = v134 - v185;
      }
      if ( (int)(v30 + v185) > v182 )
        v182 = v30 + v185;
      if ( P )
        RtlFreeHeap(pUserHeap, 0, P);
      goto LABEL_37;
    }
    v20 = 0;
    v154 = 0;
    if ( (v8 & 0x2000) != 0 )
      v20 = v15;
    v165 = v20;
    if ( (unsigned __int64)Src < v18 )
    {
      v21 = v179;
      v22 = 0;
      v146 = 0;
      v10 = (unsigned __int16 *)Src;
      LODWORD(lpString) = v179;
      sz = (tagSIZE)Src;
      while ( 1 )
      {
        if ( v22 )
          goto LABEL_130;
        if ( (v8 & 0x500) == 0 && v21 * (top + v15 + v20) > v11->bottom * v21 )
        {
          v146 = 1;
          v22 = 1;
          if ( (v8 & 0xC000) != 0 )
          {
            v10 += (int)AddEllipsisAndDrawLine(v9, top, v10, v7, v8, (struct DRAWTEXTDATA *)&v174, a7);
            sz = (tagSIZE)v10;
            goto LABEL_129;
          }
        }
        v161 = 0;
        v43 = 0;
        v163 = 0;
        CodePage = GdiGetCodePage(v9);
        *(_DWORD *)v153 = CodePage;
        v45 = v10;
        v144 = v174;
        v46 = &v10[(int)v7];
        v155 = 0;
        P = v46;
        v152 = (struct tagSIZE)v10;
        while ( 2 )
        {
          if ( v45 >= v46 )
          {
            v70 = v163;
            goto LABEL_122;
          }
          v161 = v45;
          v47 = 0;
          v48 = v45;
          LOBYTE(String[0]) = 0;
          v49 = 1;
          v50 = v45;
          v51 = v8 & 0x10;
          v52 = (v8 & 0x10) != 0 && (v8 & 0x80000) == 0;
          while ( v48 < v46 )
          {
            v53 = *v48;
            if ( v53 <= 0x20 )
            {
              if ( v53 == 32 || v53 == 9 )
              {
LABEL_95:
                if ( v51 )
                {
                  LODWORD(v48) = (_DWORD)v48 + 2 * v49;
                  break;
                }
                goto LABEL_82;
              }
              if ( v53 == 10 || v53 == 13 )
                break;
LABEL_82:
              if ( v52 )
              {
                WideCharStr = *v48;
                if ( (unsigned __int16)v53 >= 0x80u )
                {
                  for ( i = 0; i < 4; ++i )
                  {
                    if ( (unsigned __int16)v53 >= *((_WORD *)qword_1800AA200 + 2 * i)
                      && (unsigned __int16)v53 <= *((_WORD *)qword_1800AA200 + 2 * i + 1) )
                    {
                      goto LABEL_153;
                    }
                  }
                  if ( WideCharToMultiByte(CodePage, 0, &WideCharStr, 1, 0, 0, 0, 0) <= 1 )
                  {
                    v50 = (WCHAR *)v161;
                    goto LABEL_83;
                  }
LABEL_153:
                  if ( v49 )
                  {
                    v84 = v48 + 1;
                    if ( v48 + 1 == v46 || !(unsigned int)UserIsFELineBreakEnd(*v84) )
                      LODWORD(v48) = (_DWORD)v84;
                    else
                      LODWORD(v48) = (_DWORD)v48 + 4;
                  }
                  break;
                }
              }
LABEL_83:
              if ( v51 && v48 >= v50 && v186 )
              {
                v54 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, WCHAR *, _DWORD, _DWORD, _DWORD, _QWORD, int, int))fpLpkDrawTextEx)(
                        0,
                        0,
                        0,
                        v48,
                        v46 - v48,
                        0,
                        0,
                        0,
                        2,
                        -1);
                v55 = 2LL * v54;
                if ( v54 > 0 )
                {
                  LODWORD(v48) = v55 + (_DWORD)v48;
                  break;
                }
                v50 = &v48[v55 / 0xFFFFFFFFFFFFFFFEuLL];
                v161 = &v48[v55 / 0xFFFFFFFFFFFFFFFEuLL];
              }
              CodePage = *(_DWORD *)v153;
              v49 = 0;
LABEL_85:
              v47 = String[0];
              ++v48;
            }
            else
            {
              if ( v53 != 38 )
              {
                if ( (_WORD)v53 == 0xF020 )
                  goto LABEL_95;
                goto LABEL_82;
              }
              if ( (a5 & 0x800) != 0 )
                goto LABEL_82;
              v49 = v47 == 0;
              if ( v47 )
              {
                LOBYTE(String[0]) = 0;
                goto LABEL_85;
              }
              LOBYTE(String[0]) = 1;
              ++v48;
              v47 = 1;
            }
          }
          v56 = v152;
          v57 = (unsigned __int64)((int)v48 - v152.cx) >> 1;
          if ( (_DWORD)v57 )
          {
            v58 = (unsigned __int64)((int)v46 - v152.cx) >> 1;
            LongChar = DT_GetLongChar(*(const unsigned __int16 **)&v152, v57 - 1, v58);
            v60 = LongChar;
            if ( LongChar < 0x10000 )
            {
              if ( LongChar >= 0xFE00 )
              {
                if ( LongChar > 0xFE0F )
                  goto LABEL_101;
                goto LABEL_103;
              }
LABEL_102:
              if ( (int)v57 < (int)v58 )
              {
                v98 = DT_GetLongChar(*(const unsigned __int16 **)&v152, v57, v58);
                if ( v98 - 65024 <= 0xF || v98 - 917760 <= 0xEF )
                  LODWORD(v57) = 2 - (v98 < 0x10000) + v57;
              }
              goto LABEL_103;
            }
            if ( (unsigned int)Feature_Servicing_ComponentServicesFreeze__private_IsEnabledDeviceUsageNoInline() )
            {
              if ( (int)v57 <= 1 )
                LODWORD(v57) = v57 + 1;
              else
                LODWORD(v57) = v57 - 1;
            }
            else
            {
              LODWORD(v57) = v57 + 1;
            }
LABEL_101:
            if ( v60 - 917760 > 0xEF )
              goto LABEL_102;
LABEL_103:
            v56 = v152;
          }
          else
          {
            LODWORD(v57) = 0;
          }
          v61 = v10;
          v62 = v177;
          v43 = (const unsigned __int16 *)(*(_QWORD *)&v56 + 2LL * (int)v57);
          v172 = v43;
          v161 = v43;
          v63 = (unsigned __int64)((char *)v43 - (char *)v10) >> 1;
          v140 = v174;
          v64 = v144;
          if ( (GetLayout(hdc) & 1) != 0 )
            v64 = v144 - 1;
          if ( v186 )
          {
            v8 = a5;
            v65 = ((__int64 (__fastcall *)(HDC, _QWORD, _QWORD, unsigned __int16 *, _DWORD, _DWORD, unsigned int, unsigned int *, int, int))fpLpkDrawTextEx)(
                    hdc,
                    v64,
                    0,
                    v10,
                    (unsigned __int64)((char *)v43 - (char *)v10) >> 1,
                    0,
                    a5,
                    &v174,
                    1,
                    a7);
            v66 = v185;
            v67 = v65;
          }
          else if ( (a5 & 0x40) != 0 )
          {
            v66 = v185;
            v118 = v64;
            *(_DWORD *)String = v64;
            if ( (_DWORD)v63 )
            {
              v119 = v140;
              do
              {
                v120 = 0;
                v121 = v61;
                if ( (int)v63 > 0 )
                {
                  do
                  {
                    v131 = *v121++;
                    if ( v131 == 9 )
                      break;
                    ++v120;
                  }
                  while ( v120 < (int)v63 );
                  v171 = v121;
                  v142 = v120;
                  if ( !v120
                    || (v125 = DT_GetExtentMinusPrefixes(hdc, v61, v120, a5, v66, (struct DRAWTEXTDATA *)&v174, a7),
                        v66 = v185,
                        v120 = v142,
                        v64 += v125 - v185,
                        v121 = v171,
                        v142 < (int)v63) )
                  {
                    ++v120;
                    if ( v62 )
                      v64 += v62 - (int)(v64 - v119) % v62;
                  }
                }
                v61 = v121;
                LODWORD(v63) = v63 - v120;
              }
              while ( (_DWORD)v63 );
              LODWORD(v7) = v150.cx;
              v10 = (unsigned __int16 *)sz;
              v43 = v172;
              v118 = *(_DWORD *)String;
            }
            v8 = a5;
            v67 = v64 - v118;
          }
          else
          {
            v8 = a5;
            v132 = DT_GetExtentMinusPrefixes(hdc, v10, v63, a5, v185, (struct DRAWTEXTDATA *)&v174, a7);
            v66 = v185;
            v67 = v132 - v185;
          }
          if ( (v8 & 0x10) == 0 || (int)(v66 + v67) <= v181 )
          {
            v46 = (WCHAR *)P;
            if ( v43 < P )
            {
              v68 = *v43;
              if ( *v43 == 13 || v68 == 10 )
              {
                if ( ++v43 < P && *v43 == (v68 ^ 7) )
                  ++v43;
                v72 = (unsigned __int64)((int)v161 - (int)v10) >> 1;
                goto LABEL_123;
              }
            }
            CodePage = *(_DWORD *)v153;
            v45 = (WCHAR *)v43;
            v152 = (struct tagSIZE)v43;
            v155 = v67;
            continue;
          }
          break;
        }
        if ( *(unsigned __int16 **)&v152 != v10 )
        {
          v46 = (WCHAR *)P;
          v43 = (const unsigned __int16 *)v152;
          v71 = (unsigned __int64)(v152.cx - (int)v10) >> 1;
          LODWORD(v72) = v71;
LABEL_138:
          if ( v43 < v46 )
          {
            v76 = v8 & 3;
            if ( v76 == 1 )
            {
              v77 = *(v43 - 1);
              if ( v77 == 32 || v77 == 9 )
                LODWORD(v72) = v72 - 1;
              if ( *v43 == 32 || *v43 == 9 )
LABEL_313:
                ++v43;
            }
            else if ( (v8 & 3) != 0 )
            {
              if ( v76 == 2 )
              {
                v105 = *(v43 - 1);
                if ( v105 == 9 || v105 == 32 )
                  LODWORD(v72) = v71 - 1;
              }
            }
            else if ( *v43 == 32 || *v43 == 9 )
            {
              goto LABEL_313;
            }
          }
LABEL_123:
          v73 = a7;
          v9 = hdc;
          goto LABEL_124;
        }
        if ( (v8 & 0x42000) != 0x2000 )
        {
          v70 = 1;
          v46 = (WCHAR *)P;
          if ( (v8 & 0x40000) != 0 && v43 < P )
          {
            v102 = *v43;
            if ( *v43 == 13 || v102 == 10 )
            {
              if ( ++v43 < P && *v43 == (v102 ^ 7) )
                ++v43;
              v70 = 0;
            }
          }
LABEL_122:
          v71 = (unsigned __int64)((int)v161 - (int)v10) >> 1;
          LODWORD(v72) = v71;
          if ( v70 )
            goto LABEL_138;
          goto LABEL_123;
        }
        v73 = a7;
        v9 = hdc;
        v43 = DT_BreakAWord(
                hdc,
                *(const unsigned __int16 **)&v152,
                ((unsigned __int64)v43 - *(_QWORD *)&v152) >> 1,
                v181 - v155,
                v8,
                v66,
                (struct DRAWTEXTDATA *)&v174,
                a7);
        v72 = (unsigned __int64)((int)v43 - (int)v10) >> 1;
LABEL_124:
        if ( (v8 & 0x40000) != 0 || (unsigned __int64)v43 >= v167 && (v8 & 0xC000) != 0 )
        {
          lpDefaultChar = v73;
          top = v137;
          AddEllipsisAndDrawLine(v9, v137, v10, v72, v8, (struct DRAWTEXTDATA *)&v174, lpDefaultChar);
        }
        else
        {
          lpDefaultChara = v73;
          top = v137;
          DT_DrawJustifiedLine(v9, v137, v10, v72, v8, (struct DRAWTEXTDATA *)&v174, lpDefaultChara);
        }
        v11 = v168;
        v74 = (_DWORD)v43 - (_DWORD)v10;
        sz = (tagSIZE)v43;
        v10 = (unsigned __int16 *)v43;
        v22 = v146;
        LODWORD(v7) = v7 - ((unsigned __int64)v74 >> 1);
        v150 = (struct tagSIZE)(unsigned int)v7;
LABEL_129:
        v15 = v180;
        top += v180;
        ++v154;
        v18 = v167;
        v20 = v165;
        v21 = (int)lpString;
        v137 = top;
        if ( (unsigned __int64)v10 >= v167 )
        {
LABEL_130:
          v17 = v170;
          break;
        }
      }
    }
    if ( (v8 & 0x2000) == 0 && v18 > (unsigned __int64)v17 )
    {
      v75 = *(_WORD *)(v18 - 2);
      if ( v75 == 13 || v75 == 10 )
        goto LABEL_39;
    }
LABEL_40:
    v11 = v168;
    if ( !v158 )
      goto LABEL_41;
    v41 = v182;
    v176 = v174 + v182 * v178;
    v42 = v154 <= 1;
    v168->right = v183 + v176;
    if ( v42 || v41 <= v181 )
      break;
    v18 = v167;
    v16 = v159;
    v181 = v41;
    v17 = v170;
    LODWORD(v10) = (_DWORD)v170;
    v7 = (unsigned __int64)((int)v167 - (int)v170) >> 1;
    v150 = (struct tagSIZE)v7;
  }
  v11->bottom = top;
LABEL_41:
  v31 = hrgn;
  if ( hrgn )
  {
    if ( hrgn == (HRGN)-1LL )
    {
      ExtSelectClipRgn(v9, 0, 5);
    }
    else
    {
      ExtSelectClipRgn(v9, hrgn, 5);
      DeleteObject(v31);
    }
  }
  if ( v166 )
    SetTextAlign(v9, align);
  if ( v173 )
    v173->uiLengthDrawn = (unsigned int)((_DWORD)v10 - (_DWORD)v170) >> 1;
  result = (unsigned int)(top - v11->top);
  if ( top == v11->top )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180023330  push    rbp
0x180023332  push    rbx
0x180023333  push    rsi
0x180023334  push    rdi
0x180023335  push    r12
0x180023337  push    r13
0x180023339  push    r14
0x18002333b  push    r15
0x18002333d  lea     rbp, [rsp-198h]
0x180023345  sub     rsp, 298h
0x18002334c  mov     rax, cs:__security_cookie
0x180023353  xor     rax, rsp
0x180023356  mov     [rbp+1D0h+var_50], rax
0x18002335d  mov     rsi, [rbp+1D0h+arg_28]
0x180023364  mov     ebx, r8d
0x180023367  mov     r12d, [rbp+1D0h+arg_20]
0x18002336e  mov     r15, rcx
0x180023371  mov     r14d, [rbp+1D0h+arg_30]
0x180023378  mov     rdi, rdx
0x18002337b  mov     [rbp+1D0h+Src], rdx
0x18002337f  mov     r8d, 44h ; 'D'; Size
0x180023385  mov     [rsp+2D0h+hdc], rcx
0x18002338a  xor     edx, edx; Val
0x18002338c  lea     rcx, [rbp+1D0h+var_19C]; void *
0x180023390  mov     qword ptr [rbp+1D0h+var_248.cx], rbx
0x180023394  mov     [rbp+1D0h+var_1B0], rsi
0x180023398  mov     r13, r9
0x18002339b  mov     [rbp+1D0h+var_1D8], r9
0x18002339f  mov     [rsp+2D0h+var_26C], r12d
0x1800233a4  mov     [rsp+2D0h+var_270], r14d
0x1800233a9  mov     [rbp+1D0h+var_1A0], 0
0x1800233b0  call    memset_0
0x1800233b5  test    rdi, rdi
0x1800233b8  jz      loc_180023549
0x1800233be  test    ebx, ebx
0x1800233c0  jz      loc_18002410D
0x1800233c6  cmp     ebx, 0FFFFFFFFh
0x1800233c9  jnz     short loc_1800233E0
0x1800233cb  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800233d2  inc     rbx
0x1800233d5  cmp     word ptr [rdi+rbx*2], 0
0x1800233da  jnz     short loc_1800233D2
0x1800233dc  mov     qword ptr [rbp+1D0h+var_248.cx], rbx
0x1800233e0  test    rsi, rsi
0x1800233e3  jnz     loc_1800240FF
0x1800233e9  lea     r9, [rbp+1D0h+var_1A0]; struct DRAWTEXTDATA *
0x1800233ed  mov     qword ptr [rsp+2D0h+bottom], rsi; struct tagDRAWTEXTPARAMS *
0x1800233f2  mov     r8d, r12d; unsigned int
0x1800233f5  mov     rdx, r13; struct tagRECT *
0x1800233f8  mov     rcx, r15; hdc
0x1800233fb  call    ?DT_InitDrawTextInfo@@YAHPEAUHDC__@@PEAUtagRECT@@IPEAUDRAWTEXTDATA@@PEAUtagDRAWTEXTPARAMS@@@Z; DT_InitDrawTextInfo(HDC__ *,tagRECT *,uint,DRAWTEXTDATA *,tagDRAWTEXTPARAMS *)
0x180023400  test    eax, eax
0x180023402  jz      loc_180023549
0x180023408  cmp     [rbp+1D0h+var_180], 0
0x18002340c  mov     [rbp+1D0h+var_160], r14d
0x180023410  mov     r14d, 400h
0x180023416  jle     loc_180023F34
0x18002341c  mov     eax, r12d
0x18002341f  mov     [rbp+1D0h+align], 0
0x180023426  and     eax, 20000h
0x18002342b  mov     esi, 100h
0x180023430  mov     [rbp+1D0h+var_1E4], eax
0x180023433  jz      short loc_18002344E
0x180023435  mov     rcx, r15; hdc
0x180023438  call    cs:__imp_GetTextAlign
0x18002343e  or      eax, esi
0x180023440  mov     rcx, r15; hdc
0x180023443  mov     edx, eax; align
0x180023445  call    cs:__imp_SetTextAlign
0x18002344b  mov     [rbp+1D0h+align], eax
0x18002344e  test    si, r12w
0x180023452  jnz     loc_1800237D5
0x180023458  xor     r9d, r9d; y2
0x18002345b  xor     r8d, r8d; x2
0x18002345e  xor     edx, edx; y1
0x180023460  xor     ecx, ecx; x1
0x180023462  call    cs:__imp_CreateRectRgn
0x180023468  mov     [rbp+1D0h+hrgn], rax
0x18002346c  mov     rsi, rax
0x18002346f  test    rax, rax
0x180023472  jz      short loc_1800234B3
0x180023474  mov     rdx, rax; hrgn
0x180023477  mov     rcx, r15; hdc
0x18002347a  call    cs:__imp_GetClipRgn
0x180023480  cmp     eax, 1
0x180023483  jz      short loc_180023496
0x180023485  mov     rcx, rsi; ho
0x180023488  call    cs:__imp_DeleteObject
0x18002348e  mov     [rbp+1D0h+hrgn], 0FFFFFFFFFFFFFFFFh
0x180023496  mov     eax, [r13+0Ch]
0x18002349a  mov     rcx, r15; hdc
0x18002349d  mov     r9d, [r13+8]; right
0x1800234a1  mov     r8d, [r13+4]; top
0x1800234a5  mov     edx, [r13+0]; left
0x1800234a9  mov     [rsp+2D0h+bottom], eax; bottom
0x1800234ad  call    cs:__imp_IntersectClipRect
0x1800234b3  mov     edx, [rbp+1D0h+var_184]
0x1800234b6  movzx   ecx, r12w
0x1800234ba  movsxd  rax, ebx
0x1800234bd  and     cx, 20h
0x1800234c1  mov     r8, rdi
0x1800234c4  mov     [rbp+1D0h+var_1C8], rdi
0x1800234c8  mov     [rbp+1D0h+var_20E], cx
0x1800234cc  mov     r11d, 2000h
0x1800234d2  lea     r9, [rdi+rax*2]
0x1800234d6  movzx   eax, r12w
0x1800234da  and     ax, r14w
0x1800234de  mov     [rbp+1D0h+var_1E0], r9
0x1800234e2  mov     [rbp+1D0h+var_210], ax
0x1800234e6  mov     r10d, 1
0x1800234ec  nop     dword ptr [rax+00h]
0x1800234f0  mov     r14d, [r13+4]
0x1800234f4  mov     [rsp+2D0h+var_268], r14d
0x1800234f9  test    cx, cx
0x1800234fc  jnz     loc_1800236F7
0x180023502  mov     rcx, [rbp+1D0h+Src]
0x180023506  test    r11w, r12w
0x18002350a  mov     eax, 0
0x18002350f  mov     [rbp+1D0h+var_22C], 0
0x180023516  cmovnz  eax, edx
0x180023519  mov     [rbp+1D0h+var_1E8], eax
0x18002351c  cmp     rcx, r9
0x18002351f  jnb     loc_180023C2C
0x180023525  mov     r8d, [rbp+1D0h+var_188]
0x180023529  xor     esi, esi
0x18002352b  mov     [rbp+1D0h+var_250], esi
0x18002352e  mov     rdi, rcx
0x180023531  mov     dword ptr [rbp+1D0h+lpString], r8d
0x180023535  mov     qword ptr [rbp+1D0h+sz.cx], rcx
0x180023539  jmp     loc_180023846
0x18002353e  mov     ecx, 57h ; 'W'; LastError
0x180023543  call    cs:__imp_RtlSetLastWin32Error
0x180023549  xor     eax, eax
0x18002354b  jmp     loc_1800236D4
0x180023550  cmp     [rbp+1D0h+var_164], 0
0x180023554  jz      loc_18002444B
0x18002355a  mov     [rsp+2D0h+var_288], esi
0x18002355e  lea     rax, [rbp+1D0h+var_1A0]
0x180023562  mov     [rsp+2D0h+var_290], r10d
0x180023567  mov     r9, r13
0x18002356a  mov     [rsp+2D0h+lpUsedDefaultChar], rax
0x18002356f  xor     r8d, r8d
0x180023572  mov     rax, cs:fpLpkDrawTextEx
0x180023579  xor     edx, edx
0x18002357b  mov     dword ptr [rsp+2D0h+lpDefaultChar], r12d
0x180023580  mov     rcx, r15
0x180023583  mov     [rsp+2D0h+cbMultiByte], 0
0x18002358b  mov     [rsp+2D0h+bottom], ebx
0x18002358f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023594  cmp     eax, edi
0x180023596  jg      loc_180023DF4
0x18002359c  test    r12b, 3
0x1800235a0  jnz     loc_180023CDE
0x1800235a6  mov     edi, [rbp+1D0h+var_1A0]
0x1800235a9  mov     esi, r12d
0x1800235ac  and     esi, 40h
0x1800235af  mov     rcx, [rsp+2D0h+hdc]; hdc
0x1800235b4  mov     r15d, [rbp+1D0h+var_190]
0x1800235b8  mov     r12d, [rbp+1D0h+var_1A0]
0x1800235bc  call    cs:__imp_GetLayout
0x1800235c2  test    al, 1
0x1800235c4  lea     r14d, [rdi-1]
0x1800235c8  cmovz   r14d, edi
0x1800235cc  cmp     [rbp+1D0h+var_164], 0
0x1800235d0  mov     [rbp+1D0h+var_250], r14d
0x1800235d4  jz      loc_1800243A1
0x1800235da  mov     eax, [rsp+2D0h+var_270]
0x1800235de  lea     rcx, [rbp+1D0h+var_1A0]
0x1800235e2  mov     r12d, [rsp+2D0h+var_26C]
0x1800235e7  mov     r9, r13
0x1800235ea  mov     r15, [rsp+2D0h+hdc]
0x1800235ef  mov     edx, r14d
0x1800235f2  mov     r8d, [rsp+2D0h+var_268]
0x1800235f7  mov     [rsp+2D0h+var_288], eax
0x1800235fb  mov     eax, 1
0x180023600  mov     [rsp+2D0h+var_290], eax
0x180023604  mov     [rsp+2D0h+lpUsedDefaultChar], rcx
0x180023609  mov     rcx, r15
0x18002360c  mov     dword ptr [rsp+2D0h+lpDefaultChar], r12d
0x180023611  mov     [rsp+2D0h+cbMultiByte], eax
0x180023615  mov     rax, cs:fpLpkDrawTextEx
0x18002361c  mov     [rsp+2D0h+bottom], ebx
0x180023620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023625  mov     edi, eax
0x180023627  mov     ecx, [rbp+1D0h+var_168]
0x18002362a  add     ecx, edi
0x18002362c  cmp     ecx, [rbp+1D0h+var_17C]
0x18002362f  jle     short loc_180023634
0x180023631  mov     [rbp+1D0h+var_17C], ecx
0x180023634  mov     rax, [rbp+1D0h+P]
0x180023638  test    rax, rax
0x18002363b  jz      short loc_18002364F
0x18002363d  mov     rcx, cs:pUserHeap; HeapHandle
0x180023644  mov     r8, rax; P
0x180023647  xor     edx, edx; Flags
0x180023649  call    cs:__imp_RtlFreeHeap
0x18002364f  mov     r14d, [rsp+2D0h+var_268]
0x180023654  mov     rcx, [rbp+1D0h+Src]
0x180023658  mov     r11d, 2000h
0x18002365e  mov     edx, [rbp+1D0h+var_184]
0x180023661  movsxd  rax, ebx
0x180023664  lea     rdi, [rcx+rax*2]
0x180023668  add     r14d, edx
0x18002366b  cmp     [rbp+1D0h+var_210], 0
0x180023670  mov     r13, [rbp+1D0h+var_1D8]
0x180023674  jnz     loc_1800237E0
0x18002367a  mov     rbx, [rbp+1D0h+hrgn]
0x18002367e  test    rbx, rbx
0x180023681  jz      short loc_18002369E
0x180023683  mov     r8d, 5; mode
0x180023689  mov     rcx, r15; hdc
0x18002368c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180023690  jnz     loc_180023CC7
0x180023696  xor     edx, edx; hrgn
0x180023698  call    cs:__imp_ExtSelectClipRgn
0x18002369e  cmp     [rbp+1D0h+var_1E4], 0
0x1800236a2  jz      short loc_1800236B0
0x1800236a4  mov     edx, [rbp+1D0h+align]; align
0x1800236a7  mov     rcx, r15; hdc
0x1800236aa  call    cs:__imp_SetTextAlign
0x1800236b0  mov     rax, [rbp+1D0h+var_1B0]
0x1800236b4  test    rax, rax
0x1800236b7  jz      short loc_1800236C1
0x1800236b9  sub     edi, dword ptr [rbp+1D0h+var_1C8]
0x1800236bc  shr     edi, 1
0x1800236be  mov     [rax+10h], edi
0x1800236c1  mov     eax, r14d
0x1800236c4  mov     ecx, 1
0x1800236c9  sub     eax, [r13+4]
0x1800236cd  cmp     r14d, [r13+4]
0x1800236d1  cmovz   eax, ecx
0x1800236d4  mov     rcx, [rbp+1D0h+var_50]
0x1800236db  xor     rcx, rsp; StackCookie
0x1800236de  call    __security_check_cookie
0x1800236e3  add     rsp, 298h
0x1800236ea  pop     r15
0x1800236ec  pop     r14
0x1800236ee  pop     r13
0x1800236f0  pop     r12
0x1800236f2  pop     rdi
0x1800236f3  pop     rsi
0x1800236f4  pop     rbx
0x1800236f5  pop     rbp
0x1800236f6  retn
0x1800236f7  movzx   eax, r12w
0x1800236fb  and     eax, 0Ch
0x1800236fe  mov     [rbp+1D0h+var_22C], r10d
0x180023702  cmp     eax, 4
0x180023705  jz      loc_180023DB2
0x18002370b  cmp     eax, 8
0x18002370e  jz      loc_1800241BF
0x180023714  mov     r13, [rbp+1D0h+Src]
0x180023718  xor     esi, esi
0x18002371a  mov     [rbp+1D0h+P], rsi
0x18002371e  mov     [rsp+2D0h+var_254], esi
0x180023722  mov     esi, [rsp+2D0h+var_270]
0x180023726  mov     [rbp+1D0h+lpString], r13
0x18002372a  bt      r12d, 0Eh
0x18002372f  jb      loc_1800241D0
0x180023735  test    r12d, 48000h
0x18002373c  jz      loc_18002359C
0x180023742  mov     qword ptr [rbp+1D0h+sz.cx], 0
0x18002374a  test    ebx, ebx
0x18002374c  jz      loc_18002359C
0x180023752  mov     edi, [rbp+1D0h+var_180]
0x180023755  xor     r9d, r9d
0x180023758  mov     r14d, [rbp+1D0h+var_168]
0x18002375c  mov     eax, 26h ; '&'
0x180023761  mov     [rsp+2D0h+var_258], edi
0x180023765  mov     edx, ebx
0x180023767  mov     [rbp+1D0h+var_250], r14d
0x18002376b  mov     rcx, r13
0x18002376e  mov     [rbp+1D0h+String], ax
0x180023772  mov     r8d, ebx
0x180023775  mov     qword ptr [rbp+1D0h+var_238.cx], 0
0x18002377d  test    ebx, ebx
0x18002377f  jle     loc_180023550
0x180023785  nop     word ptr [rax+rax+00000000h]
0x180023790  movzx   eax, word ptr [rcx]
0x180023793  test    ax, ax
0x180023796  jz      loc_180023550
0x18002379c  test    r8d, r8d
0x18002379f  jle     loc_180023550
0x1800237a5  dec     edx
0x1800237a7  dec     r8d
0x1800237aa  add     rcx, 2
0x1800237ae  cmp     ax, 26h ; '&'
0x1800237b2  jz      loc_1800244B2
0x1800237b8  cmp     ax, 1Eh
0x1800237bc  jz      loc_1800244AA
0x1800237c2  cmp     ax, 1Fh
0x1800237c6  jz      loc_1800245EE
0x1800237cc  test    edx, edx
0x1800237ce  jg      short loc_180023790
0x1800237d0  jmp     loc_180023550
0x1800237d5  xor     eax, eax
0x1800237d7  mov     [rbp+1D0h+hrgn], rax
0x1800237db  jmp     loc_1800234B3
0x1800237e0  mov     ecx, [rbp+1D0h+var_18C]
0x1800237e3  mov     r8d, [rbp+1D0h+var_17C]
  ... truncated ...
```
