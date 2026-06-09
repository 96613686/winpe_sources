# Auditor::AuditJobOperation(Auditor::TASK_AUDIT_EVENT_TYPE,ushort const *,ushort const *)

- ea: `0x1800349c0`
- end: `0x1800354cc`
- name: `?AuditJobOperation@Auditor@@AEAAJW4TASK_AUDIT_EVENT_TYPE@1@PEBG1@Z`
- size: `2828`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800213f8`
- `0x180045df0`
- `0x18004d868`

## callees

- `0x1800349c0`
- `0x1800354d4`
- `0x180039b6c`
- `0x180054084`
- `0x18005790c`
- `0x18005b124`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!free` at `0x1800354b5`
- `msvcrt!free` at `0x1800354b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003505f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003512b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003517f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003543e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003545c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003505f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003512b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003517f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003543e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003545c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800350d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800350d3`
- `ntdll!NtQueryInformationProcess` at `0x180034da2`
- `ntdll!NtQueryInformationProcess` at `0x180034df4`
- `ntdll!NtQueryInformationProcess` at `0x180034da2`
- `ntdll!NtQueryInformationProcess` at `0x180034df4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034cda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034ff2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034cda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034ff2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034c14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034c14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034acf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034acf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034aeb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180034aeb`
- `RPCRT4!RpcImpersonateClient` at `0x180034abf`
- `RPCRT4!RpcImpersonateClient` at `0x180034abf`
- `RPCRT4!RpcRevertToSelf` at `0x180034af9`
- `RPCRT4!RpcRevertToSelf` at `0x1800350ae`
- `RPCRT4!RpcRevertToSelf` at `0x180034af9`
- `RPCRT4!RpcRevertToSelf` at `0x1800350ae`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180034d4a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180034d4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800354a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800354a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034b2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034b61`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034b2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034b61`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180034d75`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180034d75`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180034f90`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180034f90`
- `AUTHZ!AuthziInitializeAuditParams` at `0x180034f2c`
- `AUTHZ!AuthziInitializeAuditParams` at `0x180034f2c`
- `AUTHZ!AuthziLogAuditEvent` at `0x180034fab`
- `AUTHZ!AuthziLogAuditEvent` at `0x180034fab`
- `AUTHZ!AuthzFreeAuditEvent` at `0x180034fc6`
- `AUTHZ!AuthzFreeAuditEvent` at `0x180034fc6`

## string_xrefs

- `0x180034f10`: `Security`
- `0x18003525d`: `Auditor::GetTokenUserAndStatistics`

## pseudocode

