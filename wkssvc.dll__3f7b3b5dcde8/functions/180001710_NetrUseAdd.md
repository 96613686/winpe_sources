# NetrUseAdd

- ea: `0x180001710`
- end: `0x180002494`
- name: `NetrUseAdd`
- size: `3460`
- prototype: `DWORD __fastcall(__int64, int, __int64 *, _DWORD *)`
- caller_count: `0`
- callee_count: `28`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000161c`
- `0x180001710`
- `0x1800024f0`
- `0x180002a60`
- `0x180004a40`
- `0x180005a60`
- `0x180007728`
- `0x1800084d8`
- `0x180008650`
- `0x180008950`
- `0x1800089d0`
- `0x180008a4c`
- `0x180008c90`
- `0x180009f80`
- `0x18000af60`
- `0x18000b7f4`
- `0x18000b8e0`
- `0x18000c888`
- `0x18000d8ac`
- `0x18001e420`
- `0x18001ed46`
- `0x18002972c`
- `0x18002e944`
- `0x18002ea70`
- `0x18002eda0`
- `0x18002ef7c`
- `0x18002f1b0`
- `0x18002f320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180001b8b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180001b8b`
- `ntdll!RtlRunEncodeUnicodeString` at `0x180001dc1`
- `ntdll!RtlRunEncodeUnicodeString` at `0x180001dc1`
- `ntdll!RtlRunDecodeUnicodeString` at `0x180001cfa`
- `ntdll!RtlRunDecodeUnicodeString` at `0x180001cfa`
- `ntdll!NtQueryInformationFile` at `0x180002230`
- `ntdll!NtQueryInformationFile` at `0x180002230`
- `ntdll!DbgPrint` at `0x1800017ad`
- `ntdll!DbgPrint` at `0x180001862`
- `ntdll!DbgPrint` at `0x18000191b`
- `ntdll!DbgPrint` at `0x180001948`
- `ntdll!DbgPrint` at `0x180001961`
- `ntdll!DbgPrint` at `0x18000197a`
- `ntdll!DbgPrint` at `0x1800019cd`
- `ntdll!DbgPrint` at `0x1800017ad`
- `ntdll!DbgPrint` at `0x180001862`
- `ntdll!DbgPrint` at `0x18000191b`
- `ntdll!DbgPrint` at `0x180001948`
- `ntdll!DbgPrint` at `0x180001961`
- `ntdll!DbgPrint` at `0x18000197a`
- `ntdll!DbgPrint` at `0x1800019cd`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180001d35`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180001dfc`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180001d35`
- `ntdll!RtlMapSecurityErrorToNtStatus` at `0x180001dfc`
- `ntdll!RtlNtStatusToDosError` at `0x180001e08`
- `ntdll!RtlNtStatusToDosError` at `0x180001e08`
- `ntdll!RtlAcquireResourceExclusive` at `0x180001eeb`
- `ntdll!RtlAcquireResourceExclusive` at `0x180001eeb`
- `ntdll!NtClose` at `0x180001fcc`
- `ntdll!NtClose` at `0x18000216b`
- `ntdll!NtClose` at `0x180001fcc`
- `ntdll!NtClose` at `0x18000216b`
- `ntdll!RtlReleaseResource` at `0x180001f93`
- `ntdll!RtlReleaseResource` at `0x18000202c`
- `ntdll!RtlReleaseResource` at `0x180002072`
- `ntdll!RtlReleaseResource` at `0x180001f93`
- `ntdll!RtlReleaseResource` at `0x18000202c`
- `ntdll!RtlReleaseResource` at `0x180002072`
- `ntdll!RtlInitUnicodeString` at `0x1800017d7`
- `ntdll!RtlInitUnicodeString` at `0x180001cee`
- `ntdll!RtlInitUnicodeString` at `0x1800020ae`
- `ntdll!RtlInitUnicodeString` at `0x1800017d7`
- `ntdll!RtlInitUnicodeString` at `0x180001cee`
- `ntdll!RtlInitUnicodeString` at `0x1800020ae`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000199a`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000199a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001a65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001cc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001da8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001dcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001eb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000243d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001cc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001da8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001dcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001eb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000243d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d6e`
- `SspiCli!SspiFreeAuthIdentity` at `0x180001df4`
- `SspiCli!SspiFreeAuthIdentity` at `0x180001df4`
- `SspiCli!SspiLocalFree` at `0x180001d96`
- `SspiCli!SspiLocalFree` at `0x180001d96`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x180001d2d`
- `SspiCli!SspiEncodeStringsAsAuthIdentity` at `0x180001d2d`
- `SspiCli!SspiMarshalAuthIdentity` at `0x180001de8`
- `SspiCli!SspiMarshalAuthIdentity` at `0x180001de8`
- `netutils!NetpwPathCanonicalize` at `0x180001b74`
- `netutils!NetpwPathCanonicalize` at `0x180001b74`
- `netutils!NetpwNameCanonicalize` at `0x180001c1e`
- `netutils!NetpwNameCanonicalize` at `0x180001c72`
- `netutils!NetpwNameCanonicalize` at `0x180001c1e`
- `netutils!NetpwNameCanonicalize` at `0x180001c72`
- `netutils!NetpwPathType` at `0x180001b3d`
- `netutils!NetpwPathType` at `0x180001b3d`

## string_xrefs

- `0x180001757`: `bCreateGlobalMapping:%u\n`
- `0x18000195a`: `Specified SMB compression switch: %d\n`

## pseudocode

```c
DWORD __fastcall NetrUseAdd(__int64 a1, int a2, __int64 *a3, _DWORD *a4)
{
  unsigned int v4; // edi
  int v5; // r13d
  DWORD result; // eax
  __int64 v9; // r14
  unsigned __int8 v10; // al
  ULONG v11; // esi
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  ULONG v15; // edx
  _WORD *v16; // rax
  _WORD *v17; // rax
  const WCHAR *v18; // r12
  const WCHAR *v19; // r15
  unsigned int v20; // ecx
  unsigned int v21; // eax
  char *v22; // rax
  wchar_t *v23; // rsi
  const WCHAR *v24; // rbx
  _WORD *v25; // rax
  const WCHAR *v26; // rax
  __int64 v27; // rcx
  _WORD *v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rbx
  _WORD *v31; // rax
  _WORD *v32; // rax
  _WORD *v33; // rax
  const WCHAR *v34; // rdi
  _WORD *v35; // rcx
  const WCHAR *v36; // rdx
  __int64 v37; // rax
  int v38; // r15d
  ULONG v39; // eax
  NTSTATUS v40; // eax
  ULONG v41; // eax
  int LogonId; // edi
  HLOCAL v43; // r12
  __int64 v44; // rax
  _BYTE *v45; // rcx
  ULONG v46; // edi
  int v47; // eax
  int v48; // r12d
  const WCHAR *v49; // rcx
  char v50; // r13
  __int64 v51; // rcx
  char v52; // r14
  PCWSTR v53; // rbx
  const WCHAR *v54; // rcx
  struct _UNICODE_STRING *v55; // rdi
  ULONG v56; // r13d
  DWORD v57; // eax
  int v58; // r14d
  int v59; // r13d
  __int64 v60; // rdx
  int v61; // eax
  int v62; // [rsp+30h] [rbp-E0h]
  UCHAR Hash[8]; // [rsp+90h] [rbp-80h] BYREF
  PCWSTR SourceString; // [rsp+98h] [rbp-78h]
  unsigned __int8 v65; // [rsp+A0h] [rbp-70h]
  char v66; // [rsp+A1h] [rbp-6Fh]
  char v67; // [rsp+A2h] [rbp-6Eh]
  HLOCAL v68; // [rsp+A8h] [rbp-68h] BYREF
  ULONG v69; // [rsp+B0h] [rbp-60h]
  unsigned int AuthIdentityLength; // [rsp+B4h] [rbp-5Ch] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp-58h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+C0h] [rbp-50h] BYREF
  int v73; // [rsp+C8h] [rbp-48h]
  struct _LUID SourceLuid; // [rsp+D0h] [rbp-40h] BYREF
  PVOID DataBuffer; // [rsp+D8h] [rbp-38h] BYREF
  int v76; // [rsp+E0h] [rbp-30h]
  unsigned int v77; // [rsp+E4h] [rbp-2Ch] BYREF
  struct _UNICODE_STRING v78; // [rsp+E8h] [rbp-28h] BYREF
  int v79; // [rsp+F8h] [rbp-18h] BYREF
  int v80; // [rsp+FCh] [rbp-14h] BYREF
  __int64 v81; // [rsp+100h] [rbp-10h] BYREF
  __int64 v82; // [rsp+108h] [rbp-8h] BYREF
  __int64 v83; // [rsp+110h] [rbp+0h] BYREF
  PCWSTR pszDomainName[2]; // [rsp+118h] [rbp+8h] BYREF
  HLOCAL v85; // [rsp+128h] [rbp+18h]
  struct _LUID v86; // [rsp+130h] [rbp+20h] BYREF
  HANDLE hObject; // [rsp+138h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+140h] [rbp+30h] BYREF
  HLOCAL v89[2]; // [rsp+148h] [rbp+38h] BYREF
  __int64 v90; // [rsp+158h] [rbp+48h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+160h] [rbp+50h] BYREF
  _BYTE FileInformation[128]; // [rsp+170h] [rbp+60h] BYREF
  __int128 v93; // [rsp+1F0h] [rbp+E0h] BYREF
  __int128 v94; // [rsp+200h] [rbp+F0h]
  __int128 v95; // [rsp+210h] [rbp+100h]
  __int64 v96; // [rsp+220h] [rbp+110h]
  __int64 *v97; // [rsp+228h] [rbp+118h]
  __int64 v98; // [rsp+230h] [rbp+120h]
  int v99; // [rsp+238h] [rbp+128h]
  __int64 *v100; // [rsp+240h] [rbp+130h]
  __int64 v101; // [rsp+248h] [rbp+138h]
  int v102; // [rsp+250h] [rbp+140h] BYREF
  _BYTE *v103; // [rsp+258h] [rbp+148h]
  __int64 v104; // [rsp+260h] [rbp+150h]
  int v105; // [rsp+268h] [rbp+158h]
  __int64 v106; // [rsp+270h] [rbp+160h]
  __int64 v107; // [rsp+278h] [rbp+168h]
  int v108; // [rsp+280h] [rbp+170h]
  __int64 v109; // [rsp+288h] [rbp+178h]
  __int64 v110; // [rsp+290h] [rbp+180h]
  int v111; // [rsp+298h] [rbp+188h]
  __int64 v112; // [rsp+2A0h] [rbp+190h]
  __int64 v113; // [rsp+2A8h] [rbp+198h]

  v4 = (unsigned __int16)a2;
  *(_QWORD *)&v78.Length = a4;
  SourceLuid = 0;
  v5 = a2 & 0x10000;
  v86 = 0;
  v80 = 0;
  DataBuffer = 0;
  AuthIdentityLength = 0;
  DestinationString = 0;
  Handle = 0;
  hObject = (HANDLE)-1LL;
  *(_OWORD *)v89 = 0;
  hMem = 0;
  v73 = a2 & 0x10000;
  v65 = (a2 & 0x10000) != 0;
  v90 = 0;
  v83 = 0;
  v82 = 0;
  v81 = 0;
  v77 = 0;
  v68 = 0;
  v79 = 0;
  DbgPrint("bCreateGlobalMapping:%u\n", v65);
  if ( !v4 )
    return 124;
  RtlInitUnicodeString(&DestinationString, 0);
  v9 = *a3;
  if ( !*a3 )
  {
    if ( a4 )
      *a4 = -1;
    return 87;
  }
  v10 = 0;
  v66 = 0;
  if ( v4 < 3 )
  {
    v69 = 0;
    DbgPrint("bPersistMapping:%u\n", 0);
    v85 = 0;
    v76 = 0;
  }
  else
  {
    v11 = *(_DWORD *)(v9 + 56);
    v69 = v11;
    if ( v4 < 4 )
    {
      v69 = v11;
    }
    else
    {
      DataBuffer = *(PVOID *)(v9 + 72);
      AuthIdentityLength = *(_DWORD *)(v9 + 64);
      v10 = 0;
    }
    if ( (v11 & 0x20) != 0 )
    {
      if ( !v5 )
      {
        if ( a4 )
          *a4 = 7;
        return 87;
      }
      v10 = 1;
      v66 = 1;
    }
    v85 = 0;
    v76 = 0;
    DbgPrint("bPersistMapping:%u\n", v10);
    if ( v4 >= 5 )
    {
      v12 = *a3;
      if ( v12 )
      {
        v13 = *(unsigned int *)(v12 + 96);
        v14 = *(_QWORD *)(v12 + 104);
        *((_QWORD *)&v93 + 1) = &v90;
        *(_QWORD *)&v95 = &v83;
        v97 = &v82;
        v100 = &v81;
        LODWORD(v93) = 1130784068;
        *(_QWORD *)&v94 = 124;
        DWORD2(v94) = 1348563540;
        *((_QWORD *)&v95 + 1) = 24;
        LODWORD(v96) = 1349349187;
        v98 = 16;
        v99 = 1315925058;
        v101 = 16;
        if ( !(unsigned __int8)LmPopulateAndValidateUseOptionInfo(v14, v13, &v93) )
        {
          DbgPrint("Invalid value specified for a UseOption\n");
          if ( a4 )
            *a4 = 10;
          return 87;
        }
        if ( v83 )
          DbgPrint("Specified Transport : %u\n", *(_DWORD *)v83);
        if ( v82 )
          DbgPrint("Specified SMB compression switch: %d\n", *(unsigned __int8 *)v82);
        if ( v81 )
          DbgPrint("Block NTLM: %d\n", *(unsigned __int8 *)v81);
        v15 = *(_DWORD *)(v12 + 80);
        if ( v15 )
        {
          if ( !v5 || (v85 = *(HLOCAL *)(v12 + 88), !RtlValidRelativeSecurityDescriptor(v85, v15, 0)) )
          {
            if ( a4 )
              *a4 = 9;
            return 87;
          }
          v76 = *(_DWORD *)(v12 + 80);
        }
      }
    }
  }
  v16 = *(_WORD **)(v9 + 8);
  if ( !v16 || !*v16 )
  {
    if ( a4 )
      *a4 = 2;
    return 87;
  }
  if ( v5 )
  {
    result = WsImpersonateAndCheckPrivilege(28);
    if ( result )
    {
      if ( a4 )
        *a4 = 7;
      return result;
    }
  }
  v17 = *(_WORD **)v9;
  v18 = 0;
  pszDomainName[0] = 0;
  v19 = 0;
  v20 = 522;
  if ( v17 && *v17 )
    v20 = 684;
  if ( v4 >= 2 )
  {
    v21 = v20 + 514;
    if ( !*(_QWORD *)(v9 + 40) )
      v21 = v20;
    v20 = v21;
    if ( *(_QWORD *)(v9 + 48) )
      v20 = v21 + 512;
  }
  v22 = (char *)LocalAlloc(0x40u, v20);
  v23 = (wchar_t *)v22;
  if ( v22 )
  {
    v24 = (const WCHAR *)(v22 + 522);
    v25 = *(_WORD **)v9;
    SourceString = v24;
    if ( v25 && *v25 )
    {
      v26 = v24 + 81;
    }
    else
    {
      v26 = v24;
      v24 = 0;
      SourceString = 0;
    }
    if ( v4 >= 2 )
    {
      v27 = *(_QWORD *)(v9 + 40);
      v19 = v26 + 257;
      v18 = v26;
      if ( !v27 )
        v19 = v26;
      pszDomainName[0] = v19;
      if ( !v27 )
        v18 = 0;
      if ( !*(_QWORD *)(v9 + 48) )
      {
        v19 = 0;
        pszDomainName[0] = 0;
      }
    }
  }
  else
  {
    v24 = 0;
    SourceString = 0;
    result = GetLastError();
    if ( result )
      return result;
  }
  v28 = *(_WORD **)v9;
  if ( *(_QWORD *)v9 && *v28 && (unsigned int)WsUseCheckLocal(v28, v24, &v80) )
  {
    LocalFree(v23);
    if ( *(_QWORD *)&v78.Length )
      **(_DWORD **)&v78.Length = 1;
    return 87;
  }
  v29 = *(_QWORD *)(v9 + 8);
  LODWORD(ppAuthIdentity) = 0;
  if ( (unsigned int)NetpwPathType(v29, &ppAuthIdentity, 0)
    || (_DWORD)ppAuthIdentity != 4096
    || (unsigned int)NetpwPathCanonicalize(v29, v23, 520, 0, &ppAuthIdentity, 0)
    || !wcschr(v23 + 2, 0x5Cu) )
  {
    LocalFree(v23);
    if ( *(_QWORD *)&v78.Length )
      **(_DWORD **)&v78.Length = 2;
    return 87;
  }
  v30 = -1;
  do
    ++v30;
  while ( v23[v30] );
  if ( v4 < 2
    || (v31 = *(_WORD **)(v9 + 16)) == 0
    || *v31
    || (v32 = *(_WORD **)(v9 + 40)) == 0
    || *v32
    || (v33 = *(_WORD **)(v9 + 48)) == 0
    || *v33 )
  {
    if ( v18 && (unsigned int)NetpwNameCanonicalize(*(_QWORD *)(v9 + 40), v18, 514, 1, 0) )
    {
      LocalFree(v23);
      if ( *(_QWORD *)&v78.Length )
        **(_DWORD **)&v78.Length = 5;
      return 87;
    }
    if ( v19 )
    {
      v35 = *(_WORD **)(v9 + 48);
      if ( *v35 )
      {
        if ( (unsigned int)NetpwNameCanonicalize(v35, v19, 512, 4, 0) )
        {
          LocalFree(v23);
          if ( *(_QWORD *)&v78.Length )
            **(_DWORD **)&v78.Length = 6;
          return 87;
        }
      }
    }
    v36 = *(const WCHAR **)(v9 + 16);
    v34 = 0;
    if ( v36 )
    {
      v37 = -1;
      do
        ++v37;
      while ( v36[v37] );
      if ( (unsigned int)v37 > 0x7FFD )
      {
        LocalFree(v23);
        if ( *(_QWORD *)&v78.Length )
          **(_DWORD **)&v78.Length = 3;
        return 87;
      }
      v34 = *(const WCHAR **)(v9 + 16);
      RtlInitUnicodeString(&DestinationString, v36);
      RtlRunDecodeUnicodeString(0x56u, &DestinationString);
    }
  }
  else
  {
    v34 = &base;
    *v18 = 0;
    *v19 = 0;
  }
  v38 = 0;
  if ( v18 && !DataBuffer )
  {
    ppAuthIdentity = 0;
    v39 = SspiEncodeStringsAsAuthIdentity(v18, pszDomainName[0], v34, &ppAuthIdentity);
    v40 = RtlMapSecurityErrorToNtStatus(v39);
    if ( v40 < 0 )
    {
      v41 = WsMapStatus((unsigned int)v40);
LABEL_100:
      LogonId = v41;
      **(_DWORD **)&v78.Length = 5;
LABEL_101:
      v43 = v68;
      goto LABEL_102;
    }
    v46 = SspiMarshalAuthIdentity(ppAuthIdentity, &AuthIdentityLength, (char **)&DataBuffer);
    SspiFreeAuthIdentity(ppAuthIdentity);
    v47 = RtlMapSecurityErrorToNtStatus(v46);
    if ( v47 < 0 )
    {
      v41 = RtlNtStatusToDosError(v47);
      goto LABEL_100;
    }
    v38 = 1;
  }
  v48 = 0;
  if ( !DataBuffer )
    v48 = 4;
  LogonId = WsCheckLocalAndDeviceType(SourceString, *(unsigned int *)(v9 + 28), *(_QWORD *)&v78.Length);
  if ( LogonId )
    goto LABEL_101;
  if ( v5 )
  {
    SourceLuid = (struct _LUID)-1LL;
  }
  else
  {
    LogonId = WsImpersonateAndGetLogonId(&SourceLuid);
    if ( LogonId )
    {
LABEL_129:
      v43 = v68;
      goto LABEL_130;
    }
  }
  v86 = SourceLuid;
  LogonId = WsCreateTreeConnectName((int)v23, v30, (int)SourceString, v65, (PUNICODE_STRING)v89);
  if ( LogonId )
    goto LABEL_101;
  v49 = SourceString;
  if ( SourceString )
  {
    if ( (unsigned int)WsRedirectionPaused() )
    {
      LogonId = 72;
      goto LABEL_129;
    }
    v49 = SourceString;
  }
  v50 = 0;
  Hash[0] = 0;
  v67 = 0;
  if ( v49 )
  {
    LODWORD(ppAuthIdentity) = 0;
    if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
    {
      LogonId = 2140;
      goto LABEL_129;
    }
    if ( (unsigned int)WsGetUserEntry(&Use, &SourceLuid, &ppAuthIdentity, 0, 0) )
      v51 = 0;
    else
      v51 = *(_QWORD *)(Use + 24LL * (unsigned int)ppAuthIdentity);
    if ( v73 )
    {
      if ( v51 )
      {
        pszDomainName[0] = 0;
        *(_QWORD *)&v78.Length = 0;
        WsFindLocal(v51, SourceString, pszDomainName, &v78);
        if ( pszDomainName[0] )
        {
          LogonId = 85;
          goto LABEL_144;
        }
      }
    }
    else
    {
      LogonId = WsCreateSymbolicLink(SourceString, *(unsigned int *)(v9 + 28), v89[1], v51, &hMem, &hObject);
      if ( !LogonId )
      {
        Hash[0] = 1;
        RtlReleaseResource(&Resource);
LABEL_164:
        v49 = SourceString;
        goto LABEL_165;
      }
      if ( *(_QWORD *)&v78.Length && LogonId == 87 )
      {
        **(_DWORD **)&v78.Length = 1;
LABEL_144:
        RtlReleaseResource(&Resource);
        goto LABEL_145;
      }
    }
    RtlReleaseResource(&Resource);
    if ( LogonId )
    {
LABEL_145:
      v43 = v68;
      v52 = 0;
LABEL_146:
      v53 = SourceString;
      goto LABEL_147;
    }
    goto LABEL_164;
  }
LABEL_165:
  v55 = &v78;
  v56 = v69 & 0x158;
  if ( !v73 )
    v55 = 0;
  pszDomainName[0] = &v55->Length;
  while ( 1 )
  {
    v78 = 0;
    RtlInitUnicodeString(&v78, v49);
    v57 = WsOpenCreateConnectionSpecifyImpersonation(
            (struct _UNICODE_STRING *)v89,
            (const void **)v55,
            (__int64)DataBuffer,
            AuthIdentityLength,
            0,
            (char *)v85,
            v90,
            v83,
            v82,
            v81,
            v69,
            3u,
            *(_DWORD *)(v9 + 28),
            v65,
            1,
            1,
            &Handle);
    LogonId = v57;
    if ( v57 )
    {
      v53 = SourceString;
      v50 = 0;
      v43 = v68;
      v52 = 0;
      if ( v57 == 2250 )
        LogonId = 55;
      goto LABEL_147;
    }
    if ( (v69 & 4) == 0 )
      break;
    if ( (unsigned int)WsDeleteConnectionEx(&SourceLuid, Handle) )
      NtClose(Handle);
    v49 = SourceString;
    v69 &= ~4u;
    v55 = (struct _UNICODE_STRING *)pszDomainName[0];
    Handle = 0;
  }
  LogonId = WsCheckEstablishedDeviceType(Handle, *(unsigned int *)(v9 + 28));
  if ( LogonId )
    goto LABEL_190;
  v58 = v73;
  if ( !v73 )
  {
    LogonId = WsCreateLinkedConnection(Handle);
    if ( LogonId )
      goto LABEL_190;
  }
  v59 = v48 | v56;
  if ( !v58 || !v66 )
  {
    v43 = v68;
    v52 = 0;
    goto LABEL_192;
  }
  v96 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  memset_0(FileInformation, 0, 0x74u);
  *(_OWORD *)pszDomainName = 0;
  if ( NtQueryInformationFile(
         Handle,
         (PIO_STATUS_BLOCK)pszDomainName,
         FileInformation,
         0x74u,
         FileRemoteProtocolInformation) < 0
    || SLODWORD(pszDomainName[0]) < 0 )
  {
    LogonId = 2140;
    goto LABEL_190;
  }
  if ( !AuthIdentityLength )
  {
    v52 = 0;
    goto LABEL_184;
  }
  LogonId = WsSaveNetUseCredential(v23, DataBuffer, AuthIdentityLength, &v77);
  if ( LogonId )
  {
LABEL_190:
    v50 = 0;
    goto LABEL_145;
  }
  v52 = 1;
LABEL_184:
  v102 = 1130784068;
  v103 = FileInformation;
  v106 = v83;
  v109 = v82;
  v112 = v81;
  v104 = 124;
  v105 = 1348563540;
  v107 = 24;
  v108 = 1349349187;
  v110 = 16;
  v111 = 1315925058;
  v113 = 16;
  v61 = LmCreatePersistentUseOptionsForConnection(&v102, v60, &v68, &v79);
  v43 = v68;
  LogonId = v61;
  if ( v61 )
    goto LABEL_188;
  *(_QWORD *)&v93 = SourceString;
  LODWORD(v95) = v79;
  *((_QWORD *)&v95 + 1) = v85;
  LODWORD(v96) = v76;
  *((_QWORD *)&v93 + 1) = v23;
  *(_QWORD *)&v94 = __PAIR64__(v77, v59);
  *((_QWORD *)&v94 + 1) = v68;
  LogonId = WsImpersonateClient2(0, 0);
  if ( LogonId || (LogonId = WsSaveGlobalMappingToRegistry(&v93), WsRevertToSelf2(0, 0), LogonId) )
  {
LABEL_188:
    v50 = 0;
    goto LABEL_146;
  }
  v67 = 1;
LABEL_192:
  v62 = v30;
  v53 = SourceString;
  LogonId = WsAddUse(&SourceLuid, &v86, v80, (__int64)v23, v62, (__int64)v89, v59, v83, v82, v81);
  if ( LogonId )
  {
    v50 = v67;
LABEL_147:
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( (unsigned int)WsDeleteConnectionEx(&SourceLuid, Handle) )
        NtClose(Handle);
      Handle = 0;
    }
    if ( Hash[0] )
      WsDeleteSymbolicLink(v53, v89[1], hMem, hObject);
    if ( v50 )
    {
      v54 = v23;
      if ( v53 )
        v54 = v53;
      WsDeleteGlobalMappingFromRegistry(v54);
    }
    if ( v52 )
      WsDeleteNetUseCredential(v23, v77);
    goto LABEL_130;
  }
  if ( v73 )
    WsSendWnfNotification();
