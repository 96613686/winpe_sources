# xxxLOpen

- ea: `0x18001fb28`
- end: `0x180020b5e`
- name: `xxxLOpen`
- size: `4150`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation`

## callers

- `0x180011c40`

## callees

- `0x180001600`
- `0x180001f50`
- `0x180004cd0`
- `0x180007204`
- `0x180007394`
- `0x1800074b8`
- `0x180017b74`
- `0x180019fcc`
- `0x18001bd10`
- `0x18001c7c0`
- `0x18001c854`
- `0x18001eafc`
- `0x18001f514`
- `0x18001fb28`
- `0x18002c8d4`
- `0x18003cf88`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e2f0`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800200b0`
- `KERNEL32!HeapAlloc` at `0x1800203fd`
- `KERNEL32!HeapAlloc` at `0x180020a06`
- `KERNEL32!HeapAlloc` at `0x1800200b0`
- `KERNEL32!HeapAlloc` at `0x1800203fd`
- `KERNEL32!HeapAlloc` at `0x180020a06`
- `KERNEL32!CloseHandle` at `0x18001fcfb`
- `KERNEL32!CloseHandle` at `0x180020a9c`
- `KERNEL32!CloseHandle` at `0x18001fcfb`
- `KERNEL32!CloseHandle` at `0x180020a9c`
- `KERNEL32!Sleep` at `0x1800202b2`
- `KERNEL32!Sleep` at `0x1800202b2`
- `KERNEL32!DuplicateHandle` at `0x1800201ff`
- `KERNEL32!DuplicateHandle` at `0x1800201ff`
- `KERNEL32!ReleaseMutex` at `0x18001fced`
- `KERNEL32!ReleaseMutex` at `0x1800202aa`
- `KERNEL32!ReleaseMutex` at `0x1800207e1`
- `KERNEL32!ReleaseMutex` at `0x180020b38`
- `KERNEL32!ReleaseMutex` at `0x18001fced`
- `KERNEL32!ReleaseMutex` at `0x1800202aa`
- `KERNEL32!ReleaseMutex` at `0x1800207e1`
- `KERNEL32!ReleaseMutex` at `0x180020b38`
- `KERNEL32!GetCurrentThreadId` at `0x1800201ad`
- `KERNEL32!GetCurrentThreadId` at `0x180020211`
- `KERNEL32!GetCurrentThreadId` at `0x1800201ad`
- `KERNEL32!GetCurrentThreadId` at `0x180020211`
- `KERNEL32!WaitForSingleObject` at `0x18002025d`
- `KERNEL32!WaitForSingleObject` at `0x180020abf`
- `KERNEL32!WaitForSingleObject` at `0x18002025d`
- `KERNEL32!WaitForSingleObject` at `0x180020abf`
- `KERNEL32!LeaveCriticalSection` at `0x180020237`
- `KERNEL32!LeaveCriticalSection` at `0x1800208f4`
- `KERNEL32!LeaveCriticalSection` at `0x180020237`
- `KERNEL32!LeaveCriticalSection` at `0x1800208f4`
- `KERNEL32!EnterCriticalSection` at `0x18002019d`
- `KERNEL32!EnterCriticalSection` at `0x18002019d`

## string_xrefs

- `0x18001ff29`: `lineOpen(SINGLEADDRESS): callParams.dwAddressMode!= ADDRESSID`
- `0x180020015`: `lineOpen(PROXY): inval proxy request type array size (callParams.dwDevSpecificSize=x%x)`
- `0x18001ffff`: `lineOpen(PROXY): inval proxy request type (x%x)`
- `0x1800200d8`: `lineOpen: calling NewObject. ptLineClient %p`
- `0x18002010d`: `lineOpen: NewObject returned %Iu`
- `0x180020185`: `lineOpen: OpenContext %Iu`
- `0x180020418`: `xxxLOpen: calling NewObject ptLine %p`
- `0x1800207fa`: `xxxLOpen: adding ptLineClient [%p] to hLineApp's [%Iu] list`
- `0x180020949`: `tell clients proxy %02X opened`
- `0x1800209a2`: `tell clients that all proxys needed for TAPI3.0 ACD are open`
- `0x180020a42`: `xxxLOpen returning hLine of %Iu`

## pseudocode

