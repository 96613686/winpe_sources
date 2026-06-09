# CRunCommandContext::Perform(uchar)

- ea: `0x14006e990`
- end: `0x14006f11f`
- name: `?Perform@CRunCommandContext@@UEAAXE@Z`
- size: `1935`
- prototype: `void __fastcall(CRunCommandContext *this)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140002890`
- `0x140003e54`
- `0x140004c58`
- `0x140007130`
- `0x14000cf60`
- `0x140011ba0`
- `0x140013f60`
- `0x140014824`
- `0x140016318`
- `0x1400188fc`
- `0x14001f99c`
- `0x140026494`
- `0x14002b3ec`
- `0x140032be0`
- `0x1400575b0`
- `0x140063928`
- `0x140064a90`
- `0x14006e114`
- `0x14006e1f8`
- `0x14006e990`
- `0x14006f59c`
- `0x140092060`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006eb52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ebd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ee17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006eec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006eb52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ebd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ee17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006eec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f059`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14006ec16`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14006f0a6`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14006ec16`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14006f0a6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14006f040`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14006f040`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14006ebc6`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x14006ebc6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14006eb48`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14006eb48`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14006eeb4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14006eeb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006ef33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006ef3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006f096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006ef33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006ef3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006f096`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14006eefa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14006ef02`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14006eefa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14006ef02`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14006ee0a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14006ee0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006ed73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14006ed73`
- `ntdll!RtlNtStatusToDosError` at `0x14006edb0`
- `ntdll!RtlNtStatusToDosError` at `0x14006edb0`
- `ntdll!RtlFreeHeap` at `0x14006f0e5`
- `ntdll!RtlFreeHeap` at `0x14006f0e5`
- `ntdll!RtlDeleteSecurityObject` at `0x14006ef53`
- `ntdll!RtlDeleteSecurityObject` at `0x14006ef53`
- `ntdll!RtlDeregisterWait` at `0x14006ea1d`
- `ntdll!RtlDeregisterWait` at `0x14006ea1d`

## pseudocode

```c
void __fastcall CRunCommandContext::Perform(CRunCommandContext *this)
{
  unsigned __int16 *v2; // r12
  void *v3; // rcx
  unsigned int v4; // edx
  struct CServiceRecord *v5; // rbx
  int v6; // r14d
  __int64 v7; // rdi
  int v8; // eax
  __int64 v9; // rax
  DWORD v10; // eax
  ULONG v11; // r14d
  DWORD LastError; // eax
  unsigned int v13; // eax
  int v14; // edi
  __int64 v15; // rax
  ULONG v16; // eax
  NTSTATUS v17; // edi
  DWORD v18; // eax
  const WCHAR *v19; // rdx
  struct _SECURITY_ATTRIBUTES *lpEnvironment; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *lpAttributeList; // rcx
  BOOL v22; // edi
  DWORD v23; // eax
  int v24; // edi
  unsigned __int16 *JITReadDisplayName; // rax
  __int64 v26; // r10
  struct _PROC_THREAD_ATTRIBUTE_LIST *v27; // rcx
  BOOL v28; // edi
  DWORD v29; // eax
  const unsigned __int16 *v30; // rax
  __int16 Value[2]; // [rsp+80h] [rbp-80h] BYREF
  int updated; // [rsp+84h] [rbp-7Ch]
  ULONG_PTR Size[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v34[8]; // [rsp+98h] [rbp-68h] BYREF
  HANDLE hToken; // [rsp+A0h] [rbp-60h]
  struct CServiceRecord *v36; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v38; // [rsp+B8h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D8h] [rbp-28h] BYREF
  struct _STARTUPINFOEXW StartupInfo; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v42[3]; // [rsp+160h] [rbp+60h] BYREF

  hToken = 0;
  hMem = 0;
  v2 = 0;
  v38 = 0;
  v36 = 0;
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  v3 = (void *)*((_QWORD *)this + 1);
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Value[0] = -1;
  memset(v42, 0, sizeof(v42));
  RtlDeregisterWait(v3);
  *((_QWORD *)this + 1) = 0;
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v36);
  if ( ScGetNamedServiceRecord(*((wchar_t **)this + 2), &v36) )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
      WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 36, WPP_26cc3840edb237854ab39f5398489811_Traceguids, *((_QWORD *)this + 2));
    goto LABEL_75;
  }
  v5 = v36;
  CScmLock::LockAutoShared((char *)v36 + 312, v34);
  v6 = *((_DWORD *)this + 20);
  if ( (*(unsigned int (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v5 + 40LL))(v5) != v6 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
    {
      v7 = *((_QWORD *)this + 2);
      v8 = (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v5 + 40LL))(v5);
      WPP_SF_dSd(
        WPP_GLOBAL_Control->StubInfo,
        37,
        (unsigned int)WPP_26cc3840edb237854ab39f5398489811_Traceguids,
        v8,
        v7,
        v6);
    }
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v34);
    goto LABEL_75;
  }
  v9 = *(_QWORD *)v5;
  updated = 0;
  Value[0] = (*(__int64 (__fastcall **)(struct CServiceRecord *))(v9 + 128))(v5);
  if ( !Value[0] )
    goto LABEL_21;
  Size[0] = 48;
  if ( InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v42, 1u, 0, Size) )
  {
    --Value[0];
    updated = UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v42, 0, 0x20004u, Value, 2u, 0, 0);
    if ( !updated )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          39,
          (unsigned int)WPP_26cc3840edb237854ab39f5398489811_Traceguids,
          *((_QWORD *)v5 + 7),
          LastError);
      DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v42);
      goto LABEL_15;
    }
