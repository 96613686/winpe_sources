# UserManagerTokenAndShellHandler::LaunchShellInfrastructureHost(ulong,void *,int)

- ea: `0x18004732c`
- end: `0x180047990`
- name: `?LaunchShellInfrastructureHost@UserManagerTokenAndShellHandler@@QEAAJKPEAXH@Z`
- size: `1636`
- prototype: `__int64 __fastcall(UserManagerTokenAndShellHandler *__hidden this, unsigned int, void *, int)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800465e4`
- `0x1800479a0`
- `0x1800b68e4`

## callees

- `0x180001268`
- `0x18001135c`
- `0x180012890`
- `0x1800269c4`
- `0x180026ba0`
- `0x18002799c`
- `0x18003320c`
- `0x180034e80`
- `0x18003c1ec`
- `0x18003cc3c`
- `0x18003e290`
- `0x18004254c`
- `0x18004732c`
- `0x180047a18`
- `0x18005f2f4`
- `0x1800624bc`
- `0x180063fe8`
- `0x18006da60`
- `0x1800b759c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004774f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004774f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800474a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004752d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800474a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004752d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047396`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047688`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047908`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047396`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047688`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047908`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004764d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004764d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800477fe`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800477fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800474d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047896`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800474d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004756c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004756c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800474bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004755e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047880`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800474bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004755e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004765d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004783d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800478e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004765d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004783d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800478e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180047374`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180047374`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004753e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004753e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800478d9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800478d9`
- `ntdll!NtSetInformationProcess` at `0x180047871`
- `ntdll!NtSetInformationProcess` at `0x180047871`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800476fa`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800476fa`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800477dd`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800477dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserManagerTokenAndShellHandler::LaunchShellInfrastructureHost(
        UserManagerTokenAndShellHandler *this,
        ULONG a2,
        void *a3,
        int a4)
{
  _QWORD *v5; // rsi
  char v6; // r12
  _DWORD *v7; // r13
  unsigned int v8; // r15d
  __int64 *v9; // rax
  _QWORD *v10; // r11
  __int64 v11; // rbx
  __int64 v12; // rdx
  const struct _tlgProvider_t *v13; // rax
  int v14; // r8d
  int v15; // r9d
  UserManagerTokenAndShellHandler *v16; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v18; // rax
  signed int LastError; // ebx
  const struct _tlgProvider_t *v20; // rax
  int v21; // r8d
  int v22; // r9d
  RTL_SRWLOCK *v23; // r14
  UserManagerTokenAndShellHandler *v24; // rcx
  HANDLE v25; // rax
  const struct _tlgProvider_t *v27; // rax
  __int64 v28; // r8
  int v29; // r9d
  HANDLE EventW; // rax
  char v31; // r12
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // r15d
  int CurrentServiceSessionId; // eax
  __int64 v36; // rcx
  HANDLE v37; // rdx
  DWORD v38; // eax
  const struct _tlgProvider_t *v39; // rax
  int v40; // r8d
  int v41; // r9d
  int v42; // eax
  HANDLE v43; // rax
  int v44; // esi
  __int64 v45; // rax
  int v46; // r8d
  RTL_SRWLOCK *SRWLock; // [rsp+40h] [rbp-88h]
  int v48; // [rsp+48h] [rbp-80h]
  ULONG v49; // [rsp+4Ch] [rbp-7Ch] BYREF
  ULONGLONG TickCount64; // [rsp+50h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-70h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-68h] BYREF
  _QWORD *v53; // [rsp+68h] [rbp-60h] BYREF
  int ProcessInformation; // [rsp+70h] [rbp-58h] BYREF
  ULONG v55; // [rsp+78h] [rbp-50h] BYREF
  _QWORD *v56; // [rsp+80h] [rbp-48h]
  char *v57; // [rsp+88h] [rbp-40h]
  ULONGLONG v58; // [rsp+D0h] [rbp+8h] BYREF
  ULONG SessionId; // [rsp+D8h] [rbp+10h] BYREF
  void *v60; // [rsp+E0h] [rbp+18h]
  int v61; // [rsp+E8h] [rbp+20h]

  v61 = a4;
  v60 = a3;
  SessionId = a2;
  v5 = 0;
  hObject = (HANDLE)-1LL;
  ProcessInformation = 1;
  v48 = 0;
  v6 = *((_BYTE *)this + 152) != 0;
  v7 = 0;
  TickCount64 = GetTickCount64();
  v8 = 0;
  v58 = 0;
  SRWLock = (RTL_SRWLOCK *)((char *)this + 72);
  AcquireSRWLockExclusive((PSRWLOCK)this + 9);
  v57 = (char *)this + 80;
  v9 = (__int64 *)std::_Tree<std::_Tmap_traits<unsigned int,Windows::System::Internal::Implementation::SignOutProgress *,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(
                    (char *)this + 80,
                    &v55,
                    &SessionId);
  v11 = *v9;
  if ( *v9 != *v10 )
  {
    if ( !v61 )
    {
LABEL_10:
      v5 = *(_QWORD **)(v11 + 40);
      std::_Tree<std::_Tmap_traits<unsigned long,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *>>,0>>::erase(
        v10,
        &v55,
        v11);
      goto LABEL_11;
    }
    v12 = *(_QWORD *)(v11 + 40);
    v48 = *(_DWORD *)(v12 + 44) + 1;
    if ( TickCount64 - *(_QWORD *)(v12 + 64) < *((unsigned int *)this + 43) )
      v8 = *(_DWORD *)(v12 + 56) + 1;
    v6 = *(_BYTE *)(v12 + 40);
    v13 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v13 > 5u )
    {
      LOBYTE(v58) = v6;
      v52 = v8;
      LODWORD(v53) = v48;
      v49 = SessionId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        (_DWORD)v13,
        (unsigned int)byte_18012B163,
        v14,
        v15,
        (__int64)&v49,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v58);
    }
    if ( v6 && v8 <= *((_DWORD *)this + 42) )
    {
      v58 = TickCount64;
      v10 = (_QWORD *)((char *)this + 80);
      goto LABEL_10;
    }
    LastError = 352;
    v20 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v20 > 2u )
    {
      LODWORD(v58) = -2147024544;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v20,
        (unsigned int)byte_18012B085,
        v21,
        v22,
        (__int64)&v58);
    }
