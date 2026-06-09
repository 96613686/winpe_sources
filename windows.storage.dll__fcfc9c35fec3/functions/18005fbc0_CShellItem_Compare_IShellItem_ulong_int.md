# CShellItem::Compare(IShellItem *,ulong,int *)

- ea: `0x18005fbc0`
- end: `0x180060718`
- name: `?Compare@CShellItem@@UEAAJPEAUIShellItem@@KPEAH@Z`
- size: `2904`
- prototype: `int(CShellItem *__hidden this, struct IShellItem *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18005ee50`
- `0x18005f600`
- `0x18005f6c0`
- `0x18005fa70`
- `0x18005fbc0`
- `0x180061860`
- `0x1800625e0`
- `0x180064ad0`
- `0x1800688f0`
- `0x1800899a4`
- `0x18008a190`
- `0x1800b4100`
- `0x1801b1844`
- `0x1803b1f60`
- `0x1803b69b9`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800604e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800604e6`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180060633`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180060633`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060253`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060253`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18005fcb8`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18005fcb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fc76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fc76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180060179`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180060179`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18005fc5a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18005fc5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006019a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800601b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006048a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060569`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006019a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800601b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006048a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060569`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18006065c`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18006065c`

## string_xrefs

- `0x180060535`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CShellItem::Compare(CShellItem *this, struct IUnknown *a2, int a3, int *a4)
{
  CShellItem *v5; // r15
  char *v6; // r12
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  int DebugInfo_high; // ebx
  int v9; // eax
  DWORD CurrentThreadId; // ebx
  HRESULT ApartmentType; // r13d
  struct IShellItem *v12; // rdi
  void **v13; // rsi
  int ItemFromObjectWorker; // ebx
  __int64 v15; // rsi
  int (__fastcall ***v16)(_QWORD, GUID *, APTTYPE *); // rbx
  int v17; // esi
  int v18; // esi
  int v19; // edi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r9
  const WCHAR *v23; // rcx
  const WCHAR *v24; // r8
  __int64 v25; // rdx
  int v26; // eax
  __int64 *v27; // rcx
  __int64 *v28; // rcx
  unsigned __int16 *v30; // r12
  unsigned __int16 *v31; // r15
  HRESULT v32; // ebx
  unsigned __int16 *v33; // rdx
  int v34; // r10d
  int v35; // r11d
  __int64 v36; // r9
  __int64 v37; // rcx
  int v38; // r8d
  unsigned __int16 *v39; // rdx
  __int64 v40; // rcx
  __int64 *v41; // rbx
  __int64 *v42; // rcx
  const struct _ITEMIDLIST_RELATIVE *v43; // rcx
  const ITEMIDLIST *v44; // rax
  ITEMIDLIST *v45; // r15
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-D0h]
  struct _ITEMIDLIST_RELATIVE **v48; // [rsp+38h] [rbp-C8h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+58h] [rbp-A8h] BYREF
  APTTYPE pAptType[2]; // [rsp+60h] [rbp-A0h] BYREF
  CShellItem *v52; // [rsp+68h] [rbp-98h] BYREF
  int (__fastcall ***v53)(_QWORD, GUID *, APTTYPEQUALIFIER *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  int (__fastcall ***v55)(_QWORD, GUID *, APTTYPE *); // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v57; // [rsp+90h] [rbp-70h] BYREF
  __int64 v58; // [rsp+98h] [rbp-68h] BYREF
  LPCWCH lpString2; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-58h]
  __int64 v61; // [rsp+B0h] [rbp-50h]
  LPCWCH lpString1; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+C8h] [rbp-38h]
  WCHAR Filename[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  LODWORD(v54) = a3;
  v5 = this;
  v52 = this;
  *a4 = 0;
  v6 = (char *)this - 8;
  v48 = (struct _ITEMIDLIST_RELATIVE **)((char *)this - 8);
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  if ( this == (CShellItem *)8 )
    v7 = 0;
  lpCriticalSection = v7;
  DebugInfo_high = HIDWORD(v7[1].DebugInfo);
  if ( DebugInfo_high != 2 )
  {
    v9 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
      goto LABEL_5;
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      if ( FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1 )
        goto LABEL_133;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 1;
    }
    else if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess != 1 )
    {
      goto LABEL_16;
    }
    if ( DebugInfo_high == 1 )
    {
      if ( !(unsigned int)IsAppCompatModeEnabled(16) )
      {
        v9 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
        if ( v9 != 1 )
          goto LABEL_16;
        goto LABEL_6;
      }
LABEL_133:
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_16;
    }
  }
