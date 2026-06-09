# PrepareUnicodePathEx

- ea: `0x18000efbc`
- end: `0x18000fd74`
- name: `PrepareUnicodePathEx`
- size: `3512`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000e9e4`
- `0x18000eb44`

## callees

- `0x1800015cc`
- `0x1800015e3`
- `0x18000e8a8`
- `0x18000eca8`
- `0x18000ed90`
- `0x18000efbc`
- `0x18000fd7c`
- `0x18000ff10`

## import_xrefs

- `msvcrt!wcsncmp` at `0x18000f0f8`
- `msvcrt!wcsncmp` at `0x18000fa12`
- `msvcrt!wcsncmp` at `0x18000f0f8`
- `msvcrt!wcsncmp` at `0x18000fa12`
- `ntdll!RtlFreeHeap` at `0x18000f318`
- `ntdll!RtlFreeHeap` at `0x18000f5b4`
- `ntdll!RtlFreeHeap` at `0x18000f318`
- `ntdll!RtlFreeHeap` at `0x18000f5b4`
- `ntdll!RtlAllocateHeap` at `0x18000f1e9`
- `ntdll!RtlAllocateHeap` at `0x18000f45d`
- `ntdll!RtlAllocateHeap` at `0x18000f8e7`
- `ntdll!RtlAllocateHeap` at `0x18000fb9a`
- `ntdll!RtlAllocateHeap` at `0x18000f1e9`
- `ntdll!RtlAllocateHeap` at `0x18000f45d`
- `ntdll!RtlAllocateHeap` at `0x18000f8e7`
- `ntdll!RtlAllocateHeap` at `0x18000fb9a`
- `KERNEL32!GetProcessHeap` at `0x18000f98d`
- `KERNEL32!GetProcessHeap` at `0x18000f9f0`
- `KERNEL32!GetProcessHeap` at `0x18000fc3d`
- `KERNEL32!GetProcessHeap` at `0x18000fc9a`
- `KERNEL32!GetProcessHeap` at `0x18000fcce`
- `KERNEL32!GetProcessHeap` at `0x18000fd05`
- `KERNEL32!GetProcessHeap` at `0x18000f98d`
- `KERNEL32!GetProcessHeap` at `0x18000f9f0`
- `KERNEL32!GetProcessHeap` at `0x18000fc3d`
- `KERNEL32!GetProcessHeap` at `0x18000fc9a`
- `KERNEL32!GetProcessHeap` at `0x18000fcce`
- `KERNEL32!GetProcessHeap` at `0x18000fd05`
- `KERNEL32!HeapFree` at `0x18000f9a1`
- `KERNEL32!HeapFree` at `0x18000fc51`
- `KERNEL32!HeapFree` at `0x18000fcae`
- `KERNEL32!HeapFree` at `0x18000fce2`
- `KERNEL32!HeapFree` at `0x18000fd19`
- `KERNEL32!HeapFree` at `0x18000f9a1`
- `KERNEL32!HeapFree` at `0x18000fc51`
- `KERNEL32!HeapFree` at `0x18000fcae`
- `KERNEL32!HeapFree` at `0x18000fce2`
- `KERNEL32!HeapFree` at `0x18000fd19`
- `KERNEL32!GetLastError` at `0x18000f088`
- `KERNEL32!GetLastError` at `0x18000f0a8`
- `KERNEL32!GetLastError` at `0x18000f367`
- `KERNEL32!GetLastError` at `0x18000f386`
- `KERNEL32!GetLastError` at `0x18000f5ea`
- `KERNEL32!GetLastError` at `0x18000f606`
- `KERNEL32!GetLastError` at `0x18000f633`
- `KERNEL32!GetLastError` at `0x18000f653`
- `KERNEL32!GetLastError` at `0x18000f088`
- `KERNEL32!GetLastError` at `0x18000f0a8`
- `KERNEL32!GetLastError` at `0x18000f367`
- `KERNEL32!GetLastError` at `0x18000f386`
- `KERNEL32!GetLastError` at `0x18000f5ea`
- `KERNEL32!GetLastError` at `0x18000f606`
- `KERNEL32!GetLastError` at `0x18000f633`
- `KERNEL32!GetLastError` at `0x18000f653`
- `KERNEL32!SetLastError` at `0x18000fd28`
- `KERNEL32!SetLastError` at `0x18000fd3e`
- `KERNEL32!SetLastError` at `0x18000fd28`
- `KERNEL32!SetLastError` at `0x18000fd3e`

## pseudocode

```c
char *__fastcall PrepareUnicodePathEx(const wchar_t *a1, wchar_t **a2)
{
  char *Heap; // rdi
  WCHAR *v3; // rax
  wchar_t *v4; // r15
  signed int v5; // ebx
  WCHAR *v6; // r12
  signed int LastError; // eax
  bool v8; // sf
  signed int v9; // eax
  __int64 v10; // r13
  unsigned __int64 v11; // rax
  int v12; // eax
  char *v13; // rsi
  int v14; // r15d
  __int64 v15; // rbx
  __int64 v16; // r14
  __int16 v17; // dx
  bool v18; // zf
  __int64 v19; // rcx
  size_t v20; // r12
  HRESULT v21; // eax
  unsigned __int16 v22; // bx
  HRESULT v23; // eax
  size_t v24; // rcx
  STRSAFE_LPWSTR v25; // rdx
  size_t v26; // r8
  signed __int64 v27; // rsi
  wchar_t v28; // ax
  STRSAFE_LPWSTR v29; // rax
  signed int v30; // eax
  signed int v31; // eax
  bool v32; // sf
  signed int v33; // eax
  wchar_t *v34; // r12
  int v35; // r14d
  __int64 v36; // rbx
  __int64 v37; // rsi
  __int64 v38; // rcx
  size_t v39; // r15
  HRESULT v40; // eax
  unsigned __int16 v41; // bx
  HRESULT v42; // eax
  size_t v43; // rcx
  STRSAFE_LPWSTR v44; // rdx
  size_t v45; // r8
  signed __int64 v46; // r12
  wchar_t v47; // ax
  STRSAFE_LPWSTR v48; // rax
  signed int v49; // eax
  signed int v50; // eax
  bool v51; // sf
  signed int v52; // eax
  signed int v53; // eax
  bool v54; // sf
  signed int v55; // eax
  wchar_t *v56; // r14
  const wchar_t *v57; // rcx
  wchar_t *v58; // rax
  const wchar_t *v59; // rsi
  int v60; // r12d
  _WORD *v61; // rsi
  unsigned __int64 v62; // rax
  unsigned __int64 v63; // rax
  BOOL v64; // ecx
  wchar_t *v65; // rax
  unsigned __int64 v66; // r15
  wchar_t *v67; // rax
  unsigned __int64 v68; // rax
  unsigned __int64 v69; // r12
  _WORD *i; // rcx
  __int16 v71; // dx
  _WORD *v72; // rax
  void *v73; // r13
  HANDLE ProcessHeap; // rax
  HANDLE v75; // rax
  void *v76; // r8
  __int16 v77; // cx
  __int64 v78; // r12
  int v79; // r13d
  unsigned __int64 v80; // rax
  _WORD *v81; // rsi
  unsigned __int64 v82; // rax
  BOOL v83; // ecx
  wchar_t *v84; // rax
  unsigned __int64 v85; // r15
  wchar_t *v86; // rax
  unsigned __int64 v87; // rax
  unsigned __int64 v88; // r12
  _WORD *j; // rcx
  __int16 v90; // dx
  _WORD *v91; // rax
  void *v92; // r12
  HANDLE v93; // rax
  _WORD *v94; // r15
  HANDLE v95; // rax
  void *v96; // rsi
  HANDLE v97; // rax
  DWORD v99; // [rsp+30h] [rbp-D0h]
  DWORD v100; // [rsp+30h] [rbp-D0h]
  DWORD v101; // [rsp+30h] [rbp-D0h]
  STRSAFE_LPWSTR pszDest; // [rsp+40h] [rbp-C0h] BYREF
  size_t cchDest; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t **v104; // [rsp+50h] [rbp-B0h]
  STRSAFE_LPCWSTR v105; // [rsp+58h] [rbp-A8h]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h]
  wchar_t String2[4]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t pszSrc[8]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v109[16]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v110[12]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v111[24]; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t v112[12]; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t v113[20]; // [rsp+100h] [rbp+0h] BYREF

  v104 = a2;
  v105 = a1;
  Heap = 0;
  wcscpy(String2, L"\\\\?");
  wcscpy(v109, L"\\\\?\\GLOBALROOT");
  wcscpy(pszSrc, L"\\\\?\\UNC");
  wcscpy(v112, L"\\\\?\\Volume{");
  if ( !a1 || !*a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v3 = FormFullPathName(a1);
  lpMem = v3;
  v4 = v3;
  if ( v3 )
  {
    v5 = 0;
    v6 = v3;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError > 0 )
      v8 = 1;
    if ( !v8 )
    {
LABEL_222:
      LOWORD(v5) = 16389;
      goto LABEL_223;
    }
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = 0;
    if ( v5 < 0 )
      goto LABEL_223;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( v4[v11] );
  if ( v11 >= 0x104 )
  {
    if ( !wcsncmp(v4, String2, 3u) || !wcsnicmp_0(v4, pszSrc, 7u) )
      goto LABEL_58;
    LODWORD(pszDest) = 0;
    v12 = ParseUncPathEx(v4);
    LOWORD(v5) = v12;
    if ( v12 < 0 )
    {
LABEL_223:
      Heap = 0;
      goto LABEL_224;
    }
    cchDest = 0;
    v18 = (_DWORD)pszDest == 1;
    pszDest = 0;
    if ( v18 )
    {
      v13 = (char *)(v4 + 1);
      v14 = 0;
      if ( !v13 )
      {
        NtCurrentTeb()->LastErrorValue = 87;
        goto LABEL_53;
      }
      v15 = -1;
      do
        ++v15;
      while ( pszSrc[v15] );
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)&v13[2 * v16] );
      if ( (_DWORD)v15 )
      {
        v17 = *(_WORD *)v13;
        if ( pszSrc[(unsigned int)(v15 - 1)] == 92 )
        {
          v18 = v17 == 92;
          if ( v17 == 92 )
          {
            LODWORD(v16) = v16 - 1;
            v18 = 1;
          }
          if ( !v18 )
            v13 = (char *)v6;
          v13 += 2;
        }
        else if ( v17 != 92 )
        {
          v14 = 1;
        }
      }
      v19 = (unsigned int)(v15 + v14 + v16 + 1);
      v20 = (unsigned int)v19;
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v19);
      if ( !Heap )
      {
        Heap = 0;
        NtCurrentTeb()->LastErrorValue = 8;
LABEL_53:
        v31 = GetLastError();
        v32 = v31 < 0;
        if ( v31 > 0 )
          v32 = 1;
        if ( v32 )
        {
          v33 = GetLastError();
          v5 = v33;
          if ( v33 > 0 )
            v5 = (unsigned __int16)v33 | 0x80070000;
        }
        else
        {
          v5 = -2147467259;
        }
LABEL_58:
        if ( v5 < 0 )
          goto LABEL_220;
        goto LABEL_59;
      }
      v21 = StringCchCopyNExW((STRSAFE_LPWSTR)Heap, v20, pszSrc, (unsigned int)v15, &pszDest, &cchDest, v99);
      v22 = v21;
      if ( v21 < 0 )
        goto LABEL_49;
      if ( v14 )
      {
        v23 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v100);
        v22 = v23;
        if ( v23 < 0 )
          goto LABEL_49;
      }
      v24 = cchDest;
      if ( cchDest - 1 > 0x7FFFFFFE )
      {
        v30 = -2147024809;
        v22 = 87;
        if ( cchDest )
          goto LABEL_51;
      }
      else
      {
        if ( (unsigned int)v16 > 0x7FFFFFFEuLL )
        {
          v22 = 87;
LABEL_51:
          *pszDest = 0;
          goto LABEL_49;
        }
        v25 = pszDest;
        if ( cchDest )
        {
          v26 = (unsigned int)v16 - cchDest;
          v27 = v13 - (char *)pszDest;
          do
          {
            if ( !(v26 + v24) )
              break;
            v28 = *(STRSAFE_LPWSTR)((char *)v25 + v27);
            if ( !v28 )
              break;
            *v25++ = v28;
            --v24;
          }
          while ( v24 );
        }
        v29 = v25 - 1;
        if ( v24 )
          v29 = v25;
        *v29 = 0;
        v30 = v24 == 0 ? 0x8007007A : 0;
      }
      v22 = v30;
      if ( v30 < 0 )
      {
LABEL_49:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        Heap = 0;
        NtCurrentTeb()->LastErrorValue = v22;
        goto LABEL_53;
      }
