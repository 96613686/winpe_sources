# SOS_Task::Sleep(ulong,SOS_WaitInfo const *)

- ea: `0x1004095e0`
- end: `0x10040974b`
- name: `?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z`
- size: `363`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x10040c5b0`
- `0x1004119c0`
- `0x100439f60`
- `0x10043f1c0`
- `0x10044f190`
- `0x100455b90`

## callees

- `0x1004095e0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100409637`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004096b7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100409637`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004096b7`
- `sqldk!SystemThread_TlsOffset` at `0x10040961c`
- `sqldk!SystemThread_TlsOffset` at `0x10040969c`
- `sqldk!SystemThread_TlsIndex` at `0x100409612`
- `sqldk!SystemThread_TlsIndex` at `0x100409693`
- `sqldk!?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z` at `0x100409712`
- `sqldk!?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z` at `0x100409712`
- `sqldk!?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z` at `0x1004096f9`
- `sqldk!?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z` at `0x1004096f9`
- `sqldk!?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z` at `0x100409705`
- `sqldk!?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z` at `0x100409705`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SOS_Task::Sleep(unsigned int a1, const struct SOS_WaitInfo *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v9; // rbx
  __int64 v10; // rdi
  int v11; // ebx
  __int64 v12; // rsi

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  v6 = *(_QWORD *)(v5 + 600);
  if ( v6 )
  {
    if ( *(_QWORD *)(v6 + 152) )
    {
      if ( (*(_DWORD *)(v6 + 188) & 4) != 0 )
      {
        v7 = *(_QWORD *)(v6 + 152);
        if ( (*(_BYTE *)(v7 + 616) & 1) == 0 && (*(_DWORD *)(v7 + 800) & 0x180) == 0 )
          return 2;
      }
    }
  }
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v11 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
  if ( v11 )
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v10 + 608) + 32LL))(*(_QWORD *)(v10 + 608), v10) == 0;
  SOS_Task::PreWait(a2);
  v12 = (unsigned int)SOS_Scheduler::Suspend(v5, a1);
  SOS_Task::PostWait(a2, v12);
  if ( v11 )
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v10 + 608) + 24LL))(*(_QWORD *)(v10 + 608), v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1004095e0  push    r14
0x1004095e2  sub     rsp, 40h
0x1004095e6  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1004095ef  mov     [rsp+48h+arg_0], rbx
0x1004095f4  mov     [rsp+48h+arg_8], rbp
0x1004095f9  mov     [rsp+48h+arg_10], rsi
0x1004095fe  mov     [rsp+48h+arg_18], rdi
0x100409603  mov     rbp, rdx
0x100409606  mov     r14d, ecx
0x100409609  mov     r9, gs:58h
0x100409612  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100409619  mov     r8d, [rax]
0x10040961c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100409623  mov     ebx, [rax]
0x100409625  add     rbx, [r9+r8*8]
0x100409629  mov     rsi, [rbx+100h]
0x100409630  test    rsi, rsi
0x100409633  jnz     short loc_100409644
0x100409635  xor     ecx, ecx
0x100409637  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040963d  mov     rsi, [rbx+100h]
0x100409644  mov     rcx, [rsi+258h]
0x10040964b  test    rcx, rcx
0x10040964e  jz      short loc_10040968A
0x100409650  cmp     qword ptr [rcx+98h], 0
0x100409658  jz      short loc_10040968A
0x10040965a  mov     eax, [rcx+0BCh]
0x100409660  test    al, 4
0x100409662  jz      short loc_10040968A
0x100409664  mov     rax, [rcx+98h]
0x10040966b  test    byte ptr [rax+268h], 1
0x100409672  jnz     short loc_10040968A
0x100409674  test    dword ptr [rax+320h], 180h
0x10040967e  jnz     short loc_10040968A
0x100409680  mov     eax, 2
0x100409685  jmp     loc_100409730
0x10040968a  mov     rdx, gs:58h
0x100409693  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040969a  mov     ecx, [rax]
0x10040969c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004096a3  mov     ebx, [rax]
0x1004096a5  add     rbx, [rdx+rcx*8]
0x1004096a9  mov     rdi, [rbx+100h]
0x1004096b0  test    rdi, rdi
0x1004096b3  jnz     short loc_1004096C4
0x1004096b5  xor     ecx, ecx
0x1004096b7  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004096bd  mov     rdi, [rbx+100h]
0x1004096c4  mov     [rsp+48h+var_18], rdi
0x1004096c9  mov     ebx, [rdi+320h]
0x1004096cf  shr     ebx, 0Bh
0x1004096d2  and     ebx, 1
0x1004096d5  mov     [rsp+48h+var_20], ebx
0x1004096d9  jz      short loc_1004096F6
0x1004096db  mov     rcx, [rdi+260h]
0x1004096e2  mov     rax, [rcx]
0x1004096e5  mov     rdx, rdi
0x1004096e8  call    qword ptr [rax+20h]
0x1004096eb  xor     ebx, ebx
0x1004096ed  test    eax, eax
0x1004096ef  setz    bl
0x1004096f2  mov     [rsp+48h+var_20], ebx
0x1004096f6  mov     rcx, rbp
0x1004096f9  call    cs:__imp_?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z; SOS_Task::PreWait(SOS_WaitInfo const *)
0x1004096ff  mov     edx, r14d
0x100409702  mov     rcx, rsi
0x100409705  call    cs:__imp_?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z; SOS_Scheduler::Suspend(Worker *,ulong)
0x10040970b  mov     esi, eax
0x10040970d  mov     edx, eax
0x10040970f  mov     rcx, rbp
0x100409712  call    cs:__imp_?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z; SOS_Task::PostWait(SOS_WaitInfo const *,SOS_RESULT)
0x100409718  nop
0x100409719  test    ebx, ebx
0x10040971b  jz      short loc_10040972E
0x10040971d  mov     rcx, [rdi+260h]
0x100409724  mov     r8, [rcx]
0x100409727  mov     rdx, rdi
0x10040972a  call    qword ptr [r8+18h]
0x10040972e  mov     eax, esi
0x100409730  mov     rbx, [rsp+48h+arg_0]
0x100409735  mov     rbp, [rsp+48h+arg_8]
0x10040973a  mov     rsi, [rsp+48h+arg_10]
0x10040973f  mov     rdi, [rsp+48h+arg_18]
0x100409744  add     rsp, 40h
0x100409748  pop     r14
0x10040974a  retn
```
