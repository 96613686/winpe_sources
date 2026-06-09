# UserClientShutdown

- ea: `0x180009688`
- end: `0x18000a1af`
- name: `UserClientShutdown`
- size: `2855`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, char, DWORD, union _LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000a500`

## callees

- `0x18000592c`
- `0x1800063a0`
- `0x180006468`
- `0x180007374`
- `0x18000755c`
- `0x180008c10`
- `0x180009688`
- `0x18000a5c8`
- `0x18000a6e0`
- `0x18000b9a8`
- `0x1800138f0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800098de`
- `KERNELBASE!LocalAlloc` at `0x1800098de`
- `ntdll!NtTerminateProcess` at `0x18000a11a`
- `ntdll!NtTerminateProcess` at `0x18000a11a`
- `ntdll!NtWaitForSingleObject` at `0x180009f18`
- `ntdll!NtWaitForSingleObject` at `0x180009f18`
- `ntdll!EtwEventWrite` at `0x180009783`
- `ntdll!EtwEventWrite` at `0x180009ef1`
- `ntdll!EtwEventWrite` at `0x180009f8b`
- `ntdll!EtwEventWrite` at `0x18000a04e`
- `ntdll!EtwEventWrite` at `0x18000a105`
- `ntdll!EtwEventWrite` at `0x18000a18f`
- `ntdll!EtwEventWrite` at `0x180009783`
- `ntdll!EtwEventWrite` at `0x180009ef1`
- `ntdll!EtwEventWrite` at `0x180009f8b`
- `ntdll!EtwEventWrite` at `0x18000a04e`
- `ntdll!EtwEventWrite` at `0x18000a105`
- `ntdll!EtwEventWrite` at `0x18000a18f`
- `ntdll!EtwEventEnabled` at `0x18000973a`
- `ntdll!EtwEventEnabled` at `0x180009eb2`
- `ntdll!EtwEventEnabled` at `0x180009f3b`
- `ntdll!EtwEventEnabled` at `0x18000a004`
- `ntdll!EtwEventEnabled` at `0x18000a0c9`
- `ntdll!EtwEventEnabled` at `0x18000a13f`
- `ntdll!EtwEventEnabled` at `0x18000973a`
- `ntdll!EtwEventEnabled` at `0x180009eb2`
- `ntdll!EtwEventEnabled` at `0x180009f3b`
- `ntdll!EtwEventEnabled` at `0x18000a004`
- `ntdll!EtwEventEnabled` at `0x18000a0c9`
- `ntdll!EtwEventEnabled` at `0x18000a13f`
- `ntdll!NtClose` at `0x180009fdd`
- `ntdll!NtClose` at `0x180009fdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800096f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a091`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800096f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a091`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009968`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009968`
- `CSRSRV!CsrUnlockThread` at `0x18000993f`
- `CSRSRV!CsrUnlockThread` at `0x18000993f`
- `CSRSRV!CsrDereferenceThread` at `0x180009a5c`
- `CSRSRV!CsrDereferenceThread` at `0x180009bb5`
- `CSRSRV!CsrDereferenceThread` at `0x180009e14`
- `CSRSRV!CsrDereferenceThread` at `0x180009a5c`
- `CSRSRV!CsrDereferenceThread` at `0x180009bb5`
- `CSRSRV!CsrDereferenceThread` at `0x180009e14`
- `CSRSRV!CsrLockThreadByClientId` at `0x18000992a`
- `CSRSRV!CsrLockThreadByClientId` at `0x18000992a`
- `CSRSRV!CsrDereferenceProcess` at `0x180009fac`
- `CSRSRV!CsrDereferenceProcess` at `0x180009fac`
- `CSRSRV!CsrUnlockProcess` at `0x180009a15`
- `CSRSRV!CsrUnlockProcess` at `0x180009b14`
- `CSRSRV!CsrUnlockProcess` at `0x180009c6f`
- `CSRSRV!CsrUnlockProcess` at `0x180009cc9`
- `CSRSRV!CsrUnlockProcess` at `0x180009d04`
- `CSRSRV!CsrUnlockProcess` at `0x180009a15`
- `CSRSRV!CsrUnlockProcess` at `0x180009b14`
- `CSRSRV!CsrUnlockProcess` at `0x180009c6f`
- `CSRSRV!CsrUnlockProcess` at `0x180009cc9`
- `CSRSRV!CsrUnlockProcess` at `0x180009d04`
- `CSRSRV!CsrReferenceThread` at `0x180009a05`
- `CSRSRV!CsrReferenceThread` at `0x180009b04`
- `CSRSRV!CsrReferenceThread` at `0x180009cf4`
- `CSRSRV!CsrReferenceThread` at `0x180009a05`
- `CSRSRV!CsrReferenceThread` at `0x180009b04`
- `CSRSRV!CsrReferenceThread` at `0x180009cf4`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000997b`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009a4b`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009ba4`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009e03`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000997b`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009a4b`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009ba4`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009e03`
- `win32u!NtUserQueryInformationThread` at `0x180009904`
- `win32u!NtUserQueryInformationThread` at `0x180009a36`
- `win32u!NtUserQueryInformationThread` at `0x180009d31`
- `win32u!NtUserQueryInformationThread` at `0x180009904`
- `win32u!NtUserQueryInformationThread` at `0x180009a36`
- `win32u!NtUserQueryInformationThread` at `0x180009d31`
- `win32u!NtUserSetInformationThread` at `0x180009e7a`
- `win32u!NtUserSetInformationThread` at `0x180009e7a`