LABEL_17:
    v23 = (RTL_SRWLOCK *)((char *)this + 72);
LABEL_18:
    ReleaseSRWLockExclusive(v23);
    goto LABEL_19;
  }
  if ( v61 )
  {
    LastError = 352;
    v27 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v27 > 2u && (unsigned __int8)tlgKeywordOn(v27, 0x200000000000LL, v28, v27) )
    {
      TickCount64 = 0x1000000;
      LODWORD(v58) = -2147024544;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v29,
        (unsigned int)byte_18012B0F3,
        0,
        v29,
        (__int64)&v58,
        (__int64)&TickCount64);
    }
    goto LABEL_17;
  }
LABEL_11:
  ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
    UserManagerTokenAndShellHandler::FreeShellInfrastructureHostMapEntry(
      v16,
      (struct _SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *)v5,
      v61);
  ProcessHeap = GetProcessHeap();
  v18 = HeapAlloc(ProcessHeap, 8u, 0x48u);
  v5 = v18;
  v53 = v18;
  if ( !v18 )
  {
    LastError = 8;
    goto LABEL_19;
  }
  *v18 = -1;
  v18[1] = -1;
  v18[3] = -1;
  *((_BYTE *)v18 + 40) = v6;
  *((_DWORD *)v18 + 11) = v48;
  v18[6] = -1;
  *((_DWORD *)v18 + 14) = v8;
  v18[8] = v58;
  EventW = CreateEventW(0, 0, 0, 0);
  v5[3] = EventW;
  if ( EventW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_19;
  }
  v31 = 0;
  LOBYTE(v58) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShellInfraHostLock>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockExclusive(SRWLock);
    v31 = 1;
    LOBYTE(v58) = 1;
  }
  if ( !*((_BYTE *)this + 160) )
  {
    CurrentServiceSessionId = RtlGetCurrentServiceSessionId(v32);
    if ( CurrentServiceSessionId == SessionId )
    {
      if ( !*((_BYTE *)this + 156) )
      {
        LastError = UserManagerTokenAndShellHandler::WaitForFirstUserToken(this);
        if ( LastError )
        {
          v39 = UserMgrUserModelTelemetry::Provider();
          if ( *(_DWORD *)v39 > 2u )
          {
            LODWORD(v58) = LastError;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (_DWORD)v39,
              (unsigned int)&word_18012B03E,
              v40,
              v41,
              (__int64)&v58);
          }
          goto LABEL_75;
        }
        AcquireSRWLockShared((PSRWLOCK)this + 4);
        TickCount64 = (ULONGLONG)this + 32;
        LastError = LaunchProcessAsUser(
                      *((unsigned __int16 **)this + 16),
                      *((HANDLE *)this + 5),
                      (LPPROCESS_INFORMATION)v5);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&TickCount64);
        goto LABEL_62;
      }
      if ( *((_QWORD *)this + 3) == -1 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v36);
      v37 = (HANDLE)*((_QWORD *)this + 3);
    }
    else
    {
      if ( !*((_BYTE *)this + 152) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v36);
      if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
      {
        LastError = 127;
        goto LABEL_75;
      }
      if ( !WTSQueryUserToken(SessionId, &hObject) || !SetTokenInformation(hObject, TokenSessionId, &SessionId, 4u) )
      {
        v38 = GetLastError();
        goto LABEL_61;
      }
      v42 = UserManagerTokenAndShellHandler::RestoreStateFromTokenIfNeeded(this, SessionId, hObject);
      LastError = v42;
      if ( v42 < 0 )
      {
        if ( (v42 & 0x1FFF0000) == 0x70000 )
          LastError = (unsigned __int16)v42;
        goto LABEL_62;
      }
      v37 = hObject;
    }
    v38 = LaunchProcessAsUser(*((unsigned __int16 **)this + 16), v37, (LPPROCESS_INFORMATION)v5);
