# PolicyManager::Start(void)

- ea: `0x1800ab458`
- end: `0x1800aba78`
- name: `?Start@PolicyManager@@QEAAKXZ`
- size: `1568`
- prototype: `unsigned int __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007bae4`

## callees

- `0x180006770`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x18002d6dc`
- `0x1800660ac`
- `0x18006c144`
- `0x180077ad0`
- `0x180083b84`
- `0x180092008`
- `0x180092ee4`
- `0x1800a9c10`
- `0x1800aa42c`
- `0x1800ab458`
- `0x1800abd88`
- `0x1800d334c`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800ab7d1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800ab873`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800ab9af`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800ab7d1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800ab873`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800ab9af`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab80b`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab8ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab9e9`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab80b`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab8ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab9e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab68e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab90c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab68e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab90c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800ab74b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800ab74b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800ab521`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800ab521`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800ab534`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800ab534`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aba3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aba3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab4b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab4b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab764`
- `USERENV!RegisterGPNotification` at `0x1800ab75a`
- `USERENV!RegisterGPNotification` at `0x1800ab75a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PolicyManager::Start(PSRWLOCK SRWLock)
{
  HANDLE EventW; // rax
  PVOID Ptr; // rcx
  DWORD LastError; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v9; // rcx
  __int64 v10; // rcx
  unsigned int WinevtRegPath; // eax
  int v12; // ebx
  HKEY *phkResult; // rax
  PVOID *v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // eax
  NTSTATUS v17; // ebx
  __int64 v18; // rax
  unsigned int v19; // eax
  NTSTATUS v20; // ebx
  HKEY *v21; // rax
  bool v22; // al
  __int64 v23; // rax
  unsigned int v24; // eax
  NTSTATUS v25; // ebx
  ULONG v26; // eax
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-49h] BYREF
  char v28; // [rsp+48h] [rbp-41h]
  _BYTE v29[32]; // [rsp+60h] [rbp-29h] BYREF
  __int128 pExceptionObject; // [rsp+80h] [rbp-9h] BYREF
  __int64 v31; // [rsp+90h] [rbp+7h]
  int v32; // [rsp+98h] [rbp+Fh]
  __int64 v33; // [rsp+9Ch] [rbp+13h]
  char v34; // [rsp+A4h] [rbp+1Bh]
  __int64 v35; // [rsp+F0h] [rbp+67h] BYREF
  HKEY v36; // [rsp+F8h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+100h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  Ptr = SRWLock[5].Ptr;
  SRWLock[5].Ptr = EventW;
  if ( Ptr )
    PolicyManager::CloseGPNotification(Ptr);
  if ( !SRWLock[5].Ptr )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v6 = 11;
