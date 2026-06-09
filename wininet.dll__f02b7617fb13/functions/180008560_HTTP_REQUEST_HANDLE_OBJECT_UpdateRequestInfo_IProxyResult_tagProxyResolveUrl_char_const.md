# HTTP_REQUEST_HANDLE_OBJECT::UpdateRequestInfo(IProxyResult *,tagProxyResolveUrl *,char const *)

- ea: `0x180008560`
- end: `0x180009ce1`
- name: `?UpdateRequestInfo@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEAUIProxyResult@@PEAUtagProxyResolveUrl@@PEBD@Z`
- size: `6017`
- prototype: `unsigned int __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this, struct IProxyResult *, struct tagProxyResolveUrl *, const char *)`
- caller_count: `1`
- callee_count: `45`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180031150`

## callees

- `0x180008560`
- `0x180009cf0`
- `0x18000cd64`
- `0x18000d360`
- `0x1800100d0`
- `0x180012a40`
- `0x180016c48`
- `0x1800178dc`
- `0x180030588`
- `0x18003602c`
- `0x1800701d0`
- `0x1800c14f4`
- `0x1800c1c50`
- `0x1800ca050`
- `0x1800ca1b4`
- `0x1800ca2d0`
- `0x1800cccbc`
- `0x1800cd7a0`
- `0x1800da530`
- `0x1800dadac`
- `0x1800e3b34`
- `0x1800f20bc`
- `0x180114434`
- `0x180117e30`
- `0x180117f9c`
- `0x18011fcc8`
- `0x18012ae0c`
- `0x180136824`
- `0x180136c6c`
- `0x1801487c8`
- `0x18014a7a0`
- `0x18014a7e0`
- `0x18014b3b4`
- `0x180154882`
- `0x1801d4be8`
- `0x1801d7fb4`
- `0x1801e1790`
- `0x1801e2c8c`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e67a8`
- `0x1801e7d84`
- `0x1801e7e14`
- `0x1801e8ab4`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008897`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008897`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009999`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009999`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a97`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008631`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000869f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008754`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800087c2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008631`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000869f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008754`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800087c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e0a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180009047`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180009047`
- `ntdll!RtlNtStatusToDosError` at `0x1800090a5`
- `ntdll!RtlNtStatusToDosError` at `0x1800090a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008773`

## string_xrefs

- `0x180009159`: `no-cache`
- `0x180009354`: `no-cache`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::UpdateRequestInfo(
        HTTP_REQUEST_HANDLE_OBJECT *this,
        struct IProxyResult *a2,
        const WCHAR **a3,
        const char *a4)
{
  const char *v5; // r12
  const WCHAR *v7; // rax
  unsigned int v8; // r15d
  char *v9; // rsi
  CHAR *v10; // rbx
  CHAR *v11; // rdi
  __int64 v12; // r14
  signed int v13; // r15d
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  CHAR *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  signed int v20; // eax
  signed int LastError; // eax
  const WCHAR *v22; // rax
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  CHAR *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  CHAR *v29; // rbx
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rbx
  unsigned int v33; // eax
  int v34; // r9d
  char *v35; // rcx
  _QWORD *v36; // rax
  _DWORD *v37; // rdx
  unsigned int v38; // r15d
  unsigned __int8 *v39; // r8
  int v40; // edx
  unsigned __int8 v41; // al
  int v42; // edx
  __int64 v43; // r8
  int v44; // eax
  __int64 v45; // rcx
  __int64 v46; // r11
  int v47; // ecx
  char *v48; // r15
  unsigned int v49; // r9d
  __int64 *v50; // rdx
  unsigned int i; // r10d
  unsigned int v52; // eax
  char *v53; // r8
  int v54; // eax
  char *v55; // r15
  int v56; // ecx
  int v57; // eax
  unsigned int v58; // r15d
  int v59; // edx
  int v60; // ecx
  int v61; // r8d
  void *v62; // r8
  __int64 v63; // r9
  size_t v64; // rbx
  struct CServerInfo *v65; // rcx
  unsigned int v66; // edx
  unsigned int ServerInfo; // eax
  void *v68; // rcx
  CHttpHeaders *v70; // r12
  _QWORD *v71; // r14
  HTTP_REQUEST_HANDLE_OBJECT *v72; // rcx
  __int64 v73; // rbx
  unsigned int v74; // r10d
  __int64 v75; // rbx
  __int64 v76; // rcx
  int v77; // eax
  unsigned int v78; // ecx
  __int64 v79; // r8
  CHAR v80; // dl
  _QWORD *v81; // rbx
  unsigned int v82; // r12d
  _QWORD *v83; // rcx
  unsigned int v84; // edx
  _QWORD *v85; // r14
  __int64 v86; // rcx
  int v87; // eax
  signed int v88; // ebx
  __int64 v89; // r12
  __int64 v90; // r14
  ULONG v91; // eax
  unsigned int v92; // r14d
  int v93; // eax
  int v94; // ebx
  unsigned int v95; // ebx
  int v96; // eax
  unsigned int v97; // r9d
  __int64 v98; // rdx
  CHAR v99; // cl
  _QWORD *v100; // r14
  HTTP_REQUEST_HANDLE_OBJECT *v101; // rcx
  __int64 v102; // rbx
  _QWORD *v103; // rcx
  _QWORD *v104; // rax
  int v105; // eax
  int v106; // eax
  unsigned int v107; // eax
  unsigned int v108; // eax
  bool v109; // sf
  bool v110; // sf
  int v111; // eax
  int v112; // eax
  __int64 v113; // rcx
  int v114; // eax
  int v115; // edx
  int v116; // ecx
  int v117; // r8d
  const char *v118; // rax
  int v119; // r10d
  unsigned int AuthState; // eax
  void *v121; // [rsp+50h] [rbp-B0h]
  __int64 v122; // [rsp+50h] [rbp-B0h]
  int Sizea; // [rsp+58h] [rbp-A8h]
  unsigned int Size; // [rsp+58h] [rbp-A8h]
  unsigned int Size_4; // [rsp+5Ch] [rbp-A4h]
  unsigned int Size_4a; // [rsp+5Ch] [rbp-A4h]
  CHAR *lpMultiByteStr; // [rsp+60h] [rbp-A0h]
  CHAR *v128; // [rsp+60h] [rbp-A0h]
  const CHAR *v129; // [rsp+60h] [rbp-A0h]
  int cbMultiByte; // [rsp+70h] [rbp-90h]
  int v131; // [rsp+70h] [rbp-90h]
  int v132; // [rsp+70h] [rbp-90h]
  size_t v133; // [rsp+78h] [rbp-88h]
  size_t v134; // [rsp+78h] [rbp-88h]
  char *v135; // [rsp+78h] [rbp-88h]
  _QWORD *v136; // [rsp+78h] [rbp-88h]
  unsigned int v137[2]; // [rsp+80h] [rbp-80h] BYREF
  void *v138; // [rsp+88h] [rbp-78h] BYREF
  struct IProxyResult *v139; // [rsp+90h] [rbp-70h]
  unsigned int v140; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v141; // [rsp+9Ch] [rbp-64h] BYREF
  LPCWCH lpWideCharStr; // [rsp+A0h] [rbp-60h]
  __int16 v143[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v144; // [rsp+ACh] [rbp-54h] BYREF
  int v145; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  int v147; // [rsp+C0h] [rbp-40h] BYREF
  int v148[3]; // [rsp+C4h] [rbp-3Ch] BYREF
  char Src[272]; // [rsp+D0h] [rbp-30h] BYREF

  v139 = a2;
  v138 = a3;
  v5 = a4;
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_qsq(
      1025,
      64,
      (unsigned int)WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids,
      (_DWORD)a2,
      (__int64)a4,
      (__int64)a3);
  v7 = a3[1];
  pv = 0;
  v8 = 0;
  v144 = 0;
  v9 = 0;
  v143[0] = 0;
  v145 = 0;
  v10 = 0;
  v147 = 0;
  v11 = 0;
  v148[0] = 0;
  v137[0] = 0;
  lpWideCharStr = v7;
  lpMultiByteStr = 0;
  if ( !v7 )
    goto LABEL_96;
  v12 = -1;
  v13 = -2147024882;
  if ( GlobalSafeToAssumeUTF8 )
  {
    v14 = WideCharToMultiByte(0xFDE9u, 0, v7, -1, 0, 0, 0, 0);
    cbMultiByte = v14;
    if ( v14 )
    {
      v133 = v14;
      v17 = (CHAR *)CoTaskMemAlloc(v14);
      lpMultiByteStr = v17;
      if ( v17 )
      {
        memset_0(v17, 0, v133);
        if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
        {
          v20 = 0;
LABEL_9:
          v10 = lpMultiByteStr;
LABEL_13:
          v11 = v10;
          goto LABEL_14;
        }
        LastError = WxGetLastError(v19, v18);
        v110 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v110 = LastError < 0;
        }
        if ( !v110 )
          LastError = -2147418113;
        Sizea = LastError;
        CoTaskMemFree(lpMultiByteStr);
        v20 = Sizea;
        if ( Sizea >= 0 )
          goto LABEL_13;
      }
      else
      {
        v20 = -2147024882;
      }
    }
    else
    {
      v20 = WxGetLastError(v16, v15);
      v109 = v20 < 0;
      if ( v20 > 0 )
      {
        v20 = (unsigned __int16)v20 | 0x80070000;
        v109 = v20 < 0;
      }
      if ( !v109 )
        v20 = -2147418113;
    }
  }
  else
  {
    v20 = WxNewStringWtoACchCp<WxCoTaskAllocator>(v7);
    if ( v20 >= 0 )
      goto LABEL_9;
  }
LABEL_14:
  if ( v20 < 0 )
  {
    v8 = 0;
    goto LABEL_96;
  }
  v22 = (const WCHAR *)*((_QWORD *)v138 + 2);
  lpWideCharStr = v22;
  if ( !v22 )
  {
    v8 = 0;
    goto LABEL_96;
  }
  if ( GlobalSafeToAssumeUTF8 )
  {
    v23 = WideCharToMultiByte(0xFDE9u, 0, v22, -1, 0, 0, 0, 0);
    v131 = v23;
    if ( v23 )
    {
      v134 = v23;
      v26 = (CHAR *)CoTaskMemAlloc(v23);
      v128 = v26;
      if ( v26 )
      {
        memset_0(v26, 0, v134);
        if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, v128, v131, 0, 0) )
        {
          v29 = v128;
          v13 = 0;
LABEL_24:
          v9 = v29;
          goto LABEL_25;
        }
        v112 = WxGetLastError(v28, v27);
        v13 = v112;
        if ( v112 > 0 )
          v13 = (unsigned __int16)v112 | 0x80070000;
        if ( v13 >= 0 )
          v13 = -2147418113;
        CoTaskMemFree(v128);
      }
    }
    else
    {
      v111 = WxGetLastError(v25, v24);
      v13 = v111;
      if ( v111 > 0 )
        v13 = (unsigned __int16)v111 | 0x80070000;
      if ( v13 >= 0 )
        v13 = -2147418113;
    }
  }
  else
  {
    v29 = 0;
    v13 = WxNewStringWtoACchCp<WxCoTaskAllocator>(v22);
    if ( v13 >= 0 )
      goto LABEL_24;
  }
LABEL_25:
  if ( v13 < 0 )
  {
    v8 = 0;
    goto LABEL_96;
  }
  v30 = (*(__int64 (__fastcall **)(struct IProxyResult *, int *))(*(_QWORD *)v139 + 24LL))(v139, &v145);
  if ( v30 < 0 )
    goto LABEL_255;
  v31 = *(_QWORD *)v139;
  if ( !v145 )
  {
    v30 = (*(__int64 (__fastcall **)(struct IProxyResult *, int *, int *))(v31 + 32))(v139, &v147, v148);
    if ( v30 >= 0 )
      goto LABEL_29;
LABEL_255:
    v8 = WX_WIN32_FROM_HR((unsigned int)v30);
    goto LABEL_96;
  }
  v106 = (*(__int64 (__fastcall **)(struct IProxyResult *, int *, LPVOID *, __int16 *))(v31 + 48))(
           v139,
           &v144,
           &pv,
           v143);
  if ( v106 < 0 )
  {
    v8 = WX_WIN32_FROM_HR((unsigned int)v106);
    goto LABEL_96;
  }
  v8 = HostWCharToCharEx((LPCWSTR)pv, -1, (__int64)v137);
  if ( v8 )
    goto LABEL_96;
LABEL_29:
  if ( v144 == 8 )
  {
    if ( pv )
      WxCoTaskAllocator::Free(&pv);
    v147 = 1;
    v148[0] = 0;
  }
  if ( *((_DWORD *)this + 248) && (*((_DWORD *)this + 1319) & 0x200) == 0 && (!v145 || ((v144 - 4) & 0xFFFFFFFB) == 0) )
  {
    v8 = 12019;
    goto LABEL_96;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 3024));
  v32 = -1;
  if ( !v5 )
    v5 = v9;
  do
    ++v32;
  while ( v5[v32] );
  v33 = *((_DWORD *)this + 766);
  v132 = v33;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    v114 = MapHttpMethodType(v33);
    WPP_SF_ssdsd(v116, v115, v117, v114, (__int64)v5, v32, 0, 0);
    v33 = v132;
  }
  if ( *((_QWORD *)this + 371) )
  {
    if ( v33 == -1 )
    {
      v37 = (_DWORD *)((char *)this + 2888);
      v34 = *((_DWORD *)this + 722);
      v36 = (_QWORD *)((char *)this + 2880);
      v35 = (char *)*((_QWORD *)this + 360);
      Size_4 = v34;
      goto LABEL_41;
    }
    if ( v33 <= 0x1E )
    {
      _mm_lfence();
      v34 = dword_1801F1D50[6 * v33];
      Size_4 = v34;
      if ( v34 != -1 )
      {
        v35 = (&off_1801F1D58)[3 * (int)v33];
        v36 = (_QWORD *)((char *)this + 2880);
        v37 = (_DWORD *)((char *)this + 2888);
LABEL_41:
        v135 = v35;
        v129 = (const CHAR *)*((_QWORD *)this + 364);
        Size = *((_DWORD *)this + 730);
        *v36 = 0;
        v38 = 0;
        *v37 = 0;
        *((_DWORD *)this + 718) += -2 - *((_DWORD *)this + 744);
        *((_QWORD *)this + 362) = 0;
        *((_DWORD *)this + 726) = 0;
        *((_QWORD *)this + 364) = 0;
        *((_DWORD *)this + 730) = 0;
        v140 = 0;
        v141 = 0;
        if ( v35 )
        {
          v39 = (unsigned __int8 *)v35;
          v40 = v34;
          if ( v34 )
          {
            while ( 1 )
            {
              v41 = *v39;
              if ( *v39 != 9 && v41 != 32 )
                break;
              if ( !--v40 )
                goto LABEL_52;
              ++v39;
            }
            if ( v40 )
            {
              while ( v41 > 0x20u && v41 < 0x7Fu )
              {
                if ( !--v40 )
                  goto LABEL_52;
                v41 = *++v39;
              }
              while ( (unsigned int)IsLWS(*v39) )
              {
                v39 = (unsigned __int8 *)(v43 + 1);
                if ( v42 == 1 )
                  goto LABEL_52;
              }
              v38 = -2147024809;
            }
          }
        }
LABEL_52:
        v44 = WX_WIN32_FROM_HR(v38);
        v45 = (unsigned int)v44;
        if ( v44 > 0 )
          v45 = (unsigned __int16)v44 | 0x80070000;
        if ( (int)v45 < 0 )
          goto LABEL_68;
        v46 = *((_QWORD *)this + 358);
        v47 = 0;
        v48 = 0;
        v49 = v32 + Size_4 + Size + 2;
        LODWORD(lpWideCharStr) = v49;
        v121 = 0;
        v138 = 0;
        if ( v49 > *(_DWORD *)(v46 + 4) )
        {
          v47 = 1;
        }
        else
        {
          v50 = *(__int64 **)(v46 + 8);
          for ( i = 0; i < 0xA && v50 != (__int64 *)(v46 + 8); ++i )
          {
            v52 = *((_DWORD *)v50 + 4);
            if ( v52 >= v49 )
            {
              v53 = (char *)v50[3];
              *((_DWORD *)v50 + 4) = v52 - v49;
              v50[3] = (__int64)&v53[v49];
              if ( v53 )
              {
                v48 = v53;
                v138 = v53;
                goto LABEL_62;
              }
              break;
            }
            v50 = (__int64 *)*v50;
          }
          v47 = 1;
LABEL_62:
          v121 = v48;
        }
        if ( v47 )
        {
          v105 = WxFastHeapAllocator::CreateAllocationEntry((WxFastHeapAllocator *)v46, v49, &v138);
          v45 = (unsigned int)v105;
          if ( v105 < 0 )
          {
LABEL_68:
            v57 = WX_WIN32_FROM_HR(v45);
            v58 = v57;
            if ( v57 > 0 )
              v58 = (unsigned __int16)v57 | 0x80070000;
            goto LABEL_70;
          }
          v48 = (char *)v138;
          v121 = v138;
        }
        v54 = _ParseHttpVersion(v129, Size, &v140, &v141);
        LODWORD(v138) = v54;
        v45 = (unsigned int)v54;
        if ( v54 > 0 )
        {
          v45 = (unsigned __int16)v54 | 0x80070000;
          LODWORD(v138) = (unsigned __int16)v54 | 0x80070000;
        }
        if ( (int)v45 >= 0 )
        {
          memcpy_0(v48, v135, Size_4);
          v48[Size_4] = 32;
          v55 = &v48[Size_4 + 1];
          memcpy_0(v55, v5, (unsigned int)v32);
          v55[(unsigned int)v32] = 32;
          memcpy_0(&v55[(unsigned int)v32 + 1], v129, Size);
          v56 = (int)lpWideCharStr;
          *((_QWORD *)this + 364) = &v55[(unsigned int)v32 + 1];
          v12 = -1;
          *((_DWORD *)this + 744) = v56;
          *((_DWORD *)this + 722) = Size_4;
          *((_DWORD *)this + 718) += v56 + 2;
          v45 = (unsigned int)v138;
          *((_QWORD *)this + 360) = v121;
          *((_QWORD *)this + 371) = v121;
          *((_DWORD *)this + 739) = v140;
          *((_DWORD *)this + 740) = v141;
          *((_QWORD *)this + 362) = v55;
          *((_DWORD *)this + 726) = v32;
          *((_DWORD *)this + 730) = Size;
        }
        goto LABEL_68;
      }
    }
  }
  v58 = -2147024809;
LABEL_70:
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    v107 = WX_WIN32_FROM_HR(v58);
    WPP_SF_d(1025, 48, WPP_764547bcea91352f6757a10208e155bd_Traceguids, v107);
  }
  if ( !(unsigned int)WX_WIN32_FROM_HR(v58) )
    *((_DWORD *)this + 766) = v132;
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_dsddsd(v60, v59, v61, *((_DWORD *)this + 1323), *((_QWORD *)this + 660), *((_WORD *)this + 2644), -1, 0, 0);
  v62 = (void *)*((_QWORD *)this + 660);
  if ( v62 )
    HeapFree(g_hWxProcessHeap, 0, v62);
  *((_QWORD *)this + 660) = 0;
  *((_WORD *)this + 2644) = 0;
  *((_DWORD *)this + 1323) = -1;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    WPP_SF_d(1025, 27, WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, 0);
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qqq(
        1025,
        30,
        (unsigned int)WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids,
        (_DWORD)this,
        *((_QWORD *)this + 664),
        0);
  }
  v63 = *((_QWORD *)this + 664);
  if ( v63 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_q(1025, 31, WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, v63);
    v113 = *((_QWORD *)this + 664);
    if ( v113 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
      *((_QWORD *)this + 664) = 0;
    }
  }
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_(1025, 32, WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids);
  if ( *((_QWORD *)this + 122) && v11 )
  {
    do
      ++v12;
    while ( v11[v12] );
    v64 = (unsigned int)v12;
    if ( (unsigned int)v12 > 0x100 )
      v64 = 256;
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_sd(1032, 47, (unsigned int)WPP_ebf5ebc2fb2b37980c6e0149dcb01477_Traceguids, (_DWORD)v11, v12);
    v65 = (struct CServerInfo *)*((_QWORD *)this + 122);
    if ( v65 )
      ReleaseServerInfo(v65);
    memcpy_0(Src, v11, v64);
    if ( v64 >= 0x101 )
      _report_rangecheckfailure();
    v66 = *((_DWORD *)this + 161);
    Src[v64] = 0;
    ServerInfo = GetServerInfo(Src, v66, (struct CServerInfo **)this + 122);
    v8 = ServerInfo;
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_d(1032, 48, WPP_ebf5ebc2fb2b37980c6e0149dcb01477_Traceguids, ServerInfo);
    if ( v8 )
      goto LABEL_95;
  }
  v70 = (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280);
  if ( *((_DWORD *)this + 1288) )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_sd(1025, 82, (unsigned int)WPP_764547bcea91352f6757a10208e155bd_Traceguids, (unsigned int)"Connection", 23);
    v100 = (_QWORD *)((char *)this + 1656);
    v101 = (HTTP_REQUEST_HANDLE_OBJECT *)*((_QWORD *)this + 207);
    v102 = (__int64)v101 - 16;
    if ( v101 == (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1656) )
      v102 = 0;
    while ( v102 )
    {
      CHttpHeaders::_RemoveHeaderFromLists(
        (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
        (struct _HEADER_LIST_ENTRY *)v102);
      if ( *(_DWORD *)(v102 + 72) )
      {
        WxHeapFree<char>(v102 + 56);
        *(_DWORD *)(v102 + 64) = 0;
      }
      v102 = *v100 - 16LL;
      if ( (_QWORD *)*v100 == v100 )
        v102 = 0;
    }
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_(1025, 83, WPP_764547bcea91352f6757a10208e155bd_Traceguids);
    v74 = 69;
  }
  else
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_sd(
        1025,
        82,
        (unsigned int)WPP_764547bcea91352f6757a10208e155bd_Traceguids,
        (unsigned int)"Proxy-Connection",
        69);
    v71 = (_QWORD *)((char *)this + 2392);
    v72 = (HTTP_REQUEST_HANDLE_OBJECT *)*((_QWORD *)this + 299);
    v73 = (__int64)v72 - 16;
    if ( v72 == (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 2392) )
      v73 = 0;
    while ( v73 )
    {
      CHttpHeaders::_RemoveHeaderFromLists(
        (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
        (struct _HEADER_LIST_ENTRY *)v73);
      if ( *(_DWORD *)(v73 + 72) )
      {
        WxHeapFree<char>(v73 + 56);
        *(_DWORD *)(v73 + 64) = 0;
      }
      v73 = *v71 - 16LL;
      if ( (_QWORD *)*v71 == v71 )
        v73 = 0;
    }
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_(1025, 83, WPP_764547bcea91352f6757a10208e155bd_Traceguids);
    v74 = 23;
  }
  v75 = 16LL * v74;
  v76 = v74;
  Size_4a = v74;
  v122 = v74;
  if ( *(HTTP_REQUEST_HANDLE_OBJECT **)((char *)this + v75 + 1288) != (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + v75 + 1288) )
  {
    *((_DWORD *)this + 317) |= 0x400000u;
    *((_DWORD *)this + 1289) = 1;
  }
  v77 = *((_DWORD *)this + 317);
  v8 = 0;
  if ( GlobalDisableKeepAlive )
  {
    HTTP_REQUEST_HANDLE_OBJECT::RemoveAllRequestHeadersByName(this, 0x17u);
    HTTP_REQUEST_HANDLE_OBJECT::RemoveAllRequestHeadersByName(this, 0x45u);
    if ( (unsigned int)HTTP_REQUEST_HANDLE_OBJECT::IsRequestHttp1_1(this) )
      CHttpHeaders::ReplaceHeaderByIndex(
        (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
        0x17u,
        "Close",
        5u,
        0,
        0x20000000u);
    *((_DWORD *)this + 317) &= ~0x400000u;
    v77 = *((_DWORD *)this + 317);
    v74 = Size_4a;
    v76 = v122;
  }
  if ( (v77 & 0x400000) != 0 )
  {
    *((_DWORD *)this + 1289) = 1;
    v78 = 10;
    do
    {
      v79 = v78 - 1;
      v80 = aKeepAlive[v79];
      if ( v80 != 9 && v80 != 32 )
        break;
      --v78;
    }
    while ( (_DWORD)v79 );
    CHttpHeaders::_ReplaceHeader(
      (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
      v74,
      0,
      0,
      "Keep-Alive",
      v78,
      0,
      0x10000000u);
    v74 = Size_4a;
    v76 = v122;
  }
  if ( *((_DWORD *)this + 739) <= 1u && (*((_DWORD *)this + 739) != 1 || !*((_DWORD *)this + 740)) )
    goto LABEL_168;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    v118 = InternetMapHttpOption(v74);
    WPP_SF_ds(1025, 68, (unsigned int)WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids, v119, (__int64)v118);
    v76 = v122;
  }
  v137[0] = 0;
  v81 = (_QWORD *)((char *)this + v75 + 1288);
  v82 = 0;
  v136 = v81;
  while ( 1 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_sd(
        1025,
        43,
        (unsigned int)WPP_764547bcea91352f6757a10208e155bd_Traceguids,
        *((_QWORD *)&GlobalKnownHeaders + 3 * v76),
        v82);
    v83 = (_QWORD *)*v81;
    v84 = v82;
    HIDWORD(v139) = 0;
    v85 = v83 - 2;
    if ( v83 == v81 )
      v85 = 0;
    if ( v82 )
    {
      while ( v85 )
      {
        v103 = (_QWORD *)v85[2];
        v104 = 0;
        if ( v103 != v81 )
          v104 = v103 - 2;
        v85 = v104;
        if ( !--v84 )
          goto LABEL_137;
      }
    }
    else
    {
LABEL_137:
      if ( v85 )
        goto LABEL_139;
    }
    HIDWORD(v139) = 2854;
LABEL_139:
    v86 = 2148282230LL;
    if ( v85 )
      v86 = 0;
    v87 = WX_WIN32_FROM_HR(v86);
    v88 = v87;
    if ( v87 > 0 )
      v88 = (unsigned __int16)v87 | 0x80070000;
    if ( v88 < 0 )
    {
      HIDWORD(v139) = 4850;
      v89 = 16;
      v90 = 24;
    }
    else
    {
      v89 = (__int64)(v85 + 7);
      v90 = (__int64)(v85 + 8);
    }
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      v108 = WX_WIN32_FROM_HR((unsigned int)v88);
      WPP_SF_d(1025, 44, WPP_764547bcea91352f6757a10208e155bd_Traceguids, v108);
    }
    if ( (v88 & 0x1FFF0000) == 0xC0000 )
    {
      v88 = (unsigned __int16)v88;
    }
    else
    {
      if ( v88 >= 0 )
        goto LABEL_149;
      if ( (v88 & 0x1FFF0000) == 0x70000
        || (v88 & 0x10000000) != 0 && (v91 = RtlNtStatusToDosError(v88 & 0xEFFFFFFF)) != 0 && v91 != 317 )
      {
LABEL_161:
        v92 = 0;
        v93 = 1;
        goto LABEL_162;
      }
    }
    if ( v88 )
      goto LABEL_161;
LABEL_149:
    if ( *(_DWORD *)v90 == 5 && !StrCmpNICA(*(LPCSTR *)v89, "Close", 5) )
      break;
    v81 = v136;
    v82 = v137[0] + 1;
    v76 = v122;
    ++v137[0];
  }
  v93 = 1;
  v92 = 1;
LABEL_162:
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    WPP_SF_d(1025, 69, WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids, v92);
    v93 = 1;
  }
  v94 = *((_DWORD *)this + 317);
  if ( v92 || (*((_DWORD *)this + 1319) & 0x200) != 0 )
  {
    HTTP_REQUEST_HANDLE_OBJECT::RemoveAllRequestHeadersByName(this, Size_4a);
    if ( (*((_DWORD *)this + 1319) & 0x200) != 0
      || HTTP_REQUEST_HANDLE_OBJECT::GetAuthState(this) && HTTP_REQUEST_HANDLE_OBJECT::GetAuthState(this) != 1 )
    {
      if ( (xmmword_180266B60 & 2) != 0 )
      {
        AuthState = HTTP_REQUEST_HANDLE_OBJECT::GetAuthState(this);
        WPP_SF_d(1025, 66, WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids, AuthState);
      }
      *((_DWORD *)this + 310) = 1;
      v70 = (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280);
    }
    else
    {
      v70 = (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280);
      CHttpHeaders::ReplaceHeaderByIndex(
        (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
        Size_4a,
        "Close",
        5u,
        0,
        0x20000000u);
    }
    v93 = 0;
    v95 = v94 & 0xFFBFFFFF;
  }
  else
  {
    v95 = v94 | 0x400000;
    v70 = (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280);
  }
  *((_DWORD *)this + 1289) = v93;
  *((_DWORD *)this + 317) = v95;
LABEL_168:
  v96 = *((_DWORD *)this + 191);
  if ( *((_DWORD *)this + 766) == 2 && !*((_QWORD *)this + 86) )
    v96 |= 0x80000000;
  if ( (v96 & 0x80000100) != 0 )
  {
    if ( *((_DWORD *)this + 1288) )
      goto LABEL_204;
    if ( (v96 & 0x800) != 0 )
      goto LABEL_95;
    if ( !GlobalEnableHttp1_1 )
    {
LABEL_204:
      CHttpHeaders::ReplaceHeaderByIndex(v70, 0x11u, "no-cache", 8u, 0, 0x10000000u);
    }
    else
    {
      v97 = 8;
      do
      {
        v98 = v97 - 1;
        v99 = aNoCache[v98];
        if ( v99 != 9 && v99 != 32 )
          break;
        --v97;
      }
      while ( (_DWORD)v98 );
      CHttpHeaders::_ReplaceHeader(v70, 0x31u, 0, 0, "no-cache", v97, 0, 0x10000000u);
    }
  }
LABEL_95:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 3024));
LABEL_96:
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_d(1025, 67, WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids, v8);
  v68 = pv;
  if ( pv )
  {
    pv = 0;
    CoTaskMemFree(v68);
  }
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v11 )
    CoTaskMemFree(v11);
  return v8;
}

```

