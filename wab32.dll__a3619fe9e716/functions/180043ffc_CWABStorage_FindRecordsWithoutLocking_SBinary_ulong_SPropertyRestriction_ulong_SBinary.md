# CWABStorage::_FindRecordsWithoutLocking(_SBinary *,ulong,_SPropertyRestriction *,ulong *,_SBinary * *)

- ea: `0x180043ffc`
- end: `0x180044fff`
- name: `?_FindRecordsWithoutLocking@CWABStorage@@AEAAJPEAU_SBinary@@KPEAU_SPropertyRestriction@@PEAKPEAPEAU2@@Z`
- size: `4099`
- prototype: `__int64 __fastcall(CWABStorage *__hidden this, struct _SBinary *, unsigned int, struct _SPropertyRestriction *, unsigned int *, struct _SBinary **)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800419c0`
- `0x180042810`
- `0x180043290`

## callees

- `0x1800045e4`
- `0x180030264`
- `0x180030ec0`
- `0x180031618`
- `0x180032200`
- `0x1800323b8`
- `0x180032704`
- `0x1800329b4`
- `0x180032f24`
- `0x180033040`
- `0x180033ae0`
- `0x180041a94`
- `0x180043ffc`
- `0x1800450b8`
- `0x180091e92`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180044664`
- `KERNEL32!SetFilePointer` at `0x1800446bb`
- `KERNEL32!SetFilePointer` at `0x180044664`
- `KERNEL32!SetFilePointer` at `0x1800446bb`
- `KERNEL32!lstrcmpiW` at `0x1800442fd`
- `KERNEL32!lstrcmpiW` at `0x180044321`
- `KERNEL32!lstrcmpiW` at `0x180044c46`
- `KERNEL32!lstrcmpiW` at `0x1800442fd`
- `KERNEL32!lstrcmpiW` at `0x180044321`
- `KERNEL32!lstrcmpiW` at `0x180044c46`
- `KERNEL32!LocalAlloc` at `0x180044169`
- `KERNEL32!LocalAlloc` at `0x18004420d`
- `KERNEL32!LocalAlloc` at `0x1800443ef`
- `KERNEL32!LocalAlloc` at `0x180044640`
- `KERNEL32!LocalAlloc` at `0x1800447bf`
- `KERNEL32!LocalAlloc` at `0x18004489e`
- `KERNEL32!LocalAlloc` at `0x180044a56`
- `KERNEL32!LocalAlloc` at `0x180044a8b`
- `KERNEL32!LocalAlloc` at `0x180044e9f`
- `KERNEL32!LocalAlloc` at `0x180044ef8`
- `KERNEL32!LocalAlloc` at `0x180044f1a`
- `KERNEL32!LocalAlloc` at `0x180044169`
- `KERNEL32!LocalAlloc` at `0x18004420d`
- `KERNEL32!LocalAlloc` at `0x1800443ef`
- `KERNEL32!LocalAlloc` at `0x180044640`
- `KERNEL32!LocalAlloc` at `0x1800447bf`
- `KERNEL32!LocalAlloc` at `0x18004489e`
- `KERNEL32!LocalAlloc` at `0x180044a56`
- `KERNEL32!LocalAlloc` at `0x180044a8b`
- `KERNEL32!LocalAlloc` at `0x180044e9f`
- `KERNEL32!LocalAlloc` at `0x180044ef8`
- `KERNEL32!LocalAlloc` at `0x180044f1a`
- `KERNEL32!LocalFree` at `0x180044893`
- `KERNEL32!LocalFree` at `0x180044e65`
- `KERNEL32!LocalFree` at `0x180044e78`
- `KERNEL32!LocalFree` at `0x180044f5f`
- `KERNEL32!LocalFree` at `0x180044f71`
- `KERNEL32!LocalFree` at `0x180044f83`
- `KERNEL32!LocalFree` at `0x180044f96`
- `KERNEL32!LocalFree` at `0x180044893`
- `KERNEL32!LocalFree` at `0x180044e65`
- `KERNEL32!LocalFree` at `0x180044e78`
- `KERNEL32!LocalFree` at `0x180044f5f`
- `KERNEL32!LocalFree` at `0x180044f71`
- `KERNEL32!LocalFree` at `0x180044f83`
- `KERNEL32!LocalFree` at `0x180044f96`
- `KERNEL32!CloseHandle` at `0x180044fc6`
- `KERNEL32!CloseHandle` at `0x180044fc6`
- `KERNEL32!GetFileSize` at `0x1800440ee`
- `KERNEL32!GetFileSize` at `0x1800440ee`
- `KERNEL32!ReadFile` at `0x1800446e7`
- `KERNEL32!ReadFile` at `0x1800447ec`
- `KERNEL32!ReadFile` at `0x1800448d2`
- `KERNEL32!ReadFile` at `0x1800446e7`
- `KERNEL32!ReadFile` at `0x1800447ec`
- `KERNEL32!ReadFile` at `0x1800448d2`
- `KERNEL32!CompareFileTime` at `0x180044c2b`
- `KERNEL32!CompareFileTime` at `0x180044c2b`

## pseudocode

```c
__int64 __fastcall CWABStorage::_FindRecordsWithoutLocking(
        CWABStorage *this,
        struct _SBinary *a2,
        char a3,
        struct _SPropertyRestriction *a4,
        unsigned int *a5,
        struct _SBinary **a6)
{
  void *v6; // r14
  unsigned int *v7; // r12
  struct _SPropertyRestriction *v8; // r15
  int v10; // ebx
  int v11; // esi
  unsigned int v12; // eax
  __int64 v13; // rcx
  ULONG relop; // r13d
  HANDLE v15; // rbx
  DWORD FileSize; // eax
  struct _tagMPSWabFileInfo *v17; // rcx
  __int64 v18; // rcx
  ULONG ulPropTag; // eax
  _DWORD *v20; // rdi
  unsigned int i; // ebx
  __int64 v22; // rsi
  __int64 v23; // r9
  int v24; // eax
  unsigned int v25; // ebx
  unsigned int v26; // edi
  unsigned int v27; // r14d
  int v28; // eax
  unsigned int v29; // r15d
  unsigned int v30; // eax
  unsigned int v31; // ecx
  ULONG v32; // r13d
  ULONG v33; // r13d
  ULONG v34; // r13d
  ULONG v35; // r13d
  __int64 v36; // r9
  unsigned int v37; // r8d
  __int64 k; // r8
  __int64 m; // r8
  __int64 v40; // r8
  unsigned int v41; // r15d
  __int64 n; // r8
  ULONG v43; // r13d
  ULONG v44; // r13d
  ULONG v45; // r13d
  __int64 nn; // r9
  struct _SBinary *v47; // rcx
  __int64 ii; // r8
  CWABStorage *v49; // rdi
  int v50; // r14d
  unsigned int v51; // r8d
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rdi
  unsigned int v55; // ebx
  __m128i v56; // xmm1
  __int64 v57; // rax
  int v58; // eax
  int v59; // ecx
  bool v60; // zf
  HLOCAL v61; // rax
  ULONG v62; // r8d
  int v63; // edx
  DWORD v64; // ebx
  __int64 j; // rcx
  HLOCAL v66; // rax
  unsigned __int8 *v67; // rdi
  int v68; // edi
  unsigned __int32 v69; // eax
  char *v70; // rbx
  unsigned int v71; // r8d
  int v72; // edx
  __int64 v73; // rcx
  size_t v74; // rdi
  char *v75; // r15
  size_t v76; // r8
  unsigned int *v77; // rcx
  SIZE_T v78; // rbx
  double v79; // xmm0_8
  SIZE_T v80; // rdx
  _BYTE *v81; // rax
  SIZE_T v82; // rdx
  unsigned int *v83; // rax
  bool v84; // zf
  __int64 v85; // rax
  float v86; // xmm0_4
  int v87; // r14d
  int b; // ecx
  LPSPropValue lpProp; // r9
  unsigned int ul; // r8d
  __int64 v91; // rdx
  _QWORD *int64; // rdx
  __int64 v93; // rax
  int v94; // eax
  LPSPropValue v95; // rcx
  int v96; // eax
  void **v97; // rcx
  LPBYTE lpb; // rax
  __int64 v99; // rbx
  unsigned int v100; // r8d
  struct _tagMPSWabFileInfo *v101; // rdx
  int FolderEIDs; // eax
  _DWORD *v103; // rbx
  unsigned int v104; // r10d
  __int64 jj; // r8
  __int64 kk; // rdx
  __int64 v107; // rcx
  int v108; // edx
  struct _SBinary *v109; // rax
  struct _SBinary **v110; // r15
  __int64 mm; // rsi
  int v113; // [rsp+38h] [rbp-D0h]
  HLOCAL v114; // [rsp+40h] [rbp-C8h]
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v118; // [rsp+5Ch] [rbp-ACh] BYREF
  unsigned int v119[2]; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE hFile; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v121; // [rsp+70h] [rbp-98h]
  DWORD v122; // [rsp+74h] [rbp-94h] BYREF
  unsigned int v123[4]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE *v124; // [rsp+88h] [rbp-80h] BYREF
  int v125; // [rsp+90h] [rbp-78h]
  unsigned __int32 v126; // [rsp+94h] [rbp-74h]
  int v127; // [rsp+98h] [rbp-70h]
  HLOCAL hMem; // [rsp+A0h] [rbp-68h]
  HLOCAL v129; // [rsp+A8h] [rbp-60h] BYREF
  HLOCAL v130; // [rsp+B0h] [rbp-58h] BYREF
  void *v131; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int *v132; // [rsp+C0h] [rbp-48h]
  struct _SBinary **v133; // [rsp+C8h] [rbp-40h]
  _OWORD v134[2]; // [rsp+D8h] [rbp-30h] BYREF
  __m128i Buffer; // [rsp+F8h] [rbp-10h] BYREF
  SIZE_T uBytes[2]; // [rsp+108h] [rbp+0h]
  WCHAR String2[40]; // [rsp+118h] [rbp+10h] BYREF

