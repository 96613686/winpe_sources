# CFSFolder::_GetMountPoint(CMountPoint * *)

- ea: `0x180055cf0`
- end: `0x180056573`
- name: `?_GetMountPoint@CFSFolder@@IEAAJPEAPEAVCMountPoint@@@Z`
- size: `2179`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, struct CMountPoint **)`
- caller_count: `6`
- callee_count: `17`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800557d8`
- `0x1800572c0`
- `0x18005a2d0`
- `0x180288730`
- `0x1802a2f00`
- `0x18032cef0`

## callees

- `0x180036df0`
- `0x180038f50`
- `0x18003ad20`
- `0x18004e06c`
- `0x1800551d0`
- `0x1800559e0`
- `0x180055cf0`
- `0x180056580`
- `0x180056df0`
- `0x180103290`
- `0x180159c78`
- `0x1802d7a50`
- `0x180363e2c`
- `0x1803b1f60`
- `0x1803b29ea`
- `0x1803b2ac0`
- `0x1803b69c5`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180056523`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180056523`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055e53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055e53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055f9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055f9a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005617a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005632c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005617a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005632c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180056220`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180056220`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180055e40`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180055e40`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800560a1`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800560a1`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180056119`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800563de`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180056119`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800563de`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180055e0d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180055e0d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800564f4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800564f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055da1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055da1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056055`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFSFolder::_GetMountPoint(CFSFolder *this, struct CMountPoint **a2)
{
  struct CMtPtLocal *v2; // rsi
  const KNOWNFOLDERID *v4; // rcx
  __int64 v5; // rax
  _BYTE *v6; // rbx
  __int64 v7; // rcx
  char *v8; // rax
  size_t v9; // rdi
  size_t v10; // r14
  WCHAR *v11; // rax
  __int64 v12; // r8
  const WCHAR *v13; // rsi
  WCHAR *v14; // r12
  volatile signed __int32 *v15; // rdi
  int DriveNumberW; // ebx
  int Error; // r15d
  int v18; // r13d
  __int64 v19; // rbx
  WCHAR *v20; // r14
  WCHAR *v21; // r8
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rdi
  struct CMountPoint *v24; // rdi
  __int64 v25; // r8
  int v26; // ebx
  WCHAR *v27; // rcx
  HRESULT v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r9
  unsigned __int64 v32; // rdx
  const WCHAR *v33; // rax
  const WCHAR *i; // rcx
  WCHAR *v35; // r8
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // rdi
  __int64 v38; // rcx
  WCHAR *v39; // rdx
  __int64 v40; // r8
  WCHAR v41; // ax
  _WORD *v42; // rcx
  unsigned __int64 v43; // rdx
  _WORD *v44; // rax
  unsigned __int64 j; // rcx
  __int64 v46; // rcx
  __int64 v47; // r8
  WCHAR *p_szVolumePathName; // rdx
  WCHAR v49; // ax
  WCHAR *v50; // rcx
  const ITEMIDLIST *v51; // rcx
  HRESULT v52; // eax
  __int64 v53; // rcx
  const ITEMIDLIST *v54; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  volatile signed __int32 *v56; // [rsp+30h] [rbp-D0h]
  int v57; // [rsp+38h] [rbp-C8h]
  int v58; // [rsp+3Ch] [rbp-C4h]
  LPCWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  struct CMountPoint *v60[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct CMtPtLocal *v61[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR szVolumePathName; // [rsp+70h] [rbp-90h] BYREF
  char v63[526]; // [rsp+72h] [rbp-8Eh] BYREF
  WCHAR v64[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v65[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  v2 = (struct CMtPtLocal *)a2;
  v61[0] = (struct CMtPtLocal *)a2;
  *a2 = 0;
  pszPath = 0;
  v4 = (const KNOWNFOLDERID *)((char *)this + 496);
  v5 = *(_QWORD *)&v4->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v4->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v5 = *(_QWORD *)v4->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v5 )
  {
    v29 = SHGetKnownFolderPath(v4, 0x4000u, 0, (PWSTR *)&pszPath);
    v26 = v29;
    if ( v29 >= 0 )
      goto LABEL_13;
    v30 = 1163;
    goto LABEL_51;
  }
  v6 = (_BYTE *)*((_QWORD *)this + 56);
  if ( !v6 )
  {
    v51 = (const ITEMIDLIST *)*((_QWORD *)this + 55);
    if ( v51 )
    {
      v52 = SHGetNameFromIDList(v51, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pszPath);
      v26 = v52;
      if ( v52 < 0 )
      {
        v30 = 1177;
        v31 = (unsigned int)v52;
        goto LABEL_53;
      }
LABEL_126:
      if ( pszPath )
      {
        *((_QWORD *)this + 56) = SysAllocString(pszPath);
        goto LABEL_13;
      }
      v26 = -2147024893;
LABEL_54:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2214,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v26,
        bIgnoreCase);
      v27 = (WCHAR *)pszPath;
      goto LABEL_55;
    }
    v54 = (const ITEMIDLIST *)*((_QWORD *)this + 54);
    if ( !v54 )
      goto LABEL_126;
    v29 = SHGetNameFromIDList(v54, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pszPath);
    v26 = v29;
    if ( v29 >= 0 )
      goto LABEL_126;
    v30 = 1181;
LABEL_51:
    v31 = (unsigned int)v29;
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)v31,
      bIgnoreCase);
    goto LABEL_54;
  }
  v7 = 0x7FFFFFFF;
  v8 = (char *)*((_QWORD *)this + 56);
  do
  {
    if ( !*(_WORD *)v8 )
      break;
    v8 += 2;
    --v7;
  }
  while ( v7 );
  v9 = 2 * ((v8 - v6) >> 1);
  v10 = v9 + 2;
  v11 = (WCHAR *)CoTaskMemAlloc(v9 + 2);
  v13 = v11;
  if ( !v11 )
  {
    pszPath = 0;
    v26 = -2147024882;
    v31 = 2147942414LL;
    v30 = 1171;
    goto LABEL_53;
  }
  if ( v9 )
  {
    if ( v10 < v9 )
    {
      memset_0(v11, 0, v10);
      *(_DWORD *)_o__errno(v53) = 34;
      invalid_parameter_noinfo();
    }
    else
    {
      memcpy_0(v11, v6, v9);
    }
  }
  v13[v9 / 2] = 0;
  pszPath = v13;
  v2 = v61[0];
LABEL_13:
  v14 = (WCHAR *)pszPath;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Shell32_MountPoint_GetMountPoint_Start,
      v12,
      1,
      v60);
  *(_QWORD *)v2 = 0;
  v15 = 0;
  v56 = 0;
  v60[0] = 0;
  DriveNumberW = PathGetDriveNumberW(v14);
  v57 = DriveNumberW;
  if ( DriveNumberW != -1 )
  {
    InitOnceExecuteOnce(&InitOnce, _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_, &Parameter, 0);
    EnterCriticalSection(&Parameter);
    if ( !HIDWORD(qword_180828300) )
    {
      if ( CMountPoint::_ExtractDriveLetter(v14) || (unsigned int)CMountPoint::_IsNetDriveLazyLoadNetDLLs(DriveNumberW) )
      {
        CMountPoint::_GetMountPointForDriveLetter(DriveNumberW, v60);
        v24 = v60[0];
        goto LABEL_40;
      }
      memset_0(v63, 0, 0x206u);
      szVolumePathName = 0;
      Error = 1;
      if ( qword_1808282E8 )
      {
        v58 = *(_DWORD *)qword_1808282E8;
        v18 = 0;
        if ( *(int *)qword_1808282E8 > 0 )
        {
          while ( 1 )
          {
            if ( v15 )
            {
LABEL_37:
              DriveNumberW = v57;
              v2 = v61[0];
              if ( szVolumePathName )
                goto LABEL_38;
              goto LABEL_65;
            }
            v19 = qword_1808282E8 && v18 >= 0 && v18 < *(_DWORD *)qword_1808282E8
                ? *(_QWORD *)(*(_QWORD *)(qword_1808282E8 + 8) + 8LL * v18)
                : 0LL;
            v20 = (WCHAR *)(v19 + 520);
            if ( (unsigned __int64)(v19 + 520) < 0x10000 )
            {
              if ( SHGetFolderPathW(0, (unsigned int)v20 | 0x4000, 0, 0, v64) < 0 )
                goto LABEL_36;
              v21 = v64;
            }
            else
            {
              v21 = (WCHAR *)(v19 + 520);
            }
            v22 = -1;
            do
              ++v22;
            while ( v21[v22] );
            if ( v22 && v21[v22 - 1] == 92 )
              --v22;
            v23 = -1;
            do
              ++v23;
            while ( v14[v23] );
            if ( v23 && v14[v23 - 1] == 92 )
              --v23;
            if ( v22 <= v23 )
            {
              v32 = v22;
              if ( v14[v22] != 92 )
                v32 = v23;
              if ( v32 == v22 && CompareStringOrdinal(v14, v32, v21, v22, 1) == 2 )
                break;
            }
LABEL_35:
            v15 = v56;
LABEL_36:
            if ( ++v18 >= v58 )
              goto LABEL_37;
          }
          if ( v22 < v23 )
          {
            v33 = &v14[v22 + 1];
            for ( i = &v14[v23]; v33 < i; ++v33 )
            {
              if ( *v33 == 92 )
                break;
            }
          }
          if ( (unsigned __int64)v14 < 0x10000 )
          {
            if ( SHGetFolderPathW(0, (unsigned int)v14 | 0x4000, 0, 0, v65) < 0 )
              goto LABEL_87;
            v35 = v65;
          }
          else
          {
            v35 = v14;
          }
          v36 = -1;
          do
            ++v36;
          while ( v35[v36] );
          if ( v36 && v35[v36 - 1] == 92 )
            --v36;
          v37 = -1;
          do
            ++v37;
          while ( *(_WORD *)(v19 + 2 * v37) );
          if ( v37 && *(_WORD *)(v19 + 2 * v37 - 2) == 92 )
            --v37;
          if ( v36 <= v37 )
          {
            v43 = v36;
            if ( *(_WORD *)(v19 + 2 * v36) != 92 )
              v43 = v37;
            if ( v43 == v36 && CompareStringOrdinal((LPCWCH)v19, v43, v35, v36, 1) == 2 )
            {
              if ( v36 < v37 )
              {
                v44 = (_WORD *)(v19 + 2 * (v36 + 1));
                for ( j = v19 + 2 * v37; (unsigned __int64)v44 < j; ++v44 )
                {
                  if ( *v44 == 92 )
                    break;
                }
              }
              v15 = *(volatile signed __int32 **)(v19 + 1040);
              v56 = v15;
              v60[0] = (struct CMountPoint *)v15;
              _InterlockedIncrement(v15 + 12);
              v46 = 2147483646;
              v47 = 260;
              p_szVolumePathName = &szVolumePathName;
              do
              {
                if ( !v46 )
                  break;
                v49 = *v20;
                if ( !*v20 )
                  break;
                ++v20;
                *p_szVolumePathName++ = v49;
                --v46;
                --v47;
              }
              while ( v47 );
              v50 = p_szVolumePathName - 1;
              if ( v47 )
                v50 = p_szVolumePathName;
              *v50 = 0;
              ++*(_DWORD *)(v19 + 1048);
              Error = 0;
              goto LABEL_36;
            }
          }
LABEL_87:
          if ( (szVolumePathName
             || GetVolumePathNameW(v14, &szVolumePathName, 0x104u)
             || (int)ResultFromKnownLastError() >= 0)
            && !StrCmpIW(&szVolumePathName, (PCWSTR)(v19 + 520)) )
          {
            v15 = *(volatile signed __int32 **)(v19 + 1040);
            v56 = v15;
            v60[0] = (struct CMountPoint *)v15;
            _InterlockedIncrement(v15 + 12);
            v38 = 2147483646;
            v39 = v14;
            v40 = 260;
            do
            {
              if ( !v38 )
                break;
              v41 = *v39;
              if ( !*v39 )
                break;
              ++v39;
              *(_WORD *)v19 = v41;
              v19 += 2;
              --v38;
              --v40;
            }
            while ( v40 );
            v42 = (_WORD *)(v19 - 2);
            if ( v40 )
              v42 = (_WORD *)v19;
            *v42 = 0;
            Error = 0;
            goto LABEL_36;
          }
          goto LABEL_35;
        }
      }
LABEL_65:
      if ( !GetVolumePathNameW(v14, &szVolumePathName, 0x104u) )
        Error = ResultFromKnownLastError();
LABEL_38:
      if ( Error >= 0 && !v15 )
      {
        PathCchAddBackslash(&szVolumePathName, 0x104u);
        if ( CMountPoint::_ExtractDriveLetter(&szVolumePathName) )
        {
          CMountPoint::_GetMountPointForDriveLetter(DriveNumberW, v60);
          v24 = v60[0];
        }
        else
        {
          v61[0] = 0;
          CMountPoint::_GetMountPointForFolder(&szVolumePathName, v61);
          v24 = v61[0];
        }
        if ( v24 )
          CDriveLetterCache::AddPathLookupEntry((CDriveLetterCache *)&qword_180827FA8, v14, &szVolumePathName, v24);
        goto LABEL_40;
      }
    }
    v24 = (struct CMountPoint *)v56;
LABEL_40:
    LeaveCriticalSection(&Parameter);
    goto LABEL_41;
  }
  CMountPoint::GetSimulatedMountPointFromVolumeGuid(v14, v60);
  v24 = v60[0];
LABEL_41:
  v26 = -2147467259;
  if ( v24 )
  {
    *(_QWORD *)v2 = v24;
    v26 = 0;
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Shell32_MountPoint_GetMountPoint_Stop,
      v25,
      1,
      v61);
  v27 = (WCHAR *)pszPath;
  if ( v26 >= 0 )
  {
    if ( pszPath )
      CoTaskMemFree((LPVOID)pszPath);
    return 0;
  }
LABEL_55:
  if ( v27 )
    CoTaskMemFree(v27);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180055cf0  mov     [rsp-8+arg_10], rbx
0x180055cf5  push    rbp
0x180055cf6  push    rsi
0x180055cf7  push    rdi
0x180055cf8  push    r12
0x180055cfa  push    r13
0x180055cfc  push    r14
0x180055cfe  push    r15
0x180055d00  lea     rbp, [rsp-5B0h]
0x180055d08  sub     rsp, 6B0h
0x180055d0f  mov     rax, cs:__security_cookie
0x180055d16  xor     rax, rsp
0x180055d19  mov     [rbp+5E0h+var_40], rax
0x180055d20  mov     rsi, rdx
0x180055d23  mov     [rsp+6E0h+var_688], rdx
0x180055d28  mov     rdi, rcx
0x180055d2b  mov     qword ptr [rdx], 0
0x180055d32  mov     [rsp+6E0h+pszPath], 0
0x180055d3b  add     rcx, 1F0h; rfid
0x180055d42  mov     rax, [rcx]
0x180055d45  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180055d4c  jnz     short loc_180055D59
0x180055d4e  mov     rax, [rcx+8]
0x180055d52  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180055d59  test    rax, rax
0x180055d5c  jnz     loc_180055FE4
0x180055d62  mov     rbx, [rdi+1C0h]
0x180055d69  test    rbx, rbx
0x180055d6c  jz      loc_1800564A5
0x180055d72  mov     ecx, 7FFFFFFFh
0x180055d77  mov     rax, rbx
0x180055d7a  nop     word ptr [rax+rax+00h]
0x180055d80  cmp     word ptr [rax], 0
0x180055d84  jz      short loc_180055D90
0x180055d86  add     rax, 2
0x180055d8a  sub     rcx, 1
0x180055d8e  jnz     short loc_180055D80
0x180055d90  sub     rax, rbx
0x180055d93  sar     rax, 1
0x180055d96  lea     rdi, [rax+rax]
0x180055d9a  lea     r14, [rdi+2]
0x180055d9e  mov     rcx, r14; cb
0x180055da1  call    cs:__imp_CoTaskMemAlloc
0x180055da8  nop     dword ptr [rax+rax+00h]
0x180055dad  mov     rsi, rax
0x180055db0  test    rax, rax
0x180055db3  jz      loc_18005600A
0x180055db9  test    rdi, rdi
0x180055dbc  jz      short loc_180055DD5
0x180055dbe  mov     rcx, rax; void *
0x180055dc1  cmp     r14, rdi
0x180055dc4  jb      loc_180056519
0x180055dca  mov     r8, rdi; Size
0x180055dcd  mov     rdx, rbx; Src
0x180055dd0  call    memcpy_0
0x180055dd5  xor     eax, eax
0x180055dd7  mov     [rdi+rsi], ax
0x180055ddb  mov     [rsp+6E0h+pszPath], rsi
0x180055de0  mov     rsi, [rsp+6E0h+var_688]
0x180055de5  mov     r12, [rsp+6E0h+pszPath]
0x180055dea  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180055df1  jnz     loc_1800562B8
0x180055df7  mov     qword ptr [rsi], 0
0x180055dfe  xor     edi, edi
0x180055e00  mov     [rsp+6E0h+var_6B0], rdi
0x180055e05  mov     [rsp+6E0h+var_698], rdi
0x180055e0a  mov     rcx, r12; pszPath
0x180055e0d  call    cs:__imp_PathGetDriveNumberW
0x180055e14  nop     dword ptr [rax+rax+00h]
0x180055e19  mov     ebx, eax
0x180055e1b  mov     [rsp+6E0h+var_6A8], eax
0x180055e1f  cmp     eax, 0FFFFFFFFh
0x180055e22  jz      loc_180056404
0x180055e28  xor     r9d, r9d; Context
0x180055e2b  lea     r8, Parameter; Parameter
0x180055e32  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180055e39  lea     rcx, InitOnce; InitOnce
0x180055e40  call    cs:__imp_InitOnceExecuteOnce
0x180055e47  nop     dword ptr [rax+rax+00h]
0x180055e4c  lea     rcx, Parameter; lpCriticalSection
0x180055e53  call    cs:__imp_EnterCriticalSection
0x180055e5a  nop     dword ptr [rax+rax+00h]
0x180055e5f  cmp     dword ptr cs:qword_180828300+4, edi
0x180055e65  jnz     loc_180055F8E
0x180055e6b  mov     rcx, r12; unsigned __int16 *
0x180055e6e  call    ?_ExtractDriveLetter@CMountPoint@@CAGPEBG@Z; CMountPoint::_ExtractDriveLetter(ushort const *)
0x180055e73  test    ax, ax
0x180055e76  jnz     loc_1800564DE
0x180055e7c  mov     ecx, ebx; int
0x180055e7e  call    ?_IsNetDriveLazyLoadNetDLLs@CMountPoint@@CAHH@Z; CMountPoint::_IsNetDriveLazyLoadNetDLLs(int)
0x180055e83  test    eax, eax
0x180055e85  jnz     loc_1800564DE
0x180055e8b  xor     edx, edx; Val
0x180055e8d  mov     r8d, 206h; Size
0x180055e93  lea     rcx, [rsp+6E0h+var_66E]; void *
0x180055e98  call    memset_0
0x180055e9d  xor     eax, eax
0x180055e9f  mov     [rsp+6E0h+szVolumePathName], ax
0x180055ea4  mov     r15d, 1
0x180055eaa  mov     rax, cs:qword_1808282E8
0x180055eb1  test    rax, rax
0x180055eb4  jz      loc_18005610B
0x180055eba  mov     eax, [rax]
0x180055ebc  mov     [rsp+6E0h+var_6A4], eax
0x180055ec0  xor     r13d, r13d
0x180055ec3  test    eax, eax
0x180055ec5  jle     loc_18005610B
0x180055ecb  nop     dword ptr [rax+rax+00h]
0x180055ed0  test    rdi, rdi
0x180055ed3  jnz     loc_180055F70
0x180055ed9  mov     rax, cs:qword_1808282E8
0x180055ee0  test    rax, rax
0x180055ee3  jz      loc_18005614F
0x180055ee9  test    r13d, r13d
0x180055eec  js      loc_18005614F
0x180055ef2  cmp     r13d, [rax]
0x180055ef5  jge     loc_18005614F
0x180055efb  movsxd  rcx, r13d
0x180055efe  mov     rax, [rax+8]
0x180055f02  mov     rbx, [rax+rcx*8]
0x180055f06  lea     r14, [rbx+208h]
0x180055f0d  cmp     r14, 10000h
0x180055f14  jb      loc_18005643D
0x180055f1a  mov     r8, r14; lpString2
0x180055f1d  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180055f24  inc     rsi
0x180055f27  cmp     word ptr [r8+rsi*2], 0
0x180055f2d  jnz     short loc_180055F24
0x180055f2f  test    rsi, rsi
0x180055f32  jnz     loc_18005613A
0x180055f38  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180055f3f  nop
0x180055f40  inc     rdi
0x180055f43  cmp     word ptr [r12+rdi*2], 0
0x180055f49  jnz     short loc_180055F40
0x180055f4b  test    rdi, rdi
0x180055f4e  jnz     loc_1800560F6
0x180055f54  cmp     rsi, rdi
0x180055f57  jbe     loc_180056156
0x180055f5d  mov     rdi, [rsp+6E0h+var_6B0]
0x180055f62  inc     r13d
0x180055f65  cmp     r13d, [rsp+6E0h+var_6A4]
0x180055f6a  jl      loc_180055ED0
0x180055f70  mov     ebx, [rsp+6E0h+var_6A8]
0x180055f74  mov     rsi, [rsp+6E0h+var_688]
0x180055f79  cmp     [rsp+6E0h+szVolumePathName], 0
0x180055f7f  jz      loc_18005610B
0x180055f85  test    r15d, r15d
0x180055f88  jns     loc_18005608E
0x180055f8e  mov     rdi, [rsp+6E0h+var_6B0]
0x180055f93  lea     rcx, Parameter; lpCriticalSection
0x180055f9a  call    cs:__imp_LeaveCriticalSection
0x180055fa1  nop     dword ptr [rax+rax+00h]
0x180055fa6  mov     ebx, 80004005h
0x180055fab  test    rdi, rdi
0x180055fae  jz      short loc_180055FB5
0x180055fb0  mov     [rsi], rdi
0x180055fb3  xor     ebx, ebx
0x180055fb5  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180055fbc  jnz     loc_180056290
0x180055fc2  mov     rcx, [rsp+6E0h+pszPath]; pv
0x180055fc7  test    ebx, ebx
0x180055fc9  js      loc_180056050
0x180055fcf  test    rcx, rcx
0x180055fd2  jz      short loc_180055FE0
0x180055fd4  call    cs:__imp_CoTaskMemFree
0x180055fdb  nop     dword ptr [rax+rax+00h]
0x180055fe0  xor     eax, eax
0x180055fe2  jmp     short loc_180056063
0x180055fe4  lea     r9, [rsp+6E0h+pszPath]; ppszPath
0x180055fe9  xor     r8d, r8d; hToken
0x180055fec  mov     edx, 4000h; dwFlags
0x180055ff1  call    SHGetKnownFolderPath
0x180055ff6  mov     ebx, eax
0x180055ff8  test    eax, eax
0x180055ffa  jns     loc_180055DE5
0x180056000  mov     edx, 48Bh
0x180056005  mov     r9d, eax
0x180056008  jmp     short loc_18005601C
0x18005600a  mov     [rsp+6E0h+pszPath], rsi
0x18005600f  mov     ebx, 8007000Eh
0x180056014  mov     r9d, ebx; char *
0x180056017  mov     edx, 493h; void *
0x18005601c  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180056023  mov     rcx, [rbp+5E8h]; this
0x18005602a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005602f  mov     rcx, [rbp+5E8h]; this
0x180056036  mov     r9d, ebx; char *
0x180056039  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180056040  mov     edx, 2214h; void *
0x180056045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005604a  nop
0x18005604b  mov     rcx, [rsp+6E0h+pszPath]; pv
0x180056050  test    rcx, rcx
0x180056053  jz      short loc_180056061
0x180056055  call    cs:__imp_CoTaskMemFree
0x18005605c  nop     dword ptr [rax+rax+00h]
0x180056061  mov     eax, ebx
0x180056063  mov     rcx, [rbp+5E0h+var_40]
0x18005606a  xor     rcx, rsp; StackCookie
0x18005606d  call    __security_check_cookie
0x180056072  mov     rbx, [rsp+6E0h+arg_10]
0x18005607a  add     rsp, 6B0h
0x180056081  pop     r15
0x180056083  pop     r14
0x180056085  pop     r13
0x180056087  pop     r12
0x180056089  pop     rdi
0x18005608a  pop     rsi
0x18005608b  pop     rbp
0x18005608c  retn
0x18005608e  test    rdi, rdi
0x180056091  jnz     loc_180055F8E
0x180056097  mov     edx, 104h; cchPath
0x18005609c  lea     rcx, [rsp+6E0h+szVolumePathName]; pszPath
0x1800560a1  call    cs:__imp_PathCchAddBackslash
0x1800560a8  nop     dword ptr [rax+rax+00h]
0x1800560ad  lea     rcx, [rsp+6E0h+szVolumePathName]; unsigned __int16 *
0x1800560b2  call    ?_ExtractDriveLetter@CMountPoint@@CAGPEBG@Z; CMountPoint::_ExtractDriveLetter(ushort const *)
0x1800560b7  test    ax, ax
0x1800560ba  jz      loc_18005641B
0x1800560c0  lea     rdx, [rsp+6E0h+var_698]; struct CMountPoint **
0x1800560c5  mov     ecx, ebx; int
0x1800560c7  call    ?_GetMountPointForDriveLetter@CMountPoint@@CAJHPEAPEAV1@@Z; CMountPoint::_GetMountPointForDriveLetter(int,CMountPoint * *)
0x1800560cc  mov     rdi, [rsp+6E0h+var_698]
0x1800560d1  test    rdi, rdi
0x1800560d4  jz      loc_180055F93
0x1800560da  mov     r9, rdi; struct CMountPoint *
0x1800560dd  lea     r8, [rsp+6E0h+szVolumePathName]; unsigned __int16 *
0x1800560e2  mov     rdx, r12; unsigned __int16 *
0x1800560e5  lea     rcx, qword_180827FA8; this
0x1800560ec  call    ?AddPathLookupEntry@CDriveLetterCache@@QEAAJPEBG0PEAVCMountPoint@@@Z; CDriveLetterCache::AddPathLookupEntry(ushort const *,ushort const *,CMountPoint *)
0x1800560f1  jmp     loc_180055F93
0x1800560f6  cmp     word ptr [r12+rdi*2-2], 5Ch ; '\'
0x1800560fd  jnz     loc_180055F54
0x180056103  dec     rdi
0x180056106  jmp     loc_180055F54
0x18005610b  mov     r8d, 104h; cchBufferLength
0x180056111  lea     rdx, [rsp+6E0h+szVolumePathName]; lpszVolumePathName
0x180056116  mov     rcx, r12; lpszFileName
0x180056119  call    cs:__imp_GetVolumePathNameW
0x180056120  nop     dword ptr [rax+rax+00h]
0x180056125  test    eax, eax
0x180056127  jnz     loc_180055F85
0x18005612d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180056132  mov     r15d, eax
0x180056135  jmp     loc_180055F85
0x18005613a  cmp     word ptr [r8+rsi*2-2], 5Ch ; '\'
0x180056141  jnz     loc_180055F38
0x180056147  dec     rsi
0x18005614a  jmp     loc_180055F38
0x18005614f  xor     ebx, ebx
0x180056151  jmp     loc_180055F06
0x180056156  mov     rdx, rsi
0x180056159  cmp     word ptr [r12+rsi*2], 5Ch ; '\'
0x18005615f  cmovnz  rdx, rdi; cchCount1
0x180056163  cmp     rdx, rsi
0x180056166  jnz     loc_180055F5D
0x18005616c  mov     r9d, esi; cchCount2
0x18005616f  mov     [rsp+6E0h+bIgnoreCase], 1; bIgnoreCase
0x180056177  mov     rcx, r12; lpString1
0x18005617a  call    cs:__imp_CompareStringOrdinal
0x180056181  nop     dword ptr [rax+rax+00h]
0x180056186  cmp     eax, 2
0x180056189  jnz     loc_180055F5D
0x18005618f  cmp     rsi, rdi
0x180056192  jnb     short loc_1800561B5
0x180056194  lea     rax, [r12+2]
0x180056199  lea     rax, [rax+rsi*2]
0x18005619d  lea     rcx, [r12+rdi*2]
0x1800561a1  cmp     rax, rcx
0x1800561a4  jnb     short loc_1800561B5
0x1800561a6  cmp     word ptr [rax], 5Ch ; '\'
0x1800561aa  jz      short loc_1800561B5
0x1800561ac  add     rax, 2
0x1800561b0  cmp     rax, rcx
0x1800561b3  jb      short loc_1800561A6
0x1800561b5  cmp     r12, 10000h
0x1800561bc  jb      loc_180056471
0x1800561c2  mov     r8, r12; lpString2
0x1800561c5  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800561cc  nop     dword ptr [rax+00h]
0x1800561d0  inc     rsi
0x1800561d3  cmp     word ptr [r8+rsi*2], 0
0x1800561d9  jnz     short loc_1800561D0
0x1800561db  test    rsi, rsi
0x1800561de  jnz     loc_1800562F4
0x1800561e4  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800561eb  nop     dword ptr [rax+rax+00h]
0x1800561f0  inc     rdi
0x1800561f3  cmp     word ptr [rbx+rdi*2], 0
0x1800561f8  jnz     short loc_1800561F0
0x1800561fa  test    rdi, rdi
0x1800561fd  jnz     loc_1800562E0
0x180056203  cmp     rsi, rdi
0x180056206  jbe     loc_180056309
0x18005620c  cmp     [rsp+6E0h+szVolumePathName], 0
0x180056212  jz      loc_1800563D0
0x180056218  mov     rdx, r14; psz2
0x18005621b  lea     rcx, [rsp+6E0h+szVolumePathName]; psz1
  ... truncated ...
```