LABEL_6:
  if ( LODWORD(v7[1].DebugInfo) != -3 )
  {
    CurrentThreadId = 0;
    pAptType[0] = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(pAptType, pAptQualifier);
    if ( ApartmentType >= 0 )
    {
      if ( pAptType[0] == APTTYPE_MAINSTA || pAptType[0] == APTTYPE_STA )
      {
        CurrentThreadId = GetCurrentThreadId();
      }
      else if ( pAptType[0] == APTTYPE_NA )
      {
        CurrentThreadId = -1;
      }
      if ( CurrentThreadId != LODWORD(v7[1].DebugInfo) )
        ApartmentType = -2147417842;
    }
    if ( ApartmentType < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
        (const char *)(unsigned int)ApartmentType,
        bIgnoreCase);
      goto LABEL_18;
    }
  }
LABEL_16:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection(v7) )
    ApartmentType = 0;
LABEL_18:
  if ( ApartmentType >= 0 )
  {
    v12 = (struct IShellItem *)v5;
    if ( !v6 )
      v12 = 0;
    if ( v12 && a2 )
    {
      if ( v12 == (struct IShellItem *)a2 )
      {
LABEL_107:
        ItemFromObjectWorker = 0;
        v7 = lpCriticalSection;
        goto LABEL_77;
      }
      *(_QWORD *)pAptQualifier = 0;
      v53 = 0;
      if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, APTTYPEQUALIFIER *))v12->lpVtbl->QueryInterface)(
             v12,
             &GUID_00000000_0000_0000_c000_000000000046,
             pAptQualifier) < 0 )
        goto LABEL_27;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_00000000_0000_0000_c000_000000000046,
             &v53) >= 0 )
      {
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *)))(*v53)[2])(v53);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
        if ( *(int (__fastcall ****)(_QWORD, GUID *, APTTYPEQUALIFIER *))pAptQualifier != v53 )
          goto LABEL_27;
        goto LABEL_107;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
    }
