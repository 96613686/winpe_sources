# ItSpUnregisterIdleTask(ushort *,int * *,uchar)

- ea: `0x18005571c`
- end: `0x180055994`
- name: `?ItSpUnregisterIdleTask@@YAXPEAGPEAPEAHE@Z`
- size: `632`
- prototype: `void __fastcall(unsigned __int16 *, int **, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x180077950`
- `0x180078930`

## callees

- `0x1800403a4`
- `0x18005571c`
- `0x18005599c`
- `0x180076288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055889`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800558c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800558c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800557f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800558a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800557f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800558a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055735`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005580c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055735`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005580c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055770`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005590b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055770`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005590b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055760`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005591b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055934`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005597c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055760`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005591b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055934`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005597c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005595c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005595c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800557ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055948`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800557ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055948`
- `RPCRT4!RpcImpersonateClient` at `0x18005585d`
- `RPCRT4!RpcImpersonateClient` at `0x18005585d`
- `RPCRT4!RpcRevertToSelf` at `0x180055895`
- `RPCRT4!RpcRevertToSelf` at `0x1800558d4`
- `RPCRT4!RpcRevertToSelf` at `0x180055895`
- `RPCRT4!RpcRevertToSelf` at `0x1800558d4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180055878`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180055878`

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

  EnterCriticalSection(&stru_1800C1360);
  IdleTask = ItSpFindIdleTask(&stru_1800C1388, *a2);
  v6 = IdleTask;
  if ( !IdleTask )
  {
    LeaveCriticalSection(&stru_1800C1360);
    EnterCriticalSection(&stru_1800C12E8);
    if ( ItSrvGlobalContext == 1147547701 )
      goto LABEL_14;
    v13 = ItSpFindIdleTask(&stru_1800C1310, *a2);
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
    --dword_1800C1328;
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
    if ( stru_1800C1310.Flink == &stru_1800C1310 )
      SetEvent(qword_1800C1320);
LABEL_14:
    v12 = &stru_1800C12E8;
    goto LABEL_15;
  }
  SetEvent(*((HANDLE *)IdleTask + 8));
  ResetEvent(*((HANDLE *)v6 + 7));
  EventManager::EvtReport(v7, &ItSpEvt_UnregisterIdleTask, *((_DWORD *)v6 + 7), *((_DWORD *)v6 + 8), v20, v21);
  v8 = *((_DWORD *)v6 + 4);
  if ( (v8 & 2) == 0 )
  {
    --dword_1800C1398;
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
  v12 = &stru_1800C1360;
LABEL_15:
  LeaveCriticalSection(v12);
  *a2 = 0;
}

```

## disassembly

