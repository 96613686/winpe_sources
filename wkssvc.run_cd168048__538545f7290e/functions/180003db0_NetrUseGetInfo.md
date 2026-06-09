# NetrUseGetInfo

- ea: `0x180003db0`
- end: `0x180004d1e`
- name: `NetrUseGetInfo`
- size: `3950`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002640`
- `0x180003db0`
- `0x180004d30`
- `0x180005504`
- `0x180005840`
- `0x18000a730`
- `0x18001fbd0`
- `0x1800204f6`
- `0x180031878`
- `0x18003190c`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180003f1c`
- `ntdll!RtlAcquireResourceShared` at `0x180003f1c`
- `ntdll!RtlCopyLuid` at `0x180004108`
- `ntdll!RtlCopyLuid` at `0x1800043b4`
- `ntdll!RtlCopyLuid` at `0x180004421`
- `ntdll!RtlCopyLuid` at `0x180004108`
- `ntdll!RtlCopyLuid` at `0x1800043b4`
- `ntdll!RtlCopyLuid` at `0x180004421`
- `ntdll!NtOpenThreadToken` at `0x180003ec1`
- `ntdll!NtOpenThreadToken` at `0x180003ec1`
- `ntdll!RtlNtStatusToDosError` at `0x180004776`
- `ntdll!RtlNtStatusToDosError` at `0x180004917`
- `ntdll!RtlNtStatusToDosError` at `0x180004776`
- `ntdll!RtlNtStatusToDosError` at `0x180004917`
- `ntdll!NtClose` at `0x1800043c4`
- `ntdll!NtClose` at `0x1800045cd`
- `ntdll!NtClose` at `0x1800043c4`
- `ntdll!NtClose` at `0x1800045cd`
- `ntdll!RtlReleaseResource` at `0x1800040ba`
- `ntdll!RtlReleaseResource` at `0x1800042f3`
- `ntdll!RtlReleaseResource` at `0x1800040ba`
- `ntdll!RtlReleaseResource` at `0x1800042f3`
- `ntdll!RtlCompareUnicodeString` at `0x18000400a`
- `ntdll!RtlCompareUnicodeString` at `0x18000400a`
- `ntdll!NtQueryInformationToken` at `0x180004389`
- `ntdll!NtQueryInformationToken` at `0x180004389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004555`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003e22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000420c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003e22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000420c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000409f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000430b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800044d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000409f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800042d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000430b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800044d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a9c`
- `RPCRT4!RpcImpersonateClient` at `0x180003e9a`
- `RPCRT4!RpcImpersonateClient` at `0x180003e9a`
- `RPCRT4!RpcRevertToSelf` at `0x180003ee9`
- `RPCRT4!RpcRevertToSelf` at `0x180003ee9`
- `netutils!NetpwPathCanonicalize` at `0x180003e57`
- `netutils!NetpwPathCanonicalize` at `0x180003e57`

## pseudocode

```c
DWORD __fastcall NetrUseGetInfo(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  __int64 *v4; // r14
  unsigned int v5; // r12d
  int Info; // ebx
  bool v8; // r13
  _WORD *v9; // rdi
  RPC_STATUS v10; // eax
  int v11; // r8d
  int v12; // eax
  int v13; // esi
  RPC_STATUS v14; // eax
  int v15; // r8d
  char *v16; // r15
  unsigned int v17; // edx
  __int64 LowPart; // r8
  __int64 **v19; // rax
  unsigned __int8 v20; // si
  _WORD *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  HANDLE v24; // rsi
  DWORD v25; // ebx
  int v26; // eax
  _WORD *v27; // rsi
  unsigned int v28; // edx
  unsigned int v29; // ecx
  int v30; // r8d
  int v31; // ecx
  int v32; // ecx
  SIZE_T v33; // rdx
  __int64 v34; // rbx
  char *v35; // rax
  __int16 v36; // cx
  unsigned int v37; // ecx
  int InformationToken; // eax
  int v40; // esi
  __int64 v41; // r14
  char *v42; // rax
  void *v43; // r15
  unsigned int v44; // r12d
  char *v45; // r13
  char *v46; // rcx
  bool v47; // zf
  int v48; // eax
  ULONG v49; // eax
  ULONG v50; // eax
  __int64 v51; // rdx
  char v52; // [rsp+90h] [rbp-80h]
  ULONG ReturnLength[2]; // [rsp+98h] [rbp-78h] BYREF
  void *TokenHandle[2]; // [rsp+A0h] [rbp-70h] BYREF
  struct _LUID SourceLuid; // [rsp+B0h] [rbp-60h] BYREF
  UNICODE_STRING String2; // [rsp+B8h] [rbp-58h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp-48h] BYREF
  int v58; // [rsp+D0h] [rbp-40h] BYREF
  unsigned int v59; // [rsp+D4h] [rbp-3Ch]
  _QWORD *v60; // [rsp+D8h] [rbp-38h]
  _DWORD v61[2]; // [rsp+E0h] [rbp-30h] BYREF
  struct _LUID v62[2]; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v63; // [rsp+F8h] [rbp-18h]
  int v64; // [rsp+100h] [rbp-10h]
  struct _LUID DestinationLuid[7]; // [rsp+108h] [rbp-8h] BYREF

  v4 = 0;
  v5 = (unsigned __int16)a3;
  v60 = a4;
  Info = a3 & 0x10000;
  v59 = (unsigned __int16)a3;
  SourceLuid = 0;
  v8 = (a3 & 0x10000) != 0;
  Handle = 0;
  v52 = v8;
  v58 = 0;
  *a4 = 0;
  if ( (unsigned __int16)a3 > 5u )
    return 124;
  v9 = LocalAlloc(0x40u, 0x20Au);
  if ( !v9 )
    return GetLastError();
  if ( (unsigned int)NetpwPathCanonicalize(a2, v9, 522, 0, &v58, 0) )
  {
    LocalFree(v9);
    return 2250;
  }
  if ( Info )
  {
    v16 = 0;
    *(_QWORD *)ReturnLength = 0;
    SourceLuid = (struct _LUID)-1LL;
    while ( 1 )
    {
LABEL_11:
      if ( !RtlAcquireResourceShared(&Resource, 1u) )
      {
        LocalFree(v9);
        return 2140;
      }
      v17 = 0;
      LowPart = SourceLuid.LowPart;
      while ( v17 < dword_180052110 )
      {
        v19 = (__int64 **)(Use + 24LL * v17);
        if ( *(__int64 **)&SourceLuid == v19[1] || *(__int64 **)&SourceLuid == v19[2] )
        {
          v4 = *v19;
          break;
        }
        ++v17;
      }
      v20 = 0;
      if ( SourceLuid.HighPart == -1 )
        v20 = SourceLuid.LowPart == -1;
      if ( v9[1] != 92 )
      {
        while ( v4 )
        {
          v21 = (_WORD *)v4[2];
          if ( v21 )
          {
            *(_OWORD *)TokenHandle = 0;
            v22 = -1;
            String2 = 0;
            do
              ++v22;
            while ( v21[v22] );
            TokenHandle[1] = v21;
            WORD1(TokenHandle[0]) = 2 * (v22 + 1);
            LOWORD(TokenHandle[0]) = WORD1(TokenHandle[0]);
            v23 = -1;
            do
              ++v23;
            while ( v9[v23] );
            String2.Buffer = v9;
            String2.MaximumLength = 2 * (v23 + 1);
            String2.Length = String2.MaximumLength;
            if ( !RtlCompareUnicodeString((PCUNICODE_STRING)TokenHandle, &String2, 1u) )
              goto LABEL_29;
          }
          v4 = (__int64 *)*v4;
        }
        Info = 2250;
LABEL_65:
        RtlReleaseResource(&Resource);
        goto LABEL_66;
      }
      while ( v4 )
      {
        if ( !v4[2] && !(unsigned int)FULLSTRICMP(v4[1] + 8, v9, LowPart) )
        {
LABEL_29:
          v24 = (HANDLE)v4[4];
          Handle = v24;
          goto LABEL_32;
        }
        v4 = (__int64 *)*v4;
      }
      *(_OWORD *)&v62[0].LowPart = 0;
      v63 = 0;
      v41 = -1;
      v64 = 0;
      TokenHandle[0] = 0;
      do
        ++v41;
      while ( v9[v41] );
      v61[0] = 1;
      v61[1] = 6;
      String2 = 0;
      RtlCopyLuid((PLUID)&v62[0].HighPart, &SourceLuid);
      v62[0].LowPart = 0;
      v64 = 0;
      Info = WsDeviceControlGetInfo(0, WsRedirDeviceHandle, 1311143, v61, 36, TokenHandle, -1, 0);
      if ( Info )
        goto LABEL_65;
      v42 = (char *)TokenHandle[0];
      v43 = TokenHandle[0];
      if ( v62[1].HighPart )
      {
        v44 = 0;
        v45 = (char *)TokenHandle[0];
        v46 = (char *)TokenHandle[0];
        do
        {
          if ( Info )
            break;
          v47 = (unsigned int)WsCompareStringU(
                                *((_QWORD *)v46 + 1),
                                *(unsigned __int16 *)v42 >> 1,
                                v9,
                                (unsigned int)v41) == 0;
          v42 = v45 + 24;
          v45 = v42;
          v46 = v42;
          Info = v47;
          ++v44;
        }
        while ( v44 < v62[1].HighPart );
        v43 = TokenHandle[0];
        v5 = v59;
        v8 = v52;
      }
      LocalFree(v43);
      if ( !Info )
      {
        Info = 2250;
LABEL_204:
        v16 = *(char **)ReturnLength;
        goto LABEL_65;
      }
      v51 = -1;
      do
        ++v51;
      while ( v9[v51] );
      Info = WsCreateTreeConnectName((int)v9, v51, 0, v20, &String2);
      if ( Info )
        goto LABEL_204;
      v4 = 0;
      Info = WsOpenCreateConnectionSpecifyImpersonation(
               (int)&String2,
               0,
               0,
               0,
               0,
               0,
               0,
               0,
               0,
               0,
               0,
               1u,
               -1,
               v20,
               1,
               0,
               &Handle);
      LocalFree(String2.Buffer);
      if ( Info )
        goto LABEL_204;
      RtlReleaseResource(&Resource);
      v24 = Handle;
      v16 = *(char **)ReturnLength;
LABEL_32:
      DestinationLuid[0].LowPart = 1;
      TokenHandle[0] = 0;
      DestinationLuid[3] = 0;
      DestinationLuid[4].LowPart = 0;
      v25 = v5;
      DestinationLuid[0].HighPart = 6;
      if ( v5 > 2 )
        v25 = 2;
      *(_OWORD *)&DestinationLuid[1].LowPart = 0;
      RtlCopyLuid((PLUID)&DestinationLuid[1].HighPart, &SourceLuid);
      DestinationLuid[1].LowPart = v25;
      *(_QWORD *)&DestinationLuid[3].HighPart = 0;
      v26 = 552;
      if ( v25 != 1 )
        v26 = 1136;
      Info = WsDeviceControlGetInfo(0, v24, 1311139, DestinationLuid, 36, TokenHandle, -1, v26);
      if ( !Info )
        break;
LABEL_64:
      if ( v4 )
        goto LABEL_65;
      NtClose(Handle);
LABEL_66:
      if ( v8 || !Info )
      {
        LocalFree(v9);
        *v60 = v16;
        return Info;
      }
      v8 = 1;
      SourceLuid = (struct _LUID)-1LL;
      v52 = 1;
      v4 = 0;
    }
    v27 = TokenHandle[0];
    if ( v4 )
    {
      v28 = *((_DWORD *)v4 + 6);
      if ( v28 > 0xFFFF || (v29 = *(_DWORD *)(v4[1] + 4), v29 > 0xFFFF) )
      {
        Info = 2317;
        goto LABEL_65;
      }
      v30 = 2 * (v29 + v28);
    }
    else
    {
      v30 = *(unsigned __int16 *)TokenHandle[0];
    }
    switch ( v5 )
    {
      case 5u:
        v31 = 112;
        break;
      case 4u:
        v31 = 80;
        break;
      case 3u:
        v31 = 64;
        break;
      case 2u:
        v31 = 56;
        break;
      default:
        if ( v5 == 1 || (v31 = 16, v5 < 2) )
        {
          v32 = 40;
          if ( v5 != 1 )
            v32 = 16;
          goto LABEL_48;
        }
        break;
    }
    v32 = *((unsigned __int16 *)TokenHandle[0] + 16) + 2 + v31;
LABEL_48:
    v33 = (unsigned int)(v30 + v32 + 4);
    if ( v5 >= 2 )
    {
      v48 = *((unsigned __int16 *)TokenHandle[0] + 24);
      if ( (_WORD)v48 )
        v33 = (unsigned int)(v48 + 2 + v33);
    }
    if ( v5 >= 5 )
      v33 = ((_DWORD)v33 + 67) & 0xFFFFFFFC;
    v34 = (unsigned int)v33;
    v35 = (char *)LocalAlloc(0x40u, v33);
    *(_QWORD *)ReturnLength = v35;
    v16 = v35;
    if ( v35 )
    {
      memset_0(v35, 0, (unsigned int)v34);
      *(_QWORD *)&String2.Length = v16;
      TokenHandle[0] = &v16[v34];
      if ( v4 )
      {
        v36 = 2 * *(_WORD *)(v4[1] + 4);
        v27[1] = v36;
        *v27 = v36;
        *((_QWORD *)v27 + 1) = v4[1] + 8;
      }
      switch ( v5 )
      {
        case 5u:
          v37 = 112;
          break;
        case 4u:
          v37 = 80;
          break;
        case 3u:
          v37 = 64;
          break;
        case 2u:
          v37 = 56;
          break;
        default:
          v37 = 16;
          if ( v5 == 1 )
            v37 = 40;
          break;
      }
      if ( &v16[v37] < &v16[v34]
        && (unsigned int)WsFillUseBuffer(v5, (_DWORD)v4, (_DWORD)v27, (unsigned int)&String2, (__int64)TokenHandle, v37) )
      {
        Info = 0;
      }
      else
      {
        Info = 234;
        LocalFree(v16);
        v16 = 0;
        *(_QWORD *)ReturnLength = 0;
      }
      LocalFree(v27);
    }
    else
    {
      Info = 8;
    }
    goto LABEL_64;
  }
  TokenHandle[0] = 0;
  ReturnLength[0] = 0;
  memset(DestinationLuid, 0, sizeof(DestinationLuid));
  v10 = RpcImpersonateClient(0);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v11, (unsigned int)"unknown", 0, v10);
    }
    Info = 5;
    goto LABEL_215;
  }
  v12 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, TokenHandle);
  v13 = v12;
  if ( !v12 )
    goto LABEL_72;
  if ( v12 == -2147483611 )
    goto LABEL_8;
  if ( v12 > -1073741531 )
  {
    if ( v12 > -1073741495 )
    {
      switch ( v12 )
      {
        case -1073741433:
LABEL_150:
          Info = 2226;
          goto LABEL_71;
        case -1073741421:
          Info = 2239;
          goto LABEL_8;
        case -1073741261:
          Info = 2453;
          goto LABEL_8;
      }
    }
    else
    {
      switch ( v12 )
      {
        case -1073741495:
          Info = 2403;
          goto LABEL_8;
        case -1073741529:
          goto LABEL_140;
        case -1073741518:
          Info = 2210;
          goto LABEL_8;
        case -1073741517:
          Info = 2457;
          goto LABEL_8;
        case -1073741516:
          Info = 2249;
          goto LABEL_8;
      }
    }
LABEL_146:
    v49 = RtlNtStatusToDosError(v12);
    Info = 2140;
    if ( v49 != v13 )
      Info = v49;
LABEL_71:
    if ( v13 < 0 )
      goto LABEL_8;
LABEL_72:
    InformationToken = NtQueryInformationToken(TokenHandle[0], TokenStatistics, DestinationLuid, 0x38u, ReturnLength);
    v40 = InformationToken;
    if ( !InformationToken )
    {
      Info = 0;
LABEL_76:
      RtlCopyLuid(&SourceLuid, &DestinationLuid[1]);
      goto LABEL_77;
    }
    if ( InformationToken == -2147483611 )
    {
      Info = 0;
LABEL_77:
      NtClose(TokenHandle[0]);
      goto LABEL_8;
    }
    if ( InformationToken <= -1073741531 )
    {
      if ( InformationToken != -1073741531 )
      {
        switch ( InformationToken )
        {
          case -1073741789:
            Info = 2123;
            break;
          case -1073741727:
            Info = 5;
            break;
          case -1073741726:
            Info = 2202;
            break;
          case -1073741725:
            Info = 2224;
            break;
          case -1073741724:
            Info = 2221;
            break;
          case -1073741723:
            Info = 2223;
            break;
          case -1073741722:
          case -1073741709:
            Info = 2220;
            break;
          case -1073741721:
            Info = 2236;
            break;
          case -1073741720:
            Info = 2237;
            break;
          case -1073741716:
            Info = 2245;
            break;
          case -1073741713:
            Info = 2241;
            break;
          case -1073741712:
            Info = 2240;
            break;
          case -1073741711:
            Info = 2242;
            break;
          case -1073741604:
          case -1073741602:
            goto LABEL_191;
          case -1073741603:
            Info = 2227;
            break;
          case -1073741596:
            Info = 2247;
            break;
          case -1073741573:
            Info = 2102;
            break;
          case -1073741561:
            Info = 2401;
            break;
          case -1073741560:
            Info = 2404;
            break;
          default:
            goto LABEL_187;
        }
        goto LABEL_77;
      }
LABEL_181:
      Info = 2234;
      goto LABEL_107;
    }
    if ( InformationToken > -1073741495 )
    {
      switch ( InformationToken )
      {
        case -1073741433:
LABEL_191:
          Info = 2226;
          goto LABEL_107;
        case -1073741421:
          Info = 2239;
          goto LABEL_77;
        case -1073741261:
          Info = 2453;
          goto LABEL_77;
      }
    }
    else
    {
      switch ( InformationToken )
      {
        case -1073741495:
          Info = 2403;
          goto LABEL_77;
        case -1073741529:
          goto LABEL_181;
        case -1073741518:
          Info = 2210;
          goto LABEL_77;
        case -1073741517:
          Info = 2457;
          goto LABEL_77;
        case -1073741516:
          Info = 2249;
          goto LABEL_77;
      }
    }
LABEL_187:
    v50 = RtlNtStatusToDosError(InformationToken);
    Info = 2140;
    if ( v50 != v40 )
      Info = v50;
LABEL_107:
    if ( v40 < 0 )
      goto LABEL_77;
    goto LABEL_76;
  }
  if ( v12 == -1073741531 )
  {
LABEL_140:
    Info = 2234;
    goto LABEL_71;
  }
  switch ( v12 )
  {
    case -1073741789:
      Info = 2123;
      break;
    case -1073741727:
      Info = 5;
      break;
    case -1073741726:
      Info = 2202;
      break;
    case -1073741725:
      Info = 2224;
      break;
    case -1073741724:
      Info = 2221;
      break;
    case -1073741723:
      Info = 2223;
      break;
    case -1073741722:
    case -1073741709:
      Info = 2220;
      break;
    case -1073741721:
      Info = 2236;
      break;
    case -1073741720:
      Info = 2237;
      break;
    case -1073741716:
      Info = 2245;
      break;
    case -1073741713:
      Info = 2241;
      break;
    case -1073741712:
      Info = 2240;
      break;
    case -1073741711:
      Info = 2242;
      break;
    case -1073741604:
    case -1073741602:
      goto LABEL_150;
    case -1073741603:
      Info = 2227;
      break;
    case -1073741596:
      Info = 2247;
      break;
    case -1073741573:
      Info = 2102;
      break;
    case -1073741561:
      Info = 2401;
      break;
    case -1073741560:
      Info = 2404;
      break;
    default:
      goto LABEL_146;
  }
