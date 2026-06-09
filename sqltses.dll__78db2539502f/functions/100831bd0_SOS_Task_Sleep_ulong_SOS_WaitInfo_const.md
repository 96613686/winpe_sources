# SOS_Task::Sleep(ulong,SOS_WaitInfo const *)

- ea: `0x100831bd0`
- end: `0x100831d3b`
- name: `?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x100830030`

## callees

- `0x100831bd0`

## import_xrefs

- `sqldk!?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z` at `0x100831d02`
- `sqldk!?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z` at `0x100831d02`
- `sqldk!?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z` at `0x100831cf5`
- `sqldk!?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z` at `0x100831cf5`
- `sqldk!?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z` at `0x100831ce9`
- `sqldk!?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z` at `0x100831ce9`
- `sqldk!SystemThread_TlsIndex` at `0x100831c02`
- `sqldk!SystemThread_TlsIndex` at `0x100831c83`
- `sqldk!SystemThread_TlsOffset` at `0x100831c0c`
- `sqldk!SystemThread_TlsOffset` at `0x100831c8c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100831c27`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100831ca7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100831c27`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100831ca7`

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
0x100831bd0  push    r14
0x100831bd2  sub     rsp, 40h
0x100831bd6  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x100831bdf  mov     [rsp+48h+arg_0], rbx
0x100831be4  mov     [rsp+48h+arg_8], rbp
0x100831be9  mov     [rsp+48h+arg_10], rsi
0x100831bee  mov     [rsp+48h+arg_18], rdi
0x100831bf3  mov     rbp, rdx
0x100831bf6  mov     r14d, ecx
0x100831bf9  mov     r9, gs:58h
0x100831c02  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100831c09  mov     r8d, [rax]
0x100831c0c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100831c13  mov     ebx, [rax]
0x100831c15  add     rbx, [r9+r8*8]
0x100831c19  mov     rsi, [rbx+100h]
0x100831c20  test    rsi, rsi
0x100831c23  jnz     short loc_100831C34
0x100831c25  xor     ecx, ecx
0x100831c27  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100831c2d  mov     rsi, [rbx+100h]
0x100831c34  mov     rcx, [rsi+258h]
0x100831c3b  test    rcx, rcx
0x100831c3e  jz      short loc_100831C7A
0x100831c40  cmp     qword ptr [rcx+98h], 0
0x100831c48  jz      short loc_100831C7A
0x100831c4a  mov     eax, [rcx+0BCh]
0x100831c50  test    al, 4
0x100831c52  jz      short loc_100831C7A
0x100831c54  mov     rax, [rcx+98h]
0x100831c5b  test    byte ptr [rax+268h], 1
0x100831c62  jnz     short loc_100831C7A
0x100831c64  test    dword ptr [rax+320h], 180h
0x100831c6e  jnz     short loc_100831C7A
0x100831c70  mov     eax, 2
0x100831c75  jmp     loc_100831D20
0x100831c7a  mov     rdx, gs:58h
0x100831c83  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100831c8a  mov     ecx, [rax]
0x100831c8c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100831c93  mov     ebx, [rax]
0x100831c95  add     rbx, [rdx+rcx*8]
0x100831c99  mov     rdi, [rbx+100h]
0x100831ca0  test    rdi, rdi
0x100831ca3  jnz     short loc_100831CB4
0x100831ca5  xor     ecx, ecx
0x100831ca7  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100831cad  mov     rdi, [rbx+100h]
0x100831cb4  mov     [rsp+48h+var_18], rdi
0x100831cb9  mov     ebx, [rdi+320h]
0x100831cbf  shr     ebx, 0Bh
0x100831cc2  and     ebx, 1
0x100831cc5  mov     [rsp+48h+var_20], ebx
0x100831cc9  jz      short loc_100831CE6
0x100831ccb  mov     rcx, [rdi+260h]
0x100831cd2  mov     rax, [rcx]
0x100831cd5  mov     rdx, rdi
0x100831cd8  call    qword ptr [rax+20h]
0x100831cdb  xor     ebx, ebx
0x100831cdd  test    eax, eax
0x100831cdf  setz    bl
0x100831ce2  mov     [rsp+48h+var_20], ebx
0x100831ce6  mov     rcx, rbp
0x100831ce9  call    cs:__imp_?PreWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@@Z; SOS_Task::PreWait(SOS_WaitInfo const *)
0x100831cef  mov     edx, r14d
0x100831cf2  mov     rcx, rsi
0x100831cf5  call    cs:__imp_?Suspend@SOS_Scheduler@@SA?AW4SOS_RESULT@@PEAVWorker@@K@Z; SOS_Scheduler::Suspend(Worker *,ulong)
0x100831cfb  mov     esi, eax
0x100831cfd  mov     edx, eax
0x100831cff  mov     rcx, rbp
0x100831d02  call    cs:__imp_?PostWait@SOS_Task@@SAXPEBVSOS_WaitInfo@@W4SOS_RESULT@@@Z; SOS_Task::PostWait(SOS_WaitInfo const *,SOS_RESULT)
0x100831d08  nop
0x100831d09  test    ebx, ebx
0x100831d0b  jz      short loc_100831D1E
0x100831d0d  mov     rcx, [rdi+260h]
0x100831d14  mov     r8, [rcx]
0x100831d17  mov     rdx, rdi
0x100831d1a  call    qword ptr [r8+18h]
0x100831d1e  mov     eax, esi
0x100831d20  mov     rbx, [rsp+48h+arg_0]
0x100831d25  mov     rbp, [rsp+48h+arg_8]
0x100831d2a  mov     rsi, [rsp+48h+arg_10]
0x100831d2f  mov     rdi, [rsp+48h+arg_18]
0x100831d34  add     rsp, 40h
0x100831d38  pop     r14
0x100831d3a  retn
```