```c
__int64 __fastcall xxxLOpen(_QWORD *a1, __int64 a2, unsigned int a3, __int64 a4, _DWORD *a5, int a6)
{
  _DWORD *v8; // r14
  _DWORD *v9; // r15
  int v10; // esi
  int *v11; // r13
  __int64 v12; // rcx
  int v13; // ebx
  bool v14; // zf
  void (__fastcall *v15)(_QWORD, _QWORD); // rax
  void (__fastcall *v16)(_QWORD); // rax
  unsigned int v18; // r8d
  _DWORD *v19; // r10
  __int64 v20; // r11
  __int64 v21; // r9
  __int64 v22; // r8
  _DWORD *v23; // rax
  int *v24; // rcx
  __int64 v25; // r8
  unsigned int v26; // r10d
  __int64 v27; // rcx
  const wchar_t *v28; // r8
  __int64 v29; // rax
  char *v30; // rdx
  unsigned int i; // ecx
  __int64 v32; // r8
  unsigned int v33; // r13d
  int v34; // eax
  _DWORD *v35; // rax
  __int64 v36; // rcx
  int v37; // eax
  BOOL v38; // ebx
  int v39; // eax
  int v40; // ecx
  size_t v41; // rdx
  char *v42; // r13
  void *v43; // rdx
  size_t v44; // rdx
  _DWORD *v45; // rax
  int v46; // ebx
  _QWORD *v47; // r8
  int valid; // eax
  const char *v49; // rdx
  _DWORD *v50; // rax
  __int64 v51; // rcx
  unsigned int v52; // eax
  __int64 v53; // rcx
  char *v54; // r9
  unsigned __int64 v55; // rdx
  __int64 (__fastcall *v56)(_QWORD, unsigned __int64, _DWORD *, _QWORD, __int64 (__fastcall *)(int, int, int, int, void *, size_t)); // rax
  void (__fastcall *v57)(_QWORD, _DWORD *); // rax
  unsigned int j; // edx
  unsigned int v59; // ecx
  unsigned int (__fastcall *v60)(_QWORD, _QWORD, _DWORD *); // rax
  __int64 (__fastcall *v61)(_QWORD, _QWORD, _QWORD *); // rax
  unsigned int v62; // ebx
  unsigned int v63; // edx
  char *v64; // rsi
  int v65; // edx
  unsigned int k; // ecx
  __int64 v67; // rax
  unsigned __int64 v68; // rbx
  __int64 v69; // rax
  unsigned int v70; // r13d
  __int64 v71; // rax
  size_t v72; // rbx
  wchar_t *v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rax
  void (__fastcall *v77)(_QWORD, _QWORD); // rax
  int v78; // [rsp+70h] [rbp-1A8h]
  _QWORD *v80; // [rsp+80h] [rbp-198h]
  int v81; // [rsp+88h] [rbp-190h]
  int v82; // [rsp+88h] [rbp-190h]
  unsigned int v83; // [rsp+8Ch] [rbp-18Ch]
  int v84; // [rsp+94h] [rbp-184h]
  int v85; // [rsp+98h] [rbp-180h]
  unsigned int v86; // [rsp+9Ch] [rbp-17Ch]
  unsigned int v87; // [rsp+A0h] [rbp-178h]
  int v88; // [rsp+A4h] [rbp-174h]
  int v89; // [rsp+A8h] [rbp-170h]
  _DWORD *lpMem; // [rsp+B0h] [rbp-168h]
  unsigned int v91; // [rsp+B8h] [rbp-160h] BYREF
  unsigned int v92; // [rsp+BCh] [rbp-15Ch]
  BOOL v93; // [rsp+C0h] [rbp-158h]
  HANDLE hMutex; // [rsp+C8h] [rbp-150h] BYREF
  char *v95; // [rsp+D0h] [rbp-148h] BYREF
  int v96; // [rsp+D8h] [rbp-140h]
  unsigned int v97; // [rsp+DCh] [rbp-13Ch] BYREF
  unsigned int v98; // [rsp+E0h] [rbp-138h] BYREF
  char *v99; // [rsp+E8h] [rbp-130h]
  _QWORD *v100; // [rsp+F0h] [rbp-128h]
  int *v101; // [rsp+100h] [rbp-118h]
  _DWORD *v102; // [rsp+108h] [rbp-110h]
  HANDLE v103[6]; // [rsp+110h] [rbp-108h] BYREF
  unsigned int *v104; // [rsp+140h] [rbp-D8h]
  _DWORD *v105; // [rsp+148h] [rbp-D0h]
  _DWORD *v106; // [rsp+150h] [rbp-C8h]
  _QWORD v107[5]; // [rsp+158h] [rbp-C0h] BYREF
  wchar_t pszDest[40]; // [rsp+180h] [rbp-98h] BYREF

  v101 = (int *)a2;
  v100 = a1;
  v103[5] = (HANDLE)a2;
  v103[4] = a1;
  v102 = a5;
  v98 = 0;
  v91 = 0;
  v103[0] = 0;
  v97 = 0;
  v95 = 0;
  lpMem = 0;
  hMutex = 0;
  v85 = 0;
  v78 = 0;
  v84 = 0;
  v93 = 0;
  v8 = 0;
  v80 = 0;
  v9 = 0;
  pszDest[0] = 0;
  v10 = LineProlog((__int64)a1, 3, *(_DWORD *)(a2 + 8), &v91, *(_DWORD *)(a2 + 12), v103, &v98, 0, 0, 0, 0, &v97, &v95);
  v96 = v10;
  if ( v10 )
    goto LABEL_4;
  if ( (dword_180051900 & 1) != 0 )
  {
    v10 = -2147483566;
LABEL_4:
    v11 = (int *)a2;
LABEL_5:
    v12 = 0;
LABEL_6:
    v13 = 0;
    goto LABEL_7;
  }
  v86 = *(_DWORD *)(a2 + 20);
  if ( !(unsigned int)IsAPIVersionInRange(v86, *(unsigned int *)v95) )
  {
    v10 = -2147483636;
    v11 = v19;
    goto LABEL_5;
  }
  v104 = v19 + 8;
  LODWORD(v21) = v19[8];
  v81 = v21;
  v80 = *(_QWORD **)(v20 + 24);
  v103[2] = v80;
  if ( (v21 & 0x3FFFFFF8) != 0 || (v21 & 7) == 0 || (v21 & 6) != 0 && (v21 & 1) != 0 )
  {
    v10 = -2147483594;
    goto LABEL_35;
  }
  v87 = v19[6];
  v83 = 0;
  v99 = 0;
  if ( (v21 & 0xC0000000) != 0 || a6 )
  {
    v22 = (unsigned int)v19[10];
    v23 = 0;
    if ( (_DWORD)v22 != -1 )
      v23 = (_DWORD *)(a4 + v22);
    lpMem = v23;
    if ( !v23 )
    {
      v10 = -2147483595;
LABEL_35:
      v11 = v19;
LABEL_36:
      v12 = (__int64)v80;
      goto LABEL_6;
    }
    if ( (unsigned int)IsBadStructParam(a3, a4, v22) )
    {
      v24 = v101;
      *v101 = -2147483576;
      v11 = v24;
      goto LABEL_36;
    }
    v11 = (int *)a2;
    v10 = ValidateCallParams(lpMem, *(_DWORD *)(a2 + 44));
    v96 = v10;
    if ( v10 )
    {
      v10 = -2147483595;
      goto LABEL_36;
    }
    v19 = (_DWORD *)a2;
    v93 = lpMem != (_DWORD *)(a4 + *(unsigned int *)(a2 + 40));
    v21 = (unsigned int)v81;
    if ( v81 < 0 && lpMem[6] != 1 )
    {
      TRACELogPrint(65538, "lineOpen(SINGLEADDRESS): callParams.dwAddressMode!= ADDRESSID");
      goto LABEL_44;
    }
    if ( (v81 & 0x40000000) == 0 )
      goto LABEL_59;
    v25 = (unsigned int)lpMem[26];
    v26 = (lpMem[26] >> 2) & 0x3FFF;
    v83 = v26;
    if ( v26 - 1 > 0x13 )
    {
      TRACELogPrint(
        65538,
        "lineOpen(PROXY): inval proxy request type array size (callParams.dwDevSpecificSize=x%x)",
        v25,
        (unsigned int)v81);
    }
    else
    {
      if ( !WORD1(v25) )
        goto LABEL_52;
      v27 = *((unsigned __int16 *)lpMem + 52);
      v28 = (const wchar_t *)((char *)lpMem + (unsigned int)lpMem[27] + v27);
      lpMem[26] = v27;
      v29 = -1;
      do
        ++v29;
      while ( v28[v29] );
      if ( (unsigned __int64)(2 * v29) <= 0x50 )
      {
        StringCbCopyW(pszDest, 2 * v29, v28);
        v21 = (unsigned int)v81;
        v26 = v83;
LABEL_52:
        v30 = (char *)lpMem + (unsigned int)lpMem[27];
        v99 = v30;
        for ( i = 0; i < v26; ++i )
        {
          v32 = *(unsigned int *)&v30[4 * i];
          if ( (unsigned int)(v32 - 1) > 0x13 )
          {
            TRACELogPrint(65538, "lineOpen(PROXY): inval proxy request type (x%x)", v32, v21);
            goto LABEL_44;
          }
        }
        v19 = (_DWORD *)a2;
LABEL_59:
        v18 = v86;
        goto LABEL_60;
      }
    }
LABEL_44:
    v10 = -2147483623;
    goto LABEL_36;
  }
LABEL_60:
  if ( (v21 & 4) != 0 )
  {
    v33 = v19[9];
    v92 = v33;
    if ( v18 == 65539 )
    {
      v34 = 16760833;
    }
    else if ( v18 == 65540 || v18 == 0x20000 )
    {
      v34 = 16744449;
    }
    else
    {
      v34 = 16711681;
    }
    if ( !v33 || (v34 & v33) != 0 )
    {
      v10 = -2147483601;
LABEL_70:
      v11 = (int *)a2;
      goto LABEL_36;
    }
  }
  else
  {
    v33 = 0;
    v92 = 0;
  }
  v35 = HeapAlloc(ghTapisrvHeap, 8u, 0x128u);
  v106 = v35;
  v9 = v35;
  v103[3] = v35;
  if ( !v35 )
  {
LABEL_73:
    v10 = -2147483580;
    goto LABEL_70;
  }
  TRACELogPrint(524290, "lineOpen: calling NewObject. ptLineClient %p", v35);
  v37 = NewObject(v36, v9, 0);
  v9[6] = v37;
  if ( !v37 )
  {
    v9 = 0;
    ServerFree(0);
    goto LABEL_73;
  }
  v38 = 0;
  TRACELogPrint(524290, "lineOpen: NewObject returned %Iu", v37);
  *((_QWORD *)v9 + 1) = v100;
  v39 = *(_DWORD *)(a2 + 52);
  if ( !v39 )
    v39 = v9[6];
  v9[14] = v39;
  v9[15] = v86;
  v9[16] = v81;
  v9[17] = v33;
  v9[18] = *(_DWORD *)(a2 + 28);
  if ( v81 >= 0 )
    v40 = -1;
  else
    v40 = lpMem[7];
  v105 = v9 + 10;
  v9[10] = v40;
  TRACELogPrint(262146, "lineOpen: OpenContext %Iu", *(_DWORD *)(a2 + 28));
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 25404;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(::pszDest, v41, "i\\server\\line.c");
  v42 = v95;
  v43 = (void *)*((_QWORD *)v95 + 2);
  if ( v43 )
    v38 = DuplicateHandle(hSourceProcessHandle, v43, hSourceProcessHandle, &hMutex, 0, 0, 2u);
  dword_1800519F8 = 25419;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v44, "i\\server\\line.c");
  LeaveCriticalSection(&CriticalSection);
  if ( !v38 )
  {
    v84 = 0;
    v10 = -2147483576;
    goto LABEL_70;
  }
  while ( 1 )
  {
    if ( WaitForSingleObject(hMutex, 0xFFFFFFFF) )
    {
      v84 = 0;
      goto LABEL_87;
    }
    v84 = 1;
    v45 = (_DWORD *)*((_QWORD *)v42 + 1);
    if ( !v45 || *v45 == 1162758476 )
      break;
    ReleaseMutex(hMutex);
    Sleep(0);
  }
  v46 = v81;
  v47 = v80;
  if ( *((_DWORD *)v95 + 8) )
  {
    v10 = -2147483646;
    goto LABEL_88;
  }
  if ( v87 )
  {
    valid = IsValidLineExtVersion(v91, v87, v80);
    v47 = v80;
    if ( !valid || !v80[66] )
    {
      v49 = "The provider does not support TSPI_lineSelectExtVersion - that's a problem";
      if ( v80[66] )
        v49 = "Bad ExtVersion was passed in - that's a problem";
      TRACELogPrint(65538, v49, v80);
      v10 = -2147483635;
LABEL_88:
      v12 = (__int64)v80;
LABEL_89:
      v11 = (int *)a2;
      v13 = v78;
      goto LABEL_7;
    }
  }
  v8 = (_DWORD *)*((_QWORD *)v95 + 1);
  if ( v8 )
  {
    if ( (v81 & 0x40000000) != 0 )
    {
      for ( j = 0; j < v83; ++j )
      {
        if ( *(_QWORD *)&v8[2 * *(unsigned int *)&v99[4 * j] + 6] )
        {
          v10 = -2147483577;
          goto LABEL_88;
        }
      }
    }
    goto LABEL_124;
  }
  v50 = HeapAlloc(ghTapisrvHeap, 8u, 0x110u);
  v8 = v50;
  if ( !v50 )
  {
LABEL_103:
    v10 = -2147483580;
    goto LABEL_88;
  }
  TRACELogPrint(524290, "xxxLOpen: calling NewObject ptLine %p", v50);
  v52 = NewObject(v51, v8, 0);
  v53 = v52;
  v8[52] = v52;
  if ( !v52 )
  {
    ServerFree(v8);
    goto LABEL_103;
  }
  *v8 = 1313426505;
  v54 = v95;
  *((_QWORD *)v8 + 1) = *((_QWORD *)v95 + 2);
  *((_QWORD *)v8 + 24) = v80;
  v8[53] = v91;
  v8[54] = *(_DWORD *)v54;
  v55 = v52;
  if ( v80 == (_QWORD *)pRemoteSP )
  {
    v107[0] = v52;
    v107[1] = *v104;
    v107[2] = *(unsigned int *)(a2 + 36);
    v107[3] = lpMem;
    v107[4] = v87;
    v55 = (unsigned __int64)v107;
  }
  v56 = (__int64 (__fastcall *)(_QWORD, unsigned __int64, _DWORD *, _QWORD, __int64 (__fastcall *)(int, int, int, int, void *, size_t)))v80[58];
  if ( !v56 )
    v10 = -2147483575;
  if ( v10 || (v10 = v56(v91, v55, v8 + 50, *(unsigned int *)v54, LineEventProcSP)) != 0 )
  {
    DereferenceObject(v53, v8[52], 1);
    goto LABEL_116;
  }
  v85 = 1;
  v12 = (__int64)v80;
  v57 = (void (__fastcall *)(_QWORD, _DWORD *))v80[50];
  if ( !v57 )
  {
    v10 = -2147483575;
    goto LABEL_89;
  }
  v57(*((_QWORD *)v8 + 25), v8 + 57);
  ++dword_1800518AC;
  v46 = v81;
  v47 = v80;
LABEL_124:
  *((_QWORD *)v9 + 4) = v8;
  if ( v46 < 0 && *v105 >= v8[57] )
  {
    v10 = -2147483631;
    goto LABEL_88;
  }
  v59 = v87;
  if ( v87 )
  {
    if ( !v8[56] )
    {
      if ( v47 != (_QWORD *)pRemoteSP )
      {
        if ( !v47[66] )
        {
          v10 = -2147483575;
          goto LABEL_88;
        }
        if ( v47 != (_QWORD *)pRemoteSP )
        {
          v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v47[66])(*((_QWORD *)v8 + 25), v87);
          if ( !v10 )
          {
            v59 = v87;
            v47 = v80;
            goto LABEL_135;
          }
LABEL_116:
          if ( !a6 )
            goto LABEL_88;
LABEL_87:
          v10 = -2147483576;
          goto LABEL_88;
        }
      }
LABEL_135:
      v8[55] = v59;
    }
    v9[24] = v59;
    ++v8[56];
    v78 = 1;
  }
  if ( a6 )
  {
    v60 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _DWORD *))v47[25];
    if ( !v60 || v60(*((_QWORD *)v8 + 25), v8[58] | v92, lpMem) )
    {
      --dword_1800518AC;
      goto LABEL_87;
    }
  }
  if ( (*(_BYTE *)(a2 + 32) & 4) != 0 )
  {
    if ( (v92 & v8[58]) != v92 )
    {
      v61 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD *))v80[77];
      if ( !v61 )
      {
        v10 = -2147483575;
LABEL_147:
        --dword_1800518AC;
        goto LABEL_88;
      }
      v62 = v92 | v8[58];
      v10 = v61(*((_QWORD *)v8 + 25), v62, v47);
      if ( v10 )
      {
        if ( a6 )
          v10 = -2147483576;
        goto LABEL_147;
      }
      v8[58] = v62;
    }
    v46 = v81;
  }
  v82 = v46 & 0x40000000;
  if ( (v46 & 0x40000000) != 0 )
  {
    v63 = 0;
    if ( v83 )
    {
      v64 = v99;
      do
        *(_QWORD *)&v8[2 * *(unsigned int *)&v64[4 * v63++] + 6] = v9;
      while ( v63 < v83 );
      v10 = 0;
    }
  }
  v65 = 0;
  for ( k = 1; k <= 0x14; ++k )
  {
    if ( *(_QWORD *)&v8[2 * k + 6] )
      v65 |= 1 << k;
  }
  v88 = v65;
  v67 = *((_QWORD *)v8 + 2);
  *((_QWORD *)v9 + 14) = v67;
  if ( v67 )
    *(_QWORD *)(v67 + 104) = v9;
  *((_QWORD *)v8 + 2) = v9;
  ++v8[59];
  if ( v85 )
  {
    *((_QWORD *)v95 + 1) = v8;
    *v8 = 1162758476;
  }
  ReleaseMutex(hMutex);
  v84 = 0;
  v11 = (int *)a2;
  TRACELogPrint(524290, "xxxLOpen: adding ptLineClient [%p] to hLineApp's [%Iu] list", v9, *(_DWORD *)(a2 + 8));
  v68 = WaitForExclusiveLineAppAccess(*(unsigned int *)(a2 + 8), v100);
  if ( v68 )
  {
    if ( *(_DWORD *)(v68 + 48) > 0x30000u )
    {
      *(_OWORD *)(v9 + 42) = *(_OWORD *)(v68 + 80);
      *(_OWORD *)(v9 + 46) = *(_OWORD *)(v68 + 96);
      *(_OWORD *)(v9 + 50) = *(_OWORD *)(v68 + 112);
      *(_OWORD *)(v9 + 54) = *(_OWORD *)(v68 + 128);
      *(_OWORD *)(v9 + 58) = *(_OWORD *)(v68 + 144);
      *(_OWORD *)(v9 + 62) = *(_OWORD *)(v68 + 160);
      *(_OWORD *)(v9 + 66) = *(_OWORD *)(v68 + 176);
      *(_OWORD *)(v9 + 69) = *(_OWORD *)(v68 + 188);
    }
    else
    {
      memset_0(v9 + 42, 255, 0x7Cu);
    }
    v69 = *(_QWORD *)(v68 + 16);
    *((_QWORD *)v9 + 16) = v69;
    if ( v69 )
      *(_QWORD *)(v69 + 120) = v9;
    *(_QWORD *)(v68 + 16) = v9;
    v89 = v9[6];
    *((_QWORD *)v9 + 2) = v68;
    *v106 = 1229734732;
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v68 >> 4)));
    SendMsgToLineClients((_DWORD)v8, (_DWORD)v9, 8, 512, 0, 0);
    if ( v82 )
    {
      v70 = 0;
      if ( v83 )
      {
        do
        {
          TRACELogPrint(262146, "tell clients proxy %02X opened", *(_DWORD *)&v99[4 * v70]);
          SendMsgToLineClients((_DWORD)v8, (_DWORD)v9, 31, 1, *(_DWORD *)&v99[4 * v70++], 0);
        }
        while ( v70 < v83 );
        v10 = 0;
      }
      if ( (v88 & 0x1FFE10) == 0x1FFE10 )
      {
        TRACELogPrint(262146, "tell clients that all proxys needed for TAPI3.0 ACD are open");
        SendMsgToLineClients((_DWORD)v8, (_DWORD)v9, 31, 4, 0, 0);
      }
      if ( pszDest[0] )
      {
        v71 = -1;
        do
          ++v71;
        while ( pszDest[v71] );
        v72 = 2 * v71 + 2;
        v73 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * v71 + 2));
        *((_QWORD *)v9 + 20) = v73;
        if ( v73 )
        {
          StringCbCopyW(v73, v72, pszDest);
          OnProxyLineOpen(pszDest);
        }
      }
    }
    TRACELogPrint(524290, "xxxLOpen returning hLine of %Iu", v89);
    *(_DWORD *)(a2 + 16) = v89;
    *v102 = 56;
    if ( (v100[1] & 0xFFFFFFFFFFFFFFFEuLL) == 0xFFFFFFFFFFFFFFFEuLL || v100[1] == -3 )
      *(_DWORD *)(a2 + 48) = -1;
    v13 = v78;
    v11 = (int *)a2;
  }
  else
  {
    v10 = -2147483628;
    WaitForSingleObject(hMutex, 0xFFFFFFFF);
    v74 = *((_QWORD *)v9 + 14);
    if ( v74 )
      *(_QWORD *)(v74 + 104) = *((_QWORD *)v9 + 13);
    v75 = *((_QWORD *)v9 + 13);
    v76 = *((_QWORD *)v9 + 14);
    if ( v75 )
      *(_QWORD *)(v75 + 112) = v76;
    else
      *((_QWORD *)v8 + 2) = v76;
    --v8[59];
    v13 = v78;
    if ( v78 == 1 )
    {
      v14 = v8[56]-- == 1;
      if ( v14 )
      {
        v8[55] = 0;
        v77 = (void (__fastcall *)(_QWORD, _QWORD))v80[66];
        if ( v77 )
          v77(*((_QWORD *)v8 + 25), 0);
      }
    }
    ReleaseMutex(hMutex);
    DestroytLine(v8, 0);
    v85 = 0;
  }
  CloseHandle(hMutex);
  v12 = (__int64)v80;
LABEL_7:
  if ( v84 )
  {
    if ( v10 )
    {
      if ( v13 == 1 )
      {
        v14 = v8[56]-- == 1;
        if ( v14 )
        {
          v8[55] = 0;
          v15 = *(void (__fastcall **)(_QWORD, _QWORD))(v12 + 528);
          if ( v15 )
            v15(*((_QWORD *)v8 + 25), 0);
        }
      }
      if ( v85 == 1 )
      {
        v16 = (void (__fastcall *)(_QWORD))v80[21];
        if ( v16 )
          v16(*((_QWORD *)v8 + 25));
      }
    }
    ReleaseMutex(hMutex);
    CloseHandle(hMutex);
  }
  *v101 = v10;
  if ( v10 )
  {
    if ( v9 )
      DereferenceObject(v12, v9[6], 1);
    if ( v85 )
      DereferenceObject(v12, v8[52], 1);
  }
  if ( v93 )
    ServerFree(lpMem);
  return LineEpilogSync(v11, (__int64)v103[0], v98, v97);
}

```

