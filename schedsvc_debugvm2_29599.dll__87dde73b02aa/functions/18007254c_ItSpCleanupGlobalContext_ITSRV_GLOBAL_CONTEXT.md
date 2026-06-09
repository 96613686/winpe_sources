# ItSpCleanupGlobalContext(_ITSRV_GLOBAL_CONTEXT *)

- ea: `0x18007254c`
- end: `0x1800727a2`
- name: `?ItSpCleanupGlobalContext@@YAXPEAU_ITSRV_GLOBAL_CONTEXT@@@Z`
- size: `598`
- prototype: `void __fastcall(struct _ITSRV_GLOBAL_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180073c94`
- `0x180074918`

## callees

- `0x1800527dc`
- `0x18005318c`
- `0x18007254c`
- `0x180073c40`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007262b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007266f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800725f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007262b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007266f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180072581`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007258e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007259b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180072581`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007258e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007259b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007265d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800726da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007272b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072754`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007265d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800726da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007272b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072754`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007264f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800726cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007271d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072746`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007264f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800726cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007271d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072746`
- `RPCRT4!RpcBindingVectorFree` at `0x180072780`
- `RPCRT4!RpcBindingVectorFree` at `0x180072780`
- `WMICLNT!WmiCloseBlock` at `0x18007263d`
- `WMICLNT!WmiCloseBlock` at `0x18007263d`

## pseudocode

```c
void __fastcall ItSpCleanupGlobalContext(struct _ITSRV_GLOBAL_CONTEXT *a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax
  struct _ITSRV_IDLE_TASK_CONTEXT *Flink; // rbx
  struct _LIST_ENTRY *v4; // rax
  HANDLE v5; // rax
  struct _ITSRV_IDLE_TASK_CONTEXT *v6; // rbx
  struct _LIST_ENTRY *v7; // rax
  HANDLE v8; // rax
  wchar_t *v9; // rbx
  HANDLE v10; // rax

  if ( !Timer && ((ItSrvGlobalContext - 1147547697) & 0xFFFFFFFB) == 0 )
  {
    DeleteCriticalSection(&stru_1800BD1E8);
    DeleteCriticalSection(&stru_1800BD260);
    DeleteCriticalSection(&stru_1800BD230);
    if ( hObject )
      CloseHandle(hObject);
    if ( qword_1800BD310 )
      CloseHandle(qword_1800BD310);
    if ( hHandle )
      CloseHandle(hHandle);
    if ( qword_1800BD320 )
      CloseHandle(qword_1800BD320);
    if ( qword_1800BD4A0 )
      CloseHandle(qword_1800BD4A0);
    if ( qword_1800BD498 )
      CloseHandle(qword_1800BD498);
    if ( hEvent )
      CloseHandle(hEvent);
    if ( qword_1800BD220 )
      CloseHandle(qword_1800BD220);
    if ( qword_1800BD370 )
      WmiCloseBlock();
    v1 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    if ( qword_1800BD388 )
      CloseHandle(qword_1800BD388);
    ItSpCleanupSystemSnapshot((struct _ITSRV_SYSTEM_SNAPSHOT *)&dword_1800BD390);
    ItSpCleanupSystemSnapshot((struct _ITSRV_SYSTEM_SNAPSHOT *)&dword_1800BD3E8);
    while ( 1 )
    {
      Flink = (struct _ITSRV_IDLE_TASK_CONTEXT *)stru_1800BD210.Flink;
      if ( stru_1800BD210.Flink == &stru_1800BD210 )
        break;
      --dword_1800BD228;
      if ( stru_1800BD210.Flink->Blink != &stru_1800BD210
        || (v4 = stru_1800BD210.Flink->Flink, stru_1800BD210.Flink->Flink->Blink != stru_1800BD210.Flink) )
      {
LABEL_34:
        __fastfail(3u);
      }
      stru_1800BD210.Flink = stru_1800BD210.Flink->Flink;
      v4->Blink = &stru_1800BD210;
      ItSpCleanupIdleTask(Flink);
      v5 = GetProcessHeap();
      HeapFree(v5, 0, Flink);
    }
    while ( 1 )
    {
      v6 = (struct _ITSRV_IDLE_TASK_CONTEXT *)stru_1800BD288.Flink;
      if ( stru_1800BD288.Flink == &stru_1800BD288 )
        break;
      --dword_1800BD298;
      if ( stru_1800BD288.Flink->Blink != &stru_1800BD288 )
        goto LABEL_34;
      v7 = stru_1800BD288.Flink->Flink;
      if ( stru_1800BD288.Flink->Flink->Blink != stru_1800BD288.Flink )
        goto LABEL_34;
      stru_1800BD288.Flink = stru_1800BD288.Flink->Flink;
      v7->Blink = &stru_1800BD288;
      ItSpCleanupIdleTask(v6);
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v6);
    }
    v9 = String1;
    if ( String1 )
    {
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v9);
      String1 = 0;
      dword_1800BD364 = 0;
    }
    if ( BindingVector )
      RpcBindingVectorFree(&BindingVector);
    ItSpUpdateStatus(&ItSrvGlobalContext, 1147547702);
  }
}

```