```c
__int64 __fastcall Auditor::AuditJobOperation(__int64 *a1, int a2, __int64 a3, __int16 *a4)
{
  int v6; // edx
  int v7; // edx
  int v8; // edx
  __int64 v10; // rax
  DWORD v11; // r13d
  RPC_STATUS v12; // eax
  EventManager *v13; // rcx
  RPC_STATUS v14; // edi
  HANDLE CurrentThread; // rax
  _QWORD *v16; // rcx
  signed int v17; // eax
  unsigned int v18; // edi
  unsigned __int64 v19; // rsi
  __int64 v20; // rax
  unsigned __int64 v21; // rdi
  SIZE_T v22; // rax
  OLECHAR *v23; // rax
  OLECHAR *v24; // r14
  unsigned __int64 v25; // rcx
  OLECHAR *v26; // rdx
  int v27; // esi
  __int16 v28; // ax
  int v29; // r14d
  DWORD v30; // r15d
  HANDLE v31; // rax
  void *v32; // rsi
  signed int v33; // edi
  Auditor *v34; // rcx
  void *v35; // r12
  unsigned __int16 *ComputerNameDnsFullyQualified; // rax
  unsigned __int16 *v37; // rsi
  const wchar_t *v38; // rcx
  void *v39; // r14
  const OLECHAR *v40; // rdx
  OLECHAR *v41; // rcx
  __int64 v42; // rax
  OLECHAR v43; // r8
  signed int LastError; // eax
  signed int v45; // eax
  __int64 v46; // rdx
  signed int v47; // eax
  _QWORD *v48; // rcx
  __int64 v49; // rdx
  signed int v50; // eax
  signed int v51; // eax
  PDWORD ReturnLength; // [rsp+20h] [rbp-448h]
  const struct _GUID *v53; // [rsp+28h] [rbp-440h]
  int v54; // [rsp+80h] [rbp-3E8h]
  void *TokenHandle; // [rsp+B8h] [rbp-3B0h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-3A8h]
  DWORD v57[2]; // [rsp+C8h] [rbp-3A0h] BYREF
  AUTHZ_AUDIT_EVENT_HANDLE hAuditEvent; // [rsp+D0h] [rbp-398h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp-390h] BYREF
  __int64 v60; // [rsp+E0h] [rbp-388h]
  __int128 v61; // [rsp+E8h] [rbp-380h] BYREF
  int *v62; // [rsp+F8h] [rbp-370h]
  void **pExceptionObject; // [rsp+100h] [rbp-368h] BYREF
  char v64; // [rsp+108h] [rbp-360h]
  const unsigned __int16 *v65; // [rsp+110h] [rbp-358h]
  __int64 v66; // [rsp+118h] [rbp-350h]
  __int64 v67; // [rsp+120h] [rbp-348h]
  RPC_STATUS v68; // [rsp+128h] [rbp-340h]
  __int64 v69; // [rsp+12Ch] [rbp-33Ch]
  void **v70; // [rsp+138h] [rbp-330h] BYREF
  char v71; // [rsp+140h] [rbp-328h]
  const unsigned __int16 *v72; // [rsp+148h] [rbp-320h]
  __int64 v73; // [rsp+150h] [rbp-318h]
  __int64 v74; // [rsp+158h] [rbp-310h]
  int v75; // [rsp+160h] [rbp-308h]
  __int64 v76; // [rsp+164h] [rbp-304h]
  _OWORD ProcessInformation[2]; // [rsp+170h] [rbp-2F8h] BYREF
  __int128 v78; // [rsp+190h] [rbp-2D8h]
  _DWORD RpcCallAttributes[2]; // [rsp+1A0h] [rbp-2C8h] BYREF
  __int128 v80; // [rsp+1A8h] [rbp-2C0h]
  __int128 v81; // [rsp+1B8h] [rbp-2B0h]
  __int128 v82; // [rsp+1C8h] [rbp-2A0h]
  DWORD dwProcessId[4]; // [rsp+1D8h] [rbp-290h]
  __int128 v84; // [rsp+1E8h] [rbp-280h]
  __int128 v85; // [rsp+1F8h] [rbp-270h]
  __int128 v86; // [rsp+208h] [rbp-260h]
  int v87; // [rsp+220h] [rbp-248h] BYREF
  char v88[12]; // [rsp+224h] [rbp-244h] BYREF
  __int64 v89; // [rsp+230h] [rbp-238h]
  char v90[8]; // [rsp+380h] [rbp-E8h] BYREF
  __int64 v91; // [rsp+388h] [rbp-E0h]
  __int64 TokenInformation[14]; // [rsp+3C0h] [rbp-A8h] BYREF

  v60 = a3;
  if ( a2 )
  {
    v6 = a2 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( v8 != 1 )
            return 2147549183LL;
          v10 = a1[2];
        }
        else
        {
          v10 = a1[3];
        }
      }
      else
      {
        v10 = a1[4];
      }
    }
    else
    {
      v10 = a1[1];
    }
  }
  else
  {
    v10 = *a1;
  }
  v56 = v10;
  if ( !v10 )
    return 2147549183LL;
  v11 = 0;
  hAuditEvent = 0;
  v61 = 0;
  v62 = 0;
  v87 = 1;
  memset_0(v88, 0, 0x15Cu);
  hMem = 0;
  TokenHandle = 0;
  v12 = RpcImpersonateClient(0);
  v14 = v12;
  if ( v12 )
  {
    EventManager::EvtReport(v13, &IMPERSONATION_FAILURE, L"Auditor::GetTokenUserAndStatistics", v12, ReturnLength, v53);
    v64 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v65 = &qword_1800A4718;
    v66 = 0;
    v67 = 0;
    v68 = v14;
    v69 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_e148bc2992f63fedaeaba66ed01f4918_Traceguids, v18);
    }
    RpcRevertToSelf();
    goto LABEL_86;
  }
  RpcRevertToSelf();
  v57[0] = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x64u, v57) )
  {
    if ( GetTokenInformation(TokenHandle, TokenStatistics, v90, 0x38u, v57) )
    {
      CloseHandle(TokenHandle);
      v16 = WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    v45 = GetLastError();
    v18 = v45;
    if ( v45 > 0 )
      v18 = (unsigned __int16)v45 | 0x80070000;
    CloseHandle(TokenHandle);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v46 = 20;
LABEL_85:
      WPP_SF_d(v16[2], v46, WPP_e148bc2992f63fedaeaba66ed01f4918_Traceguids, v18);
LABEL_86:
      v16 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    CloseHandle(TokenHandle);
    v17 = GetLastError();
    v18 = v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v46 = 19;
      goto LABEL_85;
    }
  }
  if ( (v18 & 0x80000000) != 0 )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x8000) != 0 && *((_BYTE *)v16 + 25) >= 2u )
      WPP_SF_d(v16[2], 10, WPP_e148bc2992f63fedaeaba66ed01f4918_Traceguids, v18);
    return v18;
  }
LABEL_18:
  v62 = &v87;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(a3 + 2 * v20) );
  v21 = 3500 - v20;
  if ( v20 != 3500 )
  {
    v22 = 2 * v21;
    if ( !is_mul_ok(v21, 2u) )
      v22 = -1;
    v23 = (OLECHAR *)HeapAlloc(g_PrivateHeap, 0, v22);
    v24 = v23;
    *(_QWORD *)v57 = v23;
    if ( !v23 )
    {
      v71 = 0;
      v72 = &qword_1800A4718;
      v73 = 0;
      v74 = 0;
      v75 = 14;
      v76 = -1;
      v70 = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&v70;
    }
    if ( a4 )
    {
      do
        ++v19;
      while ( a4[v19] );
      v25 = v21 - 1;
      if ( v21 - 1 >= v19 )
        v25 = v19;
      if ( v21 > 0x7FFFFFFF )
      {
        v27 = -2147024809;
        *v23 = 0;
      }
      else if ( v25 > 0x7FFFFFFE )
      {
        v27 = -2147024809;
        *v23 = 0;
      }
      else
      {
        v26 = v23;
        v27 = 0;
        while ( v25 )
        {
          v28 = *a4;
          if ( !*a4 )
          {
            if ( !v21 )
            {
LABEL_34:
              --v26;
              v27 = -2147024774;
              break;
            }
            break;
          }
          ++a4;
          *v26++ = v28;
          --v25;
          if ( !--v21 )
            goto LABEL_34;
        }
        *v26 = 0;
      }
    }
    else if ( v21 > 0x7FFFFFFF )
    {
      v27 = -2147024809;
      *v23 = 0;
    }
    else
    {
      v42 = 2147483646;
      v40 = &ChannelPath;
      v41 = v24;
      v27 = 0;
      while ( v42 )
      {
        v43 = *v40;
        if ( !*v40 )
        {
          if ( !v21 )
          {
LABEL_64:
            --v41;
            v27 = -2147024774;
            break;
          }
          break;
        }
        ++v40;
        *v41++ = v43;
        --v42;
        if ( !--v21 )
          goto LABEL_64;
      }
      *v41 = 0;
    }
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_e148bc2992f63fedaeaba66ed01f4918_Traceguids,
          (unsigned int)v27);
      }
      HeapFree(g_PrivateHeap, 0, v24);
      return (unsigned int)v27;
    }
    TokenHandle = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    *(_OWORD *)dwProcessId = 0;
    v84 = 0;
    v85 = 0;
    v86 = 0;
    RpcCallAttributes[0] = 3;
    RpcCallAttributes[1] = 16;
    if ( RpcServerInqCallAttributesW(0, RpcCallAttributes) )
    {
      v33 = -1073741244;
    }
    else
    {
      v29 = 0;
      v30 = dwProcessId[2];
      v11 = dwProcessId[1];
      v31 = OpenProcess(0x1000u, 0, dwProcessId[2]);
      v32 = v31;
      if ( v31 )
      {
        v33 = NtQueryInformationProcess(v31, ProcessLUIDDeviceMapsEnabled|0x40, &TokenHandle, 8u, 0);
        if ( v33 >= 0 )
        {
          TokenHandle = (void *)(((unsigned __int64)MEMORY[0x7FFE02C4] << 48) | (unsigned __int64)TokenHandle);
          memset(ProcessInformation, 0, sizeof(ProcessInformation));
          v78 = 0;
          if ( !NtQueryInformationProcess(v32, ProcessBasicInformation, ProcessInformation, 0x30u, 0) )
          {
            v33 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
            if ( v33 >= 0 )
              v29 = DWORD2(v78);
          }
        }
        CloseHandle(v32);
      }
      else if ( (int)GetLastError() > 0 )
      {
        v33 = (unsigned __int16)GetLastError() | 0xC0070000;
      }
      else
      {
        v33 = GetLastError();
      }
      if ( v33 >= 0 )
      {
        v35 = TokenHandle;
        goto LABEL_51;
      }
      v11 = 0;
    }
    v34 = (Auditor *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v35 = 0;
    }
    else
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_e148bc2992f63fedaeaba66ed01f4918_Traceguids,
        (unsigned int)v33);
      v35 = 0;
    }
    v29 = 0;
    v30 = 0;
LABEL_51:
    ComputerNameDnsFullyQualified = Auditor::GetComputerNameDnsFullyQualified(v34);
    v37 = ComputerNameDnsFullyQualified;
    v38 = L"Unknown";
    if ( ComputerNameDnsFullyQualified )
      v38 = ComputerNameDnsFullyQualified;
    v54 = v29;
    v39 = *(void **)v57;
    LOWORD(ReturnLength) = 8;
    if ( (unsigned int)AuthziInitializeAuditParams(
                         1,
                         &v61,
                         &hMem,
                         L"Security",
                         (_DWORD)ReturnLength,
                         13,
                         v91,
                         2,
                         v60,
                         2,
                         *(_QWORD *)v57,
                         11,
                         v35,
                         3,
                         v30,
                         3,
                         v54,
                         3,
                         v11,
                         2,
                         v38) )
    {
      v89 = TokenInformation[0];
      if ( (unsigned int)AuthziInitializeAuditEvent(
                           0,
                           0,
                           v56,
                           &v61,
                           0,
                           -1,
                           &ChannelPath,
                           &ChannelPath,
                           &ChannelPath,
                           &ChannelPath,
                           &hAuditEvent) )
      {
        if ( (unsigned int)AuthziLogAuditEvent(0, hAuditEvent, 0) )
          goto LABEL_56;
        v51 = GetLastError();
        v33 = v51;
        if ( v51 > 0 )
          v33 = (unsigned __int16)v51 | 0x80070000;
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_56;
        }
        v49 = 16;
      }
      else
      {
        v50 = GetLastError();
        v33 = v50;
        if ( v50 > 0 )
          v33 = (unsigned __int16)v50 | 0x80070000;
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_56;
        }
        v49 = 15;
      }
    }
    else
    {
      v47 = GetLastError();
      v33 = v47;
      if ( v47 > 0 )
        v33 = (unsigned __int16)v47 | 0x80070000;
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_56;
      }
      v49 = 14;
    }
    WPP_SF_d(v48[2], v49, WPP_e148bc2992f63fedaeaba66ed01f4918_Traceguids, (unsigned int)v33);
LABEL_56:
    if ( hAuditEvent )
      AuthzFreeAuditEvent(hAuditEvent);
    if ( hMem )
      LocalFree(hMem);
    if ( v37 )
      free(v37);
    HeapFree(g_PrivateHeap, 0, v39);
    return (unsigned int)v33;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x8000) != 0 && *((_BYTE *)v16 + 25) >= 2u )
    WPP_SF_(v16[2], 11, WPP_e148bc2992f63fedaeaba66ed01f4918_Traceguids);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800349c0  mov     [rsp+arg_8], rbx
0x1800349c5  mov     [rsp+arg_18], rsi
0x1800349ca  push    rdi
0x1800349cb  push    r12
0x1800349cd  push    r13
0x1800349cf  push    r14
0x1800349d1  push    r15
0x1800349d3  sub     rsp, 440h
0x1800349da  mov     rax, cs:__security_cookie
0x1800349e1  xor     rax, rsp
0x1800349e4  mov     [rsp+468h+var_38], rax
0x1800349ec  mov     rbx, r9
0x1800349ef  mov     r14, r8
0x1800349f2  mov     [rsp+468h+var_388], r8
0x1800349fa  test    edx, edx
0x1800349fc  jz      loc_180035252
0x180034a02  sub     edx, 1
0x180034a05  jz      loc_180035249
0x180034a0b  sub     edx, 1
0x180034a0e  jz      short loc_180034A54
0x180034a10  sub     edx, 1
0x180034a13  jz      loc_180035240
0x180034a19  cmp     edx, 1
0x180034a1c  jz      loc_180035237
0x180034a22  mov     eax, 8000FFFFh
0x180034a27  mov     rcx, [rsp+468h+var_38]
0x180034a2f  xor     rcx, rsp; StackCookie
0x180034a32  call    __security_check_cookie
0x180034a37  lea     r11, [rsp+468h+var_28]
0x180034a3f  mov     rbx, [r11+38h]
0x180034a43  mov     rsi, [r11+48h]
0x180034a47  mov     rsp, r11
0x180034a4a  pop     r15
0x180034a4c  pop     r14
0x180034a4e  pop     r13
0x180034a50  pop     r12
0x180034a52  pop     rdi
0x180034a53  retn
0x180034a54  mov     rax, [rcx+20h]
0x180034a58  mov     [rsp+468h+var_3A8], rax
0x180034a60  test    rax, rax
0x180034a63  jz      short loc_180034A22
0x180034a65  xor     r13d, r13d
0x180034a68  mov     [rsp+468h+var_3B8], r13d
0x180034a70  mov     [rsp+468h+hAuditEvent], r13
0x180034a78  xorps   xmm0, xmm0
0x180034a7b  xor     eax, eax
0x180034a7d  movups  [rsp+468h+var_380], xmm0
0x180034a85  mov     [rsp+468h+var_370], rax
0x180034a8d  mov     [rsp+468h+var_248], 1
0x180034a98  xor     edx, edx; Val
0x180034a9a  mov     r8d, 15Ch; Size
0x180034aa0  lea     rcx, [rsp+468h+var_244]; void *
0x180034aa8  call    memset_0
0x180034aad  mov     [rsp+468h+hMem], r13
0x180034ab5  mov     [rsp+468h+TokenHandle], r13
0x180034abd  xor     ecx, ecx; BindingHandle
0x180034abf  call    cs:__imp_RpcImpersonateClient
0x180034ac5  mov     edi, eax
0x180034ac7  test    eax, eax
0x180034ac9  jnz     loc_18003525A
0x180034acf  call    cs:__imp_GetCurrentThread
0x180034ad5  mov     rcx, rax; ThreadHandle
0x180034ad8  lea     r9, [rsp+468h+TokenHandle]; TokenHandle
0x180034ae0  mov     edx, 8; DesiredAccess
0x180034ae5  mov     r8d, 1; OpenAsSelf
0x180034aeb  call    cs:__imp_OpenThreadToken
0x180034af1  test    eax, eax
0x180034af3  jz      loc_18003505F
0x180034af9  call    cs:__imp_RpcRevertToSelf
0x180034aff  mov     [rsp+468h+var_3A0], r13d
0x180034b07  lea     rax, [rsp+468h+var_3A0]
0x180034b0f  mov     [rsp+468h+ReturnLength], rax; ReturnLength
0x180034b14  mov     r9d, 64h ; 'd'; TokenInformationLength
0x180034b1a  lea     r8, [rsp+468h+TokenInformation]; TokenInformation
0x180034b22  mov     edx, 1; TokenInformationClass
0x180034b27  mov     rcx, [rsp+468h+TokenHandle]; TokenHandle
0x180034b2f  call    cs:__imp_GetTokenInformation
0x180034b35  mov     rcx, [rsp+468h+TokenHandle]; hObject
0x180034b3d  test    eax, eax
0x180034b3f  jz      short loc_180034B8D
0x180034b41  lea     rax, [rsp+468h+var_3A0]
0x180034b49  mov     [rsp+468h+ReturnLength], rax; ReturnLength
0x180034b4e  mov     r9d, 38h ; '8'; TokenInformationLength
0x180034b54  lea     r8, [rsp+468h+var_E8]; TokenInformation
0x180034b5c  mov     edx, 0Ah; TokenInformationClass
0x180034b61  call    cs:__imp_GetTokenInformation
0x180034b67  test    eax, eax
0x180034b69  jz      loc_1800350B6
0x180034b6f  mov     rcx, [rsp+468h+TokenHandle]; hObject
0x180034b77  call    cs:__imp_CloseHandle
0x180034b7d  lea     r12, WPP_GLOBAL_Control
0x180034b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b8b  jmp     short loc_180034BC9
0x180034b8d  call    cs:__imp_CloseHandle
0x180034b93  call    cs:__imp_GetLastError
0x180034b99  mov     edi, eax
0x180034b9b  test    eax, eax
0x180034b9d  jg      loc_1800352CD
0x180034ba3  lea     r12, WPP_GLOBAL_Control
0x180034baa  mov     rcx, cs:WPP_GLOBAL_Control
0x180034bb1  cmp     rcx, r12
0x180034bb4  jnz     loc_1800352DB
0x180034bba  mov     [rsp+468h+var_3B8], edi
0x180034bc1  test    edi, edi
0x180034bc3  js      loc_1800352FC
0x180034bc9  lea     rax, [rsp+468h+var_248]
0x180034bd1  mov     [rsp+468h+var_370], rax
0x180034bd9  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180034be0  mov     rax, rsi
0x180034be3  inc     rax
0x180034be6  cmp     word ptr [r14+rax*2], 0
0x180034bec  jnz     short loc_180034BE3
0x180034bee  mov     edi, 0DACh
0x180034bf3  sub     rdi, rax
0x180034bf6  jz      loc_18003532F
0x180034bfc  mov     eax, 2
0x180034c01  mul     rdi
0x180034c04  cmovb   rax, rsi
0x180034c08  mov     r8, rax; dwBytes
0x180034c0b  xor     edx, edx; dwFlags
0x180034c0d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180034c14  call    cs:__imp_HeapAlloc
0x180034c1a  mov     r14, rax
0x180034c1d  mov     qword ptr [rsp+468h+var_3A0], rax
0x180034c25  test    rax, rax
0x180034c28  jz      loc_180035362
0x180034c2e  test    rbx, rbx
0x180034c31  jz      loc_180035027
0x180034c37  nop     word ptr [rax+rax+00000000h]
0x180034c40  inc     rsi
0x180034c43  cmp     word ptr [rbx+rsi*2], 0
0x180034c48  jnz     short loc_180034C40
0x180034c4a  lea     rcx, [rdi-1]
0x180034c4e  cmp     rcx, rsi
0x180034c51  jb      short loc_180034C56
0x180034c53  mov     rcx, rsi
0x180034c56  cmp     rdi, 7FFFFFFFh
0x180034c5d  ja      loc_1800353BF
0x180034c63  mov     eax, 7FFFFFFEh
0x180034c68  cmp     rcx, rax
0x180034c6b  ja      loc_1800353CD
0x180034c71  mov     rdx, r14
0x180034c74  mov     esi, r13d
0x180034c77  test    rcx, rcx
0x180034c7a  jz      short loc_180034CA8
0x180034c7c  movzx   eax, word ptr [rbx]
0x180034c7f  test    ax, ax
0x180034c82  jz      short loc_180034CA3
0x180034c84  add     rbx, 2
0x180034c88  mov     [rdx], ax
0x180034c8b  add     rdx, 2
0x180034c8f  dec     rcx
0x180034c92  sub     rdi, 1
0x180034c96  jnz     short loc_180034C77
0x180034c98  sub     rdx, 2
0x180034c9c  mov     esi, 8007007Ah
0x180034ca1  jmp     short loc_180034CA8
0x180034ca3  test    rdi, rdi
0x180034ca6  jz      short loc_180034C98
0x180034ca8  mov     [rdx], r13w
0x180034cac  lea     rbx, ChannelPath
0x180034cb3  mov     [rsp+468h+var_3B8], esi
0x180034cba  test    esi, esi
0x180034cbc  jns     short loc_180034CE7
0x180034cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180034cc5  cmp     rcx, r12
0x180034cc8  jnz     loc_1800353E9
0x180034cce  mov     r8, r14; lpMem
0x180034cd1  xor     edx, edx; dwFlags
0x180034cd3  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180034cda  call    cs:__imp_HeapFree
0x180034ce0  mov     eax, esi
0x180034ce2  jmp     loc_180034A27
0x180034ce7  mov     [rsp+468h+TokenHandle], r13
0x180034cef  xorps   xmm0, xmm0
0x180034cf2  movups  [rsp+468h+var_2C0], xmm0
0x180034cfa  movups  [rsp+468h+var_2B0], xmm0
0x180034d02  movups  [rsp+468h+var_2A0], xmm0
0x180034d0a  movups  xmmword ptr [rsp+468h+dwProcessId], xmm0
0x180034d12  movups  [rsp+468h+var_280], xmm0
0x180034d1a  movups  [rsp+468h+var_270], xmm0
0x180034d22  movups  [rsp+468h+var_260], xmm0
0x180034d2a  mov     [rsp+468h+RpcCallAttributes], 3
0x180034d35  mov     [rsp+468h+var_2C4], 10h
0x180034d40  lea     rdx, [rsp+468h+RpcCallAttributes]; RpcCallAttributes
0x180034d48  xor     ecx, ecx; ClientBinding
0x180034d4a  call    cs:__imp_RpcServerInqCallAttributesW
0x180034d50  test    eax, eax
0x180034d52  jnz     loc_18003541D
0x180034d58  mov     r14d, r13d
0x180034d5b  mov     r15d, [rsp+468h+dwProcessId+8]
0x180034d63  mov     r13d, [rsp+468h+dwProcessId+4]
0x180034d6b  mov     r8d, r15d; dwProcessId
0x180034d6e  xor     edx, edx; bInheritHandle
0x180034d70  mov     ecx, 1000h; dwDesiredAccess
0x180034d75  call    cs:__imp_OpenProcess
0x180034d7b  mov     rsi, rax
0x180034d7e  test    rax, rax
0x180034d81  jz      loc_180035427
0x180034d87  mov     [rsp+468h+ReturnLength], r14; ReturnLength
0x180034d8c  mov     r9d, 8; ProcessInformationLength
0x180034d92  lea     r8, [rsp+468h+TokenHandle]; ProcessInformation
0x180034d9a  mov     edx, 5Ch ; '\'; ProcessInformationClass
0x180034d9f  mov     rcx, rax; ProcessHandle
0x180034da2  call    cs:__imp_NtQueryInformationProcess
0x180034da8  mov     edi, eax
0x180034daa  test    eax, eax
0x180034dac  js      short loc_180034E02
0x180034dae  mov     eax, ds:7FFE02C4h
0x180034db5  shl     rax, 30h
0x180034db9  or      [rsp+468h+TokenHandle], rax
0x180034dc1  xorps   xmm0, xmm0
0x180034dc4  movups  [rsp+468h+ProcessInformation], xmm0
0x180034dcc  movups  [rsp+468h+var_2E8], xmm0
0x180034dd4  movups  [rsp+468h+var_2D8], xmm0
0x180034ddc  mov     [rsp+468h+ReturnLength], r14; ReturnLength
0x180034de1  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180034de7  lea     r8, [rsp+468h+ProcessInformation]; ProcessInformation
0x180034def  xor     edx, edx; ProcessInformationClass
0x180034df1  mov     rcx, rsi; ProcessHandle
0x180034df4  call    cs:__imp_NtQueryInformationProcess
0x180034dfa  test    eax, eax
0x180034dfc  jz      loc_180035452
0x180034e02  mov     rcx, rsi; hObject
0x180034e05  call    cs:__imp_CloseHandle
0x180034e0b  test    edi, edi
0x180034e0d  jns     loc_180035485
0x180034e13  xor     r13d, r13d
0x180034e16  mov     [rsp+468h+var_3B8], edi
0x180034e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e24  cmp     rcx, r12
0x180034e27  jz      loc_180035499
0x180034e2d  test    dword ptr [rcx+1Ch], 8000h
0x180034e34  jz      loc_180035499
0x180034e3a  cmp     byte ptr [rcx+19h], 2
0x180034e3e  jb      loc_180035499
0x180034e44  mov     edx, 0Dh
0x180034e49  mov     r9d, edi
0x180034e4c  lea     r8, WPP_e148bc2992f63fedaeaba66ed01f4918_Traceguids
0x180034e53  mov     rcx, [rcx+10h]
0x180034e57  call    WPP_SF_d
0x180034e5c  mov     r12, r13
0x180034e5f  jmp     loc_18003549C
0x180034e64  call    ?GetComputerNameDnsFullyQualified@Auditor@@AEAAPEAGXZ; Auditor::GetComputerNameDnsFullyQualified(void)
0x180034e69  mov     rsi, rax
0x180034e6c  lea     rcx, aUnknown; "Unknown"
0x180034e73  test    rax, rax
0x180034e76  cmovnz  rcx, rax
0x180034e7a  mov     [rsp+468h+var_3C8], rcx
0x180034e82  mov     [rsp+468h+var_3D0], 2
0x180034e8d  mov     [rsp+468h+var_3D8], r13d
0x180034e95  mov     [rsp+468h+var_3E0], 3
0x180034ea0  mov     [rsp+468h+var_3E8], r14d
0x180034ea8  mov     [rsp+468h+var_3F0], 3
0x180034eb0  mov     [rsp+468h+var_3F8], r15d
0x180034eb5  mov     [rsp+468h+var_400], 3
0x180034ebd  mov     [rsp+468h+var_408], r12
0x180034ec2  mov     [rsp+468h+var_410], 0Bh
0x180034eca  mov     r14, qword ptr [rsp+468h+var_3A0]
0x180034ed2  mov     [rsp+468h+var_418], r14
0x180034ed7  mov     dword ptr [rsp+468h+var_420], 2
0x180034edf  mov     rax, [rsp+468h+var_388]
0x180034ee7  mov     [rsp+468h+var_428], rax
0x180034eec  mov     dword ptr [rsp+468h+var_430], 2
0x180034ef4  mov     rax, [rsp+468h+var_E0]
0x180034efc  mov     [rsp+468h+var_438], rax
0x180034f01  mov     dword ptr [rsp+468h+var_440], 0Dh
0x180034f09  mov     word ptr [rsp+468h+ReturnLength], 8
0x180034f10  lea     r9, aSecurity; "Security"
0x180034f17  lea     r8, [rsp+468h+hMem]
0x180034f1f  lea     rdx, [rsp+468h+var_380]
0x180034f27  mov     ecx, 1
0x180034f2c  call    cs:__imp_AuthziInitializeAuditParams
0x180034f32  test    eax, eax
0x180034f34  jz      loc_18003512B
0x180034f3a  mov     rax, [rsp+468h+TokenInformation]
0x180034f42  mov     [rsp+468h+var_238], rax
0x180034f4a  lea     rax, [rsp+468h+hAuditEvent]
0x180034f52  mov     [rsp+468h+var_418], rax
0x180034f57  mov     [rsp+468h+var_420], rbx
0x180034f5c  mov     [rsp+468h+var_428], rbx
0x180034f61  mov     [rsp+468h+var_430], rbx
0x180034f66  mov     [rsp+468h+var_438], rbx
0x180034f6b  mov     dword ptr [rsp+468h+var_440], 0FFFFFFFFh
0x180034f73  mov     [rsp+468h+ReturnLength], 0
0x180034f7c  lea     r9, [rsp+468h+var_380]
0x180034f84  mov     r8, [rsp+468h+var_3A8]
0x180034f8c  xor     edx, edx
0x180034f8e  xor     ecx, ecx
0x180034f90  call    cs:__imp_AuthziInitializeAuditEvent
0x180034f96  test    eax, eax
0x180034f98  jz      loc_18003517F
0x180034f9e  xor     r8d, r8d
0x180034fa1  mov     rdx, [rsp+468h+hAuditEvent]
0x180034fa9  xor     ecx, ecx
0x180034fab  call    cs:__imp_AuthziLogAuditEvent
0x180034fb1  test    eax, eax
0x180034fb3  jz      loc_1800351D0
0x180034fb9  mov     rcx, [rsp+468h+hAuditEvent]; hAuditEvent
  ... truncated ...
```
