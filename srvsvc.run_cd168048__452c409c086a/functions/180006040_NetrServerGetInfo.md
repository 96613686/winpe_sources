# NetrServerGetInfo

- ea: `0x180006040`
- end: `0x180006b2d`
- name: `NetrServerGetInfo`
- size: `2797`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006040`
- `0x180006b40`
- `0x18001deb0`
- `0x180020dc0`
- `0x180021fb0`
- `0x180028c24`
- `0x1800435ec`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800063f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006432`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800065d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006612`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006653`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800068a5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800069fd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006a36`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006a6a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006afb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800063f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006432`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800065d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006612`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006653`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800068a5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800069fd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006a36`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006a6a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006afb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000634c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006531`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ac5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000634c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006531`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ac5`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x18000621a`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x18000621a`
- `ntdll!RtlAcquireResourceShared` at `0x1800061ad`
- `ntdll!RtlAcquireResourceShared` at `0x1800061ad`
- `ntdll!RtlReleaseResource` at `0x180006443`
- `ntdll!RtlReleaseResource` at `0x1800064be`
- `ntdll!RtlReleaseResource` at `0x18000668f`
- `ntdll!RtlReleaseResource` at `0x1800067c3`
- `ntdll!RtlReleaseResource` at `0x180006443`
- `ntdll!RtlReleaseResource` at `0x1800064be`
- `ntdll!RtlReleaseResource` at `0x18000668f`
- `ntdll!RtlReleaseResource` at `0x1800067c3`
- `ntdll!RtlInitUnicodeString` at `0x1800060f9`
- `ntdll!RtlInitUnicodeString` at `0x180006106`
- `ntdll!RtlInitUnicodeString` at `0x180006118`
- `ntdll!RtlInitUnicodeString` at `0x1800061d2`
- `ntdll!RtlInitUnicodeString` at `0x1800060f9`
- `ntdll!RtlInitUnicodeString` at `0x180006106`
- `ntdll!RtlInitUnicodeString` at `0x180006118`
- `ntdll!RtlInitUnicodeString` at `0x1800061d2`
- `ntdll!RtlAdjustPrivilege` at `0x18000612d`
- `ntdll!RtlAdjustPrivilege` at `0x18000612d`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180006183`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180006183`
- `RPCRT4!RpcImpersonateClient` at `0x180006135`
- `RPCRT4!RpcImpersonateClient` at `0x180006135`
- `RPCRT4!RpcRevertToSelf` at `0x18000618b`
- `RPCRT4!RpcRevertToSelf` at `0x18000618b`

## pseudocode

