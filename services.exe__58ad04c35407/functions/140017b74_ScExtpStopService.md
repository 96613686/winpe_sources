# ScExtpStopService

- ea: `0x140017b74`
- end: `0x14001828c`
- name: `ScExtpStopService`
- size: `1816`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140017a50`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140017b74`
- `0x140018700`
- `0x1400188fc`
- `0x1400575b0`
- `0x1400885d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400181dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400181dd`
- `ntdll!RtlFreeHeap` at `0x140018237`
- `ntdll!RtlFreeHeap` at `0x140018237`
- `ntdll!RtlAllocateHeap` at `0x140017e22`
- `ntdll!RtlAllocateHeap` at `0x140017e22`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018002`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018133`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001824a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018258`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018261`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018002`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018133`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001824a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018258`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018261`
- `api-ms-win-service-management-l1-1-0!ControlServiceExW` at `0x14001806d`
- `api-ms-win-service-management-l1-1-0!ControlServiceExW` at `0x14001806d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140017bdf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140017bdf`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140017c42`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140017f9e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140017c42`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140017f9e`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x140017dae`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x140017e91`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x140017dae`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x140017e91`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140017ca1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140017ca1`

## pseudocode

```c
__int64 __fastcall ScExtpStopService(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  DWORD LastError; // eax
  unsigned int v5; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // r12
  DWORD v8; // eax
  DWORD v9; // eax
  SC_HANDLE v10; // rsi
  DWORD v11; // eax
  struct _ENUM_SERVICE_STATUSW *Heap; // rax
  _ENUM_SERVICE_STATUSW *p_Services; // r13
  DWORD v14; // eax
  DWORD v15; // edx
  __int64 i; // rcx
  DWORD dwControlsAccepted; // r8d
  __int64 j; // rcx
  const WCHAR *v19; // r15
  __int64 v20; // rcx
  DWORD dwCurrentState; // ebx
  DWORD v22; // eax
  PRPC_ASYNC_STATE v23; // rcx
  int v24; // edx
  int v26; // [rsp+30h] [rbp-D0h]
  _BYTE v27[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v28; // [rsp+44h] [rbp-BCh] BYREF
  SC_HANDLE v29; // [rsp+48h] [rbp-B8h]
  DWORD cbBufSize; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ServicesReturned; // [rsp+54h] [rbp-ACh] BYREF
  int v32; // [rsp+58h] [rbp-A8h]
  __int128 pControlParams; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  _SERVICE_STATUS ServiceStatus; // [rsp+98h] [rbp-68h] BYREF
  _ENUM_SERVICE_STATUSW Services; // [rsp+C0h] [rbp-40h] BYREF

  ServicesReturned = 0;
  v27[0] = 0;
  v36 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  cbBufSize = 0;
  pControlParams = 0;
  v34 = 0;
  v35 = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v29 = v2;
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 103, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, LastError);
    return v5;
  }
  v6 = OpenServiceW(v2, lpServiceName, 0x2Cu);
  v7 = v6;
  if ( !v6 )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        104,
        (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
        (_DWORD)lpServiceName,
        v8);
    goto LABEL_96;
  }
  if ( !QueryServiceStatus(v6, &ServiceStatus) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        105,
        (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
        (_DWORD)lpServiceName,
        v9);
    goto LABEL_95;
  }
  if ( ServiceStatus.dwCurrentState == 1 )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) != 0 )
      WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 106, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, lpServiceName);
    goto LABEL_95;
  }
  if ( (ServiceStatus.dwControlsAccepted & 1) == 0 )
  {
    v5 = 1061;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        107,
        (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
        (_DWORD)lpServiceName,
        ServiceStatus.dwControlsAccepted);
    goto LABEL_95;
  }
  v10 = 0;
  if ( EnumDependentServicesW(v7, 1u, &Services, 0x200u, &cbBufSize, &ServicesReturned) )
  {
    p_Services = &Services;
  }
  else
  {
    v11 = GetLastError();
    v5 = v11;
    if ( v11 != 234 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          108,
          (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
          (_DWORD)lpServiceName,
          v11);
      goto LABEL_94;
    }
    Heap = (struct _ENUM_SERVICE_STATUSW *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, cbBufSize);
    p_Services = Heap;
    if ( !Heap )
    {
      v5 = 8;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 109, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, lpServiceName);
      goto LABEL_94;
    }
    if ( !EnumDependentServicesW(v7, 1u, Heap, cbBufSize, &cbBufSize, &ServicesReturned) )
    {
      v14 = GetLastError();
      v5 = v14;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          110,
          (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
          (_DWORD)lpServiceName,
          v14);
      goto LABEL_89;
    }
  }
  v15 = ServicesReturned;
  for ( i = 0; (unsigned int)i < ServicesReturned; i = (unsigned int)(i + 1) )
  {
    dwControlsAccepted = p_Services[i].ServiceStatus.dwControlsAccepted;
    if ( (dwControlsAccepted & 1) == 0 )
    {
      v5 = 1061;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_SSL(
          WPP_GLOBAL_Control->StubInfo,
          ServicesReturned,
          dwControlsAccepted,
          (_DWORD)lpServiceName,
          (__int64)p_Services[i].lpServiceName,
          dwControlsAccepted);
      goto LABEL_88;
    }
  }
  for ( j = 0; ; j = (unsigned int)(v32 + 1) )
  {
    v32 = j;
    if ( (unsigned int)j >= v15 + 1 )
    {
      v5 = 0;
      goto LABEL_88;
    }
    if ( (_DWORD)j == v15 )
    {
      v19 = lpServiceName;
      v28 = 0;
      v10 = v7;
    }
    else
    {
      v20 = j;
      v19 = p_Services[v20].lpServiceName;
      dwCurrentState = p_Services[v20].ServiceStatus.dwCurrentState;
      v28 = dwCurrentState;
      v10 = OpenServiceW(v29, v19, 0x24u);
      if ( !v10 )
      {
        v22 = GetLastError();
        v5 = v22;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v24 = 112;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
      if ( dwCurrentState == 1 )
        goto LABEL_70;
    }
    v22 = ScExtpWaitForService(v10, (__int64)&v28, 0, v26, (__int64)v27);
    v5 = v22;
    if ( v22 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v24 = 113;
        goto LABEL_86;
      }
      goto LABEL_88;
    }
    if ( v28 == 1 )
    {
      if ( v10 != v7 )
      {
        CloseServiceHandle(v10);
        v10 = 0;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) != 0 )
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 114, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, v19);
      goto LABEL_70;
    }
    v36 = 0;
    pControlParams = 0;
    LODWORD(pControlParams) = 1073938449;
    v34 = 0;
    v35 = 0;
    if ( !ControlServiceExW(v10, 1u, 1u, &pControlParams) )
    {
      v22 = GetLastError();
      v5 = v22;
      if ( v22 != 1062 )
        break;
    }
    if ( DWORD1(v34) != 1 )
    {
      if ( v10 == v7 )
        goto LABEL_70;
      v22 = ScExtpWaitForService(v10, (__int64)&v28, 0, v26, (__int64)v27);
      v5 = v22;
      if ( v22 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v24 = 117;
          goto LABEL_86;
        }
        goto LABEL_88;
      }
      if ( v28 != 1 )
      {
        v5 = 1235;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            119,
            (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
            (_DWORD)lpServiceName,
            v28);
        }
        goto LABEL_88;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) != 0 )
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 118, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, v19);
LABEL_69:
      CloseServiceHandle(v10);
      v10 = 0;
      goto LABEL_70;
    }
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) != 0 )
      WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 116, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, v19);
    if ( v10 != v7 )
      goto LABEL_69;
LABEL_70:
    v15 = ServicesReturned;
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v24 = 115;
LABEL_86:
    WPP_SF_Sd(v23->StubInfo, v24, (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, (_DWORD)v19, v22);
  }
LABEL_88:
  if ( p_Services )
  {
LABEL_89:
    if ( p_Services != &Services )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, p_Services);
  }
  if ( v10 && v10 != v7 )
    CloseServiceHandle(v10);
LABEL_94:
  v3 = v29;
LABEL_95:
  CloseServiceHandle(v7);
LABEL_96:
  CloseServiceHandle(v3);
  return v5;
}

```

