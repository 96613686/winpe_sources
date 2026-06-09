# CShellItem::BindToHandler(IBindCtx *,_GUID const &,_GUID const &,void * *)

- ea: `0x180088a70`
- end: `0x1800897e7`
- name: `?BindToHandler@CShellItem@@UEAAJPEAUIBindCtx@@AEBU_GUID@@1PEAPEAX@Z`
- size: `3447`
- prototype: `__int64 __fastcall(CShellItem *__hidden this, struct IBindCtx *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180061860`
- `0x180067e20`
- `0x180088a70`
- `0x1800899a4`
- `0x1800d3170`
- `0x180146150`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180088de0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180088de0`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180089547`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180089547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088e8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088e8d`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180088b75`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180088b75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088b34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088b34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180089144`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180089144`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180089171`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180089171`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180088b1a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180088b1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008926f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008926f`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x180088d95`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1800890ca`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x180088d95`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1800890ca`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180088e10`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180088e10`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800894ce`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800895c0`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18008966b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800894ce`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800895c0`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18008966b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x18008945f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x18008945f`

## string_xrefs

- `0x18008904d`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`
- `0x180088fc7`: `UI During Binding`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CShellItem::BindToHandler(
        CShellItem *this,
        struct IBindCtx *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        void **a5)
{
  char *v6; // r15
  char *v7; // rsi
  int v8; // ebx
  int v9; // eax
  DWORD CurrentThreadId; // ebx
  HRESULT ApartmentType; // edi
  unsigned int v12; // edx
  GUID **v13; // r9
  __m128i *v14; // r8
  __int64 v15; // rax
  __m128i v16; // xmm1
  __int64 (__fastcall *v17)(CShellItem *, struct IBindCtx *, const struct _GUID *, const struct _GUID *, void **); // xmm6_8
  int v18; // r13d
  const struct _GUID *v19; // rbx
  const struct _GUID *v20; // r12
  __int64 v21; // rax
  __int64 (__fastcall *v22)(CShellItem *, struct IBindCtx *, const struct _GUID *, const struct _GUID *, void **); // xmm1_8
  void **v23; // r8
  int v24; // r15d
  CShellItem *v25; // rdx
  IUnknown **v26; // rbx
  __int64 v27; // rcx
  HWND v28; // rbx
  int (__fastcall ***v29)(_QWORD, GUID *, LPMALLOC *); // rcx
  CShellItem *v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  IUnknown **v33; // rbx
  int v34; // eax
  _WORD *v35; // rax
  int v36; // ecx
  void **v37; // r12
  IUnknown **v39; // rbx
  void (__stdcall *HeapMinimize)(IMalloc *); // rbx
  HWND UIWindow; // rax
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  CShellItem *v43; // r10
  int v44; // eax
  _WORD *v45; // rax
  unsigned __int16 *v46; // rax
  unsigned __int16 *v47; // rdx
  APTTYPE v48; // r8d
  __int64 v49; // rcx
  _WORD *v50; // rcx
  unsigned __int16 v51; // ax
  _WORD *v52; // rdx
  struct IMallocVtbl *lpVtbl; // rax
  APTTYPE v54; // eax
  int (__fastcall ***v55)(_QWORD, GUID *, LPMALLOC *); // rcx
  int v56; // ebx
  bool v57; // sf
  CShellItem *v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  int v64; // eax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 (__fastcall ***v72)(_QWORD, _QWORD, _QWORD); // rbx
  int cchValue; // [rsp+20h] [rbp-E0h]
  CShellItem *v74; // [rsp+40h] [rbp-C0h]
  __int64 Size; // [rsp+68h] [rbp-98h]
  LPMALLOC ppMalloc; // [rsp+80h] [rbp-80h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+88h] [rbp-78h] BYREF
  IUnknown *punk; // [rsp+90h] [rbp-70h] BYREF
  HWND phwnd; // [rsp+98h] [rbp-68h] BYREF
  APTTYPE pAptType; // [rsp+A0h] [rbp-60h] BYREF
  __int128 Buf1; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v85; // [rsp+B8h] [rbp-48h] BYREF
  __m128i v86; // [rsp+C8h] [rbp-38h]
  int v87; // [rsp+D8h] [rbp-28h]
  WCHAR Filename[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  *a5 = 0;
  v6 = (char *)this - 8;
  v74 = (CShellItem *)((char *)this - 8);
  v7 = (char *)this + 72;
  if ( this == (CShellItem *)8 )
    v7 = 0;
  v8 = *((_DWORD *)v7 + 11);
  if ( v8 == 2 )
    goto LABEL_6;
  v9 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_5;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v36 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v36;
  }
  else
  {
    v36 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v36 != 1 )
    goto LABEL_17;
  if ( v8 == 1 )
  {
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_17;
    }
    v9 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
    if ( v9 != 1 )
      goto LABEL_17;
  }
LABEL_6:
  if ( *((_DWORD *)v7 + 10) == -3 )
    goto LABEL_17;
  CurrentThreadId = 0;
  pAptType = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
  {
LABEL_13:
    if ( ApartmentType < 0 )
      goto LABEL_16;
    goto LABEL_14;
  }
  if ( pAptType == APTTYPE_MAINSTA || pAptType == APTTYPE_STA )
  {
    CurrentThreadId = GetCurrentThreadId();
  }
  else if ( pAptType != APTTYPE_MTA )
  {
    if ( pAptType != APTTYPE_NA )
      goto LABEL_13;
    CurrentThreadId = -1;
  }
LABEL_14:
  if ( CurrentThreadId != *((_DWORD *)v7 + 10) )
    ApartmentType = -2147417842;
LABEL_16:
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    goto LABEL_19;
  }
LABEL_17:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v7) )
    ApartmentType = 0;
LABEL_19:
  if ( ApartmentType < 0 )
  {
    v24 = ApartmentType;
    goto LABEL_74;
  }
  v12 = 0;
  v13 = &off_180686E60;
  while ( 1 )
  {
    if ( v12 >= 0x17 )
    {
      v24 = -2147221019;
      goto LABEL_74;
    }
    v14 = (__m128i *)(&off_180686E60 + 5 * (int)v12);
    v15 = *(_QWORD *)&a3->Data1 - *(_QWORD *)v14->m128i_i64[0];
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)v14->m128i_i64[0] )
      v15 = *(_QWORD *)a3->Data4 - *(_QWORD *)(v14->m128i_i64[0] + 8);
    if ( !v15 )
      break;
    ++v12;
  }
  v16 = *v14;
  v86 = v14[1];
  v17 = (__int64 (__fastcall *)(CShellItem *, struct IBindCtx *, const struct _GUID *, const struct _GUID *, void **))v14[2].m128i_i64[0];
  v18 = _mm_cvtsi128_si32(v86);
  v19 = a4;
  if ( (v18 & 8) != 0 )
    v20 = a4;
  else
    v20 = (const struct _GUID *)v86.m128i_i64[1];
  if ( v20 )
  {
    v21 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&a4->Data1;
    if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&a4->Data1 )
      v21 = *(_QWORD *)v20->Data4 - *(_QWORD *)a4->Data4;
    if ( !v21 )
      v18 |= 0x10u;
  }
  v22 = (__int64 (__fastcall *)(CShellItem *, struct IBindCtx *, const struct _GUID *, const struct _GUID *, void **))_mm_srli_si128(v16, 8).m128i_u64[0];
  if ( !v22 )
  {
    v23 = a5;
    *a5 = 0;
    v24 = -2147467262;
    v25 = v74;
    if ( (v18 & 3) == 0 )
      goto LABEL_83;
    v26 = (IUnknown **)((char *)v74 + 168);
    if ( !*((_QWORD *)v74 + 21) )
    {
LABEL_41:
      punk = 0;
      v28 = (HWND)((char *)v25 + 176);
      phwnd = (HWND)((char *)v25 + 176);
      if ( !*((_QWORD *)v25 + 22) )
      {
        *(_QWORD *)&Buf1 = *((_QWORD *)v25 + 17);
        v46 = (unsigned __int16 *)Buf1;
        *(_QWORD *)v28 = 0;
        if ( !v46 )
        {
LABEL_82:
          if ( v24 >= 0 )
            goto LABEL_70;
LABEL_83:
          if ( (v18 & 4) == 0 )
          {
LABEL_88:
            v37 = a5;
LABEL_72:
            v19 = a4;
            goto LABEL_73;
          }
          ppMalloc = 0;
          v39 = (IUnknown **)((char *)v25 + 168);
          if ( !*((_QWORD *)v25 + 21) )
          {
            punk = 0;
            if ( (*(int (__fastcall **)(CShellItem *, _QWORD, const GUID *, GUID *, IUnknown **))(*(_QWORD *)this + 24LL))(
                   this,
                   0,
                   &BHID_SFObject,
                   &GUID_000214e6_0000_0000_c000_000000000046,
                   &punk) < 0 )
              goto LABEL_87;
            IUnknown_Set(v39, punk);
            if ( *((_DWORD *)v74 + 52) )
              IUnknown_PrepareForCaching(*v39);
            ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          }
          if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, LPMALLOC *, GUID **))(*v39)->lpVtbl->QueryInterface)(
                 *v39,
                 &GUID_000214e6_0000_0000_c000_000000000046,
                 &ppMalloc,
                 v13) >= 0 )
          {
            HeapMinimize = ppMalloc->lpVtbl->HeapMinimize;
            UIWindow = BindCtx_GetUIWindow(a2);
            v24 = ((__int64 (__fastcall *)(LPMALLOC, HWND, const struct _GUID *, void **))HeapMinimize)(
                    ppMalloc,
                    UIWindow,
                    v20,
                    a5);
            ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
          }
LABEL_87:
          if ( v24 < 0 )
            goto LABEL_88;
LABEL_70:
          v37 = a5;
          if ( (v18 & 0x10) == 0 )
          {
            v72 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))*a5;
            v24 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*a5)(*a5, a4, a5);
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v72)[2])(v72);
          }
          goto LABEL_72;
        }
        v47 = v46;
        v48 = APTTYPE_NA;
        do
        {
          v49 = *v47;
          if ( !(_WORD)v49 )
            break;
          v48 += (int)v49;
          v47 = (unsigned __int16 *)((char *)v47 + v49);
        }
        while ( v47 );
        pAptType = v48;
        *(_QWORD *)pAptQualifier = CoTaskMemAlloc((unsigned int)v48);
        if ( !*(_QWORD *)pAptQualifier )
          goto LABEL_81;
        Size = 0;
        ppMalloc = 0;
        if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
        {
          Size = ((__int64 (__fastcall *)(LPMALLOC, _QWORD))ppMalloc->lpVtbl->GetSize)(
                   ppMalloc,
                   *(_QWORD *)pAptQualifier);
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        }
        memset_0(*(void **)pAptQualifier, 0, Size);
        memcpy_0(*(void **)pAptQualifier, (const void *)Buf1, (unsigned int)pAptType);
        v50 = *(_WORD **)pAptQualifier;
        v51 = **(_WORD **)pAptQualifier;
        if ( **(_WORD **)pAptQualifier )
        {
          do
          {
            v52 = v50;
            v50 = (_WORD *)((char *)v50 + v51);
            v51 = *v50;
          }
          while ( *v50 );
          *v52 = 0;
        }
        *(_QWORD *)v28 = 0;
        ppMalloc = 0;
        pAptType = (unsigned int)CDesktopFolder_CreateInstance(0, &GUID_000214e6_0000_0000_c000_000000000046, &ppMalloc);
        if ( pAptType >= APTTYPE_STA )
        {
          lpVtbl = ppMalloc->lpVtbl;
          if ( **(_WORD **)pAptQualifier )
            v54 = ((unsigned int (__fastcall *)(LPMALLOC, _QWORD, _QWORD, GUID *, HWND))lpVtbl->Free)(
                    ppMalloc,
                    *(_QWORD *)pAptQualifier,
                    0,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    v28);
          else
            v54 = ((unsigned int (__fastcall *)(LPMALLOC, GUID *, HWND))lpVtbl->QueryInterface)(
                    ppMalloc,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    v28);
          pAptType = v54;
          if ( v54 >= APTTYPE_STA )
          {
            if ( !*(_QWORD *)v28 )
              v54 = -2147467259;
            pAptType = v54;
          }
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        }
        CoTaskMemFree(*(LPVOID *)pAptQualifier);
        if ( pAptType < APTTYPE_STA )
          goto LABEL_81;
        if ( *((_DWORD *)v74 + 52) )
        {
          v55 = *(int (__fastcall ****)(_QWORD, GUID *, LPMALLOC *))v28;
          *(_QWORD *)&Buf1 = v55;
          if ( v55 )
          {
            ppMalloc = 0;
            if ( (**v55)(v55, &GUID_771e5917_5788_4a36_a276_b0ddbf8e4abf, &ppMalloc) >= 0
              || (*(_QWORD *)pAptQualifier = 0,
                  (**(int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *))Buf1)(
                    Buf1,
                    &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                    pAptQualifier) >= 0)
              && (v56 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const GUID *, GUID *, LPMALLOC *))(**(_QWORD **)pAptQualifier + 24LL))(
                          *(_QWORD *)pAptQualifier,
                          0,
                          &BHID_SFObject,
                          &GUID_771e5917_5788_4a36_a276_b0ddbf8e4abf,
                          &ppMalloc),
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier),
                  v57 = v56 < 0,
                  v28 = phwnd,
                  !v57) )
            {
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Alloc)(ppMalloc);
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
            }
          }
        }
      }
      if ( (***(__int64 (__fastcall ****)(_QWORD, GUID *, IUnknown **, GUID **))v28)(
             *(_QWORD *)v28,
             &GUID_000214e6_0000_0000_c000_000000000046,
             &punk,
             v13) >= 0 )
      {
        if ( (v18 & 1) == 0 )
          goto LABEL_79;
        v29 = *(int (__fastcall ****)(_QWORD, GUID *, LPMALLOC *))v28;
        v30 = v74;
        if ( *(_QWORD *)v28 )
        {
          Buf1 = 0;
          v45 = (_WORD *)*((_QWORD *)v74 + 18);
          if ( v45 && *v45 )
            goto LABEL_46;
          if ( (int)IUnknown_GetClassID(v29, &Buf1) < 0 || memcmp_0(&Buf1, &CLSID_ShellDesktop, 0x10u) )
          {
            v30 = v74;
            goto LABEL_46;
          }
        }
        else if ( *((_QWORD *)v74 + 20) )
        {
LABEL_46:
          if ( a2 )
            goto LABEL_77;
          v31 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_IShellFolder.Data1;
          if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_IShellFolder.Data1 )
            v31 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_IShellFolder.Data4;
          if ( !v31 )
            goto LABEL_53;
          v32 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_IShellFolder2.Data1;
          if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_IShellFolder2.Data1 )
            v32 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_IShellFolder2.Data4;
          if ( !v32 )
            goto LABEL_53;
          v59 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&GUID_711b2cfd_93d1_422b_bdf4_69be923f2449.Data1;
          if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&GUID_711b2cfd_93d1_422b_bdf4_69be923f2449.Data1 )
            v59 = *(_QWORD *)v20->Data4 - *(_QWORD *)GUID_711b2cfd_93d1_422b_bdf4_69be923f2449.Data4;
          if ( !v59 )
            goto LABEL_53;
          v60 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_ISearchBoxSettings.Data1;
          if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_ISearchBoxSettings.Data1 )
            v60 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_ISearchBoxSettings.Data4;
          if ( !v60 )
            goto LABEL_53;
          v61 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_ITopViewAwareItem.Data1;
          if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_ITopViewAwareItem.Data1 )
            v61 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_ITopViewAwareItem.Data4;
          if ( !v61 )
            goto LABEL_53;
          v62 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_INavigationRelatedItem.Data1;
          if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_INavigationRelatedItem.Data1 )
            v62 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_INavigationRelatedItem.Data4;
          if ( !v62 )
            goto LABEL_53;
          v63 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_IViewResultRelatedItem.Data1;
          if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_IViewResultRelatedItem.Data1 )
            v63 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_IViewResultRelatedItem.Data4;
          if ( v63 )
          {
LABEL_77:
            v34 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, struct IBindCtx *, const struct _GUID *, void **))punk->lpVtbl[1].Release)(
                    punk,
                    *((_QWORD *)v30 + 18),
                    a2,
                    v20,
                    a5);
          }
          else
          {
LABEL_53:
            *a5 = 0;
            v33 = (IUnknown **)((char *)v30 + 168);
            if ( !*((_QWORD *)v30 + 21) )
            {
              ppMalloc = 0;
              if ( punk )
                v64 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, GUID *, LPMALLOC *))punk->lpVtbl[1].Release)(
                        punk,
                        *((_QWORD *)v30 + 18),
                        0,
                        &GUID_000214e6_0000_0000_c000_000000000046,
                        &ppMalloc);
              else
                v64 = (*(__int64 (__fastcall **)(CShellItem *, _QWORD, const GUID *, GUID *, LPMALLOC *))(*(_QWORD *)this + 24LL))(
                        this,
                        0,
                        &BHID_SFObject,
                        &GUID_000214e6_0000_0000_c000_000000000046,
                        &ppMalloc);
              v24 = v64;
              if ( v64 < 0 )
                goto LABEL_89;
              IUnknown_Set(v33, (IUnknown *)ppMalloc);
              if ( *((_DWORD *)v74 + 52) )
                IUnknown_PrepareForCaching(*v33);
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
            }
            v34 = ((__int64 (__fastcall *)(IUnknown *, const struct _GUID *, void **))(*v33)->lpVtbl->QueryInterface)(
                    *v33,
                    v20,
                    a5);
          }
          goto LABEL_78;
        }
        v34 = CShellItem::_BindToParent(v74, a4, a5);
LABEL_78:
        v24 = v34;
LABEL_79:
        if ( v24 >= 0 )
        {
LABEL_80:
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          goto LABEL_81;
        }
LABEL_89:
        if ( (v18 & 2) != 0 )
        {
          AddRef = punk->lpVtbl[3].AddRef;
          phwnd = 0;
          ppMalloc = 0;
          v85 = *(_OWORD *)L"UI During Binding";
          v86 = *(__m128i *)L"g Binding";
          v87 = *(_DWORD *)L"g";
          if ( a2
            && ((int (__fastcall *)(struct IBindCtx *, __int128 *, LPMALLOC *))a2->lpVtbl->GetObjectParam)(
                 a2,
                 &v85,
                 &ppMalloc) >= 0 )
          {
            IUnknown_GetWindow((IUnknown *)ppMalloc, &phwnd);
            ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
          }
          v24 = ((__int64 (__fastcall *)(IUnknown *, HWND, __int64, char *, const struct _GUID *, _QWORD, void **))AddRef)(
                  punk,
                  phwnd,
                  1,
                  (char *)v74 + 144,
                  v20,
                  0,
                  a5);
        }
        goto LABEL_80;
      }
LABEL_81:
      v25 = v74;
      goto LABEL_82;
    }
    v27 = *((_QWORD *)v74 + 22);
    if ( v27 )
    {
      Buf1 = 0;
      v35 = (_WORD *)*((_QWORD *)v74 + 18);
      if ( !v35 || !*v35 )
      {
        if ( (int)IUnknown_GetClassID(v27, &Buf1) >= 0 && !memcmp_0(&Buf1, &CLSID_ShellDesktop, 0x10u) )
          goto LABEL_40;
        v23 = a5;
      }
    }
    else if ( !*((_QWORD *)v74 + 20) )
    {
      goto LABEL_40;
    }
    if ( (v18 & 1) != 0 && !a2 )
    {
      v65 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_IShellFolder.Data1;
      if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_IShellFolder.Data1 )
        v65 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_IShellFolder.Data4;
      if ( !v65 )
        goto LABEL_67;
      v66 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_IShellFolder2.Data1;
      if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_IShellFolder2.Data1 )
        v66 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_IShellFolder2.Data4;
      if ( !v66 )
        goto LABEL_67;
      v67 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&GUID_711b2cfd_93d1_422b_bdf4_69be923f2449.Data1;
      if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&GUID_711b2cfd_93d1_422b_bdf4_69be923f2449.Data1 )
        v67 = *(_QWORD *)v20->Data4 - *(_QWORD *)GUID_711b2cfd_93d1_422b_bdf4_69be923f2449.Data4;
      if ( !v67 )
        goto LABEL_67;
      v68 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_ISearchBoxSettings.Data1;
      if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_ISearchBoxSettings.Data1 )
        v68 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_ISearchBoxSettings.Data4;
      if ( !v68 )
        goto LABEL_67;
      v69 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_ITopViewAwareItem.Data1;
      if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_ITopViewAwareItem.Data1 )
        v69 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_ITopViewAwareItem.Data4;
      if ( !v69 )
        goto LABEL_67;
      v70 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_INavigationRelatedItem.Data1;
      if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_INavigationRelatedItem.Data1 )
        v70 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_INavigationRelatedItem.Data4;
      if ( !v70 )
        goto LABEL_67;
      v71 = *(_QWORD *)&v20->Data1 - *(_QWORD *)&IID_IViewResultRelatedItem.Data1;
      if ( *(_QWORD *)&v20->Data1 == *(_QWORD *)&IID_IViewResultRelatedItem.Data1 )
        v71 = *(_QWORD *)v20->Data4 - *(_QWORD *)IID_IViewResultRelatedItem.Data4;
      if ( !v71 )
      {
LABEL_67:
        *v23 = 0;
        if ( !*v26 )
        {
          ppMalloc = 0;
          v24 = (*(__int64 (__fastcall **)(CShellItem *, _QWORD, const GUID *, GUID *, LPMALLOC *))(*(_QWORD *)this
                                                                                                  + 24LL))(
                  this,
                  0,
                  &BHID_SFObject,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &ppMalloc);
          if ( v24 < 0 )
          {
LABEL_69:
            if ( v24 >= 0 )
              goto LABEL_70;
            goto LABEL_40;
          }
          IUnknown_Set(v26, (IUnknown *)ppMalloc);
          if ( *((_DWORD *)v74 + 52) )
            IUnknown_PrepareForCaching(*v26);
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        }
        v24 = ((__int64 (__fastcall *)(IUnknown *, const struct _GUID *))(*v26)->lpVtbl->QueryInterface)(*v26, v20);
        goto LABEL_69;
      }
    }
LABEL_40:
    v25 = v74;
    goto LABEL_41;
  }
  if ( v6 )
    v58 = this;
  else
    v58 = 0;
  v37 = a5;
  v24 = v22(v58, a2, a3, a4, a5);
LABEL_73:
  if ( (unsigned int)(v24 + 2147467263) <= 1 && v17 )
  {
    v43 = this;
    if ( !v74 )
      v43 = 0;
    v44 = v17(v43, a2, a3, v19, v37);
    if ( v44 >= 0 || !v18 )
      v24 = v44;
  }
LABEL_74:
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180088a70  push    rbp
0x180088a72  push    rbx
0x180088a73  push    rsi
0x180088a74  push    rdi
0x180088a75  push    r12
0x180088a77  push    r13
0x180088a79  push    r14
0x180088a7b  push    r15
0x180088a7d  lea     rbp, [rsp-218h]
0x180088a85  sub     rsp, 318h
0x180088a8c  movaps  [rsp+350h+var_50], xmm6
0x180088a94  mov     rax, cs:__security_cookie
0x180088a9b  xor     rax, rsp
0x180088a9e  mov     [rbp+250h+var_60], rax
0x180088aa5  mov     [rsp+350h+var_2F8], r9
0x180088aaa  mov     r14, r8
0x180088aad  mov     [rsp+350h+var_300], rdx
0x180088ab2  mov     [rsp+350h+var_2F0], rcx
0x180088ab7  mov     rax, [rbp+250h+arg_20]
0x180088abe  mov     [rsp+350h+var_308], rax
0x180088ac3  xor     r12d, r12d
0x180088ac6  mov     [rax], r12
0x180088ac9  lea     r15, [rcx-8]
0x180088acd  mov     [rsp+350h+var_310], r15
0x180088ad2  lea     rsi, [rcx+48h]
0x180088ad6  test    r15, r15
0x180088ad9  cmovz   rsi, r12
0x180088add  mov     [rsp+350h+var_2E0], rsi
0x180088ae2  mov     ebx, [rsi+2Ch]
0x180088ae5  mov     edi, 2
0x180088aea  cmp     ebx, edi
0x180088aec  jz      short loc_180088B01
0x180088aee  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180088af4  test    eax, eax
0x180088af6  jz      loc_180088DD4
0x180088afc  cmp     eax, 1
0x180088aff  jnz     short loc_180088B72
0x180088b01  cmp     dword ptr [rsi+28h], 0FFFFFFFDh
0x180088b05  jz      short loc_180088B72
0x180088b07  mov     ebx, r12d
0x180088b0a  mov     [rbp+250h+pAptType], r12d
0x180088b0e  mov     [rbp+250h+pAptQualifier], r12d
0x180088b12  lea     rdx, [rbp+250h+pAptQualifier]; pAptQualifier
0x180088b16  lea     rcx, [rbp+250h+pAptType]; pAptType
0x180088b1a  call    cs:__imp_CoGetApartmentType
0x180088b21  nop     dword ptr [rax+rax+00h]
0x180088b26  mov     edi, eax
0x180088b28  test    eax, eax
0x180088b2a  js      short loc_180088B56
0x180088b2c  mov     eax, [rbp+250h+pAptType]
0x180088b2f  cmp     eax, 3
0x180088b32  jnz     short loc_180088B44
0x180088b34  call    cs:__imp_GetCurrentThreadId
0x180088b3b  nop     dword ptr [rax+rax+00h]
0x180088b40  mov     ebx, eax
0x180088b42  jmp     short loc_180088B5A
0x180088b44  test    eax, eax
0x180088b46  jz      short loc_180088B34
0x180088b48  sub     eax, 1
0x180088b4b  jz      short loc_180088B5A
0x180088b4d  cmp     eax, 1
0x180088b50  jz      loc_180089480
0x180088b56  test    edi, edi
0x180088b58  js      short loc_180088B63
0x180088b5a  cmp     ebx, [rsi+28h]
0x180088b5d  jnz     loc_180089620
0x180088b63  mov     rcx, [rbp+258h]; this
0x180088b6a  test    edi, edi
0x180088b6c  js      loc_18008904A
0x180088b72  mov     rcx, rsi; lpCriticalSection
0x180088b75  call    cs:__imp_TryEnterCriticalSection
0x180088b7c  nop     dword ptr [rax+rax+00h]
0x180088b81  mov     edi, 8001010Eh
0x180088b86  test    eax, eax
0x180088b88  cmovnz  edi, r12d
0x180088b8c  mov     [rsp+350h+var_2D8], edi
0x180088b90  test    edi, edi
0x180088b92  js      loc_180088E2F
0x180088b98  mov     edx, r12d
0x180088b9b  lea     r9, off_180686E60
0x180088ba2  cmp     edx, 17h
0x180088ba5  jnb     loc_1800897DB
0x180088bab  movsxd  rax, edx
0x180088bae  lea     rcx, [rax+rax*4]
0x180088bb2  lea     r8, [r9+rcx*8]
0x180088bb6  mov     rcx, [r8]
0x180088bb9  mov     rax, [r14]
0x180088bbc  sub     rax, [rcx]
0x180088bbf  jnz     short loc_180088BC9
0x180088bc1  mov     rax, [r14+8]
0x180088bc5  sub     rax, [rcx+8]
0x180088bc9  test    rax, rax
0x180088bcc  jz      short loc_180088BD2
0x180088bce  inc     edx
0x180088bd0  jmp     short loc_180088BA2
0x180088bd2  movups  xmm1, xmmword ptr [r8]
0x180088bd6  movups  xmm0, xmmword ptr [r8+10h]
0x180088bdb  movups  [rbp+250h+var_288], xmm0
0x180088bdf  movsd   xmm6, qword ptr [r8+20h]
0x180088be5  movd    r13d, xmm0
0x180088bea  mov     rbx, [rsp+350h+var_2F8]
0x180088bef  test    r13b, 8
0x180088bf3  jz      loc_1800895F7
0x180088bf9  mov     r12, rbx
0x180088bfc  test    r12, r12
0x180088bff  jz      short loc_180088C1C
0x180088c01  mov     rax, [r12]
0x180088c05  sub     rax, [rbx]
0x180088c08  jnz     short loc_180088C13
0x180088c0a  mov     rax, [r12+8]
0x180088c0f  sub     rax, [rbx+8]
0x180088c13  test    rax, rax
0x180088c16  jnz     short loc_180088C1C
0x180088c18  or      r13d, 10h
0x180088c1c  psrldq  xmm1, 8
0x180088c21  movq    rax, xmm1
0x180088c26  test    rax, rax
0x180088c29  jnz     loc_18008937B
0x180088c2f  mov     r8, [rsp+350h+var_308]
0x180088c34  mov     [r8], rax
0x180088c37  mov     r15d, 80004002h
0x180088c3d  mov     rdx, [rsp+350h+var_310]
0x180088c42  test    r13b, 3
0x180088c46  jz      loc_180088F19
0x180088c4c  lea     rbx, [rdx+0A8h]
0x180088c53  cmp     [rbx], rax
0x180088c56  jz      short loc_180088C88
0x180088c58  mov     rcx, [rdx+0B0h]
0x180088c5f  test    rcx, rcx
0x180088c62  jnz     loc_180088D74
0x180088c68  cmp     [rdx+0A0h], rcx
0x180088c6f  jz      short loc_180088C83
0x180088c71  test    r13b, 1
0x180088c75  jz      short loc_180088C83
0x180088c77  cmp     [rsp+350h+var_300], 0
0x180088c7d  jz      loc_1800896A2
0x180088c83  mov     rdx, [rsp+350h+var_310]
0x180088c88  mov     [rbp+250h+punk], 0
0x180088c90  lea     rbx, [rdx+0B0h]
0x180088c97  mov     [rbp+250h+phwnd], rbx
0x180088c9b  cmp     qword ptr [rbx], 0
0x180088c9f  jz      loc_180089109
0x180088ca5  mov     rcx, [rbx]
0x180088ca8  mov     rax, [rcx]
0x180088cab  lea     r8, [rbp+250h+punk]
0x180088caf  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180088cb6  mov     rax, [rax]
0x180088cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088cbe  test    eax, eax
0x180088cc0  js      loc_180088F0B
0x180088cc6  test    r13b, 1
0x180088cca  jz      loc_180088EF2
0x180088cd0  mov     rcx, [rbx]
0x180088cd3  mov     rdx, [rsp+350h+var_310]
0x180088cd8  test    rcx, rcx
0x180088cdb  jnz     loc_1800890A9
0x180088ce1  cmp     [rdx+0A0h], rcx
0x180088ce8  jz      loc_180089362
0x180088cee  mov     r10, [rsp+350h+var_300]
0x180088cf3  test    r10, r10
0x180088cf6  jnz     loc_180088EC8
0x180088cfc  mov     rax, [r12]
0x180088d00  sub     rax, qword ptr cs:IID_IShellFolder.Data1
0x180088d07  jnz     short loc_180088D15
0x180088d09  mov     rax, [r12+8]
0x180088d0e  sub     rax, qword ptr cs:IID_IShellFolder.Data4
0x180088d15  test    rax, rax
0x180088d18  jz      short loc_180088D3C
0x180088d1a  mov     rax, [r12]
0x180088d1e  sub     rax, qword ptr cs:IID_IShellFolder2.Data1
0x180088d25  jnz     short loc_180088D33
0x180088d27  mov     rax, [r12+8]
0x180088d2c  sub     rax, qword ptr cs:IID_IShellFolder2.Data4
0x180088d33  test    rax, rax
0x180088d36  jnz     loc_1800893A8
0x180088d3c  mov     rax, [rsp+350h+var_308]
0x180088d41  mov     qword ptr [rax], 0
0x180088d48  lea     rbx, [rdx+0A8h]
0x180088d4f  cmp     qword ptr [rbx], 0
0x180088d53  jz      loc_180089577
0x180088d59  mov     rcx, [rbx]
0x180088d5c  mov     rax, [rcx]
0x180088d5f  mov     r8, [rsp+350h+var_308]
0x180088d64  mov     rdx, r12
0x180088d67  mov     rax, [rax]
0x180088d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d6f  jmp     loc_180088EEF
0x180088d74  xorps   xmm0, xmm0
0x180088d77  movups  [rbp+250h+Buf1], xmm0
0x180088d7b  mov     rax, [rdx+90h]
0x180088d82  test    rax, rax
0x180088d85  jz      short loc_180088D91
0x180088d87  cmp     word ptr [rax], 0
0x180088d8b  jnz     loc_180088C71
0x180088d91  lea     rdx, [rbp+250h+Buf1]
0x180088d95  call    cs:__imp_IUnknown_GetClassID
0x180088d9c  nop     dword ptr [rax+rax+00h]
0x180088da1  test    eax, eax
0x180088da3  js      short loc_180088DCA
0x180088da5  mov     r8d, 10h; Size
0x180088dab  lea     rdx, CLSID_ShellDesktop; Buf2
0x180088db2  lea     rcx, [rbp+250h+Buf1]; Buf1
0x180088db6  call    memcmp_0
0x180088dbb  xor     ecx, ecx
0x180088dbd  test    eax, eax
0x180088dbf  setz    cl
0x180088dc2  test    ecx, ecx
0x180088dc4  jnz     loc_180088C83
0x180088dca  mov     r8, [rsp+350h+var_308]
0x180088dcf  jmp     loc_180088C71
0x180088dd4  mov     r8d, 104h; nSize
0x180088dda  lea     rdx, [rbp+250h+Filename]; lpFilename
0x180088dde  xor     ecx, ecx; hModule
0x180088de0  call    cs:__imp_GetModuleFileNameW
0x180088de7  nop     dword ptr [rax+rax+00h]
0x180088dec  test    eax, eax
0x180088dee  jnz     loc_180089521
0x180088df4  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180088dfa  cmp     ecx, 1
0x180088dfd  jnz     loc_180088B72
0x180088e03  cmp     ebx, ecx
0x180088e05  jnz     loc_180088B01
0x180088e0b  mov     ecx, 10h
0x180088e10  call    cs:__imp_IsAppCompatModeEnabled
0x180088e17  nop     dword ptr [rax+rax+00h]
0x180088e1c  test    eax, eax
0x180088e1e  jz      loc_180089795
0x180088e24  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, edi; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180088e2a  jmp     loc_180088B72
0x180088e2f  mov     r15d, edi
0x180088e32  jmp     short loc_180088E86
0x180088e34  mov     qword ptr [r8], 0
0x180088e3b  cmp     qword ptr [rbx], 0
0x180088e3f  jz      loc_18008948A
0x180088e45  mov     rcx, [rbx]
0x180088e48  mov     rax, [rcx]
0x180088e4b  mov     rdx, r12
0x180088e4e  mov     rax, [rax]
0x180088e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e56  mov     r15d, eax
0x180088e59  test    r15d, r15d
0x180088e5c  js      loc_180088C83
0x180088e62  mov     r12, [rsp+350h+var_308]
0x180088e67  test    r13b, 10h
0x180088e6b  jz      loc_1800897AA
0x180088e71  mov     rbx, [rsp+350h+var_2F8]
0x180088e76  lea     eax, [r15+7FFFBFFFh]
0x180088e7d  cmp     eax, 1
0x180088e80  jbe     loc_180089063
0x180088e86  test    edi, edi
0x180088e88  js      short loc_180088E99
0x180088e8a  mov     rcx, rsi; lpCriticalSection
0x180088e8d  call    cs:__imp_LeaveCriticalSection
0x180088e94  nop     dword ptr [rax+rax+00h]
0x180088e99  mov     eax, r15d
0x180088e9c  mov     rcx, [rbp+250h+var_60]
0x180088ea3  xor     rcx, rsp; StackCookie
0x180088ea6  call    __security_check_cookie
0x180088eab  movaps  xmm6, [rsp+350h+var_50]
0x180088eb3  add     rsp, 318h
0x180088eba  pop     r15
0x180088ebc  pop     r14
0x180088ebe  pop     r13
0x180088ec0  pop     r12
0x180088ec2  pop     rdi
0x180088ec3  pop     rsi
0x180088ec4  pop     rbx
0x180088ec5  pop     rbp
0x180088ec6  retn
0x180088ec8  mov     rcx, [rbp+250h+punk]
0x180088ecc  mov     rax, [rcx]
0x180088ecf  mov     r8, [rsp+350h+var_308]
0x180088ed4  mov     qword ptr [rsp+350h+cchValue], r8
0x180088ed9  mov     r9, r12
0x180088edc  mov     r8, r10
0x180088edf  mov     rdx, [rdx+90h]
0x180088ee6  mov     rax, [rax+28h]
0x180088eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088eef  mov     r15d, eax
0x180088ef2  test    r15d, r15d
0x180088ef5  js      loc_180088FA7
0x180088efb  mov     rcx, [rbp+250h+punk]
0x180088eff  mov     rax, [rcx]
0x180088f02  mov     rax, [rax+10h]
0x180088f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f0b  mov     rdx, [rsp+350h+var_310]
0x180088f10  test    r15d, r15d
0x180088f13  jns     loc_180088E62
0x180088f19  test    r13b, 4
0x180088f1d  jz      short loc_180088F9D
0x180088f1f  mov     [rbp+250h+ppMalloc], 0
0x180088f27  lea     rbx, [rdx+0A8h]
0x180088f2e  cmp     qword ptr [rbx], 0
0x180088f32  jz      loc_18008962A
0x180088f38  mov     rcx, [rbx]
0x180088f3b  mov     rax, [rcx]
0x180088f3e  lea     r8, [rbp+250h+ppMalloc]
0x180088f42  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180088f49  mov     rax, [rax]
0x180088f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