LABEL_12:
    WPP_SF_d(v5[2], v6, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, LastError);
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(PolicyManager::PolicyChangedCallback, SRWLock, 0);
  v9 = (struct _TP_WAIT *)SRWLock[6].Ptr;
  SRWLock[6].Ptr = ThreadpoolWait;
  if ( v9 )
    CloseThreadpoolWait(v9);
  if ( !SRWLock[6].Ptr )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v6 = 12;
    goto LABEL_12;
  }
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpSubKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v29);
  WinevtRegPath = RegistryPaths::GetWinevtRegPath(v10, &hKey, &lpSubKey, v29);
  v12 = WinevtRegPath;
  if ( WinevtRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, WinevtRegPath);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v31 = 0;
    v32 = v12;
    v33 = -1;
    v34 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&lpSubKey) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, 14);
    }
    pExceptionObject = 0;
    v31 = 0;
    v32 = 14;
    v33 = 0x68FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v35 = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v35);
  LastError = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, phkResult);
  if ( !v35 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids,
          LastError,
          (__int64)lpSubKey);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x2000) != 0 && *((_BYTE *)v14 + 25) >= 2u )
        WPP_SF_d(v14[2], 16, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, LastError);
    }
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v35);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpSubKey);
    return LastError;
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v35);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpSubKey);
  SetThreadpoolWait((PTP_WAIT)SRWLock[6].Ptr, SRWLock[5].Ptr, 0);
  if ( !RegisterGPNotification(SRWLock[5].Ptr, 1) )
  {
    LastError = GetLastError();
    if ( LastError != 1 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return LastError;
      }
      v6 = 17;
      goto LABEL_12;
    }
  }
  v15 = tlx::replace<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(&SRWLock[3]);
  v16 = RtlSubscribeWnfStateChangeNotification(
          v15,
          WNF_ENTR_APPHVSI_POLICY_VALUE_CHANGED,
          0,
          PolicyManager::WnfNotificationCallback,
          SRWLock,
          0,
          0,
          0);
  v17 = v16;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, v16);
    }
    LastError = RtlNtStatusToDosError(v17);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v6 = 19;
    goto LABEL_12;
  }
  v18 = tlx::replace<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(&SRWLock[4]);
  v19 = RtlSubscribeWnfStateChangeNotification(
          v18,
          WNF_DCSP_POLICIES_UPDATED,
          0,
          PolicyManager::WnfNotificationCallback,
          SRWLock,
          0,
          0,
          0);
  v20 = v19;
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, v19);
    }
    LastError = RtlNtStatusToDosError(v20);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v6 = 21;
    goto LABEL_12;
  }
  v36 = 0;
  v21 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v36);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Containers",
         0,
         0x20119u,
         v21) )
  {
    BYTE1(SRWLock[16].Ptr) = 1;
  }
  else
  {
    LODWORD(v35) = 0;
    if ( (unsigned int)RegReadDWORDValueNoThrow(v36, &pszFormat, L"WaitForRestore", (unsigned int *)&v35) )
      v22 = 1;
    else
      v22 = (_DWORD)v35 == 0;
    BYTE1(SRWLock[16].Ptr) = v22;
    if ( !v22 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids);
      }
      v23 = tlx::replace<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(&SRWLock[1]);
      v24 = RtlSubscribeWnfStateChangeNotification(
              v23,
              WNF_CONT_CONTAINER_STATE,
              0,
              PolicyManager::WnfNotificationCallback,
              SRWLock,
              0,
              0,
              0);
      v25 = v24;
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, v24);
        }
        v26 = RtlNtStatusToDosError(v25);
        LastError = v26;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids, v26);
        }
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v36);
        return LastError;
      }
    }
  }
  lpSubKey = (LPCWSTR)SRWLock;
  AcquireSRWLockExclusive(SRWLock);
  v28 = 1;
  PolicyManager::Update(SRWLock, &lpSubKey);
  utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&lpSubKey);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v36);
  return 0;
}

