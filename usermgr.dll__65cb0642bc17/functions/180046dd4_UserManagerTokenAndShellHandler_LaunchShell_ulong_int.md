# UserManagerTokenAndShellHandler::LaunchShell(ulong,int)

- ea: `0x180046dd4`
- end: `0x180047323`
- name: `?LaunchShell@UserManagerTokenAndShellHandler@@QEAAJKH@Z`
- size: `1359`
- prototype: `__int64 __fastcall(UserManagerTokenAndShellHandler *__hidden this, unsigned int, int)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180046338`
- `0x1800b68e4`
- `0x1800b71f0`

## callees

- `0x180011490`
- `0x180012890`
- `0x180026ba0`
- `0x18003320c`
- `0x1800347a0`
- `0x180036248`
- `0x18003e290`
- `0x18004254c`
- `0x180046dd4`
- `0x1800624bc`
- `0x180063e64`
- `0x180063fe8`
- `0x180075590`
- `0x1800b759c`
- `0x1800b75cc`
- `0x1800de450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180047042`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180047042`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800471e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800471e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047140`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047140`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046e90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004708f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047157`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046e90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004708f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047157`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046f8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046f8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046f78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047186`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047196`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047186`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047196`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046e49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180047244`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046e49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180047244`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800471db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800471db`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800471bf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800471bf`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800470c0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800470c0`
- `ntdll!NtSetInformationProcess` at `0x180047004`
- `ntdll!NtSetInformationProcess` at `0x180047004`
- `ntdll!RtlNtStatusToDosError` at `0x180046f3b`
- `ntdll!RtlNtStatusToDosError` at `0x180046f3b`
- `ntdll!RtlPublishWnfStateData` at `0x180046f33`
- `ntdll!RtlPublishWnfStateData` at `0x180046f33`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180046f59`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180046f69`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180046f59`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180046f69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserManagerTokenAndShellHandler::LaunchShell(
        UserManagerTokenAndShellHandler *this,
        unsigned int a2,
        int a3)
{
  unsigned int v3; // r12d
  UserManagerTokenAndShellHandler *v4; // r15
  signed int UserToken; // esi
  struct _PROCESS_INFORMATION *v6; // r13
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 *v9; // rax
  _QWORD *v10; // r11
  int v11; // ebx
  UserManagerTokenAndShellHandler *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  NTSTATUS v16; // eax
  __int64 v17; // rcx
  HANDLE ProcessHeap; // rax
  struct _PROCESS_INFORMATION *v19; // rax
  __int64 v20; // rcx
  RTL_SRWLOCK *v21; // r12
  __int64 v22; // rbx
  HANDLE CurrentProcess; // rdi
  void *v24; // rbx
  HANDLE v25; // rax
  const struct _tlgProvider_t *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  const struct _tlgProvider_t *v29; // rbx
  unsigned int *dwMilliseconds; // [rsp+20h] [rbp-138h]
  char v32; // [rsp+40h] [rbp-118h]
  unsigned int v34; // [rsp+50h] [rbp-108h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-100h]
  int v36; // [rsp+60h] [rbp-F8h] BYREF
  struct _PROCESS_INFORMATION *v37; // [rsp+68h] [rbp-F0h] BYREF
  _QWORD ProcessInformation[2]; // [rsp+70h] [rbp-E8h] BYREF
  __int64 v39; // [rsp+80h] [rbp-D8h] BYREF
  unsigned int v40; // [rsp+88h] [rbp-D0h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp-C8h] BYREF
  ULONGLONG TickCount64; // [rsp+98h] [rbp-C0h]
  char v43[16]; // [rsp+A0h] [rbp-B8h] BYREF
  _QWORD *v44; // [rsp+D0h] [rbp-88h]
  __int64 v45; // [rsp+D8h] [rbp-80h]
  int *v46; // [rsp+E0h] [rbp-78h]
  __int64 v47; // [rsp+E8h] [rbp-70h]
  struct _PROCESS_INFORMATION **v48; // [rsp+F0h] [rbp-68h]
  __int64 v49; // [rsp+F8h] [rbp-60h]
  __int64 *v50; // [rsp+100h] [rbp-58h]
  __int64 v51; // [rsp+108h] [rbp-50h]

  v3 = a2;
  v35 = a2;
  v4 = this;
  v39 = (__int64)this;
  v34 = a2;
  v36 = a3;
  UserToken = 0;
  v6 = 0;
  v32 = 0;
  TargetHandle = (HANDLE)-1LL;
  v7 = **((_QWORD **)this + 10);
  v40 = a2;
  TickCount64 = GetTickCount64();
  if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 0x20) != 0 )
    McTemplateU0q_EventWriteTransfer(v8, LaunchShell_Start, v3);
  if ( !*((_QWORD *)v4 + 16) )
    goto LABEL_16;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShellInfraHostLock>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)v4 + 9);
    v32 = 1;
  }
  v9 = (__int64 *)std::_Tree<std::_Tmap_traits<unsigned int,Windows::System::Internal::Implementation::SignOutProgress *,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(
                    (char *)v4 + 80,
                    &v37,
                    &v34);
  v7 = *v9;
  if ( *v10 != *v9 )
  {
    LODWORD(ProcessInformation[0]) = *(_DWORD *)(*(_QWORD *)(v7 + 40) + 44LL);
    dwMilliseconds = &v40;
    v16 = RtlPublishWnfStateData(WNF_UMGR_SIHOST_READY, 0, ProcessInformation, 4);
    UserToken = RtlNtStatusToDosError(v16);
    if ( UserToken )
      goto LABEL_8;
LABEL_16:
    if ( *((_BYTE *)v4 + 159) == 1 )
    {
      if ( v3 != (unsigned int)RtlGetCurrentServiceSessionId(v8) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v17);
      if ( v3 != (unsigned int)RtlGetCurrentServiceSessionId(v17) )
        goto LABEL_8;
      ProcessHeap = GetProcessHeap();
      v19 = (struct _PROCESS_INFORMATION *)HeapAlloc(ProcessHeap, 8u, 0x20u);
      v6 = v19;
      v37 = v19;
      if ( !v19 )
      {
        UserToken = 8;
        goto LABEL_8;
      }
      v19[1].hProcess = (HANDLE)-1LL;
      if ( *((_BYTE *)v4 + 152) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v20);
      if ( *((_BYTE *)v4 + 156) )
      {
        UserToken = LaunchProcessAsUser(*((unsigned __int16 **)v4 + 15), *((HANDLE *)v4 + 3), v6);
        if ( UserToken )
          goto LABEL_8;
        if ( *((_BYTE *)v4 + 162) == 1 )
        {
          LODWORD(ProcessInformation[0]) = 1;
          NtSetInformationProcess(v6->hProcess, ProcessBreakOnTermination, ProcessInformation, 4u);
        }
      }
      else
      {
        if ( *((_BYTE *)v4 + 157) )
        {
          UserToken = LaunchProcessAsUser(*((unsigned __int16 **)v4 + 15), *((HANDLE *)v4 + 6), v6);
        }
        else
        {
          UserToken = UserManagerTokenAndShellHandler::WaitForFirstUserToken(v4);
          if ( UserToken )
            goto LABEL_8;
          AcquireSRWLockShared((PSRWLOCK)v4 + 4);
          ProcessInformation[0] = (char *)v4 + 32;
          UserToken = LaunchProcessAsUser(*((unsigned __int16 **)v4 + 15), *((HANDLE *)v4 + 5), v6);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(ProcessInformation);
        }
        if ( UserToken )
          goto LABEL_8;
      }
      v11 = a3;
      UserManagerTokenAndShellHandler::RemoveAndFreeShellMapEntry(v4, v3, a3);
      v21 = (RTL_SRWLOCK *)((char *)v4 + 96);
      AcquireSRWLockExclusive((PSRWLOCK)v4 + 12);
      if ( !*((_BYTE *)v4 + 177)
        || RegisterWaitForSingleObject(&v6[1].hProcess, v6->hProcess, RestartShellProcess, 0, 0xFFFFFFFF, 8u) )
      {
        try
        {
          LODWORD(ProcessInformation[0]) = v35;
          ProcessInformation[1] = v6;
          std::_Tree<std::_Tmap_traits<unsigned long,_SHELL_MAP_ENTRY *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,_SHELL_MAP_ENTRY *>>,0>>::insert<std::pair<unsigned long,_SHELL_MAP_ENTRY *>>(
            (char *)v4 + 104,
            v43,
            ProcessInformation);
          v6 = 0;
          v37 = 0;
        }
        catch ( std::bad_alloc )
        {
          LODWORD(ProcessInformation[0]) = 8;
          v21 = (RTL_SRWLOCK *)((char *)v4 + 96);
          UserToken = 8;
          v6 = v37;
          v4 = (UserManagerTokenAndShellHandler *)v39;
          v35 = v34;
          v11 = v36;
        }
      }
      else
      {
        UserToken = GetLastError();
      }
    }
    else
    {
      UserToken = WaitForSingleObject(*(HANDLE *)(*(_QWORD *)(v7 + 40) + 24LL), *((_DWORD *)v4 + 41));
      if ( UserToken )
        goto LABEL_8;
      v21 = (RTL_SRWLOCK *)((char *)v4 + 96);
      AcquireSRWLockExclusive((PSRWLOCK)v4 + 12);
      std::_Tree<std::_Tmap_traits<unsigned int,Windows::System::Internal::Implementation::SignOutProgress *,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(
        (char *)v4 + 104,
        &v39,
        &v34);
      v22 = v39;
      if ( v39 == *((_QWORD *)v4 + 13) )
      {
        UserToken = 0;
      }
      else
      {
        CurrentProcess = GetCurrentProcess();
        v24 = **(void ***)(v22 + 40);
        v25 = GetCurrentProcess();
        if ( DuplicateHandle(v25, v24, CurrentProcess, &TargetHandle, 0, 0, 2u) )
          CloseHandle(TargetHandle);
        else
          UserToken = GetLastError();
      }
      v11 = a3;
    }
    ReleaseSRWLockExclusive(v21);
    v3 = v35;
    goto LABEL_9;
  }
  UserToken = 1168;
LABEL_8:
  v11 = a3;
LABEL_9:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShellInfraHostLock>::GetImpl'::`2'::impl)
    && v32 )
  {
    ReleaseSRWLockExclusive((PSRWLOCK)v4 + 9);
  }
  UserManagerTokenAndShellHandler::FreeShellMapEntry(v12, (struct _SHELL_MAP_ENTRY *)v6, v11);
  if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 0x20) != 0 )
  {
    if ( UserToken > 0 )
      v15 = (unsigned __int16)UserToken | 0x80070000;
    else
      v15 = (unsigned int)UserToken;
    McTemplateU0qd_EventWriteTransfer(v14, v13, v3, v15, dwMilliseconds);
  }
  v26 = UserMgrUserModelTelemetry::Provider();
  v29 = v26;
  if ( *(_DWORD *)v26 > 5u && (unsigned __int8)tlgKeywordOn(v26, 0x400000000000LL, v27, v28) )
  {
    v39 = 0x1000000;
    v37 = (struct _PROCESS_INFORMATION *)(GetTickCount64() - TickCount64);
    v36 = UserToken;
    LODWORD(ProcessInformation[0]) = v3;
    v50 = &v39;
    v51 = 8;
    v48 = &v37;
    v49 = 8;
    v46 = &v36;
    v47 = 4;
    v44 = ProcessInformation;
    v45 = 4;
    tlgWriteTransfer_EventWriteTransfer(v29, &byte_18012AF5F, 0, 0);
  }
  if ( UserToken > 0 )
    return (unsigned __int16)UserToken | 0x80070000;
  return (unsigned int)UserToken;
}

