# CKnownFoldersFolder::_EnumFolders(int,ulong,CDPA<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>> *,CDPA<ushort,CTContainer_PolicyUnOwned<ushort>> *)

- ea: `0x1800b45e0`
- end: `0x1800b52d2`
- name: `?_EnumFolders@CKnownFoldersFolder@@IEAAJHKPEAV?$CDPA@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@PEAV?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@@Z`
- size: `3314`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180141af0`
- `0x180143430`
- `0x1802392d0`
- `0x1802f28b0`

## callees

- `0x180009fc0`
- `0x180038f50`
- `0x18004d470`
- `0x18004d720`
- `0x180054f30`
- `0x1800550e0`
- `0x1800b3210`
- `0x1800b45e0`
- `0x1800b52e0`
- `0x1800b5450`
- `0x1800b55bc`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x1803b69d1`
- `0x1806496a4`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4665`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b46af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4665`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b46af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4692`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b4692`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b4ada`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b4ada`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800b5194`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800b5194`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800b4709`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800b4709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4899`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b48a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b48b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b490d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4f5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b50bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b510a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4899`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b48a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b48b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b490d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b4f5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b50bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b510a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4a4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4c48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4d68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4d79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4e6d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4e7e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4a4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4c48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4d68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4d79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4e6d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b4e7e`
- `PROPSYS!PropVariantToGUID` at `0x1800b4b9f`
- `PROPSYS!PropVariantToGUID` at `0x1800b4b9f`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800b5221`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800b5221`

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
LABEL_23:
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v90)[2])(v90);
          v18 = hdpa;
          goto LABEL_24;
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
          goto LABEL_114;
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
              goto LABEL_114;
            }
            CoTaskMemFree(v61);
            Instance = -2147024882;
          }
          lpString2 = (LPCWSTR)DPA_DeletePtr(hdpa, v56);
          v6 = v80;
