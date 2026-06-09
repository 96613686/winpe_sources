# ItSrvRegisterIdleTask

- ea: `0x180074390`
- end: `0x18007469e`
- name: `ItSrvRegisterIdleTask`
- size: `782`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callees

- `0x18003e8f8`
- `0x18005318c`
- `0x180072498`
- `0x180074390`
- `0x18007e68a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007443d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800744cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007443d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800744cb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007447e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800744c1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007447e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800744c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007463e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007463e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074584`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074620`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074685`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074584`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074620`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074685`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074518`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074541`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074518`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074541`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800744e5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180074610`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800744e5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180074610`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800744f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800744f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074673`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074673`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800743b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074665`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800743b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074665`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800743c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800743c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074495`
- `RPCRT4!RpcImpersonateClient` at `0x180074414`
- `RPCRT4!RpcImpersonateClient` at `0x180074414`
- `RPCRT4!RpcRevertToSelf` at `0x1800744d8`
- `RPCRT4!RpcRevertToSelf` at `0x180074649`
- `RPCRT4!RpcRevertToSelf` at `0x1800744d8`
- `RPCRT4!RpcRevertToSelf` at `0x180074649`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007442f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007442f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ItSrvRegisterIdleTask(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // r15
  HANDLE ProcessHeap; // rax
  char *v6; // rax
  char *v7; // rdi
  DWORD LastError; // ebx
  char v9; // r12
  HANDLE v10; // rbp
  char v11; // r13
  HANDLE CurrentProcess; // rax
  HANDLE v13; // rax
  EventManager *v14; // rcx
  struct _ITSRV_GLOBAL_CONTEXT *v15; // rcx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rax
  HANDLE v18; // rax
  void *dwDesiredAccess; // [rsp+20h] [rbp-68h]
  const struct _GUID *bInheritHandle; // [rsp+28h] [rbp-60h]

  *a2 = 0;
  v4 = a2;
  ProcessHeap = GetProcessHeap();
  v6 = (char *)HeapAlloc(ProcessHeap, 0, 0x48u);
  v7 = v6;
  if ( !v6 )
    return 8;
  v9 = 0;
  memset_0(v6, 0, 0x48u);
  *(_OWORD *)(v7 + 24) = *(_OWORD *)a3;
  *(_OWORD *)(v7 + 40) = *(_OWORD *)(a3 + 16);
  if ( *((_DWORD *)v7 + 6) != 32 || *((_DWORD *)v7 + 7) > 8u )
  {
    LastError = 11;
    goto LABEL_37;
  }
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    v10 = OpenProcess(0x1FFFFFu, 0, *(_DWORD *)(a3 + 8));
    if ( !v10 )
    {
      LastError = GetLastError();
LABEL_33:
      RpcRevertToSelf();
LABEL_34:
      if ( !LastError )
      {
        *v4 = v7;
        goto LABEL_38;
      }
      goto LABEL_37;
    }
    LastError = 1;
    v11 = 1;
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v10, *(HANDLE *)(a3 + 16), CurrentProcess, (LPHANDLE)v7 + 7, 0x1F0003u, 0, 0) )
    {
      LastError = GetLastError();
      goto LABEL_32;
    }
    v13 = GetCurrentProcess();
    if ( !DuplicateHandle(v10, *(HANDLE *)(a3 + 24), v13, (LPHANDLE)v7 + 8, 0x1F0003u, 0, 0)
      || (RpcRevertToSelf(), v11 = 0, !ResetEvent(*((HANDLE *)v7 + 7)))
      || !SetEvent(*((HANDLE *)v7 + 8)) )
    {
      LastError = GetLastError();
LABEL_31:
      v4 = a2;
      goto LABEL_32;
    }
    EventManager::EvtReport(
      v14,
      &ItSpEvt_RegisterIdleTask,
      *((_DWORD *)v7 + 7),
      *((_DWORD *)v7 + 8),
      dwDesiredAccess,
      bInheritHandle);
    EnterCriticalSection(&stru_1800BD1E8);
    v9 = 1;
    if ( !ItSpCheckRegistrationExempts(v15, v10) )
    {
LABEL_15:
      LastError = 0;
      goto LABEL_31;
    }
    if ( *((_DWORD *)v7 + 7) == 7 )
    {
      EnterCriticalSection(&stru_1800BD260);
      *((_DWORD *)v7 + 4) |= 1u;
      Flink = stru_1800BD288.Flink;
      ++dword_1800BD298;
      if ( stru_1800BD288.Flink->Blink == &stru_1800BD288 )
      {
        *((_QWORD *)v7 + 1) = &stru_1800BD288;
        *(_QWORD *)v7 = Flink;
        Flink->Blink = (struct _LIST_ENTRY *)v7;
        stru_1800BD288.Flink = (struct _LIST_ENTRY *)v7;
        *((_DWORD *)v7 + 5) = 1;
        LeaveCriticalSection(&stru_1800BD260);
        goto LABEL_15;
      }
    }
    else
    {
      if ( dword_1800BD228 >= (unsigned int)dword_1800BD350 )
      {
        LastError = 4;
        goto LABEL_31;
      }
      if ( ItSrvGlobalContext == 1147547697 )
      {
        LastError = 21;
        goto LABEL_31;
      }
      if ( ItSrvGlobalContext != 1147547698 && ItSrvGlobalContext != 1147547699 && ItSrvGlobalContext != 1147547700 )
      {
        v4 = a2;
        if ( (unsigned int)(ItSrvGlobalContext - 1147547701) <= 1 )
          LastError = 21;
LABEL_32:
        CloseHandle(v10);
        if ( !v11 )
          goto LABEL_34;
        goto LABEL_33;
      }
      ++dword_1800BD228;
      Blink = stru_1800BD210.Blink;
      if ( stru_1800BD210.Blink->Flink == &stru_1800BD210 )
      {
        *(_QWORD *)v7 = &stru_1800BD210;
        *((_QWORD *)v7 + 1) = Blink;
        Blink->Flink = (struct _LIST_ENTRY *)v7;
        stru_1800BD210.Blink = (struct _LIST_ENTRY *)v7;
        ResetEvent(qword_1800BD220);
        *((_DWORD *)v7 + 5) = 1;
        LeaveCriticalSection(&stru_1800BD1E8);
        v9 = 0;
        goto LABEL_15;
      }
    }
    __fastfail(3u);
  }
