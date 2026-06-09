# CKnownFoldersFolder::_EnumFolders(int,ulong,CDPA<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>> *,CDPA<ushort,CTContainer_PolicyUnOwned<ushort>> *)

- ea: `0x180052490`
- end: `0x1800530ea`
- name: `?_EnumFolders@CKnownFoldersFolder@@IEAAJHKPEAV?$CDPA@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@PEAV?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@@Z`
- size: `3162`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800cce50`
- `0x1802241f0`
- `0x180261bc0`
- `0x1802e1fc0`

## callees

- `0x18000d6cc`
- `0x1800432f0`
- `0x180051110`
- `0x180052490`
- `0x1800530f0`
- `0x18005325c`
- `0x1800533b4`
- `0x18009c6c0`
- `0x18009c960`
- `0x18012c710`
- `0x18012c8b0`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x1803a96f1`
- `0x180628884`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005250f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005254d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005250f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005254d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800524f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052536`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800524f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052536`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18005292d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18005292d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180052fb8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180052fb8`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800525a1`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800525a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052e75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052e75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005270b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005271f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005276d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052d84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052ed9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005270b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005271f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005276d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052d84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052ed9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800528a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052a8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052ba9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052bb4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052ca2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052cad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800528a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052a8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052ba9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052bb4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052ca2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052cad`
- `PROPSYS!PropVariantToGUID` at `0x1800529ec`
- `PROPSYS!PropVariantToGUID` at `0x1800529ec`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18005303f`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18005303f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CKnownFoldersFolder::_EnumFolders(
        void **a1,
        int a2,
        unsigned int a3,
        struct _DPA **a4,
        struct _DPA **a5)
{
  char v5; // r14
  void **v6; // r13
  __int64 v7; // r15
  struct _DPA *v8; // r12
  struct _DPA *v9; // rbx
  HANDLE ProcessHeap; // rsi
  struct _DPA *v11; // rax
  struct _DPA *v12; // rdi
  HANDLE v13; // rsi
  struct _DPA *v14; // rax
  HRESULT Instance; // r14d
  char *v16; // rdx
  unsigned int v17; // eax
  struct _DPA *v18; // r15
  unsigned int v19; // esi
  __int64 v20; // r12
  int v21; // eax
  int v22; // eax
  char *v23; // rax
  int v24; // r14d
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rdi
  int v27; // eax
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 *); // r14
  int v29; // eax
  char v30; // r13
  __int64 v31; // r8
  __int64 v32; // rcx
  bool v33; // zf
  struct _DPA *v34; // r14
  int ShouldAllowAccessToKnownFolder; // eax
  const WCHAR *FileNameW; // rax
  __int16 v37; // r14
  wchar_t *v38; // r15
  wchar_t *v39; // rcx
  HRESULT v40; // eax
  void *v41; // r15
  __int64 (__fastcall *v42)(void *, GUID *, __int64 *); // r14
  int v43; // eax
  bool v44; // di
  __int64 v45; // rcx
  struct _DPA *v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  int v50; // eax
  const WCHAR *v51; // rdi
  int v52; // r15d
  int i; // r14d
  HDPA v54; // r15
  unsigned int v55; // eax
  int v56; // r13d
  unsigned int v57; // edx
  int v58; // eax
  LPCWSTR v59; // rdi
  __int128 *v60; // r14
  void *v61; // r15
  void **v62; // r12
  int v63; // edi
  __int128 v64; // xmm6
  void *v65; // r14
  unsigned int v66; // eax
  __int64 v67; // r12
  __int16 v68; // r15
  void *v69; // rax
  __int64 v70; // r14
  __int64 (__fastcall ***v71)(_QWORD, GUID *, _QWORD *); // rcx
  struct _DPA *v72; // rdi
  int ppv; // [rsp+20h] [rbp-E0h]
  HRESULT v74; // [rsp+30h] [rbp-D0h]
  HRESULT v75; // [rsp+30h] [rbp-D0h]
  HRESULT v76; // [rsp+30h] [rbp-D0h]
  char v77[4]; // [rsp+34h] [rbp-CCh] BYREF
  HDPA hdpa; // [rsp+38h] [rbp-C8h]
  HDPA v79; // [rsp+40h] [rbp-C0h]
  void **v80; // [rsp+48h] [rbp-B8h]
  unsigned int v81; // [rsp+50h] [rbp-B0h]
  int v82; // [rsp+54h] [rbp-ACh]
  struct _DPA *v83; // [rsp+58h] [rbp-A8h]
  struct _DPA *v84; // [rsp+60h] [rbp-A0h]
  struct _DPA **v85; // [rsp+68h] [rbp-98h]
  struct _DPA *v86; // [rsp+70h] [rbp-90h]
  struct _DPA **v87; // [rsp+78h] [rbp-88h]
  LPCWSTR lpString2; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v89; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v90)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-70h] BYREF
  __int64 (__fastcall ***v91)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-68h] BYREF
  __int64 v92; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v93; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID Src; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v95; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int Size; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int Size_4; // [rsp+C4h] [rbp-3Ch] BYREF
  __int64 v98; // [rsp+C8h] [rbp-38h] BYREF
  PROPVARIANT pvar; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+D8h] [rbp-28h]
  GUID pguid; // [rsp+E8h] [rbp-18h] BYREF
  PROPVARIANT propvar[3]; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID pv[2]; // [rsp+110h] [rbp+10h] BYREF
  LPVOID v104[2]; // [rsp+120h] [rbp+20h]
  LPCWSTR pszPath[2]; // [rsp+130h] [rbp+30h]
  LPVOID v106[2]; // [rsp+140h] [rbp+40h]
  LPVOID v107[2]; // [rsp+150h] [rbp+50h]
  LPVOID v108[2]; // [rsp+160h] [rbp+60h]
  __int128 v109; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v87 = a4;
  v5 = a3;
  v81 = a3;
  v82 = a2;
  v6 = a1;
  v80 = a1;
  v7 = (__int64)a5;
  v85 = a5;
  v8 = 0;
  v9 = 0;
  v84 = 0;
  ProcessHeap = GetProcessHeap();
  v11 = (struct _DPA *)HeapAlloc(ProcessHeap, 8u, 0x20u);
  v12 = v11;
  v86 = v11;
  if ( !v11 )
  {
    v12 = 0;
    v83 = 0;
    Instance = -2147024882;
    goto LABEL_71;
  }
  *((_DWORD *)v11 + 7) = 16;
  *((_QWORD *)v11 + 2) = ProcessHeap;
  v83 = v11;
  v13 = GetProcessHeap();
  v14 = (struct _DPA *)HeapAlloc(v13, 8u, 0x20u);
  v9 = v14;
  if ( !v14 )
  {
    v9 = 0;
    v84 = 0;
    Instance = -2147024882;
LABEL_85:
    v8 = v12;
    goto LABEL_71;
  }
  *((_DWORD *)v14 + 7) = 16;
  *((_QWORD *)v14 + 2) = v13;
  v84 = v14;
  if ( (v5 & 0x20) == 0 )
  {
    Instance = 0;
    v8 = v12;
    v18 = v14;
    goto LABEL_29;
  }
  v92 = 0;
  if ( v6[37]
    || (Instance = SHCoCreateInstance(
                     0,
                     &CLSID_KnownFolderManager,
                     0,
                     &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
                     v6 + 37),
        Instance >= 0) )
  {
    Instance = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v6[37])(
                 v6[37],
                 &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
                 &v92);
  }
  if ( Instance < 0 )
    goto LABEL_85;
  Size_4 = 0;
  v89 = 0;
  v16 = (char *)v6[43];
  if ( v16 )
  {
    v17 = *((_DWORD *)v6 + 88);
    Size_4 = v17;
    v89 = v16;
  }
  else
  {
    Instance = (*(__int64 (__fastcall **)(__int64, LPVOID *, unsigned int *))(*(_QWORD *)v92 + 40LL))(
                 v92,
                 &v89,
                 &Size_4);
    if ( Instance < 0 )
    {
      v8 = v12;
      v18 = v9;
      goto LABEL_28;
    }
    v17 = Size_4;
    v16 = (char *)v89;
  }
  v18 = v9;
  if ( !v17 )
  {
    v8 = v12;
    goto LABEL_26;
  }
  v19 = 0;
  hdpa = v9;
  v79 = v12;
  do
  {
    v90 = 0;
    v20 = 16LL * v19;
    v21 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD *))(*(_QWORD *)v92 + 48LL))(v92, &v16[v20], &v90);
    v74 = v21;
    if ( v21 >= 0 )
    {
      *(_OWORD *)pv = 0;
      *(_OWORD *)v104 = 0;
      *(_OWORD *)pszPath = 0;
      *(_OWORD *)v106 = 0;
      *(_OWORD *)v107 = 0;
      *(_OWORD *)v108 = 0;
      v109 = 0;
      v22 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), LPVOID *))(*v90)[11])(v90, pv);
      if ( v22 < 0 )
      {
        if ( v22 != -2147467263 )
          goto LABEL_22;
      }
      else
      {
        if ( (v81 & 0x80u) == 0 && ((__int64)v108[1] & 2) != 0 )
          goto LABEL_20;
        v23 = (char *)((char *)v104[1] - (char *)v6[29]);
        if ( v104[1] == v6[29] )
          v23 = (char *)((char *)pszPath[0] - (char *)v6[30]);
        if ( v23 || !pszPath[1] || (FileNameW = PathFindFileNameW(pszPath[1]), pszPath[1] != FileNameW) )
LABEL_20:
          v24 = 0;
        else
          v24 = 1;
        CoTaskMemFree(pv[1]);
        CoTaskMemFree(v104[0]);
        CoTaskMemFree((LPVOID)pszPath[1]);
        CoTaskMemFree(v106[0]);
        CoTaskMemFree(v106[1]);
        CoTaskMemFree(v107[0]);
        CoTaskMemFree(v107[1]);
        CoTaskMemFree(v108[0]);
        if ( !v24 )
          goto LABEL_22;
      }
      v26 = v90;
      v27 = CKnownFoldersFilter::EnsureManager((CKnownFoldersFilter *)(v6 + 39));
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\KnownFolderFilter.h",
          (const char *)(unsigned int)v27,
          ppv);
        goto LABEL_22;
      }
      v95 = 0;
      v28 = **v26;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
      v29 = v28(v26, &GUID_0e207e42_dc38_440d_9b00_2e8cf0e23c8d, &v95);
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\KnownFolderFilter.h",
          (const char *)(unsigned int)v29,
          ppv);
        v47 = v95;
        if ( v95 )
        {
          v95 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        }
        goto LABEL_22;
      }
      v30 = 1;
      LOWORD(pvar) = 0;
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v95 + 24LL))(
             v95,
             L"ThisPCPolicy",
             &pvar) < 0 )
      {
LABEL_41:
        PropVariantClear(&pvar);
        v32 = v95;
        if ( v95 )
        {
          v95 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v33 = v30 == 0;
        v6 = v80;
        if ( v33 )
          goto LABEL_22;
        v34 = v79;
        hdpa = v18;
        v77[0] = 0;
        ShouldAllowAccessToKnownFolder = NamespaceRestrictionHelper::ShouldAllowAccessToKnownFolder(
                                           v80 + 41,
                                           (char *)v89 + v20,
                                           v31,
                                           v77);
        if ( ShouldAllowAccessToKnownFolder < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18C,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
            (const char *)(unsigned int)ShouldAllowAccessToKnownFolder,
            ppv);
LABEL_22:
          Instance = v74;
          goto LABEL_23;
        }
        if ( !v77[0] )
        {
          v79 = v34;
          hdpa = v18;
          goto LABEL_22;
        }
        lpString2 = 0;
        v50 = (*v90)[6](v90, (GUID *)0x4000, (__int64 *)&lpString2);
        v75 = v50;
        if ( v50 < 0 )
        {
          v79 = v34;
          hdpa = v18;
          Instance = v50;
          goto LABEL_23;
        }
        if ( v82 && ((v81 & 0x2000) == 0 || !PathIsNetworkPathW(lpString2)) && !PathFileExistsW(lpString2) )
        {
          v79 = v34;
          hdpa = v18;
LABEL_109:
          Instance = v75;
          goto LABEL_114;
        }
        v51 = lpString2;
        v52 = *(_DWORD *)v9;
        for ( i = 0; i < v52; ++i )
        {
          if ( !(unsigned int)ComparePaths(v51, *(LPCWCH *)(*((_QWORD *)v9 + 1) + 8LL * i)) )
          {
            if ( i != -1 )
              goto LABEL_109;
            break;
          }
        }
        v54 = hdpa;
        v55 = *(_DWORD *)hdpa;
        v56 = 0x7FFFFFFF;
        if ( *(_DWORD *)hdpa != 0x7FFFFFFF )
          v56 = *(_DWORD *)hdpa;
        v57 = v55 + 1;
        if ( v55 + 1 < v55 )
          goto LABEL_113;
        v58 = *((_DWORD *)hdpa + 6);
        if ( v58 < 0 )
          goto LABEL_113;
        v59 = lpString2;
        if ( v57 > v58 && !DPA_Grow(hdpa, v57) )
          goto LABEL_113;
        if ( v56 < *(_DWORD *)v54 )
          memmove_0(
            (void *)(*((_QWORD *)v54 + 1) + 8LL * (v56 + 1)),
            (const void *)(*((_QWORD *)v54 + 1) + 8LL * v56),
            8LL * (*(_DWORD *)v54 - v56));
        *(_QWORD *)(*((_QWORD *)v54 + 1) + 8LL * v56) = v59;
        ++*(_DWORD *)v54;
        if ( v56 == -1 )
        {
LABEL_113:
          Instance = -2147024882;
          v6 = v80;
LABEL_114:
          CoTaskMemFree((LPVOID)lpString2);
          goto LABEL_23;
        }
        v60 = (__int128 *)((char *)v89 + v20);
        v61 = 0;
        v91 = 0;
        v62 = v80;
        v63 = (*((__int64 (__fastcall **)(void **, __int128 *, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))*v80
               + 6))(
                v80,
                v60,
                (v81 >> 12) & 1,
                &v91);
        v76 = v63;
        if ( v63 < 0 )
        {
LABEL_130:
          v71 = v91;
          v91 = 0;
          if ( v71 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v71)[2])(v71);
          if ( v63 < 0 )
          {
            Instance = v76;
          }
          else
          {
            v72 = v79;
            if ( DPA_InsertPtr(v79, 0x7FFFFFFF, v61) != -1 )
            {
              lpString2 = 0;
              Instance = 0;
              v79 = v72;
              v6 = v80;
              CoTaskMemFree(0);
              goto LABEL_23;
            }
            CoTaskMemFree(v61);
            Instance = -2147024882;
          }
          lpString2 = (LPCWSTR)DPA_DeletePtr(hdpa, v56);
          v6 = v80;
          CoTaskMemFree((LPVOID)lpString2);
LABEL_23:
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v90)[2])(v90);
          v18 = hdpa;
          goto LABEL_24;
        }
        v64 = *v60;
        v65 = v62[21];
        *(_QWORD *)&pguid.Data1 = 0;
        Src = 0;
        v66 = 0;
        Size = 0;
        if ( v91 )
        {
          v93 = 0;
          v63 = (**v91)(v91, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v93);
          v76 = v63;
          if ( v63 < 0 )
            goto LABEL_130;
          v63 = (*(__int64 (__fastcall **)(__int64, LPVOID *, unsigned int *))(*(_QWORD *)v93 + 40LL))(v93, &Src, &Size);
          v76 = v63;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
          if ( v63 < 0 )
            goto LABEL_130;
          v66 = Size;
        }
        v67 = v66 + 24 + 2LL;
        if ( v65 )
        {
          v70 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v65 + 24LL))(v65, v66 + 24 + 2LL);
        }
        else
        {
          v68 = v66 + 34;
          if ( (unsigned __int64)(v66 + 24) + 10 > 0x10001 )
            goto LABEL_149;
          v69 = CoTaskMemAlloc(v66 + 24 + 10LL);
          v70 = (__int64)v69;
          if ( v69 )
          {
            memset_0(v69, 0, v67 + 8);
            *(_WORD *)v70 = v68 - 2;
            *(_WORD *)(v70 + 4) = v67;
LABEL_126:
            *(_DWORD *)(v70 + 6) = 603896814;
            *(_WORD *)(v70 + 10) = Size;
            *(_WORD *)(v70 + 12) = 16;
            *(_OWORD *)(v70 + 14) = v64;
            if ( Src )
              memcpy_0((void *)(v70 + 30), Src, Size);
            v61 = (void *)v70;
            v63 = 0;
            goto LABEL_129;
          }
        }
        if ( v70 )
          goto LABEL_126;
