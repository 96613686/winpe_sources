# ItSrvRegisterIdleTask

- ea: `0x180078170`
- end: `0x180078513`
- name: `ItSrvRegisterIdleTask`
- size: `931`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800403a4`
- `0x18005599c`
- `0x180075e48`
- `0x180078170`
- `0x1800829fa`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800782e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800782e7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180078282`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800782d7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180078282`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800782d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078494`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078494`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800783c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078470`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800784f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800783c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078470`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800784f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007834c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007837b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007834c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007837b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007830d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007845a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007830d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007845a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180078321`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180078321`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800784db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800784db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800784c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800784c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800781ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800781ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078250`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800782a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078250`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800782a5`
- `RPCRT4!RpcImpersonateClient` at `0x180078200`
- `RPCRT4!RpcImpersonateClient` at `0x180078200`
- `RPCRT4!RpcRevertToSelf` at `0x1800782fa`
- `RPCRT4!RpcRevertToSelf` at `0x1800784a5`
- `RPCRT4!RpcRevertToSelf` at `0x1800782fa`
- `RPCRT4!RpcRevertToSelf` at `0x1800784a5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078221`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180078221`

## pseudocode

```c
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
    EnterCriticalSection(&stru_1800C12E8);
    v9 = 1;
    if ( !ItSpCheckRegistrationExempts(v15, v10) )
    {
LABEL_15:
      LastError = 0;
      goto LABEL_31;
    }
    if ( *((_DWORD *)v7 + 7) == 7 )
    {
      EnterCriticalSection(&stru_1800C1360);
      *((_DWORD *)v7 + 4) |= 1u;
      Flink = stru_1800C1388.Flink;
      ++dword_1800C1398;
      if ( stru_1800C1388.Flink->Blink == &stru_1800C1388 )
      {
        *((_QWORD *)v7 + 1) = &stru_1800C1388;
        *(_QWORD *)v7 = Flink;
        Flink->Blink = (struct _LIST_ENTRY *)v7;
        stru_1800C1388.Flink = (struct _LIST_ENTRY *)v7;
        *((_DWORD *)v7 + 5) = 1;
        LeaveCriticalSection(&stru_1800C1360);
        goto LABEL_15;
      }
    }
    else
    {
      if ( dword_1800C1328 >= (unsigned int)dword_1800C1450 )
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
      ++dword_1800C1328;
      Blink = stru_1800C1310.Blink;
      if ( stru_1800C1310.Blink->Flink == &stru_1800C1310 )
      {
        *(_QWORD *)v7 = &stru_1800C1310;
        *((_QWORD *)v7 + 1) = Blink;
        Blink->Flink = (struct _LIST_ENTRY *)v7;
        stru_1800C1310.Blink = (struct _LIST_ENTRY *)v7;
        ResetEvent(qword_1800C1320);
        *((_DWORD *)v7 + 5) = 1;
        LeaveCriticalSection(&stru_1800C12E8);
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
    LeaveCriticalSection(&stru_1800C12E8);
  return LastError;
}

```

## disassembly

```asm
0x180078170  mov     [rsp+arg_8], rdx
0x180078175  push    rbx
0x180078176  push    rbp
0x180078177  push    rsi
0x180078178  push    rdi
0x180078179  push    r12
0x18007817b  push    r13
0x18007817d  push    r14
0x18007817f  push    r15
0x180078181  sub     rsp, 48h
0x180078185  mov     rsi, r8
0x180078188  mov     qword ptr [rdx], 0
0x18007818f  mov     r15, rdx
0x180078192  call    cs:__imp_GetProcessHeap
0x180078199  nop     dword ptr [rax+rax+00h]
0x18007819e  mov     ebx, 48h ; 'H'
0x1800781a3  xor     edx, edx; dwFlags
0x1800781a5  mov     rcx, rax; hHeap
0x1800781a8  mov     r8d, ebx; dwBytes
0x1800781ab  call    cs:__imp_HeapAlloc
0x1800781b2  nop     dword ptr [rax+rax+00h]
0x1800781b7  mov     rdi, rax
0x1800781ba  test    rax, rax
0x1800781bd  jnz     short loc_1800781C7
0x1800781bf  lea     ebx, [rax+8]
0x1800781c2  jmp     loc_1800784FF
0x1800781c7  mov     r8, rbx; Size
0x1800781ca  xor     edx, edx; Val
0x1800781cc  mov     rcx, rdi; void *
0x1800781cf  xor     r12b, r12b
0x1800781d2  call    memset_0
0x1800781d7  movups  xmm0, xmmword ptr [rsi]
0x1800781da  movups  xmmword ptr [rdi+18h], xmm0
0x1800781de  movups  xmm1, xmmword ptr [rsi+10h]
0x1800781e2  movups  xmmword ptr [rdi+28h], xmm1
0x1800781e6  cmp     dword ptr [rdi+18h], 20h ; ' '
0x1800781ea  jnz     loc_1800784BA
0x1800781f0  mov     ebx, 8
0x1800781f5  cmp     [rdi+1Ch], ebx
0x1800781f8  ja      loc_1800784BA
0x1800781fe  xor     ecx, ecx; BindingHandle
0x180078200  call    cs:__imp_RpcImpersonateClient
0x180078207  nop     dword ptr [rax+rax+00h]
0x18007820c  mov     ebx, eax
0x18007820e  test    eax, eax
0x180078210  jnz     loc_1800784BF
0x180078216  mov     r8d, [rsi+8]; dwProcessId
0x18007821a  xor     edx, edx; bInheritHandle
0x18007821c  mov     ecx, 1FFFFFh; dwDesiredAccess
0x180078221  call    cs:__imp_OpenProcess
0x180078228  nop     dword ptr [rax+rax+00h]
0x18007822d  mov     rbp, rax
0x180078230  test    rax, rax
0x180078233  jnz     short loc_180078248
0x180078235  call    cs:__imp_GetLastError
0x18007823c  nop     dword ptr [rax+rax+00h]
0x180078241  mov     ebx, eax
0x180078243  jmp     loc_1800784A5
0x180078248  mov     ebx, 1
0x18007824d  mov     r13b, bl
0x180078250  call    cs:__imp_GetCurrentProcess
0x180078257  nop     dword ptr [rax+rax+00h]
0x18007825c  mov     rdx, [rsi+10h]; hSourceHandle
0x180078260  lea     r9, [rdi+38h]; lpTargetHandle
0x180078264  mov     [rsp+88h+dwOptions], 0; dwOptions
0x18007826c  mov     r8, rax; hTargetProcessHandle
0x18007826f  mov     dword ptr [rsp+88h+bInheritHandle], 0; bInheritHandle
0x180078277  mov     rcx, rbp; hSourceProcessHandle
0x18007827a  mov     dword ptr [rsp+88h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180078282  call    cs:__imp_DuplicateHandle
0x180078289  nop     dword ptr [rax+rax+00h]
0x18007828e  test    eax, eax
0x180078290  jnz     short loc_1800782A5
0x180078292  call    cs:__imp_GetLastError
0x180078299  nop     dword ptr [rax+rax+00h]
0x18007829e  mov     ebx, eax
0x1800782a0  jmp     loc_180078491
0x1800782a5  call    cs:__imp_GetCurrentProcess
0x1800782ac  nop     dword ptr [rax+rax+00h]
0x1800782b1  mov     rdx, [rsi+18h]; hSourceHandle
0x1800782b5  lea     r9, [rdi+40h]; lpTargetHandle
0x1800782b9  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800782c1  mov     r8, rax; hTargetProcessHandle
0x1800782c4  mov     dword ptr [rsp+88h+bInheritHandle], 0; struct _GUID *
0x1800782cc  mov     rcx, rbp; hSourceProcessHandle
0x1800782cf  mov     dword ptr [rsp+88h+dwDesiredAccess], 1F0003h; void *
0x1800782d7  call    cs:__imp_DuplicateHandle
0x1800782de  nop     dword ptr [rax+rax+00h]
0x1800782e3  test    eax, eax
0x1800782e5  jnz     short loc_1800782FA
0x1800782e7  call    cs:__imp_GetLastError
0x1800782ee  nop     dword ptr [rax+rax+00h]
0x1800782f3  mov     ebx, eax
0x1800782f5  jmp     loc_180078489
0x1800782fa  call    cs:__imp_RpcRevertToSelf
0x180078301  nop     dword ptr [rax+rax+00h]
0x180078306  mov     rcx, [rdi+38h]; hEvent
0x18007830a  xor     r13b, r13b
0x18007830d  call    cs:__imp_ResetEvent
0x180078314  nop     dword ptr [rax+rax+00h]
0x180078319  test    eax, eax
0x18007831b  jz      short loc_1800782E7
0x18007831d  mov     rcx, [rdi+40h]; hEvent
0x180078321  call    cs:__imp_SetEvent
0x180078328  nop     dword ptr [rax+rax+00h]
0x18007832d  test    eax, eax
0x18007832f  jz      short loc_1800782E7
0x180078331  mov     r9d, [rdi+20h]; unsigned int
0x180078335  lea     rdx, ItSpEvt_RegisterIdleTask; struct _EVENT_DESCRIPTOR *
0x18007833c  mov     r8d, [rdi+1Ch]; unsigned int
0x180078340  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,void *,_GUID const *)
0x180078345  lea     rcx, stru_1800C12E8; lpCriticalSection
0x18007834c  call    cs:__imp_EnterCriticalSection
0x180078353  nop     dword ptr [rax+rax+00h]
0x180078358  mov     rdx, rbp; void *
0x18007835b  mov     r12b, bl
0x18007835e  call    ?ItSpCheckRegistrationExempts@@YAEPEAU_ITSRV_GLOBAL_CONTEXT@@PEAX@Z; ItSpCheckRegistrationExempts(_ITSRV_GLOBAL_CONTEXT *,void *)
0x180078363  test    al, al
0x180078365  jnz     short loc_18007836E
0x180078367  xor     ebx, ebx
0x180078369  jmp     loc_180078489
0x18007836e  cmp     dword ptr [rdi+1Ch], 7
0x180078372  jnz     short loc_1800783D2
0x180078374  lea     rcx, stru_1800C1360; lpCriticalSection
0x18007837b  call    cs:__imp_EnterCriticalSection
0x180078382  nop     dword ptr [rax+rax+00h]
0x180078387  or      [rdi+10h], ebx
0x18007838a  lea     rcx, stru_1800C1388
0x180078391  mov     rax, cs:stru_1800C1388.Flink
0x180078398  add     cs:dword_1800C1398, ebx
0x18007839e  cmp     [rax+8], rcx
0x1800783a2  jnz     loc_18007843B
0x1800783a8  mov     [rdi+8], rcx
0x1800783ac  lea     rcx, stru_1800C1360; lpCriticalSection
0x1800783b3  mov     [rdi], rax
0x1800783b6  mov     [rax+8], rdi
0x1800783ba  mov     cs:stru_1800C1388.Flink, rdi
0x1800783c1  mov     [rdi+14h], ebx
0x1800783c4  call    cs:__imp_LeaveCriticalSection
0x1800783cb  nop     dword ptr [rax+rax+00h]
0x1800783d0  jmp     short loc_180078367
0x1800783d2  mov     edx, cs:dword_1800C1328
0x1800783d8  cmp     edx, cs:dword_1800C1450
0x1800783de  jb      short loc_1800783EA
0x1800783e0  mov     ebx, 4
0x1800783e5  jmp     loc_180078489
0x1800783ea  mov     ecx, cs:?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x1800783f0  sub     ecx, 44663031h
0x1800783f6  jz      loc_180078484
0x1800783fc  sub     ecx, ebx
0x1800783fe  jz      short loc_18007841F
0x180078400  sub     ecx, ebx
0x180078402  jz      short loc_18007841F
0x180078404  sub     ecx, ebx
0x180078406  jz      short loc_18007841F
0x180078408  mov     r15, [rsp+88h+arg_8]
0x180078410  sub     ecx, ebx
0x180078412  jz      short loc_180078418
0x180078414  cmp     ecx, ebx
0x180078416  jnz     short loc_180078491
0x180078418  mov     ebx, 15h
0x18007841d  jmp     short loc_180078491
0x18007841f  lea     eax, [rdx+1]
0x180078422  mov     cs:dword_1800C1328, eax
0x180078428  lea     rcx, stru_1800C1310
0x18007842f  mov     rax, cs:stru_1800C1310.Blink
0x180078436  cmp     [rax], rcx
0x180078439  jz      short loc_180078442
0x18007843b  mov     ecx, 3
0x180078440  int     29h; Win8: RtlFailFast(ecx)
0x180078442  mov     [rdi], rcx
0x180078445  mov     [rdi+8], rax
0x180078449  mov     [rax], rdi
0x18007844c  mov     rcx, cs:qword_1800C1320; hEvent
0x180078453  mov     cs:stru_1800C1310.Blink, rdi
0x18007845a  call    cs:__imp_ResetEvent
0x180078461  nop     dword ptr [rax+rax+00h]
0x180078466  lea     rcx, stru_1800C12E8; lpCriticalSection
0x18007846d  mov     [rdi+14h], ebx
0x180078470  call    cs:__imp_LeaveCriticalSection
0x180078477  nop     dword ptr [rax+rax+00h]
0x18007847c  xor     r12b, r12b
0x18007847f  jmp     loc_180078367
0x180078484  mov     ebx, 15h
0x180078489  mov     r15, [rsp+88h+arg_8]
0x180078491  mov     rcx, rbp; hObject
0x180078494  call    cs:__imp_CloseHandle
0x18007849b  nop     dword ptr [rax+rax+00h]
0x1800784a0  test    r13b, r13b
0x1800784a3  jz      short loc_1800784B1
0x1800784a5  call    cs:__imp_RpcRevertToSelf
0x1800784ac  nop     dword ptr [rax+rax+00h]
0x1800784b1  test    ebx, ebx
0x1800784b3  jnz     short loc_1800784BF
0x1800784b5  mov     [r15], rdi
0x1800784b8  jmp     short loc_1800784E7
0x1800784ba  mov     ebx, 0Bh
0x1800784bf  mov     rcx, rdi; struct _ITSRV_IDLE_TASK_CONTEXT *
0x1800784c2  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x1800784c7  call    cs:__imp_GetProcessHeap
0x1800784ce  nop     dword ptr [rax+rax+00h]
0x1800784d3  mov     r8, rdi; lpMem
0x1800784d6  xor     edx, edx; dwFlags
0x1800784d8  mov     rcx, rax; hHeap
0x1800784db  call    cs:__imp_HeapFree
0x1800784e2  nop     dword ptr [rax+rax+00h]
0x1800784e7  test    r12b, r12b
0x1800784ea  jz      short loc_1800784FF
0x1800784ec  lea     rcx, stru_1800C12E8; lpCriticalSection
0x1800784f3  call    cs:__imp_LeaveCriticalSection
0x1800784fa  nop     dword ptr [rax+rax+00h]
0x1800784ff  mov     eax, ebx
0x180078501  add     rsp, 48h
0x180078505  pop     r15
0x180078507  pop     r14
0x180078509  pop     r13
0x18007850b  pop     r12
0x18007850d  pop     rdi
0x18007850e  pop     rsi
0x18007850f  pop     rbp
0x180078510  pop     rbx
0x180078511  retn
```