LABEL_90:
      NtCurrentTeb()->LastErrorValue = 0;
      goto LABEL_60;
    }
    v34 = v4;
    v35 = 0;
    if ( !v4 )
    {
      NtCurrentTeb()->LastErrorValue = 87;
      goto LABEL_95;
    }
    v36 = -1;
    do
      ++v36;
    while ( String2[v36] );
    v37 = -1;
    do
      ++v37;
    while ( v4[v37] );
    if ( (_DWORD)v36 )
    {
      if ( String2[(unsigned int)(v36 - 1)] == 92 )
      {
        if ( *v4 == 92 )
        {
          v34 = v4 + 1;
          LODWORD(v37) = v37 - 1;
        }
      }
      else if ( *v4 != 92 )
      {
        v35 = 1;
      }
    }
    v38 = (unsigned int)(v36 + v35 + v37 + 1);
    v39 = (unsigned int)v38;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v38);
    if ( !Heap )
    {
      Heap = 0;
      NtCurrentTeb()->LastErrorValue = 8;
LABEL_95:
      v50 = GetLastError();
      v51 = v50 < 0;
      if ( v50 > 0 )
        v51 = 1;
      if ( !v51 )
      {
        LOWORD(v5) = 16389;
        goto LABEL_220;
      }
      v52 = GetLastError();
      v5 = v52;
      if ( v52 > 0 )
        v5 = (unsigned __int16)v52 | 0x80070000;
      goto LABEL_58;
    }
    v40 = StringCchCopyNExW((STRSAFE_LPWSTR)Heap, v39, String2, (unsigned int)v36, &pszDest, &cchDest, v99);
    v41 = v40;
    if ( v40 < 0
      || v35 && (v42 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v101), v41 = v42, v42 < 0) )
    {
LABEL_93:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = 0;
      NtCurrentTeb()->LastErrorValue = v41;
      goto LABEL_95;
    }
    v43 = cchDest;
    if ( cchDest - 1 > 0x7FFFFFFE )
    {
      v49 = -2147024809;
      v41 = 87;
      if ( cchDest )
        goto LABEL_92;
    }
    else
    {
      if ( (unsigned int)v37 > 0x7FFFFFFEuLL )
      {
        v41 = 87;
LABEL_92:
        *pszDest = 0;
        goto LABEL_93;
      }
      v44 = pszDest;
      if ( cchDest )
      {
        v45 = (unsigned int)v37 - cchDest;
        v46 = (char *)v34 - (char *)pszDest;
        do
        {
          if ( !(v45 + v43) )
            break;
          v47 = *(STRSAFE_LPWSTR)((char *)v44 + v46);
          if ( !v47 )
            break;
          *v44++ = v47;
          --v43;
        }
        while ( v43 );
      }
      v48 = v44 - 1;
      if ( v43 )
        v48 = v44;
      *v48 = 0;
      v49 = v43 == 0 ? 0x8007007A : 0;
    }
    v41 = v49;
    if ( v49 >= 0 )
      goto LABEL_90;
    goto LABEL_93;
  }
