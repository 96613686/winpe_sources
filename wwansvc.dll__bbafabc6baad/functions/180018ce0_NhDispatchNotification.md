# _NhDispatchNotification

- ea: `0x180018ce0`
- end: `0x180018ea4`
- name: `_NhDispatchNotification`
- size: `452`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x180014f1c`
- `0x180016c50`
- `0x180018b08`
- `0x180018ce0`
- `0x180018eac`
- `0x18001918c`
- `0x1800769a4`
- `0x18007a0fc`
- `0x1800aa998`
- `0x1800aad9c`
- `0x1800b6a0c`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018cf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018da8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018cf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018da8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018d08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018d08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018dd2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018e28`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018e28`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018e86`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018e86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e77`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180018d55`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180018d55`

## string_xrefs

- `0x180018d12`: `started notification thread %x`
- `0x180018d31`: `notification thread %x waiting for work`
- `0x180018d68`: `notification thread %x signaled to perform work`
- `0x180018e39`: `notification thread %x signaled to exit by itself`
- `0x180018e53`: `notification thread %x was signaled to exit`

## pseudocode

```c
__int64 __fastcall NhDispatchNotification(LPCRITICAL_SECTION lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbp
  int v3; // r15d
  DWORD v4; // eax
  CWwanManager *Instance; // rax
  LPCRITICAL_SECTION v6; // r14
  _QWORD *p_Type; // rsi
  struct _RTL_CRITICAL_SECTION_DEBUG *v8; // rax
  struct _L2_NOTIFICATION_DATA *v9; // rdi
  struct _WWAN_SAP_MGR *v10; // rcx
  const unsigned __int16 *v11; // rdi
  DWORD CurrentThreadId; // eax

  DebugInfo = lpCriticalSection[3].DebugInfo;
  EnterCriticalSection(lpCriticalSection);
  LODWORD(lpCriticalSection[2].SpinCount) = GetCurrentThreadId();
  LeaveCriticalSection(lpCriticalSection);
  WwanLog::Info(
    "_NhDispatchNotification",
    0,
    L"started notification thread %x",
    LODWORD(lpCriticalSection[2].SpinCount));
  v3 = 1;
  do
  {
    while ( 1 )
    {
      WwanLog::Verbose(
        "_NhDispatchNotification",
        0,
        L"notification thread %x waiting for work",
        LODWORD(lpCriticalSection[2].SpinCount));
      v4 = WaitForMultipleObjects(3u, (const HANDLE *)&lpCriticalSection[1].SpinCount, 0, 0xFFFFFFFF);
      if ( v4 != 1 )
        break;
      WwanLog::Verbose(
        "_NhDispatchNotification",
        0,
        L"notification thread %x signaled to perform work",
        LODWORD(lpCriticalSection[2].SpinCount));
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WWAN_Fix_DispatchNotification_Illegal_CWwanManagerSelectInterface_Exception>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WWAN_Fix_DispatchNotification_Illegal_CWwanManagerSelectInterface_Exception>::GetImpl'::`2'::impl) )
      {
        Instance = CWwanManager::GetInstance();
        CWwanManager::SelectInterface(Instance, (const struct _GUID *)&lpCriticalSection[2].OwningThread, 0);
      }
      v6 = lpCriticalSection + 1;
      while ( 1 )
      {
        EnterCriticalSection(lpCriticalSection);
        p_Type = &v6->DebugInfo->Type;
        if ( v6->DebugInfo->CriticalSection != v6
          || (v8 = (struct _RTL_CRITICAL_SECTION_DEBUG *)*p_Type, *(_QWORD **)(*p_Type + 8LL) != p_Type) )
        {
          __fastfail(3u);
        }
        v6->DebugInfo = v8;
        v8->CriticalSection = v6;
        LeaveCriticalSection(lpCriticalSection);
        if ( v6 == (LPCRITICAL_SECTION)p_Type )
          break;
        v9 = (struct _L2_NOTIFICATION_DATA *)p_Type[2];
        if ( (unsigned int)IsClientNotification(v9->NotificationSource, v9->NotificationCode) )
          _WwanSapMgrSendNotification(v10, v9, 0);
        if ( v9->NotificationSource == 16 )
          Wwan2SapMgrSendNotification(v9, 0);
        PublishSebNotification(v9);
        WwanNhFreeNotification(v9);
        WwanMemFree(p_Type);
      }
      if ( !WaitForSingleObject(DebugInfo, 0) )
      {
        v3 = 0;
        v11 = L"notification thread %x signaled to exit by itself";
        CurrentThreadId = GetCurrentThreadId();
        goto LABEL_18;
      }
    }
  }
  while ( v4 );
  CurrentThreadId = lpCriticalSection[2].SpinCount;
  v11 = L"notification thread %x was signaled to exit";
