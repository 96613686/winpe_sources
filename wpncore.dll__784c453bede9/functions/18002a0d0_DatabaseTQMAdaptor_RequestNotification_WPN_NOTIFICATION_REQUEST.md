# DatabaseTQMAdaptor::RequestNotification(WPN_NOTIFICATION_REQUEST *)

- ea: `0x18002a0d0`
- end: `0x18002ab81`
- name: `?RequestNotification@DatabaseTQMAdaptor@@UEAAJPEAUWPN_NOTIFICATION_REQUEST@@@Z`
- size: `2737`
- prototype: `__int64 __fastcall(DatabaseTQMAdaptor *__hidden this, struct WPN_NOTIFICATION_REQUEST *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000522c`
- `0x18000e5f4`
- `0x1800298b0`
- `0x180029ea4`
- `0x18002a0d0`
- `0x18002ab88`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002aaa4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002aaa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aa96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002aa96`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a431`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a480`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a431`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a480`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a3b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a3b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a601`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x18002a555`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x18002a72e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x18002a555`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x18002a72e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18002a583`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18002a583`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DatabaseTQMAdaptor::RequestNotification(
        DatabaseTQMAdaptor *this,
        struct WPN_NOTIFICATION_REQUEST *a2)
{
  DatabaseTQMAdaptor *v3; // rbx
  unsigned int v4; // r12d
  __int64 v5; // rax
  __int64 v6; // r13
  __int64 v7; // rdi
  int LastBootTime; // r15d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, const wchar_t *, __int64); // rbx
  int v11; // eax
  char v12; // cl
  __int64 v13; // rdx
  ULARGE_INTEGER v14; // rcx
  unsigned int v15; // r15d
  _QWORD *v16; // r14
  _QWORD *v17; // r12
  _QWORD *v18; // r15
  _QWORD *v19; // rax
  const char *v20; // r9
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, LPVOID *); // rdi
  int v27; // eax
  __int64 v28; // rdx
  const WCHAR *v29; // rcx
  __int64 v30; // rdx
  const WCHAR *v31; // rcx
  __int64 v32; // r14
  unsigned __int64 k; // rcx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, IStream **); // rbx
  int v36; // eax
  HRESULT v37; // eax
  char *v38; // rbx
  HRESULT v39; // eax
  IStream *v40; // rcx
  ULARGE_INTEGER v41; // rdi
  __int64 (__fastcall *v42)(ULARGE_INTEGER, _QWORD, __int64 *); // rbx
  int v43; // eax
  __int64 v44; // rcx
  int v45; // eax
  unsigned __int64 j; // rcx
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, IStream **); // rbx
  int v49; // eax
  HRESULT v50; // eax
  IStream *v51; // rcx
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, _QWORD, const wchar_t *); // rbx
  int v54; // eax
  int v56; // eax
  unsigned int i; // r14d
  ULARGE_INTEGER v58; // rdi
  __int64 (__fastcall *v59)(ULARGE_INTEGER, _QWORD, IStream **); // rbx
  int v60; // eax
  IStream *v61; // rcx
  ULARGE_INTEGER v62; // rcx
  __int64 v63; // rdx
  HANDLE ProcessHeap; // rax
  LPVOID v65; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-B8h]
  ULARGE_INTEGER pui; // [rsp+40h] [rbp-98h] BYREF
  IStream *v68; // [rsp+48h] [rbp-90h] BYREF
  __int64 v69; // [rsp+50h] [rbp-88h]
  __int64 v70; // [rsp+58h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-78h] BYREF
  __int64 v72; // [rsp+68h] [rbp-70h]
  __int64 v73; // [rsp+70h] [rbp-68h]
  _QWORD *v74; // [rsp+78h] [rbp-60h] BYREF
  _QWORD *v75; // [rsp+80h] [rbp-58h]
  void *v76; // [rsp+90h] [rbp-48h]
  _QWORD *v77; // [rsp+98h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  IStream *pstm; // [rsp+E8h] [rbp+10h] BYREF
  __int64 v81; // [rsp+F0h] [rbp+18h] BYREF
  int v82; // [rsp+F8h] [rbp+20h]

  v3 = this;
  v4 = 0;
  LODWORD(pstm) = 0;
  v5 = 0;
  while ( 1 )
  {
    v82 = v5;
    if ( (unsigned int)v5 >= *((_DWORD *)a2 + 2) )
      return 0;
    v6 = 6 * v5;
    v7 = *((_QWORD *)a2 + 2);
    v69 = v7;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(&v74);
    try
    {
      LastBootTime = GetLastBootTime();
      if ( (*(_BYTE *)(v7 + 8 * v6 + 32) & 1) != 0 )
      {
        pui.QuadPart = 0;
        v9 = *((_QWORD *)v3 + 7);
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v9 + 120LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pui);
        bIgnoreCase = LastBootTime;
        v11 = v10(v9, *(_QWORD *)(v69 + 8 * v6), L"badge", 1);
        if ( (int)(v11 + 0x80000000) < 0 || (v12 = 0, v11 == -2147023728) )
          v12 = 1;
        if ( !v12 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x10F,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v11,
            LastBootTime);
        if ( v11 >= 0 )
        {
          v81 = 0;
          v41 = pui;
          v42 = *(__int64 (__fastcall **)(ULARGE_INTEGER, _QWORD, __int64 *))(*(_QWORD *)pui.QuadPart + 24LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
          v43 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v42)((ULARGE_INTEGER)v41.QuadPart, 0, &v81);
          if ( v43 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x114,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
              (const char *)(unsigned int)v43,
              LastBootTime);
          std::vector<Microsoft::WRL::ComPtr<IWpnNotification>>::_Emplace_one_at_back<Microsoft::WRL::ComPtr<IWpnNotification> const &>(
            &v74,
            &v81);
          v44 = v81;
          if ( v81 )
          {
            v81 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          }
          v7 = v69;
        }
        else
        {
          v13 = 10LL * v4;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 8 * v13 + 12) = 2;
          v7 = v69;
          *(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * v13) = *(_QWORD *)(v69 + 8 * v6);
          *(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * v13 + 40) = 0;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 8 * v13 + 48) = 0;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 8 * v13 + 8) = 0;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 8 * v13 + 16) = -2147023728;
          LODWORD(pstm) = ++v4;
        }
        v14 = pui;
        if ( pui.QuadPart )
        {
          pui.QuadPart = 0;
          (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v14.QuadPart + 16LL))(v14);
        }
        v3 = this;
      }
      if ( *(unsigned int *)(v7 + 8 * v6 + 8) - (v75 - v74) != v4 )
      {
        pui.QuadPart = 0;
        v52 = *((_QWORD *)v3 + 7);
        v53 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *))(*(_QWORD *)v52 + 120LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pui);
        bIgnoreCase = LastBootTime;
        v54 = v53(v52, *(_QWORD *)(v69 + 8 * v6), L"tile");
        if ( (int)(v54 + 0x80000000) >= 0 && v54 != -2147023728 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x12F,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v54,
            LastBootTime);
        if ( v54 < 0 )
        {
          v63 = 10LL * v4;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 8 * v63 + 12) = 1;
          v7 = v69;
          *(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * v63) = *(_QWORD *)(v69 + 8 * v6);
          *(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * v63 + 40) = 0;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 8 * v63 + 48) = 0;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 8 * v63 + 8) = 0;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 8 * v63 + 16) = -2147023728;
          LODWORD(pstm) = v4 + 1;
        }
        else
        {
          LODWORD(v81) = 0;
          v56 = (*(__int64 (__fastcall **)(ULARGE_INTEGER, __int64 *))(*(_QWORD *)pui.QuadPart + 32LL))(pui, &v81);
          if ( v56 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x134,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
              (const char *)(unsigned int)v56,
              LastBootTime);
          for ( i = 0; i < (unsigned int)v81; ++i )
          {
            v68 = 0;
            v58 = pui;
            v59 = *(__int64 (__fastcall **)(ULARGE_INTEGER, _QWORD, IStream **))(*(_QWORD *)pui.QuadPart + 24LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
            v60 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v59)((ULARGE_INTEGER)v58.QuadPart, i, &v68);
            if ( v60 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x138,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
                (const char *)(unsigned int)v60,
                LastBootTime);
            std::vector<Microsoft::WRL::ComPtr<IWpnNotification>>::_Emplace_one_at_back<Microsoft::WRL::ComPtr<IWpnNotification> const &>(
              &v74,
              &v68);
            v61 = v68;
            if ( v68 )
            {
              v68 = 0;
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v61 + 16LL))(v61);
            }
          }
          v7 = v69;
        }
        v62 = pui;
        if ( pui.QuadPart )
        {
          pui.QuadPart = 0;
          (*(void (__fastcall **)(ULARGE_INTEGER))(*(_QWORD *)v62.QuadPart + 16LL))(v62);
        }
      }
      v15 = 0;
      v16 = v74;
      v17 = v75;
      while ( v16 != v17 )
      {
        LODWORD(v81) = 0;
        v45 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v16 + 24LL))(*v16, &v81);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x14E,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v45,
            bIgnoreCase);
        for ( j = 0; j < *(unsigned int *)(v7 + 8 * v6 + 16); ++j )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v7 + 8 * v6 + 24) + 4 * j) == (_DWORD)v81 )
            goto LABEL_68;
        }
        v68 = 0;
        pui.QuadPart = 0;
        v47 = *v16;
        v48 = *(__int64 (__fastcall **)(__int64, IStream **))(*(_QWORD *)*v16 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
        v49 = v48(v47, &v68);
        if ( v49 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x154,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v49,
            bIgnoreCase);
        v50 = IStream_Size(v68, &pui);
        if ( v50 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x155,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v50,
            bIgnoreCase);
        v15 += pui.LowPart;
        v51 = v68;
        if ( v68 )
        {
          v68 = 0;
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v51 + 16LL))(v51);
        }
        v7 = v69;
