# ItSpUnregisterIdleTask(ushort *,int * *,uchar)

- ea: `0x180052f90`
- end: `0x180053183`
- name: `?ItSpUnregisterIdleTask@@YAXPEAGPEAPEAHE@Z`
- size: `499`
- prototype: `void __fastcall(unsigned __int16 *, int **, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x180073c70`
- `0x180074a10`

## callees

- `0x18003e8f8`
- `0x180052f90`
- `0x18005318c`
- `0x180072848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800530c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800530c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800530ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800530ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005304f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800530d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005304f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800530d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052fa9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005305c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052fa9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005305c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180052fd8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005311e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180052fd8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005311e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180052fce`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180053128`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005313b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180053171`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180052fce`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180053128`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005313b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180053171`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005303e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053157`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005303e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053157`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053030`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053149`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053030`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053149`
- `RPCRT4!RpcImpersonateClient` at `0x1800530a3`
- `RPCRT4!RpcImpersonateClient` at `0x1800530a3`
- `RPCRT4!RpcRevertToSelf` at `0x1800530c9`
- `RPCRT4!RpcRevertToSelf` at `0x1800530f5`
- `RPCRT4!RpcRevertToSelf` at `0x1800530c9`
- `RPCRT4!RpcRevertToSelf` at `0x1800530f5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800530b8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800530b8`

## pseudocode

```c
void __fastcall ItSpUnregisterIdleTask(unsigned __int16 *a1, int **a2, char a3)
{
  struct _ITSRV_IDLE_TASK_CONTEXT *IdleTask; // rax
  struct _ITSRV_IDLE_TASK_CONTEXT *v6; // rbx
  EventManager *v7; // rcx
  int v8; // eax
  __int64 v9; // rdx
  struct _ITSRV_IDLE_TASK_CONTEXT **v10; // rax
  HANDLE v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  struct _ITSRV_IDLE_TASK_CONTEXT *v13; // rax
  EventManager *v14; // rcx
  struct _ITSRV_IDLE_TASK_CONTEXT *v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rcx
  struct _ITSRV_IDLE_TASK_CONTEXT **v18; // rax
  HANDLE ProcessHeap; // rax
  void *v20; // [rsp+20h] [rbp-38h]
  const struct _GUID *v21; // [rsp+28h] [rbp-30h]

  EnterCriticalSection(&stru_1800BD260);
  IdleTask = ItSpFindIdleTask(&stru_1800BD288, *a2);
  v6 = IdleTask;
  if ( !IdleTask )
  {
    LeaveCriticalSection(&stru_1800BD260);
    EnterCriticalSection(&stru_1800BD1E8);
    if ( ItSrvGlobalContext == 1147547701 )
      goto LABEL_14;
    v13 = ItSpFindIdleTask(&stru_1800BD210, *a2);
    v15 = v13;
    if ( !v13 )
      goto LABEL_14;
    EventManager::EvtReport(v14, &ItSpEvt_UnregisterIdleTask, *((_DWORD *)v13 + 7), *((_DWORD *)v13 + 8), v20, v21);
    if ( !a3 )
    {
      if ( RpcImpersonateClient(0) )
        goto LABEL_14;
      v16 = OpenProcess(0x1FFFFFu, 0, *((_DWORD *)v15 + 8));
      if ( !v16 )
      {
        GetLastError();
        RpcRevertToSelf();
        goto LABEL_14;
      }
      CloseHandle(v16);
      RpcRevertToSelf();
    }
    --dword_1800BD228;
    v17 = *(_QWORD *)v15;
    if ( *(struct _ITSRV_IDLE_TASK_CONTEXT **)(*(_QWORD *)v15 + 8LL) != v15 )
      goto LABEL_23;
    v18 = (struct _ITSRV_IDLE_TASK_CONTEXT **)*((_QWORD *)v15 + 1);
    if ( *v18 != v15 )
      goto LABEL_23;
    *v18 = (struct _ITSRV_IDLE_TASK_CONTEXT *)v17;
    *(_QWORD *)(v17 + 8) = v18;
    ResetEvent(*((HANDLE *)v15 + 8));
    SetEvent(*((HANDLE *)v15 + 7));
    if ( *((_DWORD *)v15 + 5) == 2 )
      SetEvent(hEvent);
    ItSpCleanupIdleTask(v15);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
    if ( stru_1800BD210.Flink == &stru_1800BD210 )
      SetEvent(qword_1800BD220);
LABEL_14:
    v12 = &stru_1800BD1E8;
    goto LABEL_15;
  }
  SetEvent(*((HANDLE *)IdleTask + 8));
  ResetEvent(*((HANDLE *)v6 + 7));
  EventManager::EvtReport(v7, &ItSpEvt_UnregisterIdleTask, *((_DWORD *)v6 + 7), *((_DWORD *)v6 + 8), v20, v21);
  v8 = *((_DWORD *)v6 + 4);
  if ( (v8 & 2) == 0 )
  {
    --dword_1800BD298;
    v9 = *(_QWORD *)v6;
    if ( *(struct _ITSRV_IDLE_TASK_CONTEXT **)(*(_QWORD *)v6 + 8LL) == v6 )
    {
      v10 = (struct _ITSRV_IDLE_TASK_CONTEXT **)*((_QWORD *)v6 + 1);
      if ( *v10 == v6 )
      {
        *v10 = (struct _ITSRV_IDLE_TASK_CONTEXT *)v9;
        *(_QWORD *)(v9 + 8) = v10;
        ItSpCleanupIdleTask(v6);
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v6);
        goto LABEL_7;
      }
    }
LABEL_23:
    __fastfail(3u);
  }
  *((_DWORD *)v6 + 4) = v8 | 4;
