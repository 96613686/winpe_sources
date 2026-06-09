# CWaitItem::IssueWait(int)

- ea: `0x180002990`
- end: `0x180002d8e`
- name: `?IssueWait@CWaitItem@@IEAAJH@Z`
- size: `1022`
- prototype: `__int64 __fastcall(PVOID Context, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180001c70`
- `0x180001e70`
- `0x180002250`
- `0x1800028a8`
- `0x180028de0`
- `0x180029890`

## callees

- `0x180002654`
- `0x180002990`
- `0x180007890`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002d78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002bfe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002bfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002cf4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180002b6a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180002b6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002b5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a6d`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180002b9a`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180002d12`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180002b9a`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180002d12`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800029be`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800029be`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002ffde`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002ffde`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180002aca`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180002aca`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180002c93`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180002c93`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180002c43`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180002c43`

## string_xrefs

- `0x180002c11`: `CWaitItem::IsSystemProcess`
- `0x180002c66`: `CWaitItem::IsSystemProcess`
- `0x180002cb6`: `CWaitItem::IsSystemProcess`
- `0x180002c1b`: `new pSid failed: 0x%x in %s`
- `0x180002bdf`: `this->lHasCompletedSystemProcessCheck is already 1 - no need to do the check again.`
- `0x180002cc0`: `CheckTokenMembership failed: 0x%x in %s`
- `0x180002c70`: `CreateWellKnownSid failed: 0x%x in %s`
- `0x180002b89`: `ProcessIdToSessionId failed : 0x%X`
- `0x180002d01`: `IsSystemProcess failed : 0x%X`
- `0x180002d37`: `Winsta.dll`

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
  void *v14; // r15
  HLOCAL v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  const WCHAR *v18; // rdx
  DWORD v19; // ecx
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
        v10 = (MIDL_STUBLESS_PROXY_INFO *)&stru_180032018;
      }
      else
      {
        v9 = 2;
        v10 = (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo;
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
        v18 = &CWindowNotification::g_WindowNotificationListHead;
        v19 = 5;
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
0x180002990  mov     [rsp+arg_0], rcx
0x180002995  push    rbx
0x180002996  push    rsi
0x180002997  push    rdi
0x180002998  push    r12
0x18000299a  push    r14
0x18000299c  push    r15
0x18000299e  sub     rsp, 58h
0x1800029a2  mov     rbx, rcx
0x1800029a5  test    edx, edx
0x1800029a7  jnz     loc_180002A31
0x1800029ad  lock inc dword ptr [rcx+8]
0x1800029b1  xor     r8d, r8d; Flags
0x1800029b4  mov     rdx, rcx; Context
0x1800029b7  lea     rcx, ?staticIssueWait@CWaitItem@@CAKPEAX@Z; Function
0x1800029be  call    cs:__imp_QueueUserWorkItem
0x1800029c4  test    eax, eax
0x1800029c6  jnz     short loc_180002A1D
0x1800029c8  call    cs:__imp_GetLastError
0x1800029ce  mov     edi, eax
0x1800029d0  test    eax, eax
0x1800029d2  jle     short loc_1800029DD
0x1800029d4  movzx   edi, ax
0x1800029d7  or      edi, 80070000h
0x1800029dd  mov     eax, 0FFFFFFFFh
0x1800029e2  lock xadd [rbx+8], eax
0x1800029e7  cmp     eax, 1
0x1800029ea  jnz     loc_180002D7E
0x1800029f0  test    rbx, rbx
0x1800029f3  jz      loc_180002D7E
0x1800029f9  mov     rax, [rbx]
0x1800029fc  mov     edx, 1
0x180002a01  mov     rcx, rbx
0x180002a04  mov     rax, [rax+10h]
0x180002a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0d  mov     eax, edi
0x180002a0f  add     rsp, 58h
0x180002a13  pop     r15
0x180002a15  pop     r14
0x180002a17  pop     r12
0x180002a19  pop     rdi
0x180002a1a  pop     rsi
0x180002a1b  pop     rbx
0x180002a1c  retn
0x180002a1d  xor     r14d, r14d
0x180002a20  mov     eax, r14d
0x180002a23  add     rsp, 58h
0x180002a27  pop     r15
0x180002a29  pop     r14
0x180002a2b  pop     r12
0x180002a2d  pop     rdi
0x180002a2e  pop     rsi
0x180002a2f  pop     rbx
0x180002a30  retn
0x180002a31  lea     rdi, [rcx+628h]
0x180002a38  mov     rcx, [rdi]; hMem
0x180002a3b  lea     r15, [rbx+630h]
0x180002a42  test    rcx, rcx
0x180002a45  jz      short loc_180002A58
0x180002a47  call    cs:__imp_LocalFree
0x180002a4d  xor     r14d, r14d
0x180002a50  mov     [rdi], r14
0x180002a53  mov     [r15], r14d
0x180002a56  jmp     short loc_180002A5B
0x180002a58  xor     r14d, r14d
0x180002a5b  lea     rsi, [rbx+5E0h]
0x180002a62  mov     [rsp+88h+uBytes], rsi
0x180002a6a  mov     rcx, rsi; lpCriticalSection
0x180002a6d  call    cs:__imp_EnterCriticalSection
0x180002a73  lea     rcx, [rbx+0C8h]
0x180002a7a  cmp     dword ptr [rcx], 1
0x180002a7d  jnz     loc_180002B2B
0x180002a83  mov     edx, 2
0x180002a88  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x180002a8d  lea     r9, [rbx+58h]
0x180002a91  mov     rax, [rbx+50h]
0x180002a95  mov     [rsp+88h+var_58], r15
0x180002a9a  xor     r8d, r8d; pReturnValue
0x180002a9d  mov     [rsp+88h+var_60], rdi
0x180002aa2  mov     [rsp+88h+var_68], rax
0x180002aa7  cmp     [rbx+60Ch], r8d
0x180002aae  jz      short loc_180002ABE
0x180002ab0  mov     edx, 1
0x180002ab5  lea     rcx, stru_180032018
0x180002abc  jmp     short loc_180002ACA
0x180002abe  mov     edx, 2; nProcNum
0x180002ac3  lea     rcx, pProxyInfo; pProxyInfo
0x180002aca  call    cs:__imp_Ndr64AsyncClientCall
0x180002ad0  lock inc dword ptr [rbx+8]
0x180002ad4  mov     edi, r14d
0x180002ad7  mov     [rsp+88h+var_48], r14d
0x180002adc  jmp     short loc_180002B30
0x180002ade  mov     edi, eax
0x180002ae0  mov     rbx, [rsp+88h+arg_0]
0x180002ae8  lea     rcx, [rbx+0C8h]
0x180002aef  mov     edx, 1
0x180002af4  call    ??4?$StateTracker@W4WaitItemCallState@CWaitItem@@@@QEAA?AW4WaitItemCallState@CWaitItem@@W412@@Z; StateTracker<CWaitItem::WaitItemCallState>::operator=(CWaitItem::WaitItemCallState)
0x180002af9  test    edi, edi
0x180002afb  jle     short loc_180002B06
0x180002afd  movzx   edi, di
0x180002b00  or      edi, 80070000h
0x180002b06  mov     [rsp+88h+var_48], edi
0x180002b0a  mov     r8d, edi
0x180002b0d  lea     rdx, aRpcwaitasyncno; "RpcWaitAsyncNotificationEx threw an exc"...
0x180002b14  mov     ecx, 8; int
0x180002b19  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002b1e  xor     r14d, r14d
0x180002b21  mov     rsi, [rsp+88h+uBytes]
0x180002b29  jmp     short loc_180002B30
0x180002b2b  mov     edi, 8007012Fh
0x180002b30  mov     rcx, rsi; lpCriticalSection
0x180002b33  call    cs:__imp_LeaveCriticalSection
0x180002b39  test    edi, edi
0x180002b3b  js      loc_180002D7E
0x180002b41  cmp     qword ptr [rbx+5D0h], 0
0x180002b49  jnz     loc_180002D7E
0x180002b4f  mov     [rsp+88h+pSessionId], 0FFFFh
0x180002b5a  call    cs:__imp_GetCurrentProcessId
0x180002b60  mov     ecx, eax; dwProcessId
0x180002b62  lea     rdx, [rsp+88h+pSessionId]; pSessionId
0x180002b6a  call    cs:__imp_ProcessIdToSessionId
0x180002b70  test    eax, eax
0x180002b72  jnz     short loc_180002B9A
0x180002b74  call    cs:__imp_GetLastError
0x180002b7a  test    eax, eax
0x180002b7c  jle     short loc_180002B86
0x180002b7e  movzx   eax, ax
0x180002b81  or      eax, 80070000h
0x180002b86  mov     r8d, eax
0x180002b89  lea     rdx, aProcessidtoses; "ProcessIdToSessionId failed : 0x%X"
0x180002b90  mov     ecx, 8; int
0x180002b95  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002b9a  call    cs:__imp_WTSGetServiceSessionId
0x180002ba0  cmp     [rsp+88h+pSessionId], eax
0x180002ba7  jz      loc_180002D12
0x180002bad  mov     eax, [rbx+610h]
0x180002bb3  test    eax, eax
0x180002bb5  jnz     loc_180002D12
0x180002bbb  mov     dword ptr [rsp+88h+uBytes], 44h ; 'D'
0x180002bc6  mov     [rsp+88h+IsMember], r14d
0x180002bce  mov     eax, [rbx+610h]
0x180002bd4  cmp     eax, 1
0x180002bd7  jnz     short loc_180002BF2
0x180002bd9  mov     esi, r14d
0x180002bdc  mov     r15, r14
0x180002bdf  lea     rdx, aThisLhascomple; "this->lHasCompletedSystemProcessCheck i"...
0x180002be6  mov     ecx, eax; int
0x180002be8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002bed  jmp     loc_180002CF1
0x180002bf2  mov     edx, dword ptr [rsp+88h+uBytes]; uBytes
0x180002bf9  mov     ecx, 40h ; '@'; uFlags
0x180002bfe  call    cs:__imp_LocalAlloc
0x180002c04  mov     r15, rax
0x180002c07  test    rax, rax
0x180002c0a  jnz     short loc_180002C31
0x180002c0c  mov     esi, 8007000Eh
0x180002c11  lea     r9, aCwaititemIssys; "CWaitItem::IsSystemProcess"
0x180002c18  mov     r8d, esi
0x180002c1b  lea     rdx, aNewPsidFailed0; "new pSid failed: 0x%x in %s"
0x180002c22  mov     ecx, 8; int
0x180002c27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002c2c  jmp     loc_180002CF1
0x180002c31  lea     r9, [rsp+88h+uBytes]; cbSid
0x180002c39  mov     r8, r15; pSid
0x180002c3c  xor     edx, edx; DomainSid
0x180002c3e  mov     ecx, 16h; WellKnownSidType
0x180002c43  call    cs:__imp_CreateWellKnownSid
0x180002c49  test    eax, eax
0x180002c4b  jnz     short loc_180002C83
0x180002c4d  call    cs:__imp_GetLastError
0x180002c53  mov     esi, eax
0x180002c55  test    eax, eax
0x180002c57  jle     short loc_180002C62
0x180002c59  movzx   esi, ax
0x180002c5c  or      esi, 80070000h
0x180002c62  test    esi, esi
0x180002c64  jns     short loc_180002C86
0x180002c66  lea     r9, aCwaititemIssys; "CWaitItem::IsSystemProcess"
0x180002c6d  mov     r8d, esi
0x180002c70  lea     rdx, aCreatewellknow_0; "CreateWellKnownSid failed: 0x%x in %s"
0x180002c77  mov     ecx, 8; int
0x180002c7c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002c81  jmp     short loc_180002CF1
0x180002c83  mov     esi, r14d
0x180002c86  lea     r8, [rsp+88h+IsMember]; IsMember
0x180002c8e  mov     rdx, r15; SidToCheck
0x180002c91  xor     ecx, ecx; TokenHandle
0x180002c93  call    cs:__imp_CheckTokenMembership
0x180002c99  test    eax, eax
0x180002c9b  jnz     short loc_180002CD3
0x180002c9d  call    cs:__imp_GetLastError
0x180002ca3  mov     esi, eax
0x180002ca5  test    eax, eax
0x180002ca7  jle     short loc_180002CB2
0x180002ca9  movzx   esi, ax
0x180002cac  or      esi, 80070000h
0x180002cb2  test    esi, esi
0x180002cb4  jns     short loc_180002CD3
0x180002cb6  lea     r9, aCwaititemIssys; "CWaitItem::IsSystemProcess"
0x180002cbd  mov     r8d, esi
0x180002cc0  lea     rdx, aChecktokenmemb_0; "CheckTokenMembership failed: 0x%x in %s"
0x180002cc7  mov     ecx, 8; int
0x180002ccc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002cd1  jmp     short loc_180002CF1
0x180002cd3  cmp     [rsp+88h+IsMember], 0
0x180002cdb  setnz   r14b
0x180002cdf  xchg    r14d, [rbx+614h]
0x180002ce6  mov     eax, 1
0x180002ceb  xchg    eax, [rbx+610h]
0x180002cf1  mov     rcx, r15; hMem
0x180002cf4  call    cs:__imp_LocalFree
0x180002cfa  test    esi, esi
0x180002cfc  jns     short loc_180002D12
0x180002cfe  mov     r8d, esi
0x180002d01  lea     rdx, aIssystemproces; "IsSystemProcess failed : 0x%X"
0x180002d08  mov     ecx, 8; int
0x180002d0d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002d12  call    cs:__imp_WTSGetServiceSessionId
0x180002d18  cmp     [rsp+88h+pSessionId], eax
0x180002d1f  jz      short loc_180002D45
0x180002d21  mov     eax, [rbx+610h]
0x180002d27  cmp     eax, 1
0x180002d2a  jnz     short loc_180002D37
0x180002d2c  mov     eax, [rbx+614h]
0x180002d32  cmp     eax, 1
0x180002d35  jz      short loc_180002D45
0x180002d37  lea     rdx, aWinstaDll_1; "Winsta.dll"
0x180002d3e  mov     ecx, 1
0x180002d43  jmp     short loc_180002D71
0x180002d45  mov     r9d, [rbx+614h]
0x180002d4c  mov     r8d, [rsp+88h+pSessionId]
0x180002d54  lea     rdx, aProcessIsInSes; "Process is in Session %d or process is "...
0x180002d5b  mov     ecx, 1; int
0x180002d60  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002d65  lea     rdx, ?g_WindowNotificationListHead@CWindowNotification@@2U_LIST_ENTRY@@A; lpModuleName
0x180002d6c  mov     ecx, 5; dwFlags
0x180002d71  lea     r8, [rbx+5D0h]; phModule
0x180002d78  call    cs:__imp_GetModuleHandleExW
0x180002d7e  mov     eax, edi
0x180002d80  add     rsp, 58h
0x180002d84  pop     r15
0x180002d86  pop     r14
0x180002d88  pop     r12
0x180002d8a  pop     rdi
0x180002d8b  pop     rsi
0x180002d8c  pop     rbx
0x180002d8d  retn
0x18002ffd0  push    rbp
0x18002ffd2  sub     rsp, 40h
0x18002ffd6  mov     rbp, rdx
0x18002ffd9  mov     rcx, [rcx]
0x18002ffdc  mov     ecx, [rcx]; ExceptionCode
0x18002ffde  call    cs:__imp_I_RpcExceptionFilter
0x18002ffe4  nop
0x18002ffe5  add     rsp, 40h
0x18002ffe9  pop     rbp
0x18002ffea  retn
```