## disassembly

```asm
0x180008560  push    rbp
0x180008562  push    rbx
0x180008563  push    rsi
0x180008564  push    rdi
0x180008565  push    r12
0x180008567  push    r13
0x180008569  push    r14
0x18000856b  push    r15
0x18000856d  lea     rbp, [rsp-0F8h]
0x180008575  sub     rsp, 1F8h
0x18000857c  mov     rax, cs:__security_cookie
0x180008583  xor     rax, rsp
0x180008586  mov     [rbp+130h+var_50], rax
0x18000858d  mov     rbx, r8
0x180008590  mov     [rbp+130h+var_1A0], rdx
0x180008594  mov     [rbp+130h+var_1A8], rbx
0x180008598  mov     r12, r9
0x18000859b  mov     rax, rdx
0x18000859e  mov     r13, rcx
0x1800085a1  test    byte ptr cs:xmmword_180266B60, 2
0x1800085a8  jnz     loc_1800097F9
0x1800085ae  mov     rax, [rbx+8]
0x1800085b2  xor     edx, edx; dwFlags
0x1800085b4  mov     [rbp+130h+pv], rdx
0x1800085b8  mov     r15d, edx
0x1800085bb  mov     [rbp+130h+var_184], edx
0x1800085be  mov     esi, edx
0x1800085c0  mov     [rbp+130h+var_188], dx
0x1800085c4  mov     r14d, edx
0x1800085c7  mov     [rbp+130h+var_180], edx
0x1800085ca  mov     ebx, edx
0x1800085cc  mov     [rbp+130h+var_170], edx
0x1800085cf  mov     edi, edx
0x1800085d1  mov     [rbp+130h+var_16C], edx
0x1800085d4  mov     [rsp+230h+var_1DC], edx
0x1800085d8  mov     dword ptr [rsp+230h+Size+4], edx
0x1800085dc  mov     [rsp+230h+hMem], rdx
0x1800085e1  mov     [rbp+130h+var_1B0], edx
0x1800085e4  mov     [rbp+130h+lpWideCharStr], rax
0x1800085e8  mov     [rsp+60h], rdx
0x1800085ed  test    rax, rax
0x1800085f0  jz      loc_180009821
0x1800085f6  cmp     cs:GlobalSafeToAssumeUTF8, edx
0x1800085fc  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180008603  mov     r15d, 8007000Eh
0x180008609  jz      loc_180009406
0x18000860f  mov     [rsp+230h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x180008614  mov     r9d, r14d; cchWideChar
0x180008617  mov     [rsp+230h+lpDefaultChar], rdx; lpDefaultChar
0x18000861c  mov     r8, rax; lpWideCharStr
0x18000861f  mov     [rsp+230h+cbMultiByte], edx; cbMultiByte
0x180008623  mov     ecx, 0FDE9h; CodePage
0x180008628  mov     [rsp+230h+lpMultiByteStr], rdx; lpMultiByteStr
0x18000862d  mov     [rsp+230h+var_1DC], edx
0x180008631  call    cs:__imp_WideCharToMultiByte
0x180008637  mov     [rsp+230h+var_1C0], eax
0x18000863b  test    eax, eax
0x18000863d  jz      loc_1800096F7
0x180008643  mov     eax, eax
0x180008645  mov     ecx, eax; cb
0x180008647  mov     [rsp+230h+var_1B4], ebx
0x18000864b  mov     [rsp+78h], rax
0x180008650  call    cs:__imp_CoTaskMemAlloc
0x180008656  mov     [rsp+60h], rax
0x18000865b  test    rax, rax
0x18000865e  jz      loc_180009247
0x180008664  mov     r8, [rsp+78h]; Size
0x180008669  xor     edx, edx; Val
0x18000866b  mov     rcx, rax; void *
0x18000866e  call    memset_0
0x180008673  mov     r8, [rbp+130h+lpWideCharStr]; lpWideCharStr
0x180008677  xor     eax, eax
0x180008679  mov     [rsp+230h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18000867e  mov     r9d, r14d; cchWideChar
0x180008681  mov     [rsp+230h+lpDefaultChar], rax; lpDefaultChar
0x180008686  xor     edx, edx; dwFlags
0x180008688  mov     eax, [rsp+230h+var_1C0]
0x18000868c  mov     ecx, 0FDE9h; CodePage
0x180008691  mov     [rsp+230h+cbMultiByte], eax; cbMultiByte
0x180008695  mov     rax, [rsp+60h]
0x18000869a  mov     [rsp+230h+lpMultiByteStr], rax; lpMultiByteStr
0x18000869f  call    cs:__imp_WideCharToMultiByte
0x1800086a5  test    eax, eax
0x1800086a7  jz      loc_18000972B
0x1800086ad  xor     eax, eax
0x1800086af  mov     dword ptr [rsp+230h+Size], eax
0x1800086b3  mov     rbx, [rsp+60h]
0x1800086b8  jmp     short loc_1800086E5
0x1800086ba  mov     ecx, 8000FFFFh
0x1800086bf  mov     [rsp+230h+var_1DC], 15Ch
0x1800086c7  cmovns  eax, ecx
0x1800086ca  mov     rcx, [rsp+60h]; pv
0x1800086cf  mov     dword ptr [rsp+230h+Size], eax
0x1800086d3  call    cs:__imp_CoTaskMemFree
0x1800086d9  mov     eax, dword ptr [rsp+230h+Size]
0x1800086dd  test    eax, eax
0x1800086df  js      loc_18000925E
0x1800086e5  mov     rdi, rbx
0x1800086e8  xor     ebx, ebx
0x1800086ea  test    rbx, rbx
0x1800086ed  jz      short loc_1800086FC
0x1800086ef  mov     rcx, rbx; pv
0x1800086f2  call    cs:__imp_CoTaskMemFree
0x1800086f8  mov     eax, dword ptr [rsp+230h+Size]
0x1800086fc  xor     edx, edx; dwFlags
0x1800086fe  test    eax, eax
0x180008700  js      loc_18000923F
0x180008706  mov     rax, [rbp+130h+var_1A8]
0x18000870a  mov     ebx, edx
0x18000870c  mov     [rsp+60h], rdx
0x180008711  mov     rax, [rax+10h]
0x180008715  mov     [rbp+130h+lpWideCharStr], rax
0x180008719  mov     [rsp+230h+var_1DC], edx
0x18000871d  test    rax, rax
0x180008720  jz      loc_18000982E
0x180008726  cmp     cs:GlobalSafeToAssumeUTF8, edx
0x18000872c  jz      loc_180009434
0x180008732  mov     [rsp+230h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x180008737  mov     r9d, r14d; cchWideChar
0x18000873a  mov     [rsp+230h+lpDefaultChar], rdx; lpDefaultChar
0x18000873f  mov     r8, rax; lpWideCharStr
0x180008742  mov     [rsp+230h+cbMultiByte], edx; cbMultiByte
0x180008746  mov     ecx, 0FDE9h; CodePage
0x18000874b  mov     [rsp+230h+lpMultiByteStr], rdx; lpMultiByteStr
0x180008750  mov     [rsp+230h+var_1DC], edx
0x180008754  call    cs:__imp_WideCharToMultiByte
0x18000875a  mov     [rsp+230h+var_1C0], eax
0x18000875e  test    eax, eax
0x180008760  jz      loc_180009747
0x180008766  mov     eax, eax
0x180008768  mov     ecx, eax; cb
0x18000876a  mov     [rsp+230h+var_1B4], ebx
0x18000876e  mov     [rsp+78h], rax
0x180008773  call    cs:__imp_CoTaskMemAlloc
0x180008779  mov     [rsp+60h], rax
0x18000877e  test    rax, rax
0x180008781  jz      loc_18000926B
0x180008787  mov     r8, [rsp+78h]; Size
0x18000878c  xor     edx, edx; Val
0x18000878e  mov     rcx, rax; void *
0x180008791  call    memset_0
0x180008796  mov     r15, [rsp+60h]
0x18000879b  xor     eax, eax
0x18000879d  mov     r8, [rbp+130h+lpWideCharStr]; lpWideCharStr
0x1800087a1  mov     r9d, r14d; cchWideChar
0x1800087a4  mov     [rsp+230h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800087a9  xor     edx, edx; dwFlags
0x1800087ab  mov     [rsp+230h+lpDefaultChar], rax; lpDefaultChar
0x1800087b0  mov     ecx, 0FDE9h; CodePage
0x1800087b5  mov     eax, [rsp+230h+var_1C0]
0x1800087b9  mov     [rsp+230h+cbMultiByte], eax; cbMultiByte
0x1800087bd  mov     [rsp+230h+lpMultiByteStr], r15; lpMultiByteStr
0x1800087c2  call    cs:__imp_WideCharToMultiByte
0x1800087c8  test    eax, eax
0x1800087ca  jz      loc_18000977F
0x1800087d0  mov     rbx, r15
0x1800087d3  xor     r15d, r15d
0x1800087d6  jmp     short loc_180008800
0x1800087d8  mov     rcx, [rsp+60h]; pv
0x1800087dd  test    r15d, r15d
0x1800087e0  mov     eax, 8000FFFFh
0x1800087e5  mov     [rsp+230h+var_1DC], 15Ch
0x1800087ed  cmovns  r15d, eax
0x1800087f1  call    cs:__imp_CoTaskMemFree
0x1800087f7  test    r15d, r15d
0x1800087fa  js      loc_18000927B
0x180008800  mov     rsi, rbx
0x180008803  xor     ebx, ebx
0x180008805  test    rbx, rbx
0x180008808  jnz     loc_1800089F7
0x18000880e  test    r15d, r15d
0x180008811  js      loc_180009CB7
0x180008817  mov     rbx, [rbp+130h+var_1A0]
0x18000881b  lea     rdx, [rbp+130h+var_180]
0x18000881f  mov     rcx, rbx
0x180008822  mov     rax, [rbx]
0x180008825  mov     rax, [rax+18h]
0x180008829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882e  test    eax, eax
0x180008830  js      loc_18000983E
0x180008836  cmp     [rbp+130h+var_180], 0
0x18000883a  mov     r15d, 1
0x180008840  mov     rax, [rbx]
0x180008843  mov     rcx, rbx
0x180008846  jnz     loc_180009515
0x18000884c  mov     rax, [rax+20h]
0x180008850  lea     r8, [rbp+130h+var_16C]
0x180008854  lea     rdx, [rbp+130h+var_170]
0x180008858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885d  test    eax, eax
0x18000885f  js      loc_18000985C
0x180008865  cmp     [rbp+130h+var_184], 8
0x180008869  mov     rbx, [rsp+230h+hMem]
0x18000886e  jz      loc_18000979F
0x180008874  xor     edx, edx
0x180008876  cmp     dword ptr [r13+3E0h], 0
0x18000887e  jnz     loc_18000986B
0x180008884  lea     rcx, [r13+0BD0h]; lpCriticalSection
0x18000888b  mov     [rsp+60h], rdx
0x180008890  mov     r15, rdx
0x180008893  mov     dword ptr [rsp+230h+Size], edx
0x180008897  call    cs:__imp_EnterCriticalSection
0x18000889d  test    rbx, rbx
0x1800088a0  jnz     loc_180009881
0x1800088a6  test    r12, r12
0x1800088a9  mov     rbx, r14
0x1800088ac  cmovz   r12, rsi
0x1800088b0  inc     rbx
0x1800088b3  cmp     byte ptr [r12+rbx], 0
0x1800088b8  jnz     short loc_1800088B0
0x1800088ba  mov     eax, [r13+0BF8h]
0x1800088c1  mov     [rsp+230h+var_1C0], eax
0x1800088c5  test    byte ptr cs:xmmword_180266B60, 2
0x1800088cc  jnz     loc_1800098CE
0x1800088d2  xor     r10d, r10d
0x1800088d5  lea     rdx, __ImageBase
0x1800088dc  mov     [rsp+230h+var_1DC], r10d
0x1800088e1  cmp     [r13+0B98h], r10
0x1800088e8  jz      loc_18000907F
0x1800088ee  cmp     eax, r14d
0x1800088f1  jz      loc_18000932E
0x1800088f7  cmp     eax, 1Eh
0x1800088fa  ja      loc_1800092DC
0x180008900  lfence
0x180008903  cdqe
0x180008905  lea     rcx, [rax+rax*2]
0x180008909  mov     r9d, ds:rva dword_1801F1D50[rdx+rcx*8]
0x180008911  mov     dword ptr [rsp+230h+Size+4], r9d
0x180008916  cmp     r9d, 0FFFFFFFFh
0x18000891a  jz      loc_1800092DC
0x180008920  mov     rcx, ds:rva off_1801F1D58[rdx+rcx*8]; "GET" ...
0x180008928  lea     rax, [r13+0B40h]
0x18000892f  lea     rdx, [r13+0B48h]
0x180008936  mov     [rsp+78h], rcx
0x18000893b  test    r15, r15
0x18000893e  jnz     short loc_180008958
0x180008940  mov     r8, [r13+0B60h]
0x180008947  mov     [rsp+60h], r8
0x18000894c  mov     r8d, [r13+0B68h]
0x180008953  mov     dword ptr [rsp+230h+Size], r8d
0x180008958  mov     [rax], r10
0x18000895b  mov     r15d, r10d
0x18000895e  mov     [rdx], r10d
0x180008961  mov     eax, 0FFFFFFFEh
0x180008966  sub     eax, [r13+0BA0h]
0x18000896d  add     [r13+0B38h], eax
0x180008974  mov     [r13+0B50h], r10
0x18000897b  mov     [r13+0B58h], r10d
0x180008982  mov     [r13+0B60h], r10
0x180008989  mov     [r13+0B68h], r10d
0x180008990  mov     [rsp+230h+var_1DC], r10d
0x180008995  mov     [rbp+130h+var_198], r10d
0x180008999  mov     [rbp+130h+var_194], r10d
0x18000899d  mov     [rsp+230h+var_1DC], r10d
0x1800089a2  test    rcx, rcx
0x1800089a5  jz      short loc_180008A0E
0x1800089a7  mov     r8, rcx
0x1800089aa  mov     edx, r9d
0x1800089ad  test    r9d, r9d
0x1800089b0  jz      short loc_180008A0E
0x1800089b2  movzx   eax, byte ptr [r8]
0x1800089b6  cmp     al, 9
0x1800089b8  jz      loc_180008E12
0x1800089be  cmp     al, 20h ; ' '
0x1800089c0  jz      loc_180008E12
0x1800089c6  test    edx, edx
0x1800089c8  jz      short loc_180008A0E
0x1800089ca  nop     word ptr [rax+rax+00h]
0x1800089d0  cmp     al, 20h ; ' '
0x1800089d2  jbe     short loc_1800089DC
0x1800089d4  cmp     al, 7Fh
0x1800089d6  jb      short loc_180008A05
0x1800089d8  test    edx, edx
0x1800089da  jz      short loc_180008A0E
0x1800089dc  movzx   ecx, byte ptr [r8]; unsigned __int8
0x1800089e0  call    ?IsLWS@@YAHE@Z; IsLWS(uchar)
0x1800089e5  test    eax, eax
0x1800089e7  jz      loc_1800098FC
0x1800089ed  inc     r8
0x1800089f0  add     edx, 0FFFFFFFFh
0x1800089f3  jnz     short loc_1800089DC
0x1800089f5  jmp     short loc_180008A0E
0x1800089f7  mov     rcx, rbx; pv
0x1800089fa  call    cs:__imp_CoTaskMemFree
0x180008a00  jmp     loc_18000880E
0x180008a05  add     edx, 0FFFFFFFFh
0x180008a08  jnz     loc_180009072
0x180008a0e  mov     ecx, r15d
0x180008a11  call    WX_WIN32_FROM_HR
0x180008a16  mov     ecx, eax
0x180008a18  test    eax, eax
0x180008a1a  jle     short loc_180008A25
0x180008a1c  movzx   ecx, ax
0x180008a1f  or      ecx, 80070000h
0x180008a25  test    ecx, ecx
0x180008a27  js      loc_180009378
0x180008a2d  mov     r11, [r13+0B30h]
0x180008a34  xor     eax, eax
0x180008a36  mov     r9d, dword ptr [rsp+230h+Size]
0x180008a3b  mov     ecx, eax
  ... truncated ...
```