```asm
0x18005571c  push    rbx
0x18005571e  push    rbp
0x18005571f  push    rsi
0x180055720  push    rdi
0x180055721  sub     rsp, 38h
0x180055725  lea     rbp, stru_1800C1360
0x18005572c  mov     sil, r8b
0x18005572f  mov     rcx, rbp; lpCriticalSection
0x180055732  mov     rdi, rdx
0x180055735  call    cs:__imp_EnterCriticalSection
0x18005573c  nop     dword ptr [rax+rax+00h]
0x180055741  mov     rdx, [rdi]; int *
0x180055744  lea     rcx, stru_1800C1388; struct _LIST_ENTRY *
0x18005574b  call    ?ItSpFindIdleTask@@YAPEAU_ITSRV_IDLE_TASK_CONTEXT@@PEAU_LIST_ENTRY@@PEAH@Z; ItSpFindIdleTask(_LIST_ENTRY *,int *)
0x180055750  mov     rbx, rax
0x180055753  test    rax, rax
0x180055756  jz      loc_1800557F6
0x18005575c  mov     rcx, [rax+40h]; hEvent
0x180055760  call    cs:__imp_SetEvent
0x180055767  nop     dword ptr [rax+rax+00h]
0x18005576c  mov     rcx, [rbx+38h]; hEvent
0x180055770  call    cs:__imp_ResetEvent
0x180055777  nop     dword ptr [rax+rax+00h]
0x18005577c  mov     r9d, [rbx+20h]; unsigned int
0x180055780  lea     rdx, ItSpEvt_UnregisterIdleTask; struct _EVENT_DESCRIPTOR *
0x180055787  mov     r8d, [rbx+1Ch]; unsigned int
0x18005578b  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,void *,_GUID const *)
0x180055790  mov     eax, [rbx+10h]
0x180055793  test    al, 2
0x180055795  jz      short loc_18005579F
0x180055797  or      eax, 4
0x18005579a  mov     [rbx+10h], eax
0x18005579d  jmp     short loc_1800557EE
0x18005579f  dec     cs:dword_1800C1398
0x1800557a5  mov     rdx, [rbx]
0x1800557a8  cmp     [rdx+8], rbx
0x1800557ac  jnz     loc_18005598D
0x1800557b2  mov     rax, [rbx+8]
0x1800557b6  cmp     [rax], rbx
0x1800557b9  jnz     loc_18005598D
0x1800557bf  mov     [rax], rdx
0x1800557c2  mov     rcx, rbx; struct _ITSRV_IDLE_TASK_CONTEXT *
0x1800557c5  mov     [rdx+8], rax
0x1800557c9  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x1800557ce  call    cs:__imp_GetProcessHeap
0x1800557d5  nop     dword ptr [rax+rax+00h]
0x1800557da  mov     r8, rbx; lpMem
0x1800557dd  xor     edx, edx; dwFlags
0x1800557df  mov     rcx, rax; hHeap
0x1800557e2  call    cs:__imp_HeapFree
0x1800557e9  nop     dword ptr [rax+rax+00h]
0x1800557ee  mov     rcx, rbp
0x1800557f1  jmp     loc_1800558A8
0x1800557f6  mov     rcx, rbp; lpCriticalSection
0x1800557f9  call    cs:__imp_LeaveCriticalSection
0x180055800  nop     dword ptr [rax+rax+00h]
0x180055805  lea     rcx, stru_1800C12E8; lpCriticalSection
0x18005580c  call    cs:__imp_EnterCriticalSection
0x180055813  nop     dword ptr [rax+rax+00h]
0x180055818  cmp     cs:?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A, 44663035h; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x180055822  jz      short loc_1800558A1
0x180055824  mov     rdx, [rdi]; int *
0x180055827  lea     rbp, stru_1800C1310
0x18005582e  mov     rcx, rbp; struct _LIST_ENTRY *
0x180055831  call    ?ItSpFindIdleTask@@YAPEAU_ITSRV_IDLE_TASK_CONTEXT@@PEAU_LIST_ENTRY@@PEAH@Z; ItSpFindIdleTask(_LIST_ENTRY *,int *)
0x180055836  mov     rbx, rax
0x180055839  test    rax, rax
0x18005583c  jz      short loc_1800558A1
0x18005583e  mov     r9d, [rax+20h]; unsigned int
0x180055842  lea     rdx, ItSpEvt_UnregisterIdleTask; struct _EVENT_DESCRIPTOR *
0x180055849  mov     r8d, [rax+1Ch]; unsigned int
0x18005584d  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,void *,_GUID const *)
0x180055852  test    sil, sil
0x180055855  jnz     loc_1800558E0
0x18005585b  xor     ecx, ecx; BindingHandle
0x18005585d  call    cs:__imp_RpcImpersonateClient
0x180055864  nop     dword ptr [rax+rax+00h]
0x180055869  test    eax, eax
0x18005586b  jnz     short loc_1800558A1
0x18005586d  mov     r8d, [rbx+20h]; dwProcessId
0x180055871  xor     edx, edx; bInheritHandle
0x180055873  mov     ecx, 1FFFFFh; dwDesiredAccess
0x180055878  call    cs:__imp_OpenProcess
0x18005587f  nop     dword ptr [rax+rax+00h]
0x180055884  test    rax, rax
0x180055887  jnz     short loc_1800558C5
0x180055889  call    cs:__imp_GetLastError
0x180055890  nop     dword ptr [rax+rax+00h]
0x180055895  call    cs:__imp_RpcRevertToSelf
0x18005589c  nop     dword ptr [rax+rax+00h]
0x1800558a1  lea     rcx, stru_1800C12E8; lpCriticalSection
0x1800558a8  call    cs:__imp_LeaveCriticalSection
0x1800558af  nop     dword ptr [rax+rax+00h]
0x1800558b4  mov     qword ptr [rdi], 0
0x1800558bb  add     rsp, 38h
0x1800558bf  pop     rdi
0x1800558c0  pop     rsi
0x1800558c1  pop     rbp
0x1800558c2  pop     rbx
0x1800558c3  retn
0x1800558c5  mov     rcx, rax; hObject
0x1800558c8  call    cs:__imp_CloseHandle
0x1800558cf  nop     dword ptr [rax+rax+00h]
0x1800558d4  call    cs:__imp_RpcRevertToSelf
0x1800558db  nop     dword ptr [rax+rax+00h]
0x1800558e0  dec     cs:dword_1800C1328
0x1800558e6  mov     rcx, [rbx]
0x1800558e9  cmp     [rcx+8], rbx
0x1800558ed  jnz     loc_18005598D
0x1800558f3  mov     rax, [rbx+8]
0x1800558f7  cmp     [rax], rbx
0x1800558fa  jnz     loc_18005598D
0x180055900  mov     [rax], rcx
0x180055903  mov     [rcx+8], rax
0x180055907  mov     rcx, [rbx+40h]; hEvent
0x18005590b  call    cs:__imp_ResetEvent
0x180055912  nop     dword ptr [rax+rax+00h]
0x180055917  mov     rcx, [rbx+38h]; hEvent
0x18005591b  call    cs:__imp_SetEvent
0x180055922  nop     dword ptr [rax+rax+00h]
0x180055927  cmp     dword ptr [rbx+14h], 2
0x18005592b  jnz     short loc_180055940
0x18005592d  mov     rcx, cs:hEvent; hEvent
0x180055934  call    cs:__imp_SetEvent
0x18005593b  nop     dword ptr [rax+rax+00h]
0x180055940  mov     rcx, rbx; struct _ITSRV_IDLE_TASK_CONTEXT *
0x180055943  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x180055948  call    cs:__imp_GetProcessHeap
0x18005594f  nop     dword ptr [rax+rax+00h]
0x180055954  mov     r8, rbx; lpMem
0x180055957  xor     edx, edx; dwFlags
0x180055959  mov     rcx, rax; hHeap
0x18005595c  call    cs:__imp_HeapFree
0x180055963  nop     dword ptr [rax+rax+00h]
0x180055968  cmp     cs:stru_1800C1310.Flink, rbp
0x18005596f  jnz     loc_1800558A1
0x180055975  mov     rcx, cs:qword_1800C1320; hEvent
0x18005597c  call    cs:__imp_SetEvent
0x180055983  nop     dword ptr [rax+rax+00h]
0x180055988  jmp     loc_1800558A1
0x18005598d  mov     ecx, 3
0x180055992  int     29h; Win8: RtlFailFast(ecx)
```
