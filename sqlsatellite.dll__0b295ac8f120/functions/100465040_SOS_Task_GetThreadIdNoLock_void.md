# SOS_Task::GetThreadIdNoLock(void)

- ea: `0x100465040`
- end: `0x1004651e2`
- name: `?GetThreadIdNoLock@SOS_Task@@AEAAKXZ`
- size: `418`
- prototype: `unsigned int __fastcall(SOS_Task *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x100464e90`

## callees

- `0x100418930`
- `0x1004189a0`
- `0x100465040`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100465172`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100465172`
- `sqldk!?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x1004650ca`
- `sqldk!?SilentBackoutHandler@@YAHHHHHPEAD@Z` at `0x1004650e7`
- `sqldk!SystemThread_TlsIndex` at `0x10046508c`
- `sqldk!SystemThread_TlsIndex` at `0x10046513a`
- `sqldk!SystemThread_TlsIndex` at `0x100465182`
- `sqldk!SystemThread_TlsOffset` at `0x100465095`
- `sqldk!SystemThread_TlsOffset` at `0x100465143`
- `sqldk!SystemThread_TlsOffset` at `0x10046518b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004650ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10046515c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004651a6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004650ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10046515c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004651a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SOS_Task::GetThreadIdNoLock(SOS_Task *this)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rax
  unsigned int v11; // [rsp+30h] [rbp-68h]
  _BYTE v12[16]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v13[24]; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v14[48]; // [rsp+68h] [rbp-30h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+8h]

  v2 = *((_QWORD *)this + 19);
  if ( !v2 || !*(_QWORD *)(v2 + 624) )
    return 0;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v15 = *(_QWORD *)(v4 + 3208);
  v5 = v15;
  *(_QWORD *)(v4 + 3208) = ex_trans_cexcept_nodump;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v14, 0, 0, 0, SilentBackoutHandler, 0);
    v11 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 19) + 624LL) + 280LL);
    ExcHandler::~ExcHandler((ExcHandler *)v14);
  }
  catch ( SQLError v13 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v12, (const struct SQLError *)v13);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v12);
    }
    catch ( ShortStackException )
    {
    }
    v5 = v15;
  }
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  if ( *(_DWORD *)(v7 + 556) )
    ExceptionPostCatchActions((struct Worker *)v7);
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  *(_QWORD *)(v9 + 3208) = v5;
  return v11;
}

```

## disassembly

```asm
0x100465040  push    rdi
0x100465042  sub     rsp, 90h
0x100465049  mov     [rsp+98h+var_60], 0FFFFFFFFFFFFFFFEh
0x100465052  mov     [rsp+98h+arg_10], rbx
0x10046505a  mov     rdi, rcx
0x10046505d  mov     [rsp+98h+var_68], 0
0x100465065  mov     rax, [rcx+98h]
0x10046506c  test    rax, rax
0x10046506f  jz      loc_1004651CF
0x100465075  cmp     qword ptr [rax+270h], 0
0x10046507d  jz      loc_1004651CF
0x100465083  mov     rdx, gs:58h
0x10046508c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100465093  mov     ecx, [rax]
0x100465095  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10046509c  mov     ebx, [rax]
0x10046509e  add     rbx, [rdx+rcx*8]
0x1004650a2  mov     rcx, [rbx+100h]
0x1004650a9  test    rcx, rcx
0x1004650ac  jnz     short loc_1004650BB
0x1004650ae  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004650b4  mov     rcx, [rbx+100h]
0x1004650bb  mov     rbx, [rcx+0C88h]
0x1004650c2  mov     [rsp+98h+arg_0], rbx
0x1004650ca  mov     rax, cs:__imp_?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept_nodump(uint,_EXCEPTION_POINTERS *)
0x1004650d1  mov     [rcx+0C88h], rax
0x1004650d8  mov     [rsp+98h+arg_8], rbx
0x1004650e0  xor     edx, edx; unsigned __int16
0x1004650e2  mov     [rsp+98h+var_70], rdx; struct Worker *
0x1004650e7  mov     rax, cs:__imp_?SilentBackoutHandler@@YAHHHHHPEAD@Z; SilentBackoutHandler(int,int,int,int,char *)
0x1004650ee  mov     [rsp+98h+var_78], rax; int (*)(int, int, int, int, char *)
0x1004650f3  xor     r9d, r9d; unsigned __int8
0x1004650f6  xor     r8d, r8d; unsigned __int8
0x1004650f9  lea     rcx, [rsp+98h+var_30]; this
0x1004650fe  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100465103  nop
0x100465104  mov     rax, [rdi+98h]
0x10046510b  mov     rcx, [rax+270h]
0x100465112  mov     eax, [rcx+118h]
0x100465118  mov     [rsp+98h+var_68], eax
0x10046511c  lea     rcx, [rsp+98h+var_30]; this
0x100465121  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x100465126  nop
0x100465127  jmp     short loc_100465131
0x100465129  mov     rbx, [rsp+98h+arg_0]
0x100465131  mov     rdx, gs:58h
0x10046513a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100465141  mov     ecx, [rax]
0x100465143  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10046514a  mov     edi, [rax]
0x10046514c  add     rdi, [rdx+rcx*8]
0x100465150  mov     rcx, [rdi+100h]
0x100465157  test    rcx, rcx
0x10046515a  jnz     short loc_100465169
0x10046515c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100465162  mov     rcx, [rdi+100h]
0x100465169  cmp     dword ptr [rcx+22Ch], 0
0x100465170  jz      short loc_100465179
0x100465172  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x100465178  nop
0x100465179  mov     rdx, gs:58h
0x100465182  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100465189  mov     ecx, [rax]
0x10046518b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100465192  mov     edi, [rax]
0x100465194  add     rdi, [rdx+rcx*8]
0x100465198  mov     rax, [rdi+100h]
0x10046519f  test    rax, rax
0x1004651a2  jnz     short loc_1004651B3
0x1004651a4  xor     ecx, ecx
0x1004651a6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004651ac  mov     rax, [rdi+100h]
0x1004651b3  mov     [rax+0C88h], rbx
0x1004651ba  mov     eax, [rsp+98h+var_68]
0x1004651be  mov     rbx, [rsp+98h+arg_10]
0x1004651c6  add     rsp, 90h
0x1004651cd  pop     rdi
0x1004651ce  retn
0x1004651cf  xor     eax, eax
0x1004651d1  mov     rbx, [rsp+98h+arg_10]
0x1004651d9  add     rsp, 90h
0x1004651e0  pop     rdi
0x1004651e1  retn
```