LABEL_59:
  Heap = (char *)StrDupe(v105);
  if ( Heap )
  {
LABEL_60:
    v5 = 0;
    goto LABEL_107;
  }
  v53 = GetLastError();
  v54 = v53 < 0;
  if ( v53 > 0 )
    v54 = 1;
  if ( !v54 )
    goto LABEL_222;
  v55 = GetLastError();
  v5 = v55;
  if ( v55 > 0 )
    v5 = (unsigned __int16)v55 | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_223;
LABEL_107:
  if ( !v104 )
    goto LABEL_224;
  v56 = 0;
  if ( !wcsnicmp_0((const wchar_t *)Heap, v109, 0xEu) )
  {
    v56 = (wchar_t *)(Heap + 28);
    wcscpy(v111, L"\\Device\\HarddiskVolume");
    wcscpy(v113, L"\\Device\\Harddisk");
    if ( !wcsnicmp_0((const wchar_t *)Heap + 14, v111, 0x16u) )
    {
      v57 = (const wchar_t *)(Heap + 74);
LABEL_111:
      v56 = wcschr_0(v57, 0x5Cu);
      goto LABEL_219;
    }
    if ( !wcsnicmp_0((const wchar_t *)Heap + 14, v113, 0x10u) )
    {
      wcscpy(v110, L"Partition");
      v58 = wcschr_0((const wchar_t *)Heap + 31, 0x5Cu);
      if ( v58 )
      {
        v59 = v58 + 1;
        if ( !wcsnicmp_0(v58 + 1, v110, 9u) )
        {
          v57 = v59;
          goto LABEL_111;
        }
      }
      goto LABEL_169;
    }
    goto LABEL_219;
  }
  if ( !wcsnicmp_0((const wchar_t *)Heap, v112, 0xBu) )
  {
    v56 = (wchar_t *)(Heap + 96);
    goto LABEL_219;
  }
  if ( !wcsnicmp_0((const wchar_t *)Heap, pszSrc, 7u) )
  {
    v60 = 0;
    v61 = 0;
    if ( !Heap )
    {
      v5 = -2147024809;
      goto LABEL_219;
    }
    v62 = -1;
    do
      ++v62;
    while ( *(_WORD *)&Heap[2 * v62] );
    if ( v62 < 2 || wcsnicmp_0((const wchar_t *)Heap, L"\\\\", 2u) )
    {
      v5 = 0;
      v60 = 0;
      v61 = 0;
    }
    else
    {
      v63 = -1;
      do
        ++v63;
      while ( *(_WORD *)&Heap[2 * v63] );
      v64 = v63 >= 8 && wcsnicmp_0((const wchar_t *)Heap, L"\\\\?\\UNC\\", 8u) == 0;
      v65 = wcschr_0((const wchar_t *)&Heap[v64 ? 16LL : 4LL], 0x5Cu);
      if ( v65 )
      {
        v66 = -1;
        do
          ++v66;
        while ( *(_WORD *)&Heap[2 * v66] );
        v67 = wcschr_0(v65 + 1, 0x5Cu);
        if ( v67 )
          v66 = ((char *)v67 - Heap) >> 1;
        v5 = -2147024882;
        v68 = -1;
        do
          ++v68;
        while ( *(_WORD *)&Heap[2 * v68] );
        if ( v66 > v68 )
        {
          v5 = -2147024809;
        }
        else
        {
          v69 = v66 + 1;
          v61 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (v66 + 1));
          if ( v61 )
          {
            if ( v66 > 0x7FFFFFFE )
            {
              v5 = -2147024809;
              if ( v66 != -1 )
                *v61 = 0;
            }
            else
            {
              for ( i = v61; v69 != 1; ++i )
              {
                v71 = *(_WORD *)((char *)i + Heap - (char *)v61);
                if ( !v71 )
                  break;
                *i = v71;
                --v69;
              }
              v72 = i - 1;
              if ( v69 )
                v72 = i;
              v5 = v69 == 0 ? 0x8007007A : 0;
              *v72 = 0;
            }
          }
          v73 = v61;
          if ( v5 < 0 )
          {
            v60 = 0;
            v61 = 0;
            if ( v73 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v73);
            }
            v10 = -1;
          }
          else
          {
            v10 = -1;
            v60 = 1;
          }
        }
      }
      else
      {
        v5 = -2147024883;
      }
    }
    if ( v5 >= 0 )
    {
      if ( v60 == 1 )
      {
        do
          ++v10;
        while ( v61[v10] );
        v56 = (wchar_t *)&Heap[2 * v10];
      }
      else
      {
        v56 = 0;
      }
    }
    if ( !v61 )
      goto LABEL_219;
    v75 = GetProcessHeap();
    v76 = v61;