LABEL_21:
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v34);
    v13 = ScLookupServiceAccount(*((struct _SERVICE_CONFIG_ROOT **)v5 + 27), *((unsigned __int16 **)v5 + 7), &v38);
    v2 = v38;
    v11 = v13;
    if ( v38 )
    {
      (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v5 + 112LL))(v5);
      v14 = (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v5 + 216LL))(v5);
      v15 = (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v5 + 32LL))(v5);
      v16 = ScLogonService(*((_QWORD *)v5 + 7), v2, 0, 0, 0, 0, 0, 0, v15 != 0, 0, v14);
      v11 = v16;
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 40, WPP_26cc3840edb237854ab39f5398489811_Traceguids, v16);
        }
LABEL_68:
        if ( updated )
          DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v42);
        goto LABEL_70;
      }
      ProcessAttributes.nLength = 24;
      ProcessAttributes.bInheritHandle = 0;
      Size[1] = (ULONG_PTR)&hMem;
      LOWORD(Size[0]) = 0;
      BYTE2(Size[0]) = 0;
      HIDWORD(Size[0]) = 0x1FFFFF;
      v17 = ScCreateAndSetSD((unsigned int)Size, 1, 0, 0, (__int64)&ProcessAttributes.lpSecurityDescriptor);
      LocalFree(hMem);
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 41, WPP_26cc3840edb237854ab39f5398489811_Traceguids, (unsigned int)v17);
        }
        v11 = RtlNtStatusToDosError(v17);
LABEL_66:
        if ( hToken )
          CloseHandle(hToken);
        goto LABEL_68;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
      {
        WPP_SF_SSD(
          WPP_GLOBAL_Control->StubInfo,
          42,
          (unsigned int)WPP_26cc3840edb237854ab39f5398489811_Traceguids,
          (_DWORD)v2,
          *((_QWORD *)this + 6),
          Value[0]);
      }
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        v18 = GetLastError();
        v11 = v18;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 43, WPP_26cc3840edb237854ab39f5398489811_Traceguids, v18);
        }