LABEL_18:
  WwanLog::Info("_NhDispatchNotification", 0, v11, CurrentThreadId);
  if ( DebugInfo != (PRTL_CRITICAL_SECTION_DEBUG)-1LL )
    CloseHandle(DebugInfo);
  if ( v3 )
    SetEvent(*(HANDLE *)&lpCriticalSection[2].LockCount);
  return 0;
}

```

## disassembly

```asm
0x180018ce0  push    rbx
0x180018ce2  push    rbp
0x180018ce3  push    rsi
0x180018ce4  push    rdi
0x180018ce5  push    r12
0x180018ce7  push    r14
0x180018ce9  push    r15
0x180018ceb  sub     rsp, 20h
0x180018cef  mov     rbp, [rcx+78h]
0x180018cf3  mov     rbx, rcx
0x180018cf6  call    cs:__imp_EnterCriticalSection
0x180018cfc  call    cs:__imp_GetCurrentThreadId
0x180018d02  mov     rcx, rbx; lpCriticalSection
0x180018d05  mov     [rbx+70h], eax
0x180018d08  call    cs:__imp_LeaveCriticalSection
0x180018d0e  mov     r9d, [rbx+70h]
0x180018d12  lea     r8, aStartedNotific; "started notification thread %x"
0x180018d19  xor     edx, edx; struct _GUID *
0x180018d1b  lea     rcx, aNhdispatchnoti; "_NhDispatchNotification"
0x180018d22  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180018d27  mov     r15d, 1
0x180018d2d  mov     r9d, [rbx+70h]
0x180018d31  lea     r8, aNotificationTh_0; "notification thread %x waiting for work"
0x180018d38  xor     edx, edx; struct _GUID *
0x180018d3a  lea     rcx, aNhdispatchnoti; "_NhDispatchNotification"
0x180018d41  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x180018d46  xor     r8d, r8d; bWaitAll
0x180018d49  lea     rdx, [rbx+48h]; lpHandles
0x180018d4d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180018d51  lea     ecx, [r8+3]; nCount
0x180018d55  call    cs:__imp_WaitForMultipleObjects
0x180018d5b  cmp     eax, r15d
0x180018d5e  jnz     loc_180018E48
0x180018d64  mov     r9d, [rbx+70h]
0x180018d68  lea     r8, aNotificationTh_1; "notification thread %x signaled to perf"...
0x180018d6f  xor     edx, edx; struct _GUID *
0x180018d71  lea     rcx, aNhdispatchnoti; "_NhDispatchNotification"
0x180018d78  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x180018d7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WWAN_Fix_DispatchNotification_Illegal_CWwanManagerSelectInterface_Exception@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WWAN_Fix_DispatchNotification_Illegal_CWwanManagerSelectInterface_Exception@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WWAN_Fix_DispatchNotification_Illegal_CWwanManagerSelectInterface_Exception> `wil::Feature<__WilFeatureTraits_Feature_WWAN_Fix_DispatchNotification_Illegal_CWwanManagerSelectInterface_Exception>::GetImpl(void)'::`2'::impl
0x180018d84  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WWAN_Fix_DispatchNotification_Illegal_CWwanManagerSelectInterface_Exception@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WWAN_Fix_DispatchNotification_Illegal_CWwanManagerSelectInterface_Exception>::__private_IsEnabled(void)
0x180018d89  test    al, al
0x180018d8b  jnz     short loc_180018DA1
0x180018d8d  call    ?GetInstance@CWwanManager@@SAPEAV1@XZ; CWwanManager::GetInstance(void)
0x180018d92  lea     rdx, [rbx+60h]; struct _GUID *
0x180018d96  xor     r8d, r8d; int
0x180018d99  mov     rcx, rax; this
0x180018d9c  call    ?SelectInterface@CWwanManager@@AEAAPEAVCWwanNetworkInterface@@PEBU_GUID@@H@Z; CWwanManager::SelectInterface(_GUID const *,int)
0x180018da1  lea     r14, [rbx+28h]
0x180018da5  mov     rcx, rbx; lpCriticalSection
0x180018da8  call    cs:__imp_EnterCriticalSection
0x180018dae  mov     rsi, [r14]
0x180018db1  cmp     [rsi+8], r14
0x180018db5  jnz     loc_180018E9D
0x180018dbb  mov     rax, [rsi]
0x180018dbe  cmp     [rax+8], rsi
0x180018dc2  jnz     loc_180018E9D
0x180018dc8  mov     [r14], rax
0x180018dcb  mov     rcx, rbx; lpCriticalSection
0x180018dce  mov     [rax+8], r14
0x180018dd2  call    cs:__imp_LeaveCriticalSection
0x180018dd8  cmp     r14, rsi
0x180018ddb  jz      short loc_180018E23
0x180018ddd  mov     rdi, [rsi+10h]
0x180018de1  mov     edx, [rdi+4]
0x180018de4  mov     ecx, [rdi]
0x180018de6  call    _IsClientNotification
0x180018deb  test    eax, eax
0x180018ded  jz      short loc_180018DFA
0x180018def  xor     r8d, r8d; unsigned int
0x180018df2  mov     rdx, rdi; struct _L2_NOTIFICATION_DATA *
0x180018df5  call    ?_WwanSapMgrSendNotification@@YAXPEAU_WWAN_SAP_MGR@@PEAU_L2_NOTIFICATION_DATA@@K@Z; _WwanSapMgrSendNotification(_WWAN_SAP_MGR *,_L2_NOTIFICATION_DATA *,ulong)
0x180018dfa  cmp     dword ptr [rdi], 10h
0x180018dfd  jnz     short loc_180018E09
0x180018dff  xor     edx, edx; unsigned int
0x180018e01  mov     rcx, rdi; struct _L2_NOTIFICATION_DATA *
0x180018e04  call    ?Wwan2SapMgrSendNotification@@YAXPEAU_L2_NOTIFICATION_DATA@@K@Z; Wwan2SapMgrSendNotification(_L2_NOTIFICATION_DATA *,ulong)
0x180018e09  mov     rcx, rdi
0x180018e0c  call    _PublishSebNotification
0x180018e11  mov     rcx, rdi
0x180018e14  call    WwanNhFreeNotification
0x180018e19  mov     rcx, rsi
0x180018e1c  call    WwanMemFree
0x180018e21  jmp     short loc_180018DA5
0x180018e23  xor     edx, edx; dwMilliseconds
0x180018e25  mov     rcx, rbp; hHandle
0x180018e28  call    cs:__imp_WaitForSingleObject
0x180018e2e  test    eax, eax
0x180018e30  jnz     loc_180018D2D
0x180018e36  xor     r15d, r15d
0x180018e39  lea     rdi, aNotificationTh_2; "notification thread %x signaled to exit"...
0x180018e40  call    cs:__imp_GetCurrentThreadId
0x180018e46  jmp     short loc_180018E5A
0x180018e48  test    eax, eax
0x180018e4a  jnz     loc_180018D2D
0x180018e50  mov     eax, [rbx+70h]
0x180018e53  lea     rdi, aNotificationTh; "notification thread %x was signaled to "...
0x180018e5a  mov     r9d, eax
0x180018e5d  lea     rcx, aNhdispatchnoti; "_NhDispatchNotification"
0x180018e64  mov     r8, rdi; unsigned __int16 *
0x180018e67  xor     edx, edx; struct _GUID *
0x180018e69  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180018e6e  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180018e72  jz      short loc_180018E7D
0x180018e74  mov     rcx, rbp; hObject
0x180018e77  call    cs:__imp_CloseHandle
0x180018e7d  test    r15d, r15d
0x180018e80  jz      short loc_180018E8C
0x180018e82  mov     rcx, [rbx+58h]; hEvent
0x180018e86  call    cs:__imp_SetEvent
0x180018e8c  xor     eax, eax
0x180018e8e  add     rsp, 20h
0x180018e92  pop     r15
0x180018e94  pop     r14
0x180018e96  pop     r12
0x180018e98  pop     rdi
0x180018e99  pop     rsi
0x180018e9a  pop     rbp
0x180018e9b  pop     rbx
0x180018e9c  retn
0x180018e9d  mov     ecx, 3
0x180018ea2  int     29h; Win8: RtlFailFast(ecx)
```