## disassembly

```asm
0x140017b74  push    rbp
0x140017b76  push    rbx
0x140017b77  push    rsi
0x140017b78  push    rdi
0x140017b79  push    r12
0x140017b7b  push    r13
0x140017b7d  push    r14
0x140017b7f  push    r15
0x140017b81  lea     rbp, [rsp-1D8h]
0x140017b89  sub     rsp, 2D8h
0x140017b90  mov     rax, cs:__security_cookie
0x140017b97  xor     rax, rsp
0x140017b9a  mov     [rbp+210h+var_50], rax
0x140017ba1  xorps   xmm0, xmm0
0x140017ba4  mov     [rsp+310h+ServicesReturned], 0
0x140017bac  xor     eax, eax
0x140017bae  mov     byte ptr [rsp+310h+var_2D0], 0
0x140017bb3  mov     r14, rcx
0x140017bb6  mov     [rbp+210h+var_280], rax
0x140017bba  movups  xmmword ptr [rbp+210h+ServiceStatus.dwServiceType], xmm0
0x140017bbe  xor     edx, edx; lpDatabaseName
0x140017bc0  mov     [rsp+310h+cbBufSize], eax
0x140017bc4  lea     r15d, [rax+1]
0x140017bc8  xor     ecx, ecx; lpMachineName
0x140017bca  mov     r8d, r15d; dwDesiredAccess
0x140017bcd  movups  [rsp+310h+pControlParams], xmm0
0x140017bd2  movups  [rsp+310h+var_2A0], xmm0
0x140017bd7  movups  [rbp+210h+var_290], xmm0
0x140017bdb  movups  xmmword ptr [rbp+210h+ServiceStatus.dwWin32ExitCode], xmm0
0x140017bdf  call    cs:__imp_OpenSCManagerW
0x140017be5  mov     [rsp+310h+var_2C8], rax
0x140017bea  mov     rsi, rax
0x140017bed  test    rax, rax
0x140017bf0  jnz     short loc_140017C36
0x140017bf2  call    cs:__imp_GetLastError
0x140017bf8  mov     ebx, eax
0x140017bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c01  lea     rdi, WPP_GLOBAL_Control
0x140017c08  cmp     rcx, rdi
0x140017c0b  jz      loc_140018267
0x140017c11  test    [rcx+1Ch], r15b
0x140017c15  jz      loc_140018267
0x140017c1b  mov     rcx, [rcx+10h]
0x140017c1f  lea     edx, [rsi+67h]
0x140017c22  mov     r9d, eax
0x140017c25  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140017c2c  call    WPP_SF_d
0x140017c31  jmp     loc_140018267
0x140017c36  mov     r8d, 2Ch ; ','; dwDesiredAccess
0x140017c3c  mov     rdx, r14; lpServiceName
0x140017c3f  mov     rcx, rax; hSCManager
0x140017c42  call    cs:__imp_OpenServiceW
0x140017c48  mov     r12, rax
0x140017c4b  test    rax, rax
0x140017c4e  jnz     short loc_140017C9A
0x140017c50  call    cs:__imp_GetLastError
0x140017c56  mov     ebx, eax
0x140017c58  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c5f  lea     rdi, WPP_GLOBAL_Control
0x140017c66  cmp     rcx, rdi
0x140017c69  jz      loc_14001825E
0x140017c6f  test    [rcx+1Ch], r15b
0x140017c73  jz      loc_14001825E
0x140017c79  mov     rcx, [rcx+10h]
0x140017c7d  lea     edx, [r12+68h]
0x140017c82  mov     r9, r14
0x140017c85  mov     dword ptr [rsp+310h+pcbBytesNeeded], eax
0x140017c89  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140017c90  call    WPP_SF_Sd
0x140017c95  jmp     loc_14001825E
0x140017c9a  lea     rdx, [rbp+210h+ServiceStatus]; lpServiceStatus
0x140017c9e  mov     rcx, r12; hService
0x140017ca1  call    cs:__imp_QueryServiceStatus
0x140017ca7  test    eax, eax
0x140017ca9  jnz     short loc_140017CF5
0x140017cab  call    cs:__imp_GetLastError
0x140017cb1  mov     ebx, eax
0x140017cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140017cba  lea     rdi, WPP_GLOBAL_Control
0x140017cc1  cmp     rcx, rdi
0x140017cc4  jz      loc_140018255
0x140017cca  test    [rcx+1Ch], r15b
0x140017cce  jz      loc_140018255
0x140017cd4  mov     rcx, [rcx+10h]
0x140017cd8  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140017cdf  mov     edx, 69h ; 'i'
0x140017ce4  mov     dword ptr [rsp+310h+pcbBytesNeeded], eax
0x140017ce8  mov     r9, r14
0x140017ceb  call    WPP_SF_Sd
0x140017cf0  jmp     loc_140018255
0x140017cf5  cmp     [rbp+210h+ServiceStatus.dwCurrentState], r15d
0x140017cf9  jnz     short loc_140017D39
0x140017cfb  xor     ebx, ebx
0x140017cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d04  lea     rdi, WPP_GLOBAL_Control
0x140017d0b  cmp     rcx, rdi
0x140017d0e  jz      loc_140018255
0x140017d14  test    byte ptr [rcx+1Ch], 8
0x140017d18  jz      loc_140018255
0x140017d1e  mov     rcx, [rcx+10h]
0x140017d22  lea     edx, [rbx+6Ah]
0x140017d25  mov     r9, r14
0x140017d28  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140017d2f  call    WPP_SF_S
0x140017d34  jmp     loc_140018255
0x140017d39  mov     eax, [rbp+210h+ServiceStatus.dwControlsAccepted]
0x140017d3c  test    r15b, al
0x140017d3f  jnz     short loc_140017D88
0x140017d41  mov     ebx, 425h
0x140017d46  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d4d  lea     rdi, WPP_GLOBAL_Control
0x140017d54  cmp     rcx, rdi
0x140017d57  jz      loc_140018255
0x140017d5d  test    [rcx+1Ch], r15b
0x140017d61  jz      loc_140018255
0x140017d67  mov     rcx, [rcx+10h]
0x140017d6b  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140017d72  mov     edx, 6Bh ; 'k'
0x140017d77  mov     dword ptr [rsp+310h+pcbBytesNeeded], eax
0x140017d7b  mov     r9, r14
0x140017d7e  call    WPP_SF_Sd
0x140017d83  jmp     loc_140018255
0x140017d88  lea     rax, [rsp+310h+ServicesReturned]
0x140017d8d  mov     r9d, 200h; cbBufSize
0x140017d93  mov     [rsp+310h+lpServicesReturned], rax; lpServicesReturned
0x140017d98  lea     r8, [rbp+210h+Services]; lpServices
0x140017d9c  lea     rax, [rsp+310h+cbBufSize]
0x140017da1  mov     edx, r15d; dwServiceState
0x140017da4  mov     rcx, r12; hService
0x140017da7  mov     [rsp+310h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140017dac  xor     esi, esi
0x140017dae  call    cs:__imp_EnumDependentServicesW
0x140017db4  test    eax, eax
0x140017db6  jnz     loc_140017EE5
0x140017dbc  call    cs:__imp_GetLastError
0x140017dc2  mov     ebx, eax
0x140017dc4  cmp     eax, 0EAh
0x140017dc9  jz      short loc_140017E0B
0x140017dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140017dd2  lea     rdi, WPP_GLOBAL_Control
0x140017dd9  cmp     rcx, rdi
0x140017ddc  jz      loc_140018250
0x140017de2  test    [rcx+1Ch], r15b
0x140017de6  jz      loc_140018250
0x140017dec  mov     rcx, [rcx+10h]
0x140017df0  lea     edx, [rsi+6Ch]
0x140017df3  mov     r9, r14
0x140017df6  mov     dword ptr [rsp+310h+pcbBytesNeeded], eax
0x140017dfa  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140017e01  call    WPP_SF_Sd
0x140017e06  jmp     loc_140018250
0x140017e0b  mov     rcx, gs:60h
0x140017e14  mov     edx, 8; Flags
0x140017e19  mov     r8d, [rsp+310h+cbBufSize]; Size
0x140017e1e  mov     rcx, [rcx+30h]; HeapHandle
0x140017e22  call    cs:__imp_RtlAllocateHeap
0x140017e28  mov     r13, rax
0x140017e2b  test    rax, rax
0x140017e2e  jnz     short loc_140017E6F
0x140017e30  lea     ebx, [rax+8]
0x140017e33  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e3a  lea     rdi, WPP_GLOBAL_Control
0x140017e41  cmp     rcx, rdi
0x140017e44  jz      loc_140018250
0x140017e4a  test    [rcx+1Ch], r15b
0x140017e4e  jz      loc_140018250
0x140017e54  mov     rcx, [rcx+10h]
0x140017e58  lea     edx, [rax+6Dh]
0x140017e5b  mov     r9, r14
0x140017e5e  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140017e65  call    WPP_SF_S
0x140017e6a  jmp     loc_140018250
0x140017e6f  mov     r9d, [rsp+310h+cbBufSize]; cbBufSize
0x140017e74  lea     rax, [rsp+310h+ServicesReturned]
0x140017e79  mov     [rsp+310h+lpServicesReturned], rax; lpServicesReturned
0x140017e7e  mov     r8, r13; lpServices
0x140017e81  lea     rax, [rsp+310h+cbBufSize]
0x140017e86  mov     edx, r15d; dwServiceState
0x140017e89  mov     rcx, r12; hService
0x140017e8c  mov     [rsp+310h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140017e91  call    cs:__imp_EnumDependentServicesW
0x140017e97  test    eax, eax
0x140017e99  jnz     short loc_140017EE9
0x140017e9b  call    cs:__imp_GetLastError
0x140017ea1  mov     ebx, eax
0x140017ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x140017eaa  lea     rdi, WPP_GLOBAL_Control
0x140017eb1  cmp     rcx, rdi
0x140017eb4  jz      loc_14001821C
0x140017eba  test    [rcx+1Ch], r15b
0x140017ebe  jz      loc_14001821C
0x140017ec4  mov     rcx, [rcx+10h]
0x140017ec8  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140017ecf  mov     edx, 6Eh ; 'n'
0x140017ed4  mov     dword ptr [rsp+310h+pcbBytesNeeded], eax
0x140017ed8  mov     r9, r14
0x140017edb  call    WPP_SF_Sd
0x140017ee0  jmp     loc_14001821C
0x140017ee5  lea     r13, [rbp+210h+Services]
0x140017ee9  mov     edx, [rsp+310h+ServicesReturned]
0x140017eed  xor     ecx, ecx
0x140017eef  cmp     ecx, edx
0x140017ef1  jnb     short loc_140017F4F
0x140017ef3  lea     rax, [rcx+rcx*2]
0x140017ef7  add     rax, rax
0x140017efa  mov     r8d, [r13+rax*8+18h]
0x140017eff  test    r15b, r8b
0x140017f02  jz      short loc_140017F09
0x140017f04  add     ecx, r15d
0x140017f07  jmp     short loc_140017EEF
0x140017f09  mov     ebx, 425h
0x140017f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f15  lea     rdi, WPP_GLOBAL_Control
0x140017f1c  cmp     rcx, rdi
0x140017f1f  jz      loc_140018217
0x140017f25  test    [rcx+1Ch], r15b
0x140017f29  jz      loc_140018217
0x140017f2f  mov     rax, [r13+rax*8+0]
0x140017f34  mov     r9, r14
0x140017f37  mov     rcx, [rcx+10h]
0x140017f3b  mov     dword ptr [rsp+310h+lpServicesReturned], r8d
0x140017f40  mov     [rsp+310h+pcbBytesNeeded], rax
0x140017f45  call    WPP_SF_SSL
0x140017f4a  jmp     loc_140018217
0x140017f4f  xor     ecx, ecx
0x140017f51  lea     rdi, WPP_GLOBAL_Control
0x140017f58  lea     eax, [rdx+1]
0x140017f5b  mov     [rsp+310h+var_2B8], ecx
0x140017f5f  cmp     ecx, eax
0x140017f61  jnb     loc_140018215
0x140017f67  cmp     ecx, edx
0x140017f69  jnz     short loc_140017F7B
0x140017f6b  mov     r15, r14
0x140017f6e  mov     dword ptr [rsp+310h+var_2D0+4], 0
0x140017f76  mov     rsi, r12
0x140017f79  jmp     short loc_140017FB9
0x140017f7b  lea     rcx, [rcx+rcx*2]
0x140017f7f  mov     r8d, 24h ; '$'; dwDesiredAccess
0x140017f85  add     rcx, rcx
0x140017f88  mov     r15, [r13+rcx*8+0]
0x140017f8d  mov     ebx, [r13+rcx*8+14h]
0x140017f92  mov     rdx, r15; lpServiceName
0x140017f95  mov     rcx, [rsp+310h+var_2C8]; hSCManager
0x140017f9a  mov     dword ptr [rsp+310h+var_2D0+4], ebx
0x140017f9e  call    cs:__imp_OpenServiceW
0x140017fa4  mov     rsi, rax
0x140017fa7  test    rax, rax
0x140017faa  jz      loc_1400181DD
0x140017fb0  cmp     ebx, 1
0x140017fb3  jz      loc_14001813B
0x140017fb9  lea     rax, [rsp+310h+var_2D0]
0x140017fbe  mov     r8d, 49h ; 'I'
0x140017fc4  mov     [rsp+310h+var_2D8], rax; __int64
0x140017fc9  mov     rdx, r15
0x140017fcc  lea     rax, [rsp+310h+var_2D0+4]
0x140017fd1  mov     [rsp+310h+lpServicesReturned], 0; __int64
0x140017fda  mov     rcx, rsi; hService
0x140017fdd  mov     [rsp+310h+pcbBytesNeeded], rax; __int64
0x140017fe2  call    ScExtpWaitForService
0x140017fe7  mov     ebx, eax
0x140017fe9  test    eax, eax
0x140017feb  jnz     loc_1400181C4
0x140017ff1  lea     ecx, [rax+1]
0x140017ff4  cmp     dword ptr [rsp+310h+var_2D0+4], ecx
0x140017ff8  jnz     short loc_140018041
0x140017ffa  cmp     rsi, r12
0x140017ffd  jz      short loc_14001800A
0x140017fff  mov     rcx, rsi; hSCObject
0x140018002  call    cs:__imp_CloseServiceHandle
0x140018008  xor     esi, esi
0x14001800a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018011  cmp     rcx, rdi
0x140018014  jz      loc_14001813B
0x14001801a  test    byte ptr [rcx+1Ch], 8
0x14001801e  jz      loc_14001813B
0x140018024  mov     rcx, [rcx+10h]
0x140018028  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x14001802f  mov     edx, 72h ; 'r'
0x140018034  mov     r9, r15
0x140018037  call    WPP_SF_S
0x14001803c  jmp     loc_14001813B
0x140018041  xorps   xmm0, xmm0
0x140018044  lea     r9, [rsp+310h+pControlParams]; pControlParams
0x140018049  xor     eax, eax
0x14001804b  mov     r8d, ecx; dwInfoLevel
0x14001804e  mov     edx, ecx; dwControl
0x140018050  mov     [rbp+210h+var_280], rax
0x140018054  movups  [rsp+310h+pControlParams], xmm0
0x140018059  mov     rcx, rsi; hService
0x14001805c  mov     dword ptr [rsp+310h+pControlParams], 40030011h
0x140018064  movups  [rsp+310h+var_2A0], xmm0
0x140018069  movups  [rbp+210h+var_290], xmm0
0x14001806d  call    cs:__imp_ControlServiceExW
0x140018073  test    eax, eax
0x140018075  jnz     short loc_14001808A
0x140018077  call    cs:__imp_GetLastError
0x14001807d  mov     ebx, eax
0x14001807f  cmp     eax, 426h
0x140018084  jnz     loc_14001814A
0x14001808a  cmp     dword ptr [rsp+310h+var_2A0+4], 1
  ... truncated ...
```