```

## disassembly

```asm
0x180046dd4  push    rbx
0x180046dd6  push    rsi
0x180046dd7  push    rdi
0x180046dd8  push    r12
0x180046dda  push    r13
0x180046ddc  push    r14
0x180046dde  push    r15
0x180046de0  sub     rsp, 120h
0x180046de7  mov     rax, cs:__security_cookie
0x180046dee  xor     rax, rsp
0x180046df1  mov     [rsp+158h+var_48], rax
0x180046df9  mov     eax, r8d
0x180046dfc  mov     [rsp+158h+var_110], eax
0x180046e00  mov     r12d, edx
0x180046e03  mov     [rsp+158h+var_100], edx
0x180046e07  mov     r15, rcx
0x180046e0a  mov     [rsp+158h+var_D8], rcx
0x180046e12  mov     [rsp+158h+var_108], edx
0x180046e16  mov     [rsp+158h+var_F8], eax
0x180046e1a  xor     r14d, r14d
0x180046e1d  mov     esi, r14d
0x180046e20  mov     r13d, r14d
0x180046e23  mov     [rsp+158h+var_118], r14b
0x180046e28  mov     [rsp+158h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x180046e34  mov     rbx, [rcx+50h]
0x180046e38  mov     rbx, [rbx]
0x180046e3b  mov     rdi, cs:WNF_UMGR_SIHOST_READY
0x180046e42  mov     [rsp+158h+var_D0], edx
0x180046e49  call    cs:__imp_GetTickCount64
0x180046e4f  mov     [rsp+158h+var_C0], rax
0x180046e57  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 20h
0x180046e5e  jz      short loc_180046E6F
0x180046e60  mov     r8d, r12d
0x180046e63  lea     rdx, LaunchShell_Start
0x180046e6a  call    McTemplateU0q_EventWriteTransfer
0x180046e6f  cmp     [r15+80h], r14
0x180046e76  jz      loc_180046F4B
0x180046e7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock> `wil::Feature<__WilFeatureTraits_Feature_ShellInfraHostLock>::GetImpl(void)'::`2'::impl
0x180046e83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock>::__private_IsEnabled(void)
0x180046e88  test    al, al
0x180046e8a  jz      short loc_180046E9B
0x180046e8c  lea     rcx, [r15+48h]; SRWLock
0x180046e90  call    cs:__imp_AcquireSRWLockExclusive
0x180046e96  mov     [rsp+158h+var_118], 1
0x180046e9b  lea     r11, [r15+50h]
0x180046e9f  lea     r8, [rsp+158h+var_108]
0x180046ea4  lea     rdx, [rsp+158h+var_F0]
0x180046ea9  mov     rcx, r11
0x180046eac  call    ?find@?$_Tree@V?$_Tmap_traits@IPEAVSignOutProgress@Implementation@Internal@System@Windows@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,Windows::System::Internal::Implementation::SignOutProgress *,std::less<uint>,std::allocator<std::pair<uint const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(uint const &)
0x180046eb1  mov     rbx, [rax]
0x180046eb4  cmp     [r11], rbx
0x180046eb7  jnz     short loc_180046F0B
0x180046eb9  mov     esi, 490h
0x180046ebe  mov     ebx, [rsp+158h+var_110]
0x180046ec2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock> `wil::Feature<__WilFeatureTraits_Feature_ShellInfraHostLock>::GetImpl(void)'::`2'::impl
0x180046ec9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock>::__private_IsEnabled(void)
0x180046ece  test    al, al
0x180046ed0  jz      short loc_180046EE3
0x180046ed2  cmp     [rsp+158h+var_118], r14b
0x180046ed7  jz      short loc_180046EE3
0x180046ed9  lea     rcx, [r15+48h]; SRWLock
0x180046edd  call    cs:__imp_ReleaseSRWLockExclusive
0x180046ee3  mov     r8d, ebx; int
0x180046ee6  mov     rdx, r13; struct _SHELL_MAP_ENTRY *
0x180046ee9  call    ?FreeShellMapEntry@UserManagerTokenAndShellHandler@@AEAAXPEAU_SHELL_MAP_ENTRY@@H@Z; UserManagerTokenAndShellHandler::FreeShellMapEntry(_SHELL_MAP_ENTRY *,int)
0x180046eee  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 20h
0x180046ef5  jz      loc_18004720B
0x180046efb  test    esi, esi
0x180046efd  jg      loc_1800471F8
0x180046f03  mov     r9d, esi
0x180046f06  jmp     loc_180047203
0x180046f0b  mov     rax, [rbx+28h]
0x180046f0f  mov     ecx, [rax+2Ch]
0x180046f12  mov     dword ptr [rsp+158h+ProcessInformation], ecx
0x180046f16  lea     rax, [rsp+158h+var_D0]
0x180046f1e  mov     qword ptr [rsp+158h+dwMilliseconds], rax
0x180046f23  mov     r9d, 4
0x180046f29  lea     r8, [rsp+158h+ProcessInformation]
0x180046f2e  xor     edx, edx
0x180046f30  mov     rcx, rdi
0x180046f33  call    cs:__imp_RtlPublishWnfStateData
0x180046f39  mov     ecx, eax; Status
0x180046f3b  call    cs:__imp_RtlNtStatusToDosError
0x180046f41  mov     esi, eax
0x180046f43  test    eax, eax
0x180046f45  jnz     loc_180046EBE
0x180046f4b  cmp     byte ptr [r15+9Fh], 1
0x180046f53  jnz     loc_180047131
0x180046f59  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180046f5f  cmp     r12d, eax
0x180046f62  jz      short loc_180046F69
0x180046f64  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046f69  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180046f6f  cmp     r12d, eax
0x180046f72  jnz     loc_180046EBE
0x180046f78  call    cs:__imp_GetProcessHeap
0x180046f7e  mov     rcx, rax; hHeap
0x180046f81  mov     edx, 8; dwFlags
0x180046f86  lea     r8d, [rdx+18h]; dwBytes
0x180046f8a  call    cs:__imp_HeapAlloc
0x180046f90  mov     r13, rax
0x180046f93  mov     [rsp+158h+var_F0], rax
0x180046f98  test    rax, rax
0x180046f9b  jnz     short loc_180046FA5
0x180046f9d  lea     esi, [rax+8]
0x180046fa0  jmp     loc_180046EBE
0x180046fa5  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180046fad  cmp     [r15+98h], r14b
0x180046fb4  jz      short loc_180046FBB
0x180046fb6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046fbb  cmp     [r15+9Ch], r14b
0x180046fc2  jz      short loc_18004700C
0x180046fc4  mov     r8, r13; lpProcessInformation
0x180046fc7  mov     rdx, [r15+18h]; hToken
0x180046fcb  mov     rcx, [r15+78h]; unsigned __int16 *
0x180046fcf  call    ?LaunchProcessAsUser@@YAKPEAGPEAXPEAU_PROCESS_INFORMATION@@@Z; LaunchProcessAsUser(ushort *,void *,_PROCESS_INFORMATION *)
0x180046fd4  mov     esi, eax
0x180046fd6  test    eax, eax
0x180046fd8  jnz     loc_180046EBE
0x180046fde  cmp     byte ptr [r15+0A2h], 1
0x180046fe6  jnz     loc_180047071
0x180046fec  mov     dword ptr [rsp+158h+ProcessInformation], 1
0x180046ff4  lea     r9d, [rax+4]; ProcessInformationLength
0x180046ff8  lea     r8, [rsp+158h+ProcessInformation]; ProcessInformation
0x180046ffd  lea     edx, [rax+1Dh]; ProcessInformationClass
0x180047000  mov     rcx, [r13+0]; ProcessHandle
0x180047004  call    cs:__imp_NtSetInformationProcess
0x18004700a  jmp     short loc_180047071
0x18004700c  cmp     [r15+9Dh], r14b
0x180047013  jz      short loc_180047029
0x180047015  mov     r8, r13; lpProcessInformation
0x180047018  mov     rdx, [r15+30h]; hToken
0x18004701c  mov     rcx, [r15+78h]; unsigned __int16 *
0x180047020  call    ?LaunchProcessAsUser@@YAKPEAGPEAXPEAU_PROCESS_INFORMATION@@@Z; LaunchProcessAsUser(ushort *,void *,_PROCESS_INFORMATION *)
0x180047025  mov     esi, eax
0x180047027  jmp     short loc_180047069
0x180047029  mov     rcx, r15; this
0x18004702c  call    ?WaitForFirstUserToken@UserManagerTokenAndShellHandler@@AEAAKXZ; UserManagerTokenAndShellHandler::WaitForFirstUserToken(void)
0x180047031  mov     esi, eax
0x180047033  test    eax, eax
0x180047035  jnz     loc_180046EBE
0x18004703b  lea     rbx, [r15+20h]
0x18004703f  mov     rcx, rbx; SRWLock
0x180047042  call    cs:__imp_AcquireSRWLockShared
0x180047048  mov     [rsp+158h+ProcessInformation], rbx
0x18004704d  mov     r8, r13; lpProcessInformation
0x180047050  mov     rdx, [r15+28h]; hToken
0x180047054  mov     rcx, [r15+78h]; unsigned __int16 *
0x180047058  call    ?LaunchProcessAsUser@@YAKPEAGPEAXPEAU_PROCESS_INFORMATION@@@Z; LaunchProcessAsUser(ushort *,void *,_PROCESS_INFORMATION *)
0x18004705d  mov     esi, eax
0x18004705f  lea     rcx, [rsp+158h+ProcessInformation]
0x180047064  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180047069  test    esi, esi
0x18004706b  jnz     loc_180046EBE
0x180047071  mov     ebx, [rsp+158h+var_110]
0x180047075  mov     r8d, ebx; int
0x180047078  mov     edx, r12d; unsigned int
0x18004707b  mov     rcx, r15; this
0x18004707e  call    ?RemoveAndFreeShellMapEntry@UserManagerTokenAndShellHandler@@AEAAXKH@Z; UserManagerTokenAndShellHandler::RemoveAndFreeShellMapEntry(ulong,int)
0x180047083  lea     r12, [r15+60h]
0x180047087  mov     qword ptr [rsp+158h+var_110], r12
0x18004708c  mov     rcx, r12; SRWLock
0x18004708f  call    cs:__imp_AcquireSRWLockExclusive
0x180047095  cmp     [r15+0B1h], r14b
0x18004709c  jz      short loc_1800470D7
0x18004709e  mov     [rsp+158h+dwFlags], 8; dwFlags
0x1800470a6  mov     [rsp+158h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800470ae  xor     r9d, r9d; Context
0x1800470b1  lea     r8, ?RestartShellProcess@@YAXPEAXE@Z; Callback
0x1800470b8  mov     rdx, [r13+0]; hObject
0x1800470bc  lea     rcx, [r13+18h]; phNewWaitObject
0x1800470c0  call    cs:__imp_RegisterWaitForSingleObject
0x1800470c6  test    eax, eax
0x1800470c8  jnz     short loc_1800470D7
0x1800470ca  call    cs:__imp_GetLastError
0x1800470d0  mov     esi, eax
0x1800470d2  jmp     loc_1800471E5
0x1800470d7  mov     eax, [rsp+158h+var_100]
0x1800470db  mov     dword ptr [rsp+158h+ProcessInformation], eax
0x1800470df  mov     [rsp+158h+var_E0], r13
0x1800470e4  lea     rcx, [r15+68h]
0x1800470e8  lea     r8, [rsp+158h+ProcessInformation]
0x1800470ed  lea     rdx, [rsp+158h+var_B8]
0x1800470f5  call    ??$insert@U?$pair@KPEAU_SHELL_MAP_ENTRY@@@std@@@?$_Tree@V?$_Tmap_traits@KPEAU_SHELL_MAP_ENTRY@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_SHELL_MAP_ENTRY@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_SHELL_MAP_ENTRY@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KPEAU_SHELL_MAP_ENTRY@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,_SHELL_MAP_ENTRY *,std::less<ulong>,std::allocator<std::pair<ulong const,_SHELL_MAP_ENTRY *>>,0>>::insert<std::pair<ulong,_SHELL_MAP_ENTRY *>>(std::pair<ulong,_SHELL_MAP_ENTRY *> &&)
0x1800470fa  mov     r13, r14
0x1800470fd  mov     [rsp+158h+var_F0], r14
0x180047102  jmp     loc_1800471E5
0x180047107  mov     r12, qword ptr [rsp+158h+var_110]
0x18004710c  xor     r14d, r14d
0x18004710f  mov     esi, dword ptr [rsp+158h+ProcessInformation]
0x180047113  mov     r13, [rsp+158h+var_F0]
0x180047118  mov     r15, [rsp+158h+var_D8]
0x180047120  mov     eax, [rsp+158h+var_108]
0x180047124  mov     [rsp+158h+var_100], eax
0x180047128  mov     ebx, [rsp+158h+var_F8]
0x18004712c  jmp     loc_1800471E5
0x180047131  mov     rcx, [rbx+28h]
0x180047135  mov     edx, [r15+0A4h]; dwMilliseconds
0x18004713c  mov     rcx, [rcx+18h]; hHandle
0x180047140  call    cs:__imp_WaitForSingleObject
0x180047146  mov     esi, eax
0x180047148  test    eax, eax
0x18004714a  jnz     loc_180046EBE
0x180047150  lea     r12, [r15+60h]
0x180047154  mov     rcx, r12; SRWLock
0x180047157  call    cs:__imp_AcquireSRWLockExclusive
0x18004715d  lea     r8, [rsp+158h+var_108]
0x180047162  lea     rdx, [rsp+158h+var_D8]
0x18004716a  lea     rcx, [r15+68h]
0x18004716e  call    ?find@?$_Tree@V?$_Tmap_traits@IPEAVSignOutProgress@Implementation@Internal@System@Windows@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,Windows::System::Internal::Implementation::SignOutProgress *,std::less<uint>,std::allocator<std::pair<uint const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(uint const &)
0x180047173  mov     rbx, [rsp+158h+var_D8]
0x18004717b  cmp     rbx, [r15+68h]
0x18004717f  jnz     short loc_180047186
0x180047181  mov     esi, r14d
0x180047184  jmp     short loc_1800471E1
0x180047186  call    cs:__imp_GetCurrentProcess
0x18004718c  mov     rdi, rax
0x18004718f  mov     rcx, [rbx+28h]
0x180047193  mov     rbx, [rcx]
0x180047196  call    cs:__imp_GetCurrentProcess
0x18004719c  mov     [rsp+158h+dwOptions], 2; dwOptions
0x1800471a4  mov     [rsp+158h+dwFlags], r14d; bInheritHandle
0x1800471a9  mov     [rsp+158h+dwMilliseconds], r14d; dwDesiredAccess
0x1800471ae  lea     r9, [rsp+158h+TargetHandle]; lpTargetHandle
0x1800471b6  mov     r8, rdi; hTargetProcessHandle
0x1800471b9  mov     rdx, rbx; hSourceHandle
0x1800471bc  mov     rcx, rax; hSourceProcessHandle
0x1800471bf  call    cs:__imp_DuplicateHandle
0x1800471c5  test    eax, eax
0x1800471c7  jnz     short loc_1800471D3
0x1800471c9  call    cs:__imp_GetLastError
0x1800471cf  mov     esi, eax
0x1800471d1  jmp     short loc_1800471E1
0x1800471d3  mov     rcx, [rsp+158h+TargetHandle]; hObject
0x1800471db  call    cs:__imp_CloseHandle
0x1800471e1  mov     ebx, [rsp+158h+var_110]
0x1800471e5  mov     rcx, r12; SRWLock
0x1800471e8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800471ee  mov     r12d, [rsp+158h+var_100]
0x1800471f3  jmp     loc_180046EC2
0x1800471f8  movzx   r9d, si
0x1800471fc  or      r9d, 80070000h
0x180047203  mov     r8d, r12d
0x180047206  call    McTemplateU0qd_EventWriteTransfer
0x18004720b  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180047210  mov     rbx, rax
0x180047213  mov     ecx, [rax]
0x180047215  cmp     ecx, 5
0x180047218  jbe     loc_1800472F1
0x18004721e  mov     rdx, 400000000000h
0x180047228  mov     rcx, rax
0x18004722b  call    _tlgKeywordOn
0x180047230  test    al, al
0x180047232  jz      loc_1800472F1
0x180047238  mov     [rsp+158h+var_D8], 1000000h
0x180047244  call    cs:__imp_GetTickCount64
0x18004724a  sub     rax, [rsp+158h+var_C0]
0x180047252  mov     [rsp+158h+var_F0], rax
0x180047257  mov     [rsp+158h+var_F8], esi
0x18004725b  mov     dword ptr [rsp+158h+ProcessInformation], r12d
0x180047260  lea     rax, [rsp+158h+var_D8]
0x180047268  mov     [rsp+158h+var_58], rax
0x180047270  mov     [rsp+158h+var_50], 8
0x18004727c  lea     rax, [rsp+158h+var_F0]
0x180047281  mov     [rsp+158h+var_68], rax
0x180047289  mov     [rsp+158h+var_60], 8
0x180047295  lea     rax, [rsp+158h+var_F8]
0x18004729a  mov     [rsp+158h+var_78], rax
0x1800472a2  mov     [rsp+158h+var_70], 4
0x1800472ae  lea     rax, [rsp+158h+ProcessInformation]
0x1800472b3  mov     [rsp+158h+var_88], rax
0x1800472bb  mov     [rsp+158h+var_80], 4
0x1800472c7  lea     rax, [rsp+158h+var_A8]
0x1800472cf  mov     qword ptr [rsp+158h+dwFlags], rax
0x1800472d4  mov     [rsp+158h+dwMilliseconds], 6
0x1800472dc  xor     r9d, r9d
0x1800472df  xor     r8d, r8d
0x1800472e2  lea     rdx, byte_18012AF5F
0x1800472e9  mov     rcx, rbx
0x1800472ec  call    _tlgWriteTransfer_EventWriteTransfer
0x1800472f1  test    esi, esi
0x1800472f3  jle     short loc_1800472FE
0x1800472f5  movzx   esi, si
0x1800472f8  or      esi, 80070000h
0x1800472fe  mov     eax, esi
0x180047300  mov     rcx, [rsp+158h+var_48]
0x180047308  xor     rcx, rsp; StackCookie
0x18004730b  call    __security_check_cookie
0x180047310  add     rsp, 120h
0x180047317  pop     r15
0x180047319  pop     r14
0x18004731b  pop     r13
0x18004731d  pop     r12
0x18004731f  pop     rdi
0x180047320  pop     rsi
0x180047321  pop     rbx
0x180047322  retn
```