LABEL_27:
    v53 = 0;
    v13 = (void **)((char *)v5 + 168);
    if ( !*((_QWORD *)v5 + 21) )
    {
      v43 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)v5 + 16);
      *v13 = 0;
      ItemFromObjectWorker = -2147024809;
      if ( v43 )
      {
        v44 = (const ITEMIDLIST *)ILCloneParent(v43);
        v45 = (ITEMIDLIST *)v44;
        if ( !v44 )
        {
          ItemFromObjectWorker = -2147024882;
          goto LABEL_76;
        }
        ItemFromObjectWorker = SHBindToObject(0, v44, 0, &GUID_000214e6_0000_0000_c000_000000000046, v13);
        CoTaskMemFree(v45);
        v5 = v52;
      }
      if ( ItemFromObjectWorker < 0 )
        goto LABEL_76;
      if ( *((_DWORD *)v5 + 50) )
        IUnknown_PrepareForCaching((struct IUnknown *)*v13);
    }
    ItemFromObjectWorker = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))*v13)(
                             *v13,
                             &GUID_000214e6_0000_0000_c000_000000000046,
                             &v53);
    if ( ItemFromObjectWorker < 0 )
    {
LABEL_76:
      v7 = lpCriticalSection;
      goto LABEL_77;
    }
    v15 = 0;
    v58 = 0;
    ItemFromObjectWorker = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                             a2,
                             &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                             &v58);
    if ( ItemFromObjectWorker < 0 )
    {
LABEL_75:
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *)))(*v53)[2])(v53);
      goto LABEL_76;
    }
    v55 = 0;
    pv = 0;
    v57 = 0;
    ItemFromObjectWorker = (*(__int64 (__fastcall **)(__int64, LPVOID *, int (__fastcall ****)(_QWORD, GUID *, APTTYPE *), LPVOID *))(*(_QWORD *)v58 + 32LL))(
                             v58,
                             &pv,
                             &v55,
                             &v57);
    if ( ItemFromObjectWorker < 0 )
    {
LABEL_74:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      goto LABEL_75;
    }
    if ( !*((_QWORD *)v6 + 20) && !(unsigned int)CShellItem::_IsDesktop((CShellItem *)v6) )
    {
      ItemFromObjectWorker = SHGetIDListFromObject(*((IUnknown **)v6 + 22), (LPITEMIDLIST *)v6 + 20);
      if ( ItemFromObjectWorker < 0 )
        goto LABEL_73;
    }
    if ( v53 )
    {
      v16 = v55;
      if ( v55 )
      {
        if ( v53 == (int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *))v55 )
          goto LABEL_38;
        *(_QWORD *)pAptQualifier = 0;
        *(_QWORD *)pAptType = 0;
        if ( (**v53)(v53, &GUID_00000000_0000_0000_c000_000000000046, pAptQualifier) >= 0 )
        {
          if ( (**v16)(v16, &GUID_00000000_0000_0000_c000_000000000046, pAptType) < 0 )
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
          }
          else
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
            if ( *(_QWORD *)pAptQualifier == *(_QWORD *)pAptType )
              goto LABEL_38;
          }
        }
      }
    }
    v30 = (unsigned __int16 *)*((_QWORD *)v5 + 19);
    v31 = (unsigned __int16 *)pv;
    if ( pv != v30 )
    {
      if ( !pv || !v30 )
        goto LABEL_100;
      *(_QWORD *)pAptQualifier = 0;
      v32 = SHGetDesktopFolder((IShellFolder **)pAptQualifier);
      if ( v32 >= 0 )
      {
        if ( v30 == v31 )
        {
          v32 = 0;
        }
        else
        {
          v33 = v30;
          v34 = 0;
          v35 = 2;
          v36 = 2;
          do
          {
            v37 = *v33;
            if ( !(_WORD)v37 )
              break;
            v36 = (unsigned int)(v37 + v36);
            ++v34;
            v33 = (unsigned __int16 *)((char *)v33 + v37);
          }
          while ( v33 );
          v38 = 0;
          if ( v31 )
          {
            v39 = v31;
            do
            {
              v40 = *v39;
              if ( !(_WORD)v40 )
                break;
              v35 += v40;
              ++v38;
              v39 = (unsigned __int16 *)((char *)v39 + v40);
            }
            while ( v39 );
          }
          else
          {
            v35 = 0;
          }
          if ( v34 == v38 && (_DWORD)v36 == v35 && !memcmp_0(v30, v31, (unsigned int)v36) )
          {
            v32 = 0;
          }
          else
          {
            v41 = *(__int64 **)pAptQualifier;
            *(_QWORD *)pAptType = 0;
            if ( (***(int (__fastcall ****)(_QWORD, GUID *, APTTYPE *, __int64))pAptQualifier)(
                   *(_QWORD *)pAptQualifier,
                   &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                   pAptType,
                   v36) >= 0 )
            {
              v15 = 0x10000000;
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
            }
            v32 = (*(__int64 (__fastcall **)(__int64 *, __int64, unsigned __int16 *, unsigned __int16 *))(*v41 + 56))(
                    v41,
                    v15,
                    v30,
                    v31);
          }
        }
      }
      v42 = *(__int64 **)pAptQualifier;
      if ( *(_QWORD *)pAptQualifier )
      {
        *(_QWORD *)pAptQualifier = 0;
        (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
      }
      if ( v32 )
      {
LABEL_100:
        if ( !v48[17] )
        {
          if ( (unsigned int)CShellItem::_IsDesktop((CShellItem *)v48) )
          {
            SHILClone(v48[18], v48 + 17);
          }
          else
          {
            ItemFromObjectWorker = CShellItem::_EnsureParentIdList((CShellItem *)v48);
            if ( ItemFromObjectWorker < 0 )
              goto LABEL_73;
            ItemFromObjectWorker = SHILCombine(v48[20], v48[18], v48 + 17);
            if ( ItemFromObjectWorker < 0 )
              goto LABEL_73;
          }
        }
        *(_QWORD *)pAptQualifier = 0;
        if ( _GetIDListFromObjectWorker(a2, (struct _ITEMIDLIST_ABSOLUTE **)pAptQualifier) < 0 )
        {
          *(_QWORD *)pAptType = 0;
          ItemFromObjectWorker = _GetItemFromObjectWorker(
                                   a2,
                                   &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
                                   (void **)pAptType);
          if ( ItemFromObjectWorker < 0
            || (ItemFromObjectWorker = (*(__int64 (__fastcall **)(_QWORD, APTTYPEQUALIFIER *))(**(_QWORD **)pAptType
                                                                                             + 40LL))(
                                         *(_QWORD *)pAptType,
                                         pAptQualifier),
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType),
                ItemFromObjectWorker < 0) )
          {
LABEL_73:
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, APTTYPE *)))(*v55)[2])(v55);
            CoTaskMemFree(pv);
            CoTaskMemFree(v57);
            goto LABEL_74;
          }
        }
        *(_QWORD *)pAptType = 0;
        ItemFromObjectWorker = SHGetDesktopFolder((IShellFolder **)pAptType);
        v17 = v54;
        if ( ItemFromObjectWorker >= 0 )
        {
          ItemFromObjectWorker = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)pAptType + 56LL))(
                                   *(_QWORD *)pAptType,
                                   (unsigned int)v54 & 0xF0000000,
                                   *((_QWORD *)v52 + 16),
                                   *(_QWORD *)pAptQualifier);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
        }
        CoTaskMemFree(*(LPVOID *)pAptQualifier);