LABEL_114:
          CoTaskMemFree((LPVOID)lpString2);
          goto LABEL_23;
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
0x1800b45e0  mov     [rsp-8+arg_8], rbx
0x1800b45e5  push    rbp
0x1800b45e6  push    rsi
0x1800b45e7  push    rdi
0x1800b45e8  push    r12
0x1800b45ea  push    r13
0x1800b45ec  push    r14
0x1800b45ee  push    r15
0x1800b45f0  lea     rbp, [rsp-0A0h]
0x1800b45f8  sub     rsp, 1A0h
0x1800b45ff  movaps  [rsp+1D0h+var_40], xmm6
0x1800b4607  mov     rax, cs:__security_cookie
0x1800b460e  xor     rax, rsp
0x1800b4611  mov     [rbp+0D0h+var_50], rax
0x1800b4618  mov     [rsp+1D0h+var_158], r9
0x1800b461d  mov     r14d, r8d
0x1800b4620  mov     [rsp+1D0h+var_180], r8d
0x1800b4625  mov     [rsp+1D0h+var_17C], edx
0x1800b4629  mov     r13, rcx
0x1800b462c  mov     [rsp+1D0h+var_188], rcx
0x1800b4631  mov     r15, [rbp+0D0h+arg_20]
0x1800b4638  mov     [rsp+1D0h+var_168], r15
0x1800b463d  xor     r12d, r12d
0x1800b4640  mov     ebx, r12d
0x1800b4643  mov     [rsp+1D0h+var_170], rbx
0x1800b4648  call    cs:__imp_GetProcessHeap
0x1800b464f  nop     dword ptr [rax+rax+00h]
0x1800b4654  mov     rsi, rax
0x1800b4657  mov     edx, 8; dwFlags
0x1800b465c  mov     r8d, 20h ; ' '; dwBytes
0x1800b4662  mov     rcx, rax; hHeap
0x1800b4665  call    cs:__imp_HeapAlloc
0x1800b466c  nop     dword ptr [rax+rax+00h]
0x1800b4671  mov     rdi, rax
0x1800b4674  mov     [rsp+1D0h+var_160], rax
0x1800b4679  test    rax, rax
0x1800b467c  jz      loc_1800B4CA5
0x1800b4682  mov     dword ptr [rax+1Ch], 10h
0x1800b4689  mov     [rax+10h], rsi
0x1800b468d  mov     [rsp+1D0h+var_178], rax
0x1800b4692  call    cs:__imp_GetProcessHeap
0x1800b4699  nop     dword ptr [rax+rax+00h]
0x1800b469e  mov     rsi, rax
0x1800b46a1  mov     edx, 8; dwFlags
0x1800b46a6  mov     r8d, 20h ; ' '; dwBytes
0x1800b46ac  mov     rcx, rax; hHeap
0x1800b46af  call    cs:__imp_HeapAlloc
0x1800b46b6  nop     dword ptr [rax+rax+00h]
0x1800b46bb  mov     rbx, rax
0x1800b46be  test    rax, rax
0x1800b46c1  jz      loc_1800B4DA9
0x1800b46c7  mov     dword ptr [rax+1Ch], 10h
0x1800b46ce  mov     [rax+10h], rsi
0x1800b46d2  mov     [rsp+1D0h+var_170], rax
0x1800b46d7  test    r14b, 20h
0x1800b46db  jz      loc_1800B52C3
0x1800b46e1  mov     [rbp+0D0h+var_130], r12
0x1800b46e5  lea     rsi, [r13+128h]
0x1800b46ec  cmp     [rsi], r12
0x1800b46ef  jnz     short loc_1800B471C
0x1800b46f1  mov     qword ptr [rsp+1D0h+ppv], rsi; int
0x1800b46f6  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x1800b46fd  xor     r8d, r8d; pUnkOuter
0x1800b4700  lea     rdx, CLSID_KnownFolderManager; pclsid
0x1800b4707  xor     ecx, ecx; pszCLSID
0x1800b4709  call    cs:__imp_SHCoCreateInstance
0x1800b4710  nop     dword ptr [rax+rax+00h]
0x1800b4715  mov     r14d, eax
0x1800b4718  test    eax, eax
0x1800b471a  js      short loc_1800B4738
0x1800b471c  mov     rcx, [rsi]
0x1800b471f  mov     rax, [rcx]
0x1800b4722  lea     r8, [rbp+0D0h+var_130]
0x1800b4726  lea     rdx, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018
0x1800b472d  mov     rax, [rax]
0x1800b4730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4735  mov     r14d, eax
0x1800b4738  test    r14d, r14d
0x1800b473b  js      loc_1800B4DB7
0x1800b4741  mov     dword ptr [rbp+0D0h+Size+4], r12d
0x1800b4745  mov     [rbp+0D0h+var_148], r12
0x1800b4749  mov     rdx, [r13+158h]
0x1800b4750  test    rdx, rdx
0x1800b4753  jnz     loc_1800B4DFB
0x1800b4759  mov     rcx, [rbp+0D0h+var_130]
0x1800b475d  mov     rax, [rcx]
0x1800b4760  lea     r8, [rbp+0D0h+Size+4]
0x1800b4764  lea     rdx, [rbp+0D0h+var_148]
0x1800b4768  mov     rax, [rax+28h]
0x1800b476c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4771  mov     r14d, eax
0x1800b4774  test    eax, eax
0x1800b4776  js      loc_1800B4DE6
0x1800b477c  mov     eax, dword ptr [rbp+0D0h+Size+4]
0x1800b477f  mov     rdx, [rbp+0D0h+var_148]
0x1800b4783  mov     r15, rbx
0x1800b4786  test    eax, eax
0x1800b4788  jz      loc_1800B4E40
0x1800b478e  xor     esi, esi
0x1800b4790  mov     [rsp+1D0h+hdpa], rbx
0x1800b4795  mov     [rsp+1D0h+var_190], rdi
0x1800b479a  nop     word ptr [rax+rax+00h]
0x1800b47a0  mov     [rbp+0D0h+var_140], 0
0x1800b47a8  mov     r12d, esi
0x1800b47ab  shl     r12, 4
0x1800b47af  mov     rcx, [rbp+0D0h+var_130]
0x1800b47b3  mov     rax, [rcx]
0x1800b47b6  add     rdx, r12
0x1800b47b9  lea     r8, [rbp+0D0h+var_140]
0x1800b47bd  mov     rax, [rax+30h]
0x1800b47c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b47c6  mov     [rsp+1D0h+var_1A0], eax
0x1800b47ca  test    eax, eax
0x1800b47cc  js      loc_1800B49C8
0x1800b47d2  mov     rcx, [rbp+0D0h+var_140]
0x1800b47d6  xorps   xmm0, xmm0
0x1800b47d9  movups  xmmword ptr [rbp+0D0h+pv], xmm0
0x1800b47dd  movups  xmmword ptr [rbp+0D0h+var_B0], xmm0
0x1800b47e1  movups  xmmword ptr [rbp+0D0h+pszPath], xmm0
0x1800b47e5  movups  xmmword ptr [rbp+0D0h+var_90], xmm0
0x1800b47e9  movups  xmmword ptr [rbp+0D0h+var_80], xmm0
0x1800b47ed  movups  xmmword ptr [rbp+0D0h+var_70], xmm0
0x1800b47f1  movups  [rbp+0D0h+var_60], xmm0
0x1800b47f5  mov     rdx, [rcx]
0x1800b47f8  mov     rax, [rdx+58h]
0x1800b47fc  lea     rdx, [rbp+0D0h+pv]
0x1800b4800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4805  test    eax, eax
0x1800b4807  js      loc_1800B4DD6
0x1800b480d  test    byte ptr [rsp+1D0h+var_180], 80h
0x1800b4812  jz      loc_1800B4C96
0x1800b4818  mov     rax, [rbp+0D0h+var_B0+8]
0x1800b481c  sub     rax, [r13+0E8h]
0x1800b4823  jnz     short loc_1800B4830
0x1800b4825  mov     rax, [rbp+0D0h+pszPath]
0x1800b4829  sub     rax, [r13+0F0h]
0x1800b4830  test    rax, rax
0x1800b4833  jnz     short loc_1800B4842
0x1800b4835  mov     rcx, [rbp+0D0h+pszPath+8]; pszPath
0x1800b4839  test    rcx, rcx
0x1800b483c  jnz     loc_1800B4ADA
0x1800b4842  xor     r14d, r14d
0x1800b4845  mov     rcx, [rbp+0D0h+pv+8]; pv
0x1800b4849  call    cs:__imp_CoTaskMemFree
0x1800b4850  nop     dword ptr [rax+rax+00h]
0x1800b4855  mov     rcx, [rbp+0D0h+var_B0]; pv
0x1800b4859  call    cs:__imp_CoTaskMemFree
0x1800b4860  nop     dword ptr [rax+rax+00h]
0x1800b4865  mov     rcx, [rbp+0D0h+pszPath+8]; pv
0x1800b4869  call    cs:__imp_CoTaskMemFree
0x1800b4870  nop     dword ptr [rax+rax+00h]
0x1800b4875  mov     rcx, [rbp+0D0h+var_90]; pv
0x1800b4879  call    cs:__imp_CoTaskMemFree
0x1800b4880  nop     dword ptr [rax+rax+00h]
0x1800b4885  mov     rcx, [rbp+0D0h+var_90+8]; pv
0x1800b4889  call    cs:__imp_CoTaskMemFree
0x1800b4890  nop     dword ptr [rax+rax+00h]
0x1800b4895  mov     rcx, [rbp+0D0h+var_80]; pv
0x1800b4899  call    cs:__imp_CoTaskMemFree
0x1800b48a0  nop     dword ptr [rax+rax+00h]
0x1800b48a5  mov     rcx, [rbp+0D0h+var_80+8]; pv
0x1800b48a9  call    cs:__imp_CoTaskMemFree
0x1800b48b0  nop     dword ptr [rax+rax+00h]
0x1800b48b5  mov     rcx, [rbp+0D0h+var_70]; pv
0x1800b48b9  call    cs:__imp_CoTaskMemFree
0x1800b48c0  nop     dword ptr [rax+rax+00h]
0x1800b48c5  test    r14d, r14d
0x1800b48c8  jnz     loc_1800B49D0
0x1800b48ce  mov     r14d, [rsp+1D0h+var_1A0]
0x1800b48d3  mov     rcx, [rbp+0D0h+var_140]
0x1800b48d7  mov     rax, [rcx]
0x1800b48da  mov     rax, [rax+10h]
0x1800b48de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b48e3  mov     r15, [rsp+1D0h+hdpa]
0x1800b48e8  inc     esi
0x1800b48ea  mov     rdx, [rbp+0D0h+var_148]
0x1800b48ee  cmp     esi, dword ptr [rbp+0D0h+Size+4]
0x1800b48f1  jb      loc_1800B47A0
0x1800b48f7  mov     rdi, [rsp+1D0h+var_160]
0x1800b48fc  mov     r12, [rsp+1D0h+var_190]
0x1800b4901  cmp     rdx, [r13+158h]
0x1800b4908  jz      short loc_1800B4919
0x1800b490a  mov     rcx, rdx; pv
0x1800b490d  call    cs:__imp_CoTaskMemFree
0x1800b4914  nop     dword ptr [rax+rax+00h]
0x1800b4919  mov     rcx, [rbp+0D0h+var_130]
0x1800b491d  mov     rax, [rcx]
0x1800b4920  mov     rax, [rax+10h]
0x1800b4924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4929  test    r14d, r14d
0x1800b492c  js      loc_1800B4DF1
0x1800b4932  xor     edi, edi
0x1800b4934  mov     [rsp+1D0h+var_178], rdi
0x1800b4939  mov     rax, [rsp+1D0h+var_158]
0x1800b493e  mov     [rax], r12
0x1800b4941  mov     rax, [rsp+1D0h+var_168]
0x1800b4946  test    rax, rax
0x1800b4949  jz      loc_1800B4DBF
0x1800b494f  mov     [rax], r15
0x1800b4952  xor     ebx, ebx
0x1800b4954  test    rbx, rbx
0x1800b4957  jz      short loc_1800B4973
0x1800b4959  xor     r8d, r8d; pData
0x1800b495c  lea     rdx, ?AppliesTo@CQueueItem@@UEAAJPEAUIUnknown@@@Z; pfnCB
0x1800b4963  mov     rcx, rbx; hdpa
0x1800b4966  call    DPA_DestroyCallback
0x1800b496b  xor     ecx, ecx; hdpa
0x1800b496d  call    DPA_Destroy
0x1800b4972  nop
0x1800b4973  test    rdi, rdi
0x1800b4976  jz      short loc_1800B4992
0x1800b4978  xor     r8d, r8d; pData
0x1800b497b  lea     rdx, ?AppliesTo@CQueueItem@@UEAAJPEAUIUnknown@@@Z; pfnCB
0x1800b4982  mov     rcx, rdi; hdpa
0x1800b4985  call    DPA_DestroyCallback
0x1800b498a  xor     ecx, ecx; hdpa
0x1800b498c  call    DPA_Destroy
0x1800b4991  nop
0x1800b4992  mov     eax, r14d
0x1800b4995  mov     rcx, [rbp+0D0h+var_50]
0x1800b499c  xor     rcx, rsp; StackCookie
0x1800b499f  call    __security_check_cookie
0x1800b49a4  mov     rbx, [rsp+1D0h+arg_8]
0x1800b49ac  movaps  xmm6, [rsp+1D0h+var_40]
0x1800b49b4  add     rsp, 1A0h
0x1800b49bb  pop     r15
0x1800b49bd  pop     r14
0x1800b49bf  pop     r13
0x1800b49c1  pop     r12
0x1800b49c3  pop     rdi
0x1800b49c4  pop     rsi
0x1800b49c5  pop     rbp
0x1800b49c6  retn
0x1800b49c8  mov     r14d, eax
0x1800b49cb  jmp     loc_1800B48E8
0x1800b49d0  lea     rcx, [r13+138h]; this
0x1800b49d7  mov     rdi, [rbp+0D0h+var_140]
0x1800b49db  call    ?EnsureManager@CKnownFoldersFilter@@AEAAJXZ; CKnownFoldersFilter::EnsureManager(void)
0x1800b49e0  test    eax, eax
0x1800b49e2  js      loc_1800B525B
0x1800b49e8  mov     [rbp+0D0h+var_118], 0
0x1800b49f0  mov     rax, [rdi]
0x1800b49f3  mov     r14, [rax]
0x1800b49f6  lea     rcx, [rbp+0D0h+var_118]
0x1800b49fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b49ff  lea     r8, [rbp+0D0h+var_118]
0x1800b4a03  lea     rdx, _GUID_0e207e42_dc38_440d_9b00_2e8cf0e23c8d
0x1800b4a0a  mov     rcx, rdi
0x1800b4a0d  mov     rax, r14
0x1800b4a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4a15  test    eax, eax
0x1800b4a17  js      loc_1800B4CEB
0x1800b4a1d  mov     r13b, 1
0x1800b4a20  xor     eax, eax
0x1800b4a22  mov     word ptr [rbp+0D0h+pvar], ax
0x1800b4a26  mov     rcx, [rbp+0D0h+var_118]
0x1800b4a2a  mov     rax, [rcx]
0x1800b4a2d  lea     r8, [rbp+0D0h+pvar]
0x1800b4a31  lea     rdx, aThispcpolicy; "ThisPCPolicy"
0x1800b4a38  mov     rax, [rax+18h]
0x1800b4a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4a41  test    eax, eax
0x1800b4a43  jns     loc_1800B4AFB
0x1800b4a49  lea     rcx, [rbp+0D0h+pvar]; pvar
0x1800b4a4d  call    cs:__imp_PropVariantClear
0x1800b4a54  nop     dword ptr [rax+rax+00h]
0x1800b4a59  nop
0x1800b4a5a  mov     rcx, [rbp+0D0h+var_118]
0x1800b4a5e  test    rcx, rcx
0x1800b4a61  jz      short loc_1800B4A78
0x1800b4a63  mov     [rbp+0D0h+var_118], 0
0x1800b4a6b  mov     rax, [rcx]
0x1800b4a6e  mov     rax, [rax+10h]
0x1800b4a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4a77  nop
0x1800b4a78  test    r13b, r13b
0x1800b4a7b  mov     r13, [rsp+1D0h+var_188]
0x1800b4a80  jz      loc_1800B48CE
0x1800b4a86  mov     r14, [rsp+1D0h+var_190]
0x1800b4a8b  mov     [rsp+1D0h+var_190], r14
0x1800b4a90  mov     [rsp+1D0h+hdpa], r15
0x1800b4a95  mov     [rsp+1D0h+var_19C], 0
0x1800b4a9a  mov     rdx, [rbp+0D0h+var_148]
0x1800b4a9e  add     rdx, r12
0x1800b4aa1  lea     rcx, [r13+148h]
0x1800b4aa8  lea     r9, [rsp+1D0h+var_19C]
0x1800b4aad  call    ?ShouldAllowAccessToKnownFolder@NamespaceRestrictionHelper@@AEAAJPEBU_GUID@@W4NamespaceRestrictionCategory@@PEA_N@Z; NamespaceRestrictionHelper::ShouldAllowAccessToKnownFolder(_GUID const *,NamespaceRestrictionCategory,bool *)
0x1800b4ab2  test    eax, eax
0x1800b4ab4  jns     loc_1800B4E9E
0x1800b4aba  mov     rcx, [rbp+0D8h]; this
0x1800b4ac1  mov     r9d, eax; char *
0x1800b4ac4  lea     r8, aOnecoreuapInte_19; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800b4acb  mov     edx, 18Ch; void *
0x1800b4ad0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4ad5  jmp     loc_1800B48CE
0x1800b4ada  call    cs:__imp_PathFindFileNameW
0x1800b4ae1  nop     dword ptr [rax+rax+00h]
0x1800b4ae6  cmp     [rbp+0D0h+pszPath+8], rax
0x1800b4aea  jnz     loc_1800B4842
0x1800b4af0  mov     r14d, 1
  ... truncated ...
```