LABEL_50:
        if ( v2 )
          RtlDeleteSecurityObject(&ProcessAttributes.lpSecurityDescriptor);
        goto LABEL_66;
      }
      ScInitStartupInfo(&StartupInfo, 0);
      Size[0] = (ULONG_PTR)this + 48;
      lpAttributeList = (struct _PROC_THREAD_ATTRIBUTE_LIST *)v42;
      if ( updated == (_DWORD)lpEnvironment )
        lpAttributeList = StartupInfo.lpAttributeList;
      StartupInfo.lpAttributeList = lpAttributeList;
      v22 = CreateProcessAsUserW(
              hToken,
              v19,
              *((LPWSTR *)this + 6),
              &ProcessAttributes,
              lpEnvironment,
              (BOOL)lpEnvironment,
              0x80010u,
              lpEnvironment,
              (LPCWSTR)lpEnvironment,
              &StartupInfo.StartupInfo,
              &ProcessInformation);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Buffer::~_Buffer(Size);
      if ( !v22 )
      {
        v23 = GetLastError();
        v11 = v23;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 44, WPP_26cc3840edb237854ab39f5398489811_Traceguids, v23);
        }
        RevertToSelf();
        goto LABEL_50;
      }
      RevertToSelf();
    }
    else
    {
      v24 = 0;
      if ( (*((_DWORD *)v5 + 20) & 0x100) != 0 )
      {
        v24 = ScAllowInteractiveServices();
        if ( !v24
          && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
        {
          JITReadDisplayName = CServiceRecord::GetJITReadDisplayName(v5);
          WPP_SF_S(
            WPP_GLOBAL_Control->StubInfo,
            45,
            WPP_26cc3840edb237854ab39f5398489811_Traceguids,
            JITReadDisplayName);
        }
      }
      ScInitStartupInfo(&StartupInfo, v24);
      v27 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)v42;
      if ( !updated )
        v27 = StartupInfo.lpAttributeList;
      StartupInfo.lpAttributeList = v27;
      if ( (PRPC_ASYNC_STATE *)v26 != &WPP_GLOBAL_Control && (*(_DWORD *)(v26 + 28) & 0x100) != 0 )
        WPP_SF_Sd(
          *(_QWORD *)(v26 + 16),
          46,
          (unsigned int)WPP_26cc3840edb237854ab39f5398489811_Traceguids,
          *((_QWORD *)this + 6),
          Value[0]);
      Size[0] = (ULONG_PTR)this + 48;
      v28 = CreateProcessW(
              0,
              *((LPWSTR *)this + 6),
              0,
              0,
              0,
              0x80010u,
              0,
              0,
              &StartupInfo.StartupInfo,
              &ProcessInformation);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Buffer::~_Buffer(Size);
      if ( !v28 )
      {
        v29 = GetLastError();
        v11 = v29;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 47, WPP_26cc3840edb237854ab39f5398489811_Traceguids, v29);
        }
        goto LABEL_66;
      }
    }
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 48, WPP_26cc3840edb237854ab39f5398489811_Traceguids);
    }
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(ProcessInformation.hProcess);
    goto LABEL_50;
  }
  v10 = GetLastError();
  v11 = v10;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      38,
      (unsigned int)WPP_26cc3840edb237854ab39f5398489811_Traceguids,
      *((_QWORD *)v5 + 7),
      v10);
LABEL_15:
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v34);
LABEL_70:
  if ( v11 && v5 )
  {
    v30 = CServiceRecord::GetJITReadDisplayName(v5);
    ScLogRecoveryFailure(3u, v30, v11);
  }
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
LABEL_75:
  CRunCommandContext::`scalar deleting destructor'(this, v4);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v36);
}

```

## disassembly