LABEL_61:
    LastError = v38;
    goto LABEL_62;
  }
  LastError = 0;
  v34 = LaunchShellHostAsVirtualAccount(
          SessionId,
          v60,
          *((unsigned __int16 **)this + 16),
          (const struct _VIRTUAL_ACCOUNT_CONTEXT **)v5 + 4,
          (struct _PROCESS_INFORMATION *)v5);
  if ( v34 >= 0 )
    goto LABEL_63;
  MicrosoftTelemetryAssertTriggeredNoArgs(v33);
  if ( (v34 & 0x1FFF0000) == 0x70000 )
    LastError = (unsigned __int16)v34;
  else
    LastError = v34;
LABEL_62:
  if ( LastError )
  {
LABEL_75:
    v23 = SRWLock;
    goto LABEL_76;
  }
LABEL_63:
  if ( *((_BYTE *)this + 152) )
    goto LABEL_67;
  if ( *((_BYTE *)this + 161) )
    NtSetInformationProcess((HANDLE)*v5, ProcessBreakOnTermination, &ProcessInformation, 4u);
  if ( *((_BYTE *)this + 152) )
  {
LABEL_67:
    v43 = GetProcessHeap();
    v7 = HeapAlloc(v43, 8u, 0x10u);
    if ( !v7 )
    {
      LastError = 8;
      goto LABEL_75;
    }
    v7[2] = SessionId;
    *(_QWORD *)v7 = this;
    if ( !RegisterWaitForSingleObject(
            (PHANDLE)v5 + 6,
            (HANDLE)*v5,
            RestartShellInfrastructureHostProcess,
            v7,
            0xFFFFFFFF,
            8u) )
    {
      LastError = GetLastError();
      goto LABEL_75;
    }
  }
  v23 = (RTL_SRWLOCK *)((char *)this + 72);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShellInfraHostLock>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockExclusive(SRWLock);
    v31 = 1;
    LOBYTE(v58) = 1;
  }
  try
  {
    v55 = SessionId;
    v56 = v5;
    v44 = (int)v57;
    v45 = std::_Tree_buy<std::pair<unsigned long const,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *>>::_Buynode<std::pair<unsigned long,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *>>(
            v57,
            &v55);
    std::_Tree<std::_Tmap_traits<unsigned long,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *>>,0>>::_Insert_nohint<std::pair<unsigned long const,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *> &,std::_Tree_node<std::pair<unsigned long const,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *>,void *> *>(
      v44,
      (unsigned int)&v55,
      v46,
      v45 + 32,
      v45);
  }
  catch ( std::bad_alloc )
  {
    v49 = 8;
    v7 = 0;
    LastError = 8;
    v5 = v53;
    v31 = v58;
    goto LABEL_75;
  }
  v5 = 0;
  v7 = 0;
