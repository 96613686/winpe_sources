# CShellItem::BindToHandler(IBindCtx *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800dc2e0`
- end: `0x1800dcff3`
- name: `?BindToHandler@CShellItem@@UEAAJPEAUIBindCtx@@AEBU_GUID@@1PEAPEAX@Z`
- size: `3347`
- prototype: `__int64 __fastcall(CShellItem *__hidden this, struct IBindCtx *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800cfc30`
- `0x1800d60a0`
- `0x1800dc2e0`
- `0x1800dd190`
- `0x1800e6df0`
- `0x1800e7470`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800dc638`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800dc638`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800dcd65`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800dcd65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dc6d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dc6d9`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800dc3d9`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800dc3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dc39e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dc39e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc983`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800dc9aa`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800dc9aa`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800dc38a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800dc38a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dca9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dca9f`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1800dc5f3`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1800dc90f`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1800dc5f3`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1800dc90f`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800dc662`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800dc662`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800dccf2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800dcdd8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800dce7d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800dccf2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800dcdd8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800dce7d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x1800dcc89`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x1800dcc89`

## string_xrefs

- `0x1800dc892`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`
- `0x1800dc80c`: `UI During Binding`

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
  v13 = &off_18066C990;
  while ( 1 )
  {
    if ( v12 >= 0x17 )
    {
      v24 = -2147221019;
      goto LABEL_74;
    }
    v14 = (__m128i *)(&off_18066C990 + 5 * (int)v12);
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
0x1800dc2e0  push    rbp
0x1800dc2e2  push    rbx
0x1800dc2e3  push    rsi
0x1800dc2e4  push    rdi
0x1800dc2e5  push    r12
0x1800dc2e7  push    r13
0x1800dc2e9  push    r14
0x1800dc2eb  push    r15
0x1800dc2ed  lea     rbp, [rsp-218h]
0x1800dc2f5  sub     rsp, 318h
0x1800dc2fc  movaps  [rsp+350h+var_50], xmm6
0x1800dc304  mov     rax, cs:__security_cookie
0x1800dc30b  xor     rax, rsp
0x1800dc30e  mov     [rbp+250h+var_60], rax
0x1800dc315  mov     [rsp+350h+var_2F8], r9
0x1800dc31a  mov     r14, r8
0x1800dc31d  mov     [rsp+350h+var_300], rdx
0x1800dc322  mov     [rsp+350h+var_2F0], rcx
0x1800dc327  mov     rax, [rbp+250h+arg_20]
0x1800dc32e  mov     [rsp+350h+var_308], rax
0x1800dc333  xor     r12d, r12d
0x1800dc336  mov     [rax], r12
0x1800dc339  lea     r15, [rcx-8]
0x1800dc33d  mov     [rsp+350h+var_310], r15
0x1800dc342  lea     rsi, [rcx+48h]
0x1800dc346  test    r15, r15
0x1800dc349  cmovz   rsi, r12
0x1800dc34d  mov     [rsp+350h+var_2E0], rsi
0x1800dc352  mov     ebx, [rsi+2Ch]
0x1800dc355  mov     edi, 2
0x1800dc35a  cmp     ebx, edi
0x1800dc35c  jz      short loc_1800DC371
0x1800dc35e  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dc364  test    eax, eax
0x1800dc366  jz      loc_1800DC62C
0x1800dc36c  cmp     eax, 1
0x1800dc36f  jnz     short loc_1800DC3D6
0x1800dc371  cmp     dword ptr [rsi+28h], 0FFFFFFFDh
0x1800dc375  jz      short loc_1800DC3D6
0x1800dc377  mov     ebx, r12d
0x1800dc37a  mov     [rbp+250h+pAptType], r12d
0x1800dc37e  mov     [rbp+250h+pAptQualifier], r12d
0x1800dc382  lea     rdx, [rbp+250h+pAptQualifier]; pAptQualifier
0x1800dc386  lea     rcx, [rbp+250h+pAptType]; pAptType
0x1800dc38a  call    cs:__imp_CoGetApartmentType
0x1800dc390  mov     edi, eax
0x1800dc392  test    eax, eax
0x1800dc394  js      short loc_1800DC3BA
0x1800dc396  mov     eax, [rbp+250h+pAptType]
0x1800dc399  cmp     eax, 3
0x1800dc39c  jnz     short loc_1800DC3A8
0x1800dc39e  call    cs:__imp_GetCurrentThreadId
0x1800dc3a4  mov     ebx, eax
0x1800dc3a6  jmp     short loc_1800DC3BE
0x1800dc3a8  test    eax, eax
0x1800dc3aa  jz      short loc_1800DC39E
0x1800dc3ac  sub     eax, 1
0x1800dc3af  jz      short loc_1800DC3BE
0x1800dc3b1  cmp     eax, 1
0x1800dc3b4  jz      loc_1800DCCA4
0x1800dc3ba  test    edi, edi
0x1800dc3bc  js      short loc_1800DC3C7
0x1800dc3be  cmp     ebx, [rsi+28h]
0x1800dc3c1  jnz     loc_1800DCE32
0x1800dc3c7  mov     rcx, [rbp+258h]; this
0x1800dc3ce  test    edi, edi
0x1800dc3d0  js      loc_1800DC88F
0x1800dc3d6  mov     rcx, rsi; lpCriticalSection
0x1800dc3d9  call    cs:__imp_TryEnterCriticalSection
0x1800dc3df  mov     edi, 8001010Eh
0x1800dc3e4  test    eax, eax
0x1800dc3e6  cmovnz  edi, r12d
0x1800dc3ea  mov     [rsp+350h+var_2D8], edi
0x1800dc3ee  test    edi, edi
0x1800dc3f0  js      loc_1800DC67B
0x1800dc3f6  mov     edx, r12d
0x1800dc3f9  lea     r9, off_18066C990
0x1800dc400  cmp     edx, 17h
0x1800dc403  jnb     loc_1800DCFE7
0x1800dc409  movsxd  rax, edx
0x1800dc40c  lea     rcx, [rax+rax*4]
0x1800dc410  lea     r8, [r9+rcx*8]
0x1800dc414  mov     rcx, [r8]
0x1800dc417  mov     rax, [r14]
0x1800dc41a  sub     rax, [rcx]
0x1800dc41d  jnz     short loc_1800DC427
0x1800dc41f  mov     rax, [r14+8]
0x1800dc423  sub     rax, [rcx+8]
0x1800dc427  test    rax, rax
0x1800dc42a  jz      short loc_1800DC430
0x1800dc42c  inc     edx
0x1800dc42e  jmp     short loc_1800DC400
0x1800dc430  movups  xmm1, xmmword ptr [r8]
0x1800dc434  movups  xmm0, xmmword ptr [r8+10h]
0x1800dc439  movups  [rbp+250h+var_288], xmm0
0x1800dc43d  movsd   xmm6, qword ptr [r8+20h]
0x1800dc443  movd    r13d, xmm0
0x1800dc448  mov     rbx, [rsp+350h+var_2F8]
0x1800dc44d  test    r13b, 8
0x1800dc451  jz      loc_1800DCE09
0x1800dc457  mov     r12, rbx
0x1800dc45a  test    r12, r12
0x1800dc45d  jz      short loc_1800DC47A
0x1800dc45f  mov     rax, [r12]
0x1800dc463  sub     rax, [rbx]
0x1800dc466  jnz     short loc_1800DC471
0x1800dc468  mov     rax, [r12+8]
0x1800dc46d  sub     rax, [rbx+8]
0x1800dc471  test    rax, rax
0x1800dc474  jnz     short loc_1800DC47A
0x1800dc476  or      r13d, 10h
0x1800dc47a  psrldq  xmm1, 8
0x1800dc47f  movq    rax, xmm1
0x1800dc484  test    rax, rax
0x1800dc487  jnz     loc_1800DCBA5
0x1800dc48d  mov     r8, [rsp+350h+var_308]
0x1800dc492  mov     [r8], rax
0x1800dc495  mov     r15d, 80004002h
0x1800dc49b  mov     rdx, [rsp+350h+var_310]
0x1800dc4a0  test    r13b, 3
0x1800dc4a4  jz      loc_1800DC75E
0x1800dc4aa  lea     rbx, [rdx+0A8h]
0x1800dc4b1  cmp     [rbx], rax
0x1800dc4b4  jz      short loc_1800DC4E6
0x1800dc4b6  mov     rcx, [rdx+0B0h]
0x1800dc4bd  test    rcx, rcx
0x1800dc4c0  jnz     loc_1800DC5D2
0x1800dc4c6  cmp     [rdx+0A0h], rcx
0x1800dc4cd  jz      short loc_1800DC4E1
0x1800dc4cf  test    r13b, 1
0x1800dc4d3  jz      short loc_1800DC4E1
0x1800dc4d5  cmp     [rsp+350h+var_300], 0
0x1800dc4db  jz      loc_1800DCEAE
0x1800dc4e1  mov     rdx, [rsp+350h+var_310]
0x1800dc4e6  mov     [rbp+250h+punk], 0
0x1800dc4ee  lea     rbx, [rdx+0B0h]
0x1800dc4f5  mov     [rbp+250h+phwnd], rbx
0x1800dc4f9  cmp     qword ptr [rbx], 0
0x1800dc4fd  jz      loc_1800DC948
0x1800dc503  mov     rcx, [rbx]
0x1800dc506  mov     rax, [rcx]
0x1800dc509  lea     r8, [rbp+250h+punk]
0x1800dc50d  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800dc514  mov     rax, [rax]
0x1800dc517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc51c  test    eax, eax
0x1800dc51e  js      loc_1800DC750
0x1800dc524  test    r13b, 1
0x1800dc528  jz      loc_1800DC737
0x1800dc52e  mov     rcx, [rbx]
0x1800dc531  mov     rdx, [rsp+350h+var_310]
0x1800dc536  test    rcx, rcx
0x1800dc539  jnz     loc_1800DC8EE
0x1800dc53f  cmp     [rdx+0A0h], rcx
0x1800dc546  jz      loc_1800DCB8C
0x1800dc54c  mov     r10, [rsp+350h+var_300]
0x1800dc551  test    r10, r10
0x1800dc554  jnz     loc_1800DC70D
0x1800dc55a  mov     rax, [r12]
0x1800dc55e  sub     rax, qword ptr cs:IID_IShellFolder.Data1
0x1800dc565  jnz     short loc_1800DC573
0x1800dc567  mov     rax, [r12+8]
0x1800dc56c  sub     rax, qword ptr cs:IID_IShellFolder.Data4
0x1800dc573  test    rax, rax
0x1800dc576  jz      short loc_1800DC59A
0x1800dc578  mov     rax, [r12]
0x1800dc57c  sub     rax, qword ptr cs:IID_IShellFolder2.Data1
0x1800dc583  jnz     short loc_1800DC591
0x1800dc585  mov     rax, [r12+8]
0x1800dc58a  sub     rax, qword ptr cs:IID_IShellFolder2.Data4
0x1800dc591  test    rax, rax
0x1800dc594  jnz     loc_1800DCBD2
0x1800dc59a  mov     rax, [rsp+350h+var_308]
0x1800dc59f  mov     qword ptr [rax], 0
0x1800dc5a6  lea     rbx, [rdx+0A8h]
0x1800dc5ad  cmp     qword ptr [rbx], 0
0x1800dc5b1  jz      loc_1800DCD8F
0x1800dc5b7  mov     rcx, [rbx]
0x1800dc5ba  mov     rax, [rcx]
0x1800dc5bd  mov     r8, [rsp+350h+var_308]
0x1800dc5c2  mov     rdx, r12
0x1800dc5c5  mov     rax, [rax]
0x1800dc5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc5cd  jmp     loc_1800DC734
0x1800dc5d2  xorps   xmm0, xmm0
0x1800dc5d5  movups  [rbp+250h+Buf1], xmm0
0x1800dc5d9  mov     rax, [rdx+90h]
0x1800dc5e0  test    rax, rax
0x1800dc5e3  jz      short loc_1800DC5EF
0x1800dc5e5  cmp     word ptr [rax], 0
0x1800dc5e9  jnz     loc_1800DC4CF
0x1800dc5ef  lea     rdx, [rbp+250h+Buf1]
0x1800dc5f3  call    cs:__imp_IUnknown_GetClassID
0x1800dc5f9  test    eax, eax
0x1800dc5fb  js      short loc_1800DC622
0x1800dc5fd  mov     r8d, 10h; Size
0x1800dc603  lea     rdx, CLSID_ShellDesktop; Buf2
0x1800dc60a  lea     rcx, [rbp+250h+Buf1]; Buf1
0x1800dc60e  call    memcmp_0
0x1800dc613  xor     ecx, ecx
0x1800dc615  test    eax, eax
0x1800dc617  setz    cl
0x1800dc61a  test    ecx, ecx
0x1800dc61c  jnz     loc_1800DC4E1
0x1800dc622  mov     r8, [rsp+350h+var_308]
0x1800dc627  jmp     loc_1800DC4CF
0x1800dc62c  mov     r8d, 104h; nSize
0x1800dc632  lea     rdx, [rbp+250h+Filename]; lpFilename
0x1800dc636  xor     ecx, ecx; hModule
0x1800dc638  call    cs:__imp_GetModuleFileNameW
0x1800dc63e  test    eax, eax
0x1800dc640  jnz     loc_1800DCD3F
0x1800dc646  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dc64c  cmp     ecx, 1
0x1800dc64f  jnz     loc_1800DC3D6
0x1800dc655  cmp     ebx, ecx
0x1800dc657  jnz     loc_1800DC371
0x1800dc65d  mov     ecx, 10h
0x1800dc662  call    cs:__imp_IsAppCompatModeEnabled
0x1800dc668  test    eax, eax
0x1800dc66a  jz      loc_1800DCFA1
0x1800dc670  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, edi; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800dc676  jmp     loc_1800DC3D6
0x1800dc67b  mov     r15d, edi
0x1800dc67e  jmp     short loc_1800DC6D2
0x1800dc680  mov     qword ptr [r8], 0
0x1800dc687  cmp     qword ptr [rbx], 0
0x1800dc68b  jz      loc_1800DCCAE
0x1800dc691  mov     rcx, [rbx]
0x1800dc694  mov     rax, [rcx]
0x1800dc697  mov     rdx, r12
0x1800dc69a  mov     rax, [rax]
0x1800dc69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc6a2  mov     r15d, eax
0x1800dc6a5  test    r15d, r15d
0x1800dc6a8  js      loc_1800DC4E1
0x1800dc6ae  mov     r12, [rsp+350h+var_308]
0x1800dc6b3  test    r13b, 10h
0x1800dc6b7  jz      loc_1800DCFB6
0x1800dc6bd  mov     rbx, [rsp+350h+var_2F8]
0x1800dc6c2  lea     eax, [r15+7FFFBFFFh]
0x1800dc6c9  cmp     eax, 1
0x1800dc6cc  jbe     loc_1800DC8A8
0x1800dc6d2  test    edi, edi
0x1800dc6d4  js      short loc_1800DC6DF
0x1800dc6d6  mov     rcx, rsi; lpCriticalSection
0x1800dc6d9  call    cs:__imp_LeaveCriticalSection
0x1800dc6df  mov     eax, r15d
0x1800dc6e2  mov     rcx, [rbp+250h+var_60]
0x1800dc6e9  xor     rcx, rsp; StackCookie
0x1800dc6ec  call    __security_check_cookie
0x1800dc6f1  movaps  xmm6, [rsp+350h+var_50]
0x1800dc6f9  add     rsp, 318h
0x1800dc700  pop     r15
0x1800dc702  pop     r14
0x1800dc704  pop     r13
0x1800dc706  pop     r12
0x1800dc708  pop     rdi
0x1800dc709  pop     rsi
0x1800dc70a  pop     rbx
0x1800dc70b  pop     rbp
0x1800dc70c  retn
0x1800dc70d  mov     rcx, [rbp+250h+punk]
0x1800dc711  mov     rax, [rcx]
0x1800dc714  mov     r8, [rsp+350h+var_308]
0x1800dc719  mov     qword ptr [rsp+350h+cchValue], r8
0x1800dc71e  mov     r9, r12
0x1800dc721  mov     r8, r10
0x1800dc724  mov     rdx, [rdx+90h]
0x1800dc72b  mov     rax, [rax+28h]
0x1800dc72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc734  mov     r15d, eax
0x1800dc737  test    r15d, r15d
0x1800dc73a  js      loc_1800DC7EC
0x1800dc740  mov     rcx, [rbp+250h+punk]
0x1800dc744  mov     rax, [rcx]
0x1800dc747  mov     rax, [rax+10h]
0x1800dc74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc750  mov     rdx, [rsp+350h+var_310]
0x1800dc755  test    r15d, r15d
0x1800dc758  jns     loc_1800DC6AE
0x1800dc75e  test    r13b, 4
0x1800dc762  jz      short loc_1800DC7E2
0x1800dc764  mov     [rbp+250h+ppMalloc], 0
0x1800dc76c  lea     rbx, [rdx+0A8h]
0x1800dc773  cmp     qword ptr [rbx], 0
0x1800dc777  jz      loc_1800DCE3C
0x1800dc77d  mov     rcx, [rbx]
0x1800dc780  mov     rax, [rcx]
0x1800dc783  lea     r8, [rbp+250h+ppMalloc]
0x1800dc787  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800dc78e  mov     rax, [rax]
0x1800dc791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc796  test    eax, eax
0x1800dc798  js      short loc_1800DC7D9
0x1800dc79a  mov     rax, [rbp+250h+ppMalloc]
0x1800dc79e  mov     rcx, [rax]
0x1800dc7a1  mov     rbx, [rcx+40h]
0x1800dc7a5  mov     rcx, [rsp+350h+var_300]; struct IBindCtx *
0x1800dc7aa  call    ?BindCtx_GetUIWindow@@YAPEAUHWND__@@PEAUIBindCtx@@@Z; BindCtx_GetUIWindow(IBindCtx *)
  ... truncated ...
```
