# CWaitItem::IssueWait(int)

- ea: `0x18000c7e0`
- end: `0x18000cc62`
- name: `?IssueWait@CWaitItem@@IEAAJH@Z`
- size: `1154`
- prototype: `__int64 __fastcall(PVOID Context, int)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b9e0`
- `0x18000bc00`
- `0x18000c020`
- `0x18000c6ec`
- `0x18002a9c0`
- `0x18002b4d0`

## callees

- `0x180005b40`
- `0x18000c478`
- `0x18000c7e0`
- `0x180031ad4`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000cc45`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000cc45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c81e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c81e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ca8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ca8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cba0`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000c9e6`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000c9e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c9d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c9d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c9a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c9a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c8d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c8d1`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000ca22`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000cbc4`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000ca22`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000cbc4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000c80e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000c80e`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800333ce`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800333ce`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000c934`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000c934`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000cb33`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000cb33`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000cad7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000cad7`

## string_xrefs

- `0x18000caa5`: `CWaitItem::IsSystemProcess`
- `0x18000cb06`: `CWaitItem::IsSystemProcess`
- `0x18000cb62`: `CWaitItem::IsSystemProcess`
- `0x18000caaf`: `new pSid failed: 0x%x in %s`
- `0x18000ca6d`: `this->lHasCompletedSystemProcessCheck is already 1 - no need to do the check again.`
- `0x18000cb6c`: `CheckTokenMembership failed: 0x%x in %s`
- `0x18000cb10`: `CreateWellKnownSid failed: 0x%x in %s`
- `0x18000ca11`: `ProcessIdToSessionId failed : 0x%X`
- `0x18000cbb3`: `IsSystemProcess failed : 0x%X`
- `0x18000cbef`: `Winsta.dll`

## pseudocode

```c
__int64 __fastcall CWaitItem::IssueWait(char *Context, int a2)
{
  signed int v3; // eax
  unsigned int v4; // edi
  _QWORD *v6; // rdi
  void *v7; // rcx
  __int32 v8; // r14d
  unsigned int v9; // edx
  MIDL_STUBLESS_PROXY_INFO *v10; // rcx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  signed int v13; // esi
  void *v14; // r12
  HLOCAL v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  const WCHAR *v18; // rdx
  DWORD v19; // ecx
  char IsEnabled; // al
  DWORD pSessionId; // [rsp+98h] [rbp+10h] BYREF
  SIZE_T uBytes; // [rsp+A0h] [rbp+18h] BYREF
  WINBOOL IsMember; // [rsp+A8h] [rbp+20h] BYREF

  if ( a2 )
  {
    v6 = Context + 1576;
    v7 = (void *)*((_QWORD *)Context + 197);
    if ( v7 )
    {
      LocalFree(v7);
      v8 = 0;
      *v6 = 0;
      *((_DWORD *)Context + 396) = 0;
    }
    else
    {
      v8 = 0;
    }
    uBytes = (SIZE_T)(Context + 1504);
    EnterCriticalSection((LPCRITICAL_SECTION)(Context + 1504));
    if ( *((_DWORD *)Context + 50) == 1 )
    {
      StateTracker<enum CWaitItem::WaitItemCallState>::operator=(Context + 200, 2);
      if ( *((_DWORD *)Context + 387) )
      {
        v9 = 1;
        v10 = (MIDL_STUBLESS_PROXY_INFO *)&stru_1800350F0;
      }
      else
      {
        v9 = 2;
        v10 = (MIDL_STUBLESS_PROXY_INFO *)&stru_1800352C0;
      }
      Ndr64AsyncClientCall(v10, v9, 0, Context + 88, *((_QWORD *)Context + 10), v6, Context + 1584);
      _InterlockedIncrement((volatile signed __int32 *)Context + 2);
      v4 = 0;
    }
    else
    {
      v4 = -2147024593;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 1504));
    if ( (v4 & 0x80000000) != 0 || *((_QWORD *)Context + 186) )
      return v4;
    pSessionId = 0xFFFF;
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "ProcessIdToSessionId failed : 0x%X", LastError);
    }
    if ( pSessionId == (unsigned int)WTSGetServiceSessionId() || *((_DWORD *)Context + 388) )
    {
LABEL_44:
      if ( pSessionId == (unsigned int)WTSGetServiceSessionId()
        || *((_DWORD *)Context + 388) == 1 && *((_DWORD *)Context + 389) == 1 )
      {
        _DbgPrintMessage(
          1,
          "Process is in Session %d or process is running under System context : %d.",
          pSessionId,
          *((_DWORD *)Context + 389));
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaitItemPinsModule>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaitItemPinsModule>::GetImpl'::`2'::impl);
        v18 = &CWindowNotification::g_WindowNotificationListHead;
        v19 = 5;
        if ( !IsEnabled )
          v19 = 4;
      }
      else
      {
        v18 = L"Winsta.dll";
        v19 = 1;
      }
      GetModuleHandleExW(v19, v18, (HMODULE *)Context + 186);
      return v4;
    }
    LODWORD(uBytes) = 68;
    IsMember = 0;
    if ( *((_DWORD *)Context + 388) == 1 )
    {
      v13 = 0;
      v14 = 0;
      _DbgPrintMessage(1, "this->lHasCompletedSystemProcessCheck is already 1 - no need to do the check again.");
      goto LABEL_42;
    }
    v15 = LocalAlloc(0x40u, (unsigned int)uBytes);
    v14 = v15;
    if ( !v15 )
    {
      v13 = -2147024882;
      _DbgPrintMessage(8, "new pSid failed: 0x%x in %s", -2147024882, "CWaitItem::IsSystemProcess");
      goto LABEL_42;
    }
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, v15, (DWORD *)&uBytes) )
    {
      v13 = 0;
    }
    else
    {
      v16 = GetLastError();
      v13 = v16;
      if ( v16 > 0 )
        v13 = (unsigned __int16)v16 | 0x80070000;
      if ( v13 < 0 )
      {
        _DbgPrintMessage(8, "CreateWellKnownSid failed: 0x%x in %s", v13, "CWaitItem::IsSystemProcess");
LABEL_42:
        LocalFree(v14);
        if ( v13 < 0 )
          _DbgPrintMessage(8, "IsSystemProcess failed : 0x%X", v13);
        goto LABEL_44;
      }
    }
    if ( CheckTokenMembership(0, v14, &IsMember) )
      goto LABEL_41;
    v17 = GetLastError();
    v13 = v17;
    if ( v17 > 0 )
      v13 = (unsigned __int16)v17 | 0x80070000;
    if ( v13 >= 0 )
    {
LABEL_41:
      LOBYTE(v8) = IsMember != 0;
      _InterlockedExchange((volatile __int32 *)Context + 389, v8);
      _InterlockedExchange((volatile __int32 *)Context + 388, 1);
    }
    else
    {
      _DbgPrintMessage(8, "CheckTokenMembership failed: 0x%x in %s", v13, "CWaitItem::IsSystemProcess");
    }
    goto LABEL_42;
  }
  _InterlockedIncrement((volatile signed __int32 *)Context + 2);
  if ( QueueUserWorkItem(CWaitItem::staticIssueWait, Context, 0) )
    return 0;
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Context + 2, 0xFFFFFFFF) == 1 && Context )
  {
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)Context + 16LL))(Context, 1);
    return v4;
  }
  return v4;
}