LABEL_76:
  if ( v31 )
    goto LABEL_18;
LABEL_19:
  v24 = (UserManagerTokenAndShellHandler *)hObject;
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v5 )
    UserManagerTokenAndShellHandler::FreeShellInfrastructureHostMapEntry(
      v24,
      (struct _SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *)v5,
      v61);
  if ( v7 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v7);
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18004732c  mov     rax, rsp
0x18004732f  mov     [rax+20h], r9d
0x180047333  mov     [rax+18h], r8
0x180047337  mov     [rax+10h], edx
0x18004733a  push    rbx
0x18004733b  push    rsi
0x18004733c  push    rdi
0x18004733d  push    r12
0x18004733f  push    r13
0x180047341  push    r14
0x180047343  push    r15
0x180047345  sub     rsp, 90h
0x18004734c  mov     r14, rcx
0x18004734f  xor     edi, edi
0x180047351  mov     esi, edi
0x180047353  mov     qword ptr [rax-70h], 0FFFFFFFFFFFFFFFFh
0x18004735b  mov     dword ptr [rax-58h], 1
0x180047362  mov     [rsp+0C8h+var_80], edi
0x180047366  cmp     [rcx+98h], dil
0x18004736d  setnz   r12b
0x180047371  mov     r13d, edi
0x180047374  call    cs:__imp_GetTickCount64
0x18004737a  mov     [rsp+0C8h+var_78], rax
0x18004737f  mov     r15d, edi
0x180047382  mov     [rsp+0C8h+arg_0], rdi
0x18004738a  lea     rax, [r14+48h]
0x18004738e  mov     [rsp+0C8h+SRWLock], rax
0x180047393  mov     rcx, rax; SRWLock
0x180047396  call    cs:__imp_AcquireSRWLockExclusive
0x18004739c  lea     r11, [r14+50h]
0x1800473a0  mov     [rsp+0C8h+var_40], r11
0x1800473a8  lea     r8, [rsp+0C8h+SessionId]
0x1800473b0  lea     rdx, [rsp+0C8h+var_50]
0x1800473b5  mov     rcx, r11
0x1800473b8  call    ?find@?$_Tree@V?$_Tmap_traits@IPEAVSignOutProgress@Implementation@Internal@System@Windows@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,Windows::System::Internal::Implementation::SignOutProgress *,std::less<uint>,std::allocator<std::pair<uint const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(uint const &)
0x1800473bd  mov     rbx, [rax]
0x1800473c0  cmp     rbx, [r11]
0x1800473c3  jz      loc_180047594
0x1800473c9  cmp     [rsp+0C8h+arg_18], edi
0x1800473d0  jz      loc_180047488
0x1800473d6  mov     rdx, [rbx+28h]
0x1800473da  mov     eax, [rdx+2Ch]
0x1800473dd  inc     eax
0x1800473df  mov     [rsp+0C8h+var_80], eax
0x1800473e3  mov     rcx, [rsp+0C8h+var_78]
0x1800473e8  sub     rcx, [rdx+40h]
0x1800473ec  mov     eax, [r14+0ACh]
0x1800473f3  cmp     rcx, rax
0x1800473f6  jnb     short loc_1800473FF
0x1800473f8  mov     r15d, [rdx+38h]
0x1800473fc  inc     r15d
0x1800473ff  mov     r12b, [rdx+28h]
0x180047403  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180047408  mov     ecx, [rax]
0x18004740a  cmp     ecx, 5
0x18004740d  jbe     short loc_180047469
0x18004740f  mov     byte ptr [rsp+0C8h+arg_0], r12b
0x180047417  mov     [rsp+0C8h+var_68], r15d
0x18004741c  mov     ecx, [rsp+0C8h+var_80]
0x180047420  mov     dword ptr [rsp+0C8h+var_60], ecx
0x180047424  mov     ecx, [rsp+0C8h+SessionId]
0x18004742b  mov     [rsp+0C8h+var_7C], ecx
0x18004742f  lea     rcx, [rsp+0C8h+arg_0]
0x180047437  mov     [rsp+0C8h+var_90], rcx
0x18004743c  lea     rcx, [rsp+0C8h+var_68]
0x180047441  mov     [rsp+0C8h+var_98], rcx
0x180047446  lea     rcx, [rsp+0C8h+var_60]
0x18004744b  mov     qword ptr [rsp+0C8h+dwFlags], rcx
0x180047450  lea     rcx, [rsp+0C8h+var_7C]
0x180047455  mov     qword ptr [rsp+0C8h+dwMilliseconds], rcx
0x18004745a  lea     rdx, byte_18012B163
0x180047461  mov     rcx, rax
0x180047464  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180047469  test    r12b, r12b
0x18004746c  jz      short loc_1800474ED
0x18004746e  cmp     r15d, [r14+0A8h]
0x180047475  ja      short loc_1800474ED
0x180047477  mov     rax, [rsp+0C8h+var_78]
0x18004747c  mov     [rsp+0C8h+arg_0], rax
0x180047484  lea     r11, [r14+50h]
0x180047488  mov     rsi, [rbx+28h]
0x18004748c  mov     r8, rbx
0x18004748f  lea     rdx, [rsp+0C8h+var_50]
0x180047494  mov     rcx, r11
0x180047497  call    ?erase@?$_Tree@V?$_Tmap_traits@KPEAU_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *,std::less<ulong>,std::allocator<std::pair<ulong const,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *>>>>)
0x18004749c  mov     rbx, [rsp+0C8h+SRWLock]
0x1800474a1  mov     rcx, rbx; SRWLock
0x1800474a4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800474aa  test    rsi, rsi
0x1800474ad  jz      short loc_1800474BF
0x1800474af  mov     r8d, [rsp+0C8h+arg_18]; int
0x1800474b7  mov     rdx, rsi; struct _SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *
0x1800474ba  call    ?FreeShellInfrastructureHostMapEntry@UserManagerTokenAndShellHandler@@AEAAXPEAU_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY@@H@Z; UserManagerTokenAndShellHandler::FreeShellInfrastructureHostMapEntry(_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *,int)
0x1800474bf  call    cs:__imp_GetProcessHeap
0x1800474c5  mov     rcx, rax; hHeap
0x1800474c8  mov     edx, 8; dwFlags
0x1800474cd  lea     r8d, [rdx+40h]; dwBytes
0x1800474d1  call    cs:__imp_HeapAlloc
0x1800474d7  mov     rsi, rax
0x1800474da  mov     [rsp+0C8h+var_60], rax
0x1800474df  test    rax, rax
0x1800474e2  jnz     loc_180047615
0x1800474e8  lea     ebx, [rax+8]
0x1800474eb  jmp     short loc_180047533
0x1800474ed  mov     ebx, 160h
0x1800474f2  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800474f7  mov     ecx, [rax]
0x1800474f9  cmp     ecx, 2
0x1800474fc  jbe     short loc_180047525
0x1800474fe  mov     dword ptr [rsp+0C8h+arg_0], 80070160h
0x180047509  lea     rcx, [rsp+0C8h+arg_0]
0x180047511  mov     qword ptr [rsp+0C8h+dwMilliseconds], rcx
0x180047516  lea     rdx, byte_18012B085
0x18004751d  mov     rcx, rax
0x180047520  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180047525  mov     r14, [rsp+0C8h+SRWLock]
0x18004752a  mov     rcx, r14; SRWLock
0x18004752d  call    cs:__imp_ReleaseSRWLockExclusive
0x180047533  mov     rcx, [rsp+0C8h+hObject]; hObject
0x180047538  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004753c  jz      short loc_180047544
0x18004753e  call    cs:__imp_CloseHandle
0x180047544  test    rsi, rsi
0x180047547  jz      short loc_180047559
0x180047549  mov     r8d, [rsp+0C8h+arg_18]; int
0x180047551  mov     rdx, rsi; struct _SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *
0x180047554  call    ?FreeShellInfrastructureHostMapEntry@UserManagerTokenAndShellHandler@@AEAAXPEAU_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY@@H@Z; UserManagerTokenAndShellHandler::FreeShellInfrastructureHostMapEntry(_SHELL_INFRASTRUCTURE_HOST_MAP_ENTRY *,int)
0x180047559  test    r13, r13
0x18004755c  jz      short loc_180047572
0x18004755e  call    cs:__imp_GetProcessHeap
0x180047564  mov     rcx, rax; hHeap
0x180047567  mov     r8, r13; lpMem
0x18004756a  xor     edx, edx; dwFlags
0x18004756c  call    cs:__imp_HeapFree
0x180047572  test    ebx, ebx
0x180047574  jle     short loc_18004757F
0x180047576  movzx   ebx, bx
0x180047579  or      ebx, 80070000h
0x18004757f  mov     eax, ebx
0x180047581  add     rsp, 90h
0x180047588  pop     r15
0x18004758a  pop     r14
0x18004758c  pop     r13
0x18004758e  pop     r12
0x180047590  pop     rdi
0x180047591  pop     rsi
0x180047592  pop     rbx
0x180047593  retn
0x180047594  cmp     [rsp+0C8h+arg_18], edi
0x18004759b  jz      loc_18004749C
0x1800475a1  mov     ebx, 160h
0x1800475a6  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800475ab  mov     r9, rax
0x1800475ae  mov     ecx, [rax]
0x1800475b0  cmp     ecx, 2
0x1800475b3  jbe     loc_180047525
0x1800475b9  mov     rdx, 200000000000h
0x1800475c3  mov     rcx, rax
0x1800475c6  call    _tlgKeywordOn
0x1800475cb  test    al, al
0x1800475cd  jz      loc_180047525
0x1800475d3  mov     [rsp+0C8h+var_78], 1000000h
0x1800475dc  mov     dword ptr [rsp+0C8h+arg_0], 80070160h
0x1800475e7  lea     rax, [rsp+0C8h+var_78]
0x1800475ec  mov     qword ptr [rsp+0C8h+dwFlags], rax
0x1800475f1  lea     rax, [rsp+0C8h+arg_0]
0x1800475f9  mov     qword ptr [rsp+0C8h+dwMilliseconds], rax
0x1800475fe  xor     r8d, r8d
0x180047601  lea     rdx, byte_18012B0F3
0x180047608  mov     rcx, r9
0x18004760b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180047610  jmp     loc_180047525
0x180047615  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180047619  mov     [rax], rcx
0x18004761c  mov     [rax+8], rcx
0x180047620  mov     [rax+18h], rcx
0x180047624  mov     [rax+28h], r12b
0x180047628  mov     eax, [rsp+0C8h+var_80]
0x18004762c  mov     [rsi+2Ch], eax
0x18004762f  mov     [rsi+30h], rcx
0x180047633  mov     [rsi+38h], r15d
0x180047637  mov     rax, [rsp+0C8h+arg_0]
0x18004763f  mov     [rsi+40h], rax
0x180047643  xor     r9d, r9d; lpName
0x180047646  xor     r8d, r8d; bInitialState
0x180047649  xor     edx, edx; bManualReset
0x18004764b  xor     ecx, ecx; lpEventAttributes
0x18004764d  call    cs:__imp_CreateEventW
0x180047653  mov     [rsi+18h], rax
0x180047657  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004765b  jnz     short loc_18004766A
0x18004765d  call    cs:__imp_GetLastError
0x180047663  mov     ebx, eax
0x180047665  jmp     loc_180047533
0x18004766a  mov     r12b, dil
0x18004766d  mov     byte ptr [rsp+0C8h+arg_0], dil
0x180047675  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock> `wil::Feature<__WilFeatureTraits_Feature_ShellInfraHostLock>::GetImpl(void)'::`2'::impl
0x18004767c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShellInfraHostLock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellInfraHostLock>::__private_IsEnabled(void)
0x180047681  test    al, al
0x180047683  jz      short loc_180047699
0x180047685  mov     rcx, rbx; SRWLock
0x180047688  call    cs:__imp_AcquireSRWLockExclusive
0x18004768e  mov     r12b, 1
0x180047691  mov     byte ptr [rsp+0C8h+arg_0], r12b
0x180047699  cmp     [r14+0A0h], dil
0x1800476a0  jz      short loc_1800476FA
0x1800476a2  mov     ebx, edi
0x1800476a4  lea     r9, [rsi+20h]; struct _VIRTUAL_ACCOUNT_CONTEXT **
0x1800476a8  mov     qword ptr [rsp+0C8h+dwMilliseconds], rsi; struct _PROCESS_INFORMATION *
0x1800476ad  mov     r8, [r14+80h]; unsigned __int16 *
0x1800476b4  mov     rdx, [rsp+0C8h+arg_10]; void *
0x1800476bc  mov     ecx, [rsp+0C8h+SessionId]; unsigned int
0x1800476c3  call    ?LaunchShellHostAsVirtualAccount@@YAJKPEAXPEAGPEAPEBU_VIRTUAL_ACCOUNT_CONTEXT@@PEAU_PROCESS_INFORMATION@@@Z; LaunchShellHostAsVirtualAccount(ulong,void *,ushort *,_VIRTUAL_ACCOUNT_CONTEXT const * *,_PROCESS_INFORMATION *)
0x1800476c8  mov     r15d, eax
0x1800476cb  test    eax, eax
0x1800476cd  jns     loc_18004784D
0x1800476d3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800476d8  mov     ecx, r15d
0x1800476db  and     ecx, 1FFF0000h
0x1800476e1  cmp     ecx, 70000h
0x1800476e7  jnz     short loc_1800476F2
0x1800476e9  movzx   ebx, r15w
0x1800476ed  jmp     loc_180047845
0x1800476f2  mov     ebx, r15d
0x1800476f5  jmp     loc_180047845
0x1800476fa  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180047700  cmp     eax, [rsp+0C8h+SessionId]
0x180047707  jnz     loc_1800477B6
0x18004770d  cmp     [r14+9Ch], dil
0x180047714  jz      short loc_18004773A
0x180047716  cmp     qword ptr [r14+18h], 0FFFFFFFFFFFFFFFFh
0x18004771b  jnz     short loc_180047722
0x18004771d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180047722  mov     rdx, [r14+18h]; hToken
0x180047726  mov     r8, rsi; lpProcessInformation
0x180047729  mov     rcx, [r14+80h]; unsigned __int16 *
0x180047730  call    ?LaunchProcessAsUser@@YAKPEAGPEAXPEAU_PROCESS_INFORMATION@@@Z; LaunchProcessAsUser(ushort *,void *,_PROCESS_INFORMATION *)
0x180047735  jmp     loc_180047843
0x18004773a  mov     rcx, r14; this
0x18004773d  call    ?WaitForFirstUserToken@UserManagerTokenAndShellHandler@@AEAAKXZ; UserManagerTokenAndShellHandler::WaitForFirstUserToken(void)
0x180047742  mov     ebx, eax
0x180047744  test    eax, eax
0x180047746  jnz     short loc_18004777E
0x180047748  lea     rbx, [r14+20h]
0x18004774c  mov     rcx, rbx; SRWLock
0x18004774f  call    cs:__imp_AcquireSRWLockShared
0x180047755  mov     [rsp+0C8h+var_78], rbx
0x18004775a  mov     r8, rsi; lpProcessInformation
0x18004775d  mov     rdx, [r14+28h]; hToken
0x180047761  mov     rcx, [r14+80h]; unsigned __int16 *
0x180047768  call    ?LaunchProcessAsUser@@YAKPEAGPEAXPEAU_PROCESS_INFORMATION@@@Z; LaunchProcessAsUser(ushort *,void *,_PROCESS_INFORMATION *)
0x18004776d  mov     ebx, eax
0x18004776f  lea     rcx, [rsp+0C8h+var_78]
0x180047774  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180047779  jmp     loc_180047845
0x18004777e  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180047783  mov     ecx, [rax]
0x180047785  cmp     ecx, 2
0x180047788  jbe     loc_18004797D
0x18004778e  mov     dword ptr [rsp+0C8h+arg_0], ebx
0x180047795  lea     rcx, [rsp+0C8h+arg_0]
0x18004779d  mov     qword ptr [rsp+0C8h+dwMilliseconds], rcx
0x1800477a2  lea     rdx, word_18012B03E
0x1800477a9  mov     rcx, rax
0x1800477ac  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800477b1  jmp     loc_18004797D
0x1800477b6  cmp     [r14+98h], dil
0x1800477bd  jnz     short loc_1800477C4
0x1800477bf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800477c4  call    IsWTSEnumerateSessionsWPresent
0x1800477c9  test    al, al
0x1800477cb  jz      loc_180047978
0x1800477d1  lea     rdx, [rsp+0C8h+hObject]; phToken
0x1800477d6  mov     ecx, [rsp+0C8h+SessionId]; SessionId
0x1800477dd  call    cs:__imp_WTSQueryUserToken
0x1800477e3  test    eax, eax
0x1800477e5  jz      short loc_18004783D
0x1800477e7  mov     r9d, 4; TokenInformationLength
0x1800477ed  lea     r8, [rsp+0C8h+SessionId]; TokenInformation
0x1800477f5  lea     edx, [r9+8]; TokenInformationClass
0x1800477f9  mov     rcx, [rsp+0C8h+hObject]; TokenHandle
0x1800477fe  call    cs:__imp_SetTokenInformation
0x180047804  test    eax, eax
0x180047806  jz      short loc_18004783D
0x180047808  mov     r8, [rsp+0C8h+hObject]; void *
0x18004780d  mov     edx, [rsp+0C8h+SessionId]; unsigned int
0x180047814  mov     rcx, r14; this
0x180047817  call    ?RestoreStateFromTokenIfNeeded@UserManagerTokenAndShellHandler@@AEAAJKPEAX@Z; UserManagerTokenAndShellHandler::RestoreStateFromTokenIfNeeded(ulong,void *)
0x18004781c  mov     ebx, eax
0x18004781e  test    eax, eax
0x180047820  js      short loc_18004782C
0x180047822  mov     rdx, [rsp+0C8h+hObject]
0x180047827  jmp     loc_180047726
0x18004782c  and     eax, 1FFF0000h
0x180047831  cmp     eax, 70000h
0x180047836  jnz     short loc_180047845
0x180047838  movzx   ebx, bx
0x18004783b  jmp     short loc_180047845
0x18004783d  call    cs:__imp_GetLastError
0x180047843  mov     ebx, eax
  ... truncated ...
```