## pseudocode

```c
__int64 __fastcall UserClientShutdown(_QWORD *a1, unsigned int a2, char a3, DWORD a4, union _LARGE_INTEGER a5)
{
  int v5; // r12d
  unsigned int v6; // r15d
  DWORD TickCount; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  NTSTATUS v11; // esi
  unsigned int v12; // ebx
  int v13; // r13d
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  __int128 *p_hMem; // r8
  __int64 v18; // r9
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  int v22; // ecx
  __int128 *v23; // rbx
  int v24; // edx
  unsigned int v25; // esi
  unsigned int v26; // r14d
  __int128 *v27; // rax
  int InformationThread; // eax
  __int64 v29; // rax
  __int128 *v30; // r14
  _QWORD **v31; // r14
  _QWORD *i; // rcx
  _QWORD *j; // rax
  int v34; // ecx
  _QWORD *k; // rcx
  int v36; // ebx
  bool v37; // sf
  __int64 v38; // rcx
  unsigned int v39; // ebx
  __int64 v40; // r8
  unsigned int v41; // ebx
  unsigned int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  unsigned int v45; // ebx
  unsigned int v46; // eax
  int v47; // r12d
  DWORD v48; // r15d
  _QWORD *m; // rax
  unsigned int v50; // ebx
  __int64 v51; // r8
  NTSTATUS v52; // esi
  unsigned int v54; // eax
  bool v55; // cf
  NTSTATUS v57; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v58; // [rsp+50h] [rbp-B0h] BYREF
  int v59; // [rsp+58h] [rbp-A8h]
  unsigned int v60; // [rsp+60h] [rbp-A0h] BYREF
  int v61; // [rsp+68h] [rbp-98h]
  int v62; // [rsp+6Ch] [rbp-94h]
  int v63; // [rsp+70h] [rbp-90h] BYREF
  int v64; // [rsp+78h] [rbp-88h] BYREF
  __int64 v65; // [rsp+80h] [rbp-80h] BYREF
  int v66; // [rsp+88h] [rbp-78h] BYREF
  int v67; // [rsp+8Ch] [rbp-74h]
  NTSTATUS v68; // [rsp+90h] [rbp-70h]
  __int128 hMem; // [rsp+98h] [rbp-68h] BYREF
  __int128 v70; // [rsp+A8h] [rbp-58h]
  int v71; // [rsp+B8h] [rbp-48h]
  DWORD v72; // [rsp+BCh] [rbp-44h]
  __int128 v73; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v74; // [rsp+D0h] [rbp-30h]
  HANDLE Handle; // [rsp+E0h] [rbp-20h]
  NTSTATUS *v76; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+100h] [rbp+0h]
  union _LARGE_INTEGER Timeout; // [rsp+108h] [rbp+8h] BYREF
  __int64 v80; // [rsp+110h] [rbp+10h]

  Timeout = a5;
  v72 = a4;
  v5 = 0;
  Handle = 0;
  v6 = a2;
  v60 = a2;
  v58 = 0;
  v65 = 0;
  hMem = 0;
  v70 = 0;
  v73 = 0;
  v74 = 0;
  TickCount = GetTickCount();
  v11 = *(_DWORD *)a1;
  v57 = TickCount;
  Handle = 0;
  v68 = v11;
  v63 = v6;
  v64 = v11;
  v73 = 0;
  v74 = 0;
  if ( g_EtwRegHandle && (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_ProcessShutdown_Start) )
  {
    v76 = &v64;
    *(_QWORD *)&v77 = 4;
    *((_QWORD *)&v77 + 1) = &v63;
    v78 = 4;
    EtwEventWrite(g_EtwRegHandle, WinSrvEvt_ProcessShutdown_Start, 2, &v76);
  }
  if ( (v6 & 1) == 0 && (*((_BYTE *)a1 + 124) & 8) != 0 )
  {
    v12 = 2;
    goto LABEL_142;
  }
  v61 = 1;
  v64 = 0;
  v13 = 0;
  v63 = 0;
  v67 = -1073741790;
  v62 = 0;
  if ( (v6 & 0x40) != 0 )
    RegisterApplicationRestartCL((HANDLE)a1[10]);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *a1, v6);
  }
  if ( (*((_DWORD *)a1 + 31) & 1) != 0 || (v14 = 0, (v6 & 4) != 0) )
    v14 = 128;
  v15 = v14 | ((v6 & 0x2040580B) != 0 ? 256 : -2147483392);
  if ( (v6 & 0x10) != 0 )
    v15 |= 0x40u;
  LODWORD(hMem) = 0;
  v16 = v15 | 0x800;
  p_hMem = &hMem;
  v18 = 32;
  if ( (v6 & 0x800000) == 0 )
    v16 = v15;
  v19 = v16 | 8;
  if ( (*((_BYTE *)a1 + 124) & 0xC) != 0 )
    v19 = v16;
  v20 = v19 | 1;
  if ( (v6 & 0x40) == 0 )
    v20 = v19;
  v71 = v6 & 4;
  v21 = v20 | 0x40000000;
  if ( (v6 & 4) == 0 )
    v21 = v20;
  v22 = v21 | 4;
  v23 = &hMem;
  if ( (v6 & 1) == 0 )
    v22 = v21;
  v24 = v22 | 0x400;
  if ( (v6 & 2) == 0 )
    v24 = v22;
  v25 = v24 | 0x200;
  if ( (v6 & 0x20) == 0 )
    v25 = v24;
  while ( 1 )
  {
    InformationThread = NtUserQueryInformationThread(a1[10], 11, p_hMem, v18);
    if ( InformationThread >= 0 )
      break;
    if ( InformationThread != -1073741801 )
      goto LABEL_44;
    v26 = *(_DWORD *)v23;
    if ( !*(_DWORD *)v23 )
      goto LABEL_44;
    if ( v23 != &hMem )
      goto LABEL_46;
    v27 = (__int128 *)LocalAlloc(0, v26);
    v23 = v27;
    if ( !v27 )
      goto LABEL_44;
    *(_DWORD *)v27 = 0;
    v18 = v26;
    p_hMem = v27;
  }
  v29 = *(_QWORD *)v23;
  if ( *(_QWORD *)v23 )
  {
    v30 = v23;
    do
    {
      if ( (int)CsrLockThreadByClientId(v29, *a1, &v58) >= 0 )
        CsrUnlockThread(v58);
      v30 = (__int128 *)((char *)v30 + 8);
      v29 = *(_QWORD *)v30;
    }
    while ( *(_QWORD *)v30 );
  }
LABEL_44:
  if ( v23 != &hMem && v23 )
LABEL_46:
    LocalFree(v23);
  CsrLockProcessByClientId(*a1, &v65);
  v31 = (_QWORD **)(a1 + 4);
  DWORD2(hMem) = 2;
  for ( i = (_QWORD *)a1[4]; i != v31; i = (_QWORD *)*i )
  {
    v58 = i - 1;
    *((_DWORD *)i + 16) &= 0xFFFFFFE7;
  }
  v59 = 0;
  v70 = 0;
  do
  {
    while ( 1 )
    {
LABEL_52:
      for ( j = *v31; ; j = (_QWORD *)*j )
      {
        if ( j == v31 )
          goto LABEL_56;
        v58 = j - 1;
        v34 = *((_DWORD *)j + 16);
        if ( (v34 & 0xC) == 0 )
          break;
      }
      *((_DWORD *)j + 16) = v34 | 8;
      HIDWORD(hMem) = v25;
      CsrReferenceThread(v58);
      CsrUnlockProcess(v65);
      v36 = NtUserQueryInformationThread(v58[8], 0, &hMem, 32);
      CsrLockProcessByClientId(*a1, &v65);
      if ( (unsigned int)CsrDereferenceThread(v58) )
      {
        v37 = v36 < 0;
        v12 = 1;
        if ( !v37 && DWORD2(hMem) != 2 )
          break;
      }
    }
    if ( DWORD2(hMem) == 1 )
    {
      CsrUnlockProcess(v65);
LABEL_129:
      v52 = v67;
      goto LABEL_130;
    }
    v38 = (__int64)v58;
    if ( *((_DWORD *)v58 + 12) == gdwThreadEndSession )
      goto LABEL_52;
    if ( (v25 & 8) == 0 && !(_QWORD)hMem )
    {
      DWORD2(hMem) = 2;
      goto LABEL_52;
    }
    ++v59;
    v64 = v71;
    if ( (*((_BYTE *)a1 + 124) & 1) != 0 || (BYTE12(hMem) & 1) == 0 )
    {
      v61 &= 1u;
    }
    else
    {
      v12 = 0;
      v61 = 0;
      if ( !v71 )
        goto LABEL_73;
    }
    BoostHardError(v58[5], 1);
    if ( v12 )
    {
      v5 = v59;
      goto LABEL_52;
    }
    v38 = (__int64)v58;
LABEL_73:
    v66 = 0;
    CsrReferenceThread(v38);
    CsrUnlockProcess(v65);
    EtwLogThreadShutdownNotifyStart(v25 | 2, v58);
    v39 = ThreadShutdownNotify(v25 | 2, (__int64)v58, 0, v72, &v66, Timeout.QuadPart, (__int64)&v73);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v40, v39);
    }
    EtwLogThreadShutdownNotifyStop(v39, v58);
    CsrLockProcessByClientId(*a1, &v65);
    CsrDereferenceThread(v58);
    v41 = v39 - 1;
    if ( !v41 )
      goto LABEL_91;
    v42 = v41 - 1;
    if ( !v42 )
      goto LABEL_88;
    v43 = v42 - 1;
    if ( !v43 )
      goto LABEL_97;
    v44 = v43 - 1;
    if ( !v44 )
    {
      v63 = 1;
      if ( (v25 & 0x200) != 0 )
        v25 &= ~0x100u;
LABEL_88:
      v46 = v25 & 0xFFFFFEFF;
      if ( v71 )
        v46 = v25;
      v25 = v46;
LABEL_91:
      if ( v66 )
        v13 = 1;
      goto LABEL_93;
    }
    v45 = v44 - 1;
    if ( v45 )
    {
      if ( v45 == 2 )
      {
        v25 |= 0x40000380u;
        v62 = 1;
LABEL_97:
        v25 |= 0x100u;
        if ( !v66 )
          goto LABEL_108;
        v13 = 1;
      }
LABEL_93:
      v5 = v59;
      continue;
    }
    if ( !a3 )
      goto LABEL_93;
    v59 = v5;
  }
  while ( !v63 || (v25 & 0x100) != 0 );
LABEL_56:
  if ( v13 )
  {
    for ( k = *v31; k != v31; k = (_QWORD *)*k )
    {
      v58 = k - 1;
      *((_DWORD *)k + 16) &= 0xFFFFFFE7;
    }
    v47 = v64;
    v48 = v72;
LABEL_103:
    for ( m = *v31; m != v31; m = (_QWORD *)*m )
    {
      v58 = m - 1;
      if ( (m[8] & 0xC) == 0 )
      {
        CsrReferenceThread(m - 1);
        CsrUnlockProcess(v65);
        *((_DWORD *)v58 + 18) |= 8u;
        HIDWORD(hMem) = v25;
        if ( (int)NtUserQueryInformationThread(v58[8], 0, &hMem, 32) >= 0
          && DWORD2(hMem) != 2
          && (BYTE12(hMem) & 1) != 0 )
        {
          EtwLogThreadShutdownNotifyStart(v25, v58);
          v50 = ThreadShutdownNotify(v25, (__int64)v58, 0, v48, 0, Timeout.QuadPart, (__int64)&v73);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v51, v50);
          }
          EtwLogThreadShutdownNotifyStop(v50, v58);
          if ( v50 == 4 )
          {
            if ( !v47 )
              v25 &= ~0x100u;
            if ( (v25 & 0x200) != 0 )
              v25 &= ~0x100u;
          }
          else if ( v50 == 7 )
          {
            v62 = 1;
          }
        }
        CsrLockProcessByClientId(*a1, &v65);
        CsrDereferenceThread(v58);
        goto LABEL_103;
      }
    }
    v6 = v60;
  }
LABEL_108:
  CsrUnlockProcess(v65);
  if ( !v61 && (v25 & 0x100) == 0 )
  {
    v12 = 3;
    goto LABEL_129;
  }
  if ( !v59 )
  {
    DWORD2(hMem) = 2;
    goto LABEL_128;
  }
  DWORD2(hMem) = 1;
  if ( (v25 & 8) == 0 )
  {
LABEL_128:
    v12 = 2;
    if ( !*((_QWORD *)&v70 + 1) )
      goto LABEL_141;
    goto LABEL_129;
  }
  v54 = GetTickCount() - v57;
  if ( v54 >= gCmsHungAppTimeout )
    ReportShutdownDelayingProcess((__int64)a1, v54, 1);
  if ( g_EtwRegHandle && (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_TerminateProcess_Start) )
  {
    v57 = *(_DWORD *)a1;
    v80 = 4;
    Timeout.QuadPart = (LONGLONG)&v57;
    EtwEventWrite(g_EtwRegHandle, WinSrvEvt_TerminateProcess_Start, 1, &Timeout);
  }
  v52 = NtTerminateProcess((HANDLE)a1[10], 1073807364);
  v60 = v52;
  if ( g_EtwRegHandle && (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_TerminateProcess_Stop) )
  {
    v57 = *(_DWORD *)a1;
    *(_QWORD *)&v77 = 4;
    v76 = &v57;
    *((_QWORD *)&v77 + 1) = &v60;
    v78 = 4;
    EtwEventWrite(g_EtwRegHandle, WinSrvEvt_TerminateProcess_Stop, 2, &v76);
  }
  *((_DWORD *)a1 + 23) |= 0x40u;
  v55 = v62 != 0;
  v62 = -v62;
  v12 = v55 ? 4 : 1;
LABEL_130:
  v77 = v70;
  v76 = 0;
  v78 = 1;
  NtUserSetInformationThread(-2, 9, &v76);
  if ( v12 != 2 )
  {
    if ( v52 != -1073741790 )
    {
      Timeout.QuadPart = 0;
      if ( g_EtwRegHandle && (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_WaitForProcess_Start) )
      {
        v57 = *(_DWORD *)a1;
        *(_QWORD *)&v77 = 4;
        v76 = &v57;
        EtwEventWrite(g_EtwRegHandle, WinSrvEvt_WaitForProcess_Start, 1, &v76);
      }
      Timeout.QuadPart = -10000LL * (unsigned int)gdwProcessTerminateTimeout;
      v57 = NtWaitForSingleObject((HANDLE)a1[10], 0, &Timeout);
      if ( g_EtwRegHandle && (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_WaitForProcess_Stop) )
      {
        v60 = *(_DWORD *)a1;
        *(_QWORD *)&v77 = 4;
        v76 = &v57;
        *((_QWORD *)&v77 + 1) = &v60;
        v78 = 4;
        EtwEventWrite(g_EtwRegHandle, WinSrvEvt_WaitForProcess_Stop, 2, &v76);
      }
    }
    if ( v12 != 3 )
      BoostHardError(*a1, 1);
    CsrDereferenceProcess(a1);
  }
LABEL_141:
  v11 = v68;
LABEL_142:
  if ( !a3 && v12 == 2 )
    v12 = DefaultProcessShutdown(a1, v6);
  if ( Handle )
    NtClose(Handle);
  v60 = v12;
  v57 = v11;
  if ( g_EtwRegHandle && (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_ProcessShutdown_Stop) )
  {
    v76 = &v57;
    *(_QWORD *)&v77 = 4;
    *((_QWORD *)&v77 + 1) = &v60;
    v78 = 4;
    EtwEventWrite(g_EtwRegHandle, WinSrvEvt_ProcessShutdown_Stop, 2, &v76);
  }
  return v12;
}

```