LABEL_149:
        v63 = -2147024882;
        v61 = *(void **)&pguid.Data1;
LABEL_129:
        v76 = v63;
        CoTaskMemFree(Src);
        goto LABEL_130;
      }
      v37 = (__int16)pvar;
      if ( (_WORD)pvar == 8 || (_WORD)pvar == 31 )
      {
        v38 = String1;
        if ( String1 )
        {
          v39 = String1;
          goto LABEL_51;
        }
      }
      else
      {
        v38 = String1;
      }
      v39 = (wchar_t *)&WindowName;
LABEL_51:
      if ( !wcscmp_0(v39, L"Hide") )
      {
        LODWORD(lpString2) = 0;
        if ( ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), LPCWSTR *))(*v26)[10])(
               v26,
               &lpString2) >= 0 )
        {
          v30 = BYTE1(lpString2) & 1;
          v18 = hdpa;
          goto LABEL_41;
        }
        v30 = 0;
LABEL_65:
        v18 = hdpa;
        goto LABEL_41;
      }
      if ( v37 != 8 && v37 != 31 || !v38 )
        v38 = (wchar_t *)&WindowName;
      if ( wcscmp_0(v38, L"Show") )
        goto LABEL_65;
      LOWORD(propvar[0]) = 0;
      if ( (*(int (__fastcall **)(__int64, const WCHAR *, PROPVARIANT *))(*(_QWORD *)v95 + 24LL))(
             v95,
             L"BaseFolderId",
             propvar) >= 0 )
      {
        pguid = GUID_NULL;
        if ( LOWORD(propvar[0]) )
        {
          v40 = PropVariantToGUID(propvar, &pguid);
          if ( v40 >= 0 )
          {
            v98 = 0;
            v6 = v80;
            v41 = v80[39];
            v42 = *(__int64 (__fastcall **)(void *, GUID *, __int64 *))(*(_QWORD *)v41 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
            v43 = v42(v41, &pguid, &v98);
            if ( v43 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x54,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\KnownFolderFilter.h",
                (const char *)(unsigned int)v43,
                ppv);
              v48 = v98;
              if ( v98 )
              {
                v98 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
              }
              PropVariantClear(propvar);
              PropVariantClear(&pvar);
              v49 = v95;
              if ( v95 )
              {
                v95 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              }
              goto LABEL_22;
            }
            LODWORD(lpString2) = 0;
            v44 = (*(int (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v98 + 80LL))(v98, &lpString2) < 0
               || (BYTE1(lpString2) & 1) == 0;
            v45 = v98;
            if ( v98 )
            {
              v98 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            }
            v30 = v44;
            goto LABEL_64;
          }
        }
        else
        {
          v40 = -2147023728;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\KnownFolderFilter.h",
          (const char *)(unsigned int)v40,
          ppv);
        PropVariantClear(propvar);
        PropVariantClear(&pvar);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
        v6 = v80;
        goto LABEL_22;
      }
LABEL_64:
      PropVariantClear(propvar);
      goto LABEL_65;
    }
    Instance = v21;
