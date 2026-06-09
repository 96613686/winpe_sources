# CWorkItemManager::ObtainWorkItem(tagWorkItemType)

- ea: `0x18001b2cc`
- end: `0x18001b6cf`
- name: `?ObtainWorkItem@CWorkItemManager@@QEAAJW4tagWorkItemType@@@Z`
- size: `1027`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800551e0`

## callees

- `0x18001b2cc`
- `0x18001bb4c`
- `0x18001bf7c`
- `0x18001c3cc`
- `0x180111e18`
- `0x18012b618`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b58a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b58a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b419`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b419`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b306`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b306`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b633`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b462`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001b51d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001b51d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001b34b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001b3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001b4a5`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001b691`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001b34b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001b3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001b4a5`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001b691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b486`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b486`

## string_xrefs

- `0x18001b373`: `Work item %ws is in use in thread %u. Is the thread executing? %ws`
- `0x18001b3f8`: `Work item %ws is exiting in thread %u`
- `0x18001b4c4`: `Work item %ws is executing in thread %u`
- `0x18001b54d`: `Created a thread %u to execute work item %ws.`
- `0x18001b6b0`: `Execute work item %ws in existing thread: %u`
- `0x18001b42d`: `fail to submit work item to thread pool, hr=%#lX. Retry Later.`
- `0x18001b5f2`: `Set %ws in use and subscribe WorkItemCompleteEvent %p, Destination: %d, ID: %lu`

## pseudocode

