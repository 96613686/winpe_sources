# CRegZone::Init(ushort const *,int,REGZONEUSE,int)

- ea: `0x18003b2b0`
- end: `0x18003bedd`
- name: `?Init@CRegZone@@QEAAHPEBGHW4REGZONEUSE@@H@Z`
- size: `3117`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, BOOL, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003abdc`
- `0x18003bf74`
- `0x180112450`
- `0x1801133d0`
- `0x180113614`

## callees

- `0x18003b2b0`
- `0x18003bef0`
- `0x18003bf28`
- `0x18005c800`
- `0x1801272d4`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?SetKernelHandleToLowIL@@YAJPEAX@Z` at `0x18003b5b9`
- `iertutil!__imp_?SetKernelHandleToLowIL@@YAJPEAX@Z` at `0x18003b5b9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18003b331`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18003b331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b372`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b5d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b372`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b5d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b34d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b34d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x18003b790`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x18003b790`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18003b52c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18003b735`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18003b75e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18003b52c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18003b735`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18003b75e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b59f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b59f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b5e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b5e5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003bc8e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003bcae`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003bc8e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x18003bcae`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003ba61`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003baab`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003baf8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003bb33`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003ba61`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003baab`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003baf8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x18003bb33`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b50b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b718`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b859`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b8f4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b9fa`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003bc18`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003bc66`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003bce7`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b50b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b718`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b859`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b8f4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003b9fa`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003bc18`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003bc66`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003bce7`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x18003b961`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x18003bdc4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x18003b961`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x18003bdc4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bb67`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bb82`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bb9b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bbb8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bd5c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bd7c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bb67`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bb82`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bb9b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bbb8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bd5c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003bd7c`

## string_xrefs

- `0x18003be2d`: `Software\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\TemplatePolicies\`
- `0x18003bde5`: `Software\Microsoft\Windows\CurrentVersion\Internet Settings\TemplatePolicies\`
- `0x18003b32a`: `Local\ZonesLockedCacheCounterMutex`
- `0x18003b5ca`: `Local\ZonesCacheCounterMutex`
- `0x18003be86`: `TemplateIndex`

## pseudocode

```c
__int64 __fastcall CRegZone::Init(__int64 a1, const WCHAR *a2, BOOL a3, int a4)
{
  const WCHAR *v6; // r13
  __int64 *v8; // rbx
  const CHAR *v9; // r8
  HANDLE MutexA; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  __int64 v12; // rbx
  const WCHAR *v13; // rdi
  __int64 v14; // rsi
  __int64 v15; // rcx
  WCHAR *v16; // r8
  const WCHAR *v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rcx
  const wchar_t *v20; // rdx
  WCHAR *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // rcx
  const WCHAR *v26; // r8
  _WORD *v27; // r9
  _WORD *v28; // rcx
  BOOL fIgnoreHKCU; // eax
  PWSTR v30; // rax
  const wchar_t *v31; // rdx
  __int64 v32; // rcx
  WCHAR *v33; // r8
  __int64 v34; // r9
  const wchar_t *v35; // rdx
  __int64 v36; // rcx
  WCHAR *v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rdx
  WCHAR *v40; // rax
  __int64 v41; // rcx
  const WCHAR *v42; // r8
  _WORD *v43; // r9
  _WORD *v44; // rcx
  BOOL v45; // eax
  PWSTR v46; // rax
  const WCHAR *v47; // rax
  WCHAR *v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  WCHAR *v51; // rcx
  WCHAR *v52; // rax
  __int64 v53; // r9
  _WORD *v54; // rdx
  _WORD *v55; // rcx
  BOOL v56; // eax
  HUSKEY v57; // rcx
  _BYTE *v58; // rbx
  BOOL v59; // eax
  HUSKEY v60; // rcx
  DWORD v61; // edi
  DWORD v62; // eax
  DWORD v63; // eax
  unsigned int v64; // ebx
  int v65; // ebx
  DWORD v66; // eax
  SHREGDEL_FLAGS v68; // r8d
  SHREGDEL_FLAGS v69; // r8d
  __int64 v70; // rcx
  const wchar_t *v71; // r8
  __int64 v72; // rdx
  WCHAR *v73; // rax
  HUSKEY phNewUSKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v75; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  const unsigned int *v77; // [rsp+50h] [rbp-B0h] BYREF
  HUSKEY hUSKey; // [rsp+58h] [rbp-A8h]
  BOOL v79; // [rsp+60h] [rbp-A0h]
  __int64 v80; // [rsp+64h] [rbp-9Ch]
  const unsigned int *v81; // [rsp+70h] [rbp-90h] BYREF
  HUSKEY v82; // [rsp+78h] [rbp-88h]
  BOOL v83; // [rsp+80h] [rbp-80h]
  __int64 v84; // [rsp+84h] [rbp-7Ch]
  const unsigned int *v85; // [rsp+90h] [rbp-70h] BYREF
  HUSKEY v86; // [rsp+98h] [rbp-68h]
  BOOL v87; // [rsp+A0h] [rbp-60h]
  __int64 v88; // [rsp+A4h] [rbp-5Ch]
  const unsigned int *v89; // [rsp+B0h] [rbp-50h] BYREF
  HUSKEY v90; // [rsp+B8h] [rbp-48h]
  BOOL v91; // [rsp+C0h] [rbp-40h]
  __int64 v92; // [rsp+C4h] [rbp-3Ch]
  WCHAR pwzPath[259]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v94; // [rsp+2D6h] [rbp+1D6h]
  _BYTE v95[8]; // [rsp+2D8h] [rbp+1D8h] BYREF

  v6 = a2;
  if ( !a2 )
    return 0;
  *(_DWORD *)(a1 + 40) = a3;
  *(_DWORD *)(a1 + 56) = a4;
  v8 = CRegZone::s_lockrzcache;
  if ( a4 != 2 )
    v8 = CRegZone::s_rzcache;
  *(_QWORD *)(a1 + 64) = v8;
  if ( !*((_DWORD *)v8 + 15) )
  {
    if ( *((_DWORD *)v8 + 14) )
      v9 = "Local\\ZonesLockedCacheCounterMutex";
    else
      v9 = "Local\\ZonesCacheCounterMutex";
    MutexA = CreateMutexA(0, 0, v9);
    if ( MutexA && GetLastError() != 183 )
      SetKernelHandleToLowIL(MutexA);
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 2));
    v11 = (struct _RTL_CRITICAL_SECTION *)(v8 + 2);
    if ( *((_DWORD *)v8 + 15) )
    {
      LeaveCriticalSection(v11);
      CloseHandle(MutexA);
    }
    else
    {
      v8[1] = (__int64)MutexA;
      *((_DWORD *)v8 + 15) = 1;
      LeaveCriticalSection(v11);
    }
  }
  v91 = a3;
  v90 = 0;
  v89 = &CRegKey::`vftable';
  v12 = 260;
  v92 = 1;
  v85 = &CRegKey::`vftable';
  v13 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Zones\\";
  v86 = 0;
  v14 = -1;
  v87 = a3;
  v88 = 0;
  if ( !a4 )
  {
    v15 = 259;
    v16 = pwzPath;
    v17 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Zones\\";
    v18 = 260;
    do
    {
      if ( !v15 )
        break;
      if ( !*v17 )
        break;
      *v16++ = *v17++;
      --v15;
      --v18;
    }
    while ( v18 );
LABEL_22:
    v21 = v16 - 1;
    if ( v18 )
      v21 = v16;
    goto LABEL_24;
  }
  if ( a4 != 1 )
  {
    if ( a4 != 2 )
      goto LABEL_38;
    v19 = 259;
    v20 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Lockdown_Zones\\";
    v18 = 260;
    v16 = pwzPath;
    do
    {
      if ( !v19 )
        break;
      if ( !*v20 )
        break;
      *v16++ = *v20++;
      --v19;
      --v18;
    }
    while ( v18 );
    goto LABEL_22;
  }
  v70 = 259;
  v71 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\TemplatePolicies\\";
  v72 = 260;
  v73 = pwzPath;
  do
  {
    if ( !v70 )
      break;
    if ( !*v71 )
      break;
    *v73++ = *v71++;
    --v70;
    --v72;
  }
  while ( v72 );
  v21 = v73 - 1;
  if ( v72 )
    v21 = v73;