LABEL_39:
        if ( ItemFromObjectWorker >= 0 )
        {
          *a4 = (__int16)ItemFromObjectWorker;
          if ( (_WORD)ItemFromObjectWorker )
          {
            if ( (v17 & 0x20000000) != 0 )
            {
              *(_QWORD *)pAptType = 0;
              *(_QWORD *)pAptQualifier = 0;
              if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, APTTYPEQUALIFIER *))v12->lpVtbl->BindToHandler)(
                     v12,
                     0,
                     &BHID_SFObject,
                     &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
                     pAptQualifier) >= 0 )
              {
                v52 = 0;
                v18 = (*(__int64 (__fastcall **)(_QWORD, CShellItem **))(**(_QWORD **)pAptQualifier + 32LL))(
                        *(_QWORD *)pAptQualifier,
                        &v52);
                if ( v18 >= 0 )
                {
                  v18 = (**(__int64 (__fastcall ***)(CShellItem *, GUID *, APTTYPE *))v52)(
                          v52,
                          &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                          pAptType);
                  (*(void (__fastcall **)(CShellItem *))(*(_QWORD *)v52 + 16LL))(v52);
                }
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
                if ( v18 >= 0 )
                  goto LABEL_47;
              }
              if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, APTTYPE *))v12->lpVtbl->QueryInterface)(
                     v12,
                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                     pAptType) >= 0 )
              {
LABEL_47:
                *(_QWORD *)pAptQualifier = 0;
                v54 = 0;
                if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, const GUID *, GUID *, __int64 *))a2->lpVtbl[1].QueryInterface)(
                       a2,
                       0,
                       &BHID_SFObject,
                       &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
                       &v54) >= 0 )
                {
                  v52 = 0;
                  v19 = (*(__int64 (__fastcall **)(__int64, CShellItem **))(*(_QWORD *)v54 + 32LL))(v54, &v52);
                  if ( v19 >= 0 )
                  {
                    v19 = (**(__int64 (__fastcall ***)(CShellItem *, GUID *, APTTYPEQUALIFIER *))v52)(
                            v52,
                            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                            pAptQualifier);
                    (*(void (__fastcall **)(CShellItem *))(*(_QWORD *)v52 + 16LL))(v52);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
                  if ( v19 >= 0 )
                    goto LABEL_52;
                }
                if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, APTTYPEQUALIFIER *))a2->lpVtbl->QueryInterface)(
                       a2,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       pAptQualifier) >= 0 )
                {
LABEL_52:
                  lpString1 = 0;
                  v63 = 0;
                  v64 = 0;
                  v20 = **(_QWORD **)pAptType;
                  v63 = -1;
                  v64 = -1;
                  if ( (*(int (__fastcall **)(_QWORD, __int64, LPCWCH *))(v20 + 40))(
                         *(_QWORD *)pAptType,
                         2147647488LL,
                         &lpString1) >= 0 )
                  {
                    lpString2 = 0;
                    v60 = 0;
                    v61 = 0;
                    v21 = **(_QWORD **)pAptQualifier;
                    v60 = -1;
                    v61 = -1;
                    if ( (*(int (__fastcall **)(_QWORD, __int64, LPCWCH *))(v21 + 40))(
                           *(_QWORD *)pAptQualifier,
                           2147647488LL,
                           &lpString2) >= 0 )
                    {
                      v22 = v60;
                      if ( v60 == -1 )
                      {
                        if ( lpString2 )
                        {
                          do
                            ++v22;
                          while ( lpString2[v22] );
                        }
                        else
                        {
                          LODWORD(v22) = 0;
                        }
                      }
                      v23 = &WindowName;
                      v24 = &WindowName;
                      if ( lpString2 )
                        v24 = lpString2;
                      v25 = v63;
                      if ( v63 == -1 )
                      {
                        if ( lpString1 )
                        {
                          do
                            ++v25;
                          while ( lpString1[v25] );
                        }
                        else
                        {
                          LODWORD(v25) = 0;
                        }
                      }
                      if ( lpString1 )
                        v23 = lpString1;
                      v26 = CompareStringOrdinal(v23, v25, v24, v22, 1);
                      *a4 = v26 - 2;
                      ItemFromObjectWorker = v26 != 2;
                    }
                    if ( lpString2 )
                      CoTaskMemFree((LPVOID)lpString2);
                  }
                  if ( lpString1 )
                    CoTaskMemFree((LPVOID)lpString1);
                }
                v27 = *(__int64 **)pAptQualifier;
                if ( *(_QWORD *)pAptQualifier )
                {
                  *(_QWORD *)pAptQualifier = 0;
                  (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
                }
              }
              v28 = *(__int64 **)pAptType;
              if ( *(_QWORD *)pAptType )
              {
                *(_QWORD *)pAptType = 0;
                (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
              }
            }
            else
            {
              ItemFromObjectWorker = 1;
            }
          }
          else
          {
            ItemFromObjectWorker = 0;
          }
        }
        goto LABEL_73;
      }
    }
    v5 = v52;