```c
__int64 __fastcall CWorkItemManager::ObtainWorkItem(__int64 a1, int a2)
{
  __int64 v2; // r13
  signed int v4; // edi
  __int64 v5; // r14
  const wchar_t *v6; // rbx
  DWORD v7; // eax
  __int64 v8; // rax
  int v9; // edx
  int v10; // ebx
  _QWORD *v11; // rsi
  DWORD v12; // eax
  __int64 WorkItemTypeAsString; // rax
  int v14; // edx
  DWORD v15; // eax
  signed int LastError; // eax
  void *v17; // rcx
  DWORD v18; // eax
  __int64 v19; // rax
  int v20; // edx
  HANDLE v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // r8
  DWORD v29; // eax
  __int64 v30; // rax
  int v31; // edx
  __int64 v32; // [rsp+30h] [rbp-78h]
  __int64 v33; // [rsp+30h] [rbp-78h]
  __int64 v34; // [rsp+38h] [rbp-70h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+50h] [rbp-58h]
  DWORD ThreadId; // [rsp+58h] [rbp-50h] BYREF

  v2 = a2;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(a1 + 680);
  v4 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 680));
  CWorkItemManager::AdjustThreadPriorities((CWorkItemManager *)a1);
  v5 = a1 + 80 * v2;
  if ( !*(_DWORD *)v5 )
  {
    if ( *(_DWORD *)(a1 + 80 * v2 + 68) )
    {
      v12 = GetThreadId(*(HANDLE *)(v5 + 40));
      WorkItemTypeAsString = GetWorkItemTypeAsString((unsigned int)v2, v12);
      WUTrace(0, 0, 1, 5, 0, L"Work item %ws is exiting in thread %u", WorkItemTypeAsString, v14);
      v15 = WaitForSingleObject(*(HANDLE *)(v5 + 40), 0xFFFFFFFF);
      if ( v15 )
      {
        if ( v15 != -1 )
        {
          v4 = -2147467259;
LABEL_12:
          LODWORD(v32) = v4;
          WUTrace(0, 0, 1, 5, 0, L"fail to submit work item to thread pool, hr=%#lX. Retry Later.", v32);
          CWorkItemManager::SubmitWorkItemRetryTimeout((CWorkItemManager *)a1);
          goto LABEL_25;
        }
LABEL_13:
        LastError = GetLastError();
        v4 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v4 = LastError;
        if ( v4 >= 0 )
          v4 = -2147418113;
        goto LABEL_12;
      }
      CloseHandle(*(HANDLE *)(v5 + 40));
      *(_QWORD *)(v5 + 40) = 0;
      *(_DWORD *)(a1 + 80 * v2 + 68) = 0;
    }
    v17 = *(void **)(v5 + 40);
    if ( *(_DWORD *)(a1 + 80 * v2 + 72) )
    {
      v4 = -2147024713;
      v18 = GetThreadId(v17);
      v19 = GetWorkItemTypeAsString((unsigned int)v2, v18);
      LODWORD(v34) = v20;
      WUTrace(0, 0, 1, 5, 0, L"Work item %ws is executing in thread %u", v19, v34);
      goto LABEL_12;
    }
    if ( v17 )
    {
      v29 = GetThreadId(v17);
      v30 = GetWorkItemTypeAsString((unsigned int)v2, v29);
      LODWORD(v34) = v31;
      WUTrace(0, 0, 1, 5, 0, L"Execute work item %ws in existing thread: %u", v30, v34);
    }
    else
    {
      ThreadId = 0;
      v21 = CreateThread(0, 0, CWorkItemManager::ExecuteWorkItemWrapper, (LPVOID)(a1 + 80 * v2), 0, &ThreadId);
      *(_QWORD *)(v5 + 40) = v21;
      if ( !v21 )
        goto LABEL_13;
      v23 = GetWorkItemTypeAsString((unsigned int)v2, v22);
      LODWORD(v32) = ThreadId;
      WUTrace(0, 0, 1, 5, 0, L"Created a thread %u to execute work item %ws.", v32, v23);
      LOBYTE(v24) = 1;
      ChangeThreadPriorityState(*(_QWORD *)(v5 + 40), *(unsigned int *)(a1 + 760), v24);
    }
    SetEvent(*(HANDLE *)(a1 + 80 * v2 + 32));
    *(_DWORD *)(a1 + 80 * v2 + 64) = 1;
    *(_DWORD *)(a1 + 80 * v2) = 1;
    v26 = GetWorkItemTypeAsString((unsigned int)v2, v25);
    WUTrace(
      0,
      0,
      1,
      5,
      0,
      L"Set %ws in use and subscribe WorkItemCompleteEvent %p, Destination: %d, ID: %lu",
      v26,
      *(_QWORD *)(v27 + 32),
      *(_DWORD *)(v27 + 52),
      *(_DWORD *)(v27 + 56),
      lpCriticalSection);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(a1 + 728) + 216LL) + 24LL))(
      *(_QWORD *)(a1 + 728) + 216LL,
      *(_QWORD *)(a1 + 80 * v2 + 24));
    goto LABEL_25;
  }
  v6 = L"No";
  if ( *(_DWORD *)(a1 + 80 * v2 + 72) )
    v6 = L"Yes";
  v7 = GetThreadId(*(HANDLE *)(v5 + 40));
  v8 = GetWorkItemTypeAsString((unsigned int)v2, v7);
  WUTrace(0, 0, 1, 5, 0, L"Work item %ws is in use in thread %u. Is the thread executing? %ws", v8, v9, v6);
  if ( !(_DWORD)v2 )
  {
    v10 = 2;
    v11 = (_QWORD *)(a1 + 656);
    do
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 24LL))(*v11);
      --v10;
      --v11;
    }
    while ( v10 > 0 );
  }
LABEL_25:
  LeaveCriticalSection(lpCriticalSection);
  if ( v4 < 0 )
  {
    LODWORD(v34) = v4;
    LODWORD(v33) = v2;
    WUTrace(0, 0, 1, 5, 0, L"fail to obtain work item type %d with error %#lx", v33, v34);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001b2cc  mov     [rsp+arg_10], rbx
0x18001b2d1  push    rbp
0x18001b2d2  push    rsi
0x18001b2d3  push    rdi
0x18001b2d4  push    r12
0x18001b2d6  push    r13
0x18001b2d8  push    r14
0x18001b2da  push    r15
0x18001b2dc  sub     rsp, 70h
0x18001b2e0  mov     rax, cs:__security_cookie
0x18001b2e7  xor     rax, rsp
0x18001b2ea  mov     [rsp+0A8h+var_48], rax
0x18001b2ef  lea     rax, [rcx+2A8h]
0x18001b2f6  movsxd  r13, edx
0x18001b2f9  mov     rsi, rcx
0x18001b2fc  mov     [rsp+0A8h+lpCriticalSection], rax
0x18001b301  mov     rcx, rax; lpCriticalSection
0x18001b304  xor     edi, edi
0x18001b306  call    cs:__imp_EnterCriticalSection
0x18001b30c  mov     rcx, rsi; this
0x18001b30f  call    ?AdjustThreadPriorities@CWorkItemManager@@AEAAXXZ; CWorkItemManager::AdjustThreadPriorities(void)
0x18001b314  lea     r15, ds:0[r13*4]
0x18001b31c  add     r15, r13
0x18001b31f  add     r15, r15
0x18001b322  lea     r14, [rsi+r15*8]
0x18001b326  cmp     [rsi+r15*8], edi
0x18001b32a  jz      loc_18001B3C1
0x18001b330  cmp     [rsi+r15*8+48h], edi
0x18001b335  lea     rax, aYes; "Yes"
0x18001b33c  mov     rcx, [r14+28h]; Thread
0x18001b340  lea     rbx, aNo_0; "No"
0x18001b347  cmovnz  rbx, rax
0x18001b34b  call    cs:__imp_GetThreadId
0x18001b351  mov     ecx, r13d
0x18001b354  mov     edx, eax
0x18001b356  call    ?GetWorkItemTypeAsString@@YAPEB_WW4tagWorkItemType@@@Z; GetWorkItemTypeAsString(tagWorkItemType)
0x18001b35b  mov     [rsp+0A8h+var_68], rbx
0x18001b360  lea     r12d, [rdi+5]
0x18001b364  mov     dword ptr [rsp+0A8h+var_70], edx
0x18001b368  lea     ebp, [rdi+1]
0x18001b36b  mov     [rsp+0A8h+var_78], rax
0x18001b370  mov     r9d, r12d
0x18001b373  lea     rax, aWorkItemWsIsIn; "Work item %ws is in use in thread %u. I"...
0x18001b37a  mov     r8d, ebp
0x18001b37d  mov     [rsp+0A8h+lpThreadId], rax
0x18001b382  xor     edx, edx
0x18001b384  xor     ecx, ecx
0x18001b386  mov     qword ptr [rsp+0A8h+dwCreationFlags], rdi
0x18001b38b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001b390  test    r13d, r13d
0x18001b393  jnz     loc_18001B62E
0x18001b399  lea     ebx, [rdi+2]
0x18001b39c  add     rsi, 290h
0x18001b3a3  mov     rcx, [rsi]
0x18001b3a6  mov     rax, [rcx]
0x18001b3a9  mov     rax, [rax+18h]
0x18001b3ad  call    _guard_dispatch_icall
0x18001b3b2  sub     ebx, ebp
0x18001b3b4  lea     rsi, [rsi-8]
0x18001b3b8  test    ebx, ebx
0x18001b3ba  jg      short loc_18001B3A3
0x18001b3bc  jmp     loc_18001B62E
0x18001b3c1  mov     ebp, 1
0x18001b3c6  lea     r12d, [rbp+4]
0x18001b3ca  cmp     [rsi+r15*8+44h], edi
0x18001b3cf  jz      loc_18001B495
0x18001b3d5  mov     rcx, [r14+28h]; Thread
0x18001b3d9  call    cs:__imp_GetThreadId
0x18001b3df  mov     ecx, r13d
0x18001b3e2  mov     edx, eax
0x18001b3e4  call    ?GetWorkItemTypeAsString@@YAPEB_WW4tagWorkItemType@@@Z; GetWorkItemTypeAsString(tagWorkItemType)
0x18001b3e9  mov     dword ptr [rsp+0A8h+var_70], edx
0x18001b3ed  mov     r9d, r12d
0x18001b3f0  mov     [rsp+0A8h+var_78], rax
0x18001b3f5  mov     r8d, ebp
0x18001b3f8  lea     rax, aWorkItemWsIsEx; "Work item %ws is exiting in thread %u"
0x18001b3ff  xor     edx, edx
0x18001b401  mov     [rsp+0A8h+lpThreadId], rax
0x18001b406  xor     ecx, ecx
0x18001b408  mov     qword ptr [rsp+0A8h+dwCreationFlags], rdi
0x18001b40d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001b412  mov     rcx, [r14+28h]; hHandle
0x18001b416  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b419  call    cs:__imp_WaitForSingleObject
0x18001b41f  test    eax, eax
0x18001b421  jz      short loc_18001B482
0x18001b423  cmp     eax, 0FFFFFFFFh
0x18001b426  jz      short loc_18001B462
0x18001b428  mov     edi, 80004005h
0x18001b42d  lea     rax, aFailToSubmitWo; "fail to submit work item to thread pool"...
0x18001b434  mov     dword ptr [rsp+0A8h+var_78], edi
0x18001b438  mov     [rsp+0A8h+lpThreadId], rax
0x18001b43d  mov     r9d, r12d
0x18001b440  mov     r8d, ebp
0x18001b443  mov     qword ptr [rsp+0A8h+dwCreationFlags], 0
0x18001b44c  xor     edx, edx
0x18001b44e  xor     ecx, ecx
0x18001b450  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001b455  mov     rcx, rsi; this
0x18001b458  call    ?SubmitWorkItemRetryTimeout@CWorkItemManager@@AEAAXXZ; CWorkItemManager::SubmitWorkItemRetryTimeout(void)
0x18001b45d  jmp     loc_18001B62E
0x18001b462  call    cs:__imp_GetLastError
0x18001b468  movzx   edi, ax
0x18001b46b  or      edi, 80070000h
0x18001b471  test    eax, eax
0x18001b473  cmovle  edi, eax
0x18001b476  mov     eax, 8000FFFFh
0x18001b47b  test    edi, edi
0x18001b47d  cmovns  edi, eax
0x18001b480  jmp     short loc_18001B42D
0x18001b482  mov     rcx, [r14+28h]; hObject
0x18001b486  call    cs:__imp_CloseHandle
0x18001b48c  mov     [r14+28h], rdi
0x18001b490  mov     [rsi+r15*8+44h], edi
0x18001b495  mov     rcx, [r14+28h]; Thread
0x18001b499  cmp     [rsi+r15*8+48h], edi
0x18001b49e  jz      short loc_18001B4E7
0x18001b4a0  mov     edi, 800700B7h
0x18001b4a5  call    cs:__imp_GetThreadId
0x18001b4ab  mov     ecx, r13d
0x18001b4ae  mov     edx, eax
0x18001b4b0  call    ?GetWorkItemTypeAsString@@YAPEB_WW4tagWorkItemType@@@Z; GetWorkItemTypeAsString(tagWorkItemType)
0x18001b4b5  mov     dword ptr [rsp+0A8h+var_70], edx
0x18001b4b9  mov     r9d, r12d
0x18001b4bc  mov     [rsp+0A8h+var_78], rax
0x18001b4c1  mov     r8d, ebp
0x18001b4c4  lea     rax, aWorkItemWsIsEx_0; "Work item %ws is executing in thread %u"
0x18001b4cb  xor     edx, edx
0x18001b4cd  mov     [rsp+0A8h+lpThreadId], rax
0x18001b4d2  xor     ecx, ecx
0x18001b4d4  mov     qword ptr [rsp+0A8h+dwCreationFlags], 0
0x18001b4dd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001b4e2  jmp     loc_18001B42D
0x18001b4e7  test    rcx, rcx
0x18001b4ea  jnz     loc_18001B691
0x18001b4f0  lea     rax, [rsp+0A8h+ThreadId]
0x18001b4f5  mov     [rsp+0A8h+ThreadId], edi
0x18001b4f9  mov     [rsp+0A8h+lpThreadId], rax; lpThreadId
0x18001b4fe  lea     r9, ds:0[r13*4]
0x18001b506  add     r9, r13
0x18001b509  mov     [rsp+0A8h+dwCreationFlags], edi; dwCreationFlags
0x18001b50d  shl     r9, 4
0x18001b511  lea     r8, ?ExecuteWorkItemWrapper@CWorkItemManager@@CAKPEAX@Z; lpStartAddress
0x18001b518  add     r9, rsi; lpParameter
0x18001b51b  xor     edx, edx; dwStackSize
0x18001b51d  call    cs:__imp_CreateThread
0x18001b523  mov     [r14+28h], rax
0x18001b527  test    rax, rax
0x18001b52a  jz      loc_18001B462
0x18001b530  mov     ecx, r13d
0x18001b533  call    ?GetWorkItemTypeAsString@@YAPEB_WW4tagWorkItemType@@@Z; GetWorkItemTypeAsString(tagWorkItemType)
0x18001b538  mov     [rsp+0A8h+var_70], rax
0x18001b53d  mov     r9d, r12d
0x18001b540  mov     eax, [rsp+0A8h+ThreadId]
0x18001b544  mov     r8d, ebp
0x18001b547  mov     dword ptr [rsp+0A8h+var_78], eax
0x18001b54b  xor     edx, edx
0x18001b54d  lea     rax, aCreatedAThread; "Created a thread %u to execute work ite"...
0x18001b554  xor     ecx, ecx
0x18001b556  mov     [rsp+0A8h+lpThreadId], rax
0x18001b55b  mov     qword ptr [rsp+0A8h+dwCreationFlags], rdi
0x18001b560  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001b565  mov     edx, [rsi+2F8h]
0x18001b56b  mov     r8b, bpl
0x18001b56e  mov     rcx, [r14+28h]
0x18001b572  call    ?ChangeThreadPriorityState@@YAJPEAXW4ThreadPriorityLevel@@_N@Z; ChangeThreadPriorityState(void *,ThreadPriorityLevel,bool)
0x18001b577  lea     rcx, ds:0[r13*4]
0x18001b57f  add     rcx, r13
0x18001b582  add     rcx, rcx
0x18001b585  mov     rcx, [rsi+rcx*8+20h]; hEvent
0x18001b58a  call    cs:__imp_SetEvent
0x18001b590  lea     rax, ds:0[r13*4]
0x18001b598  mov     ecx, r13d
0x18001b59b  add     rax, r13
0x18001b59e  lea     rbx, ds:0[r13*4]
0x18001b5a6  add     rax, rax
0x18001b5a9  add     rbx, r13
0x18001b5ac  add     rbx, rbx
0x18001b5af  mov     [rsi+rax*8+40h], ebp
0x18001b5b3  lea     rax, ds:0[r13*4]
0x18001b5bb  mov     r8, [rsi+rbx*8+18h]
0x18001b5c0  add     rax, r13
0x18001b5c3  add     rax, rax
0x18001b5c6  mov     [rsi+rax*8], ebp
0x18001b5c9  call    ?GetWorkItemTypeAsString@@YAPEB_WW4tagWorkItemType@@@Z; GetWorkItemTypeAsString(tagWorkItemType)
0x18001b5ce  mov     rdx, rax
0x18001b5d1  mov     r9d, r12d
0x18001b5d4  mov     eax, [r8+38h]
0x18001b5d8  xor     ecx, ecx
0x18001b5da  mov     [rsp+0A8h+var_60], eax
0x18001b5de  mov     eax, [r8+34h]
0x18001b5e2  mov     dword ptr [rsp+0A8h+var_68], eax
0x18001b5e6  mov     rax, [r8+20h]
0x18001b5ea  mov     r8d, ebp
0x18001b5ed  mov     [rsp+0A8h+var_70], rax
0x18001b5f2  lea     rax, aSetWsInUseAndS; "Set %ws in use and subscribe WorkItemCo"...
0x18001b5f9  mov     [rsp+0A8h+var_78], rdx
0x18001b5fe  xor     edx, edx
0x18001b600  mov     [rsp+0A8h+lpThreadId], rax
0x18001b605  mov     qword ptr [rsp+0A8h+dwCreationFlags], rdi
0x18001b60a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001b60f  mov     rcx, [rsi+2D8h]
0x18001b616  mov     rdx, [rsi+rbx*8+18h]
0x18001b61b  add     rcx, 0D8h
0x18001b622  mov     rax, [rcx]
0x18001b625  mov     rax, [rax+18h]
0x18001b629  call    _guard_dispatch_icall
0x18001b62e  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x18001b633  call    cs:__imp_LeaveCriticalSection
0x18001b639  test    edi, edi
0x18001b63b  jns     short loc_18001B66A
0x18001b63d  mov     dword ptr [rsp+0A8h+var_70], edi
0x18001b641  lea     rax, aFailToObtainWo; "fail to obtain work item type %d with e"...
0x18001b648  mov     dword ptr [rsp+0A8h+var_78], r13d
0x18001b64d  mov     r9d, r12d
0x18001b650  mov     [rsp+0A8h+lpThreadId], rax
0x18001b655  mov     r8d, ebp
0x18001b658  xor     edx, edx
0x18001b65a  mov     qword ptr [rsp+0A8h+dwCreationFlags], 0
0x18001b663  xor     ecx, ecx
0x18001b665  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001b66a  mov     eax, edi
0x18001b66c  mov     rcx, [rsp+0A8h+var_48]
0x18001b671  xor     rcx, rsp; StackCookie
0x18001b674  call    __security_check_cookie
0x18001b679  mov     rbx, [rsp+0A8h+arg_10]
0x18001b681  add     rsp, 70h
0x18001b685  pop     r15
0x18001b687  pop     r14
0x18001b689  pop     r13
0x18001b68b  pop     r12
0x18001b68d  pop     rdi
0x18001b68e  pop     rsi
0x18001b68f  pop     rbp
0x18001b690  retn
0x18001b691  call    cs:__imp_GetThreadId
0x18001b697  mov     ecx, r13d
0x18001b69a  mov     edx, eax
0x18001b69c  call    ?GetWorkItemTypeAsString@@YAPEB_WW4tagWorkItemType@@@Z; GetWorkItemTypeAsString(tagWorkItemType)
0x18001b6a1  mov     dword ptr [rsp+0A8h+var_70], edx
0x18001b6a5  mov     r9d, r12d
0x18001b6a8  mov     [rsp+0A8h+var_78], rax
0x18001b6ad  mov     r8d, ebp
0x18001b6b0  lea     rax, aExecuteWorkIte; "Execute work item %ws in existing threa"...
0x18001b6b7  xor     edx, edx
0x18001b6b9  mov     [rsp+0A8h+lpThreadId], rax
0x18001b6be  xor     ecx, ecx
0x18001b6c0  mov     qword ptr [rsp+0A8h+dwCreationFlags], rdi
0x18001b6c5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001b6ca  jmp     loc_18001B577
```