LABEL_24:
  *v21 = 0;
  v94 = 0;
  v22 = -1;
  do
    ++v22;
  while ( pwzPath[v22] );
  v23 = 260;
  v24 = pwzPath;
  while ( *v24 )
  {
    ++v24;
    if ( !--v23 )
      goto LABEL_38;
  }
  v25 = 259 - v22;
  if ( (unsigned __int64)(259 - v22) <= 0x7FFFFFFE )
  {
    v26 = v6;
    v27 = &v95[-2 * v23];
    do
    {
      if ( !v25 )
        break;
      if ( !*v26 )
        break;
      *v27++ = *v26++;
      --v25;
      --v23;
    }
    while ( v23 );
    v28 = v27 - 1;
    if ( v23 )
      v28 = v27;
    *v28 = 0;
  }
LABEL_38:
  phNewUSKey = 0;
  CRegKey::Close((CRegKey *)&v85);
  if ( !(_DWORD)v88 )
  {
LABEL_39:
    fIgnoreHKCU = v87;
    goto LABEL_40;
  }
  fIgnoreHKCU = v87;
  if ( !v87 )
  {
    if ( !SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
      goto LABEL_41;
    goto LABEL_39;
  }
LABEL_40:
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, fIgnoreHKCU) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_42;
  }
