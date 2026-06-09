# AppXUtil::GetApplicableUsersForCategories(AppxCategory const * const *,ulong,ISusEseSession *,ulong *,ulong * *)

- ea: `0x18021b2b8`
- end: `0x18021bd09`
- name: `?GetApplicableUsersForCategories@AppXUtil@@YAJPEBQEBVAppxCategory@@KPEAUISusEseSession@@PEAKPEAPEAK@Z`
- size: `2641`
- prototype: `__int64 __fastcall(AppXUtil *__hidden this, const struct AppxCategory *const *, unsigned int, struct ISusEseSession *, unsigned int *, unsigned int **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180206860`

## callees

- `0x18003bab0`
- `0x180052114`
- `0x18012b618`
- `0x180219790`
- `0x18021b2b8`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021b3f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021b447`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021b3f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021b447`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18021ba2a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18021ba2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18021b9ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18021b9ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18021ba8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18021ba8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18021b99f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18021b99f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021b406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021b45b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021b406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18021b45b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b61d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b76a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b81f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b8aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b8f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b96d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b9b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021ba00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021ba9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021bb18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021bbb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021bc0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b61d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b76a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b81f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b8aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b8f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b96d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021b9b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021ba00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021ba9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021bb18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021bbb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021bc0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021b9e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021b9e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall AppXUtil::GetApplicableUsersForCategories(
        AppXUtil *this,
        const struct AppxCategory *const *a2,
        __int64 a3,
        struct ISusEseSession *a4,
        unsigned int *a5)
{
  int PackageManager; // edi
  unsigned int v6; // r12d
  struct CPackageManagerWrapper *v7; // r15
  __int64 v8; // rcx
  const WCHAR *v9; // rdi
  unsigned __int64 v10; // rbx
  HSTRING v11; // r14
  const WCHAR *v12; // rdi
  unsigned __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64 *); // rdi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rbx
  int (__fastcall *v22)(__int64, __int64 *); // rsi
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  struct CPackageManagerWrapper *v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rbx
  int (__fastcall *v39)(__int64, __int64 *); // rsi
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  int i; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  const WCHAR *StringRawBuffer; // rax
  __int64 v52; // rcx
  DWORD LengthSid; // eax
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  int v60; // esi
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  struct CPackageManagerWrapper *v68; // rcx
  unsigned int v70; // [rsp+30h] [rbp-D0h]
  struct CPackageManagerWrapper *v71; // [rsp+38h] [rbp-C8h] BYREF
  AppXUtil *v72; // [rsp+40h] [rbp-C0h]
  __int64 v73; // [rsp+48h] [rbp-B8h]
  struct ISusEseSession *v74; // [rsp+50h] [rbp-B0h]
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v77; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER v78; // [rsp+80h] [rbp-80h] BYREF
  PSID Sid; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v80[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v81; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v82; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v84; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v85; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v86; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v87; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v88; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v89; // [rsp+E8h] [rbp-18h] BYREF
  int v90; // [rsp+F0h] [rbp-10h] BYREF
  BOOL hasEmbedNull; // [rsp+F4h] [rbp-Ch] BYREF
  int v92; // [rsp+F8h] [rbp-8h] BYREF
  void **v93; // [rsp+100h] [rbp+0h] BYREF
  __int64 v94; // [rsp+108h] [rbp+8h]
  __int128 v95; // [rsp+110h] [rbp+10h]

  v74 = a4;
  v73 = a3;
  v70 = (unsigned int)a2;
  v72 = this;
  v71 = 0;
  v89 = 0;
  v88 = 0;
  v80[0] = 0;
  v94 = 0;
  v95 = 0u;
  v93 = &CSusSortedArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>::`vftable';
  if ( a4 && a5 )
  {
    *(_DWORD *)a4 = 0;
    *(_QWORD *)a5 = 0;
    if ( this && (_DWORD)a2 && a3 )
    {
      PackageManager = GetPackageManager(&v71);
      if ( PackageManager >= 0 )
      {
        v6 = 0;
        while ( 1 )
        {
          v7 = v71;
          v8 = v89;
          if ( v89 )
          {
            v89 = 0;
            (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v8 + 16LL))(v8, 0, 0xFFFFFFFFLL);
          }
          v9 = *(const WCHAR **)(*((_QWORD *)v72 + v6) + 8LL);
          v10 = -1;
          do
            ++v10;
          while ( v9[v10] );
          if ( v10 > 0xFFFFFFFF )
          {
            LODWORD(v10) = -1;
            RaiseException(0xC000000D, 1u, 0, 0);
          }
          WindowsCreateStringReference(v9, v10, &hstringHeader, &string);
          v11 = string;
          v12 = (const WCHAR *)**((_QWORD **)v72 + v6);
          v13 = -1;
          do
            ++v13;
          while ( v12[v13] );
          if ( v13 > 0xFFFFFFFF )
          {
            LODWORD(v13) = -1;
            RaiseException(0xC000000D, 1u, 0, 0);
          }
          WindowsCreateStringReference(v12, v13, &v78, &v77);
          PackageManager = (*(__int64 (__fastcall **)(_QWORD, HSTRING, HSTRING, __int64, __int64 *))(**((_QWORD **)v7 + 3) + 88LL))(
                             *((_QWORD *)v7 + 3),
                             v77,
                             v11,
                             63,
                             &v89);
          if ( PackageManager < 0 )
            break;
          v14 = v89;
          v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v89 + 48LL);
          v16 = v88;
          if ( v88 )
          {
            v88 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          PackageManager = v15(v14, &v88);
          if ( PackageManager < 0 )
            break;
          if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v88 + 56LL))(v88, v80) >= 0 )
          {
            do
            {
              if ( !v80[0] )
                break;
              v85 = 0;
              v84 = 0;
              v87 = 0;
              v83 = 0;
              v81 = 0;
              if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v88 + 48LL))(v88, &v85) >= 0 )
              {
                v21 = v85;
                v22 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v85 + 48LL);
                v23 = v84;
                if ( v84 )
                {
                  v84 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                }
                if ( v22(v21, &v84) >= 0 )
                {
                  if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v84 + 96LL))(v84, &v87) >= 0 )
                  {
                    v32 = v71;
                    v33 = v83;
                    if ( v83 )
                    {
                      v83 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                    }
                    if ( (*(int (__fastcall **)(_QWORD, HSTRING, __int64 *))(**((_QWORD **)v32 + 2) + 120LL))(
                           *((_QWORD *)v32 + 2),
                           v87,
                           &v83) >= 0 )
                    {
                      v38 = v83;
                      v39 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 48LL);
                      v40 = v81;
                      if ( v81 )
                      {
                        v81 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                      }
                      if ( v39(v38, &v81) >= 0 )
                      {
                        for ( i = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v81 + 56LL))(v81, v80);
                              i >= 0 && v80[0];
                              i = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v81 + 64LL))(v81, v80) )
                        {
                          v82 = 0;
                          v86 = 0;
                          Sid = 0;
                          v90 = 0;
                          if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v81 + 48LL))(v81, &v82) >= 0 )
                          {
                            if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v82 + 56LL))(v82, &v90) >= 0 )
                            {
                              if ( v90 == 2 )
                              {
                                if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v82 + 48LL))(v82, &v86) >= 0 )
                                {
                                  hasEmbedNull = 0;
                                  WindowsStringHasEmbeddedNull(v86, &hasEmbedNull);
                                  if ( hasEmbedNull )
                                  {
                                    if ( v86 )
                                      WindowsDeleteString(v86);
                                    v50 = v82;
                                    if ( v82 )
                                    {
                                      v82 = 0;
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                                    }
                                  }
                                  else
                                  {
                                    StringRawBuffer = WindowsGetStringRawBuffer(v86, 0);
                                    if ( ConvertStringSidToSidW(StringRawBuffer, &Sid) )
                                    {
                                      LengthSid = GetLengthSid(Sid);
                                      v92 = -1;
                                      if ( (*(int (__fastcall **)(__int64, _QWORD, PSID, __int64, int *))(*(_QWORD *)v73 + 184LL))(
                                             v73,
                                             LengthSid,
                                             Sid,
                                             1,
                                             &v92) >= 0 )
                                      {
                                        v54 = CSusSortedArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>::Add(
                                                &v93,
                                                &v92,
                                                1);
                                        PackageManager = v54;
                                        if ( v54 < 0 )
                                        {
                                          if ( v54 != -2145124333 )
                                          {
                                            if ( v86 )
                                              WindowsDeleteString(v86);
                                            v61 = v82;
                                            if ( v82 )
                                            {
                                              v82 = 0;
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                                            }
                                            v62 = v81;
                                            if ( v81 )
                                            {
                                              v81 = 0;
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                                            }
                                            v63 = v83;
                                            if ( v83 )
                                            {
                                              v83 = 0;
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
                                            }
                                            if ( v87 )
                                              WindowsDeleteString(v87);
                                            v64 = v84;
                                            if ( v84 )
                                            {
                                              v84 = 0;
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
                                            }
                                            v65 = v85;
                                            if ( v85 )
                                            {
                                              v85 = 0;
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                                            }
                                            goto LABEL_169;
                                          }
                                          PackageManager = 0;
                                        }
                                      }
                                      LocalFree(Sid);
                                      if ( v86 )
                                        WindowsDeleteString(v86);
                                      v55 = v82;
                                      if ( v82 )
                                      {
                                        v82 = 0;
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                                      }
                                    }
                                    else
                                    {
                                      if ( v86 )
                                        WindowsDeleteString(v86);
                                      v52 = v82;
                                      if ( v82 )
                                      {
                                        v82 = 0;
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                                      }
                                    }
                                  }
                                }
                                else
                                {
                                  if ( v86 )
                                    WindowsDeleteString(v86);
                                  v49 = v82;
                                  if ( v82 )
                                  {
                                    v82 = 0;
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
                                  }
                                }
                              }
                              else
                              {
                                if ( v86 )
                                  WindowsDeleteString(v86);
                                v48 = v82;
                                if ( v82 )
                                {
                                  v82 = 0;
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
                                }
                              }
                            }
                            else
                            {
                              if ( v86 )
                                WindowsDeleteString(v86);
                              v47 = v82;
                              if ( v82 )
                              {
                                v82 = 0;
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                              }
                            }
                          }
                          else
                          {
                            if ( v86 )
                              WindowsDeleteString(v86);
                            v46 = v82;
                            if ( v82 )
                            {
                              v82 = 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                            }
                          }
                        }
                        v56 = v81;
                        if ( v81 )
                        {
                          v81 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                        }
                        v57 = v83;
                        if ( v83 )
                        {
                          v83 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
                        }
                        if ( v87 )
                          WindowsDeleteString(v87);
                        v58 = v84;
                        if ( v84 )
                        {
                          v84 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
                        }
                        v59 = v85;
                        if ( v85 )
                        {
                          v85 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
                        }
                      }
                      else
                      {
                        v41 = v81;
                        if ( v81 )
                        {
                          v81 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                        }
                        v42 = v83;
                        if ( v83 )
                        {
                          v83 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                        }
                        if ( v87 )
                          WindowsDeleteString(v87);
                        v43 = v84;
                        if ( v84 )
                        {
                          v84 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                        }
                        v44 = v85;
                        if ( v85 )
                        {
                          v85 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                        }
                      }
                    }
                    else
                    {
                      v34 = v81;
                      if ( v81 )
                      {
                        v81 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                      }
                      v35 = v83;
                      if ( v83 )
                      {
                        v83 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                      }
                      if ( v87 )
                        WindowsDeleteString(v87);
                      v36 = v84;
                      if ( v84 )
                      {
                        v84 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                      }
                      v37 = v85;
                      if ( v85 )
                      {
                        v85 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                      }
                    }
                  }
                  else
                  {
                    v28 = v81;
                    if ( v81 )
                    {
                      v81 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                    }
                    v29 = v83;
                    if ( v83 )
                    {
                      v83 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                    }
                    if ( v87 )
                      WindowsDeleteString(v87);
                    v30 = v84;
                    if ( v84 )
                    {
                      v84 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                    }
                    v31 = v85;
                    if ( v85 )
                    {
                      v85 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    }
                  }
                }
                else
                {
                  v24 = v81;
                  if ( v81 )
                  {
                    v81 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                  }
                  v25 = v83;
                  if ( v83 )
                  {
                    v83 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                  }
                  if ( v87 )
                    WindowsDeleteString(v87);
                  v26 = v84;
                  if ( v84 )
                  {
                    v84 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                  }
                  v27 = v85;
                  if ( v85 )
                  {
                    v85 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                  }
                }
              }
              else
              {
                v17 = v81;
                if ( v81 )
                {
                  v81 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                }
                v18 = v83;
                if ( v83 )
                {
                  v83 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                }
                if ( v87 )
                  WindowsDeleteString(v87);
                v19 = v84;
                if ( v84 )
                {
                  v84 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                }
                v20 = v85;
                if ( v85 )
                {
                  v85 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                }
              }
            }
            while ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v88 + 64LL))(v88, v80) >= 0 );
          }
          if ( ++v6 >= v70 )
          {
            if ( PackageManager < 0 )
              break;
            v60 = DWORD1(v95);
            *(_QWORD *)a5 = v94;
            *(_DWORD *)v74 = v60;
            v94 = 0;
            *(_QWORD *)&v95 = 0;
            goto LABEL_170;
          }
        }
      }
    }
    else
    {
      PackageManager = -2147024809;
    }
  }
  else
  {
    PackageManager = -2147467261;
  }
LABEL_169:
  WUTrace("AppXUtil::GetApplicableUsersForCategories", 440, 0x100000, 3, PackageManager, L"Method failed");
LABEL_170:
  CSusArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>::~CSusArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>(&v93);
  v66 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  }
  v67 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  }
  v68 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(struct CPackageManagerWrapper *))(*(_QWORD *)v68 + 16LL))(v68);
  }
  return (unsigned int)PackageManager;
}

```

## disassembly

```asm
0x18021b2b8  mov     [rsp-8+arg_8], rbx
0x18021b2bd  push    rbp
0x18021b2be  push    rsi
0x18021b2bf  push    rdi
0x18021b2c0  push    r12
0x18021b2c2  push    r13
0x18021b2c4  push    r14
0x18021b2c6  push    r15
0x18021b2c8  lea     rbp, [rsp-30h]
0x18021b2cd  sub     rsp, 130h
0x18021b2d4  mov     rax, cs:__security_cookie
0x18021b2db  xor     rax, rsp
0x18021b2de  mov     [rbp+60h+var_40], rax
0x18021b2e2  mov     [rsp+160h+var_110], r9
0x18021b2e7  mov     [rsp+160h+var_118], r8
0x18021b2ec  mov     r14d, edx
0x18021b2ef  mov     [rsp+160h+var_130], edx
0x18021b2f3  mov     [rsp+160h+var_120], rcx
0x18021b2f8  mov     r13, [rbp+60h+arg_20]
0x18021b2ff  xor     r15d, r15d
0x18021b302  mov     [rsp+160h+var_128], r15
0x18021b307  mov     [rbp+60h+var_78], r15
0x18021b30b  mov     [rbp+60h+var_80], r15
0x18021b30f  mov     [rbp+60h+var_C0], r15b
0x18021b313  xorps   xmm0, xmm0
0x18021b316  movups  [rbp+60h+var_60], xmm0
0x18021b31a  movups  [rbp+60h+var_50], xmm0
0x18021b31e  mov     ebx, r15d
0x18021b321  mov     qword ptr [rbp+60h+var_60+8], rbx
0x18021b325  mov     qword ptr [rbp+60h+var_50], r15
0x18021b329  mov     esi, r15d
0x18021b32c  lea     rdx, ??_7?$CSusSortedArrayList@KV?$CSusSortedArrayListItemOpsBasic@K@@@@6B@; const CSusSortedArrayList<ulong,CSusSortedArrayListItemOpsBasic<ulong>>::`vftable'
0x18021b333  mov     qword ptr [rbp+60h+var_60], rdx
0x18021b337  mov     dword ptr [rbp+60h+var_50+8], r15d
0x18021b33b  test    r9, r9
0x18021b33e  jz      loc_18021BC53
0x18021b344  test    r13, r13
0x18021b347  jz      loc_18021BC53
0x18021b34d  mov     [r9], r15d
0x18021b350  mov     [r13+0], r15
0x18021b354  test    rcx, rcx
0x18021b357  jz      loc_18021BC4C
0x18021b35d  test    r14d, r14d
0x18021b360  jz      loc_18021BC4C
0x18021b366  test    r8, r8
0x18021b369  jz      loc_18021BC4C
0x18021b36f  lea     rcx, [rsp+160h+var_128]; struct CPackageManagerWrapper **
0x18021b374  call    ?GetPackageManager@@YAJPEAPEAVCPackageManagerWrapper@@@Z; GetPackageManager(CPackageManagerWrapper * *)
0x18021b379  mov     edi, eax
0x18021b37b  test    eax, eax
0x18021b37d  js      loc_18021BC58
0x18021b383  mov     r12d, r15d
0x18021b386  test    r14d, r14d
0x18021b389  jz      loc_18021BB8C
0x18021b38f  mov     r8d, 0FFFFFFFFh
0x18021b395  mov     r15, [rsp+160h+var_128]
0x18021b39a  mov     rcx, [rbp+60h+var_78]
0x18021b39e  xor     edx, edx
0x18021b3a0  test    rcx, rcx
0x18021b3a3  jz      short loc_18021B3BD
0x18021b3a5  mov     [rbp+60h+var_78], rdx
0x18021b3a9  mov     rax, [rcx]
0x18021b3ac  mov     rax, [rax+10h]
0x18021b3b0  call    _guard_dispatch_icall
0x18021b3b5  xor     edx, edx
0x18021b3b7  mov     r8d, 0FFFFFFFFh
0x18021b3bd  mov     esi, r12d
0x18021b3c0  mov     rax, [rsp+160h+var_120]
0x18021b3c5  mov     rax, [rax+rsi*8]
0x18021b3c9  mov     rdi, [rax+8]
0x18021b3cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18021b3d1  inc     rbx
0x18021b3d4  cmp     [rdi+rbx*2], dx
0x18021b3d8  jnz     short loc_18021B3D1
0x18021b3da  cmp     rbx, r8
0x18021b3dd  jbe     short loc_18021B3F7
0x18021b3df  mov     ebx, r8d
0x18021b3e2  xor     r9d, r9d; lpArguments
0x18021b3e5  xor     r8d, r8d; nNumberOfArguments
0x18021b3e8  lea     edx, [r9+1]; dwExceptionFlags
0x18021b3ec  mov     ecx, 0C000000Dh; dwExceptionCode
0x18021b3f1  call    cs:__imp_RaiseException
0x18021b3f7  lea     r9, [rsp+160h+string]; string
0x18021b3fc  lea     r8, [rsp+160h+hstringHeader]; hstringHeader
0x18021b401  mov     edx, ebx; length
0x18021b403  mov     rcx, rdi; sourceString
0x18021b406  call    cs:__imp_WindowsCreateStringReference
0x18021b40c  mov     r14, [rsp+160h+string]
0x18021b411  mov     rax, [rsp+160h+var_120]
0x18021b416  mov     rax, [rax+rsi*8]
0x18021b41a  mov     rdi, [rax]
0x18021b41d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18021b421  xor     eax, eax
0x18021b423  inc     rbx
0x18021b426  cmp     [rdi+rbx*2], ax
0x18021b42a  jnz     short loc_18021B423
0x18021b42c  mov     eax, 0FFFFFFFFh
0x18021b431  cmp     rbx, rax
0x18021b434  jbe     short loc_18021B44D
0x18021b436  mov     ebx, eax
0x18021b438  xor     r9d, r9d; lpArguments
0x18021b43b  xor     r8d, r8d; nNumberOfArguments
0x18021b43e  lea     edx, [r9+1]; dwExceptionFlags
0x18021b442  mov     ecx, 0C000000Dh; dwExceptionCode
0x18021b447  call    cs:__imp_RaiseException
0x18021b44d  lea     r9, [rsp+160h+var_E8]; string
0x18021b452  lea     r8, [rbp+60h+var_E0]; hstringHeader
0x18021b456  mov     edx, ebx; length
0x18021b458  mov     rcx, rdi; sourceString
0x18021b45b  call    cs:__imp_WindowsCreateStringReference
0x18021b461  mov     rcx, [r15+18h]
0x18021b465  mov     rax, [rcx]
0x18021b468  lea     rdx, [rbp+60h+var_78]
0x18021b46c  mov     [rsp+160h+var_140], rdx
0x18021b471  mov     r9d, 3Fh ; '?'
0x18021b477  mov     r8, r14
0x18021b47a  mov     rdx, [rsp+160h+var_E8]
0x18021b47f  mov     rax, [rax+58h]
0x18021b483  call    _guard_dispatch_icall
0x18021b488  mov     edi, eax
0x18021b48a  xor     r15d, r15d
0x18021b48d  test    eax, eax
0x18021b48f  js      loc_18021BC58
0x18021b495  mov     rbx, [rbp+60h+var_78]
0x18021b499  mov     rax, [rbx]
0x18021b49c  mov     rdi, [rax+30h]
0x18021b4a0  mov     rcx, [rbp+60h+var_80]
0x18021b4a4  test    rcx, rcx
0x18021b4a7  jz      short loc_18021B4BA
0x18021b4a9  mov     [rbp+60h+var_80], r15
0x18021b4ad  mov     rdx, [rcx]
0x18021b4b0  mov     rax, [rdx+10h]
0x18021b4b4  call    _guard_dispatch_icall
0x18021b4b9  nop
0x18021b4ba  lea     rdx, [rbp+60h+var_80]
0x18021b4be  mov     rcx, rbx
0x18021b4c1  mov     rax, rdi
0x18021b4c4  call    _guard_dispatch_icall
0x18021b4c9  mov     edi, eax
0x18021b4cb  test    eax, eax
0x18021b4cd  js      loc_18021BC58
0x18021b4d3  mov     rcx, [rbp+60h+var_80]
0x18021b4d7  mov     rax, [rcx]
0x18021b4da  lea     rdx, [rbp+60h+var_C0]
0x18021b4de  mov     rax, [rax+38h]
0x18021b4e2  call    _guard_dispatch_icall
0x18021b4e7  test    eax, eax
0x18021b4e9  js      loc_18021BB6F
0x18021b4ef  mov     r14d, 0FFFFFFFFh
0x18021b4f5  cmp     [rbp+60h+var_C0], r15b
0x18021b4f9  jz      loc_18021BB6F
0x18021b4ff  mov     [rbp+60h+var_98], r15
0x18021b503  mov     [rbp+60h+var_A0], r15
0x18021b507  mov     [rbp+60h+var_88], r15
0x18021b50b  mov     [rbp+60h+var_A8], r15
0x18021b50f  mov     [rbp+60h+var_B8], r15
0x18021b513  mov     rcx, [rbp+60h+var_80]
0x18021b517  mov     rax, [rcx]
0x18021b51a  lea     rdx, [rbp+60h+var_98]
0x18021b51e  mov     rax, [rax+30h]
0x18021b522  call    _guard_dispatch_icall
0x18021b527  test    eax, eax
0x18021b529  jns     short loc_18021B5A8
0x18021b52b  mov     rcx, [rbp+60h+var_B8]
0x18021b52f  test    rcx, rcx
0x18021b532  jz      short loc_18021B545
0x18021b534  mov     [rbp+60h+var_B8], r15
0x18021b538  mov     rax, [rcx]
0x18021b53b  mov     rax, [rax+10h]
0x18021b53f  call    _guard_dispatch_icall
0x18021b544  nop
0x18021b545  mov     rcx, [rbp+60h+var_A8]
0x18021b549  test    rcx, rcx
0x18021b54c  jz      short loc_18021B55F
0x18021b54e  mov     [rbp+60h+var_A8], r15
0x18021b552  mov     rax, [rcx]
0x18021b555  mov     rax, [rax+10h]
0x18021b559  call    _guard_dispatch_icall
0x18021b55e  nop
0x18021b55f  mov     rcx, [rbp+60h+var_88]; string
0x18021b563  test    rcx, rcx
0x18021b566  jz      short loc_18021B56F
0x18021b568  call    cs:__imp_WindowsDeleteString
0x18021b56e  nop
0x18021b56f  mov     rcx, [rbp+60h+var_A0]
0x18021b573  test    rcx, rcx
0x18021b576  jz      short loc_18021B589
0x18021b578  mov     [rbp+60h+var_A0], r15
0x18021b57c  mov     rax, [rcx]
0x18021b57f  mov     rax, [rax+10h]
0x18021b583  call    _guard_dispatch_icall
0x18021b588  nop
0x18021b589  mov     rcx, [rbp+60h+var_98]
0x18021b58d  test    rcx, rcx
0x18021b590  jz      short loc_18021B5A3
0x18021b592  mov     [rbp+60h+var_98], r15
0x18021b596  mov     rax, [rcx]
0x18021b599  mov     rax, [rax+10h]
0x18021b59d  call    _guard_dispatch_icall
0x18021b5a2  nop
0x18021b5a3  jmp     loc_18021BB53
0x18021b5a8  mov     rbx, [rbp+60h+var_98]
0x18021b5ac  mov     rax, [rbx]
0x18021b5af  mov     rsi, [rax+30h]
0x18021b5b3  mov     rcx, [rbp+60h+var_A0]
0x18021b5b7  test    rcx, rcx
0x18021b5ba  jz      short loc_18021B5CD
0x18021b5bc  mov     [rbp+60h+var_A0], r15
0x18021b5c0  mov     rdx, [rcx]
0x18021b5c3  mov     rax, [rdx+10h]
0x18021b5c7  call    _guard_dispatch_icall
0x18021b5cc  nop
0x18021b5cd  lea     rdx, [rbp+60h+var_A0]
0x18021b5d1  mov     rcx, rbx
0x18021b5d4  mov     rax, rsi
0x18021b5d7  call    _guard_dispatch_icall
0x18021b5dc  test    eax, eax
0x18021b5de  jns     short loc_18021B65D
0x18021b5e0  mov     rcx, [rbp+60h+var_B8]
0x18021b5e4  test    rcx, rcx
0x18021b5e7  jz      short loc_18021B5FA
0x18021b5e9  mov     [rbp+60h+var_B8], r15
0x18021b5ed  mov     rax, [rcx]
0x18021b5f0  mov     rax, [rax+10h]
0x18021b5f4  call    _guard_dispatch_icall
0x18021b5f9  nop
0x18021b5fa  mov     rcx, [rbp+60h+var_A8]
0x18021b5fe  test    rcx, rcx
0x18021b601  jz      short loc_18021B614
0x18021b603  mov     [rbp+60h+var_A8], r15
0x18021b607  mov     rax, [rcx]
0x18021b60a  mov     rax, [rax+10h]
0x18021b60e  call    _guard_dispatch_icall
0x18021b613  nop
0x18021b614  mov     rcx, [rbp+60h+var_88]; string
0x18021b618  test    rcx, rcx
0x18021b61b  jz      short loc_18021B624
0x18021b61d  call    cs:__imp_WindowsDeleteString
0x18021b623  nop
0x18021b624  mov     rcx, [rbp+60h+var_A0]
0x18021b628  test    rcx, rcx
0x18021b62b  jz      short loc_18021B63E
0x18021b62d  mov     [rbp+60h+var_A0], r15
0x18021b631  mov     rax, [rcx]
0x18021b634  mov     rax, [rax+10h]
0x18021b638  call    _guard_dispatch_icall
0x18021b63d  nop
0x18021b63e  mov     rcx, [rbp+60h+var_98]
0x18021b642  test    rcx, rcx
0x18021b645  jz      short loc_18021B658
0x18021b647  mov     [rbp+60h+var_98], r15
0x18021b64b  mov     rax, [rcx]
0x18021b64e  mov     rax, [rax+10h]
0x18021b652  call    _guard_dispatch_icall
0x18021b657  nop
0x18021b658  jmp     loc_18021BB53
0x18021b65d  mov     rcx, [rbp+60h+var_A0]
0x18021b661  mov     rax, [rcx]
0x18021b664  lea     rdx, [rbp+60h+var_88]
0x18021b668  mov     rax, [rax+60h]
0x18021b66c  call    _guard_dispatch_icall
0x18021b671  test    eax, eax
0x18021b673  jns     short loc_18021B6F2
0x18021b675  mov     rcx, [rbp+60h+var_B8]
0x18021b679  test    rcx, rcx
0x18021b67c  jz      short loc_18021B68F
0x18021b67e  mov     [rbp+60h+var_B8], r15
0x18021b682  mov     rax, [rcx]
0x18021b685  mov     rax, [rax+10h]
0x18021b689  call    _guard_dispatch_icall
0x18021b68e  nop
0x18021b68f  mov     rcx, [rbp+60h+var_A8]
0x18021b693  test    rcx, rcx
0x18021b696  jz      short loc_18021B6A9
0x18021b698  mov     [rbp+60h+var_A8], r15
0x18021b69c  mov     rax, [rcx]
0x18021b69f  mov     rax, [rax+10h]
0x18021b6a3  call    _guard_dispatch_icall
0x18021b6a8  nop
0x18021b6a9  mov     rcx, [rbp+60h+var_88]; string
0x18021b6ad  test    rcx, rcx
0x18021b6b0  jz      short loc_18021B6B9
0x18021b6b2  call    cs:__imp_WindowsDeleteString
0x18021b6b8  nop
0x18021b6b9  mov     rcx, [rbp+60h+var_A0]
0x18021b6bd  test    rcx, rcx
0x18021b6c0  jz      short loc_18021B6D3
0x18021b6c2  mov     [rbp+60h+var_A0], r15
0x18021b6c6  mov     rax, [rcx]
0x18021b6c9  mov     rax, [rax+10h]
0x18021b6cd  call    _guard_dispatch_icall
0x18021b6d2  nop
0x18021b6d3  mov     rcx, [rbp+60h+var_98]
0x18021b6d7  test    rcx, rcx
0x18021b6da  jz      short loc_18021B6ED
0x18021b6dc  mov     [rbp+60h+var_98], r15
0x18021b6e0  mov     rax, [rcx]
0x18021b6e3  mov     rax, [rax+10h]
0x18021b6e7  call    _guard_dispatch_icall
0x18021b6ec  nop
  ... truncated ...
```