## disassembly

```asm
0x18007254c  mov     [rsp+arg_0], rbx
0x180072551  push    rsi
0x180072552  sub     rsp, 20h
0x180072556  cmp     cs:Timer, 0
0x18007255e  jnz     loc_180072797
0x180072564  mov     eax, cs:?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x18007256a  add     eax, 0BB99CFCFh
0x18007256f  test    eax, 0FFFFFFFBh
0x180072574  jnz     loc_180072797
0x18007257a  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x180072581  call    cs:__imp_DeleteCriticalSection
0x180072587  lea     rcx, stru_1800BD260; lpCriticalSection
0x18007258e  call    cs:__imp_DeleteCriticalSection
0x180072594  lea     rcx, stru_1800BD230; lpCriticalSection
0x18007259b  call    cs:__imp_DeleteCriticalSection
0x1800725a1  mov     rcx, cs:hObject; hObject
0x1800725a8  test    rcx, rcx
0x1800725ab  jz      short loc_1800725B3
0x1800725ad  call    cs:__imp_CloseHandle
0x1800725b3  mov     rcx, cs:qword_1800BD310; hObject
0x1800725ba  test    rcx, rcx
0x1800725bd  jz      short loc_1800725C5
0x1800725bf  call    cs:__imp_CloseHandle
0x1800725c5  mov     rcx, cs:hHandle; hObject
0x1800725cc  test    rcx, rcx
0x1800725cf  jz      short loc_1800725D7
0x1800725d1  call    cs:__imp_CloseHandle
0x1800725d7  mov     rcx, cs:qword_1800BD320; hObject
0x1800725de  test    rcx, rcx
0x1800725e1  jz      short loc_1800725E9
0x1800725e3  call    cs:__imp_CloseHandle
0x1800725e9  mov     rcx, cs:qword_1800BD4A0; hObject
0x1800725f0  test    rcx, rcx
0x1800725f3  jz      short loc_1800725FB
0x1800725f5  call    cs:__imp_CloseHandle
0x1800725fb  mov     rcx, cs:qword_1800BD498; hObject
0x180072602  test    rcx, rcx
0x180072605  jz      short loc_18007260D
0x180072607  call    cs:__imp_CloseHandle
0x18007260d  mov     rcx, cs:hEvent; hObject
0x180072614  test    rcx, rcx
0x180072617  jz      short loc_18007261F
0x180072619  call    cs:__imp_CloseHandle
0x18007261f  mov     rcx, cs:qword_1800BD220; hObject
0x180072626  test    rcx, rcx
0x180072629  jz      short loc_180072631
0x18007262b  call    cs:__imp_CloseHandle
0x180072631  mov     rcx, cs:qword_1800BD370
0x180072638  test    rcx, rcx
0x18007263b  jz      short loc_180072643
0x18007263d  call    cs:__imp_WmiCloseBlock
0x180072643  mov     rbx, cs:lpMem
0x18007264a  test    rbx, rbx
0x18007264d  jz      short loc_180072663
0x18007264f  call    cs:__imp_GetProcessHeap
0x180072655  mov     r8, rbx; lpMem
0x180072658  xor     edx, edx; dwFlags
0x18007265a  mov     rcx, rax; hHeap
0x18007265d  call    cs:__imp_HeapFree
0x180072663  mov     rcx, cs:qword_1800BD388; hObject
0x18007266a  test    rcx, rcx
0x18007266d  jz      short loc_180072675
0x18007266f  call    cs:__imp_CloseHandle
0x180072675  lea     rcx, dword_1800BD390; struct _ITSRV_SYSTEM_SNAPSHOT *
0x18007267c  call    ?ItSpCleanupSystemSnapshot@@YAXPEAU_ITSRV_SYSTEM_SNAPSHOT@@@Z; ItSpCleanupSystemSnapshot(_ITSRV_SYSTEM_SNAPSHOT *)
0x180072681  lea     rcx, dword_1800BD3E8; struct _ITSRV_SYSTEM_SNAPSHOT *
0x180072688  call    ?ItSpCleanupSystemSnapshot@@YAXPEAU_ITSRV_SYSTEM_SNAPSHOT@@@Z; ItSpCleanupSystemSnapshot(_ITSRV_SYSTEM_SNAPSHOT *)
0x18007268d  lea     rsi, stru_1800BD210
0x180072694  mov     rbx, cs:stru_1800BD210.Flink
0x18007269b  cmp     rbx, rsi
0x18007269e  jz      short loc_1800726E2
0x1800726a0  dec     cs:dword_1800BD228
0x1800726a6  cmp     [rbx+8], rsi
0x1800726aa  jnz     loc_180072733
0x1800726b0  mov     rax, [rbx]
0x1800726b3  cmp     [rax+8], rbx
0x1800726b7  jnz     short loc_180072733
0x1800726b9  mov     cs:stru_1800BD210.Flink, rax
0x1800726c0  mov     rcx, rbx; struct _ITSRV_IDLE_TASK_CONTEXT *
0x1800726c3  mov     [rax+8], rsi
0x1800726c7  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x1800726cc  call    cs:__imp_GetProcessHeap
0x1800726d2  mov     r8, rbx; lpMem
0x1800726d5  xor     edx, edx; dwFlags
0x1800726d7  mov     rcx, rax; hHeap
0x1800726da  call    cs:__imp_HeapFree
0x1800726e0  jmp     short loc_180072694
0x1800726e2  lea     rsi, stru_1800BD288
0x1800726e9  mov     rbx, cs:stru_1800BD288.Flink
0x1800726f0  cmp     rbx, rsi
0x1800726f3  jz      short loc_18007273A
0x1800726f5  dec     cs:dword_1800BD298
0x1800726fb  cmp     [rbx+8], rsi
0x1800726ff  jnz     short loc_180072733
0x180072701  mov     rax, [rbx]
0x180072704  cmp     [rax+8], rbx
0x180072708  jnz     short loc_180072733
0x18007270a  mov     cs:stru_1800BD288.Flink, rax
0x180072711  mov     rcx, rbx; struct _ITSRV_IDLE_TASK_CONTEXT *
0x180072714  mov     [rax+8], rsi
0x180072718  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x18007271d  call    cs:__imp_GetProcessHeap
0x180072723  mov     r8, rbx; lpMem
0x180072726  xor     edx, edx; dwFlags
0x180072728  mov     rcx, rax; hHeap
0x18007272b  call    cs:__imp_HeapFree
0x180072731  jmp     short loc_1800726E9
0x180072733  mov     ecx, 3
0x180072738  int     29h; Win8: RtlFailFast(ecx)
0x18007273a  mov     rbx, cs:String1
0x180072741  test    rbx, rbx
0x180072744  jz      short loc_18007276F
0x180072746  call    cs:__imp_GetProcessHeap
0x18007274c  mov     r8, rbx; lpMem
0x18007274f  xor     edx, edx; dwFlags
0x180072751  mov     rcx, rax; hHeap
0x180072754  call    cs:__imp_HeapFree
0x18007275a  mov     cs:String1, 0
0x180072765  mov     cs:dword_1800BD364, 0
0x18007276f  cmp     cs:BindingVector, 0
0x180072777  jz      short loc_180072786
0x180072779  lea     rcx, BindingVector; BindingVector
0x180072780  call    cs:__imp_RpcBindingVectorFree
0x180072786  mov     edx, 44663036h
0x18007278b  lea     rcx, ?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x180072792  call    ?ItSpUpdateStatus@@YAXPEAU_ITSRV_GLOBAL_CONTEXT@@W4_ITSRV_GLOBAL_CONTEXT_STATUS@@@Z; ItSpUpdateStatus(_ITSRV_GLOBAL_CONTEXT *,_ITSRV_GLOBAL_CONTEXT_STATUS)
0x180072797  mov     rbx, [rsp+28h+arg_0]
0x18007279c  add     rsp, 20h
0x1800727a0  pop     rsi
0x1800727a1  retn
```