LABEL_130:
  if ( v89[1] )
    LocalFree(v89[1]);
LABEL_102:
  LocalFree(v23);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v38 )
  {
    v44 = AuthIdentityLength;
    v45 = DataBuffer;
    if ( AuthIdentityLength )
    {
      do
      {
        *v45++ = 0;
        --v44;
      }
      while ( v44 );
      v45 = DataBuffer;
    }
    SspiLocalFree(v45);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( DestinationString.Length )
  {
    Hash[0] = 86;
    RtlRunEncodeUnicodeString(Hash, &DestinationString);
  }
  if ( v43 )
    LocalFree(v43);
  return LogonId;
}

```

## disassembly

```asm
0x180001710  push    rbp
0x180001712  push    rbx
0x180001713  push    rsi
0x180001714  push    rdi
0x180001715  push    r13
0x180001717  push    r15
0x180001719  lea     rbp, [rsp-1B8h]
0x180001721  sub     rsp, 2C8h
0x180001728  mov     rax, cs:__security_cookie
0x18000172f  xor     rax, rsp
0x180001732  mov     [rbp+1E0h+var_40], rax
0x180001739  xor     esi, esi
0x18000173b  movzx   edi, dx
0x18000173e  mov     r13d, edx
0x180001741  mov     qword ptr [rbp+1E0h+var_208.Length], r9
0x180001745  xorps   xmm0, xmm0
0x180001748  mov     qword ptr [rbp+1E0h+SourceLuid.LowPart], rsi
0x18000174c  and     r13d, 10000h
0x180001753  mov     qword ptr [rbp+1E0h+var_1C0.LowPart], rsi
0x180001757  lea     rcx, Format; "bCreateGlobalMapping:%u\n"
0x18000175e  mov     [rbp+1E0h+var_1F4], esi
0x180001761  setnz   al
0x180001764  mov     [rbp+1E0h+DataBuffer], rsi
0x180001768  movzx   edx, al
0x18000176b  mov     r15, r9
0x18000176e  mov     rbx, r8
0x180001771  mov     [rbp+1E0h+AuthIdentityLength], esi
0x180001774  movups  xmmword ptr [rbp+1E0h+DestinationString.Length], xmm0
0x180001778  mov     [rbp+1E0h+Handle], rsi
0x18000177c  mov     [rbp+1E0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180001784  movups  xmmword ptr [rbp+1E0h+var_1A8], xmm0
0x180001788  mov     [rbp+1E0h+hMem], rsi
0x18000178c  mov     [rbp+1E0h+var_228], r13d
0x180001790  mov     [rbp+1E0h+var_250], al
0x180001793  mov     [rbp+1E0h+var_198], rsi
0x180001797  mov     [rbp+1E0h+var_1E0], rsi
0x18000179b  mov     [rbp+1E0h+var_1E8], rsi
0x18000179f  mov     [rbp+1E0h+var_1F0], rsi
0x1800017a3  mov     [rbp+1E0h+var_20C], esi
0x1800017a6  mov     [rbp+1E0h+var_248], rsi
0x1800017aa  mov     [rbp+1E0h+var_1F8], esi
0x1800017ad  call    cs:__imp_DbgPrint
0x1800017b3  test    edi, edi
0x1800017b5  jnz     short loc_1800017C1
0x1800017b7  mov     eax, 7Ch ; '|'
0x1800017bc  jmp     loc_180002475
0x1800017c1  mov     [rsp+2F0h+arg_0], r12
0x1800017c9  lea     rcx, [rbp+1E0h+DestinationString]; DestinationString
0x1800017cd  xor     edx, edx; SourceString
0x1800017cf  mov     [rsp+2F0h+var_30], r14
0x1800017d7  call    cs:__imp_RtlInitUnicodeString
0x1800017dd  mov     r14, [rbx]
0x1800017e0  test    r14, r14
0x1800017e3  jnz     short loc_1800017FA
0x1800017e5  test    r15, r15
0x1800017e8  jz      loc_180002460
0x1800017ee  mov     dword ptr [r15], 0FFFFFFFFh
0x1800017f5  jmp     loc_180002460
0x1800017fa  xor     al, al
0x1800017fc  mov     [rbp+1E0h+var_24F], al
0x1800017ff  cmp     edi, 3
0x180001802  jb      loc_1800019C1
0x180001808  mov     esi, [r14+38h]
0x18000180c  mov     [rbp+1E0h+var_240], esi
0x18000180f  cmp     edi, 4
0x180001812  jb      short loc_180001827
0x180001814  mov     rax, [r14+48h]
0x180001818  mov     [rbp+1E0h+DataBuffer], rax
0x18000181c  mov     eax, [r14+40h]
0x180001820  mov     [rbp+1E0h+AuthIdentityLength], eax
0x180001823  xor     al, al
0x180001825  jmp     short loc_18000182A
0x180001827  mov     [rbp+1E0h+var_240], esi
0x18000182a  test    sil, 20h
0x18000182e  jz      short loc_18000184F
0x180001830  test    r13d, r13d
0x180001833  jnz     short loc_18000184A
0x180001835  test    r15, r15
0x180001838  jz      loc_180002460
0x18000183e  mov     dword ptr [r15], 7
0x180001845  jmp     loc_180002460
0x18000184a  mov     al, 1
0x18000184c  mov     [rbp+1E0h+var_24F], al
0x18000184f  xor     esi, esi
0x180001851  movzx   edx, al
0x180001854  lea     rcx, aBpersistmappin; "bPersistMapping:%u\n"
0x18000185b  mov     [rbp+1E0h+var_1C8], rsi
0x18000185f  mov     [rbp+1E0h+var_210], esi
0x180001862  call    cs:__imp_DbgPrint
0x180001868  cmp     edi, 5
0x18000186b  jb      loc_1800019DA
0x180001871  mov     rbx, [rbx]
0x180001874  test    rbx, rbx
0x180001877  jz      loc_1800019DA
0x18000187d  mov     edx, [rbx+60h]
0x180001880  lea     rax, [rbp+1E0h+var_198]
0x180001884  mov     rcx, [rbx+68h]
0x180001888  lea     r8, [rbp+1E0h+var_100]
0x18000188f  mov     qword ptr [rbp+1E0h+var_100+8], rax
0x180001896  lea     rax, [rbp+1E0h+var_1E0]
0x18000189a  mov     qword ptr [rbp+1E0h+var_E0], rax
0x1800018a1  lea     rax, [rbp+1E0h+var_1E8]
0x1800018a5  mov     [rbp+1E0h+var_C8], rax
0x1800018ac  lea     rax, [rbp+1E0h+var_1F0]
0x1800018b0  mov     [rbp+1E0h+var_B0], rax
0x1800018b7  mov     dword ptr [rbp+1E0h+var_100], 43666544h
0x1800018c1  mov     qword ptr [rbp+1E0h+var_F0], 7Ch ; '|'
0x1800018cc  mov     dword ptr [rbp+1E0h+var_F0+8], 50617254h
0x1800018d6  mov     qword ptr [rbp+1E0h+var_E0+8], 18h
0x1800018e1  mov     dword ptr [rbp+1E0h+var_D0], 506D6F43h
0x1800018eb  mov     [rbp+1E0h+var_C0], 10h
0x1800018f6  mov     [rbp+1E0h+var_B8], 4E6F6C42h
0x180001900  mov     [rbp+1E0h+var_A8], 10h
0x18000190b  call    LmPopulateAndValidateUseOptionInfo
0x180001910  test    al, al
0x180001912  jnz     short loc_180001936
0x180001914  lea     rcx, aInvalidValueSp; "Invalid value specified for a UseOption"...
0x18000191b  call    cs:__imp_DbgPrint
0x180001921  test    r15, r15
0x180001924  jz      loc_180002460
0x18000192a  mov     dword ptr [r15], 0Ah
0x180001931  jmp     loc_180002460
0x180001936  mov     rdx, [rbp+1E0h+var_1E0]
0x18000193a  test    rdx, rdx
0x18000193d  jz      short loc_18000194E
0x18000193f  mov     edx, [rdx]
0x180001941  lea     rcx, aSpecifiedTrans; "Specified Transport : %u\n"
0x180001948  call    cs:__imp_DbgPrint
0x18000194e  mov     rax, [rbp+1E0h+var_1E8]
0x180001952  test    rax, rax
0x180001955  jz      short loc_180001967
0x180001957  movzx   edx, byte ptr [rax]
0x18000195a  lea     rcx, aSpecifiedSmbCo; "Specified SMB compression switch: %d\n"
0x180001961  call    cs:__imp_DbgPrint
0x180001967  mov     rax, [rbp+1E0h+var_1F0]
0x18000196b  test    rax, rax
0x18000196e  jz      short loc_180001980
0x180001970  movzx   edx, byte ptr [rax]
0x180001973  lea     rcx, aBlockNtlmD; "Block NTLM: %d\n"
0x18000197a  call    cs:__imp_DbgPrint
0x180001980  mov     edx, [rbx+50h]; SecurityDescriptorLength
0x180001983  test    edx, edx
0x180001985  jz      short loc_1800019DA
0x180001987  test    r13d, r13d
0x18000198a  jz      short loc_1800019A4
0x18000198c  mov     rax, [rbx+58h]
0x180001990  xor     r8d, r8d; RequiredInformation
0x180001993  mov     rcx, rax; SecurityDescriptorInput
0x180001996  mov     [rbp+1E0h+var_1C8], rax
0x18000199a  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800019a0  test    al, al
0x1800019a2  jnz     short loc_1800019B9
0x1800019a4  test    r15, r15
0x1800019a7  jz      loc_180002460
0x1800019ad  mov     dword ptr [r15], 9
0x1800019b4  jmp     loc_180002460
0x1800019b9  mov     eax, [rbx+50h]
0x1800019bc  mov     [rbp+1E0h+var_210], eax
0x1800019bf  jmp     short loc_1800019DA
0x1800019c1  xor     edx, edx
0x1800019c3  mov     [rbp+1E0h+var_240], esi
0x1800019c6  lea     rcx, aBpersistmappin; "bPersistMapping:%u\n"
0x1800019cd  call    cs:__imp_DbgPrint
0x1800019d3  mov     [rbp+1E0h+var_1C8], rsi
0x1800019d7  mov     [rbp+1E0h+var_210], esi
0x1800019da  mov     rax, [r14+8]
0x1800019de  test    rax, rax
0x1800019e1  jz      loc_180002454
0x1800019e7  cmp     word ptr [rax], 0
0x1800019eb  jz      loc_180002454
0x1800019f1  test    r13d, r13d
0x1800019f4  jz      short loc_180001A19
0x1800019f6  mov     ecx, 1Ch
0x1800019fb  call    WsImpersonateAndCheckPrivilege
0x180001a00  test    eax, eax
0x180001a02  jz      short loc_180001A19
0x180001a04  test    r15, r15
0x180001a07  jz      loc_180002465
0x180001a0d  mov     dword ptr [r15], 7
0x180001a14  jmp     loc_180002465
0x180001a19  mov     rax, [r14]
0x180001a1c  mov     r12, rsi
0x180001a1f  mov     [rbp+1E0h+pszDomainName], rsi
0x180001a23  mov     r15, rsi
0x180001a26  mov     ecx, 20Ah
0x180001a2b  test    rax, rax
0x180001a2e  jz      short loc_180001A3C
0x180001a30  cmp     word ptr [rax], 0
0x180001a34  mov     edx, 2ACh
0x180001a39  cmovnz  ecx, edx
0x180001a3c  cmp     edi, 2
0x180001a3f  jb      short loc_180001A5E
0x180001a41  cmp     qword ptr [r14+28h], 0
0x180001a46  lea     eax, [rcx+202h]
0x180001a4c  cmovz   eax, ecx
0x180001a4f  cmp     qword ptr [r14+30h], 0
0x180001a54  mov     ecx, eax
0x180001a56  jz      short loc_180001A5E
0x180001a58  add     ecx, 200h
0x180001a5e  mov     edx, ecx; uBytes
0x180001a60  mov     ecx, 40h ; '@'; uFlags
0x180001a65  call    cs:__imp_LocalAlloc
0x180001a6b  mov     rsi, rax
0x180001a6e  test    rax, rax
0x180001a71  jnz     short loc_180001A89
0x180001a73  xor     ebx, ebx
0x180001a75  mov     [rbp+1E0h+SourceString], rbx
0x180001a79  call    cs:__imp_GetLastError
0x180001a7f  test    eax, eax
0x180001a81  jnz     loc_180002465
0x180001a87  jmp     short loc_180001AE8
0x180001a89  lea     rbx, [rax+20Ah]
0x180001a90  mov     rax, [r14]
0x180001a93  mov     [rbp+1E0h+SourceString], rbx
0x180001a97  test    rax, rax
0x180001a9a  jz      short loc_180001AAB
0x180001a9c  cmp     word ptr [rax], 0
0x180001aa0  jz      short loc_180001AAB
0x180001aa2  lea     rax, [rbx+0A2h]
0x180001aa9  jmp     short loc_180001AB4
0x180001aab  mov     rax, rbx
0x180001aae  xor     ebx, ebx
0x180001ab0  mov     [rbp+1E0h+SourceString], rbx
0x180001ab4  cmp     edi, 2
0x180001ab7  jb      short loc_180001AE8
0x180001ab9  mov     rcx, [r14+28h]
0x180001abd  lea     r15, [rax+202h]
0x180001ac4  test    rcx, rcx
0x180001ac7  mov     r12, rax
0x180001aca  cmovz   r15, rax
0x180001ace  xor     eax, eax
0x180001ad0  test    rcx, rcx
0x180001ad3  mov     [rbp+1E0h+pszDomainName], r15
0x180001ad7  cmovz   r12, rax
0x180001adb  cmp     [r14+30h], rax
0x180001adf  jnz     short loc_180001AE8
0x180001ae1  xor     r15d, r15d
0x180001ae4  mov     [rbp+1E0h+pszDomainName], r15
0x180001ae8  mov     rcx, [r14]
0x180001aeb  test    rcx, rcx
0x180001aee  jz      short loc_180001B28
0x180001af0  cmp     word ptr [rcx], 0
0x180001af4  jz      short loc_180001B28
0x180001af6  lea     r8, [rbp+1E0h+var_1F4]
0x180001afa  mov     rdx, rbx
0x180001afd  call    WsUseCheckLocal
0x180001b02  test    eax, eax
0x180001b04  jz      short loc_180001B28
0x180001b06  mov     rcx, rsi; hMem
0x180001b09  call    cs:__imp_LocalFree
0x180001b0f  mov     r8, qword ptr [rbp+1E0h+var_208.Length]
0x180001b13  test    r8, r8
0x180001b16  jz      loc_180002460
0x180001b1c  mov     dword ptr [r8], 1
0x180001b23  jmp     loc_180002460
0x180001b28  mov     rbx, [r14+8]
0x180001b2c  lea     rdx, [rbp+1E0h+ppAuthIdentity]
0x180001b30  mov     rcx, rbx
0x180001b33  mov     dword ptr [rbp+1E0h+ppAuthIdentity], 0
0x180001b3a  xor     r8d, r8d
0x180001b3d  call    cs:__imp_NetpwPathType
0x180001b43  test    eax, eax
0x180001b45  jnz     loc_18000243A
0x180001b4b  cmp     dword ptr [rbp+1E0h+ppAuthIdentity], 1000h
0x180001b52  jnz     loc_18000243A
0x180001b58  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x180001b5c  xor     r9d, r9d
0x180001b5f  lea     rax, [rbp+1E0h+ppAuthIdentity]
0x180001b63  mov     r8d, 208h
0x180001b69  mov     rdx, rsi
0x180001b6c  mov     qword ptr [rsp+2F0h+FileInformationClass], rax
0x180001b71  mov     rcx, rbx
0x180001b74  call    cs:__imp_NetpwPathCanonicalize
0x180001b7a  test    eax, eax
0x180001b7c  jnz     loc_18000243A
0x180001b82  mov     edx, 5Ch ; '\'; Ch
0x180001b87  lea     rcx, [rsi+4]; Str
0x180001b8b  call    cs:__imp_wcschr
0x180001b91  test    rax, rax
0x180001b94  jz      loc_18000243A
0x180001b9a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001ba1  inc     rbx
0x180001ba4  cmp     word ptr [rsi+rbx*2], 0
0x180001ba9  jnz     short loc_180001BA1
0x180001bab  mov     eax, 4
0x180001bb0  cmp     edi, 2
0x180001bb3  jb      short loc_180001BFE
0x180001bb5  mov     rax, [r14+10h]
0x180001bb9  test    rax, rax
0x180001bbc  jz      short loc_180001BF9
0x180001bbe  cmp     word ptr [rax], 0
0x180001bc2  jnz     short loc_180001BF9
0x180001bc4  mov     rax, [r14+28h]
0x180001bc8  test    rax, rax
0x180001bcb  jz      short loc_180001BF9
0x180001bcd  cmp     word ptr [rax], 0
0x180001bd1  jnz     short loc_180001BF9
0x180001bd3  mov     rax, [r14+30h]
0x180001bd7  test    rax, rax
0x180001bda  jz      short loc_180001BF9
  ... truncated ...
```