LABEL_68:
        ++v16;
      }
      if ( v15 )
      {
        ProcessHeap = GetProcessHeap();
        v65 = HeapAlloc(ProcessHeap, 0, v15);
        *(_QWORD *)(v7 + 8 * v6 + 40) = v65;
        if ( !v65 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x15F,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)0x8007000ELL,
            bIgnoreCase);
      }
      v76 = *(void **)(v7 + 8 * v6 + 40);
      v18 = v74;
      v19 = v75;
      v77 = v75;
      v4 = (unsigned int)pstm;
      while ( v18 != v19 )
      {
        LODWORD(v81) = 0;
        v70 = 0;
        v68 = 0;
        pv = 0;
        v72 = 0;
        v73 = 0;
        v22 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v18 + 24LL))(*v18, &v81);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16A,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v22,
            bIgnoreCase);
        v23 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v18 + 88LL))(*v18, &v70);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16B,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v23,
            bIgnoreCase);
        v24 = (*(__int64 (__fastcall **)(_QWORD, IStream **))(*(_QWORD *)*v18 + 72LL))(*v18, &v68);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16C,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v24,
            bIgnoreCase);
        v25 = *v18;
        v26 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)*v18 + 40LL);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v72 = -1;
        v73 = -1;
        v27 = v26(v25, &pv);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16D,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v27,
            bIgnoreCase);
        LODWORD(v28) = v72;
        if ( v72 == -1 )
        {
          if ( pv )
          {
            v28 = -1;
            do
              ++v28;
            while ( *((_WORD *)pv + v28) );
          }
          else
          {
            LODWORD(v28) = 0;
          }
        }
        v29 = &word_180124798;
        if ( pv )
          v29 = (const WCHAR *)pv;
        if ( CompareStringOrdinal(v29, v28, L"tile", -1, 0) == 2 )
        {
          *(_DWORD *)(*((_QWORD *)a2 + 3) + 80LL * v4 + 12) = 1;
        }
        else
        {
          LODWORD(v30) = v72;
          if ( v72 == -1 )
          {
            if ( pv )
            {
              v30 = -1;
              do
                ++v30;
              while ( *((_WORD *)pv + v30) );
            }
            else
            {
              LODWORD(v30) = 0;
            }
          }
          v31 = &word_180124798;
          if ( pv )
            v31 = (const WCHAR *)pv;
          if ( CompareStringOrdinal(v31, v30, L"badge", -1, 0) == 2 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 80LL * v4 + 12) = 2;
        }
        v32 = 80LL * v4;
        *(_DWORD *)(*((_QWORD *)a2 + 3) + v32 + 8) = v81;
        v7 = v69;
        *(_QWORD *)(v32 + *((_QWORD *)a2 + 3)) = *(_QWORD *)(v69 + 8 * v6);
        *(_QWORD *)(*((_QWORD *)a2 + 3) + v32 + 24) = v70;
        if ( HIDWORD(v68) && (_DWORD)v68 )
        {
          *(_QWORD *)(*((_QWORD *)a2 + 3) + v32 + 32) = v68;
          *(_DWORD *)(*((_QWORD *)a2 + 3) + v32 + 12) |= 0x10u;
        }
        for ( k = 0; k < *(unsigned int *)(v7 + 8 * v6 + 16); ++k )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v7 + 8 * v6 + 24) + 4 * k) == (_DWORD)v81 )
          {
            *(_DWORD *)(v32 + *((_QWORD *)a2 + 3) + 16) = -2143419899;
            *(_QWORD *)(v32 + *((_QWORD *)a2 + 3) + 40) = 0;
            *(_DWORD *)(v32 + *((_QWORD *)a2 + 3) + 48) = 0;
            goto LABEL_53;
          }
        }
        *(_DWORD *)(v32 + *((_QWORD *)a2 + 3) + 16) = 0;
        pui.QuadPart = 0;
        pstm = 0;
        v34 = *v18;
        v35 = *(__int64 (__fastcall **)(__int64, IStream **))(*(_QWORD *)*v18 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pstm);
        v36 = v35(v34, &pstm);
        if ( v36 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x18E,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v36,
            bIgnoreCase);
        v37 = IStream_Size(pstm, &pui);
        if ( v37 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x190,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v37,
            bIgnoreCase);
        v38 = (char *)v76;
        v39 = IStream_Read(pstm, v76, pui.LowPart);
        if ( v39 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x194,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
            (const char *)(unsigned int)v39,
            bIgnoreCase);
        *(_QWORD *)(v32 + *((_QWORD *)a2 + 3) + 40) = v38;
        *(_DWORD *)(v32 + *((_QWORD *)a2 + 3) + 48) = pui.LowPart;
        v76 = &v38[*(unsigned int *)(v32 + *((_QWORD *)a2 + 3) + 48)];
        v40 = pstm;
        if ( pstm )
        {
          pstm = 0;
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v40 + 16LL))(v40);
        }
        v7 = v69;
