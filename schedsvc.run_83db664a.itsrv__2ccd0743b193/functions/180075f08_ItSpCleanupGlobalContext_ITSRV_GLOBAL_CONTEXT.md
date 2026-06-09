# ItSpCleanupGlobalContext(_ITSRV_GLOBAL_CONTEXT *)

- ea: `0x180075f08`
- end: `0x1800761e7`
- name: `?ItSpCleanupGlobalContext@@YAXPEAU_ITSRV_GLOBAL_CONTEXT@@@Z`
- size: `735`
- prototype: `void __fastcall(struct _ITSRV_GLOBAL_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180077974`
- `0x1800787fc`

## callees

- `0x180054f58`
- `0x18005599c`
- `0x180075f08`
- `0x180077914`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075f93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075fab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075fc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075ff3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007600b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007607f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075f93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075fab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075fc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075ff3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007600b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007607f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075f3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075f50`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075f63`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075f3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075f50`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075f63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800760fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076157`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007618c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800760fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076157`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007618c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076053`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800760e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076143`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076178`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076053`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800760e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076143`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076178`
- `RPCRT4!RpcBindingVectorFree` at `0x1800761be`
- `RPCRT4!RpcBindingVectorFree` at `0x1800761be`
- `WMICLNT!WmiCloseBlock` at `0x18007603b`
- `WMICLNT!WmiCloseBlock` at `0x18007603b`

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
    DeleteCriticalSection(&stru_1800C12E8);
    DeleteCriticalSection(&stru_1800C1360);
    DeleteCriticalSection(&stru_1800C1330);
    if ( hObject )
      CloseHandle(hObject);
    if ( qword_1800C1410 )
      CloseHandle(qword_1800C1410);
    if ( hHandle )
      CloseHandle(hHandle);
    if ( qword_1800C1420 )
      CloseHandle(qword_1800C1420);
    if ( qword_1800C15A0 )
      CloseHandle(qword_1800C15A0);
    if ( qword_1800C1598 )
      CloseHandle(qword_1800C1598);
    if ( hEvent )
      CloseHandle(hEvent);
    if ( qword_1800C1320 )
      CloseHandle(qword_1800C1320);
    if ( qword_1800C1470 )
      WmiCloseBlock();
    v1 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    if ( qword_1800C1488 )
      CloseHandle(qword_1800C1488);
    ItSpCleanupSystemSnapshot((struct _ITSRV_SYSTEM_SNAPSHOT *)&dword_1800C1490);
    ItSpCleanupSystemSnapshot((struct _ITSRV_SYSTEM_SNAPSHOT *)&dword_1800C14E8);
    while ( 1 )
    {
      Flink = (struct _ITSRV_IDLE_TASK_CONTEXT *)stru_1800C1310.Flink;
      if ( stru_1800C1310.Flink == &stru_1800C1310 )
        break;
      --dword_1800C1328;
      if ( stru_1800C1310.Flink->Blink != &stru_1800C1310
        || (v4 = stru_1800C1310.Flink->Flink, stru_1800C1310.Flink->Flink->Blink != stru_1800C1310.Flink) )
      {
LABEL_34:
        __fastfail(3u);
      }
      stru_1800C1310.Flink = stru_1800C1310.Flink->Flink;
      v4->Blink = &stru_1800C1310;
      ItSpCleanupIdleTask(Flink);
      v5 = GetProcessHeap();
      HeapFree(v5, 0, Flink);
    }
    while ( 1 )
    {
      v6 = (struct _ITSRV_IDLE_TASK_CONTEXT *)stru_1800C1388.Flink;
      if ( stru_1800C1388.Flink == &stru_1800C1388 )
        break;
      --dword_1800C1398;
      if ( stru_1800C1388.Flink->Blink != &stru_1800C1388 )
        goto LABEL_34;
      v7 = stru_1800C1388.Flink->Flink;
      if ( stru_1800C1388.Flink->Flink->Blink != stru_1800C1388.Flink )
        goto LABEL_34;
      stru_1800C1388.Flink = stru_1800C1388.Flink->Flink;
      v7->Blink = &stru_1800C1388;
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
      dword_1800C1464 = 0;
    }
    if ( BindingVector )
      RpcBindingVectorFree(&BindingVector);
    ItSpUpdateStatus(&ItSrvGlobalContext, 1147547702);
  }
}

```

## disassembly