```

## disassembly

```asm
0x1800ab458  push    rbp
0x1800ab45a  push    rbx
0x1800ab45b  push    rsi
0x1800ab45c  push    rdi
0x1800ab45d  push    r12
0x1800ab45f  push    r14
0x1800ab461  push    r15
0x1800ab463  lea     rbp, [rsp-27h]
0x1800ab468  sub     rsp, 0B0h
0x1800ab46f  mov     rdi, rcx
0x1800ab472  lea     r15, WPP_GLOBAL_Control
0x1800ab479  lea     r12, WPP_8f94f11693c33cfbcff3cd2e634423d0_Traceguids
0x1800ab480  mov     r14d, 2000h
0x1800ab486  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab48d  cmp     rcx, r15
0x1800ab490  jz      short loc_1800AB4AF
0x1800ab492  test    [rcx+1Ch], r14d
0x1800ab496  jz      short loc_1800AB4AF
0x1800ab498  cmp     byte ptr [rcx+19h], 4
0x1800ab49c  jb      short loc_1800AB4AF
0x1800ab49e  mov     edx, 0Ah
0x1800ab4a3  mov     r8, r12
0x1800ab4a6  mov     rcx, [rcx+10h]
0x1800ab4aa  call    WPP_SF_
0x1800ab4af  xor     r9d, r9d; lpName
0x1800ab4b2  xor     r8d, r8d; bInitialState
0x1800ab4b5  xor     edx, edx; bManualReset
0x1800ab4b7  xor     ecx, ecx; lpEventAttributes
0x1800ab4b9  call    cs:__imp_CreateEventW
0x1800ab4bf  mov     rcx, [rdi+28h]; void *
0x1800ab4c3  mov     [rdi+28h], rax
0x1800ab4c7  xor     esi, esi
0x1800ab4c9  test    rcx, rcx
0x1800ab4cc  jz      short loc_1800AB4D3
0x1800ab4ce  call    ?CloseGPNotification@PolicyManager@@CAXPEAX@Z; PolicyManager::CloseGPNotification(void *)
0x1800ab4d3  cmp     [rdi+28h], rsi
0x1800ab4d7  jnz     short loc_1800AB514
0x1800ab4d9  call    cs:__imp_GetLastError
0x1800ab4df  mov     ebx, eax
0x1800ab4e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab4e8  cmp     rcx, r15
0x1800ab4eb  jz      short loc_1800AB50D
0x1800ab4ed  test    [rcx+1Ch], r14d
0x1800ab4f1  jz      short loc_1800AB50D
0x1800ab4f3  cmp     byte ptr [rcx+19h], 2
0x1800ab4f7  jb      short loc_1800AB50D
0x1800ab4f9  mov     edx, 0Bh
0x1800ab4fe  mov     r9d, ebx
0x1800ab501  mov     r8, r12
0x1800ab504  mov     rcx, [rcx+10h]
0x1800ab508  call    WPP_SF_d
0x1800ab50d  mov     eax, ebx
0x1800ab50f  jmp     loc_1800ABA66
0x1800ab514  xor     r8d, r8d; pcbe
0x1800ab517  mov     rdx, rdi; pv
0x1800ab51a  lea     rcx, ?PolicyChangedCallback@PolicyManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800ab521  call    cs:__imp_CreateThreadpoolWait
0x1800ab527  mov     rcx, [rdi+30h]; pwa
0x1800ab52b  mov     [rdi+30h], rax
0x1800ab52f  test    rcx, rcx
0x1800ab532  jz      short loc_1800AB53A
0x1800ab534  call    cs:__imp_CloseThreadpoolWait
0x1800ab53a  cmp     [rdi+30h], rsi
0x1800ab53e  jnz     short loc_1800AB567
0x1800ab540  call    cs:__imp_GetLastError
0x1800ab546  mov     ebx, eax
0x1800ab548  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab54f  cmp     rcx, r15
0x1800ab552  jz      short loc_1800AB50D
0x1800ab554  test    [rcx+1Ch], r14d
0x1800ab558  jz      short loc_1800AB50D
0x1800ab55a  cmp     byte ptr [rcx+19h], 2
0x1800ab55e  jb      short loc_1800AB50D
0x1800ab560  mov     edx, 0Ch
0x1800ab565  jmp     short loc_1800AB4FE
0x1800ab567  mov     [rbp+57h+hKey], rsi
0x1800ab56b  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800ab56f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800ab574  nop
0x1800ab575  lea     rcx, [rbp+57h+var_80]; void *
0x1800ab579  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800ab57e  nop
0x1800ab57f  lea     r9, [rbp+57h+var_80]
0x1800ab583  lea     r8, [rbp+57h+lpSubKey]
0x1800ab587  lea     rdx, [rbp+57h+hKey]
0x1800ab58b  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800ab590  mov     ebx, eax
0x1800ab592  test    eax, eax
0x1800ab594  jz      short loc_1800AB5F5
0x1800ab596  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab59d  cmp     rcx, r15
0x1800ab5a0  jz      short loc_1800AB5C2
0x1800ab5a2  test    [rcx+1Ch], r14d
0x1800ab5a6  jz      short loc_1800AB5C2
0x1800ab5a8  cmp     byte ptr [rcx+19h], 2
0x1800ab5ac  jb      short loc_1800AB5C2
0x1800ab5ae  mov     edx, 0Dh
0x1800ab5b3  mov     r9d, eax
0x1800ab5b6  mov     r8, r12
0x1800ab5b9  mov     rcx, [rcx+10h]
0x1800ab5bd  call    WPP_SF_d
0x1800ab5c2  lea     rax, byte_1800EC961
0x1800ab5c9  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800ab5cd  mov     qword ptr [rbp+57h+pExceptionObject+8], rsi
0x1800ab5d1  mov     [rbp+57h+var_50], rsi
0x1800ab5d5  mov     [rbp+57h+var_48], ebx
0x1800ab5d8  mov     [rbp+57h+var_44], 0FFFFFFFFFFFFFFFFh
0x1800ab5e0  mov     [rbp+57h+var_3C], sil
0x1800ab5e4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800ab5eb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800ab5ef  call    _CxxThrowException_0
0x1800ab5f5  mov     r8d, 9
0x1800ab5fb  lea     rdx, aPolicies; "\\Policies"
0x1800ab602  lea     rcx, [rbp+57h+lpSubKey]
0x1800ab606  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800ab60b  test    al, al
0x1800ab60d  jnz     short loc_1800AB66B
0x1800ab60f  mov     ebx, 0Eh
0x1800ab614  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab61b  cmp     rcx, r15
0x1800ab61e  jz      short loc_1800AB63D
0x1800ab620  test    [rcx+1Ch], r14d
0x1800ab624  jz      short loc_1800AB63D
0x1800ab626  cmp     byte ptr [rcx+19h], 2
0x1800ab62a  jb      short loc_1800AB63D
0x1800ab62c  mov     edx, ebx
0x1800ab62e  mov     r9d, ebx
0x1800ab631  mov     r8, r12
0x1800ab634  mov     rcx, [rcx+10h]
0x1800ab638  call    WPP_SF_d
0x1800ab63d  xorps   xmm0, xmm0
0x1800ab640  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800ab645  mov     [rbp+57h+var_50], rsi
0x1800ab649  mov     [rbp+57h+var_48], ebx
0x1800ab64c  mov     dword ptr [rbp+57h+var_44], 0FFFFFFFFh
0x1800ab653  mov     dword ptr [rbp+57h+var_44+4], 68h ; 'h'
0x1800ab65a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800ab661  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800ab665  call    _CxxThrowException_0
0x1800ab66b  mov     [rbp+57h+arg_0], rsi
0x1800ab66f  lea     rcx, [rbp+57h+arg_0]
0x1800ab673  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800ab678  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800ab67d  mov     r9d, 20019h; samDesired
0x1800ab683  xor     r8d, r8d; ulOptions
0x1800ab686  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800ab68a  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ab68e  call    cs:__imp_RegOpenKeyExW
0x1800ab694  mov     ebx, eax
0x1800ab696  cmp     [rbp+57h+arg_0], rsi
0x1800ab69a  jnz     loc_1800AB723
0x1800ab6a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab6a7  cmp     rcx, r15
0x1800ab6aa  jz      short loc_1800AB701
0x1800ab6ac  test    [rcx+1Ch], r14d
0x1800ab6b0  jz      short loc_1800AB6DC
0x1800ab6b2  cmp     byte ptr [rcx+19h], 1
0x1800ab6b6  jb      short loc_1800AB6DC
0x1800ab6b8  mov     edx, 0Fh
0x1800ab6bd  mov     rax, [rbp+57h+lpSubKey]
0x1800ab6c1  mov     [rsp+0E0h+phkResult], rax
0x1800ab6c6  mov     r9d, ebx
0x1800ab6c9  mov     r8, r12
0x1800ab6cc  mov     rcx, [rcx+10h]
0x1800ab6d0  call    WPP_SF_dS
0x1800ab6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab6dc  cmp     rcx, r15
0x1800ab6df  jz      short loc_1800AB701
0x1800ab6e1  test    [rcx+1Ch], r14d
0x1800ab6e5  jz      short loc_1800AB701
0x1800ab6e7  cmp     byte ptr [rcx+19h], 2
0x1800ab6eb  jb      short loc_1800AB701
0x1800ab6ed  mov     edx, 10h
0x1800ab6f2  mov     r9d, ebx
0x1800ab6f5  mov     r8, r12
0x1800ab6f8  mov     rcx, [rcx+10h]
0x1800ab6fc  call    WPP_SF_d
0x1800ab701  lea     rcx, [rbp+57h+arg_0]
0x1800ab705  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800ab70a  nop
0x1800ab70b  lea     rcx, [rbp+57h+var_80]; void *
0x1800ab70f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ab714  nop
0x1800ab715  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800ab719  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ab71e  jmp     loc_1800AB50D
0x1800ab723  lea     rcx, [rbp+57h+arg_0]
0x1800ab727  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800ab72c  nop
0x1800ab72d  lea     rcx, [rbp+57h+var_80]; void *
0x1800ab731  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ab736  nop
0x1800ab737  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800ab73b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800ab740  xor     r8d, r8d; pftTimeout
0x1800ab743  mov     rdx, [rdi+28h]; h
0x1800ab747  mov     rcx, [rdi+30h]; pwa
0x1800ab74b  call    cs:__imp_SetThreadpoolWait
0x1800ab751  mov     edx, 1; bMachine
0x1800ab756  mov     rcx, [rdi+28h]; hEvent
0x1800ab75a  call    cs:__imp_RegisterGPNotification
0x1800ab760  test    eax, eax
0x1800ab762  jnz     short loc_1800AB79F
0x1800ab764  call    cs:__imp_GetLastError
0x1800ab76a  mov     ebx, eax
0x1800ab76c  cmp     eax, 1
0x1800ab76f  jz      short loc_1800AB79F
0x1800ab771  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab778  cmp     rcx, r15
0x1800ab77b  jz      loc_1800AB50D
0x1800ab781  test    [rcx+1Ch], r14d
0x1800ab785  jz      loc_1800AB50D
0x1800ab78b  cmp     byte ptr [rcx+19h], 2
0x1800ab78f  jb      loc_1800AB50D
0x1800ab795  mov     edx, 11h
0x1800ab79a  jmp     loc_1800AB4FE
0x1800ab79f  mov     rbx, cs:WNF_ENTR_APPHVSI_POLICY_VALUE_CHANGED
0x1800ab7a6  lea     rcx, [rdi+18h]
0x1800ab7aa  call    ??$replace@U?$handle_traits@PEAU_WNF_USER_SUBSCRIPTION@@$$A6AJPEAU1@@Z$1?RtlUnsubscribeWnfNotificationWaitForCompletion@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAU_WNF_USER_SUBSCRIPTION@@AEAV?$unique_any@U?$handle_traits@PEAU_WNF_USER_SUBSCRIPTION@@$$A6AJPEAU1@@Z$1?RtlUnsubscribeWnfNotificationWaitForCompletion@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(tlx::unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>> &)
0x1800ab7af  mov     [rsp+0E0h+var_A8], esi
0x1800ab7b3  mov     [rsp+0E0h+var_B0], esi
0x1800ab7b7  mov     [rsp+0E0h+var_B8], rsi
0x1800ab7bc  mov     [rsp+0E0h+phkResult], rdi
0x1800ab7c1  lea     r9, ?WnfNotificationCallback@PolicyManager@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; PolicyManager::WnfNotificationCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800ab7c8  xor     r8d, r8d
0x1800ab7cb  mov     rdx, rbx
0x1800ab7ce  mov     rcx, rax
0x1800ab7d1  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800ab7d7  mov     ebx, eax
0x1800ab7d9  test    eax, eax
0x1800ab7db  jz      short loc_1800AB841
0x1800ab7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab7e4  cmp     rcx, r15
0x1800ab7e7  jz      short loc_1800AB809
0x1800ab7e9  test    [rcx+1Ch], r14d
0x1800ab7ed  jz      short loc_1800AB809
0x1800ab7ef  cmp     byte ptr [rcx+19h], 2
0x1800ab7f3  jb      short loc_1800AB809
0x1800ab7f5  mov     edx, 12h
0x1800ab7fa  mov     r9d, eax
0x1800ab7fd  mov     r8, r12
0x1800ab800  mov     rcx, [rcx+10h]
0x1800ab804  call    WPP_SF_d
0x1800ab809  mov     ecx, ebx; Status
0x1800ab80b  call    cs:__imp_RtlNtStatusToDosError
0x1800ab811  mov     ebx, eax
0x1800ab813  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab81a  cmp     rcx, r15
0x1800ab81d  jz      loc_1800AB50D
0x1800ab823  test    [rcx+1Ch], r14d
0x1800ab827  jz      loc_1800AB50D
0x1800ab82d  cmp     byte ptr [rcx+19h], 2
0x1800ab831  jb      loc_1800AB50D
0x1800ab837  mov     edx, 13h
0x1800ab83c  jmp     loc_1800AB4FE
0x1800ab841  mov     rbx, cs:WNF_DCSP_POLICIES_UPDATED
0x1800ab848  lea     rcx, [rdi+20h]
0x1800ab84c  call    ??$replace@U?$handle_traits@PEAU_WNF_USER_SUBSCRIPTION@@$$A6AJPEAU1@@Z$1?RtlUnsubscribeWnfNotificationWaitForCompletion@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAU_WNF_USER_SUBSCRIPTION@@AEAV?$unique_any@U?$handle_traits@PEAU_WNF_USER_SUBSCRIPTION@@$$A6AJPEAU1@@Z$1?RtlUnsubscribeWnfNotificationWaitForCompletion@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(tlx::unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>> &)
0x1800ab851  mov     [rsp+0E0h+var_A8], esi
0x1800ab855  mov     [rsp+0E0h+var_B0], esi
0x1800ab859  mov     [rsp+0E0h+var_B8], rsi
0x1800ab85e  mov     [rsp+0E0h+phkResult], rdi
0x1800ab863  lea     r9, ?WnfNotificationCallback@PolicyManager@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; PolicyManager::WnfNotificationCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800ab86a  xor     r8d, r8d
0x1800ab86d  mov     rdx, rbx
0x1800ab870  mov     rcx, rax
0x1800ab873  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800ab879  mov     ebx, eax
0x1800ab87b  test    eax, eax
0x1800ab87d  jz      short loc_1800AB8E3
0x1800ab87f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab886  cmp     rcx, r15
0x1800ab889  jz      short loc_1800AB8AB
0x1800ab88b  test    [rcx+1Ch], r14d
0x1800ab88f  jz      short loc_1800AB8AB
0x1800ab891  cmp     byte ptr [rcx+19h], 2
0x1800ab895  jb      short loc_1800AB8AB
0x1800ab897  mov     edx, 14h
0x1800ab89c  mov     r9d, eax
0x1800ab89f  mov     r8, r12
0x1800ab8a2  mov     rcx, [rcx+10h]
0x1800ab8a6  call    WPP_SF_d
0x1800ab8ab  mov     ecx, ebx; Status
0x1800ab8ad  call    cs:__imp_RtlNtStatusToDosError
0x1800ab8b3  mov     ebx, eax
0x1800ab8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab8bc  cmp     rcx, r15
0x1800ab8bf  jz      loc_1800AB50D
0x1800ab8c5  test    [rcx+1Ch], r14d
0x1800ab8c9  jz      loc_1800AB50D
0x1800ab8cf  cmp     byte ptr [rcx+19h], 2
0x1800ab8d3  jb      loc_1800AB50D
0x1800ab8d9  mov     edx, 15h
0x1800ab8de  jmp     loc_1800AB4FE
0x1800ab8e3  mov     [rbp+57h+arg_8], rsi
0x1800ab8e7  lea     rcx, [rbp+57h+arg_8]
0x1800ab8eb  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800ab8f0  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800ab8f5  mov     r9d, 20119h; samDesired
0x1800ab8fb  xor     r8d, r8d; ulOptions
  ... truncated ...
```