```c
__int64 __fastcall NetrServerGetInfo(WCHAR *SourceString, int a2, _QWORD *a3)
{
  ACCESS_MASK DesiredAccess; // edi
  const WCHAR *v7; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // r12
  struct _GENERIC_MAPPING *GenericMapping; // r15
  RPC_STATUS v10; // eax
  int v11; // r8d
  NTSTATUS v12; // ebx
  WCHAR *v13; // rdi
  unsigned int v14; // esi
  size_t v15; // r8
  int *v16; // rdx
  _BYTE *v17; // rcx
  char *v18; // rbx
  char *j; // r15
  wchar_t *v20; // rsi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  _OWORD *v25; // rax
  _OWORD *v26; // r14
  int v27; // eax
  __int64 v28; // rax
  bool v29; // zf
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // eax
  __int64 *k; // rcx
  int v34; // r14d
  int v35; // r14d
  __int64 v36; // rbx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rdx
  _OWORD *v40; // rax
  _OWORD *v41; // r13
  int v42; // eax
  __int64 *m; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rcx
  _QWORD *v51; // rcx
  __int64 v52; // rcx
  PCWSTR i; // rax
  __int64 v54; // rdx
  int v55; // r14d
  int v56; // r14d
  __int64 v57; // rbx
  __int64 v58; // rax
  _OWORD *v59; // rax
  _OWORD *v60; // rdi
  _OWORD *v61; // rax
  __int64 v62; // rbx
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rax
  _OWORD *v66; // rax
  _OWORD *v67; // r13
  int v68; // eax
  __int64 *n; // rcx
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rcx
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rbx
  __int64 v78; // rax
  _QWORD *v79; // rax
  _QWORD *v80; // rsi
  unsigned __int8 OldValue; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 GenerateOnClose[3]; // [rsp+61h] [rbp-9Fh] BYREF
  int AccessStatus; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v86; // [rsp+80h] [rbp-80h]
  UNICODE_STRING SourceStringa; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE Buf1[272]; // [rsp+C0h] [rbp-40h] BYREF

  v86 = a3;
  SourceStringa = 0;
  if ( SourceString )
  {
    v52 = 1024;
    for ( i = SourceString; *i; ++i )
    {
      if ( !--v52 )
        return 87;
    }
  }
  switch ( a2 )
  {
    case 101:
    case 100:
      DesiredAccess = 1;
      break;
    case 102:
    case 103:
    case 502:
      DesiredAccess = 2;
      break;
    case 503:
      DesiredAccess = 4;
      break;
    default:
      return 124;
  }
  v7 = SsConfigInfoSecurityObject;
  SecurityDescriptor = ::SecurityDescriptor;
  GenericMapping = ::GenericMapping;
  OldValue = 0;
  DestinationString = 0;
  GrantedAccess = 0;
  ObjectTypeName = 0;
  GenerateOnClose[0] = 0;
  ObjectName = 0;
  AccessStatus = 0;
  RtlInitUnicodeString(&DestinationString, L"Server");
  RtlInitUnicodeString(&ObjectTypeName, v7);
  RtlInitUnicodeString(&ObjectName, L"SRV Server Info");
  RtlAdjustPrivilege(0x15u, 1u, 0, &OldValue);
  v10 = RpcImpersonateClient(0);
  if ( !v10 )
  {
    v12 = NtAccessCheckAndAuditAlarm(
            &DestinationString,
            0,
            &ObjectTypeName,
            &ObjectName,
            SecurityDescriptor,
            DesiredAccess,
            GenericMapping,
            0,
            &GrantedAccess,
            &AccessStatus,
            GenerateOnClose);
    RpcRevertToSelf();
    if ( v12 >= 0 && !AccessStatus )
    {
      RtlAcquireResourceShared(&Resource, 1u);
      v13 = &WideCharStr;
      if ( SourceString )
        v13 = SourceString;
      if ( *v13 == 92 && v13[1] == 92 )
        v13 += 2;
      RtlInitUnicodeString(&SourceStringa, v13);
      ObjectName = 0;
      if ( SourceStringa.Length )
      {
        if ( SourceStringa.Length <= 0x206u )
        {
          ObjectName.Buffer = (PWSTR)Buf1;
          ObjectName.MaximumLength = 260;
          RtlUpcaseUnicodeStringToOemString((POEM_STRING)&ObjectName, &SourceStringa, 0);
          v14 = 16;
          if ( ObjectName.Length >= 0x10u )
          {
LABEL_15:
            v18 = (char *)hMem;
            for ( j = (char *)hMem; j; j = *(char **)j )
            {
              if ( *((_DWORD *)j + 67) == v14 && !memcmp_0(Buf1, j + 8, v14) )
              {
LABEL_32:
                v20 = (wchar_t *)*((_QWORD *)j + 34);
                goto LABEL_33;
              }
            }
            v20 = &pszDest;
            for ( j = v18; j; j = *(char **)j )
            {
              if ( (j[284] & 1) != 0 )
                goto LABEL_32;
            }
LABEL_33:
            if ( a2 == 101 )
            {
              v22 = -1;
              v23 = -1;
              do
                ++v23;
              while ( word_18005D560[v23] );
              v24 = -1;
              do
                ++v24;
              while ( v13[v24] );
              v25 = LocalAlloc(0x40u, (unsigned int)(2 * (v24 + v23) + 44));
              v26 = v25;
              if ( v25 )
              {
                *v25 = SsData;
                v25[1] = xmmword_18005CBD0;
                *((_QWORD *)v25 + 4) = xmmword_18005CBE0;
                if ( j )
                {
                  v32 = *((_DWORD *)j + 70);
                  *((_DWORD *)v26 + 6) = v32;
                  for ( k = (__int64 *)*((_QWORD *)j + 37); k; k = (__int64 *)*k )
                  {
                    v32 |= *((_DWORD *)k + 4);
                    *((_DWORD *)v26 + 6) = v32;
                  }
                }
                else
                {
                  v27 = dword_18005D028 | 0x1002;
                  if ( byte_18005D030 )
                    v27 = dword_18005D028 | 0x801002;
                  if ( HIDWORD(xmmword_18005CC38) )
                    v27 |= 0x20u;
                  if ( dword_18005CCF8 == 3 )
                    v27 |= 0x8000u;
                  if ( dword_18005D048 )
                    v27 |= 0x200u;
                  *((_DWORD *)v26 + 6) = v27;
                }
                v28 = -1;
                *((_QWORD *)v26 + 1) = (char *)v26 + 40;
                do
                  v29 = v13[++v28] == 0;
                while ( !v29 );
                _o_wcscpy_s((char *)v26 + 40, (unsigned int)(v28 + 1));
                v30 = -1;
                do
                  v29 = v13[++v30] == 0;
                while ( !v29 );
                v31 = *((_QWORD *)v26 + 1) + 2LL * (unsigned int)(v30 + 1);
                *((_QWORD *)v26 + 4) = v31;
                do
                  v29 = word_18005D560[++v22] == 0;
                while ( !v29 );
                _o_wcscpy_s(v31, (unsigned int)(v22 + 1));
                *a3 = v26;
                goto LABEL_56;
              }
              goto LABEL_60;
            }
            v34 = a2 - 100;
            if ( v34 )
            {
              v35 = v34 - 2;
              if ( !v35 )
              {
                v36 = -1;
                v37 = -1;
                do
                  ++v37;
                while ( word_18005D560[v37] );
                v38 = -1;
                do
                  ++v38;
                while ( word_18005D762[v38] );
                v39 = -1;
                do
                  ++v39;
                while ( v13[v39] );
                v40 = LocalAlloc(0x40u, (unsigned int)(2 * (v37 + v39 + v38) + 78));
                v41 = v40;
                if ( v40 )
                {
                  *v40 = SsData;
                  v40[1] = xmmword_18005CBD0;
                  v40[2] = xmmword_18005CBE0;
                  v40[3] = xmmword_18005CBF0;
                  *((_QWORD *)v40 + 8) = qword_18005CC00;
                  if ( j )
                  {
                    v42 = *((_DWORD *)j + 70);
                    *((_DWORD *)v41 + 6) = v42;
                    for ( m = (__int64 *)*((_QWORD *)j + 37); m; m = (__int64 *)*m )
                    {
                      v42 |= *((_DWORD *)m + 4);
                      *((_DWORD *)v41 + 6) = v42;
                    }
                  }
                  else
                  {
                    *((_DWORD *)v40 + 6) = SsGetServerType();
                  }
                  v44 = -1;
                  *((_QWORD *)v41 + 1) = (char *)v41 + 72;
                  do
                    v29 = v13[++v44] == 0;
                  while ( !v29 );
                  _o_wcscpy_s((char *)v41 + 72, (unsigned int)(v44 + 1));
                  v45 = -1;
                  do
                    v29 = v13[++v45] == 0;
                  while ( !v29 );
                  v46 = *((_QWORD *)v41 + 1) + 2LL * (unsigned int)(v45 + 1);
                  v47 = -1;
                  *((_QWORD *)v41 + 4) = v46;
                  do
                    v29 = word_18005D560[++v47] == 0;
                  while ( !v29 );
                  _o_wcscpy_s(v46, (unsigned int)(v47 + 1));
                  v48 = *((_QWORD *)v41 + 4);
                  v49 = -1;
                  do
                    ++v49;
                  while ( *(_WORD *)(v48 + 2 * v49) );
                  v50 = v48 + 2LL * (unsigned int)(v49 + 1);
                  *((_QWORD *)v41 + 8) = v50;
                  do
                    v29 = word_18005D762[++v36] == 0;
                  while ( !v29 );
                  _o_wcscpy_s(v50, (unsigned int)(v36 + 1));
                  *v86 = v41;
                  goto LABEL_56;
                }
                goto LABEL_60;
              }
              v55 = v35 - 1;
              if ( v55 )
              {
                v56 = v55 - 399;
                if ( v56 )
                {
                  if ( v56 != 1 )
                  {
                    RtlReleaseResource(&Resource);
                    return 124;
                  }
                  v57 = -1;
                  v58 = -1;
                  do
                    v29 = v20[++v58] == 0;
                  while ( !v29 );
                  v59 = LocalAlloc(0x40u, (unsigned int)(2 * v58 + 178));
                  v60 = v59;
                  if ( v59 )
                  {
                    *v59 = xmmword_18005CC08;
                    v59[1] = xmmword_18005CC18;
                    v59[2] = xmmword_18005CC28;
                    v59[3] = xmmword_18005CC38;
                    v59[4] = xmmword_18005CC48;
                    v59[5] = xmmword_18005CC58;
                    v59[6] = xmmword_18005CC68;
                    v59[7] = xmmword_18005CC78;
                    v59[8] = xmmword_18005CC88;
                    v59[9] = xmmword_18005CC98;
                    v59[10] = xmmword_18005CCA8;
                    *((_QWORD *)v59 + 9) = v59 + 11;
                    do
                      v29 = v20[++v57] == 0;
                    while ( !v29 );
                    _o_wcscpy_s(v59 + 11, (unsigned int)(v57 + 1));
                    *a3 = v60;
                    goto LABEL_56;
                  }
                }
                else
                {
                  v61 = LocalAlloc(0x40u, 0x48u);
                  *a3 = v61;
                  if ( v61 )
                  {
                    *v61 = xmmword_18005CC08;
                    v61[1] = xmmword_18005CC18;
                    v61[2] = xmmword_18005CC28;
                    v61[3] = xmmword_18005CC38;
                    *((_QWORD *)v61 + 8) = xmmword_18005CC48;
LABEL_56:
                    RtlReleaseResource(&Resource);
                    return 0;
                  }
                }
              }
              else
              {
                v62 = -1;
                v63 = -1;
                do
                  ++v63;
                while ( word_18005D560[v63] );
                v64 = -1;
                do
                  ++v64;
                while ( word_18005D762[v64] );
                v65 = -1;
                do
                  ++v65;
                while ( v13[v65] );
                v66 = LocalAlloc(0x40u, (unsigned int)(2 * (v63 + v64 + v65) + 86));
                v67 = v66;
                if ( v66 )
                {
                  *v66 = SsData;
                  v66[1] = xmmword_18005CBD0;
                  v66[2] = xmmword_18005CBE0;
                  v66[3] = xmmword_18005CBF0;
                  *((_QWORD *)v66 + 8) = qword_18005CC00;
                  if ( j )
                  {
                    v68 = *((_DWORD *)j + 70);
                    *((_DWORD *)v67 + 6) = v68;
                    for ( n = (__int64 *)*((_QWORD *)j + 37); n; n = (__int64 *)*n )
                    {
                      v68 |= *((_DWORD *)n + 4);
                      *((_DWORD *)v67 + 6) = v68;
                    }
                  }
                  else
                  {
                    *((_DWORD *)v66 + 6) = SsGetServerType();
                  }
                  v70 = -1;
                  *((_QWORD *)v67 + 1) = v67 + 5;
                  do
                    v29 = v13[++v70] == 0;
                  while ( !v29 );
                  _o_wcscpy_s(v67 + 5, (unsigned int)(v70 + 1));
                  v71 = -1;
                  do
                    v29 = v13[++v71] == 0;
                  while ( !v29 );
                  v72 = *((_QWORD *)v67 + 1) + 2LL * (unsigned int)(v71 + 1);
                  v73 = -1;
                  *((_QWORD *)v67 + 4) = v72;
                  do
                    v29 = word_18005D560[++v73] == 0;
                  while ( !v29 );
                  _o_wcscpy_s(v72, (unsigned int)(v73 + 1));
                  v74 = *((_QWORD *)v67 + 4);
                  v75 = -1;
                  do
                    ++v75;
                  while ( *(_WORD *)(v74 + 2 * v75) );
                  v76 = v74 + 2LL * (unsigned int)(v75 + 1);
                  *((_QWORD *)v67 + 8) = v76;
                  do
                    v29 = word_18005D762[++v62] == 0;
                  while ( !v29 );
                  _o_wcscpy_s(v76, (unsigned int)(v62 + 1));
                  *((_DWORD *)v67 + 18) = 0;
                  if ( dword_18005E4B0 )
                  {
                    *((_DWORD *)v67 + 18) = 1;
                    if ( !(unsigned int)HpQueryHashGenerationService() )
                      *((_DWORD *)v67 + 18) |= 2u;
                  }
                  *v86 = v67;
                  goto LABEL_56;
                }
              }
            }
            else
            {
              v77 = -1;
              v78 = -1;
              do
                v29 = v13[++v78] == 0;
              while ( !v29 );
              v79 = LocalAlloc(0x40u, (unsigned int)(2 * v78 + 18));
              v80 = v79;
              if ( v79 )
              {
                *(_OWORD *)v79 = SsData;
                v79[1] = v79 + 2;
                do
                  v29 = v13[++v77] == 0;
                while ( !v29 );
                _o_wcscpy_s(v79 + 2, (unsigned int)(v77 + 1));
                *a3 = v80;
                goto LABEL_56;
              }
            }
LABEL_60:
            RtlReleaseResource(&Resource);
            return 8;
          }
          v15 = 16LL - ObjectName.Length;
          v16 = (int *)"               ";
          v17 = &Buf1[ObjectName.Length];
LABEL_14:
          memcpy_0(v17, v16, v15);
          goto LABEL_15;
        }
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_87;
        }
        v54 = 50;
      }
      else
      {
        v14 = Size;
        if ( (unsigned int)Size <= 0x103 )
        {
          v15 = (unsigned int)Size;
          v16 = &dword_18005CF14;
          v17 = Buf1;
          goto LABEL_14;
        }
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
LABEL_87:
          RtlReleaseResource(&Resource);
          return 87;
        }
        v54 = 49;
      }
      WPP_SF_(v51[2], v54, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids);
      goto LABEL_87;
    }
    LOBYTE(v10) = 5;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_SLl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      v11,
      (_DWORD)SsConfigInfoSecurityObject,
      DesiredAccess,
      v10);
  }
  return 5;
}

```