  v6 = 0;
  v7 = a5;
  v133 = a6;
  v130 = a2;
  v8 = a4;
  v132 = a5;
  hFile = 0;
  NumberOfBytesRead = 0;
  v118 = 0;
  v129 = 0;
  hMem = 0;
  v124 = 0;
  *(_OWORD *)v123 = 0;
  Buffer = 0;
  *(_OWORD *)uBytes = 0;
  if ( !a4 )
    return (unsigned int)-2147467259;
  v11 = a3 & 1;
  v125 = v11;
  if ( (a3 & 1) == 0 && !a4->lpProp )
    return (unsigned int)-2147024809;
  v12 = *a5;
  *a5 = 0;
  v13 = *((_QWORD *)this + 1);
  relop = a4->relop;
  v121 = v12;
  v10 = OpenWABFile(*(LPCWSTR *)(v13 + 16), (HWND)a2, &hFile);
  if ( v10 < 0 )
    goto LABEL_312;
  v15 = hFile;
  FileSize = GetFileSize(hFile, 0);
  v17 = (struct _tagMPSWabFileInfo *)*((_QWORD *)this + 1);
  v122 = FileSize;
  if ( !(unsigned int)ReloadMPSWabFileInfo(v17, v15) )
  {
LABEL_8:
    v10 = -2147467259;
    goto LABEL_312;
  }
  v18 = *((_QWORD *)this + 1);
  if ( (*(_DWORD *)(*(_QWORD *)(v18 + 24) + 128LL) & 0x110) != 0
    && (int)HrDoQuickWABIntegrityCheck((struct _tagMPSWabFileInfo *)v18, v15) < 0 )
  {
    v10 = HrDoDetailedWABIntegrityCheck(*((struct _tagMPSWabFileInfo **)this + 1), v15);
    if ( v10 < 0 )
      goto LABEL_312;
  }
  ulPropTag = v8->ulPropTag;
  v127 = 0;
  v114 = 0;
  if ( ulPropTag == 268370178 )
  {
    v20 = LocalAlloc(0x40u, 4u);
    if ( !v20 )
      goto LABEL_14;
    v10 = 0;
    *v20 = v8->lpProp->Value.l;
    *a5 = 1;
    goto LABEL_295;
  }
  for ( i = 1; ; ++i )
  {
    if ( i >= 6 )
    {
      if ( (ulPropTag & 0x1000) != 0 && !v11 )
      {
        v10 = -2147024809;
        goto LABEL_312;
      }
      v49 = this;
      v114 = LocalAlloc(0x40u, 4LL * *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 120LL));
      v6 = v114;
      if ( !v114 )
        goto LABEL_14;
      if ( SetFilePointer(hFile, 0, 0, 0) == -1 )
      {
        v10 = -2147024809;
LABEL_309:
        LocalFree(v6);
LABEL_310:
        if ( v127 )
          TagWABFileError(*(struct _tagMPSWabFileHeader **)(*((_QWORD *)this + 1) + 24LL), hFile);
        goto LABEL_312;
      }
      v50 = 0;
      v22 = 0;
      v51 = 0;
      v52 = 0;
LABEL_115:
      v53 = *((_QWORD *)v49 + 1);
      v119[0] = v52;
      if ( (unsigned int)v52 >= *(_DWORD *)(*(_QWORD *)(v53 + 24) + 36LL) )
      {
LABEL_260:
        v6 = v114;
        goto LABEL_261;
      }
      v54 = (unsigned int)v52;
      v55 = *(_DWORD *)(*(_QWORD *)(v53 + 40) + 8 * v52 + 4);
      if ( SetFilePointer(hFile, v55 - v51, 0, 1u) == -1 || !ReadFile(hFile, &Buffer, 0x20u, &NumberOfBytesRead, 0) )
      {
        v10 = -2147467259;
        goto LABEL_304;
      }
      if ( NumberOfBytesRead != 32 )
        goto LABEL_258;
      v56 = Buffer;
      v118 = v55 + 32;
      v57 = *((_QWORD *)this + 1);
      v134[0] = Buffer;
      v134[1] = *(_OWORD *)uBytes;
      if ( !(unsigned int)bIsValidRecord(
                            v134,
                            *(unsigned int *)(*(_QWORD *)(v57 + 24) + 20LL),
                            v55,
                            v122,
                            1,
                            *(_DWORD *)(*(_QWORD *)(v57 + 40) + 8 * v54)) )
      {
        v127 = 1;
        goto LABEL_254;
      }
      if ( v8->ulPropTag == 268304387 && v8->relop == 4 )
      {
        v58 = _mm_cvtsi128_si32(_mm_srli_si128(v56, 4));
        if ( v58 == 2 )
        {
          v59 = 8;
        }
        else
        {
          v59 = 6;
          if ( v58 == 3 )
            v59 = 4;
        }
        v60 = v8->lpProp->Value.l == v59;
        goto LABEL_128;
      }
      LocalFreeAndNull(&v129);
      v61 = LocalAlloc(0x40u, HIDWORD(uBytes[0]));
      v129 = v61;
      if ( !v61 )
        goto LABEL_257;
      if ( !ReadFile(hFile, v61, HIDWORD(uBytes[0]), &NumberOfBytesRead, 0) )
      {
LABEL_256:
        v10 = -2147221226;
        goto LABEL_304;
      }
      if ( NumberOfBytesRead != HIDWORD(uBytes[0]) )
        goto LABEL_258;
      if ( v125 && relop - 4 > 1 || (v62 = v8->ulPropTag, (_WORD)v62 == 72) && relop - 4 > 1 )
      {
        v10 = -2147024809;
        goto LABEL_304;
      }
      v63 = 0;
      v64 = NumberOfBytesRead + v118;
      v118 += NumberOfBytesRead;
      for ( j = 0; (unsigned int)j < Buffer.m128i_i32[3]; j = (unsigned int)(j + 1) )
      {
        if ( *((_DWORD *)v129 + j) == v62 )
        {
          v63 = 1;
          break;
        }
      }
      if ( v125 )
      {
        if ( relop != 4 || !v63 )
        {
          if ( relop != 5 )
            goto LABEL_254;
          v60 = v63 == 0;
LABEL_128:
          if ( !v60 )
            goto LABEL_254;
        }
        *((_DWORD *)v114 + v22) = Buffer.m128i_i32[2];
        v22 = (unsigned int)(v22 + 1);
        goto LABEL_254;
      }
      if ( !v63 )
        goto LABEL_254;
      if ( hMem )
        LocalFree(hMem);
      v66 = LocalAlloc(0x40u, HIDWORD(uBytes[1]));
      hMem = v66;
      v67 = (unsigned __int8 *)v66;
      v131 = v66;
      if ( !v66 )
        goto LABEL_257;
      if ( !ReadFile(hFile, v66, HIDWORD(uBytes[1]), &NumberOfBytesRead, 0) )
        goto LABEL_256;
      if ( NumberOfBytesRead != HIDWORD(uBytes[1])
        || !(unsigned int)SecurityCheckPropArrayBuffer(v67, NumberOfBytesRead, Buffer.m128i_u32[3]) )
      {
LABEL_258:
        v10 = -2147221221;
        goto LABEL_304;
      }
      v68 = 0;
      v118 = NumberOfBytesRead + v64;
      v69 = 0;
      v70 = (char *)hMem;
      v113 = 0;
      while ( 1 )
      {
        v126 = v69;
        if ( v69 >= Buffer.m128i_i32[3] )
        {
LABEL_248:
          if ( relop == 5 && !v68 )
          {
            *((_DWORD *)v114 + v22) = Buffer.m128i_i32[2];
            v22 = (unsigned int)(v22 + 1);
          }
          if ( (_DWORD)v22 == v121 && v121 )
            goto LABEL_260;
          LocalFreeAndNull(&v131);
          LocalFreeAndNull(&v129);
          hMem = v131;
LABEL_254:
          v49 = this;
          v52 = v119[0] + 1;
          v51 = v118;
          goto LABEL_115;
        }
        v71 = *(_DWORD *)v70;
        v72 = *(_DWORD *)v70 & 0x1000;
        v123[0] = v71;
        v73 = (-(__int64)(v72 != 0) & 4) + 4;
        v74 = *(unsigned int *)&v70[v73];
        v75 = &v70[(-(__int64)(v72 != 0) & 4) + 8];
        if ( v71 != a4->ulPropTag || v72 )
        {
LABEL_157:
          v70 = &v75[2 * v74];
          v68 = v113;
          goto LABEL_247;
        }
        if ( (unsigned __int16)v71 <= 0xBu )
          break;
        switch ( (unsigned __int16)v71 )
        {
          case 0x14u:
            goto LABEL_165;
          case 0x1Fu:
            goto LABEL_185;
          case 0x40u:
            goto LABEL_165;
          case 0x48u:
LABEL_185:
            v82 = *(unsigned int *)&v70[v73];
            v78 = v82;
            v83 = (unsigned int *)LocalAlloc(0x40u, v82);
            *(_QWORD *)&v123[2] = v83;
            if ( !v83 )
              goto LABEL_257;
            v76 = v74;
            v77 = v83;
            goto LABEL_167;
        }
        if ( (unsigned __int16)v71 != 258 )
          goto LABEL_157;
        v80 = *(unsigned int *)&v70[v73];
        v78 = v80;
        v81 = LocalAlloc(0x40u, v80);
        v124 = v81;
        if ( !v81 )
          goto LABEL_257;
        memcpy_0(v81, v75, v74);
        v123[2] = v74;
LABEL_168:
        v70 = &v75[2 * v78];
        v8 = a4;
        if ( LOWORD(v123[0]) > 0xBu )
        {
          if ( LOWORD(v123[0]) != 20 )
          {
            switch ( LOWORD(v123[0]) )
            {
              case 0x1Fu:
                v94 = lstrcmpiW(*(LPCWSTR *)&v123[2], a4->lpProp->Value.lpszW);
                goto LABEL_223;
              case 0x40u:
                v94 = CompareFileTime((const FILETIME *)&v123[2], (const FILETIME *)&a4->lpProp->Value);
LABEL_223:
                v50 = v94;
                goto LABEL_193;
              case 0x48u:
                int64 = (_QWORD *)a4->lpProp->Value.cur.int64;
                v93 = **(_QWORD **)&v123[2] - *int64;
                if ( **(_QWORD **)&v123[2] == *int64 )
                  v93 = *(_QWORD *)(*(_QWORD *)&v123[2] + 8LL) - int64[1];
                v50 = v93 == 0;
                break;
              case 0x102u:
                lpProp = a4->lpProp;
                ul = lpProp->Value.ul;
                if ( (unsigned int)v74 < ul )
                  ul = v74;
                v91 = 0;
                if ( ul )
                {
                  while ( v124[v91] == lpProp->Value.bin.lpb[v91] )
                  {
                    v91 = (unsigned int)(v91 + 1);
                    if ( (unsigned int)v91 >= ul )
                      goto LABEL_217;
                  }
LABEL_218:
                  v87 = (unsigned __int8)v124[v91];
                  b = lpProp->Value.bin.lpb[v91];
LABEL_205:
                  v50 = v87 - b;
                  goto LABEL_193;
                }
LABEL_217:
                v50 = 0;
                if ( (_DWORD)v91 != ul )
                  goto LABEL_218;
                break;
            }
            goto LABEL_193;
          }
          LODWORD(v85) = v123[3];
        }
        else
        {
          switch ( LOWORD(v123[0]) )
          {
            case 0xBu:
              v87 = LOWORD(v123[2]);
              b = a4->lpProp->Value.b;
              goto LABEL_205;
            case 2u:
              v87 = SLOWORD(v123[2]);
              b = a4->lpProp->Value.i;
              goto LABEL_205;
            case 3u:
              v50 = v74 - a4->lpProp->Value.l;
              goto LABEL_193;
            case 4u:
              v86 = *(float *)&v123[2] - a4->lpProp->Value.flt;
              if ( v86 < 0.0 )
                goto LABEL_177;
              v84 = v86 == 0.0;
LABEL_188:
              if ( v84 )
              {
                v50 = 0;
                goto LABEL_193;
              }
LABEL_228:
              v50 = 1;
              goto LABEL_193;
            case 5u:
              goto LABEL_176;
          }
          if ( LOWORD(v123[0]) != 6 )
          {
            if ( LOWORD(v123[0]) != 7 )
              goto LABEL_193;
LABEL_176:
            v79 = *(double *)&v123[2] - a4->lpProp->Value.dbl;
            if ( v79 < 0.0 )
              goto LABEL_177;
            v84 = v79 == 0.0;
            goto LABEL_188;
          }
          v85 = *(__int64 *)&v123[2] >> 32;
        }
        v95 = a4->lpProp;
        v96 = v85 - v95->Value.cur.Hi;
        if ( v96 < 0 )
        {
LABEL_177:
          v50 = -1;
          goto LABEL_193;
        }
        if ( v96 > 0 )
          goto LABEL_228;
        if ( (unsigned int)v74 < v95->Value.l )
          goto LABEL_177;
        v50 = v74 != v95->Value.l;
LABEL_193:
        switch ( relop )
        {
          case 0u:
            if ( v50 >= 0 )
              goto LABEL_239;
            goto LABEL_230;
          case 1u:
            if ( v50 > 0 )
              goto LABEL_239;
            goto LABEL_230;
          case 2u:
            if ( v50 <= 0 )
              goto LABEL_239;
            goto LABEL_230;
          case 3u:
            if ( v50 < 0 )
              goto LABEL_239;
            goto LABEL_230;
          case 4u:
            if ( v50 )
              goto LABEL_239;
LABEL_230:
            *((_DWORD *)v114 + v22) = Buffer.m128i_i32[2];
            v22 = (unsigned int)(v22 + 1);
            goto LABEL_231;
        }
        if ( relop != 5 || v50 )
        {
LABEL_239:
          v68 = v113;
          goto LABEL_240;
        }
LABEL_231:
        v68 = 1;
        v113 = 1;
LABEL_240:
        if ( LOWORD(v123[0]) == 31 || LOWORD(v123[0]) == 72 )
        {
          v97 = (void **)&v123[2];
        }
        else
        {
          if ( LOWORD(v123[0]) != 258 )
            goto LABEL_246;
          v97 = (void **)&v124;
        }
        LocalFreeAndNull(v97);
LABEL_246:
        if ( v68 )
          goto LABEL_248;
LABEL_247:
        v8 = a4;
        v69 = v126 + 1;
      }
      if ( (unsigned __int16)v71 != 11
        && (unsigned __int16)v71 != 2
        && (unsigned __int16)v71 != 3
        && (unsigned __int16)v71 != 4
        && (unsigned int)(unsigned __int16)v71 - 6 > 1 )
      {
        goto LABEL_157;
      }
LABEL_165:
      v76 = 2;
      v77 = &v123[2];
      v78 = v74;
      if ( (unsigned int)v74 < 2 )
        v76 = v74;
LABEL_167:
      memcpy_0(v77, v75, v76);
      LODWORD(v74) = v123[2];
      goto LABEL_168;
    }
    if ( *((_DWORD *)&rgIndexArray + i) == ulPropTag )
      break;
  }
  _mm_lfence();
  v22 = *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 16LL * i + 36);
  if ( !(_DWORD)v22 )
    goto LABEL_21;
  if ( !v125 )
  {
    StringCchCopyW(String2, 0x21u, v8->lpProp->Value.lpszW);
    if ( !LoadIndex(*((struct _tagMPSWabFileInfo **)this + 1), i, hFile) )
      goto LABEL_8;
    v24 = BinSearchStr(
            *(struct _tagMPSWabIndexEntryDataString **)(*((_QWORD *)this + 1) + 32LL),
            String2,
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 16LL * i + 36),
            &v118);
    v25 = v118;
    v26 = v118;
    v119[0] = v24;
    if ( !v24 )
    {
      v27 = v118;
      v29 = v118;
      if ( relop < 2 )
      {
        *a5 = v118;
      }
      else
      {
        switch ( relop )
        {
          case 2u:
          case 3u:
            *a5 = v22 - v118;
            break;
          case 4u:
            *a5 = 0;
            break;
          case 5u:
            *a5 = v22;
            break;
        }
      }
LABEL_62:
      v30 = *a5;
      if ( !*a5 )
      {
LABEL_21:
        v10 = 0;
        goto LABEL_312;
      }
      v31 = v121;
      if ( v30 > v121 && v121 )
      {
        *a5 = v121;
        v30 = v31;
      }
      v20 = LocalAlloc(0x40u, 4LL * v30);
      if ( !v20 )
        goto LABEL_14;
      if ( v119[0] )
      {
        if ( relop && (v32 = relop - 1) != 0 )
        {
          v33 = v32 - 1;
          if ( v33 )
          {
            v34 = v33 - 1;
            if ( v34 )
            {
              v35 = v34 - 1;
              if ( v35 )
              {
                if ( v35 == 1 )
                {
                  v36 = 0;
                  if ( (unsigned int)v22 > v121 && v121 )
                    LODWORD(v22) = v121;
                  v37 = 0;
                  do
                  {
                    if ( v37 < v27 || v37 > v25 )
                    {
                      v20[v36] = *(_DWORD *)(68LL * v37 + *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 64);
                      v36 = (unsigned int)(v36 + 1);
                    }
                    ++v37;
                  }
                  while ( v37 < (unsigned int)v22 );
                }
              }
              else
              {
                for ( k = 0; (unsigned int)k < *a5; k = (unsigned int)(k + 1) )
                  v20[k] = *(_DWORD *)(68LL * (v27 + (unsigned int)k) + *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 64);
              }
            }
            else
            {
              for ( m = 0; (unsigned int)m < *a5; m = (unsigned int)(m + 1) )
                v20[m] = *(_DWORD *)(68LL * (v27 + (unsigned int)m) + *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 64);
            }
          }
          else
          {
            v40 = 0;
            if ( *a5 )
            {
              v41 = v29 + 1;
              do
              {
                v20[v40] = *(_DWORD *)(68LL * (v41 + (unsigned int)v40) + *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 64);
                v40 = (unsigned int)(v40 + 1);
              }
              while ( (unsigned int)v40 < *a5 );
            }
          }
        }
        else
        {
          for ( n = 0; (unsigned int)n < *a5; n = (unsigned int)(n + 1) )
            v20[n] = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 68LL * (unsigned int)n + 64);
        }
        goto LABEL_103;
      }
      if ( relop )
      {
        v43 = relop - 1;
        if ( v43 )
        {
          v44 = v43 - 1;
          if ( !v44 || (v45 = v44 - 1) == 0 )
          {
            for ( ii = 0; (unsigned int)ii < *a5; ii = (unsigned int)(ii + 1) )
              v20[ii] = *(_DWORD *)(68LL * (v27 + (unsigned int)ii) + *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 64);
LABEL_103:
            v47 = (struct _SBinary *)v130;
            v10 = 0;
            if ( v130 )
            {
              LODWORD(v22) = *a5;
              v6 = v20;
              *a5 = 0;
              v114 = v20;
LABEL_263:
              lpb = v47->lpb;
              if ( v47->cb )
              {
                if ( lpb )
                {
                  v130 = 0;
                  v119[0] = 0;
                  FolderEIDs = GetFolderEIDs(
                                 hFile,
                                 *((struct _tagMPSWabFileInfo **)this + 1),
                                 v47,
                                 v119,
                                 (unsigned int **)&v130);
                  v103 = v130;
                  if ( FolderEIDs >= 0 )
                  {
                    v104 = v119[0];
                    if ( v119[0] && v130 )
                    {
                      for ( jj = 0; (unsigned int)jj < (unsigned int)v22; jj = (unsigned int)(jj + 1) )
                      {
                        for ( kk = 0; (unsigned int)kk < v104; kk = (unsigned int)(kk + 1) )
                        {
                          if ( *((_DWORD *)v6 + jj) == v103[kk] )
                            goto LABEL_280;
                        }
                        *((_DWORD *)v6 + jj) = -1;
LABEL_280:
                        ;
                      }
                    }
                    else
                    {
                      LODWORD(v22) = 0;
                      if ( v6 )
                      {
                        LocalFree(v6);
                        v114 = 0;
                      }
                    }
                  }
                  if ( v103 )
                    LocalFree(v103);
                }
              }
              else if ( !lpb )
              {
                v99 = 0;
                if ( (_DWORD)v22 )
                {
                  do
                  {
                    v100 = v20[v99];
                    v101 = (struct _tagMPSWabFileInfo *)*((_QWORD *)this + 1);
                    v122 = 0;
                    if ( (unsigned int)bIsFolderMember(hFile, v101, v100, &v122) )
                      v20[v99] = -1;
                    v99 = (unsigned int)(v99 + 1);
                  }
                  while ( (unsigned int)v99 < (unsigned int)v22 );
                  v7 = v132;
                }
              }
LABEL_286:
              v20 = 0;
              *v7 = 0;
              if ( v114 && (_DWORD)v22 )
              {
                v20 = LocalAlloc(0x40u, 4LL * (unsigned int)v22);
                if ( !v20 )
                {
LABEL_257:
                  v10 = -2147024882;
                  goto LABEL_304;
                }
                v107 = 0;
                do
                {
                  v108 = *((_DWORD *)v114 + v107);
                  if ( v108 != -1 )
                    v20[(*v7)++] = v108;
                  v107 = (unsigned int)(v107 + 1);
                }
                while ( (unsigned int)v107 < (unsigned int)v22 );
              }
              v10 = 0;
            }
            if ( !v20 )
            {
LABEL_304:
              if ( hMem )
                LocalFree(hMem);
              if ( v129 )
                LocalFree(v129);
              v6 = v114;
              if ( !v114 )
                goto LABEL_310;
              goto LABEL_309;
            }
LABEL_295:
            if ( *v7 )
            {
              v109 = (struct _SBinary *)LocalAlloc(0x40u, 16LL * *v7);
              v110 = v133;
              *v133 = v109;
              if ( v109 )
              {
                for ( mm = 0; (unsigned int)mm < *v7; mm = (unsigned int)(mm + 1) )
                {
                  (*v110)[(unsigned int)mm].lpb = (LPBYTE)LocalAlloc(0x40u, 4u);
                  if ( (*v110)[(unsigned int)mm].lpb )
                  {
                    (*v110)[(unsigned int)mm].cb = 4;
                    *(_DWORD *)(*v110)[(unsigned int)mm].lpb = v20[mm];
                  }
                }
              }
              else
              {
                *v7 = 0;
              }
            }
            LocalFree(v20);
            goto LABEL_304;
          }
          if ( v45 != 2 )
            goto LABEL_103;
        }
      }
      for ( nn = 0; (unsigned int)nn < *a5; nn = (unsigned int)(nn + 1) )
        v20[nn] = *(_DWORD *)(68LL * (unsigned int)nn + *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 64);
      goto LABEL_103;
    }
    do
      v27 = v25--;
    while ( v25 != -1 && !lstrcmpiW((LPCWSTR)(*(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 68LL * v25), String2) );
    do
      v25 = v26++;
    while ( v26 != (_DWORD)v22 && !lstrcmpiW((LPCWSTR)(*(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 68LL * v26), String2) );
    switch ( relop )
    {
      case 0u:
        *a5 = v27;
        goto LABEL_52;
      case 1u:
        v28 = v25 + 1;
        break;
      case 2u:
        v28 = v22 - v25 - 1;
        break;
      case 3u:
        v28 = v22 - v27;
        break;
      case 4u:
        v28 = v25 - v27 + 1;
        break;
      case 5u:
        v28 = v22 + v27 - v25 - 1;
        break;
      default:
LABEL_52:
        v29 = v25;
        goto LABEL_62;
    }
    *a5 = v28;
    goto LABEL_52;
  }
  if ( v8->relop == 5 )
  {
    LODWORD(v22) = 0;
    v114 = 0;
    goto LABEL_261;
  }
  if ( v8->relop != 4 )
  {
    LODWORD(v22) = 0;
    goto LABEL_261;
  }
  v114 = LocalAlloc(0x40u, 4 * v22);
  v6 = v114;
  if ( v114 )
  {
    if ( !LoadIndex(*((struct _tagMPSWabFileInfo **)this + 1), i, hFile) )
    {
      v10 = -2147467259;
      goto LABEL_309;
    }
    v23 = 0;
    do
    {
      *((_DWORD *)v114 + v23) = *(_DWORD *)(68LL * (unsigned int)v23 + *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 64);
      v23 = (unsigned int)(v23 + 1);
    }
    while ( (unsigned int)v23 < (unsigned int)v22 );
LABEL_261:
    v47 = (struct _SBinary *)v130;
    if ( v130 )
    {
      v20 = v6;
      goto LABEL_263;
    }
    goto LABEL_286;
  }
LABEL_14:
  v10 = -2147024882;
LABEL_312:
  if ( hFile )
    CloseHandle(hFile);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180043ffc  mov     rax, rsp
0x180043fff  mov     [rax+18h], rbx
0x180044003  push    rbp
0x180044004  push    rsi
0x180044005  push    rdi
0x180044006  push    r12
0x180044008  push    r13
0x18004400a  push    r14
0x18004400c  push    r15
0x18004400e  lea     rbp, [rax-0C8h]
0x180044015  sub     rsp, 190h
0x18004401c  movaps  xmmword ptr [rax-48h], xmm6
0x180044020  movaps  xmmword ptr [rax-58h], xmm7
0x180044024  mov     rax, cs:__security_cookie
0x18004402b  xor     rax, rsp
0x18004402e  mov     [rbp+0C0h+var_60], rax
0x180044032  mov     rax, [rbp+0C0h+arg_28]
0x180044039  xor     r14d, r14d
0x18004403c  mov     r12, [rbp+0C0h+arg_20]
0x180044043  xorps   xmm1, xmm1
0x180044046  mov     [rbp+0C0h+var_100], rax
0x18004404a  xorps   xmm0, xmm0
0x18004404d  xor     eax, eax
0x18004404f  mov     [rsp+1C0h+var_180], r9
0x180044054  mov     [rbp+0C0h+var_118], rdx
0x180044058  mov     r15, r9
0x18004405b  mov     qword ptr [rsp+1C0h+var_178], rcx
0x180044060  mov     esi, r8d
0x180044063  mov     [rbp+0C0h+var_108], r12
0x180044067  mov     rdi, rcx
0x18004406a  mov     [rsp+1C0h+hFile], r14
0x18004406f  mov     [rsp+1C0h+NumberOfBytesRead], r14d
0x180044074  mov     [rsp+1C0h+var_16C], r14d
0x180044079  mov     [rbp+0C0h+var_120], r14
0x18004407d  mov     [rbp+0C0h+hMem], r14
0x180044081  mov     [rbp+0C0h+var_140], rax
0x180044085  movups  xmmword ptr [rsp+1C0h+var_158+8], xmm0
0x18004408a  movups  [rbp+0C0h+Buffer], xmm1
0x18004408e  movups  xmmword ptr [rbp+0C0h+uBytes], xmm1
0x180044092  test    r9, r9
0x180044095  jnz     short loc_1800440A1
0x180044097  mov     ebx, 80004005h
0x18004409c  jmp     loc_180044FCC
0x1800440a1  and     esi, 1
0x1800440a4  mov     [rbp+0C0h+var_138], esi
0x1800440a7  jnz     short loc_1800440B9
0x1800440a9  cmp     [r9+8], r14
0x1800440ad  jnz     short loc_1800440B9
0x1800440af  mov     ebx, 80070057h
0x1800440b4  jmp     loc_180044FCC
0x1800440b9  mov     eax, [r12]
0x1800440bd  lea     r8, [rsp+1C0h+hFile]; void **
0x1800440c2  mov     [r12], r14d
0x1800440c6  mov     rcx, [rcx+8]
0x1800440ca  mov     r13d, [r9]
0x1800440cd  mov     [rsp+1C0h+var_158], eax
0x1800440d1  mov     rcx, [rcx+10h]; lpFileName
0x1800440d5  call    ?OpenWABFile@@YAJPEAGPEAUHWND__@@PEAPEAX@Z; OpenWABFile(ushort *,HWND__ *,void * *)
0x1800440da  mov     ebx, eax
0x1800440dc  test    eax, eax
0x1800440de  js      loc_180044FB9
0x1800440e4  mov     rbx, [rsp+1C0h+hFile]
0x1800440e9  xor     edx, edx; lpFileSizeHigh
0x1800440eb  mov     rcx, rbx; hFile
0x1800440ee  call    cs:__imp_GetFileSize
0x1800440f4  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x1800440f8  mov     rdx, rbx; void *
0x1800440fb  mov     [rsp+1C0h+var_158+4], eax
0x1800440ff  call    ?ReloadMPSWabFileInfo@@YAHPEAU_tagMPSWabFileInfo@@PEAX@Z; ReloadMPSWabFileInfo(_tagMPSWabFileInfo *,void *)
0x180044104  test    eax, eax
0x180044106  jnz     short loc_180044112
0x180044108  mov     ebx, 80004005h
0x18004410d  jmp     loc_180044FB9
0x180044112  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180044116  mov     rax, [rcx+18h]
0x18004411a  test    dword ptr [rax+80h], 110h
0x180044124  jz      short loc_180044148
0x180044126  mov     rdx, rbx; void *
0x180044129  call    ?HrDoQuickWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoQuickWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x18004412e  test    eax, eax
0x180044130  jns     short loc_180044148
0x180044132  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180044136  mov     rdx, rbx; void *
0x180044139  call    ?HrDoDetailedWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoDetailedWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x18004413e  mov     ebx, eax
0x180044140  test    eax, eax
0x180044142  js      loc_180044FB9
0x180044148  mov     eax, [r15+4]
0x18004414c  mov     [rbp+0C0h+var_130], r14d
0x180044150  mov     [rsp+1C0h+var_188], r14
0x180044155  cmp     eax, 0FFF0102h
0x18004415a  jnz     short loc_180044199
0x18004415c  mov     r13d, 4
0x180044162  mov     edx, r13d; uBytes
0x180044165  lea     ecx, [r13+3Ch]; uFlags
0x180044169  call    cs:__imp_LocalAlloc
0x18004416f  mov     rdi, rax
0x180044172  test    rax, rax
0x180044175  jnz     short loc_180044181
0x180044177  mov     ebx, 8007000Eh
0x18004417c  jmp     loc_180044FB9
0x180044181  mov     rax, [r15+8]
0x180044185  xor     ebx, ebx
0x180044187  mov     ecx, [rax+8]
0x18004418a  mov     [rdi], ecx
0x18004418c  mov     dword ptr [r12], 1
0x180044194  jmp     loc_180044EE1
0x180044199  mov     ebx, 1
0x18004419e  mov     r8d, 40h ; '@'
0x1800441a4  cmp     ebx, 6
0x1800441a7  jnb     loc_180044615
0x1800441ad  mov     edi, ebx
0x1800441af  lea     rcx, ?rgIndexArray@@3QBKB; ulong const near * const rgIndexArray
0x1800441b6  cmp     [rcx+rdi*4], eax
0x1800441b9  jz      short loc_1800441BF
0x1800441bb  inc     ebx
0x1800441bd  jmp     short loc_18004419E
0x1800441bf  lfence
0x1800441c2  mov     r10, qword ptr [rsp+1C0h+var_178]
0x1800441c7  add     rdi, rdi
0x1800441ca  mov     rax, [r10+8]
0x1800441ce  mov     rcx, [rax+18h]
0x1800441d2  mov     esi, [rcx+rdi*8+24h]
0x1800441d6  test    esi, esi
0x1800441d8  jnz     short loc_1800441E1
0x1800441da  xor     ebx, ebx
0x1800441dc  jmp     loc_180044FB9
0x1800441e1  cmp     [rbp+0C0h+var_138], r14d
0x1800441e5  jz      loc_18004427D
0x1800441eb  cmp     dword ptr [r15], 5
0x1800441ef  jnz     short loc_1800441FD
0x1800441f1  xor     esi, esi
0x1800441f3  mov     [rsp+1C0h+var_188], r14
0x1800441f8  jmp     loc_180044D6F
0x1800441fd  cmp     dword ptr [r15], 4
0x180044201  jnz     short loc_180044276
0x180044203  mov     rdx, rsi
0x180044206  mov     ecx, r8d; uFlags
0x180044209  shl     rdx, 2; uBytes
0x18004420d  call    cs:__imp_LocalAlloc
0x180044213  mov     [rsp+1C0h+var_188], rax
0x180044218  mov     r14, rax
0x18004421b  test    rax, rax
0x18004421e  jz      loc_180044177
0x180044224  mov     rdi, qword ptr [rsp+1C0h+var_178]
0x180044229  mov     edx, ebx; unsigned int
0x18004422b  mov     r8, [rsp+1C0h+hFile]; void *
0x180044230  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180044234  call    ?LoadIndex@@YAHPEAU_tagMPSWabFileInfo@@KPEAX@Z; LoadIndex(_tagMPSWabFileInfo *,ulong,void *)
0x180044239  test    eax, eax
0x18004423b  jnz     short loc_180044247
0x18004423d  mov     ebx, 80004005h
0x180044242  jmp     loc_180044F93
0x180044247  xor     r9d, r9d
0x18004424a  test    esi, esi
0x18004424c  jz      loc_180044D6F
0x180044252  mov     rax, [rdi+8]
0x180044256  mov     r8d, r9d
0x180044259  imul    rdx, r8, 44h ; 'D'
0x18004425d  mov     rcx, [rax+20h]
0x180044261  mov     eax, [rdx+rcx+40h]
0x180044265  mov     [r14+r9*4], eax
0x180044269  inc     r9d
0x18004426c  cmp     r9d, esi
0x18004426f  jb      short loc_180044252
0x180044271  jmp     loc_180044D6F
0x180044276  xor     esi, esi
0x180044278  jmp     loc_180044D6F
0x18004427d  mov     r8, [r15+8]
0x180044281  lea     rcx, [rbp+0C0h+String2]; unsigned __int16 *
0x180044285  mov     edx, 21h ; '!'; unsigned __int64
0x18004428a  mov     r8, [r8+8]; unsigned __int16 *
0x18004428e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044293  mov     r15, qword ptr [rsp+1C0h+var_178]
0x180044298  mov     edx, ebx; unsigned int
0x18004429a  mov     r8, [rsp+1C0h+hFile]; void *
0x18004429f  mov     rcx, [r15+8]; struct _tagMPSWabFileInfo *
0x1800442a3  call    ?LoadIndex@@YAHPEAU_tagMPSWabFileInfo@@KPEAX@Z; LoadIndex(_tagMPSWabFileInfo *,ulong,void *)
0x1800442a8  test    eax, eax
0x1800442aa  jz      loc_180044108
0x1800442b0  mov     rcx, [r15+8]
0x1800442b4  lea     r9, [rsp+1C0h+var_16C]; unsigned int *
0x1800442b9  lea     rdx, [rbp+0C0h+String2]; unsigned __int16 *
0x1800442bd  mov     r8, [rcx+18h]
0x1800442c1  mov     rcx, [rcx+20h]; struct _tagMPSWabIndexEntryDataString *
0x1800442c5  mov     r8d, [r8+rdi*8+24h]; unsigned int
0x1800442ca  call    ?BinSearchStr@@YAHPEAU_tagMPSWabIndexEntryDataString@@PEAGKPEAK@Z; BinSearchStr(_tagMPSWabIndexEntryDataString *,ushort *,ulong,ulong *)
0x1800442cf  mov     ebx, [rsp+1C0h+var_16C]
0x1800442d3  mov     edi, ebx
0x1800442d5  mov     [rsp+1C0h+var_168], eax
0x1800442d9  test    eax, eax
0x1800442db  jz      loc_180044381
0x1800442e1  mov     r14d, ebx
0x1800442e4  dec     ebx
0x1800442e6  cmp     ebx, 0FFFFFFFFh
0x1800442e9  jz      short loc_180044307
0x1800442eb  mov     rax, [r15+8]
0x1800442ef  lea     rdx, [rbp+0C0h+String2]; lpString2
0x1800442f3  mov     ecx, ebx
0x1800442f5  imul    rcx, 44h ; 'D'
0x1800442f9  add     rcx, [rax+20h]; lpString1
0x1800442fd  call    cs:__imp_lstrcmpiW
0x180044303  test    eax, eax
0x180044305  jz      short loc_1800442E1
0x180044307  mov     ebx, edi
0x180044309  inc     edi
0x18004430b  cmp     edi, esi
0x18004430d  jz      short loc_18004432B
0x18004430f  mov     eax, edi
0x180044311  lea     rdx, [rbp+0C0h+String2]; lpString2
0x180044315  imul    rcx, rax, 44h ; 'D'
0x180044319  mov     rax, [r15+8]
0x18004431d  add     rcx, [rax+20h]; lpString1
0x180044321  call    cs:__imp_lstrcmpiW
0x180044327  test    eax, eax
0x180044329  jz      short loc_180044307
0x18004432b  mov     eax, r13d
0x18004432e  test    r13d, r13d
0x180044331  jz      short loc_180044378
0x180044333  sub     eax, 1
0x180044336  jz      short loc_180044373
0x180044338  sub     eax, 1
0x18004433b  jz      short loc_180044367
0x18004433d  sub     eax, 1
0x180044340  jz      short loc_180044360
0x180044342  sub     eax, 1
0x180044345  jz      short loc_180044357
0x180044347  cmp     eax, 1
0x18004434a  jnz     short loc_18004437C
0x18004434c  mov     eax, r14d
0x18004434f  sub     eax, ebx
0x180044351  dec     eax
0x180044353  add     eax, esi
0x180044355  jmp     short loc_18004436D
0x180044357  mov     eax, ebx
0x180044359  sub     eax, r14d
0x18004435c  inc     eax
0x18004435e  jmp     short loc_18004436D
0x180044360  mov     eax, esi
0x180044362  sub     eax, r14d
0x180044365  jmp     short loc_18004436D
0x180044367  mov     eax, esi
0x180044369  sub     eax, ebx
0x18004436b  dec     eax
0x18004436d  mov     [r12], eax
0x180044371  jmp     short loc_18004437C
0x180044373  lea     eax, [rbx+1]
0x180044376  jmp     short loc_18004436D
0x180044378  mov     [r12], r14d
0x18004437c  mov     r15d, ebx
0x18004437f  jmp     short loc_1800443C6
0x180044381  mov     r14d, ebx
0x180044384  mov     r15d, ebx
0x180044387  mov     eax, r13d
0x18004438a  test    r13d, r13d
0x18004438d  jz      short loc_1800443C2
0x18004438f  sub     eax, 1
0x180044392  jz      short loc_1800443C2
0x180044394  sub     eax, 1
0x180044397  jz      short loc_1800443B8
0x180044399  sub     eax, 1
0x18004439c  jz      short loc_1800443B8
0x18004439e  sub     eax, 1
0x1800443a1  jz      short loc_1800443AE
0x1800443a3  cmp     eax, 1
0x1800443a6  jnz     short loc_1800443C6
0x1800443a8  mov     [r12], esi
0x1800443ac  jmp     short loc_1800443C6
0x1800443ae  mov     dword ptr [r12], 0
0x1800443b6  jmp     short loc_1800443C6
0x1800443b8  mov     eax, esi
0x1800443ba  sub     eax, ebx
0x1800443bc  mov     [r12], eax
0x1800443c0  jmp     short loc_1800443C6
0x1800443c2  mov     [r12], ebx
0x1800443c6  mov     eax, [r12]
0x1800443ca  test    eax, eax
0x1800443cc  jz      loc_1800441DA
0x1800443d2  mov     ecx, [rsp+1C0h+var_158]
0x1800443d6  cmp     eax, ecx
0x1800443d8  jbe     short loc_1800443E4
0x1800443da  test    ecx, ecx
0x1800443dc  jz      short loc_1800443E4
0x1800443de  mov     [r12], ecx
0x1800443e2  mov     eax, ecx
0x1800443e4  mov     edx, eax
0x1800443e6  mov     ecx, 40h ; '@'; uFlags
0x1800443eb  shl     rdx, 2; uBytes
0x1800443ef  call    cs:__imp_LocalAlloc
0x1800443f5  mov     rdi, rax
0x1800443f8  test    rax, rax
0x1800443fb  jz      loc_180044177
0x180044401  cmp     [rsp+1C0h+var_168], 0
0x180044406  jz      loc_18004456F
0x18004440c  test    r13d, r13d
0x18004440f  jz      loc_18004453F
0x180044415  sub     r13d, 1
0x180044419  jz      loc_18004453F
0x18004441f  sub     r13d, 1
0x180044423  jz      loc_180044504
  ... truncated ...
```