LABEL_53:
        LODWORD(pstm) = ++v4;
        if ( pv )
          CoTaskMemFree(pv);
        ++v18;
        v19 = v77;
      }
      *(_DWORD *)(v7 + 8 * v6 + 12) = v4 - *((_DWORD *)a2 + 1);
      *((_DWORD *)a2 + 1) = v4;
      std::vector<Microsoft::WRL::ComPtr<IWpnNotification>>::_Tidy(&v74);
      v5 = (unsigned int)(v82 + 1);
      v3 = this;
    }
    catch ( ... )
    {
      LODWORD(pstm) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x1A4,
                        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\databasetqmadaptor.cpp",
                        v20);
      return (unsigned int)pstm;
    }
  }
}

```

## disassembly

```asm
0x18002a0d0  mov     [rsp+arg_0], rcx
0x18002a0d5  push    rbx
0x18002a0d6  push    rsi
0x18002a0d7  push    rdi
0x18002a0d8  push    r12
0x18002a0da  push    r13
0x18002a0dc  push    r14
0x18002a0de  push    r15
0x18002a0e0  sub     rsp, 0A0h
0x18002a0e7  mov     rsi, rdx
0x18002a0ea  mov     rbx, rcx
0x18002a0ed  xor     r14d, r14d
0x18002a0f0  mov     r12d, r14d
0x18002a0f3  mov     dword ptr [rsp+0D8h+pstm], r14d
0x18002a0fb  mov     eax, r14d
0x18002a0fe  mov     [rsp+0D8h+arg_18], eax
0x18002a105  cmp     eax, [rsi+8]
0x18002a108  jnb     loc_18002A2DE
0x18002a10e  lea     r13, [rax+rax*2]
0x18002a112  add     r13, r13
0x18002a115  mov     rdi, [rsi+10h]
0x18002a119  mov     [rsp+0D8h+var_88], rdi
0x18002a11e  lea     rcx, [rsp+0D8h+var_60]
0x18002a123  call    ??$?0AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>(std::allocator<std::pair<ulong const,std::shared_ptr<TileSession>>> const &)
0x18002a128  nop
0x18002a129  call    ?GetLastBootTime@@YA_JXZ; GetLastBootTime(void)
0x18002a12e  mov     r15, rax
0x18002a131  test    byte ptr [rdi+r13*8+20h], 1
0x18002a137  jz      loc_18002A234
0x18002a13d  mov     qword ptr [rsp+0D8h+pui], r14
0x18002a142  mov     rdi, [rbx+38h]
0x18002a146  mov     rdx, [rdi]
0x18002a149  mov     rbx, [rdx+78h]
0x18002a14d  lea     rcx, [rsp+0D8h+pui]
0x18002a152  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a157  lea     rax, [rsp+0D8h+pui]
0x18002a15c  mov     [rsp+0D8h+var_B0], rax
0x18002a161  mov     qword ptr [rsp+0D8h+bIgnoreCase], r15; int
0x18002a166  mov     r9d, 1
0x18002a16c  lea     r8, aBadge; "badge"
0x18002a173  mov     rax, [rsp+0D8h+var_88]
0x18002a178  mov     rdx, [rax+r13*8]
0x18002a17c  mov     rcx, rdi
0x18002a17f  mov     rax, rbx
0x18002a182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a187  mov     edx, 80000000h
0x18002a18c  lea     ecx, [rax+rdx]
0x18002a18f  test    edx, ecx
0x18002a191  jnz     short loc_18002A19D
0x18002a193  cmp     eax, 80070490h
0x18002a198  mov     cl, r14b
0x18002a19b  jnz     short loc_18002A19F
0x18002a19d  mov     cl, 1
0x18002a19f  mov     r10, [rsp+0D8h]
0x18002a1a7  test    cl, cl
0x18002a1a9  jz      loc_18002A2F3
0x18002a1af  test    eax, eax
0x18002a1b1  jns     loc_18002A618
0x18002a1b7  mov     eax, r12d
0x18002a1ba  lea     rdx, [rax+rax*4]
0x18002a1be  add     rdx, rdx
0x18002a1c1  mov     rax, [rsi+18h]
0x18002a1c5  mov     dword ptr [rax+rdx*8+0Ch], 2
0x18002a1cd  mov     rcx, [rsi+18h]
0x18002a1d1  mov     rdi, [rsp+0D8h+var_88]
0x18002a1d6  mov     rax, [rdi+r13*8]
0x18002a1da  mov     [rcx+rdx*8], rax
0x18002a1de  mov     rax, [rsi+18h]
0x18002a1e2  mov     [rax+rdx*8+28h], r14
0x18002a1e7  mov     rax, [rsi+18h]
0x18002a1eb  mov     [rax+rdx*8+30h], r14d
0x18002a1f0  mov     rax, [rsi+18h]
0x18002a1f4  mov     [rax+rdx*8+8], r14d
0x18002a1f9  mov     rax, [rsi+18h]
0x18002a1fd  mov     dword ptr [rax+rdx*8+10h], 80070490h
0x18002a205  inc     r12d
0x18002a208  mov     dword ptr [rsp+0D8h+pstm], r12d
0x18002a210  mov     rcx, qword ptr [rsp+0D8h+pui]
0x18002a215  test    rcx, rcx
0x18002a218  jz      short loc_18002A22C
0x18002a21a  mov     qword ptr [rsp+0D8h+pui], r14
0x18002a21f  mov     rax, [rcx]
0x18002a222  mov     rax, [rax+10h]
0x18002a226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a22b  nop
0x18002a22c  mov     rbx, [rsp+0D8h+arg_0]
0x18002a234  mov     r14d, r12d
0x18002a237  mov     rcx, [rsp+0D8h+var_58]
0x18002a23f  sub     rcx, [rsp+0D8h+var_60]
0x18002a244  sar     rcx, 3
0x18002a248  mov     eax, [rdi+r13*8+8]
0x18002a24d  sub     rax, rcx
0x18002a250  cmp     rax, r14
0x18002a253  jnz     loc_18002A7C4
0x18002a259  xor     ebx, ebx
0x18002a25b  mov     r15d, ebx
0x18002a25e  mov     r14, [rsp+0D8h+var_60]
0x18002a263  mov     r12, [rsp+0D8h+var_58]
0x18002a26b  cmp     r14, r12
0x18002a26e  jnz     loc_18002A69D
0x18002a274  test    r15d, r15d
0x18002a277  jnz     loc_18002AA96
0x18002a27d  mov     rax, [rdi+r13*8+28h]
0x18002a282  mov     [rsp+0D8h+var_48], rax
0x18002a28a  mov     r15, [rsp+0D8h+var_60]
0x18002a28f  mov     rax, [rsp+0D8h+var_58]
0x18002a297  mov     [rsp+0D8h+var_40], rax
0x18002a29f  mov     r12d, dword ptr [rsp+0D8h+pstm]
0x18002a2a7  cmp     r15, rax
0x18002a2aa  jnz     short loc_18002A30B
0x18002a2ac  mov     eax, r12d
0x18002a2af  sub     eax, [rsi+4]
0x18002a2b2  mov     [rdi+r13*8+0Ch], eax
0x18002a2b7  mov     [rsi+4], r12d
0x18002a2bb  lea     rcx, [rsp+0D8h+var_60]
0x18002a2c0  call    ?_Tidy@?$vector@V?$ComPtr@UIWpnNotification@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIWpnNotification@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IWpnNotification>>::_Tidy(void)
0x18002a2c5  mov     eax, [rsp+0D8h+arg_18]
0x18002a2cc  inc     eax
0x18002a2ce  mov     rbx, [rsp+0D8h+arg_0]
0x18002a2d6  xor     r14d, r14d
0x18002a2d9  jmp     loc_18002A0FE
0x18002a2de  xor     eax, eax
0x18002a2e0  add     rsp, 0A0h
0x18002a2e7  pop     r15
0x18002a2e9  pop     r14
0x18002a2eb  pop     r13
0x18002a2ed  pop     r12
0x18002a2ef  pop     rdi
0x18002a2f0  pop     rsi
0x18002a2f1  pop     rbx
0x18002a2f2  retn
0x18002a2f3  mov     r9d, eax; char *
0x18002a2f6  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002a2fd  mov     edx, 10Fh; void *
0x18002a302  mov     rcx, r10; this
0x18002a305  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a30b  mov     dword ptr [rsp+0D8h+arg_10], ebx
0x18002a312  mov     [rsp+0D8h+var_80], 0
0x18002a31b  mov     [rsp+0D8h+var_90], rbx
0x18002a320  mov     [rsp+0D8h+pv], rbx
0x18002a325  mov     [rsp+0D8h+var_70], rbx
0x18002a32a  mov     [rsp+0D8h+var_68], rbx
0x18002a32f  mov     rcx, [r15]
0x18002a332  mov     rax, [rcx]
0x18002a335  lea     rdx, [rsp+0D8h+arg_10]
0x18002a33d  mov     rax, [rax+18h]
0x18002a341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a346  mov     rcx, [rsp+0D8h]; this
0x18002a34e  test    eax, eax
0x18002a350  js      loc_18002A773
0x18002a356  mov     rcx, [r15]
0x18002a359  mov     rax, [rcx]
0x18002a35c  lea     rdx, [rsp+0D8h+var_80]
0x18002a361  mov     rax, [rax+58h]
0x18002a365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a36a  mov     rcx, [rsp+0D8h]; this
0x18002a372  test    eax, eax
0x18002a374  js      loc_18002A787
0x18002a37a  mov     rcx, [r15]
0x18002a37d  mov     rax, [rcx]
0x18002a380  lea     rdx, [rsp+0D8h+var_90]
0x18002a385  mov     rax, [rax+48h]
0x18002a389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a38e  mov     rcx, [rsp+0D8h]; this
0x18002a396  test    eax, eax
0x18002a398  js      loc_18002A79B
0x18002a39e  mov     rbx, [r15]
0x18002a3a1  mov     rax, [rbx]
0x18002a3a4  mov     rdi, [rax+28h]
0x18002a3a8  mov     rcx, [rsp+0D8h+pv]; pv
0x18002a3ad  test    rcx, rcx
0x18002a3b0  jz      short loc_18002A3C1
0x18002a3b2  call    cs:__imp_CoTaskMemFree
0x18002a3b8  mov     [rsp+0D8h+pv], 0
0x18002a3c1  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002a3c5  mov     [rsp+0D8h+var_70], r14
0x18002a3ca  mov     [rsp+0D8h+var_68], r14
0x18002a3cf  lea     rdx, [rsp+0D8h+pv]
0x18002a3d4  mov     rcx, rbx
0x18002a3d7  mov     rax, rdi
0x18002a3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3df  mov     rcx, [rsp+0D8h]; this
0x18002a3e7  xor     ebx, ebx
0x18002a3e9  test    eax, eax
0x18002a3eb  js      loc_18002A7AF
0x18002a3f1  mov     rdx, [rsp+0D8h+var_70]
0x18002a3f6  mov     rax, [rsp+0D8h+pv]
0x18002a3fb  cmp     rdx, r14
0x18002a3fe  jnz     short loc_18002A415
0x18002a400  test    rax, rax
0x18002a403  jz      loc_18002AADA
0x18002a409  mov     rdx, r14
0x18002a40c  inc     rdx; cchCount1
0x18002a40f  cmp     [rax+rdx*2], bx
0x18002a413  jnz     short loc_18002A40C
0x18002a415  lea     rcx, word_180124798
0x18002a41c  test    rax, rax
0x18002a41f  cmovnz  rcx, rax; lpString1
0x18002a423  mov     [rsp+0D8h+bIgnoreCase], ebx; bIgnoreCase
0x18002a427  mov     r9d, r14d; cchCount2
0x18002a42a  lea     r8, aTile; "tile"
0x18002a431  call    cs:__imp_CompareStringOrdinal
0x18002a437  cmp     eax, 2
0x18002a43a  jz      loc_18002AAEA
0x18002a440  mov     rdx, [rsp+0D8h+var_70]
0x18002a445  mov     rax, [rsp+0D8h+pv]
0x18002a44a  cmp     rdx, r14
0x18002a44d  jnz     short loc_18002A464
0x18002a44f  test    rax, rax
0x18002a452  jz      loc_18002AAE2
0x18002a458  mov     rdx, r14
0x18002a45b  inc     rdx; cchCount1
0x18002a45e  cmp     [rax+rdx*2], bx
0x18002a462  jnz     short loc_18002A45B
0x18002a464  lea     rcx, word_180124798
0x18002a46b  test    rax, rax
0x18002a46e  cmovnz  rcx, rax; lpString1
0x18002a472  mov     [rsp+0D8h+bIgnoreCase], ebx; int
0x18002a476  mov     r9d, r14d; cchCount2
0x18002a479  lea     r8, aBadge; "badge"
0x18002a480  call    cs:__imp_CompareStringOrdinal
0x18002a486  cmp     eax, 2
0x18002a489  jz      loc_18002AB05
0x18002a48f  mov     eax, r12d
0x18002a492  lea     r14, [rax+rax*4]
0x18002a496  shl     r14, 4
0x18002a49a  mov     rcx, [rsi+18h]
0x18002a49e  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x18002a4a5  mov     [rcx+r14+8], eax
0x18002a4aa  mov     rcx, [rsi+18h]
0x18002a4ae  mov     rdi, [rsp+0D8h+var_88]
0x18002a4b3  mov     rax, [rdi+r13*8]
0x18002a4b7  mov     [r14+rcx], rax
0x18002a4bb  mov     ecx, dword ptr [rsp+0D8h+var_80+4]
0x18002a4bf  shl     rcx, 20h
0x18002a4c3  mov     eax, dword ptr [rsp+0D8h+var_80]
0x18002a4c7  or      rcx, rax
0x18002a4ca  mov     rax, [rsi+18h]
0x18002a4ce  mov     [rax+r14+18h], rcx
0x18002a4d3  mov     ecx, dword ptr [rsp+0D8h+var_90+4]
0x18002a4d7  test    ecx, ecx
0x18002a4d9  jnz     loc_18002AB20
0x18002a4df  mov     rcx, rbx
0x18002a4e2  mov     edx, [rdi+r13*8+10h]
0x18002a4e7  mov     r8d, dword ptr [rsp+0D8h+arg_10]
0x18002a4ef  cmp     rcx, rdx
0x18002a4f2  jb      loc_18002A906
0x18002a4f8  mov     rax, [rsi+18h]
0x18002a4fc  mov     [r14+rax+10h], ebx
0x18002a501  mov     qword ptr [rsp+0D8h+pui], rbx
0x18002a506  mov     [rsp+0D8h+pstm], rbx
0x18002a50e  mov     rdi, [r15]
0x18002a511  mov     rax, [rdi]
0x18002a514  mov     rbx, [rax+30h]
0x18002a518  lea     rcx, [rsp+0D8h+pstm]
0x18002a520  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a525  lea     rdx, [rsp+0D8h+pstm]
0x18002a52d  mov     rcx, rdi
0x18002a530  mov     rax, rbx
0x18002a533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a538  mov     rcx, [rsp+0D8h]; this
0x18002a540  test    eax, eax
0x18002a542  js      loc_18002A947
0x18002a548  lea     rdx, [rsp+0D8h+pui]; pui
0x18002a54d  mov     rcx, [rsp+0D8h+pstm]; pstm
0x18002a555  call    cs:__imp_IStream_Size
0x18002a55b  mov     rcx, [rsp+0D8h]; this
0x18002a563  test    eax, eax
0x18002a565  js      loc_18002A95B
0x18002a56b  mov     r8d, dword ptr [rsp+0D8h+pui]; cb
0x18002a570  mov     rbx, [rsp+0D8h+var_48]
0x18002a578  mov     rdx, rbx; pv
0x18002a57b  mov     rcx, [rsp+0D8h+pstm]; pstm
0x18002a583  call    cs:__imp_IStream_Read
0x18002a589  mov     rcx, [rsp+0D8h]; this
0x18002a591  test    eax, eax
0x18002a593  js      loc_18002A96F
0x18002a599  mov     rax, [rsi+18h]
0x18002a59d  mov     [r14+rax+28h], rbx
0x18002a5a2  mov     rcx, [rsi+18h]
0x18002a5a6  mov     eax, dword ptr [rsp+0D8h+pui]
0x18002a5aa  mov     [r14+rcx+30h], eax
0x18002a5af  mov     rax, [rsi+18h]
0x18002a5b3  mov     ecx, [r14+rax+30h]
0x18002a5b8  add     rbx, rcx
0x18002a5bb  mov     [rsp+0D8h+var_48], rbx
0x18002a5c3  mov     rcx, [rsp+0D8h+pstm]
0x18002a5cb  xor     ebx, ebx
0x18002a5cd  test    rcx, rcx
0x18002a5d0  jz      short loc_18002A5E7
0x18002a5d2  mov     [rsp+0D8h+pstm], rbx
0x18002a5da  mov     rax, [rcx]
0x18002a5dd  mov     rax, [rax+10h]
0x18002a5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5e6  nop
0x18002a5e7  mov     rdi, [rsp+0D8h+var_88]
0x18002a5ec  inc     r12d
0x18002a5ef  mov     dword ptr [rsp+0D8h+pstm], r12d
0x18002a5f7  mov     rcx, [rsp+0D8h+pv]; pv
0x18002a5fc  test    rcx, rcx
  ... truncated ...
```