LABEL_41:
  v86 = phNewUSKey;
  v30 = StrDupW(pwzPath);
  *(_QWORD *)(a1 + 16) = v30;
  if ( !v30 )
  {
    v85 = &CRegKey::`vftable';
    if ( v86 )
    {
      SHRegCloseUSKey(v86);
      v86 = 0;
    }
    v89 = &CRegKey::`vftable';
    if ( v90 )
      SHRegCloseUSKey(v90);
    return 0;
  }
LABEL_42:
  switch ( a4 )
  {
    case 1:
      goto LABEL_78;
    case 0:
      v31 = L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Zones\\";
      v32 = 259;
      v33 = pwzPath;
      v34 = 260;
      do
      {
        if ( !v32 )
          break;
        if ( !*v31 )
          break;
        *v33++ = *v31++;
        --v32;
        --v34;
      }
      while ( v34 );
      goto LABEL_58;
    case 2:
      v35 = L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Lockdown_Zones\\";
      v36 = 259;
      v33 = pwzPath;
      v34 = 260;
      do
      {
        if ( !v36 )
          break;
        if ( !*v35 )
          break;
        *v33++ = *v35++;
        --v36;
        --v34;
      }
      while ( v34 );
LABEL_58:
      v37 = v33 - 1;
      if ( v34 )
        v37 = v33;
      *v37 = 0;
      v38 = -1;
      v94 = 0;
      do
        ++v38;
      while ( pwzPath[v38] );
      v39 = 260;
      v40 = pwzPath;
      while ( *v40 )
      {
        ++v40;
        if ( !--v39 )
          goto LABEL_74;
      }
      v41 = 259 - v38;
      if ( (unsigned __int64)(259 - v38) <= 0x7FFFFFFE )
      {
        v42 = v6;
        v43 = &v95[-2 * v39];
        do
        {
          if ( !v41 )
            break;
          if ( !*v42 )
            break;
          *v43++ = *v42++;
          --v41;
          --v39;
        }
        while ( v39 );
        v44 = v43 - 1;
        if ( v39 )
          v44 = v43;
        *v44 = 0;
      }
      break;
  }
LABEL_74:
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v89 + 2))(&v89);
  if ( !(_DWORD)v92 )
    goto LABEL_75;
  v45 = v91;
  if ( v91 )
  {
LABEL_76:
    if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, v45) )
      goto LABEL_78;
    goto LABEL_77;
  }
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
  {
LABEL_75:
    v45 = v91;
    goto LABEL_76;
  }
LABEL_77:
  v90 = phNewUSKey;
  v46 = StrDupW(pwzPath);
  *(_QWORD *)(a1 + 24) = v46;
  if ( !v46 )
  {
LABEL_159:
    v85 = &CRegKey::`vftable';
    CRegKey::Close((CRegKey *)&v85);
    v89 = &CRegKey::`vftable';
    CRegKey::Close((CRegKey *)&v89);
    return 0;
  }