LABEL_8:
  v14 = RpcRevertToSelf();
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v15, (unsigned int)"unknown", 0, v14);
    }
    __fastfail(7u);
  }
  v4 = 0;
  if ( !Info )
  {
    v16 = 0;
    *(_QWORD *)ReturnLength = 0;
    v52 = v8;
    goto LABEL_11;
  }
LABEL_215:
  LocalFree(v9);
  return Info;
}

```

## disassembly

```asm
0x180003db0  push    rbp
0x180003db2  push    rbx
0x180003db3  push    rsi
0x180003db4  push    r12
0x180003db6  push    r13
0x180003db8  push    r14
0x180003dba  lea     rbp, [rsp-48h]
0x180003dbf  sub     rsp, 158h
0x180003dc6  mov     rax, cs:__security_cookie
0x180003dcd  xor     rax, rsp
0x180003dd0  mov     [rbp+70h+var_40], rax
0x180003dd4  xor     r14d, r14d
0x180003dd7  movzx   r12d, r8w
0x180003ddb  mov     ebx, r8d
0x180003dde  mov     [rbp+70h+var_A8], r9
0x180003de2  and     ebx, 10000h
0x180003de8  mov     [rbp+70h+var_AC], r12d
0x180003dec  mov     rsi, rdx
0x180003def  mov     qword ptr [rbp+70h+SourceLuid.LowPart], r14
0x180003df3  setnz   r13b
0x180003df7  mov     [rbp+70h+Handle], r14
0x180003dfb  mov     [rbp+70h+var_F0], r13b
0x180003dff  mov     [rbp+70h+var_B0], r14d
0x180003e03  mov     [r9], r14
0x180003e06  cmp     r12d, 5
0x180003e0a  ja      loc_180004528
0x180003e10  mov     edx, 20Ah; uBytes
0x180003e15  mov     [rsp+180h+arg_0], rdi
0x180003e1d  mov     ecx, 40h ; '@'; uFlags
0x180003e22  call    cs:__imp_LocalAlloc
0x180003e29  nop     dword ptr [rax+rax+00h]
0x180003e2e  mov     rdi, rax
0x180003e31  test    rax, rax
0x180003e34  jz      loc_180004555
0x180003e3a  lea     rax, [rbp+70h+var_B0]
0x180003e3e  mov     dword ptr [rsp+180h+hMem], r14d
0x180003e43  xor     r9d, r9d
0x180003e46  mov     [rsp+180h+ReturnLength], rax
0x180003e4b  mov     r8d, 20Ah
0x180003e51  mov     rdx, rdi
0x180003e54  mov     rcx, rsi
0x180003e57  call    cs:__imp_NetpwPathCanonicalize
0x180003e5e  nop     dword ptr [rax+rax+00h]
0x180003e63  test    eax, eax
0x180003e65  jnz     loc_1800045EB
0x180003e6b  mov     [rsp+180h+var_30], r15
0x180003e73  test    ebx, ebx
0x180003e75  jnz     loc_1800044F0
0x180003e7b  xorps   xmm0, xmm0
0x180003e7e  mov     [rbp+70h+TokenHandle], r14
0x180003e82  xor     eax, eax
0x180003e84  mov     [rbp+70h+var_E8], r14d
0x180003e88  xor     ecx, ecx; BindingHandle
0x180003e8a  mov     [rbp+70h+var_48], rax
0x180003e8e  movups  xmmword ptr [rbp+70h+DestinationLuid.LowPart], xmm0
0x180003e92  movups  [rbp+70h+var_68], xmm0
0x180003e96  movups  [rbp+70h+var_58], xmm0
0x180003e9a  call    cs:__imp_RpcImpersonateClient
0x180003ea1  nop     dword ptr [rax+rax+00h]
0x180003ea6  test    eax, eax
0x180003ea8  jnz     loc_180004A57
0x180003eae  lea     r9, [rbp+70h+TokenHandle]; TokenHandle
0x180003eb2  mov     r8b, 1; OpenAsSelf
0x180003eb5  mov     edx, 8; DesiredAccess
0x180003eba  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180003ec1  call    cs:__imp_NtOpenThreadToken
0x180003ec8  nop     dword ptr [rax+rax+00h]
0x180003ecd  lea     r14, __ImageBase
0x180003ed4  mov     esi, eax
0x180003ed6  test    eax, eax
0x180003ed8  jz      loc_18000436D
0x180003ede  cmp     eax, 80000025h
0x180003ee3  jnz     loc_180004604
0x180003ee9  call    cs:__imp_RpcRevertToSelf
0x180003ef0  nop     dword ptr [rax+rax+00h]
0x180003ef5  test    eax, eax
0x180003ef7  jnz     loc_180004946
0x180003efd  xor     r14d, r14d
0x180003f00  test    ebx, ebx
0x180003f02  jnz     loc_180004A99
0x180003f08  mov     r15, r14
0x180003f0b  mov     qword ptr [rbp+70h+var_E8], r14
0x180003f0f  mov     [rbp+70h+var_F0], r13b
0x180003f13  mov     dl, 1; Wait
0x180003f15  lea     rcx, Resource; Resource
0x180003f1c  call    cs:__imp_RtlAcquireResourceShared
0x180003f23  nop     dword ptr [rax+rax+00h]
0x180003f28  test    al, al
0x180003f2a  jz      loc_180004532
0x180003f30  mov     r11d, [rbp+70h+SourceLuid.HighPart]
0x180003f34  mov     edx, r14d
0x180003f37  mov     r8d, [rbp+70h+SourceLuid.LowPart]
0x180003f3b  mov     r9d, cs:dword_180052110
0x180003f42  mov     r10, cs:Use
0x180003f49  nop     dword ptr [rax+00000000h]
0x180003f50  cmp     edx, r9d
0x180003f53  jnb     short loc_180003F7D
0x180003f55  mov     eax, edx
0x180003f57  lea     rcx, [rax+rax*2]
0x180003f5b  cmp     r8d, [r10+rcx*8+8]
0x180003f60  lea     rax, [r10+rcx*8]
0x180003f64  jz      short loc_180003F74
0x180003f66  cmp     r8d, [rax+10h]
0x180003f6a  jz      loc_180004566
0x180003f70  inc     edx
0x180003f72  jmp     short loc_180003F50
0x180003f74  cmp     r11d, [rax+0Ch]
0x180003f78  jnz     short loc_180003F66
0x180003f7a  mov     r14, [rax]
0x180003f7d  xor     sil, sil
0x180003f80  cmp     r11d, 0FFFFFFFFh
0x180003f84  jz      loc_180004575
0x180003f8a  cmp     word ptr [rdi+2], 5Ch ; '\'
0x180003f8f  jz      loc_1800043D5
0x180003f95  test    r14, r14
0x180003f98  jz      loc_180004997
0x180003f9e  mov     rcx, [r14+10h]
0x180003fa2  test    rcx, rcx
0x180003fa5  jz      short loc_18000401A
0x180003fa7  xorps   xmm0, xmm0
0x180003faa  xorps   xmm1, xmm1
0x180003fad  movups  xmmword ptr [rbp+70h+TokenHandle], xmm0
0x180003fb1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003fb8  movups  xmmword ptr [rbp+70h+String2.Length], xmm1
0x180003fbc  nop     dword ptr [rax+00h]
0x180003fc0  inc     rax
0x180003fc3  cmp     word ptr [rcx+rax*2], 0
0x180003fc8  jnz     short loc_180003FC0
0x180003fca  inc     ax
0x180003fcd  mov     [rbp+70h+TokenHandle+8], rcx
0x180003fd1  add     ax, ax
0x180003fd4  mov     word ptr [rbp+70h+TokenHandle+2], ax
0x180003fd8  mov     word ptr [rbp+70h+TokenHandle], ax
0x180003fdc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003fe3  inc     rax
0x180003fe6  cmp     word ptr [rdi+rax*2], 0
0x180003feb  jnz     short loc_180003FE3
0x180003fed  inc     ax
0x180003ff0  mov     [rbp+70h+String2.Buffer], rdi
0x180003ff4  add     ax, ax
0x180003ff7  lea     rdx, [rbp+70h+String2]; String2
0x180003ffb  mov     r8b, 1; CaseInsensitive
0x180003ffe  mov     [rbp+70h+String2.MaximumLength], ax
0x180004002  lea     rcx, [rbp+70h+TokenHandle]; String1
0x180004006  mov     [rbp+70h+String2.Length], ax
0x18000400a  call    cs:__imp_RtlCompareUnicodeString
0x180004011  nop     dword ptr [rax+rax+00h]
0x180004016  test    eax, eax
0x180004018  jz      short loc_180004022
0x18000401a  mov     r14, [r14]
0x18000401d  jmp     loc_180003F95
0x180004022  mov     rsi, [r14+20h]
0x180004026  mov     [rbp+70h+Handle], rsi
0x18000402a  jmp     loc_1800040CE
0x18000402f  xor     r14d, r14d
0x180004032  lea     rax, [rbp+70h+Handle]
0x180004036  mov     [rsp+180h+var_F8], r14
0x18000403e  lea     rcx, [rbp+70h+String2]; int
0x180004042  mov     [rsp+180h+FileHandle], rax; FileHandle
0x18000404a  xor     r9d, r9d; int
0x18000404d  mov     [rsp+180h+var_108], r14b; char
0x180004052  xor     r8d, r8d; int
0x180004055  mov     [rsp+180h+var_110], 1; char
0x18000405a  xor     edx, edx; int
0x18000405c  mov     [rsp+180h+var_118], sil; char
0x180004061  mov     [rsp+180h+var_120], 0FFFFFFFFh; int
0x180004069  mov     [rsp+180h+var_128], 1; ULONG
0x180004071  mov     [rsp+180h+var_130], r14d; ULONG
0x180004076  mov     [rsp+180h+var_138], r14; __int64
0x18000407b  mov     [rsp+180h+var_140], r14; __int64
0x180004080  mov     [rsp+180h+var_148], r14; __int64
0x180004085  mov     [rsp+180h+var_150], r14; __int64
0x18000408a  mov     [rsp+180h+hMem], r14; hMem
0x18000408f  mov     [rsp+180h+ReturnLength], r14; __int64
0x180004094  call    WsOpenCreateConnectionSpecifyImpersonation
0x180004099  mov     rcx, [rbp+70h+String2.Buffer]; hMem
0x18000409d  mov     ebx, eax
0x18000409f  call    cs:__imp_LocalFree
0x1800040a6  nop     dword ptr [rax+rax+00h]
0x1800040ab  test    ebx, ebx
0x1800040ad  jnz     loc_1800049FB
0x1800040b3  lea     rcx, Resource; Resource
0x1800040ba  call    cs:__imp_RtlReleaseResource
0x1800040c1  nop     dword ptr [rax+rax+00h]
0x1800040c6  mov     rsi, [rbp+70h+Handle]
0x1800040ca  mov     r15, qword ptr [rbp+70h+var_E8]
0x1800040ce  xor     eax, eax
0x1800040d0  mov     [rbp+70h+DestinationLuid.LowPart], 1
0x1800040d7  mov     ecx, 2
0x1800040dc  mov     [rbp+70h+TokenHandle], rax
0x1800040e0  xorps   xmm0, xmm0
0x1800040e3  mov     qword ptr [rbp+70h+var_68+8], rax
0x1800040e7  cmp     r12d, 2
0x1800040eb  mov     dword ptr [rbp+70h+var_58], eax
0x1800040ee  mov     ebx, r12d
0x1800040f1  mov     [rbp+70h+DestinationLuid.HighPart], 6
0x1800040f8  cmova   ebx, ecx
0x1800040fb  lea     rdx, [rbp+70h+SourceLuid]; SourceLuid
0x1800040ff  lea     rcx, [rbp+70h+DestinationLuid.HighPart+8]; DestinationLuid
0x180004103  movdqu  xmmword ptr [rbp+70h+DestinationLuid.LowPart+8], xmm0
0x180004108  call    cs:__imp_RtlCopyLuid
0x18000410f  nop     dword ptr [rax+rax+00h]
0x180004114  xor     eax, eax
0x180004116  mov     [rbp+70h+DestinationLuid.LowPart+8], ebx
0x180004119  mov     qword ptr [rbp+70h+var_68+0Ch], rax
0x18000411d  lea     r9, [rbp+70h+DestinationLuid]
0x180004121  mov     ecx, 470h
0x180004126  mov     eax, 228h
0x18000412b  cmp     ebx, 1
0x18000412e  mov     r8d, 1401A3h
0x180004134  mov     rdx, rsi
0x180004137  cmovnz  eax, ecx
0x18000413a  xor     ecx, ecx
0x18000413c  mov     dword ptr [rsp+180h+var_148], eax
0x180004140  lea     rax, [rbp+70h+TokenHandle]
0x180004144  mov     dword ptr [rsp+180h+var_150], 0FFFFFFFFh
0x18000414c  mov     [rsp+180h+hMem], rax
0x180004151  mov     dword ptr [rsp+180h+ReturnLength], 24h ; '$'
0x180004159  call    WsDeviceControlGetInfo
0x18000415e  mov     ebx, eax
0x180004160  test    eax, eax
0x180004162  jnz     loc_1800042E3
0x180004168  mov     rsi, [rbp+70h+TokenHandle]
0x18000416c  test    r14, r14
0x18000416f  jz      loc_180004515
0x180004175  mov     edx, [r14+18h]
0x180004179  cmp     edx, 0FFFFh
0x18000417f  ja      loc_18000451E
0x180004185  mov     rax, [r14+8]
0x180004189  mov     ecx, [rax+4]
0x18000418c  cmp     ecx, 0FFFFh
0x180004192  ja      loc_18000451E
0x180004198  lea     r8d, [rcx+rdx]
0x18000419c  add     r8d, r8d
0x18000419f  cmp     r12d, 5
0x1800041a3  jz      loc_1800045B5
0x1800041a9  cmp     r12d, 4
0x1800041ad  jz      loc_180004A04
0x1800041b3  cmp     r12d, 3
0x1800041b7  jz      loc_18000458A
0x1800041bd  cmp     r12d, 2
0x1800041c1  jz      loc_180004A0E
0x1800041c7  mov     eax, 10h
0x1800041cc  cmp     r12d, 1
0x1800041d0  jz      loc_180004504
0x1800041d6  mov     ecx, eax
0x1800041d8  cmp     r12d, 2
0x1800041dc  jb      loc_180004504
0x1800041e2  movzx   eax, word ptr [rsi+20h]
0x1800041e6  add     eax, 2
0x1800041e9  add     ecx, eax
0x1800041eb  lea     edx, [rcx+4]
0x1800041ee  add     edx, r8d; uBytes
0x1800041f1  cmp     r12d, 2
0x1800041f5  jnb     loc_18000459E
0x1800041fb  cmp     r12d, 5
0x1800041ff  jnb     loc_180004A18
0x180004205  mov     ecx, 40h ; '@'; uFlags
0x18000420a  mov     ebx, edx
0x18000420c  call    cs:__imp_LocalAlloc
0x180004213  nop     dword ptr [rax+rax+00h]
0x180004218  mov     qword ptr [rbp+70h+var_E8], rax
0x18000421c  mov     r15, rax
0x18000421f  test    rax, rax
0x180004222  jz      loc_18000454B
0x180004228  mov     r8d, ebx; Size
0x18000422b  xor     edx, edx; Val
0x18000422d  mov     rcx, rax; void *
0x180004230  call    memset_0
0x180004235  mov     qword ptr [rbp+70h+String2.Length], r15
0x180004239  lea     rdx, [rbx+r15]
0x18000423d  mov     [rbp+70h+TokenHandle], rdx
0x180004241  test    r14, r14
0x180004244  jz      short loc_180004264
0x180004246  mov     rax, [r14+8]
0x18000424a  movzx   ecx, word ptr [rax+4]
0x18000424e  add     cx, cx
0x180004251  mov     [rsi+2], cx
0x180004255  mov     [rsi], cx
0x180004258  mov     rax, [r14+8]
0x18000425c  add     rax, 8
0x180004260  mov     [rsi+8], rax
0x180004264  cmp     r12d, 5
0x180004268  jz      loc_1800045BF
0x18000426e  cmp     r12d, 4
0x180004272  jz      loc_180004A23
0x180004278  cmp     r12d, 3
0x18000427c  jz      loc_180004594
0x180004282  cmp     r12d, 2
0x180004286  jz      loc_180004A2D
0x18000428c  cmp     r12d, 1
0x180004290  mov     ecx, 10h
0x180004295  mov     eax, 28h ; '('
0x18000429a  cmovz   ecx, eax
0x18000429d  mov     eax, ecx
0x18000429f  add     rax, r15
0x1800042a2  cmp     rax, rdx
0x1800042a5  jnb     loc_180004A37
0x1800042ab  mov     dword ptr [rsp+180h+hMem], ecx
0x1800042af  lea     rax, [rbp+70h+TokenHandle]
  ... truncated ...
```