LABEL_24:
    ++v19;
    v16 = (char *)v89;
  }
  while ( v19 < Size_4 );
  v12 = v86;
  v8 = v79;
LABEL_26:
  if ( v16 != v6[43] )
    CoTaskMemFree(v16);
LABEL_28:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
  if ( Instance >= 0 )
  {
LABEL_29:
    v12 = 0;
    v83 = 0;
    *v87 = v8;
    if ( v85 )
    {
      *v85 = v18;
      goto LABEL_31;
    }
    v46 = v18;
LABEL_87:
    DPA_DestroyCallback(v46, DPA_ILFreeCB<_ITEMIDLIST_ABSOLUTE>, 0);
LABEL_31:
    v9 = 0;
    goto LABEL_32;
  }
  v7 = (__int64)v85;
LABEL_71:
  if ( v8 )
  {
    DPA_DestroyCallback(v8, DPA_ILFreeCB<_ITEMIDLIST_ABSOLUTE>, 0);
    v12 = 0;
    v83 = 0;
  }
  if ( v7 && v9 )
  {
    v46 = v9;
    goto LABEL_87;
  }
LABEL_32:
  if ( v9 )
  {
    DPA_DestroyCallback(v9, CQueueItem::AppliesTo, 0);
    DPA_Destroy(0);
  }
  if ( v12 )
  {
    DPA_DestroyCallback(v12, CQueueItem::AppliesTo, 0);
    DPA_Destroy(0);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180052490  mov     [rsp-8+arg_8], rbx
0x180052495  push    rbp
0x180052496  push    rsi
0x180052497  push    rdi
0x180052498  push    r12
0x18005249a  push    r13
0x18005249c  push    r14
0x18005249e  push    r15
0x1800524a0  lea     rbp, [rsp-0A0h]
0x1800524a8  sub     rsp, 1A0h
0x1800524af  movaps  [rsp+1D0h+var_40], xmm6
0x1800524b7  mov     rax, cs:__security_cookie
0x1800524be  xor     rax, rsp
0x1800524c1  mov     [rbp+0D0h+var_50], rax
0x1800524c8  mov     [rsp+1D0h+var_158], r9
0x1800524cd  mov     r14d, r8d
0x1800524d0  mov     [rsp+1D0h+var_180], r8d
0x1800524d5  mov     [rsp+1D0h+var_17C], edx
0x1800524d9  mov     r13, rcx
0x1800524dc  mov     [rsp+1D0h+var_188], rcx
0x1800524e1  mov     r15, [rbp+0D0h+arg_20]
0x1800524e8  mov     [rsp+1D0h+var_168], r15
0x1800524ed  xor     r12d, r12d
0x1800524f0  mov     ebx, r12d
0x1800524f3  mov     [rsp+1D0h+var_170], rbx
0x1800524f8  call    cs:__imp_GetProcessHeap
0x1800524fe  mov     rsi, rax
0x180052501  mov     edx, 8; dwFlags
0x180052506  mov     r8d, 20h ; ' '; dwBytes
0x18005250c  mov     rcx, rax; hHeap
0x18005250f  call    cs:__imp_HeapAlloc
0x180052515  mov     rdi, rax
0x180052518  mov     [rsp+1D0h+var_160], rax
0x18005251d  test    rax, rax
0x180052520  jz      loc_180052AE6
0x180052526  mov     dword ptr [rax+1Ch], 10h
0x18005252d  mov     [rax+10h], rsi
0x180052531  mov     [rsp+1D0h+var_178], rax
0x180052536  call    cs:__imp_GetProcessHeap
0x18005253c  mov     rsi, rax
0x18005253f  mov     edx, 8; dwFlags
0x180052544  mov     r8d, 20h ; ' '; dwBytes
0x18005254a  mov     rcx, rax; hHeap
0x18005254d  call    cs:__imp_HeapAlloc
0x180052553  mov     rbx, rax
0x180052556  test    rax, rax
0x180052559  jz      loc_180052BDE
0x18005255f  mov     dword ptr [rax+1Ch], 10h
0x180052566  mov     [rax+10h], rsi
0x18005256a  mov     [rsp+1D0h+var_170], rax
0x18005256f  test    r14b, 20h
0x180052573  jz      loc_1800530DB
0x180052579  mov     [rbp+0D0h+var_130], r12
0x18005257d  lea     rsi, [r13+128h]
0x180052584  cmp     [rsi], r12
0x180052587  jnz     short loc_1800525AE
0x180052589  mov     qword ptr [rsp+1D0h+ppv], rsi; int
0x18005258e  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x180052595  xor     r8d, r8d; pUnkOuter
0x180052598  lea     rdx, CLSID_KnownFolderManager; pclsid
0x18005259f  xor     ecx, ecx; pszCLSID
0x1800525a1  call    cs:__imp_SHCoCreateInstance
0x1800525a7  mov     r14d, eax
0x1800525aa  test    eax, eax
0x1800525ac  js      short loc_1800525CA
0x1800525ae  mov     rcx, [rsi]
0x1800525b1  mov     rax, [rcx]
0x1800525b4  lea     r8, [rbp+0D0h+var_130]
0x1800525b8  lea     rdx, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018
0x1800525bf  mov     rax, [rax]
0x1800525c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525c7  mov     r14d, eax
0x1800525ca  test    r14d, r14d
0x1800525cd  js      loc_180052BEC
0x1800525d3  mov     dword ptr [rbp+0D0h+Size+4], r12d
0x1800525d7  mov     [rbp+0D0h+var_148], r12
0x1800525db  mov     rdx, [r13+158h]
0x1800525e2  test    rdx, rdx
0x1800525e5  jnz     loc_180052C30
0x1800525eb  mov     rcx, [rbp+0D0h+var_130]
0x1800525ef  mov     rax, [rcx]
0x1800525f2  lea     r8, [rbp+0D0h+Size+4]
0x1800525f6  lea     rdx, [rbp+0D0h+var_148]
0x1800525fa  mov     rax, [rax+28h]
0x1800525fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052603  mov     r14d, eax
0x180052606  test    eax, eax
0x180052608  js      loc_180052C1B
0x18005260e  mov     eax, dword ptr [rbp+0D0h+Size+4]
0x180052611  mov     rdx, [rbp+0D0h+var_148]
0x180052615  mov     r15, rbx
0x180052618  test    eax, eax
0x18005261a  jz      loc_180052C75
0x180052620  xor     esi, esi
0x180052622  mov     [rsp+1D0h+hdpa], rbx
0x180052627  mov     [rsp+1D0h+var_190], rdi
0x18005262c  nop     dword ptr [rax+00h]
0x180052630  mov     [rbp+0D0h+var_140], 0
0x180052638  mov     r12d, esi
0x18005263b  shl     r12, 4
0x18005263f  mov     rcx, [rbp+0D0h+var_130]
0x180052643  mov     rax, [rcx]
0x180052646  add     rdx, r12
0x180052649  lea     r8, [rbp+0D0h+var_140]
0x18005264d  mov     rax, [rax+30h]
0x180052651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052656  mov     [rsp+1D0h+var_1A0], eax
0x18005265a  test    eax, eax
0x18005265c  js      loc_180052821
0x180052662  mov     rcx, [rbp+0D0h+var_140]
0x180052666  xorps   xmm0, xmm0
0x180052669  movups  xmmword ptr [rbp+0D0h+pv], xmm0
0x18005266d  movups  xmmword ptr [rbp+0D0h+var_B0], xmm0
0x180052671  movups  xmmword ptr [rbp+0D0h+pszPath], xmm0
0x180052675  movups  xmmword ptr [rbp+0D0h+var_90], xmm0
0x180052679  movups  xmmword ptr [rbp+0D0h+var_80], xmm0
0x18005267d  movups  xmmword ptr [rbp+0D0h+var_70], xmm0
0x180052681  movups  [rbp+0D0h+var_60], xmm0
0x180052685  mov     rdx, [rcx]
0x180052688  mov     rax, [rdx+58h]
0x18005268c  lea     rdx, [rbp+0D0h+pv]
0x180052690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052695  test    eax, eax
0x180052697  js      loc_180052C0B
0x18005269d  test    byte ptr [rsp+1D0h+var_180], 80h
0x1800526a2  jz      loc_180052AD7
0x1800526a8  mov     rax, [rbp+0D0h+var_B0+8]
0x1800526ac  sub     rax, [r13+0E8h]
0x1800526b3  jnz     short loc_1800526C0
0x1800526b5  mov     rax, [rbp+0D0h+pszPath]
0x1800526b9  sub     rax, [r13+0F0h]
0x1800526c0  test    rax, rax
0x1800526c3  jnz     short loc_1800526D2
0x1800526c5  mov     rcx, [rbp+0D0h+pszPath+8]; pszPath
0x1800526c9  test    rcx, rcx
0x1800526cc  jnz     loc_18005292D
0x1800526d2  xor     r14d, r14d
0x1800526d5  mov     rcx, [rbp+0D0h+pv+8]; pv
0x1800526d9  call    cs:__imp_CoTaskMemFree
0x1800526df  mov     rcx, [rbp+0D0h+var_B0]; pv
0x1800526e3  call    cs:__imp_CoTaskMemFree
0x1800526e9  mov     rcx, [rbp+0D0h+pszPath+8]; pv
0x1800526ed  call    cs:__imp_CoTaskMemFree
0x1800526f3  mov     rcx, [rbp+0D0h+var_90]; pv
0x1800526f7  call    cs:__imp_CoTaskMemFree
0x1800526fd  mov     rcx, [rbp+0D0h+var_90+8]; pv
0x180052701  call    cs:__imp_CoTaskMemFree
0x180052707  mov     rcx, [rbp+0D0h+var_80]; pv
0x18005270b  call    cs:__imp_CoTaskMemFree
0x180052711  mov     rcx, [rbp+0D0h+var_80+8]; pv
0x180052715  call    cs:__imp_CoTaskMemFree
0x18005271b  mov     rcx, [rbp+0D0h+var_70]; pv
0x18005271f  call    cs:__imp_CoTaskMemFree
0x180052725  test    r14d, r14d
0x180052728  jnz     loc_180052829
0x18005272e  mov     r14d, [rsp+1D0h+var_1A0]
0x180052733  mov     rcx, [rbp+0D0h+var_140]
0x180052737  mov     rax, [rcx]
0x18005273a  mov     rax, [rax+10h]
0x18005273e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052743  mov     r15, [rsp+1D0h+hdpa]
0x180052748  inc     esi
0x18005274a  mov     rdx, [rbp+0D0h+var_148]
0x18005274e  cmp     esi, dword ptr [rbp+0D0h+Size+4]
0x180052751  jb      loc_180052630
0x180052757  mov     rdi, [rsp+1D0h+var_160]
0x18005275c  mov     r12, [rsp+1D0h+var_190]
0x180052761  cmp     rdx, [r13+158h]
0x180052768  jz      short loc_180052773
0x18005276a  mov     rcx, rdx; pv
0x18005276d  call    cs:__imp_CoTaskMemFree
0x180052773  mov     rcx, [rbp+0D0h+var_130]
0x180052777  mov     rax, [rcx]
0x18005277a  mov     rax, [rax+10h]
0x18005277e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052783  test    r14d, r14d
0x180052786  js      loc_180052C26
0x18005278c  xor     edi, edi
0x18005278e  mov     [rsp+1D0h+var_178], rdi
0x180052793  mov     rax, [rsp+1D0h+var_158]
0x180052798  mov     [rax], r12
0x18005279b  mov     rax, [rsp+1D0h+var_168]
0x1800527a0  test    rax, rax
0x1800527a3  jz      loc_180052BF4
0x1800527a9  mov     [rax], r15
0x1800527ac  xor     ebx, ebx
0x1800527ae  test    rbx, rbx
0x1800527b1  jz      short loc_1800527CD
0x1800527b3  xor     r8d, r8d; pData
0x1800527b6  lea     rdx, ?AppliesTo@CQueueItem@@UEAAJPEAUIUnknown@@@Z; pfnCB
0x1800527bd  mov     rcx, rbx; hdpa
0x1800527c0  call    DPA_DestroyCallback
0x1800527c5  xor     ecx, ecx; hdpa
0x1800527c7  call    DPA_Destroy
0x1800527cc  nop
0x1800527cd  test    rdi, rdi
0x1800527d0  jz      short loc_1800527EC
0x1800527d2  xor     r8d, r8d; pData
0x1800527d5  lea     rdx, ?AppliesTo@CQueueItem@@UEAAJPEAUIUnknown@@@Z; pfnCB
0x1800527dc  mov     rcx, rdi; hdpa
0x1800527df  call    DPA_DestroyCallback
0x1800527e4  xor     ecx, ecx; hdpa
0x1800527e6  call    DPA_Destroy
0x1800527eb  nop
0x1800527ec  mov     eax, r14d
0x1800527ef  mov     rcx, [rbp+0D0h+var_50]
0x1800527f6  xor     rcx, rsp; StackCookie
0x1800527f9  call    __security_check_cookie
0x1800527fe  mov     rbx, [rsp+1D0h+arg_8]
0x180052806  movaps  xmm6, [rsp+1D0h+var_40]
0x18005280e  add     rsp, 1A0h
0x180052815  pop     r15
0x180052817  pop     r14
0x180052819  pop     r13
0x18005281b  pop     r12
0x18005281d  pop     rdi
0x18005281e  pop     rsi
0x18005281f  pop     rbp
0x180052820  retn
0x180052821  mov     r14d, eax
0x180052824  jmp     loc_180052748
0x180052829  lea     rcx, [r13+138h]; this
0x180052830  mov     rdi, [rbp+0D0h+var_140]
0x180052834  call    ?EnsureManager@CKnownFoldersFilter@@AEAAJXZ; CKnownFoldersFilter::EnsureManager(void)
0x180052839  test    eax, eax
0x18005283b  js      loc_180053073
0x180052841  mov     [rbp+0D0h+var_118], 0
0x180052849  mov     rax, [rdi]
0x18005284c  mov     r14, [rax]
0x18005284f  lea     rcx, [rbp+0D0h+var_118]
0x180052853  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180052858  lea     r8, [rbp+0D0h+var_118]
0x18005285c  lea     rdx, _GUID_0e207e42_dc38_440d_9b00_2e8cf0e23c8d
0x180052863  mov     rcx, rdi
0x180052866  mov     rax, r14
0x180052869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005286e  test    eax, eax
0x180052870  js      loc_180052B2C
0x180052876  mov     r13b, 1
0x180052879  xor     eax, eax
0x18005287b  mov     word ptr [rbp+0D0h+pvar], ax
0x18005287f  mov     rcx, [rbp+0D0h+var_118]
0x180052883  mov     rax, [rcx]
0x180052886  lea     r8, [rbp+0D0h+pvar]
0x18005288a  lea     rdx, aThispcpolicy; "ThisPCPolicy"
0x180052891  mov     rax, [rax+18h]
0x180052895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005289a  test    eax, eax
0x18005289c  jns     loc_180052948
0x1800528a2  lea     rcx, [rbp+0D0h+pvar]; pvar
0x1800528a6  call    cs:__imp_PropVariantClear
0x1800528ac  nop
0x1800528ad  mov     rcx, [rbp+0D0h+var_118]
0x1800528b1  test    rcx, rcx
0x1800528b4  jz      short loc_1800528CB
0x1800528b6  mov     [rbp+0D0h+var_118], 0
0x1800528be  mov     rax, [rcx]
0x1800528c1  mov     rax, [rax+10h]
0x1800528c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528ca  nop
0x1800528cb  test    r13b, r13b
0x1800528ce  mov     r13, [rsp+1D0h+var_188]
0x1800528d3  jz      loc_18005272E
0x1800528d9  mov     r14, [rsp+1D0h+var_190]
0x1800528de  mov     [rsp+1D0h+var_190], r14
0x1800528e3  mov     [rsp+1D0h+hdpa], r15
0x1800528e8  mov     [rsp+1D0h+var_19C], 0
0x1800528ed  mov     rdx, [rbp+0D0h+var_148]
0x1800528f1  add     rdx, r12
0x1800528f4  lea     rcx, [r13+148h]
0x1800528fb  lea     r9, [rsp+1D0h+var_19C]
0x180052900  call    ?ShouldAllowAccessToKnownFolder@NamespaceRestrictionHelper@@AEAAJPEBU_GUID@@W4NamespaceRestrictionCategory@@PEA_N@Z; NamespaceRestrictionHelper::ShouldAllowAccessToKnownFolder(_GUID const *,NamespaceRestrictionCategory,bool *)
0x180052905  test    eax, eax
0x180052907  jns     loc_180052CC7
0x18005290d  mov     rcx, [rbp+0D8h]; this
0x180052914  mov     r9d, eax; char *
0x180052917  lea     r8, aOnecoreuapInte_19; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18005291e  mov     edx, 18Ch; void *
0x180052923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052928  jmp     loc_18005272E
0x18005292d  call    cs:__imp_PathFindFileNameW
0x180052933  cmp     [rbp+0D0h+pszPath+8], rax
0x180052937  jnz     loc_1800526D2
0x18005293d  mov     r14d, 1
0x180052943  jmp     loc_1800526D5
0x180052948  movzx   r14d, word ptr [rbp+0D0h+pvar]
0x18005294d  cmp     r14w, 8
0x180052952  jnz     loc_180052C43
0x180052958  mov     r15, [rbp+0D0h+String1]
0x18005295c  test    r15, r15
0x18005295f  jz      loc_180052C52
0x180052965  mov     rcx, r15; String1
0x180052968  lea     rdx, aHide; "Hide"
0x18005296f  call    wcscmp_0
0x180052974  test    eax, eax
0x180052976  jz      loc_180052A9F
0x18005297c  cmp     r14w, 8
0x180052981  jnz     loc_180052C5E
0x180052987  test    r15, r15
0x18005298a  jz      loc_180052C69
  ... truncated ...
```