LABEL_218:
    HeapFree(v75, 0, v76);
    goto LABEL_219;
  }
  if ( wcsncmp((const wchar_t *)Heap, String2, 3u) )
  {
    if ( ((unsigned __int16)(*(_WORD *)Heap - 97) <= 0x19u || (unsigned __int16)(*(_WORD *)Heap - 65) <= 0x19u)
      && *((_WORD *)Heap + 1) == 58
      && *((_WORD *)Heap + 2) == 92 )
    {
      v56 = (wchar_t *)(Heap + 4);
      goto LABEL_219;
    }
    v78 = -1;
    v79 = 0;
    v80 = -1;
    v81 = 0;
    do
      ++v80;
    while ( *(_WORD *)&Heap[2 * v80] );
    if ( v80 < 2 || wcsnicmp_0((const wchar_t *)Heap, L"\\\\", 2u) )
    {
      v94 = 0;
      v5 = 0;
    }
    else
    {
      v82 = -1;
      do
        ++v82;
      while ( *(_WORD *)&Heap[2 * v82] );
      v83 = v82 >= 8 && wcsnicmp_0((const wchar_t *)Heap, L"\\\\?\\UNC\\", 8u) == 0;
      v84 = wcschr_0((const wchar_t *)&Heap[v83 ? 16LL : 4LL], 0x5Cu);
      if ( v84 )
      {
        v85 = -1;
        do
          ++v85;
        while ( *(_WORD *)&Heap[2 * v85] );
        v86 = wcschr_0(v84 + 1, 0x5Cu);
        if ( v86 )
          v85 = ((char *)v86 - Heap) >> 1;
        v5 = -2147024882;
        v87 = -1;
        do
          ++v87;
        while ( *(_WORD *)&Heap[2 * v87] );
        if ( v85 > v87 )
        {
          v5 = -2147024809;
        }
        else
        {
          v88 = v85 + 1;
          v81 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (v85 + 1));
          if ( v81 )
          {
            if ( v85 > 0x7FFFFFFE )
            {
              v5 = -2147024809;
              if ( v85 != -1 )
                *v81 = 0;
            }
            else
            {
              for ( j = v81; v88 != 1; ++j )
              {
                v90 = *(_WORD *)((char *)j + Heap - (char *)v81);
                if ( !v90 )
                  break;
                *j = v90;
                --v88;
              }
              v91 = j - 1;
              if ( v88 )
                v91 = j;
              v5 = v88 == 0 ? 0x8007007A : 0;
              *v91 = 0;
            }
          }
          v92 = v81;
          if ( v5 < 0 )
          {
            v81 = 0;
            if ( v92 )
            {
              v93 = GetProcessHeap();
              HeapFree(v93, 0, v92);
            }
            v78 = -1;
          }
          else
          {
            v78 = -1;
            v79 = 1;
          }
        }
      }
      else
      {
        v5 = -2147024883;
      }
      v94 = v81;
      if ( v5 < 0 )
        goto LABEL_216;
      if ( v79 == 1 )
      {
        do
          ++v78;
        while ( v81[v78] );
        v56 = (wchar_t *)&Heap[2 * v78];
        goto LABEL_216;
      }
    }
    v56 = 0;