LABEL_37:
  ItSpCleanupIdleTask((struct _ITSRV_IDLE_TASK_CONTEXT *)v7);
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v7);
LABEL_38:
  if ( v9 )
    LeaveCriticalSection(&stru_1800BD1E8);
  return LastError;
}

```

## disassembly

```asm
0x180074390  mov     [rsp+arg_8], rdx
0x180074395  push    rbx
0x180074396  push    rbp
0x180074397  push    rsi
0x180074398  push    rdi
0x180074399  push    r12
0x18007439b  push    r13
0x18007439d  push    r14
0x18007439f  push    r15
0x1800743a1  sub     rsp, 48h
0x1800743a5  mov     rsi, r8
0x1800743a8  mov     qword ptr [rdx], 0
0x1800743af  mov     r15, rdx
0x1800743b2  call    cs:__imp_GetProcessHeap
0x1800743b8  mov     ebx, 48h ; 'H'
0x1800743bd  xor     edx, edx; dwFlags
0x1800743bf  mov     rcx, rax; hHeap
0x1800743c2  mov     r8d, ebx; dwBytes
0x1800743c5  call    cs:__imp_HeapAlloc
0x1800743cb  mov     rdi, rax
0x1800743ce  test    rax, rax
0x1800743d1  jnz     short loc_1800743DB
0x1800743d3  lea     ebx, [rax+8]
0x1800743d6  jmp     loc_18007468B
0x1800743db  mov     r8, rbx; Size
0x1800743de  xor     edx, edx; Val
0x1800743e0  mov     rcx, rdi; void *
0x1800743e3  xor     r12b, r12b
0x1800743e6  call    memset_0
0x1800743eb  movups  xmm0, xmmword ptr [rsi]
0x1800743ee  movups  xmmword ptr [rdi+18h], xmm0
0x1800743f2  movups  xmm1, xmmword ptr [rsi+10h]
0x1800743f6  movups  xmmword ptr [rdi+28h], xmm1
0x1800743fa  cmp     dword ptr [rdi+18h], 20h ; ' '
0x1800743fe  jnz     loc_180074658
0x180074404  mov     ebx, 8
0x180074409  cmp     [rdi+1Ch], ebx
0x18007440c  ja      loc_180074658
0x180074412  xor     ecx, ecx; BindingHandle
0x180074414  call    cs:__imp_RpcImpersonateClient
0x18007441a  mov     ebx, eax
0x18007441c  test    eax, eax
0x18007441e  jnz     loc_18007465D
0x180074424  mov     r8d, [rsi+8]; dwProcessId
0x180074428  xor     edx, edx; bInheritHandle
0x18007442a  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18007442f  call    cs:__imp_OpenProcess
0x180074435  mov     rbp, rax
0x180074438  test    rax, rax
0x18007443b  jnz     short loc_18007444A
0x18007443d  call    cs:__imp_GetLastError
0x180074443  mov     ebx, eax
0x180074445  jmp     loc_180074649
0x18007444a  mov     ebx, 1
0x18007444f  mov     r13b, bl
0x180074452  call    cs:__imp_GetCurrentProcess
0x180074458  mov     rdx, [rsi+10h]; hSourceHandle
0x18007445c  lea     r9, [rdi+38h]; lpTargetHandle
0x180074460  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180074468  mov     r8, rax; hTargetProcessHandle
0x18007446b  mov     dword ptr [rsp+88h+bInheritHandle], 0; bInheritHandle
0x180074473  mov     rcx, rbp; hSourceProcessHandle
0x180074476  mov     dword ptr [rsp+88h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18007447e  call    cs:__imp_DuplicateHandle
0x180074484  test    eax, eax
0x180074486  jnz     short loc_180074495
0x180074488  call    cs:__imp_GetLastError
0x18007448e  mov     ebx, eax
0x180074490  jmp     loc_18007463B
0x180074495  call    cs:__imp_GetCurrentProcess
0x18007449b  mov     rdx, [rsi+18h]; hSourceHandle
0x18007449f  lea     r9, [rdi+40h]; lpTargetHandle
0x1800744a3  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800744ab  mov     r8, rax; hTargetProcessHandle
0x1800744ae  mov     dword ptr [rsp+88h+bInheritHandle], 0; struct _GUID *
0x1800744b6  mov     rcx, rbp; hSourceProcessHandle
0x1800744b9  mov     dword ptr [rsp+88h+dwDesiredAccess], 1F0003h; void *
0x1800744c1  call    cs:__imp_DuplicateHandle
0x1800744c7  test    eax, eax
0x1800744c9  jnz     short loc_1800744D8
0x1800744cb  call    cs:__imp_GetLastError
0x1800744d1  mov     ebx, eax
0x1800744d3  jmp     loc_180074633
0x1800744d8  call    cs:__imp_RpcRevertToSelf
0x1800744de  mov     rcx, [rdi+38h]; hEvent
0x1800744e2  xor     r13b, r13b
0x1800744e5  call    cs:__imp_ResetEvent
0x1800744eb  test    eax, eax
0x1800744ed  jz      short loc_1800744CB
0x1800744ef  mov     rcx, [rdi+40h]; hEvent
0x1800744f3  call    cs:__imp_SetEvent
0x1800744f9  test    eax, eax
0x1800744fb  jz      short loc_1800744CB
0x1800744fd  mov     r9d, [rdi+20h]; unsigned int
0x180074501  lea     rdx, ItSpEvt_RegisterIdleTask; struct _EVENT_DESCRIPTOR *
0x180074508  mov     r8d, [rdi+1Ch]; unsigned int
0x18007450c  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,void *,_GUID const *)
0x180074511  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x180074518  call    cs:__imp_EnterCriticalSection
0x18007451e  mov     rdx, rbp; void *
0x180074521  mov     r12b, bl
0x180074524  call    ?ItSpCheckRegistrationExempts@@YAEPEAU_ITSRV_GLOBAL_CONTEXT@@PEAX@Z; ItSpCheckRegistrationExempts(_ITSRV_GLOBAL_CONTEXT *,void *)
0x180074529  test    al, al
0x18007452b  jnz     short loc_180074534
0x18007452d  xor     ebx, ebx
0x18007452f  jmp     loc_180074633
0x180074534  cmp     dword ptr [rdi+1Ch], 7
0x180074538  jnz     short loc_18007458C
0x18007453a  lea     rcx, stru_1800BD260; lpCriticalSection
0x180074541  call    cs:__imp_EnterCriticalSection
0x180074547  or      [rdi+10h], ebx
0x18007454a  lea     rcx, stru_1800BD288
0x180074551  mov     rax, cs:stru_1800BD288.Flink
0x180074558  add     cs:dword_1800BD298, ebx
0x18007455e  cmp     [rax+8], rcx
0x180074562  jnz     loc_1800745F1
0x180074568  mov     [rdi+8], rcx
0x18007456c  lea     rcx, stru_1800BD260; lpCriticalSection
0x180074573  mov     [rdi], rax
0x180074576  mov     [rax+8], rdi
0x18007457a  mov     cs:stru_1800BD288.Flink, rdi
0x180074581  mov     [rdi+14h], ebx
0x180074584  call    cs:__imp_LeaveCriticalSection
0x18007458a  jmp     short loc_18007452D
0x18007458c  mov     edx, cs:dword_1800BD228
0x180074592  cmp     edx, cs:dword_1800BD350
0x180074598  jb      short loc_1800745A4
0x18007459a  mov     ebx, 4
0x18007459f  jmp     loc_180074633
0x1800745a4  mov     ecx, cs:?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x1800745aa  sub     ecx, 44663031h
0x1800745b0  jz      short loc_18007462E
0x1800745b2  sub     ecx, ebx
0x1800745b4  jz      short loc_1800745D5
0x1800745b6  sub     ecx, ebx
0x1800745b8  jz      short loc_1800745D5
0x1800745ba  sub     ecx, ebx
0x1800745bc  jz      short loc_1800745D5
0x1800745be  mov     r15, [rsp+88h+arg_8]
0x1800745c6  sub     ecx, ebx
0x1800745c8  jz      short loc_1800745CE
0x1800745ca  cmp     ecx, ebx
0x1800745cc  jnz     short loc_18007463B
0x1800745ce  mov     ebx, 15h
0x1800745d3  jmp     short loc_18007463B
0x1800745d5  lea     eax, [rdx+1]
0x1800745d8  mov     cs:dword_1800BD228, eax
0x1800745de  lea     rcx, stru_1800BD210
0x1800745e5  mov     rax, cs:stru_1800BD210.Blink
0x1800745ec  cmp     [rax], rcx
0x1800745ef  jz      short loc_1800745F8
0x1800745f1  mov     ecx, 3
0x1800745f6  int     29h; Win8: RtlFailFast(ecx)
0x1800745f8  mov     [rdi], rcx
0x1800745fb  mov     [rdi+8], rax
0x1800745ff  mov     [rax], rdi
0x180074602  mov     rcx, cs:qword_1800BD220; hEvent
0x180074609  mov     cs:stru_1800BD210.Blink, rdi
0x180074610  call    cs:__imp_ResetEvent
0x180074616  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x18007461d  mov     [rdi+14h], ebx
0x180074620  call    cs:__imp_LeaveCriticalSection
0x180074626  xor     r12b, r12b
0x180074629  jmp     loc_18007452D
0x18007462e  mov     ebx, 15h
0x180074633  mov     r15, [rsp+88h+arg_8]
0x18007463b  mov     rcx, rbp; hObject
0x18007463e  call    cs:__imp_CloseHandle
0x180074644  test    r13b, r13b
0x180074647  jz      short loc_18007464F
0x180074649  call    cs:__imp_RpcRevertToSelf
0x18007464f  test    ebx, ebx
0x180074651  jnz     short loc_18007465D
0x180074653  mov     [r15], rdi
0x180074656  jmp     short loc_180074679
0x180074658  mov     ebx, 0Bh
0x18007465d  mov     rcx, rdi; struct _ITSRV_IDLE_TASK_CONTEXT *
0x180074660  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x180074665  call    cs:__imp_GetProcessHeap
0x18007466b  mov     r8, rdi; lpMem
0x18007466e  xor     edx, edx; dwFlags
0x180074670  mov     rcx, rax; hHeap
0x180074673  call    cs:__imp_HeapFree
0x180074679  test    r12b, r12b
0x18007467c  jz      short loc_18007468B
0x18007467e  lea     rcx, stru_1800BD1E8; lpCriticalSection
0x180074685  call    cs:__imp_LeaveCriticalSection
0x18007468b  mov     eax, ebx
0x18007468d  add     rsp, 48h
0x180074691  pop     r15
0x180074693  pop     r14
0x180074695  pop     r13
0x180074697  pop     r12
0x180074699  pop     rdi
0x18007469a  pop     rsi
0x18007469b  pop     rbp
0x18007469c  pop     rbx
0x18007469d  retn
```