## disassembly

```asm
0x180006040  push    rbp
0x180006042  push    rsi
0x180006043  push    r13
0x180006045  push    r14
0x180006047  lea     rbp, [rsp-0F8h]
0x18000604f  sub     rsp, 1F8h
0x180006056  mov     rax, cs:__security_cookie
0x18000605d  xor     rax, rsp
0x180006060  mov     [rbp+110h+var_40], rax
0x180006067  mov     [rbp+110h+var_190], r8
0x18000606b  xorps   xmm0, xmm0
0x18000606e  mov     r13, r8
0x180006071  mov     r14d, edx
0x180006074  mov     rsi, rcx
0x180006077  movups  xmmword ptr [rbp+110h+SourceString.Length], xmm0
0x18000607b  test    rcx, rcx
0x18000607e  jnz     loc_1800066B5
0x180006084  mov     [rsp+210h+var_20], rdi
0x18000608c  cmp     r14d, 65h ; 'e'
0x180006090  jnz     loc_180006280
0x180006096  mov     edi, 1
0x18000609b  xor     eax, eax
0x18000609d  mov     [rsp+210h+arg_8], rbx
0x1800060a5  mov     rbx, cs:SsConfigInfoSecurityObject
0x1800060ac  lea     rdx, SourceName; "Server"
0x1800060b3  xorps   xmm0, xmm0
0x1800060b6  mov     [rsp+210h+var_28], r12
0x1800060be  mov     r12, cs:SecurityDescriptor
0x1800060c5  lea     rcx, [rbp+110h+DestinationString]; DestinationString
0x1800060c9  xorps   xmm1, xmm1
0x1800060cc  mov     [rsp+210h+var_30], r15
0x1800060d4  mov     r15, cs:GenericMapping
0x1800060db  mov     [rsp+210h+OldValue], 0
0x1800060e0  movups  xmmword ptr [rbp+110h+DestinationString.Length], xmm0
0x1800060e4  mov     [rsp+210h+var_1A8], eax
0x1800060e8  movups  xmmword ptr [rbp+110h+ObjectTypeName.Length], xmm1
0x1800060ec  mov     [rsp+210h+var_1AF], al
0x1800060f0  movups  xmmword ptr [rsp+210h+ObjectName.Length], xmm0
0x1800060f5  mov     [rsp+210h+var_1AC], eax
0x1800060f9  call    cs:__imp_RtlInitUnicodeString
0x1800060ff  mov     rdx, rbx; SourceString
0x180006102  lea     rcx, [rbp+110h+ObjectTypeName]; DestinationString
0x180006106  call    cs:__imp_RtlInitUnicodeString
0x18000610c  lea     rdx, aSrvServerInfo; "SRV Server Info"
0x180006113  lea     rcx, [rsp+210h+ObjectName]; DestinationString
0x180006118  call    cs:__imp_RtlInitUnicodeString
0x18000611e  lea     r9, [rsp+210h+OldValue]; OldValue
0x180006123  xor     r8d, r8d; ForThread
0x180006126  mov     dl, 1; NewValue
0x180006128  mov     ecx, 15h; Privilege
0x18000612d  call    cs:__imp_RtlAdjustPrivilege
0x180006133  xor     ecx, ecx; BindingHandle
0x180006135  call    cs:__imp_RpcImpersonateClient
0x18000613b  test    eax, eax
0x18000613d  jnz     loc_1800062B0
0x180006143  lea     rax, [rsp+210h+var_1AF]
0x180006148  xor     edx, edx; HandleId
0x18000614a  mov     [rsp+210h+GenerateOnClose], rax; GenerateOnClose
0x18000614f  lea     r9, [rsp+210h+ObjectName]; ObjectName
0x180006154  lea     rax, [rsp+210h+var_1AC]
0x180006159  mov     [rsp+210h+AccessStatus], rax; AccessStatus
0x18000615e  lea     r8, [rbp+110h+ObjectTypeName]; ObjectTypeName
0x180006162  lea     rax, [rsp+210h+var_1A8]
0x180006167  mov     [rsp+210h+GrantedAccess], rax; GrantedAccess
0x18000616c  lea     rcx, [rbp+110h+DestinationString]; SubsystemName
0x180006170  mov     [rsp+210h+ObjectCreation], 0; ObjectCreation
0x180006175  mov     [rsp+210h+GenericMapping], r15; GenericMapping
0x18000617a  mov     [rsp+210h+DesiredAccess], edi; DesiredAccess
0x18000617e  mov     [rsp+210h+SecurityDescriptor], r12; SecurityDescriptor
0x180006183  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180006189  mov     ebx, eax
0x18000618b  call    cs:__imp_RpcRevertToSelf
0x180006191  test    ebx, ebx
0x180006193  js      loc_1800062AB
0x180006199  cmp     [rsp+210h+var_1AC], 0
0x18000619e  jnz     loc_1800062AB
0x1800061a4  mov     dl, 1; Wait
0x1800061a6  lea     rcx, Resource; Resource
0x1800061ad  call    cs:__imp_RtlAcquireResourceShared
0x1800061b3  test    rsi, rsi
0x1800061b6  lea     rdi, WideCharStr
0x1800061bd  cmovnz  rdi, rsi
0x1800061c1  cmp     word ptr [rdi], 5Ch ; '\'
0x1800061c5  jz      loc_18000671E
0x1800061cb  mov     rdx, rdi; SourceString
0x1800061ce  lea     rcx, [rbp+110h+SourceString]; DestinationString
0x1800061d2  call    cs:__imp_RtlInitUnicodeString
0x1800061d8  movzx   eax, [rbp+110h+SourceString.Length]
0x1800061dc  xorps   xmm0, xmm0
0x1800061df  movups  xmmword ptr [rsp+210h+ObjectName.Length], xmm0
0x1800061e4  test    ax, ax
0x1800061e7  jz      loc_180006739
0x1800061ed  mov     ecx, 206h
0x1800061f2  cmp     ax, cx
0x1800061f5  ja      loc_180006665
0x1800061fb  lea     rax, [rbp+110h+Buf1]
0x1800061ff  xor     r8d, r8d; AllocateDestinationString
0x180006202  mov     [rsp+210h+ObjectName.Buffer], rax
0x180006207  lea     rdx, [rbp+110h+SourceString]; SourceString
0x18000620b  mov     eax, 104h
0x180006210  lea     rcx, [rsp+210h+ObjectName]; DestinationString
0x180006215  mov     [rsp+210h+ObjectName.MaximumLength], ax
0x18000621a  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x180006220  movzx   eax, [rsp+210h+ObjectName.Length]
0x180006225  mov     esi, 10h
0x18000622a  cmp     eax, esi
0x18000622c  jnb     short loc_180006247
0x18000622e  mov     r8d, esi
0x180006231  lea     rcx, [rbp+110h+Buf1]
0x180006235  sub     r8, rax; Size
0x180006238  lea     rdx, asc_18004E680; "               "
0x18000623f  add     rcx, rax; void *
0x180006242  call    memcpy_0
0x180006247  mov     rbx, cs:hMem
0x18000624e  mov     r15, rbx
0x180006251  test    r15, r15
0x180006254  jnz     loc_1800062DA
0x18000625a  lea     rsi, pszDest
0x180006261  mov     r15, rbx
0x180006264  test    r15, r15
0x180006267  jz      loc_180006306
0x18000626d  test    byte ptr [r15+11Ch], 1
0x180006275  jnz     loc_1800062FF
0x18000627b  mov     r15, [r15]
0x18000627e  jmp     short loc_180006264
0x180006280  mov     eax, r14d
0x180006283  sub     eax, 64h ; 'd'
0x180006286  jz      loc_180006096
0x18000628c  sub     eax, 2
0x18000628f  jz      short loc_1800062A1
0x180006291  sub     eax, 1
0x180006294  jz      short loc_1800062A1
0x180006296  sub     eax, 18Fh
0x18000629b  jnz     loc_1800066DE
0x1800062a1  mov     edi, 2
0x1800062a6  jmp     loc_18000609B
0x1800062ab  mov     eax, 5
0x1800062b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062b7  lea     rdx, WPP_GLOBAL_Control
0x1800062be  cmp     rcx, rdx
0x1800062c1  jz      short loc_1800062D0
0x1800062c3  test    dword ptr [rcx+1Ch], 200h
0x1800062ca  jnz     loc_1800066F7
0x1800062d0  mov     eax, 5
0x1800062d5  jmp     loc_18000644B
0x1800062da  cmp     [r15+10Ch], esi
0x1800062e1  jnz     loc_18000669F
0x1800062e7  mov     r8d, esi; Size
0x1800062ea  lea     rdx, [r15+8]; Buf2
0x1800062ee  lea     rcx, [rbp+110h+Buf1]; Buf1
0x1800062f2  call    memcmp_0
0x1800062f7  test    eax, eax
0x1800062f9  jnz     loc_18000669F
0x1800062ff  mov     rsi, [r15+110h]
0x180006306  cmp     r14d, 65h ; 'e'
0x18000630a  jnz     loc_1800064CB
0x180006310  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180006317  lea     rsi, word_18005D560
0x18000631e  mov     rax, rbx
0x180006321  inc     rax
0x180006324  cmp     word ptr [rsi+rax*2], 0
0x180006329  jnz     short loc_180006321
0x18000632b  mov     rcx, rbx
0x18000632e  xchg    ax, ax
0x180006330  inc     rcx
0x180006333  cmp     word ptr [rdi+rcx*2], 0
0x180006338  jnz     short loc_180006330
0x18000633a  add     rax, rcx
0x18000633d  mov     ecx, 40h ; '@'; uFlags
0x180006342  lea     rdx, ds:2Ch[rax*2]
0x18000634a  mov     edx, edx; uBytes
0x18000634c  call    cs:__imp_LocalAlloc
0x180006352  mov     r14, rax
0x180006355  test    rax, rax
0x180006358  jz      loc_1800064B7
0x18000635e  movups  xmm0, cs:SsData
0x180006365  movups  xmmword ptr [rax], xmm0
0x180006368  movups  xmm1, cs:xmmword_18005CBD0
0x18000636f  movups  xmmword ptr [rax+10h], xmm1
0x180006373  movsd   xmm0, qword ptr cs:xmmword_18005CBE0
0x18000637b  movsd   qword ptr [rax+20h], xmm0
0x180006380  test    r15, r15
0x180006383  jnz     loc_180006488
0x180006389  mov     eax, cs:dword_18005D028
0x18000638f  or      eax, 1002h
0x180006394  cmp     cs:byte_18005D030, r15b
0x18000639b  jnz     loc_180006B0A
0x1800063a1  cmp     dword ptr cs:xmmword_18005CC38+0Ch, 0
0x1800063a8  jnz     loc_180006B13
0x1800063ae  cmp     cs:dword_18005CCF8, 3
0x1800063b5  jz      loc_180006B1B
0x1800063bb  cmp     cs:dword_18005D048, 0
0x1800063c2  jnz     loc_180006B24
0x1800063c8  mov     [r14+18h], eax
0x1800063cc  lea     rcx, [r14+28h]
0x1800063d0  mov     rax, rbx
0x1800063d3  mov     [r14+8], rcx
0x1800063d7  nop     word ptr [rax+rax+00000000h]
0x1800063e0  cmp     word ptr [rdi+rax*2+2], 0
0x1800063e6  lea     rax, [rax+1]
0x1800063ea  jnz     short loc_1800063E0
0x1800063ec  lea     edx, [rax+1]
0x1800063ef  mov     r8, rdi
0x1800063f2  call    cs:__imp__o_wcscpy_s
0x1800063f8  mov     rax, rbx
0x1800063fb  nop     dword ptr [rax+rax+00h]
0x180006400  cmp     word ptr [rdi+rax*2+2], 0
0x180006406  lea     rax, [rax+1]
0x18000640a  jnz     short loc_180006400
0x18000640c  lea     ecx, [rax+1]
0x18000640f  mov     rax, [r14+8]
0x180006413  lea     rcx, [rax+rcx*2]
0x180006417  mov     [r14+20h], rcx
0x18000641b  nop     dword ptr [rax+rax+00h]
0x180006420  cmp     word ptr [rsi+rbx*2+2], 0
0x180006426  lea     rbx, [rbx+1]
0x18000642a  jnz     short loc_180006420
0x18000642c  lea     edx, [rbx+1]
0x18000642f  mov     r8, rsi
0x180006432  call    cs:__imp__o_wcscpy_s
0x180006438  mov     [r13+0], r14
0x18000643c  lea     rcx, Resource; Resource
0x180006443  call    cs:__imp_RtlReleaseResource
0x180006449  xor     eax, eax
0x18000644b  mov     r12, [rsp+210h+var_28]
0x180006453  mov     rbx, [rsp+210h+arg_8]
0x18000645b  mov     r15, [rsp+210h+var_30]
0x180006463  mov     rdi, [rsp+210h+var_20]
0x18000646b  mov     rcx, [rbp+110h+var_40]
0x180006472  xor     rcx, rsp; StackCookie
0x180006475  call    __security_check_cookie
0x18000647a  add     rsp, 1F8h
0x180006481  pop     r14
0x180006483  pop     r13
0x180006485  pop     rsi
0x180006486  pop     rbp
0x180006487  retn
0x180006488  mov     eax, [r15+118h]
0x18000648f  mov     [r14+18h], eax
0x180006493  mov     rcx, [r15+128h]
0x18000649a  test    rcx, rcx
0x18000649d  jz      loc_1800063CC
0x1800064a3  or      eax, [rcx+10h]
0x1800064a6  mov     [r14+18h], eax
0x1800064aa  mov     rcx, [rcx]
0x1800064ad  test    rcx, rcx
0x1800064b0  jnz     short loc_1800064A3
0x1800064b2  jmp     loc_1800063CC
0x1800064b7  lea     rcx, Resource; Resource
0x1800064be  call    cs:__imp_RtlReleaseResource
0x1800064c4  mov     eax, 8
0x1800064c9  jmp     short loc_18000644B
0x1800064cb  sub     r14d, 64h ; 'd'
0x1800064cf  jz      loc_180006AA3
0x1800064d5  sub     r14d, 2
0x1800064d9  jnz     loc_18000679F
0x1800064df  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800064e6  lea     rsi, word_18005D560
0x1800064ed  mov     rcx, rbx
0x1800064f0  inc     rcx
0x1800064f3  cmp     word ptr [rsi+rcx*2], 0
0x1800064f8  jnz     short loc_1800064F0
0x1800064fa  lea     r14, word_18005D762
0x180006501  mov     rax, rbx
0x180006504  inc     rax
0x180006507  cmp     word ptr [r14+rax*2], 0
0x18000650d  jnz     short loc_180006504
0x18000650f  mov     rdx, rbx
0x180006512  inc     rdx
0x180006515  cmp     word ptr [rdi+rdx*2], 0
0x18000651a  jnz     short loc_180006512
0x18000651c  add     rax, rdx
0x18000651f  add     rax, rcx
0x180006522  mov     ecx, 40h ; '@'; uFlags
0x180006527  lea     rdx, ds:4Eh[rax*2]
0x18000652f  mov     edx, edx; uBytes
0x180006531  call    cs:__imp_LocalAlloc
0x180006537  mov     r13, rax
0x18000653a  test    rax, rax
0x18000653d  jz      loc_1800064B7
0x180006543  movups  xmm0, cs:SsData
0x18000654a  movups  xmmword ptr [rax], xmm0
0x18000654d  movups  xmm1, cs:xmmword_18005CBD0
0x180006554  movups  xmmword ptr [rax+10h], xmm1
0x180006558  movups  xmm0, cs:xmmword_18005CBE0
0x18000655f  movups  xmmword ptr [rax+20h], xmm0
0x180006563  movups  xmm1, cs:xmmword_18005CBF0
0x18000656a  movups  xmmword ptr [rax+30h], xmm1
0x18000656e  movsd   xmm0, cs:qword_18005CC00
0x180006576  movsd   qword ptr [rax+40h], xmm0
0x18000657b  test    r15, r15
0x18000657e  jz      loc_1800066A7
0x180006584  mov     eax, [r15+118h]
0x18000658b  mov     [r13+18h], eax
0x18000658f  mov     rcx, [r15+128h]
0x180006596  test    rcx, rcx
0x180006599  jz      short loc_1800065AA
0x18000659b  or      eax, [rcx+10h]
0x18000659e  mov     [r13+18h], eax
0x1800065a2  mov     rcx, [rcx]
  ... truncated ...
```