LABEL_216:
    if ( !v94 )
      goto LABEL_219;
    v75 = GetProcessHeap();
    v76 = v94;
    goto LABEL_218;
  }
  v77 = *((_WORD *)Heap + 4);
  if ( (unsigned __int16)(v77 - 97) > 0x19u && (unsigned __int16)(v77 - 65) > 0x19u
    || *((_WORD *)Heap + 5) != 58
    || (v56 = (wchar_t *)(Heap + 12), *((_WORD *)Heap + 6) != 92) )
  {
LABEL_169:
    v56 = 0;
  }
LABEL_219:
  *v104 = v56;
  if ( v5 < 0 )
  {
LABEL_220:
    if ( Heap )
    {
      v95 = GetProcessHeap();
      HeapFree(v95, 0, Heap);
    }
    goto LABEL_223;
  }
LABEL_224:
  v96 = lpMem;
  if ( lpMem )
  {
    v97 = GetProcessHeap();
    HeapFree(v97, 0, v96);
  }
  SetLastError((unsigned __int16)v5);
  return Heap;
}

```

## disassembly

```asm
0x18000efbc  mov     [rsp-8+arg_10], rbx
0x18000efc1  push    rbp
0x18000efc2  push    rsi
0x18000efc3  push    rdi
0x18000efc4  push    r12
0x18000efc6  push    r13
0x18000efc8  push    r14
0x18000efca  push    r15
0x18000efcc  lea     rbp, [rsp-30h]
0x18000efd1  sub     rsp, 130h
0x18000efd8  mov     rax, cs:__security_cookie
0x18000efdf  xor     rax, rsp
0x18000efe2  mov     [rbp+60h+var_38], rax
0x18000efe6  mov     eax, dword ptr cs:aGlobalroot+18h; "OT"
0x18000efec  movups  xmm0, xmmword ptr cs:aGlobalroot; "\\\\?\\GLOBALROOT"
0x18000eff3  mov     [rbp+60h+var_C8], eax
0x18000eff6  movzx   eax, word ptr cs:aGlobalroot+1Ch; ""
0x18000effd  movups  xmm1, xmmword ptr cs:aUnc; "\\\\?\\UNC"
0x18000f004  mov     [rsp+160h+var_110], rdx
0x18000f009  xor     edx, edx
0x18000f00b  mov     [rbp+60h+var_C4], ax
0x18000f00f  mov     rax, 3F005C005Ch
0x18000f019  mov     [rsp+160h+var_108], rcx
0x18000f01e  mov     edi, edx
0x18000f020  mov     qword ptr [rsp+160h+String2], rax
0x18000f025  movups  xmmword ptr [rbp+60h+var_E0], xmm0
0x18000f029  movsd   xmm0, qword ptr cs:aGlobalroot+10h; "ALROOT"
0x18000f031  movsd   [rbp+60h+var_D0], xmm0
0x18000f036  movups  xmm0, xmmword ptr cs:aVolume; "\\\\?\\Volume{"
0x18000f03d  movdqu  xmmword ptr [rsp+160h+pszSrc], xmm1
0x18000f043  movups  xmmword ptr [rbp+60h+var_78], xmm0
0x18000f047  movsd   xmm0, qword ptr cs:aVolume+10h; "me{"
0x18000f04f  movsd   [rbp+60h+var_68], xmm0
0x18000f054  test    rcx, rcx
0x18000f057  jz      loc_18000FD39
0x18000f05d  cmp     dx, [rcx]
0x18000f060  jz      loc_18000FD39
0x18000f066  call    FormFullPathName
0x18000f06b  xor     r9d, r9d
0x18000f06e  mov     [rsp+160h+lpMem], rax
0x18000f073  mov     r15, rax
0x18000f076  mov     esi, 80070000h
0x18000f07b  test    rax, rax
0x18000f07e  jz      short loc_18000F088
0x18000f080  mov     ebx, r9d
0x18000f083  mov     r12, rax
0x18000f086  jmp     short loc_18000F0CD
0x18000f088  call    cs:__imp_GetLastError
0x18000f08f  nop     dword ptr [rax+rax+00h]
0x18000f094  xor     r9d, r9d
0x18000f097  test    eax, eax
0x18000f099  jle     short loc_18000F0A2
0x18000f09b  movzx   eax, ax
0x18000f09e  or      eax, esi
0x18000f0a0  test    eax, eax
0x18000f0a2  jns     loc_18000FCF3
0x18000f0a8  call    cs:__imp_GetLastError
0x18000f0af  nop     dword ptr [rax+rax+00h]
0x18000f0b4  xor     r9d, r9d
0x18000f0b7  mov     ebx, eax
0x18000f0b9  test    eax, eax
0x18000f0bb  jle     short loc_18000F0C2
0x18000f0bd  movzx   ebx, ax
0x18000f0c0  or      ebx, esi
0x18000f0c2  mov     r12, r9
0x18000f0c5  test    ebx, ebx
0x18000f0c7  js      loc_18000FCF8
0x18000f0cd  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000f0d1  mov     rax, r13
0x18000f0d4  inc     rax
0x18000f0d7  cmp     [r15+rax*2], r9w
0x18000f0dc  jnz     short loc_18000F0D4
0x18000f0de  cmp     rax, 104h
0x18000f0e4  jb      loc_18000F3BD
0x18000f0ea  mov     r8d, 3; MaxCount
0x18000f0f0  lea     rdx, [rsp+160h+String2]; String2
0x18000f0f5  mov     rcx, r15; String1
0x18000f0f8  call    cs:__imp_wcsncmp
0x18000f0ff  nop     dword ptr [rax+rax+00h]
0x18000f104  xor     r9d, r9d
0x18000f107  test    eax, eax
0x18000f109  jz      loc_18000F3A4
0x18000f10f  lea     r8d, [r9+7]; MaxCount
0x18000f113  mov     rcx, r15; String1
0x18000f116  lea     rdx, [rsp+160h+pszSrc]; String2
0x18000f11b  call    _wcsnicmp_0
0x18000f120  xor     r9d, r9d
0x18000f123  test    eax, eax
0x18000f125  jz      loc_18000F3A4
0x18000f12b  xor     r8d, r8d
0x18000f12e  mov     dword ptr [rsp+160h+pszDest], r9d
0x18000f133  lea     rdx, [rsp+160h+pszDest]
0x18000f138  mov     rcx, r15; String1
0x18000f13b  call    ParseUncPathEx
0x18000f140  xor     r9d, r9d
0x18000f143  mov     ebx, eax
0x18000f145  test    eax, eax
0x18000f147  js      loc_18000FCF8
0x18000f14d  lea     r8d, [r9+1]
0x18000f151  mov     [rsp+160h+cchDest], r9
0x18000f156  cmp     dword ptr [rsp+160h+pszDest], r8d
0x18000f15b  mov     [rsp+160h+pszDest], r9
0x18000f160  jnz     loc_18000F3E5
0x18000f166  lea     rsi, [r15+2]
0x18000f16a  mov     r15d, r9d
0x18000f16d  test    rsi, rsi
0x18000f170  jz      loc_18000F357
0x18000f176  lea     rax, [rsp+160h+pszSrc]
0x18000f17b  mov     rbx, r13
0x18000f17e  inc     rbx
0x18000f181  cmp     [rax+rbx*2], r9w
0x18000f186  jnz     short loc_18000F17E
0x18000f188  mov     r14, r13
0x18000f18b  inc     r14
0x18000f18e  cmp     [rsi+r14*2], r9w
0x18000f193  jnz     short loc_18000F18B
0x18000f195  test    ebx, ebx
0x18000f197  jz      short loc_18000F1C7
0x18000f199  movzx   edx, word ptr [rsi]
0x18000f19c  lea     ecx, [rbx-1]
0x18000f19f  mov     eax, 5Ch ; '\'
0x18000f1a4  cmp     ax, [rsp+rcx*2+160h+pszSrc]
0x18000f1a9  jnz     short loc_18000F1C0
0x18000f1ab  cmp     ax, dx
0x18000f1ae  jnz     short loc_18000F1B6
0x18000f1b0  dec     r14d
0x18000f1b3  cmp     ax, dx
0x18000f1b6  cmovnz  rsi, r12
0x18000f1ba  add     rsi, 2
0x18000f1be  jmp     short loc_18000F1C7
0x18000f1c0  cmp     ax, dx
0x18000f1c3  cmovnz  r15d, r8d
0x18000f1c7  lea     ecx, [r14+1]
0x18000f1cb  mov     edx, 8; Flags
0x18000f1d0  add     ecx, r15d
0x18000f1d3  add     ecx, ebx
0x18000f1d5  mov     r12d, ecx
0x18000f1d8  lea     r8, [rcx+rcx]; Size
0x18000f1dc  mov     rcx, gs:60h
0x18000f1e5  mov     rcx, [rcx+30h]; HeapHandle
0x18000f1e9  call    cs:__imp_RtlAllocateHeap
0x18000f1f0  nop     dword ptr [rax+rax+00h]
0x18000f1f5  xor     ecx, ecx
0x18000f1f7  mov     rdi, rax
0x18000f1fa  test    rax, rax
0x18000f1fd  jnz     short loc_18000F216
0x18000f1ff  mov     rax, gs:30h
0x18000f208  mov     edi, ecx
0x18000f20a  mov     dword ptr [rax+68h], 8
0x18000f211  jmp     loc_18000F367
0x18000f216  lea     rax, [rsp+160h+cchDest]
0x18000f21b  mov     r9d, ebx; cchToCopy
0x18000f21e  mov     [rsp+160h+pcchRemaining], rax; pcchRemaining
0x18000f223  lea     r8, [rsp+160h+pszSrc]; pszSrc
0x18000f228  lea     rax, [rsp+160h+pszDest]
0x18000f22d  mov     rdx, r12; cchDest
0x18000f230  mov     rcx, rdi; pszDest
0x18000f233  mov     [rsp+160h+ppszDestEnd], rax; ppszDestEnd
0x18000f238  call    StringCchCopyNExW
0x18000f23d  xor     r9d, r9d
0x18000f240  mov     ebx, eax
0x18000f242  test    eax, eax
0x18000f244  js      loc_18000F306
0x18000f24a  test    r15d, r15d
0x18000f24d  lea     r15d, [r9+1]
0x18000f251  jz      short loc_18000F289
0x18000f253  mov     rdx, [rsp+160h+cchDest]; cchDest
0x18000f258  lea     rax, [rsp+160h+cchDest]
0x18000f25d  mov     rcx, [rsp+160h+pszDest]; pszDest
0x18000f262  lea     r8, asc_180013F14; "\\"
0x18000f269  mov     [rsp+160h+pcchRemaining], rax; pcchRemaining
0x18000f26e  mov     r9d, r15d; cchToCopy
0x18000f271  lea     rax, [rsp+160h+pszDest]
0x18000f276  mov     [rsp+160h+ppszDestEnd], rax; ppszDestEnd
0x18000f27b  call    StringCchCopyNExW
0x18000f280  xor     r9d, r9d
0x18000f283  mov     ebx, eax
0x18000f285  test    eax, eax
0x18000f287  js      short loc_18000F306
0x18000f289  mov     rcx, [rsp+160h+cchDest]
0x18000f28e  mov     r10d, 7FFFFFFEh
0x18000f294  mov     r8d, r14d
0x18000f297  lea     rax, [rcx-1]
0x18000f29b  cmp     rax, r10
0x18000f29e  ja      loc_18000F33B
0x18000f2a4  cmp     r8, r10
0x18000f2a7  jbe     short loc_18000F2B3
0x18000f2a9  mov     ebx, 80070057h
0x18000f2ae  jmp     loc_18000F34C
0x18000f2b3  mov     rdx, [rsp+160h+pszDest]
0x18000f2b8  test    rcx, rcx
0x18000f2bb  jz      short loc_18000F2E1
0x18000f2bd  sub     r8, rcx
0x18000f2c0  sub     rsi, rdx
0x18000f2c3  lea     rax, [r8+rcx]
0x18000f2c7  test    rax, rax
0x18000f2ca  jz      short loc_18000F2E1
0x18000f2cc  movzx   eax, word ptr [rsi+rdx]
0x18000f2d0  test    ax, ax
0x18000f2d3  jz      short loc_18000F2E1
0x18000f2d5  mov     [rdx], ax
0x18000f2d8  add     rdx, 2
0x18000f2dc  sub     rcx, r15
0x18000f2df  jnz     short loc_18000F2C3
0x18000f2e1  test    rcx, rcx
0x18000f2e4  lea     rax, [rdx-2]
0x18000f2e8  cmovnz  rax, rdx
0x18000f2ec  neg     rcx
0x18000f2ef  mov     [rax], r9w
0x18000f2f3  sbb     eax, eax
0x18000f2f5  not     eax
0x18000f2f7  and     eax, 8007007Ah
0x18000f2fc  mov     ebx, eax
0x18000f2fe  test    eax, eax
0x18000f300  jns     loc_18000F579
0x18000f306  mov     rcx, gs:60h
0x18000f30f  mov     r8, rdi; P
0x18000f312  xor     edx, edx; Flags
0x18000f314  mov     rcx, [rcx+30h]; HeapHandle
0x18000f318  call    cs:__imp_RtlFreeHeap
0x18000f31f  nop     dword ptr [rax+rax+00h]
0x18000f324  mov     rax, gs:30h
0x18000f32d  xor     r15d, r15d
0x18000f330  movzx   ecx, bx
0x18000f333  mov     edi, r15d
0x18000f336  mov     [rax+68h], ecx
0x18000f339  jmp     short loc_18000F367
0x18000f33b  mov     r14d, 80070057h
0x18000f341  mov     eax, r14d
0x18000f344  mov     ebx, r14d
0x18000f347  test    rcx, rcx
0x18000f34a  jz      short loc_18000F2FC
0x18000f34c  mov     rax, [rsp+160h+pszDest]
0x18000f351  mov     [rax], r9w
0x18000f355  jmp     short loc_18000F306
0x18000f357  mov     rax, gs:30h
0x18000f360  mov     dword ptr [rax+68h], 57h ; 'W'
0x18000f367  call    cs:__imp_GetLastError
0x18000f36e  nop     dword ptr [rax+rax+00h]
0x18000f373  xor     r9d, r9d
0x18000f376  test    eax, eax
0x18000f378  jle     short loc_18000F384
0x18000f37a  movzx   eax, ax
0x18000f37d  or      eax, 80070000h
0x18000f382  test    eax, eax
0x18000f384  jns     short loc_18000F3DE
0x18000f386  call    cs:__imp_GetLastError
0x18000f38d  nop     dword ptr [rax+rax+00h]
0x18000f392  xor     r9d, r9d
0x18000f395  mov     ebx, eax
0x18000f397  test    eax, eax
0x18000f399  jle     short loc_18000F3A4
0x18000f39b  movzx   ebx, ax
0x18000f39e  or      ebx, 80070000h
0x18000f3a4  mov     rax, rdi
0x18000f3a7  test    ebx, ebx
0x18000f3a9  js      loc_18000FCC9
0x18000f3af  test    rax, rax
0x18000f3b2  jnz     loc_18000F675
0x18000f3b8  mov     esi, 80070000h
0x18000f3bd  mov     rcx, [rsp+160h+var_108]; pszSrc
0x18000f3c2  call    StrDupe
0x18000f3c7  xor     r9d, r9d
0x18000f3ca  mov     rdi, rax
0x18000f3cd  test    rax, rax
0x18000f3d0  jz      loc_18000F633
0x18000f3d6  mov     ebx, r9d
0x18000f3d9  jmp     loc_18000F675
0x18000f3de  mov     ebx, 80004005h
0x18000f3e3  jmp     short loc_18000F3A4
0x18000f3e5  mov     r12, r15
0x18000f3e8  mov     r14d, r9d
0x18000f3eb  test    r15, r15
0x18000f3ee  jz      loc_18000F5DA
0x18000f3f4  lea     rax, [rsp+160h+String2]
0x18000f3f9  mov     rbx, r13
0x18000f3fc  inc     rbx
0x18000f3ff  cmp     [rax+rbx*2], r9w
0x18000f404  jnz     short loc_18000F3FC
0x18000f406  mov     rsi, r13
0x18000f409  inc     rsi
0x18000f40c  cmp     [r15+rsi*2], r9w
0x18000f411  jnz     short loc_18000F409
0x18000f413  test    ebx, ebx
0x18000f415  jz      short loc_18000F43C
0x18000f417  lea     ecx, [rbx-1]
0x18000f41a  mov     eax, 5Ch ; '\'
0x18000f41f  cmp     ax, [rsp+rcx*2+160h+String2]
0x18000f424  jnz     short loc_18000F434
0x18000f426  cmp     ax, [r15]
0x18000f42a  jnz     short loc_18000F43C
0x18000f42c  lea     r12, [r15+2]
0x18000f430  dec     esi
0x18000f432  jmp     short loc_18000F43C
0x18000f434  cmp     ax, [r15]
0x18000f438  cmovnz  r14d, r8d
0x18000f43c  lea     ecx, [rsi+1]
0x18000f43f  mov     edx, 8; Flags
0x18000f444  add     ecx, r14d
0x18000f447  add     ecx, ebx
  ... truncated ...
```