LABEL_7:
  v12 = &stru_1800BD260;
LABEL_15:
  LeaveCriticalSection(v12);
  *a2 = 0;
}

```

## disassembly

```asm
0x180052f90  push    rbx
0x180052f92  push    rbp
0x180052f93  push    rsi
0x180052f94  push    rdi
0x180052f95  sub     rsp, 38h
0x180052f99  lea     rbp, stru_1800BD260
0x180052fa0  mov     sil, r8b
0x180052fa3  mov     rcx, rbp; lpCriticalSection
0x180052fa6  mov     rdi, rdx
0x180052fa9  call    cs:__imp_EnterCriticalSection
0x180052faf  mov     rdx, [rdi]; int *
0x180052fb2  lea     rcx, stru_1800BD288; struct _LIST_ENTRY *
0x180052fb9  call    ?ItSpFindIdleTask@@YAPEAU_ITSRV_IDLE_TASK_CONTEXT@@PEAU_LIST_ENTRY@@PEAH@Z; ItSpFindIdleTask(_LIST_ENTRY *,int *)
0x180052fbe  mov     rbx, rax
0x180052fc1  test    rax, rax
0x180052fc4  jz      loc_18005304C
0x180052fca  mov     rcx, [rax+40h]; hEvent
0x180052fce  call    cs:__imp_SetEvent
0x180052fd4  mov     rcx, [rbx+38h]; hEvent
0x180052fd8  call    cs:__imp_ResetEvent
0x180052fde  mov     r9d, [rbx+20h]; unsigned int
0x180052fe2  lea     rdx, ItSpEvt_UnregisterIdleTask; struct _EVENT_DESCRIPTOR *
0x180052fe9  mov     r8d, [rbx+1Ch]; unsigned int
0x180052fed  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,void *,_GUID const *)
0x180052ff2  mov     eax, [rbx+10h]
0x180052ff5  test    al, 2
0x180052ff7  jz      short loc_180053001
0x180052ff9  or      eax, 4
0x180052ffc  mov     [rbx+10h], eax
0x180052fff  jmp     short loc_180053044
0x180053001  dec     cs:dword_1800BD298
0x180053007  mov     rdx, [rbx]
0x18005300a  cmp     [rdx+8], rbx
0x18005300e  jnz     loc_18005317C
0x180053014  mov     rax, [rbx+8]
0x180053018  cmp     [rax], rbx
0x18005301b  jnz     loc_18005317C
0x180053021  mov     [rax], rdx
0x180053024  mov     rcx, rbx; struct _ITSRV_IDLE_TASK_CONTEXT *
0x180053027  mov     [rdx+8], rax
0x18005302b  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x180053030  call    cs:__imp_GetProcessHeap
0x180053036  mov     r8, rbx; lpMem
0x180053039  xor     edx, edx; dwFlags
0x18005303b  mov     rcx, rax; hHeap
0x18005303e  call    cs:__imp_HeapFree
0x180053044  mov     rcx, rbp
0x180053047  jmp     loc_1800530D6
0x18005304c  mov     rcx, rbp; lpCriticalSection
0x18005304f  call    cs:__imp_LeaveCriticalSection
0x180053055  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x18005305c  call    cs:__imp_EnterCriticalSection
0x180053062  cmp     cs:?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A, 44663035h; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x18005306c  jz      short loc_1800530CF
0x18005306e  mov     rdx, [rdi]; int *
0x180053071  lea     rbp, stru_1800BD210
0x180053078  mov     rcx, rbp; struct _LIST_ENTRY *
0x18005307b  call    ?ItSpFindIdleTask@@YAPEAU_ITSRV_IDLE_TASK_CONTEXT@@PEAU_LIST_ENTRY@@PEAH@Z; ItSpFindIdleTask(_LIST_ENTRY *,int *)
0x180053080  mov     rbx, rax
0x180053083  test    rax, rax
0x180053086  jz      short loc_1800530CF
0x180053088  mov     r9d, [rax+20h]; unsigned int
0x18005308c  lea     rdx, ItSpEvt_UnregisterIdleTask; struct _EVENT_DESCRIPTOR *
0x180053093  mov     r8d, [rax+1Ch]; unsigned int
0x180053097  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,void *,_GUID const *)
0x18005309c  test    sil, sil
0x18005309f  jnz     short loc_1800530FB
0x1800530a1  xor     ecx, ecx; BindingHandle
0x1800530a3  call    cs:__imp_RpcImpersonateClient
0x1800530a9  test    eax, eax
0x1800530ab  jnz     short loc_1800530CF
0x1800530ad  mov     r8d, [rbx+20h]; dwProcessId
0x1800530b1  xor     edx, edx; bInheritHandle
0x1800530b3  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800530b8  call    cs:__imp_OpenProcess
0x1800530be  test    rax, rax
0x1800530c1  jnz     short loc_1800530EC
0x1800530c3  call    cs:__imp_GetLastError
0x1800530c9  call    cs:__imp_RpcRevertToSelf
0x1800530cf  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x1800530d6  call    cs:__imp_LeaveCriticalSection
0x1800530dc  mov     qword ptr [rdi], 0
0x1800530e3  add     rsp, 38h
0x1800530e7  pop     rdi
0x1800530e8  pop     rsi
0x1800530e9  pop     rbp
0x1800530ea  pop     rbx
0x1800530eb  retn
0x1800530ec  mov     rcx, rax; hObject
0x1800530ef  call    cs:__imp_CloseHandle
0x1800530f5  call    cs:__imp_RpcRevertToSelf
0x1800530fb  dec     cs:dword_1800BD228
0x180053101  mov     rcx, [rbx]
0x180053104  cmp     [rcx+8], rbx
0x180053108  jnz     short loc_18005317C
0x18005310a  mov     rax, [rbx+8]
0x18005310e  cmp     [rax], rbx
0x180053111  jnz     short loc_18005317C
0x180053113  mov     [rax], rcx
0x180053116  mov     [rcx+8], rax
0x18005311a  mov     rcx, [rbx+40h]; hEvent
0x18005311e  call    cs:__imp_ResetEvent
0x180053124  mov     rcx, [rbx+38h]; hEvent
0x180053128  call    cs:__imp_SetEvent
0x18005312e  cmp     dword ptr [rbx+14h], 2
0x180053132  jnz     short loc_180053141
0x180053134  mov     rcx, cs:hEvent; hEvent
0x18005313b  call    cs:__imp_SetEvent
0x180053141  mov     rcx, rbx; struct _ITSRV_IDLE_TASK_CONTEXT *
0x180053144  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x180053149  call    cs:__imp_GetProcessHeap
0x18005314f  mov     r8, rbx; lpMem
0x180053152  xor     edx, edx; dwFlags
0x180053154  mov     rcx, rax; hHeap
0x180053157  call    cs:__imp_HeapFree
0x18005315d  cmp     cs:stru_1800BD210.Flink, rbp
0x180053164  jnz     loc_1800530CF
0x18005316a  mov     rcx, cs:qword_1800BD220; hEvent
0x180053171  call    cs:__imp_SetEvent
0x180053177  jmp     loc_1800530CF
0x18005317c  mov     ecx, 3
0x180053181  int     29h; Win8: RtlFailFast(ecx)
```