## disassembly

```asm
0x18001fb28  mov     r11, rsp
0x18001fb2b  push    rbx
0x18001fb2c  push    rsi
0x18001fb2d  push    rdi
0x18001fb2e  push    r12
0x18001fb30  push    r13
0x18001fb32  push    r14
0x18001fb34  push    r15
0x18001fb36  sub     rsp, 1E0h
0x18001fb3d  mov     rax, cs:__security_cookie
0x18001fb44  xor     rax, rsp
0x18001fb47  mov     [rsp+218h+var_48], rax
0x18001fb4f  mov     rbx, r9
0x18001fb52  mov     r13d, r8d
0x18001fb55  mov     [rsp+218h+var_118], rdx
0x18001fb5d  mov     [rsp+218h+var_128], rcx
0x18001fb65  mov     [rsp+218h+var_E0], rdx
0x18001fb6d  mov     [rsp+218h+var_E8], rcx
0x18001fb75  mov     [rsp+218h+var_1A0], rdx
0x18001fb7a  mov     rax, [rsp+218h+arg_20]
0x18001fb82  mov     [rsp+218h+var_110], rax
0x18001fb8a  xor     edi, edi
0x18001fb8c  mov     [rsp+218h+var_138], edi
0x18001fb93  mov     [rsp+218h+var_160], edi
0x18001fb9a  mov     [r11-108h], rdi
0x18001fba1  mov     [rsp+218h+var_13C], edi
0x18001fba8  mov     [r11-148h], rdi
0x18001fbaf  mov     [r11-168h], rdi
0x18001fbb6  mov     [r11-150h], rdi
0x18001fbbd  mov     eax, edi
0x18001fbbf  mov     [rsp+218h+var_180], eax
0x18001fbc6  mov     [rsp+218h+var_1A8], eax
0x18001fbca  mov     [rsp+218h+var_184], edi
0x18001fbd1  mov     [rsp+218h+var_158], edi
0x18001fbd8  mov     r14d, edi
0x18001fbdb  mov     [rsp+218h+var_198], rdi
0x18001fbe3  mov     r15d, edi
0x18001fbe6  mov     [rsp+218h+pszDest], di
0x18001fbee  lea     rax, [r11-148h]
0x18001fbf5  mov     [rsp+218h+var_1B8], rax; __int64
0x18001fbfa  lea     rax, [r11-13Ch]
0x18001fc01  mov     [rsp+218h+var_1C0], rax; __int64
0x18001fc06  mov     [rsp+218h+var_1C8], edi; int
0x18001fc0a  mov     [rsp+218h+var_1D0], rdi; __int64
0x18001fc0f  mov     [rsp+218h+var_1D8], rdi; __int64
0x18001fc14  mov     [rsp+218h+var_1E0], edi; int
0x18001fc18  lea     rax, [r11-138h]
0x18001fc1f  mov     qword ptr [rsp+218h+dwOptions], rax; __int64
0x18001fc24  lea     rax, [r11-108h]
0x18001fc2b  mov     qword ptr [rsp+218h+bInheritHandle], rax; lpTargetHandle
0x18001fc30  mov     eax, [rdx+0Ch]
0x18001fc33  mov     [rsp+218h+dwDesiredAccess], eax; int
0x18001fc37  lea     r9, [r11-160h]; int
0x18001fc3e  mov     r8d, [rdx+8]; int
0x18001fc42  lea     edx, [rdi+3]; int
0x18001fc45  call    LineProlog
0x18001fc4a  mov     esi, eax
0x18001fc4c  mov     [rsp+218h+var_188], eax
0x18001fc53  mov     [rsp+218h+var_140], eax
0x18001fc5a  lea     r12d, [rdi+1]
0x18001fc5e  test    eax, eax
0x18001fc60  jnz     short loc_18001FC74
0x18001fc62  test    byte ptr cs:dword_180051900, r12b
0x18001fc69  jz      loc_18001FD91
0x18001fc6f  mov     esi, 80000052h
0x18001fc74  mov     r13, [rsp+218h+var_1A0]
0x18001fc79  mov     rcx, rdi
0x18001fc7c  mov     ebx, edi
0x18001fc7e  cmp     [rsp+218h+var_184], edi
0x18001fc85  jz      short loc_18001FD01
0x18001fc87  test    esi, esi
0x18001fc89  jz      short loc_18001FCE5
0x18001fc8b  cmp     ebx, r12d
0x18001fc8e  jnz     short loc_18001FCBB
0x18001fc90  add     dword ptr [r14+0E0h], 0FFFFFFFFh
0x18001fc98  jnz     short loc_18001FCBB
0x18001fc9a  mov     [r14+0DCh], edi
0x18001fca1  mov     rax, [rcx+210h]
0x18001fca8  test    rax, rax
0x18001fcab  jz      short loc_18001FCBB
0x18001fcad  xor     edx, edx
0x18001fcaf  mov     rcx, [r14+0C8h]
0x18001fcb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcbb  cmp     [rsp+218h+var_180], r12d
0x18001fcc3  jnz     short loc_18001FCE5
0x18001fcc5  mov     rax, [rsp+218h+var_198]
0x18001fccd  mov     rax, [rax+0A8h]
0x18001fcd4  test    rax, rax
0x18001fcd7  jz      short loc_18001FCE5
0x18001fcd9  mov     rcx, [r14+0C8h]
0x18001fce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fce5  mov     rcx, [rsp+218h+hMutex]; hMutex
0x18001fced  call    cs:__imp_ReleaseMutex
0x18001fcf3  mov     rcx, [rsp+218h+hMutex]; hObject
0x18001fcfb  call    cs:__imp_CloseHandle
0x18001fd01  mov     rax, [rsp+218h+var_118]
0x18001fd09  mov     [rax], esi
0x18001fd0b  test    esi, esi
0x18001fd0d  jz      short loc_18001FD38
0x18001fd0f  test    r15, r15
0x18001fd12  jz      short loc_18001FD20
0x18001fd14  mov     r8d, r12d
0x18001fd17  mov     edx, [r15+18h]
0x18001fd1b  call    DereferenceObject
0x18001fd20  cmp     [rsp+218h+var_180], edi
0x18001fd27  jz      short loc_18001FD38
0x18001fd29  mov     r8d, r12d
0x18001fd2c  mov     edx, [r14+0D0h]
0x18001fd33  call    DereferenceObject
0x18001fd38  cmp     [rsp+218h+var_158], edi
0x18001fd3f  jz      short loc_18001FD4E
0x18001fd41  mov     rcx, [rsp+218h+lpMem]; lpMem
0x18001fd49  call    ServerFree
0x18001fd4e  mov     r9d, [rsp+218h+var_13C]
0x18001fd56  mov     r8d, [rsp+218h+var_138]
0x18001fd5e  mov     rdx, [rsp+218h+var_108]
0x18001fd66  mov     rcx, r13
0x18001fd69  call    LineEpilogSync
0x18001fd6e  mov     rcx, [rsp+218h+var_48]
0x18001fd76  xor     rcx, rsp; StackCookie
0x18001fd79  call    __security_check_cookie
0x18001fd7e  add     rsp, 1E0h
0x18001fd85  pop     r15
0x18001fd87  pop     r14
0x18001fd89  pop     r13
0x18001fd8b  pop     r12
0x18001fd8d  pop     rdi
0x18001fd8e  pop     rsi
0x18001fd8f  pop     rbx
0x18001fd90  retn
0x18001fd91  mov     r10, [rsp+218h+var_1A0]
0x18001fd96  mov     r8d, [r10+14h]
0x18001fd9a  mov     [rsp+218h+var_17C], r8d
0x18001fda2  mov     r11, [rsp+218h+var_148]
0x18001fdaa  mov     edx, [r11]
0x18001fdad  mov     ecx, r8d
0x18001fdb0  call    IsAPIVersionInRange
0x18001fdb5  test    eax, eax
0x18001fdb7  jnz     short loc_18001FDC6
0x18001fdb9  mov     esi, 8000000Ch
0x18001fdbe  mov     r13, r10
0x18001fdc1  jmp     loc_18001FC79
0x18001fdc6  lea     rax, [r10+20h]
0x18001fdca  mov     [rsp+218h+var_D8], rax
0x18001fdd2  mov     r9d, [rax]
0x18001fdd5  mov     [rsp+218h+var_190], r9d
0x18001fddd  mov     rax, [r11+18h]
0x18001fde1  mov     [rsp+218h+var_198], rax
0x18001fde9  mov     [rsp+218h+var_F8], rax
0x18001fdf1  test    r9d, 3FFFFFF8h
0x18001fdf8  setz    cl
0x18001fdfb  test    r9b, 7
0x18001fdff  setnz   al
0x18001fe02  test    al, cl
0x18001fe04  jz      loc_180020B54
0x18001fe0a  test    r9b, 6
0x18001fe0e  setnz   cl
0x18001fe11  test    r12b, r9b
0x18001fe14  setnz   al
0x18001fe17  test    al, cl
0x18001fe19  jnz     loc_180020B54
0x18001fe1f  mov     eax, [r10+18h]
0x18001fe23  mov     [rsp+218h+var_178], eax
0x18001fe2a  mov     [rsp+218h+var_18C], edi
0x18001fe31  mov     [rsp+218h+var_130], rdi
0x18001fe39  test    r9d, 0C0000000h
0x18001fe40  jnz     short loc_18001FE4F
0x18001fe42  cmp     [rsp+218h+arg_28], edi
0x18001fe49  jz      loc_180020029
0x18001fe4f  mov     r8d, [r10+28h]
0x18001fe53  cmp     r8d, 0FFFFFFFFh
0x18001fe57  mov     rax, rdi
0x18001fe5a  jz      short loc_18001FE60
0x18001fe5c  lea     rax, [rbx+r8]
0x18001fe60  mov     [rsp+218h+lpMem], rax
0x18001fe68  test    rax, rax
0x18001fe6b  jnz     short loc_18001FE82
0x18001fe6d  mov     esi, 80000035h
0x18001fe72  mov     r13, r10
0x18001fe75  mov     rcx, [rsp+218h+var_198]
0x18001fe7d  jmp     loc_18001FC7C
0x18001fe82  mov     rdx, rbx
0x18001fe85  mov     ecx, r13d
0x18001fe88  call    IsBadStructParam
0x18001fe8d  test    eax, eax
0x18001fe8f  jz      short loc_18001FEA4
0x18001fe91  mov     rcx, [rsp+218h+var_118]
0x18001fe99  mov     dword ptr [rcx], 80000048h
0x18001fe9f  mov     r13, rcx
0x18001fea2  jmp     short loc_18001FE75
0x18001fea4  mov     r13, [rsp+218h+var_1A0]
0x18001fea9  mov     eax, [r13+2Ch]
0x18001fead  mov     [rsp+218h+dwDesiredAccess], eax; CodePage
0x18001feb1  mov     rcx, [rsp+218h+var_148]
0x18001feb9  mov     r9d, [rcx]
0x18001febc  mov     r8d, [rsp+218h+var_17C]
0x18001fec4  lea     rdx, [rsp+218h+lpMem]
0x18001fecc  mov     rcx, [rsp+218h+lpMem]; Src
0x18001fed4  call    ValidateCallParams
0x18001fed9  mov     esi, eax
0x18001fedb  mov     [rsp+218h+var_188], eax
0x18001fee2  mov     [rsp+218h+var_140], eax
0x18001fee9  test    eax, eax
0x18001feeb  jz      short loc_18001FEF4
0x18001feed  mov     esi, 80000035h
0x18001fef2  jmp     short loc_18001FE75
0x18001fef4  mov     r10, r13
0x18001fef7  mov     eax, [r13+28h]
0x18001fefb  add     rax, rbx
0x18001fefe  mov     ecx, edi
0x18001ff00  mov     rdx, [rsp+218h+lpMem]
0x18001ff08  cmp     rdx, rax
0x18001ff0b  cmovnz  ecx, r12d
0x18001ff0f  mov     [rsp+218h+var_158], ecx
0x18001ff16  mov     r9d, [rsp+218h+var_190]
0x18001ff1e  test    r9d, r9d
0x18001ff21  jns     short loc_18001FF44
0x18001ff23  cmp     [rdx+18h], r12d
0x18001ff27  jz      short loc_18001FF44
0x18001ff29  lea     rdx, aLineopenSingle; "lineOpen(SINGLEADDRESS): callParams.dwA"...
0x18001ff30  mov     ecx, 10002h
0x18001ff35  call    TRACELogPrint
0x18001ff3a  mov     esi, 80000019h
0x18001ff3f  jmp     loc_18001FE75
0x18001ff44  bt      r9d, 1Eh
0x18001ff49  jnb     loc_180020021
0x18001ff4f  mov     rdx, [rsp+218h+lpMem]
0x18001ff57  mov     r8d, [rdx+68h]
0x18001ff5b  mov     r10d, r8d
0x18001ff5e  shr     r10d, 2
0x18001ff62  and     r10d, 3FFFh
0x18001ff69  mov     [rsp+218h+var_18C], r10d
0x18001ff71  lea     eax, [r10-1]
0x18001ff75  cmp     eax, 13h
0x18001ff78  ja      loc_180020015
0x18001ff7e  shr     r8d, 10h
0x18001ff82  test    r8w, r8w
0x18001ff86  jz      short loc_18001FFCE
0x18001ff88  movzx   ecx, word ptr [rdx+68h]
0x18001ff8c  mov     r8d, [rdx+6Ch]
0x18001ff90  add     r8, rdx
0x18001ff93  add     r8, rcx; pszSrc
0x18001ff96  mov     [rdx+68h], ecx
0x18001ff99  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ff9d  inc     rax
0x18001ffa0  cmp     [r8+rax*2], di
0x18001ffa5  jnz     short loc_18001FF9D
0x18001ffa7  lea     rdx, [rax+rax]; cbDest
0x18001ffab  cmp     rdx, 50h ; 'P'
0x18001ffaf  ja      short loc_18001FF3A
0x18001ffb1  lea     rcx, [rsp+218h+pszDest]; pszDest
0x18001ffb9  call    StringCbCopyW
0x18001ffbe  mov     r9d, [rsp+218h+var_190]
0x18001ffc6  mov     r10d, [rsp+218h+var_18C]
0x18001ffce  mov     rdx, [rsp+218h+lpMem]
0x18001ffd6  mov     eax, [rdx+6Ch]
0x18001ffd9  add     rdx, rax
0x18001ffdc  mov     [rsp+218h+var_130], rdx
0x18001ffe4  mov     ecx, edi
0x18001ffe6  cmp     ecx, r10d
0x18001ffe9  jnb     short loc_18002001E
0x18001ffeb  mov     eax, ecx
0x18001ffed  mov     r8d, [rdx+rax*4]
0x18001fff1  lea     eax, [r8-1]
0x18001fff5  cmp     eax, 13h
0x18001fff8  ja      short loc_18001FFFF
0x18001fffa  add     ecx, r12d
0x18001fffd  jmp     short loc_18001FFE6
0x18001ffff  lea     rdx, aLineopenProxyI; "lineOpen(PROXY): inval proxy request ty"...
0x180020006  mov     ecx, 10002h
0x18002000b  call    TRACELogPrint
0x180020010  jmp     loc_18001FF3A
0x180020015  lea     rdx, aLineopenProxyI_0; "lineOpen(PROXY): inval proxy request ty"...
0x18002001c  jmp     short loc_180020006
0x18002001e  mov     r10, r13
0x180020021  mov     r8d, [rsp+218h+var_17C]
0x180020029  mov     [rsp+218h+var_170], r9d
0x180020031  test    r9b, 4
0x180020035  jz      short loc_18002008D
0x180020037  mov     r13d, [r10+24h]
0x18002003b  mov     [rsp+218h+var_15C], r13d
0x180020043  mov     eax, r8d
0x180020046  sub     eax, 10003h
0x18002004b  jz      short loc_180020067
0x18002004d  sub     eax, r12d
0x180020050  jz      short loc_180020060
0x180020052  cmp     eax, 0FFFCh
0x180020057  jz      short loc_180020060
0x180020059  mov     eax, 0FF0001h
0x18002005e  jmp     short loc_18002006C
0x180020060  mov     eax, 0FF8001h
0x180020065  jmp     short loc_18002006C
0x180020067  mov     eax, 0FFC001h
0x18002006c  test    r13d, r13d
0x18002006f  jz      short loc_18002007E
0x180020071  mov     [rsp+218h+var_174], r13d
0x180020079  test    r13d, eax
0x18002007c  jz      short loc_18002009E
0x18002007e  mov     esi, 8000002Fh
0x180020083  mov     r13, [rsp+218h+var_1A0]
  ... truncated ...
```