```

## disassembly

```asm
0x18000c7e0  mov     [rsp+arg_0], rcx
0x18000c7e5  push    rbx
0x18000c7e6  push    rsi
0x18000c7e7  push    rdi
0x18000c7e8  push    r12
0x18000c7ea  push    r14
0x18000c7ec  push    r15
0x18000c7ee  sub     rsp, 58h
0x18000c7f2  mov     rbx, rcx
0x18000c7f5  test    edx, edx
0x18000c7f7  jnz     loc_18000C88F
0x18000c7fd  lock inc dword ptr [rcx+8]
0x18000c801  xor     r8d, r8d; Flags
0x18000c804  mov     rdx, rcx; Context
0x18000c807  lea     rcx, ?staticIssueWait@CWaitItem@@CAKPEAX@Z; Function
0x18000c80e  call    cs:__imp_QueueUserWorkItem
0x18000c815  nop     dword ptr [rax+rax+00h]
0x18000c81a  test    eax, eax
0x18000c81c  jnz     short loc_18000C87A
0x18000c81e  call    cs:__imp_GetLastError
0x18000c825  nop     dword ptr [rax+rax+00h]
0x18000c82a  mov     edi, eax
0x18000c82c  test    eax, eax
0x18000c82e  jle     short loc_18000C839
0x18000c830  movzx   edi, ax
0x18000c833  or      edi, 80070000h
0x18000c839  mov     eax, 0FFFFFFFFh
0x18000c83e  lock xadd [rbx+8], eax
0x18000c843  cmp     eax, 1
0x18000c846  jnz     loc_18000CC51
0x18000c84c  test    rbx, rbx
0x18000c84f  jz      loc_18000CC51
0x18000c855  mov     rax, [rbx]
0x18000c858  mov     edx, 1
0x18000c85d  mov     rcx, rbx
0x18000c860  mov     rax, [rax+10h]
0x18000c864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c869  mov     eax, edi
0x18000c86b  add     rsp, 58h
0x18000c86f  pop     r15
0x18000c871  pop     r14
0x18000c873  pop     r12
0x18000c875  pop     rdi
0x18000c876  pop     rsi
0x18000c877  pop     rbx
0x18000c878  retn
0x18000c87a  xor     r14d, r14d
0x18000c87d  mov     eax, r14d
0x18000c880  add     rsp, 58h
0x18000c884  pop     r15
0x18000c886  pop     r14
0x18000c888  pop     r12
0x18000c88a  pop     rdi
0x18000c88b  pop     rsi
0x18000c88c  pop     rbx
0x18000c88d  retn
0x18000c88f  lea     rdi, [rcx+628h]
0x18000c896  mov     rcx, [rdi]; hMem
0x18000c899  lea     r15, [rbx+630h]
0x18000c8a0  test    rcx, rcx
0x18000c8a3  jz      short loc_18000C8BC
0x18000c8a5  call    cs:__imp_LocalFree
0x18000c8ac  nop     dword ptr [rax+rax+00h]
0x18000c8b1  xor     r14d, r14d
0x18000c8b4  mov     [rdi], r14
0x18000c8b7  mov     [r15], r14d
0x18000c8ba  jmp     short loc_18000C8BF
0x18000c8bc  xor     r14d, r14d
0x18000c8bf  lea     rsi, [rbx+5E0h]
0x18000c8c6  mov     [rsp+88h+uBytes], rsi
0x18000c8ce  mov     rcx, rsi; lpCriticalSection
0x18000c8d1  call    cs:__imp_EnterCriticalSection
0x18000c8d8  nop     dword ptr [rax+rax+00h]
0x18000c8dd  lea     rcx, [rbx+0C8h]
0x18000c8e4  cmp     dword ptr [rcx], 1
0x18000c8e7  jnz     loc_18000C99B
0x18000c8ed  mov     edx, 2
0x18000c8f2  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000c8f7  lea     r9, [rbx+58h]
0x18000c8fb  mov     rax, [rbx+50h]
0x18000c8ff  mov     [rsp+88h+var_58], r15
0x18000c904  xor     r8d, r8d; pReturnValue
0x18000c907  mov     [rsp+88h+var_60], rdi
0x18000c90c  mov     [rsp+88h+var_68], rax
0x18000c911  cmp     [rbx+60Ch], r8d
0x18000c918  jz      short loc_18000C928
0x18000c91a  mov     edx, 1
0x18000c91f  lea     rcx, stru_1800350F0
0x18000c926  jmp     short loc_18000C934
0x18000c928  mov     edx, 2; nProcNum
0x18000c92d  lea     rcx, stru_1800352C0; pProxyInfo
0x18000c934  call    cs:__imp_Ndr64AsyncClientCall
0x18000c93b  nop     dword ptr [rax+rax+00h]
0x18000c940  lock inc dword ptr [rbx+8]
0x18000c944  mov     edi, r14d
0x18000c947  mov     [rsp+88h+var_48], r14d
0x18000c94c  jmp     short loc_18000C9A0
0x18000c94e  mov     edi, eax
0x18000c950  mov     rbx, [rsp+88h+arg_0]
0x18000c958  lea     rcx, [rbx+0C8h]
0x18000c95f  mov     edx, 1
0x18000c964  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x18000c969  test    edi, edi
0x18000c96b  jle     short loc_18000C976
0x18000c96d  movzx   edi, di
0x18000c970  or      edi, 80070000h
0x18000c976  mov     [rsp+88h+var_48], edi
0x18000c97a  mov     r8d, edi
0x18000c97d  lea     rdx, aRpcwaitasyncno; "RpcWaitAsyncNotificationEx threw an exc"...
0x18000c984  mov     ecx, 8; int
0x18000c989  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c98e  xor     r14d, r14d
0x18000c991  mov     rsi, [rsp+88h+uBytes]
0x18000c999  jmp     short loc_18000C9A0
0x18000c99b  mov     edi, 8007012Fh
0x18000c9a0  mov     rcx, rsi; lpCriticalSection
0x18000c9a3  call    cs:__imp_LeaveCriticalSection
0x18000c9aa  nop     dword ptr [rax+rax+00h]
0x18000c9af  test    edi, edi
0x18000c9b1  js      loc_18000CC51
0x18000c9b7  cmp     qword ptr [rbx+5D0h], 0
0x18000c9bf  jnz     loc_18000CC51
0x18000c9c5  mov     [rsp+88h+pSessionId], 0FFFFh
0x18000c9d0  call    cs:__imp_GetCurrentProcessId
0x18000c9d7  nop     dword ptr [rax+rax+00h]
0x18000c9dc  mov     ecx, eax; dwProcessId
0x18000c9de  lea     rdx, [rsp+88h+pSessionId]; pSessionId
0x18000c9e6  call    cs:__imp_ProcessIdToSessionId
0x18000c9ed  nop     dword ptr [rax+rax+00h]
0x18000c9f2  test    eax, eax
0x18000c9f4  jnz     short loc_18000CA22
0x18000c9f6  call    cs:__imp_GetLastError
0x18000c9fd  nop     dword ptr [rax+rax+00h]
0x18000ca02  test    eax, eax
0x18000ca04  jle     short loc_18000CA0E
0x18000ca06  movzx   eax, ax
0x18000ca09  or      eax, 80070000h
0x18000ca0e  mov     r8d, eax
0x18000ca11  lea     rdx, aProcessidtoses; "ProcessIdToSessionId failed : 0x%X"
0x18000ca18  mov     ecx, 8; int
0x18000ca1d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ca22  call    cs:__imp_WTSGetServiceSessionId
0x18000ca29  nop     dword ptr [rax+rax+00h]
0x18000ca2e  cmp     [rsp+88h+pSessionId], eax
0x18000ca35  jz      loc_18000CBC4
0x18000ca3b  mov     eax, [rbx+610h]
0x18000ca41  test    eax, eax
0x18000ca43  jnz     loc_18000CBC4
0x18000ca49  mov     dword ptr [rsp+88h+uBytes], 44h ; 'D'
0x18000ca54  mov     [rsp+88h+IsMember], r14d
0x18000ca5c  mov     eax, [rbx+610h]
0x18000ca62  cmp     eax, 1
0x18000ca65  jnz     short loc_18000CA80
0x18000ca67  mov     esi, r14d
0x18000ca6a  mov     r12, r14
0x18000ca6d  lea     rdx, aThisLhascomple; "this->lHasCompletedSystemProcessCheck i"...
0x18000ca74  mov     ecx, eax; int
0x18000ca76  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ca7b  jmp     loc_18000CB9D
0x18000ca80  mov     edx, dword ptr [rsp+88h+uBytes]; uBytes
0x18000ca87  mov     ecx, 40h ; '@'; uFlags
0x18000ca8c  call    cs:__imp_LocalAlloc
0x18000ca93  nop     dword ptr [rax+rax+00h]
0x18000ca98  mov     r12, rax
0x18000ca9b  test    rax, rax
0x18000ca9e  jnz     short loc_18000CAC5
0x18000caa0  mov     esi, 8007000Eh
0x18000caa5  lea     r9, aCwaititemIssys; "CWaitItem::IsSystemProcess"
0x18000caac  mov     r8d, esi
0x18000caaf  lea     rdx, aNewPsidFailed0; "new pSid failed: 0x%x in %s"
0x18000cab6  mov     ecx, 8; int
0x18000cabb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cac0  jmp     loc_18000CB9D
0x18000cac5  lea     r9, [rsp+88h+uBytes]; cbSid
0x18000cacd  mov     r8, r12; pSid
0x18000cad0  xor     edx, edx; DomainSid
0x18000cad2  mov     ecx, 16h; WellKnownSidType
0x18000cad7  call    cs:__imp_CreateWellKnownSid
0x18000cade  nop     dword ptr [rax+rax+00h]
0x18000cae3  test    eax, eax
0x18000cae5  jnz     short loc_18000CB23
0x18000cae7  call    cs:__imp_GetLastError
0x18000caee  nop     dword ptr [rax+rax+00h]
0x18000caf3  mov     esi, eax
0x18000caf5  test    eax, eax
0x18000caf7  jle     short loc_18000CB02
0x18000caf9  movzx   esi, ax
0x18000cafc  or      esi, 80070000h
0x18000cb02  test    esi, esi
0x18000cb04  jns     short loc_18000CB26
0x18000cb06  lea     r9, aCwaititemIssys; "CWaitItem::IsSystemProcess"
0x18000cb0d  mov     r8d, esi
0x18000cb10  lea     rdx, aCreatewellknow_0; "CreateWellKnownSid failed: 0x%x in %s"
0x18000cb17  mov     ecx, 8; int
0x18000cb1c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cb21  jmp     short loc_18000CB9D
0x18000cb23  mov     esi, r14d
0x18000cb26  lea     r8, [rsp+88h+IsMember]; IsMember
0x18000cb2e  mov     rdx, r12; SidToCheck
0x18000cb31  xor     ecx, ecx; TokenHandle
0x18000cb33  call    cs:__imp_CheckTokenMembership
0x18000cb3a  nop     dword ptr [rax+rax+00h]
0x18000cb3f  test    eax, eax
0x18000cb41  jnz     short loc_18000CB7F
0x18000cb43  call    cs:__imp_GetLastError
0x18000cb4a  nop     dword ptr [rax+rax+00h]
0x18000cb4f  mov     esi, eax
0x18000cb51  test    eax, eax
0x18000cb53  jle     short loc_18000CB5E
0x18000cb55  movzx   esi, ax
0x18000cb58  or      esi, 80070000h
0x18000cb5e  test    esi, esi
0x18000cb60  jns     short loc_18000CB7F
0x18000cb62  lea     r9, aCwaititemIssys; "CWaitItem::IsSystemProcess"
0x18000cb69  mov     r8d, esi
0x18000cb6c  lea     rdx, aChecktokenmemb_0; "CheckTokenMembership failed: 0x%x in %s"
0x18000cb73  mov     ecx, 8; int
0x18000cb78  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cb7d  jmp     short loc_18000CB9D
0x18000cb7f  cmp     [rsp+88h+IsMember], 0
0x18000cb87  setnz   r14b
0x18000cb8b  xchg    r14d, [rbx+614h]
0x18000cb92  mov     eax, 1
0x18000cb97  xchg    eax, [rbx+610h]
0x18000cb9d  mov     rcx, r12; hMem
0x18000cba0  call    cs:__imp_LocalFree
0x18000cba7  nop     dword ptr [rax+rax+00h]
0x18000cbac  test    esi, esi
0x18000cbae  jns     short loc_18000CBC4
0x18000cbb0  mov     r8d, esi
0x18000cbb3  lea     rdx, aIssystemproces; "IsSystemProcess failed : 0x%X"
0x18000cbba  mov     ecx, 8; int
0x18000cbbf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cbc4  call    cs:__imp_WTSGetServiceSessionId
0x18000cbcb  nop     dword ptr [rax+rax+00h]
0x18000cbd0  cmp     [rsp+88h+pSessionId], eax
0x18000cbd7  jz      short loc_18000CBFD
0x18000cbd9  mov     eax, [rbx+610h]
0x18000cbdf  cmp     eax, 1
0x18000cbe2  jnz     short loc_18000CBEF
0x18000cbe4  mov     eax, [rbx+614h]
0x18000cbea  cmp     eax, 1
0x18000cbed  jz      short loc_18000CBFD
0x18000cbef  lea     rdx, aWinstaDll_1; "Winsta.dll"
0x18000cbf6  mov     ecx, 1
0x18000cbfb  jmp     short loc_18000CC3E
0x18000cbfd  mov     r9d, [rbx+614h]
0x18000cc04  mov     r8d, [rsp+88h+pSessionId]
0x18000cc0c  lea     rdx, aProcessIsInSes; "Process is in Session %d or process is "...
0x18000cc13  mov     ecx, 1; int
0x18000cc18  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cc1d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaitItemPinsModule@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaitItemPinsModule@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaitItemPinsModule> `wil::Feature<__WilFeatureTraits_Feature_WaitItemPinsModule>::GetImpl(void)'::`2'::impl
0x18000cc24  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaitItemPinsModule@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaitItemPinsModule>::__private_IsEnabled(void)
0x18000cc29  lea     rdx, ?g_WindowNotificationListHead@CWindowNotification@@2U_LIST_ENTRY@@A; lpModuleName
0x18000cc30  test    al, al
0x18000cc32  mov     ecx, 5
0x18000cc37  jnz     short loc_18000CC3E
0x18000cc39  mov     ecx, 4; dwFlags
0x18000cc3e  lea     r8, [rbx+5D0h]; phModule
0x18000cc45  call    cs:__imp_GetModuleHandleExW
0x18000cc4c  nop     dword ptr [rax+rax+00h]
0x18000cc51  mov     eax, edi
0x18000cc53  add     rsp, 58h
0x18000cc57  pop     r15
0x18000cc59  pop     r14
0x18000cc5b  pop     r12
0x18000cc5d  pop     rdi
0x18000cc5e  pop     rsi
0x18000cc5f  pop     rbx
0x18000cc60  retn
0x1800333c0  push    rbp
0x1800333c2  sub     rsp, 40h
0x1800333c6  mov     rbp, rdx
0x1800333c9  mov     rcx, [rcx]
0x1800333cc  mov     ecx, [rcx]; ExceptionCode
0x1800333ce  call    cs:__imp_I_RpcExceptionFilter
0x1800333d5  nop     dword ptr [rax+rax+00h]
0x1800333da  nop
0x1800333db  add     rsp, 40h
0x1800333df  pop     rbp
0x1800333e0  retn
```