## disassembly

```asm
0x180009688  mov     [rsp-8+arg_10], rbx
0x18000968d  push    rbp
0x18000968e  push    rsi
0x18000968f  push    rdi
0x180009690  push    r12
0x180009692  push    r13
0x180009694  push    r14
0x180009696  push    r15
0x180009698  lea     rbp, [rsp-20h]
0x18000969d  sub     rsp, 120h
0x1800096a4  mov     rax, cs:__security_cookie
0x1800096ab  xor     rax, rsp
0x1800096ae  mov     [rbp+50h+var_38], rax
0x1800096b2  mov     rax, [rbp+50h+arg_20]
0x1800096b9  xorps   xmm0, xmm0
0x1800096bc  xorps   xmm1, xmm1
0x1800096bf  mov     qword ptr [rbp+50h+Timeout], rax
0x1800096c3  xor     eax, eax
0x1800096c5  mov     [rbp+50h+var_94], r9d
0x1800096c9  xor     r12d, r12d
0x1800096cc  mov     [rbp+50h+Handle], rax
0x1800096d0  mov     [rsp+150h+var_110], r8b
0x1800096d5  mov     r15d, edx
0x1800096d8  mov     [rsp+150h+var_F0], edx
0x1800096dc  mov     rdi, rcx
0x1800096df  mov     [rsp+150h+var_100], r12
0x1800096e4  mov     [rbp+50h+var_D0], r12
0x1800096e8  movups  [rbp+50h+hMem], xmm0
0x1800096ec  movups  [rbp+50h+var_A8], xmm0
0x1800096f0  movups  [rbp+50h+var_90], xmm1
0x1800096f4  movups  [rbp+50h+var_80], xmm1
0x1800096f8  call    cs:__imp_GetTickCount
0x1800096ff  nop     dword ptr [rax+rax+00h]
0x180009704  mov     esi, [rdi]
0x180009706  xorps   xmm0, xmm0
0x180009709  mov     rcx, cs:g_EtwRegHandle
0x180009710  mov     [rsp+150h+var_108], eax
0x180009714  xor     eax, eax
0x180009716  mov     [rbp+50h+Handle], rax
0x18000971a  mov     [rbp+50h+var_C0], esi
0x18000971d  mov     [rsp+150h+var_E0], r15d
0x180009722  mov     [rsp+150h+var_D8], esi
0x180009726  movups  [rbp+50h+var_90], xmm0
0x18000972a  movups  [rbp+50h+var_80], xmm0
0x18000972e  test    rcx, rcx
0x180009731  jz      short loc_18000978F
0x180009733  lea     rdx, WinSrvEvt_ProcessShutdown_Start
0x18000973a  call    cs:__imp_EtwEventEnabled
0x180009741  nop     dword ptr [rax+rax+00h]
0x180009746  test    al, al
0x180009748  jz      short loc_18000978F
0x18000974a  mov     rcx, cs:g_EtwRegHandle
0x180009751  lea     rax, [rsp+150h+var_D8]
0x180009756  mov     [rbp+50h+var_68], rax
0x18000975a  lea     r9, [rbp+50h+var_68]
0x18000975e  lea     rax, [rsp+150h+var_E0]
0x180009763  mov     qword ptr [rbp+50h+var_60], 4
0x18000976b  lea     r8d, [r12+2]
0x180009770  mov     qword ptr [rbp+50h+var_60+8], rax
0x180009774  lea     rdx, WinSrvEvt_ProcessShutdown_Start
0x18000977b  mov     [rbp+50h+var_50], 4
0x180009783  call    cs:__imp_EtwEventWrite
0x18000978a  nop     dword ptr [rax+rax+00h]
0x18000978f  mov     ebx, r15d
0x180009792  mov     r14d, 1
0x180009798  and     ebx, r14d
0x18000979b  jnz     short loc_1800097AC
0x18000979d  test    byte ptr [rdi+7Ch], 8
0x1800097a1  jz      short loc_1800097AC
0x1800097a3  lea     ebx, [r14+1]
0x1800097a7  jmp     loc_180009FBB
0x1800097ac  mov     esi, r15d
0x1800097af  mov     [rsp+150h+var_E8], r14d
0x1800097b4  mov     [rsp+150h+var_D8], r12d
0x1800097b9  mov     r13d, r12d
0x1800097bc  mov     [rsp+150h+var_E0], r12d
0x1800097c1  mov     [rbp+50h+var_C4], 0C0000022h
0x1800097c8  mov     [rsp+150h+var_E4], r12d
0x1800097cd  and     esi, 40h
0x1800097d0  jz      short loc_1800097DB
0x1800097d2  mov     rcx, [rdi+50h]; hProcess
0x1800097d6  call    RegisterApplicationRestartCL
0x1800097db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097e2  lea     rax, WPP_GLOBAL_Control
0x1800097e9  cmp     rcx, rax
0x1800097ec  jz      short loc_18000980B
0x1800097ee  test    [rcx+1Ch], r14b
0x1800097f2  jz      short loc_18000980B
0x1800097f4  cmp     byte ptr [rcx+19h], 4
0x1800097f8  jb      short loc_18000980B
0x1800097fa  mov     r9, [rdi]
0x1800097fd  mov     rcx, [rcx+10h]
0x180009801  mov     dword ptr [rsp+150h+var_130], r15d
0x180009806  call    WPP_SF_qD
0x18000980b  mov     r8d, [rdi+7Ch]
0x18000980f  test    r14b, r8b
0x180009812  jnz     short loc_18000981D
0x180009814  mov     ecx, r12d
0x180009817  test    r15b, 4
0x18000981b  jz      short loc_180009822
0x18000981d  mov     ecx, 80h
0x180009822  mov     eax, r15d
0x180009825  and     eax, 2040580Bh
0x18000982a  neg     eax
0x18000982c  sbb     edx, edx
0x18000982e  and     edx, 80000000h
0x180009834  add     edx, 80000100h
0x18000983a  or      edx, ecx
0x18000983c  test    r15b, 10h
0x180009840  jz      short loc_180009845
0x180009842  or      edx, 40h
0x180009845  mov     ecx, edx
0x180009847  mov     dword ptr [rbp+50h+hMem], r12d
0x18000984b  bts     ecx, 0Bh
0x18000984f  lea     r8, [rbp+50h+hMem]
0x180009853  bt      r15d, 17h
0x180009858  mov     r9d, 20h ; ' '
0x18000985e  cmovnb  ecx, edx
0x180009861  mov     edx, r15d
0x180009864  mov     eax, ecx
0x180009866  or      eax, 8
0x180009869  test    byte ptr [rdi+7Ch], 0Ch
0x18000986d  cmovnz  eax, ecx
0x180009870  mov     ecx, eax
0x180009872  or      ecx, r14d
0x180009875  test    esi, esi
0x180009877  cmovz   ecx, eax
0x18000987a  and     edx, 4
0x18000987d  mov     eax, ecx
0x18000987f  mov     [rbp+50h+var_98], edx
0x180009882  bts     eax, 1Eh
0x180009886  test    edx, edx
0x180009888  cmovz   eax, ecx
0x18000988b  mov     ecx, eax
0x18000988d  or      ecx, 4
0x180009890  test    ebx, ebx
0x180009892  lea     rbx, [rbp+50h+hMem]
0x180009896  cmovz   ecx, eax
0x180009899  mov     edx, ecx
0x18000989b  bts     edx, 0Ah
0x18000989f  test    r15b, 2
0x1800098a3  cmovz   edx, ecx
0x1800098a6  mov     esi, edx
0x1800098a8  bts     esi, 9
0x1800098ac  test    r15b, 20h
0x1800098b0  cmovz   esi, edx
0x1800098b3  jmp     short loc_1800098FB
0x1800098b5  cmp     eax, 0C0000017h
0x1800098ba  jnz     loc_180009957
0x1800098c0  mov     r14d, [rbx]
0x1800098c3  test    r14d, r14d
0x1800098c6  jz      loc_180009957
0x1800098cc  lea     rax, [rbp+50h+hMem]
0x1800098d0  cmp     rbx, rax
0x1800098d3  jnz     loc_180009965
0x1800098d9  mov     edx, r14d; uBytes
0x1800098dc  xor     ecx, ecx; uFlags
0x1800098de  call    cs:__imp_LocalAlloc
0x1800098e5  nop     dword ptr [rax+rax+00h]
0x1800098ea  mov     rbx, rax
0x1800098ed  test    rax, rax
0x1800098f0  jz      short loc_180009957
0x1800098f2  mov     [rax], r12d
0x1800098f5  mov     r9d, r14d
0x1800098f8  mov     r8, rax
0x1800098fb  mov     rcx, [rdi+50h]
0x1800098ff  mov     edx, 0Bh
0x180009904  call    cs:__imp_NtUserQueryInformationThread
0x18000990b  nop     dword ptr [rax+rax+00h]
0x180009910  test    eax, eax
0x180009912  js      short loc_1800098B5
0x180009914  mov     rax, [rbx]
0x180009917  test    rax, rax
0x18000991a  jz      short loc_180009957
0x18000991c  mov     r14, rbx
0x18000991f  mov     rdx, [rdi]
0x180009922  lea     r8, [rsp+150h+var_100]
0x180009927  mov     rcx, rax
0x18000992a  call    cs:__imp_CsrLockThreadByClientId
0x180009931  nop     dword ptr [rax+rax+00h]
0x180009936  test    eax, eax
0x180009938  js      short loc_18000994B
0x18000993a  mov     rcx, [rsp+150h+var_100]
0x18000993f  call    cs:__imp_CsrUnlockThread
0x180009946  nop     dword ptr [rax+rax+00h]
0x18000994b  add     r14, 8
0x18000994f  mov     rax, [r14]
0x180009952  test    rax, rax
0x180009955  jnz     short loc_18000991F
0x180009957  lea     rax, [rbp+50h+hMem]
0x18000995b  cmp     rbx, rax
0x18000995e  jz      short loc_180009974
0x180009960  test    rbx, rbx
0x180009963  jz      short loc_180009974
0x180009965  mov     rcx, rbx; hMem
0x180009968  call    cs:__imp_LocalFree
0x18000996f  nop     dword ptr [rax+rax+00h]
0x180009974  mov     rcx, [rdi]
0x180009977  lea     rdx, [rbp+50h+var_D0]
0x18000997b  call    cs:__imp_CsrLockProcessByClientId
0x180009982  nop     dword ptr [rax+rax+00h]
0x180009987  lea     r14, [rdi+20h]
0x18000998b  mov     dword ptr [rbp+50h+hMem+8], 2
0x180009992  mov     rcx, [r14]
0x180009995  jmp     short loc_1800099A7
0x180009997  lea     rax, [rcx-8]
0x18000999b  mov     [rsp+150h+var_100], rax
0x1800099a0  and     dword ptr [rax+48h], 0FFFFFFE7h
0x1800099a4  mov     rcx, [rcx]
0x1800099a7  cmp     rcx, r14
0x1800099aa  jnz     short loc_180009997
0x1800099ac  xorps   xmm0, xmm0
0x1800099af  mov     [rsp+150h+var_F8], r12d
0x1800099b4  movdqu  [rbp+50h+var_A8], xmm0
0x1800099b9  jmp     short loc_1800099C0
0x1800099bb  mov     r12d, [rsp+150h+var_F8]
0x1800099c0  mov     ebx, 1
0x1800099c5  mov     rax, [r14]
0x1800099c8  jmp     short loc_1800099DE
0x1800099ca  lea     rdx, [rax-8]
0x1800099ce  mov     [rsp+150h+var_100], rdx
0x1800099d3  mov     ecx, [rdx+48h]
0x1800099d6  test    cl, 0Ch
0x1800099d9  jz      short loc_1800099F7
0x1800099db  mov     rax, [rax]
0x1800099de  cmp     rax, r14
0x1800099e1  jnz     short loc_1800099CA
0x1800099e3  xor     r12d, r12d
0x1800099e6  test    r13d, r13d
0x1800099e9  jz      loc_180009CC5
0x1800099ef  mov     rcx, [r14]
0x1800099f2  jmp     loc_180009C93
0x1800099f7  or      ecx, 8
0x1800099fa  mov     [rdx+48h], ecx
0x1800099fd  mov     rcx, [rsp+150h+var_100]
0x180009a02  mov     dword ptr [rbp+50h+hMem+0Ch], esi
0x180009a05  call    cs:__imp_CsrReferenceThread
0x180009a0c  nop     dword ptr [rax+rax+00h]
0x180009a11  mov     rcx, [rbp+50h+var_D0]
0x180009a15  call    cs:__imp_CsrUnlockProcess
0x180009a1c  nop     dword ptr [rax+rax+00h]
0x180009a21  mov     rcx, [rsp+150h+var_100]
0x180009a26  lea     r8, [rbp+50h+hMem]
0x180009a2a  mov     r9d, 20h ; ' '
0x180009a30  xor     edx, edx
0x180009a32  mov     rcx, [rcx+40h]
0x180009a36  call    cs:__imp_NtUserQueryInformationThread
0x180009a3d  nop     dword ptr [rax+rax+00h]
0x180009a42  mov     rcx, [rdi]
0x180009a45  lea     rdx, [rbp+50h+var_D0]
0x180009a49  mov     ebx, eax
0x180009a4b  call    cs:__imp_CsrLockProcessByClientId
0x180009a52  nop     dword ptr [rax+rax+00h]
0x180009a57  mov     rcx, [rsp+150h+var_100]
0x180009a5c  call    cs:__imp_CsrDereferenceThread
0x180009a63  nop     dword ptr [rax+rax+00h]
0x180009a68  test    eax, eax
0x180009a6a  jz      loc_1800099C0
0x180009a70  test    ebx, ebx
0x180009a72  mov     ebx, 1
0x180009a77  js      loc_1800099C5
0x180009a7d  cmp     dword ptr [rbp+50h+hMem+8], 2
0x180009a81  jz      loc_1800099C5
0x180009a87  cmp     dword ptr [rbp+50h+hMem+8], ebx
0x180009a8a  jz      loc_180009C6B
0x180009a90  mov     rcx, [rsp+150h+var_100]
0x180009a95  mov     eax, cs:gdwThreadEndSession
0x180009a9b  cmp     [rcx+30h], eax
0x180009a9e  jz      loc_1800099C5
0x180009aa4  test    sil, 8
0x180009aa8  jnz     short loc_180009ABD
0x180009aaa  cmp     qword ptr [rbp+50h+hMem], 0
0x180009aaf  jnz     short loc_180009ABD
0x180009ab1  mov     dword ptr [rbp+50h+hMem+8], 2
0x180009ab8  jmp     loc_1800099C5
0x180009abd  add     [rsp+150h+var_F8], ebx
0x180009ac1  mov     eax, [rbp+50h+var_98]
0x180009ac4  mov     [rsp+150h+var_D8], eax
0x180009ac8  test    [rdi+7Ch], bl
0x180009acb  jnz     short loc_180009ADE
0x180009acd  test    byte ptr [rbp+50h+hMem+0Ch], bl
0x180009ad0  jz      short loc_180009ADE
0x180009ad2  xor     ebx, ebx
0x180009ad4  mov     [rsp+150h+var_E8], ebx
0x180009ad8  test    eax, eax
0x180009ada  jz      short loc_180009AFD
0x180009adc  jmp     short loc_180009AE2
0x180009ade  and     [rsp+150h+var_E8], ebx
0x180009ae2  mov     rcx, [rcx+28h]
0x180009ae6  mov     edx, 1
0x180009aeb  call    BoostHardError
0x180009af0  test    ebx, ebx
0x180009af2  jnz     loc_1800099BB
0x180009af8  mov     rcx, [rsp+150h+var_100]
0x180009afd  mov     [rbp+50h+var_C8], 0
0x180009b04  call    cs:__imp_CsrReferenceThread
0x180009b0b  nop     dword ptr [rax+rax+00h]
0x180009b10  mov     rcx, [rbp+50h+var_D0]
0x180009b14  call    cs:__imp_CsrUnlockProcess
0x180009b1b  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