```asm
0x180075f08  mov     [rsp+arg_0], rbx
0x180075f0d  push    rsi
0x180075f0e  sub     rsp, 20h
0x180075f12  cmp     cs:Timer, 0
0x180075f1a  jnz     loc_1800761DB
0x180075f20  mov     eax, cs:?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x180075f26  add     eax, 0BB99CFCFh
0x180075f2b  test    eax, 0FFFFFFFBh
0x180075f30  jnz     loc_1800761DB
0x180075f36  lea     rcx, stru_1800C12E8; lpCriticalSection
0x180075f3d  call    cs:__imp_DeleteCriticalSection
0x180075f44  nop     dword ptr [rax+rax+00h]
0x180075f49  lea     rcx, stru_1800C1360; lpCriticalSection
0x180075f50  call    cs:__imp_DeleteCriticalSection
0x180075f57  nop     dword ptr [rax+rax+00h]
0x180075f5c  lea     rcx, stru_1800C1330; lpCriticalSection
0x180075f63  call    cs:__imp_DeleteCriticalSection
0x180075f6a  nop     dword ptr [rax+rax+00h]
0x180075f6f  mov     rcx, cs:hObject; hObject
0x180075f76  test    rcx, rcx
0x180075f79  jz      short loc_180075F87
0x180075f7b  call    cs:__imp_CloseHandle
0x180075f82  nop     dword ptr [rax+rax+00h]
0x180075f87  mov     rcx, cs:qword_1800C1410; hObject
0x180075f8e  test    rcx, rcx
0x180075f91  jz      short loc_180075F9F
0x180075f93  call    cs:__imp_CloseHandle
0x180075f9a  nop     dword ptr [rax+rax+00h]
0x180075f9f  mov     rcx, cs:hHandle; hObject
0x180075fa6  test    rcx, rcx
0x180075fa9  jz      short loc_180075FB7
0x180075fab  call    cs:__imp_CloseHandle
0x180075fb2  nop     dword ptr [rax+rax+00h]
0x180075fb7  mov     rcx, cs:qword_1800C1420; hObject
0x180075fbe  test    rcx, rcx
0x180075fc1  jz      short loc_180075FCF
0x180075fc3  call    cs:__imp_CloseHandle
0x180075fca  nop     dword ptr [rax+rax+00h]
0x180075fcf  mov     rcx, cs:qword_1800C15A0; hObject
0x180075fd6  test    rcx, rcx
0x180075fd9  jz      short loc_180075FE7
0x180075fdb  call    cs:__imp_CloseHandle
0x180075fe2  nop     dword ptr [rax+rax+00h]
0x180075fe7  mov     rcx, cs:qword_1800C1598; hObject
0x180075fee  test    rcx, rcx
0x180075ff1  jz      short loc_180075FFF
0x180075ff3  call    cs:__imp_CloseHandle
0x180075ffa  nop     dword ptr [rax+rax+00h]
0x180075fff  mov     rcx, cs:hEvent; hObject
0x180076006  test    rcx, rcx
0x180076009  jz      short loc_180076017
0x18007600b  call    cs:__imp_CloseHandle
0x180076012  nop     dword ptr [rax+rax+00h]
0x180076017  mov     rcx, cs:qword_1800C1320; hObject
0x18007601e  test    rcx, rcx
0x180076021  jz      short loc_18007602F
0x180076023  call    cs:__imp_CloseHandle
0x18007602a  nop     dword ptr [rax+rax+00h]
0x18007602f  mov     rcx, cs:qword_1800C1470
0x180076036  test    rcx, rcx
0x180076039  jz      short loc_180076047
0x18007603b  call    cs:__imp_WmiCloseBlock
0x180076042  nop     dword ptr [rax+rax+00h]
0x180076047  mov     rbx, cs:lpMem
0x18007604e  test    rbx, rbx
0x180076051  jz      short loc_180076073
0x180076053  call    cs:__imp_GetProcessHeap
0x18007605a  nop     dword ptr [rax+rax+00h]
0x18007605f  mov     r8, rbx; lpMem
0x180076062  xor     edx, edx; dwFlags
0x180076064  mov     rcx, rax; hHeap
0x180076067  call    cs:__imp_HeapFree
0x18007606e  nop     dword ptr [rax+rax+00h]
0x180076073  mov     rcx, cs:qword_1800C1488; hObject
0x18007607a  test    rcx, rcx
0x18007607d  jz      short loc_18007608B
0x18007607f  call    cs:__imp_CloseHandle
0x180076086  nop     dword ptr [rax+rax+00h]
0x18007608b  lea     rcx, dword_1800C1490; struct _ITSRV_SYSTEM_SNAPSHOT *
0x180076092  call    ?ItSpCleanupSystemSnapshot@@YAXPEAU_ITSRV_SYSTEM_SNAPSHOT@@@Z; ItSpCleanupSystemSnapshot(_ITSRV_SYSTEM_SNAPSHOT *)
0x180076097  lea     rcx, dword_1800C14E8; struct _ITSRV_SYSTEM_SNAPSHOT *
0x18007609e  call    ?ItSpCleanupSystemSnapshot@@YAXPEAU_ITSRV_SYSTEM_SNAPSHOT@@@Z; ItSpCleanupSystemSnapshot(_ITSRV_SYSTEM_SNAPSHOT *)
0x1800760a3  lea     rsi, stru_1800C1310
0x1800760aa  mov     rbx, cs:stru_1800C1310.Flink
0x1800760b1  cmp     rbx, rsi
0x1800760b4  jz      short loc_180076108
0x1800760b6  dec     cs:dword_1800C1328
0x1800760bc  cmp     [rbx+8], rsi
0x1800760c0  jnz     loc_180076165
0x1800760c6  mov     rax, [rbx]
0x1800760c9  cmp     [rax+8], rbx
0x1800760cd  jnz     loc_180076165
0x1800760d3  mov     cs:stru_1800C1310.Flink, rax
0x1800760da  mov     rcx, rbx; struct _ITSRV_IDLE_TASK_CONTEXT *
0x1800760dd  mov     [rax+8], rsi
0x1800760e1  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x1800760e6  call    cs:__imp_GetProcessHeap
0x1800760ed  nop     dword ptr [rax+rax+00h]
0x1800760f2  mov     r8, rbx; lpMem
0x1800760f5  xor     edx, edx; dwFlags
0x1800760f7  mov     rcx, rax; hHeap
0x1800760fa  call    cs:__imp_HeapFree
0x180076101  nop     dword ptr [rax+rax+00h]
0x180076106  jmp     short loc_1800760AA
0x180076108  lea     rsi, stru_1800C1388
0x18007610f  mov     rbx, cs:stru_1800C1388.Flink
0x180076116  cmp     rbx, rsi
0x180076119  jz      short loc_18007616C
0x18007611b  dec     cs:dword_1800C1398
0x180076121  cmp     [rbx+8], rsi
0x180076125  jnz     short loc_180076165
0x180076127  mov     rax, [rbx]
0x18007612a  cmp     [rax+8], rbx
0x18007612e  jnz     short loc_180076165
0x180076130  mov     cs:stru_1800C1388.Flink, rax
0x180076137  mov     rcx, rbx; struct _ITSRV_IDLE_TASK_CONTEXT *
0x18007613a  mov     [rax+8], rsi
0x18007613e  call    ?ItSpCleanupIdleTask@@YAXPEAU_ITSRV_IDLE_TASK_CONTEXT@@@Z; ItSpCleanupIdleTask(_ITSRV_IDLE_TASK_CONTEXT *)
0x180076143  call    cs:__imp_GetProcessHeap
0x18007614a  nop     dword ptr [rax+rax+00h]
0x18007614f  mov     r8, rbx; lpMem
0x180076152  xor     edx, edx; dwFlags
0x180076154  mov     rcx, rax; hHeap
0x180076157  call    cs:__imp_HeapFree
0x18007615e  nop     dword ptr [rax+rax+00h]
0x180076163  jmp     short loc_18007610F
0x180076165  mov     ecx, 3
0x18007616a  int     29h; Win8: RtlFailFast(ecx)
0x18007616c  mov     rbx, cs:String1
0x180076173  test    rbx, rbx
0x180076176  jz      short loc_1800761AD
0x180076178  call    cs:__imp_GetProcessHeap
0x18007617f  nop     dword ptr [rax+rax+00h]
0x180076184  mov     r8, rbx; lpMem
0x180076187  xor     edx, edx; dwFlags
0x180076189  mov     rcx, rax; hHeap
0x18007618c  call    cs:__imp_HeapFree
0x180076193  nop     dword ptr [rax+rax+00h]
0x180076198  mov     cs:String1, 0
0x1800761a3  mov     cs:dword_1800C1464, 0
0x1800761ad  cmp     cs:BindingVector, 0
0x1800761b5  jz      short loc_1800761CA
0x1800761b7  lea     rcx, BindingVector; BindingVector
0x1800761be  call    cs:__imp_RpcBindingVectorFree
0x1800761c5  nop     dword ptr [rax+rax+00h]
0x1800761ca  mov     edx, 44663036h
0x1800761cf  lea     rcx, ?ItSrvGlobalContext@@3PAU_ITSRV_GLOBAL_CONTEXT@@A; _ITSRV_GLOBAL_CONTEXT near * ItSrvGlobalContext
0x1800761d6  call    ?ItSpUpdateStatus@@YAXPEAU_ITSRV_GLOBAL_CONTEXT@@W4_ITSRV_GLOBAL_CONTEXT_STATUS@@@Z; ItSpUpdateStatus(_ITSRV_GLOBAL_CONTEXT *,_ITSRV_GLOBAL_CONTEXT_STATUS)
0x1800761db  mov     rbx, [rsp+28h+arg_0]
0x1800761e0  add     rsp, 20h
0x1800761e4  pop     rsi
0x1800761e5  retn
```