LABEL_38:
    v17 = v54;
    ItemFromObjectWorker = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, APTTYPEQUALIFIER *), _QWORD, _QWORD, LPVOID))(*v53)[7])(
                             v53,
                             (unsigned int)v54 & 0xF0000000,
                             *((_QWORD *)v5 + 17),
                             v57);
    goto LABEL_39;
  }
  ItemFromObjectWorker = ApartmentType;
LABEL_77:
  if ( ApartmentType >= 0 )
    LeaveCriticalSection(v7);
  return (unsigned int)ItemFromObjectWorker;
}

```

## disassembly

```asm
0x18005fbc0  push    rbp
0x18005fbc2  push    rbx
0x18005fbc3  push    rsi
0x18005fbc4  push    rdi
0x18005fbc5  push    r12
0x18005fbc7  push    r13
0x18005fbc9  push    r14
0x18005fbcb  push    r15
0x18005fbcd  lea     rbp, [rsp-1F8h]
0x18005fbd5  sub     rsp, 2F8h
0x18005fbdc  mov     rax, cs:__security_cookie
0x18005fbe3  xor     rax, rsp
0x18005fbe6  mov     [rbp+230h+var_50], rax
0x18005fbed  mov     [rsp+330h+var_2F0], r9
0x18005fbf2  mov     dword ptr [rsp+330h+var_2B8], r8d
0x18005fbf7  mov     r14, rdx
0x18005fbfa  mov     r15, rcx
0x18005fbfd  mov     [rsp+330h+var_2C8], rcx
0x18005fc02  xor     esi, esi
0x18005fc04  mov     [r9], esi
0x18005fc07  lea     r12, [rcx-8]
0x18005fc0b  mov     [rsp+330h+var_2F8], r12
0x18005fc10  lea     rdi, [rcx+48h]
0x18005fc14  test    r12, r12
0x18005fc17  cmovz   rdi, rsi
0x18005fc1b  mov     [rsp+330h+lpCriticalSection], rdi
0x18005fc20  mov     [rsp+330h+var_2E8], rdi
0x18005fc25  mov     ebx, [rdi+2Ch]
0x18005fc28  cmp     ebx, 2
0x18005fc2b  jz      short loc_18005FC40
0x18005fc2d  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18005fc33  test    eax, eax
0x18005fc35  jz      loc_1800604DA
0x18005fc3b  cmp     eax, 1
0x18005fc3e  jnz     short loc_18005FCB5
0x18005fc40  cmp     dword ptr [rdi+28h], 0FFFFFFFDh
0x18005fc44  jz      short loc_18005FCB5
0x18005fc46  mov     ebx, esi
0x18005fc48  mov     [rsp+330h+pAptType], esi
0x18005fc4c  mov     [rsp+330h+pAptQualifier], esi
0x18005fc50  lea     rdx, [rsp+330h+pAptQualifier]; pAptQualifier
0x18005fc55  lea     rcx, [rsp+330h+pAptType]; pAptType
0x18005fc5a  call    cs:__imp_CoGetApartmentType
0x18005fc61  nop     dword ptr [rax+rax+00h]
0x18005fc66  mov     r13d, eax
0x18005fc69  test    eax, eax
0x18005fc6b  js      short loc_18005FCA5
0x18005fc6d  mov     edx, [rsp+330h+pAptType]
0x18005fc71  cmp     edx, 3
0x18005fc74  jnz     short loc_18005FC86
0x18005fc76  call    cs:__imp_GetCurrentThreadId
0x18005fc7d  nop     dword ptr [rax+rax+00h]
0x18005fc82  mov     ebx, eax
0x18005fc84  jmp     short loc_18005FC9C
0x18005fc86  test    edx, edx
0x18005fc88  jz      short loc_18005FC76
0x18005fc8a  sub     edx, 1
0x18005fc8d  jz      short loc_18005FC9C
0x18005fc8f  cmp     edx, 1
0x18005fc92  jz      loc_180060603
0x18005fc98  test    eax, eax
0x18005fc9a  js      short loc_18005FCA5
0x18005fc9c  cmp     ebx, [rdi+28h]
0x18005fc9f  jnz     loc_18006067B
0x18005fca5  mov     rcx, [rbp+238h]; this
0x18005fcac  test    r13d, r13d
0x18005fcaf  js      loc_180060532
0x18005fcb5  mov     rcx, rdi; lpCriticalSection
0x18005fcb8  call    cs:__imp_TryEnterCriticalSection
0x18005fcbf  nop     dword ptr [rax+rax+00h]
0x18005fcc4  mov     r13d, 8001010Eh
0x18005fcca  test    eax, eax
0x18005fccc  cmovnz  r13d, esi
0x18005fcd0  mov     [rsp+330h+var_2E0], r13d
0x18005fcd5  test    r13d, r13d
0x18005fcd8  js      loc_180060686
0x18005fcde  mov     rdi, r15
0x18005fce1  test    r12, r12
0x18005fce4  cmovz   rdi, rsi
0x18005fce8  test    rdi, rdi
0x18005fceb  jz      loc_18005FD7F
0x18005fcf1  test    r14, r14
0x18005fcf4  jz      loc_18005FD7F
0x18005fcfa  cmp     rdi, r14
0x18005fcfd  jz      loc_18006049B
0x18005fd03  mov     qword ptr [rsp+330h+pAptQualifier], rsi
0x18005fd08  mov     [rsp+330h+var_2C0], rsi
0x18005fd0d  mov     rax, [rdi]
0x18005fd10  lea     r8, [rsp+330h+pAptQualifier]
0x18005fd15  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18005fd1c  mov     rcx, rdi
0x18005fd1f  mov     rax, [rax]
0x18005fd22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd27  test    eax, eax
0x18005fd29  js      short loc_18005FD7F
0x18005fd2b  mov     rax, [r14]
0x18005fd2e  lea     r8, [rsp+330h+var_2C0]
0x18005fd33  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18005fd3a  mov     rcx, r14
0x18005fd3d  mov     rax, [rax]
0x18005fd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd45  test    eax, eax
0x18005fd47  js      loc_1800605ED
0x18005fd4d  mov     rcx, [rsp+330h+var_2C0]
0x18005fd52  mov     rax, [rcx]
0x18005fd55  mov     rax, [rax+10h]
0x18005fd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd5e  mov     rcx, qword ptr [rsp+330h+pAptQualifier]
0x18005fd63  mov     rax, [rcx]
0x18005fd66  mov     rax, [rax+10h]
0x18005fd6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd6f  mov     rax, [rsp+330h+var_2C0]
0x18005fd74  cmp     qword ptr [rsp+330h+pAptQualifier], rax
0x18005fd79  jz      loc_18006049B
0x18005fd7f  mov     [rsp+330h+var_2C0], rsi
0x18005fd84  lea     rsi, [r15+0A8h]
0x18005fd8b  cmp     qword ptr [rsi], 0
0x18005fd8f  jz      loc_1800604A7
0x18005fd95  mov     rcx, [rsi]
0x18005fd98  mov     rax, [rcx]
0x18005fd9b  lea     r8, [rsp+330h+var_2C0]
0x18005fda0  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x18005fda7  mov     rax, [rax]
0x18005fdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdaf  mov     ebx, eax
0x18005fdb1  test    eax, eax
0x18005fdb3  js      loc_180060246
0x18005fdb9  xor     esi, esi
0x18005fdbb  mov     [rbp+230h+var_298], rsi
0x18005fdbf  mov     rax, [r14]
0x18005fdc2  lea     r8, [rbp+230h+var_298]
0x18005fdc6  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x18005fdcd  mov     rcx, r14
0x18005fdd0  mov     rax, [rax]
0x18005fdd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdd8  mov     ebx, eax
0x18005fdda  test    eax, eax
0x18005fddc  js      loc_180060235
0x18005fde2  mov     [rbp+230h+var_2B0], rsi
0x18005fde6  mov     [rbp+230h+pv], rsi
0x18005fdea  mov     [rbp+230h+var_2A0], rsi
0x18005fdee  mov     rcx, [rbp+230h+var_298]
0x18005fdf2  mov     rax, [rcx]
0x18005fdf5  lea     r9, [rbp+230h+var_2A0]
0x18005fdf9  lea     r8, [rbp+230h+var_2B0]
0x18005fdfd  lea     rdx, [rbp+230h+pv]
0x18005fe01  mov     rax, [rax+20h]
0x18005fe05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe0a  mov     ebx, eax
0x18005fe0c  test    eax, eax
0x18005fe0e  js      loc_180060225
0x18005fe14  cmp     [r12+0A0h], rsi
0x18005fe1c  jz      loc_1800605B9
0x18005fe22  mov     rcx, [rsp+330h+var_2C0]
0x18005fe27  test    rcx, rcx
0x18005fe2a  jz      loc_180060296
0x18005fe30  mov     rbx, [rbp+230h+var_2B0]
0x18005fe34  test    rbx, rbx
0x18005fe37  jz      loc_180060296
0x18005fe3d  cmp     rcx, rbx
0x18005fe40  jz      short loc_18005FEBF
0x18005fe42  mov     qword ptr [rsp+330h+pAptQualifier], rsi
0x18005fe47  mov     qword ptr [rsp+330h+pAptType], rsi
0x18005fe4c  mov     rax, [rcx]
0x18005fe4f  lea     r8, [rsp+330h+pAptQualifier]
0x18005fe54  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18005fe5b  mov     rax, [rax]
0x18005fe5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe63  test    eax, eax
0x18005fe65  js      loc_180060296
0x18005fe6b  mov     rax, [rbx]
0x18005fe6e  lea     r8, [rsp+330h+pAptType]
0x18005fe73  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18005fe7a  mov     rcx, rbx
0x18005fe7d  mov     rax, [rax]
0x18005fe80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe85  test    eax, eax
0x18005fe87  js      loc_180060285
0x18005fe8d  mov     rcx, qword ptr [rsp+330h+pAptType]
0x18005fe92  mov     rax, [rcx]
0x18005fe95  mov     rax, [rax+10h]
0x18005fe99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe9e  mov     rcx, qword ptr [rsp+330h+pAptQualifier]
0x18005fea3  mov     rax, [rcx]
0x18005fea6  mov     rax, [rax+10h]
0x18005feaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005feaf  mov     rax, qword ptr [rsp+330h+pAptType]
0x18005feb4  cmp     qword ptr [rsp+330h+pAptQualifier], rax
0x18005feb9  jnz     loc_180060296
0x18005febf  mov     rcx, [rsp+330h+var_2C0]
0x18005fec4  mov     rax, [rcx]
0x18005fec7  mov     esi, dword ptr [rsp+330h+var_2B8]
0x18005fecb  mov     edx, esi
0x18005fecd  mov     r9d, 0F0000000h
0x18005fed3  and     rdx, r9
0x18005fed6  mov     r9, [rbp+230h+var_2A0]
0x18005feda  mov     r8, [r15+88h]
0x18005fee1  mov     rax, [rax+38h]
0x18005fee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005feea  mov     ebx, eax
0x18005feec  xor     r12d, r12d
0x18005feef  test    ebx, ebx
0x18005fef1  js      loc_1800601F5
0x18005fef7  movsx   eax, bx
0x18005fefa  mov     r15, [rsp+330h+var_2F0]
0x18005feff  mov     [r15], eax
0x18005ff02  test    bx, bx
0x18005ff05  jz      loc_1800605A7
0x18005ff0b  bt      esi, 1Dh
0x18005ff0f  jnb     loc_1800605AF
0x18005ff15  mov     qword ptr [rsp+330h+pAptType], r12
0x18005ff1a  mov     qword ptr [rsp+330h+pAptQualifier], r12
0x18005ff1f  mov     rax, [rdi]
0x18005ff22  lea     rcx, [rsp+330h+pAptQualifier]
0x18005ff27  mov     qword ptr [rsp+330h+bIgnoreCase], rcx
0x18005ff2c  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x18005ff33  lea     r8, BHID_SFObject
0x18005ff3a  xor     edx, edx
0x18005ff3c  mov     rcx, rdi
0x18005ff3f  mov     rax, [rax+18h]
0x18005ff43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff48  test    eax, eax
0x18005ff4a  js      short loc_18005FFB1
0x18005ff4c  mov     [rsp+330h+var_2C8], r12
0x18005ff51  mov     rcx, qword ptr [rsp+330h+pAptQualifier]
0x18005ff56  mov     rax, [rcx]
0x18005ff59  lea     rdx, [rsp+330h+var_2C8]
0x18005ff5e  mov     rax, [rax+20h]
0x18005ff62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff67  mov     esi, eax
0x18005ff69  test    eax, eax
0x18005ff6b  js      short loc_18005FF9C
0x18005ff6d  mov     rcx, [rsp+330h+var_2C8]
0x18005ff72  mov     rax, [rcx]
0x18005ff75  lea     r8, [rsp+330h+pAptType]
0x18005ff7a  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18005ff81  mov     rax, [rax]
0x18005ff84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff89  mov     esi, eax
0x18005ff8b  mov     rcx, [rsp+330h+var_2C8]
0x18005ff90  mov     rax, [rcx]
0x18005ff93  mov     rax, [rax+10h]
0x18005ff97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff9c  mov     rcx, qword ptr [rsp+330h+pAptQualifier]
0x18005ffa1  mov     rax, [rcx]
0x18005ffa4  mov     rax, [rax+10h]
0x18005ffa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffad  test    esi, esi
0x18005ffaf  jns     short loc_18005FFD3
0x18005ffb1  mov     rax, [rdi]
0x18005ffb4  lea     r8, [rsp+330h+pAptType]
0x18005ffb9  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18005ffc0  mov     rcx, rdi
0x18005ffc3  mov     rax, [rax]
0x18005ffc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffcb  test    eax, eax
0x18005ffcd  js      loc_1800601D9
0x18005ffd3  mov     qword ptr [rsp+330h+pAptQualifier], r12
0x18005ffd8  mov     [rsp+330h+var_2B8], r12
0x18005ffdd  mov     rax, [r14]
0x18005ffe0  lea     rcx, [rsp+330h+var_2B8]
0x18005ffe5  mov     qword ptr [rsp+330h+bIgnoreCase], rcx
0x18005ffea  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x18005fff1  lea     r8, BHID_SFObject
0x18005fff8  xor     edx, edx
0x18005fffa  mov     rcx, r14
0x18005fffd  mov     rax, [rax+18h]
0x180060001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060006  test    eax, eax
0x180060008  js      short loc_18006006F
0x18006000a  mov     [rsp+330h+var_2C8], r12
0x18006000f  mov     rcx, [rsp+330h+var_2B8]
0x180060014  mov     rax, [rcx]
0x180060017  lea     rdx, [rsp+330h+var_2C8]
0x18006001c  mov     rax, [rax+20h]
0x180060020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060025  mov     edi, eax
0x180060027  test    eax, eax
0x180060029  js      short loc_18006005A
0x18006002b  mov     rcx, [rsp+330h+var_2C8]
0x180060030  mov     rax, [rcx]
0x180060033  lea     r8, [rsp+330h+pAptQualifier]
0x180060038  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18006003f  mov     rax, [rax]
0x180060042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060047  mov     edi, eax
0x180060049  mov     rcx, [rsp+330h+var_2C8]
0x18006004e  mov     rax, [rcx]
0x180060051  mov     rax, [rax+10h]
0x180060055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006005a  mov     rcx, [rsp+330h+var_2B8]
0x18006005f  mov     rax, [rcx]
0x180060062  mov     rax, [rax+10h]
0x180060066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006006b  test    edi, edi
0x18006006d  jns     short loc_180060091
0x18006006f  mov     rax, [r14]
0x180060072  lea     r8, [rsp+330h+pAptQualifier]
0x180060077  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18006007e  mov     rcx, r14
  ... truncated ...
```