LABEL_78:
  if ( !*(_QWORD *)(a1 + 16) && !*(_QWORD *)(a1 + 24) )
    goto LABEL_159;
  v47 = StrDupW(v6);
  *(_QWORD *)(a1 + 8) = v47;
  if ( !v47 )
    goto LABEL_159;
  v75 = -1;
  if ( (a4 & 0xFFFFFFFD) != 0 )
  {
    if ( a4 != 1 )
    {
LABEL_82:
      v83 = a3;
      v81 = &CRegKey::`vftable';
      v48 = pwzPath;
      v82 = 0;
      v49 = 259;
      v84 = 0;
      v50 = 260;
      do
      {
        if ( !v49 )
          break;
        if ( !*v13 )
          break;
        *v48++ = *v13++;
        --v49;
        --v50;
      }
      while ( v50 );
      v51 = v48 - 1;
      if ( v50 )
        v51 = v48;
      *v51 = 0;
      v94 = 0;
      do
        ++v14;
      while ( pwzPath[v14] );
      v52 = pwzPath;
      while ( *v52 )
      {
        ++v52;
        if ( !--v12 )
          goto LABEL_105;
      }
      v53 = 259 - v14;
      if ( (unsigned __int64)(259 - v14) <= 0x7FFFFFFE )
      {
        v54 = &v95[-2 * v12];
        do
        {
          if ( !v53 )
            break;
          if ( !*v6 )
            break;
          *v54++ = *v6++;
          --v53;
          --v12;
        }
        while ( v12 );
        v55 = v54 - 1;
        if ( v12 )
          v55 = v54;
        *v55 = 0;
      }
LABEL_105:
      phNewUSKey = 0;
      CRegKey::Close((CRegKey *)&v81);
      if ( (_DWORD)v84 )
      {
        v56 = v83;
        if ( v83 )
        {
LABEL_107:
          if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, v56) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            v57 = v82;
LABEL_109:
            LODWORD(phNewUSKey) = 0;
            v58 = (_BYTE *)(a1 + 4);
            pcbData = 4;
            if ( v57 )
            {
              if ( (_DWORD)v84 && !v83 )
              {
                if ( !SHRegQueryUSValueW(v57, L"Flags", (DWORD *)&phNewUSKey, (void *)(a1 + 4), &pcbData, 1, 0, 0) )
                  goto LABEL_112;
                v57 = v82;
              }
              if ( !SHRegQueryUSValueW(v57, L"Flags", (DWORD *)&phNewUSKey, (void *)(a1 + 4), &pcbData, v83, 0, 0) )
              {
LABEL_112:
                if ( *(_DWORD *)a1 != 1
                  || (CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 4u),
                      v77 = &CRegKey::`vftable',
                      v79 = g_bUseHKLMOnly,
                      hUSKey = 0,
                      v80 = 0,
                      (NtCurrentPeb()->BitField & 0x20) != 0) )
                {
LABEL_143:
                  v57 = v82;
                  goto LABEL_133;
                }
                phNewUSKey = 0;
                CRegKey::Close((CRegKey *)&v77);
                if ( (_DWORD)v80 )
                {
                  v59 = v79;
                  if ( v79 )
                  {
LABEL_116:
                    if ( SHRegOpenUSKeyW(
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap\\",
                           0x2001Fu,
                           0,
                           &phNewUSKey,
                           v59) )
                    {
                      goto LABEL_131;
                    }
                    goto LABEL_117;
                  }
                  if ( !SHRegOpenUSKeyW(
                          L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap\\",
                          0x2001Fu,
                          0,
                          &phNewUSKey,
                          1) )
                  {
LABEL_117:
                    v60 = phNewUSKey;
                    hUSKey = phNewUSKey;
                    v61 = 2;
                    if ( (*v58 & 8) != 0 )
                    {
                      LODWORD(phNewUSKey) = *(_DWORD *)a1;
                      v62 = 2;
                      if ( v79 )
                        v62 = 8;
                      SHRegWriteUSValueW(v60, L"ProxyBypass", 4u, &phNewUSKey, 4u, v62);
                    }
                    else
                    {
                      v68 = SHREGDEL_HKCU;
                      if ( v79 )
                        v68 = SHREGDEL_HKLM;
                      SHRegDeleteUSValueW(phNewUSKey, L"ProxyBypass", v68);
                    }
                    if ( (*v58 & 0x10) != 0 )
                    {
                      LODWORD(phNewUSKey) = *(_DWORD *)a1;
                      v63 = 2;
                      if ( v79 )
                        v63 = 8;
                      SHRegWriteUSValueW(hUSKey, L"IntranetName", 4u, &phNewUSKey, 4u, v63);
                    }
                    else
                    {
                      v69 = SHREGDEL_HKCU;
                      if ( v79 )
                        v69 = SHREGDEL_HKLM;
                      SHRegDeleteUSValueW(hUSKey, L"IntranetName", v69);
                    }
                    v64 = *(_DWORD *)v58;
                    LODWORD(phNewUSKey) = (v64 >> 7) & 1;
                    v65 = (v64 >> 8) & 1;
                    v66 = 2;
                    if ( v79 )
                      v66 = 8;
                    SHRegWriteUSValueW(hUSKey, L"UNCAsIntranet", 4u, &phNewUSKey, 4u, v66);
                    if ( v79 )
                      v61 = 8;
                    LODWORD(phNewUSKey) = v65;
                    SHRegWriteUSValueW(hUSKey, L"AutoDetect", 4u, &phNewUSKey, 4u, v61);
                    if ( v65 != g_dwAutoDetectFlag )
                      g_dwAutoDetectFlag = -1;
LABEL_131:
                    v77 = &CRegKey::`vftable';
                    if ( hUSKey )
                    {
                      SHRegCloseUSKey(hUSKey);
                      v57 = v82;
                      goto LABEL_133;
                    }
                    goto LABEL_143;
                  }
                }
                v59 = v79;
                goto LABEL_116;
              }
              v57 = v82;
            }
            *(_DWORD *)v58 = 2;
LABEL_133:
            v81 = &CRegKey::`vftable';
            if ( v57 )
              SHRegCloseUSKey(v57);
            goto LABEL_135;
          }
LABEL_108:
          v57 = phNewUSKey;
          v82 = phNewUSKey;
          goto LABEL_109;
        }
        if ( !SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
          goto LABEL_108;
      }
      v56 = v83;
      goto LABEL_107;
    }
    if ( CRegKey::QueryValue((CRegKey *)&v85, &v75, L"TemplateIndex") )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    else
      *(_DWORD *)a1 = v75;
  }
  else
  {
    *(_DWORD *)a1 = StrToIntW(v47);
    if ( a4 != 1 )
      goto LABEL_82;
  }
  *(_DWORD *)(a1 + 4) = 2;