```asm
0x14006e990  push    rbp
0x14006e992  push    rbx
0x14006e993  push    rsi
0x14006e994  push    rdi
0x14006e995  push    r12
0x14006e997  push    r13
0x14006e999  push    r14
0x14006e99b  push    r15
0x14006e99d  lea     rbp, [rsp-0A8h]
0x14006e9a5  sub     rsp, 1A8h
0x14006e9ac  mov     rax, cs:__security_cookie
0x14006e9b3  xor     rax, rsp
0x14006e9b6  mov     [rbp+0E0h+var_50], rax
0x14006e9bd  xor     r13d, r13d
0x14006e9c0  mov     r15, rcx
0x14006e9c3  xor     edx, edx; Val
0x14006e9c5  mov     [rbp+0E0h+hToken], r13
0x14006e9c9  lea     rcx, [rbp+0E0h+StartupInfo.lpReserved]; void *
0x14006e9cd  mov     [rbp+0E0h+hMem], r13
0x14006e9d1  mov     r12d, r13d
0x14006e9d4  mov     [rbp+0E0h+var_128], r13
0x14006e9d8  lea     r8d, [r13+68h]; Size
0x14006e9dc  mov     [rbp+0E0h+var_138], r13
0x14006e9e0  mov     qword ptr [rbp+0E0h+StartupInfo.cb], r13
0x14006e9e4  call    memset
0x14006e9e9  mov     rcx, [r15+8]; hWaitHandle
0x14006e9ed  xorps   xmm0, xmm0
0x14006e9f0  xor     eax, eax
0x14006e9f2  xorps   xmm1, xmm1
0x14006e9f5  mov     edi, 0FFFFh
0x14006e9fa  mov     qword ptr [rbp+0E0h+ProcessAttributes.bInheritHandle], rax
0x14006e9fe  movups  xmmword ptr [rbp+0E0h+ProcessAttributes.nLength], xmm0
0x14006ea02  mov     qword ptr [rbp+0E0h+ProcessInformation.dwProcessId], rax
0x14006ea06  movups  xmmword ptr [rbp+0E0h+ProcessInformation.hProcess], xmm1
0x14006ea0a  mov     [rbp+0E0h+Value], di
0x14006ea0e  movups  [rbp+0E0h+var_80], xmm0
0x14006ea12  movups  [rbp+0E0h+var_70], xmm0
0x14006ea16  movups  [rbp+0E0h+var_60], xmm0
0x14006ea1d  call    cs:__imp_RtlDeregisterWait
0x14006ea23  lea     rcx, [rbp+0E0h+var_138]
0x14006ea27  mov     [r15+8], r13
0x14006ea2b  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x14006ea30  mov     rcx, [r15+10h]; String2
0x14006ea34  lea     rdx, [rbp+0E0h+var_138]; struct CServiceRecord **
0x14006ea38  call    ?ScGetNamedServiceRecord@@YAKPEBGPEAPEAVCServiceRecord@@@Z; ScGetNamedServiceRecord(ushort const *,CServiceRecord * *)
0x14006ea3d  test    eax, eax
0x14006ea3f  jz      short loc_14006EA7F
0x14006ea41  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ea48  lea     rsi, WPP_GLOBAL_Control
0x14006ea4f  cmp     rcx, rsi
0x14006ea52  jz      loc_14006F0EB
0x14006ea58  test    byte ptr [rcx+1Ch], 2
0x14006ea5c  jz      loc_14006F0EB
0x14006ea62  mov     r9, [r15+10h]
0x14006ea66  lea     edx, [r13+24h]
0x14006ea6a  mov     rcx, [rcx+10h]
0x14006ea6e  lea     r8, WPP_26cc3840edb237854ab39f5398489811_Traceguids
0x14006ea75  call    WPP_SF_S
0x14006ea7a  jmp     loc_14006F0EB
0x14006ea7f  mov     rbx, [rbp+0E0h+var_138]
0x14006ea83  lea     rdx, [rbp+0E0h+var_148]
0x14006ea87  lea     rcx, [rbx+138h]
0x14006ea8e  call    ?LockAutoShared@CScmLock@@QEAA?AVCScmSyncLockShared@@XZ; CScmLock::LockAutoShared(void)
0x14006ea93  mov     rax, [rbx]
0x14006ea96  mov     rcx, rbx
0x14006ea99  mov     r14d, [r15+50h]
0x14006ea9d  mov     rax, [rax+28h]
0x14006eaa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006eaa6  cmp     eax, r14d
0x14006eaa9  jz      short loc_14006EB0E
0x14006eaab  mov     rax, cs:WPP_GLOBAL_Control
0x14006eab2  lea     rsi, WPP_GLOBAL_Control
0x14006eab9  cmp     rax, rsi
0x14006eabc  jz      short loc_14006EB00
0x14006eabe  test    byte ptr [rax+1Ch], 2
0x14006eac2  jz      short loc_14006EB00
0x14006eac4  mov     rax, [rbx]
0x14006eac7  mov     rcx, rbx
0x14006eaca  mov     rdi, [r15+10h]
0x14006eace  mov     rax, [rax+28h]
0x14006ead2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ead7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eade  lea     r8, WPP_26cc3840edb237854ab39f5398489811_Traceguids
0x14006eae5  mov     edx, 25h ; '%'
0x14006eaea  mov     dword ptr [rsp+1E0h+lpPreviousValue], r14d
0x14006eaef  mov     r9d, eax
0x14006eaf2  mov     [rsp+1E0h+cbSize], rdi
0x14006eaf7  mov     rcx, [rcx+10h]
0x14006eafb  call    WPP_SF_dSd
0x14006eb00  lea     rcx, [rbp+0E0h+var_148]; this
0x14006eb04  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x14006eb09  jmp     loc_14006F0EB
0x14006eb0e  mov     rax, [rbx]
0x14006eb11  mov     rcx, rbx
0x14006eb14  mov     [rbp+0E0h+var_15C], r13d
0x14006eb18  mov     rax, [rax+80h]
0x14006eb1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006eb24  mov     [rbp+0E0h+Value], ax
0x14006eb28  test    ax, ax
0x14006eb2b  jz      loc_14006EC21
0x14006eb31  xor     r8d, r8d; dwFlags
0x14006eb34  mov     [rbp+0E0h+Size], 30h ; '0'
0x14006eb3c  lea     r9, [rbp+0E0h+Size]; lpSize
0x14006eb40  lea     rcx, [rbp+0E0h+var_80]; lpAttributeList
0x14006eb44  lea     edx, [r8+1]; dwAttributeCount
0x14006eb48  call    cs:__imp_InitializeProcThreadAttributeList
0x14006eb4e  test    eax, eax
0x14006eb50  jnz     short loc_14006EB9F
0x14006eb52  call    cs:__imp_GetLastError
0x14006eb58  mov     r14d, eax
0x14006eb5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eb62  lea     rsi, WPP_GLOBAL_Control
0x14006eb69  cmp     rcx, rsi
0x14006eb6c  jz      short loc_14006EB91
0x14006eb6e  test    byte ptr [rcx+1Ch], 1
0x14006eb72  jz      short loc_14006EB91
0x14006eb74  mov     r9, [rbx+38h]
0x14006eb78  lea     r8, WPP_26cc3840edb237854ab39f5398489811_Traceguids
0x14006eb7f  mov     rcx, [rcx+10h]
0x14006eb83  mov     edx, 26h ; '&'
0x14006eb88  mov     dword ptr [rsp+1E0h+cbSize], eax
0x14006eb8c  call    WPP_SF_Sd
0x14006eb91  lea     rcx, [rbp+0E0h+var_148]; this
0x14006eb95  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x14006eb9a  jmp     loc_14006F0AC
0x14006eb9f  add     [rbp+0E0h+Value], di
0x14006eba3  lea     r9, [rbp+0E0h+Value]; lpValue
0x14006eba7  mov     [rsp+1E0h+lpReturnSize], r13; lpReturnSize
0x14006ebac  lea     rcx, [rbp+0E0h+var_80]; lpAttributeList
0x14006ebb0  mov     [rsp+1E0h+lpPreviousValue], r13; lpPreviousValue
0x14006ebb5  xor     edx, edx; dwFlags
0x14006ebb7  mov     r8d, 20004h; Attribute
0x14006ebbd  mov     [rsp+1E0h+cbSize], 2; cbSize
0x14006ebc6  call    cs:__imp_UpdateProcThreadAttribute
0x14006ebcc  mov     [rbp+0E0h+var_15C], eax
0x14006ebcf  test    eax, eax
0x14006ebd1  jnz     short loc_14006EC21
0x14006ebd3  call    cs:__imp_GetLastError
0x14006ebd9  mov     r14d, eax
0x14006ebdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ebe3  lea     rsi, WPP_GLOBAL_Control
0x14006ebea  cmp     rcx, rsi
0x14006ebed  jz      short loc_14006EC12
0x14006ebef  test    byte ptr [rcx+1Ch], 1
0x14006ebf3  jz      short loc_14006EC12
0x14006ebf5  mov     r9, [rbx+38h]
0x14006ebf9  lea     r8, WPP_26cc3840edb237854ab39f5398489811_Traceguids
0x14006ec00  mov     rcx, [rcx+10h]
0x14006ec04  mov     edx, 27h ; '''
0x14006ec09  mov     dword ptr [rsp+1E0h+cbSize], eax
0x14006ec0d  call    WPP_SF_Sd
0x14006ec12  lea     rcx, [rbp+0E0h+var_80]; lpAttributeList
0x14006ec16  call    cs:__imp_DeleteProcThreadAttributeList
0x14006ec1c  jmp     loc_14006EB91
0x14006ec21  lea     rcx, [rbp+0E0h+var_148]; this
0x14006ec25  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x14006ec2a  mov     rdx, [rbx+38h]; unsigned __int16 *
0x14006ec2e  lea     r8, [rbp+0E0h+var_128]; unsigned __int16 **
0x14006ec32  mov     rcx, [rbx+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x14006ec39  call    ?ScLookupServiceAccount@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAGPEAPEAG@Z; ScLookupServiceAccount(_SERVICE_CONFIG_ROOT *,ushort *,ushort * *)
0x14006ec3e  mov     r12, [rbp+0E0h+var_128]
0x14006ec42  mov     r14d, eax
0x14006ec45  test    r12, r12
0x14006ec48  jz      loc_14006EF5E
0x14006ec4e  mov     rax, [rbx]
0x14006ec51  mov     r14d, r13d
0x14006ec54  cmp     [rbx+48h], r13
0x14006ec58  mov     rcx, rbx
0x14006ec5b  setnz   r14b
0x14006ec5f  mov     rax, [rax+70h]
0x14006ec63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ec68  mov     rcx, [rbx]
0x14006ec6b  mov     esi, eax
0x14006ec6d  mov     rax, [rcx+0D8h]
0x14006ec74  mov     rcx, rbx
0x14006ec77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ec7c  mov     rcx, [rbx]
0x14006ec7f  mov     edi, eax
0x14006ec81  mov     rax, [rcx+20h]
0x14006ec85  mov     rcx, rbx
0x14006ec88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ec8d  test    rax, rax
0x14006ec90  mov     ecx, r13d
0x14006ec93  lea     rax, [rbp+0E0h+hMem]
0x14006ec97  mov     rdx, r12
0x14006ec9a  mov     [rsp+1E0h+var_168], rax
0x14006ec9f  setnz   cl
0x14006eca2  mov     [rsp+1E0h+var_170], r13
0x14006eca7  lea     rax, [rbp+0E0h+hToken]
0x14006ecab  mov     [rsp+1E0h+var_178], rax
0x14006ecb0  xor     r9d, r9d
0x14006ecb3  mov     [rsp+1E0h+var_180], r14d
0x14006ecb8  xor     r8d, r8d
0x14006ecbb  mov     [rsp+1E0h+var_188], esi
0x14006ecbf  mov     dword ptr [rsp+1E0h+lpProcessInformation], edi
0x14006ecc3  mov     dword ptr [rsp+1E0h+lpStartupInfo], r13d
0x14006ecc8  mov     dword ptr [rsp+1E0h+lpCurrentDirectory], ecx
0x14006eccc  mov     rcx, [rbx+38h]
0x14006ecd0  mov     dword ptr [rsp+1E0h+lpEnvironment], r13d
0x14006ecd5  mov     dword ptr [rsp+1E0h+lpReturnSize], r13d
0x14006ecda  mov     dword ptr [rsp+1E0h+lpPreviousValue], r13d
0x14006ecdf  mov     [rsp+1E0h+cbSize], r13
0x14006ece4  call    ?ScLogonService@@YAKPEAG0PEAPEAXK1KHHHKW4_TRI_BOOL@@HH111@Z; ScLogonService(ushort *,ushort *,void * *,ulong,void * *,ulong,int,int,int,ulong,_TRI_BOOL,int,int,void * *,void * *,void * *)
0x14006ece9  mov     r14d, eax
0x14006ecec  test    eax, eax
0x14006ecee  jz      short loc_14006ED2E
0x14006ecf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ecf7  lea     rsi, WPP_GLOBAL_Control
0x14006ecfe  cmp     rcx, rsi
0x14006ed01  jz      loc_14006F09C
0x14006ed07  test    byte ptr [rcx+1Ch], 1
0x14006ed0b  jz      loc_14006F09C
0x14006ed11  mov     rcx, [rcx+10h]
0x14006ed15  lea     r8, WPP_26cc3840edb237854ab39f5398489811_Traceguids
0x14006ed1c  mov     edx, 28h ; '('
0x14006ed21  mov     r9d, eax
0x14006ed24  call    WPP_SF_d
0x14006ed29  jmp     loc_14006F09C
0x14006ed2e  xor     r9d, r9d
0x14006ed31  mov     [rbp+0E0h+ProcessAttributes.nLength], 18h
0x14006ed38  lea     rax, [rbp+0E0h+hMem]
0x14006ed3c  mov     [rbp+0E0h+ProcessAttributes.bInheritHandle], r13d
0x14006ed40  mov     [rbp+0E0h+var_150], rax
0x14006ed44  lea     rcx, [rbp+0E0h+Size]
0x14006ed48  lea     rax, [rbp+0E0h+ProcessAttributes.lpSecurityDescriptor]
0x14006ed4c  mov     word ptr [rbp+0E0h+Size], r13w
0x14006ed51  lea     edx, [r9+1]
0x14006ed55  mov     byte ptr [rbp+0E0h+Size+2], r13b
0x14006ed59  xor     r8d, r8d
0x14006ed5c  mov     dword ptr [rbp+0E0h+Size+4], 1FFFFFh
0x14006ed63  mov     [rsp+1E0h+cbSize], rax
0x14006ed68  call    ScCreateAndSetSD
0x14006ed6d  mov     rcx, [rbp+0E0h+hMem]; hMem
0x14006ed71  mov     edi, eax
0x14006ed73  call    cs:__imp_LocalFree
0x14006ed79  test    edi, edi
0x14006ed7b  jns     short loc_14006EDBE
0x14006ed7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ed84  lea     rsi, WPP_GLOBAL_Control
0x14006ed8b  cmp     rcx, rsi
0x14006ed8e  jz      short loc_14006EDAE
0x14006ed90  test    byte ptr [rcx+1Ch], 1
0x14006ed94  jz      short loc_14006EDAE
0x14006ed96  mov     rcx, [rcx+10h]
0x14006ed9a  lea     r8, WPP_26cc3840edb237854ab39f5398489811_Traceguids
0x14006eda1  mov     edx, 29h ; ')'
0x14006eda6  mov     r9d, edi
0x14006eda9  call    WPP_SF_d
0x14006edae  mov     ecx, edi; Status
0x14006edb0  call    cs:__imp_RtlNtStatusToDosError
0x14006edb6  mov     r14d, eax
0x14006edb9  jmp     loc_14006F08D
0x14006edbe  mov     rcx, cs:WPP_GLOBAL_Control
0x14006edc5  lea     rsi, WPP_GLOBAL_Control
0x14006edcc  mov     r13d, 100h
0x14006edd2  cmp     rcx, rsi
0x14006edd5  jz      short loc_14006EE06
0x14006edd7  test    [rcx+1Ch], r13d
0x14006eddb  jz      short loc_14006EE06
0x14006eddd  movzx   eax, [rbp+0E0h+Value]
0x14006ede1  lea     r8, WPP_26cc3840edb237854ab39f5398489811_Traceguids
0x14006ede8  mov     rcx, [rcx+10h]
0x14006edec  mov     edx, 2Ah ; '*'
0x14006edf1  mov     dword ptr [rsp+1E0h+lpPreviousValue], eax
0x14006edf5  mov     r9, r12
0x14006edf8  mov     rax, [r15+30h]
0x14006edfc  mov     [rsp+1E0h+cbSize], rax
0x14006ee01  call    WPP_SF_SSD
0x14006ee06  mov     rcx, [rbp+0E0h+hToken]; hToken
0x14006ee0a  call    cs:__imp_ImpersonateLoggedOnUser
0x14006ee10  xor     r9d, r9d
0x14006ee13  test    eax, eax
0x14006ee15  jnz     short loc_14006EE57
0x14006ee17  call    cs:__imp_GetLastError
0x14006ee1d  mov     r14d, eax
0x14006ee20  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ee27  cmp     rcx, rsi
0x14006ee2a  jz      loc_14006EF43
0x14006ee30  test    byte ptr [rcx+1Ch], 1
0x14006ee34  jz      loc_14006EF43
0x14006ee3a  mov     rcx, [rcx+10h]
0x14006ee3e  lea     r8, WPP_26cc3840edb237854ab39f5398489811_Traceguids
0x14006ee45  mov     edx, 2Bh ; '+'
0x14006ee4a  mov     r9d, eax
0x14006ee4d  call    WPP_SF_d
0x14006ee52  jmp     loc_14006EF43
0x14006ee57  xor     edx, edx; int
0x14006ee59  lea     rcx, [rbp+0E0h+StartupInfo]; struct _STARTUPINFOEXW *
0x14006ee5d  call    ?ScInitStartupInfo@@YAXPEAU_STARTUPINFOEXW@@H@Z; ScInitStartupInfo(_STARTUPINFOEXW *,int)
0x14006ee62  cmp     [rbp+0E0h+var_15C], r9d
0x14006ee66  lea     rax, [rbp+0E0h+ProcessInformation]
0x14006ee6a  mov     [rsp+1E0h+lpProcessInformation], rax; lpProcessInformation
0x14006ee6f  lea     r8, [r15+30h]
0x14006ee73  lea     rax, [rbp+0E0h+StartupInfo]
0x14006ee77  mov     [rbp+0E0h+Size], r8
0x14006ee7b  mov     [rsp+1E0h+lpStartupInfo], rax; lpStartupInfo
0x14006ee80  lea     rcx, [rbp+0E0h+var_80]
0x14006ee84  cmovz   rcx, [rbp+0E0h+var_88]
0x14006ee89  mov     [rsp+1E0h+lpCurrentDirectory], r9; lpCurrentDirectory
0x14006ee8e  mov     [rsp+1E0h+lpEnvironment], r9; lpEnvironment
  ... truncated ...
```