LABEL_135:
  v85 = &CRegKey::`vftable';
  if ( v86 )
  {
    SHRegCloseUSKey(v86);
    v86 = 0;
  }
  v89 = &CRegKey::`vftable';
  if ( v90 )
    SHRegCloseUSKey(v90);
  return 1;
}

```

## disassembly

```asm
0x18003b2b0  mov     [rsp-8+arg_10], rbx
0x18003b2b5  push    rbp
0x18003b2b6  push    rsi
0x18003b2b7  push    rdi
0x18003b2b8  push    r12
0x18003b2ba  push    r13
0x18003b2bc  push    r14
0x18003b2be  push    r15
0x18003b2c0  lea     rbp, [rsp-1F0h]
0x18003b2c8  sub     rsp, 2F0h
0x18003b2cf  mov     rax, cs:__security_cookie
0x18003b2d6  xor     rax, rsp
0x18003b2d9  mov     [rbp+220h+var_40], rax
0x18003b2e0  mov     r14d, r9d
0x18003b2e3  mov     r15d, r8d
0x18003b2e6  mov     r13, rdx
0x18003b2e9  mov     r12, rcx
0x18003b2ec  test    rdx, rdx
0x18003b2ef  jz      loc_18003BD88
0x18003b2f5  cmp     r9d, 2
0x18003b2f9  mov     [rcx+28h], r8d
0x18003b2fd  mov     [rcx+38h], r9d
0x18003b301  lea     rax, ?s_rzcache@CRegZone@@2VCRegZoneCache@1@A; CRegZone::CRegZoneCache CRegZone::s_rzcache
0x18003b308  lea     rbx, ?s_lockrzcache@CRegZone@@2VCRegZoneCache@1@A; CRegZone::CRegZoneCache CRegZone::s_lockrzcache
0x18003b30f  cmovnz  rbx, rax
0x18003b313  mov     [rcx+40h], rbx
0x18003b317  cmp     dword ptr [rbx+3Ch], 0
0x18003b31b  jnz     short loc_18003B37E
0x18003b31d  xor     edx, edx; bInitialOwner
0x18003b31f  xor     ecx, ecx; lpMutexAttributes
0x18003b321  cmp     [rbx+38h], ecx
0x18003b324  jz      loc_18003B5CA
0x18003b32a  lea     r8, Name; "Local\\ZonesLockedCacheCounterMutex"
0x18003b331  call    cs:__imp_CreateMutexA
0x18003b338  nop     dword ptr [rax+rax+00h]
0x18003b33d  mov     rdi, rax
0x18003b340  test    rax, rax
0x18003b343  jnz     loc_18003B59F
0x18003b349  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003b34d  call    cs:__imp_EnterCriticalSection
0x18003b354  nop     dword ptr [rax+rax+00h]
0x18003b359  cmp     dword ptr [rbx+3Ch], 0
0x18003b35d  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003b361  jnz     loc_18003B5D6
0x18003b367  mov     [rbx+8], rdi
0x18003b36b  mov     dword ptr [rbx+3Ch], 1
0x18003b372  call    cs:__imp_LeaveCriticalSection
0x18003b379  nop     dword ptr [rax+rax+00h]
0x18003b37e  xor     r11d, r11d
0x18003b381  mov     [rbp+220h+var_260], r15d
0x18003b385  mov     [rbp+220h+var_268], r11
0x18003b389  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003b390  mov     [rbp+220h+var_270], rax
0x18003b394  mov     ebx, 104h
0x18003b399  mov     [rbp+220h+var_25C], 1
0x18003b3a1  mov     r10d, 103h
0x18003b3a7  mov     [rbp+220h+var_290], rax
0x18003b3ab  lea     rdi, aSoftwareMicros_69; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003b3b2  mov     [rbp+220h+var_288], r11
0x18003b3b6  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18003b3bd  mov     [rbp+220h+var_280], r15d
0x18003b3c1  mov     [rbp+220h+var_27C], r11
0x18003b3c5  test    r14d, r14d
0x18003b3c8  jnz     short loc_18003B3FB
0x18003b3ca  mov     ecx, r10d
0x18003b3cd  lea     r8, [rbp+220h+pwzPath]
0x18003b3d1  mov     rdx, rdi
0x18003b3d4  mov     r9d, ebx
0x18003b3d7  test    rcx, rcx
0x18003b3da  jz      short loc_18003B443
0x18003b3dc  movzx   eax, word ptr [rdx]
0x18003b3df  test    ax, ax
0x18003b3e2  jz      short loc_18003B443
0x18003b3e4  mov     [r8], ax
0x18003b3e8  add     rdx, 2
0x18003b3ec  add     r8, 2
0x18003b3f0  dec     rcx
0x18003b3f3  sub     r9, 1
0x18003b3f7  jnz     short loc_18003B3D7
0x18003b3f9  jmp     short loc_18003B443
0x18003b3fb  mov     ecx, r14d
0x18003b3fe  sub     ecx, 1
0x18003b401  jz      loc_18003BDE2
0x18003b407  cmp     ecx, 1
0x18003b40a  jnz     loc_18003B4DB
0x18003b410  mov     rcx, r10
0x18003b413  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003b41a  mov     r9, rbx
0x18003b41d  lea     r8, [rbp+220h+pwzPath]
0x18003b421  test    rcx, rcx
0x18003b424  jz      short loc_18003B443
0x18003b426  movzx   eax, word ptr [rdx]
0x18003b429  test    ax, ax
0x18003b42c  jz      short loc_18003B443
0x18003b42e  mov     [r8], ax
0x18003b432  add     rdx, 2
0x18003b436  add     r8, 2
0x18003b43a  dec     rcx
0x18003b43d  sub     r9, 1
0x18003b441  jnz     short loc_18003B421
0x18003b443  test    r9, r9
0x18003b446  lea     rcx, [r8-2]
0x18003b44a  cmovnz  rcx, r8
0x18003b44e  mov     [rcx], r11w
0x18003b452  lea     rax, [rbp+220h+pwzPath]
0x18003b456  mov     [rbp+220h+var_4A], r11w
0x18003b45e  mov     r8, rsi
0x18003b461  inc     r8
0x18003b464  cmp     [rax+r8*2], r11w
0x18003b469  jnz     short loc_18003B461
0x18003b46b  mov     rdx, rbx
0x18003b46e  lea     rax, [rbp+220h+pwzPath]
0x18003b472  cmp     [rax], r11w
0x18003b476  jz      short loc_18003B484
0x18003b478  add     rax, 2
0x18003b47c  sub     rdx, 1
0x18003b480  jnz     short loc_18003B472
0x18003b482  jmp     short loc_18003B4DB
0x18003b484  mov     rcx, r10
0x18003b487  sub     rcx, r8
0x18003b48a  cmp     rcx, 7FFFFFFEh
0x18003b491  ja      short loc_18003B4DB
0x18003b493  lea     rax, [rdx+rdx]
0x18003b497  mov     r8, r13
0x18003b49a  lea     r9, [rbp+220h+var_48]
0x18003b4a1  sub     r9, rax
0x18003b4a4  test    rdx, rdx
0x18003b4a7  jz      short loc_18003B4CC
0x18003b4a9  test    rcx, rcx
0x18003b4ac  jz      short loc_18003B4CC
0x18003b4ae  movzx   eax, word ptr [r8]
0x18003b4b2  test    ax, ax
0x18003b4b5  jz      short loc_18003B4CC
0x18003b4b7  mov     [r9], ax
0x18003b4bb  add     r8, 2
0x18003b4bf  add     r9, 2
0x18003b4c3  dec     rcx
0x18003b4c6  sub     rdx, 1
0x18003b4ca  jnz     short loc_18003B4A9
0x18003b4cc  test    rdx, rdx
0x18003b4cf  lea     rcx, [r9-2]
0x18003b4d3  cmovnz  rcx, r9
0x18003b4d7  mov     [rcx], r11w
0x18003b4db  lea     rcx, [rbp+220h+var_290]; this
0x18003b4df  mov     [rsp+320h+phNewUSKey], r11
0x18003b4e4  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18003b4e9  cmp     dword ptr [rbp+220h+var_27C], 0
0x18003b4ed  jnz     loc_18003B835
0x18003b4f3  mov     eax, [rbp+220h+var_280]
0x18003b4f6  lea     r9, [rsp+320h+phNewUSKey]; phNewUSKey
0x18003b4fb  mov     [rsp+320h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003b4ff  xor     r8d, r8d; hRelativeUSKey
0x18003b502  lea     rcx, [rbp+220h+pwzPath]; pwzPath
0x18003b506  mov     edx, 20019h; samDesired
0x18003b50b  call    cs:__imp_SHRegOpenUSKeyW
0x18003b512  nop     dword ptr [rax+rax+00h]
0x18003b517  test    eax, eax
0x18003b519  jnz     loc_18003BD00
0x18003b51f  mov     rax, [rsp+320h+phNewUSKey]
0x18003b524  lea     rcx, [rbp+220h+pwzPath]; pszSrch
0x18003b528  mov     [rbp+220h+var_288], rax
0x18003b52c  call    cs:__imp_StrDupW
0x18003b533  nop     dword ptr [rax+rax+00h]
0x18003b538  mov     [r12+10h], rax
0x18003b53d  test    rax, rax
0x18003b540  jz      loc_18003BD48
0x18003b546  cmp     r14d, 1
0x18003b54a  jz      loc_18003B74F
0x18003b550  test    r14d, r14d
0x18003b553  jnz     loc_18003B5F6
0x18003b559  mov     r10d, 103h
0x18003b55f  lea     rdx, aSoftwarePolici_4; "Software\\Policies\\Microsoft\\Windows"...
0x18003b566  mov     ecx, r10d
0x18003b569  lea     r8, [rbp+220h+pwzPath]
0x18003b56d  mov     r9, rbx
0x18003b570  test    rcx, rcx
0x18003b573  jz      loc_18003B644
0x18003b579  movzx   eax, word ptr [rdx]
0x18003b57c  test    ax, ax
0x18003b57f  jz      loc_18003B644
0x18003b585  mov     [r8], ax
0x18003b589  add     rdx, 2
0x18003b58d  add     r8, 2
0x18003b591  dec     rcx
0x18003b594  sub     r9, 1
0x18003b598  jnz     short loc_18003B570
0x18003b59a  jmp     loc_18003B644
0x18003b59f  call    cs:__imp_GetLastError
0x18003b5a6  nop     dword ptr [rax+rax+00h]
0x18003b5ab  cmp     eax, 0B7h
0x18003b5b0  jz      loc_18003B349
0x18003b5b6  mov     rcx, rdi
0x18003b5b9  call    cs:__imp_?SetKernelHandleToLowIL@@YAJPEAX@Z; SetKernelHandleToLowIL(void *)
0x18003b5c0  nop     dword ptr [rax+rax+00h]
0x18003b5c5  jmp     loc_18003B349
0x18003b5ca  lea     r8, aLocalZonescach; "Local\\ZonesCacheCounterMutex"
0x18003b5d1  jmp     loc_18003B331
0x18003b5d6  call    cs:__imp_LeaveCriticalSection
0x18003b5dd  nop     dword ptr [rax+rax+00h]
0x18003b5e2  mov     rcx, rdi; hObject
0x18003b5e5  call    cs:__imp_CloseHandle
0x18003b5ec  nop     dword ptr [rax+rax+00h]
0x18003b5f1  jmp     loc_18003B37E
0x18003b5f6  mov     ecx, r14d
0x18003b5f9  sub     ecx, 1
0x18003b5fc  jz      loc_18003BE27
0x18003b602  cmp     ecx, 1
0x18003b605  jnz     loc_18003BE74
0x18003b60b  mov     r10d, 103h
0x18003b611  lea     rdx, aSoftwarePolici_7; "Software\\Policies\\Microsoft\\Windows"...
0x18003b618  mov     ecx, r10d
0x18003b61b  lea     r8, [rbp+220h+pwzPath]
0x18003b61f  mov     r9, rbx
0x18003b622  test    rcx, rcx
0x18003b625  jz      short loc_18003B644
0x18003b627  movzx   eax, word ptr [rdx]
0x18003b62a  test    ax, ax
0x18003b62d  jz      short loc_18003B644
0x18003b62f  mov     [r8], ax
0x18003b633  add     rdx, 2
0x18003b637  add     r8, 2
0x18003b63b  dec     rcx
0x18003b63e  sub     r9, 1
0x18003b642  jnz     short loc_18003B622
0x18003b644  test    r9, r9
0x18003b647  lea     rcx, [r8-2]
0x18003b64b  cmovnz  rcx, r8
0x18003b64f  xor     r11d, r11d
0x18003b652  lea     rax, [rbp+220h+pwzPath]
0x18003b656  mov     [rcx], r11w
0x18003b65a  mov     r8, rsi
0x18003b65d  mov     [rbp+220h+var_4A], r11w
0x18003b665  inc     r8
0x18003b668  cmp     word ptr [rax+r8*2], 0
0x18003b66e  jnz     short loc_18003B665
0x18003b670  mov     rdx, rbx
0x18003b673  lea     rax, [rbp+220h+pwzPath]
0x18003b677  cmp     word ptr [rax], 0
0x18003b67b  jz      short loc_18003B689
0x18003b67d  add     rax, 2
0x18003b681  sub     rdx, 1
0x18003b685  jnz     short loc_18003B677
0x18003b687  jmp     short loc_18003B6E0
0x18003b689  mov     rcx, r10
0x18003b68c  sub     rcx, r8
0x18003b68f  cmp     rcx, 7FFFFFFEh
0x18003b696  ja      short loc_18003B6E0
0x18003b698  lea     rax, [rdx+rdx]
0x18003b69c  mov     r8, r13
0x18003b69f  lea     r9, [rbp+220h+var_48]
0x18003b6a6  sub     r9, rax
0x18003b6a9  test    rdx, rdx
0x18003b6ac  jz      short loc_18003B6D1
0x18003b6ae  test    rcx, rcx
0x18003b6b1  jz      short loc_18003B6D1
0x18003b6b3  movzx   eax, word ptr [r8]
0x18003b6b7  test    ax, ax
0x18003b6ba  jz      short loc_18003B6D1
0x18003b6bc  mov     [r9], ax
0x18003b6c0  add     r8, 2
0x18003b6c4  add     r9, 2
0x18003b6c8  dec     rcx
0x18003b6cb  sub     rdx, 1
0x18003b6cf  jnz     short loc_18003B6AE
0x18003b6d1  test    rdx, rdx
0x18003b6d4  lea     rcx, [r9-2]
0x18003b6d8  cmovnz  rcx, r9
0x18003b6dc  mov     [rcx], r11w
0x18003b6e0  mov     rax, [rbp+220h+var_270]
0x18003b6e4  lea     rcx, [rbp+220h+var_270]
0x18003b6e8  mov     [rsp+320h+phNewUSKey], r11
0x18003b6ed  mov     rax, [rax+10h]
0x18003b6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6f6  cmp     dword ptr [rbp+220h+var_25C], 0
0x18003b6fa  jnz     loc_18003BBF4
0x18003b700  mov     eax, [rbp+220h+var_260]
0x18003b703  lea     r9, [rsp+320h+phNewUSKey]; phNewUSKey
0x18003b708  mov     [rsp+320h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003b70c  xor     r8d, r8d; hRelativeUSKey
0x18003b70f  lea     rcx, [rbp+220h+pwzPath]; pwzPath
0x18003b713  mov     edx, 20019h; samDesired
0x18003b718  call    cs:__imp_SHRegOpenUSKeyW
0x18003b71f  nop     dword ptr [rax+rax+00h]
0x18003b724  test    eax, eax
0x18003b726  jnz     short loc_18003B74F
0x18003b728  mov     rax, [rsp+320h+phNewUSKey]
0x18003b72d  lea     rcx, [rbp+220h+pwzPath]; pszSrch
0x18003b731  mov     [rbp+220h+var_268], rax
0x18003b735  call    cs:__imp_StrDupW
0x18003b73c  nop     dword ptr [rax+rax+00h]
0x18003b741  mov     [r12+18h], rax
0x18003b746  test    rax, rax
0x18003b749  jz      loc_18003BD25
0x18003b74f  cmp     qword ptr [r12+10h], 0
0x18003b755  jz      loc_18003BD19
0x18003b75b  mov     rcx, r13; pszSrch
0x18003b75e  call    cs:__imp_StrDupW
0x18003b765  nop     dword ptr [rax+rax+00h]
0x18003b76a  mov     [r12+8], rax
0x18003b76f  test    rax, rax
  ... truncated ...
```
