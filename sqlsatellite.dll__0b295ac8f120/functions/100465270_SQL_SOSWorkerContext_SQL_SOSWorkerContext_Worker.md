# SQL_SOSWorkerContext::SQL_SOSWorkerContext(Worker *)

- ea: `0x100465270`
- end: `0x10046543e`
- name: `??0SQL_SOSWorkerContext@@QEAA@PEAVWorker@@@Z`
- size: `462`
- prototype: `SQL_SOSWorkerContext *__fastcall(SQL_SOSWorkerContext *__hidden this, struct Worker *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100465cb0`
- `0x1004661f0`
- `0x100466700`

## callees

- `0x100418930`
- `0x1004189a0`
- `0x100465270`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004653df`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004653df`
- `sqldk!?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x1004652f1`
- `sqldk!?CreateThreadHandle@SystemThread@@AEAAXXZ` at `0x100465370`
- `sqldk!?CreateThreadHandle@SystemThread@@AEAAXXZ` at `0x100465370`
- `sqldk!?SilentBackoutHandler@@YAHHHHHPEAD@Z` at `0x10046530e`
- `sqldk!SystemThread_TlsIndex` at `0x1004652b3`
- `sqldk!SystemThread_TlsIndex` at `0x1004653a7`
- `sqldk!SystemThread_TlsIndex` at `0x1004653ef`
- `sqldk!SystemThread_TlsOffset` at `0x1004652bc`
- `sqldk!SystemThread_TlsOffset` at `0x1004653b0`
- `sqldk!SystemThread_TlsOffset` at `0x1004653f8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004652d5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004653c9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100465413`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004652d5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004653c9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100465413`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
SQL_SOSWorkerContext *__fastcall SQL_SOSWorkerContext::SQL_SOSWorkerContext(
        SQL_SOSWorkerContext *this,
        struct Worker *a2)
{
  SQL_SOSWorkerContext *v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rax
  _BYTE v14[16]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v15[24]; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v16[72]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v19; // [rsp+C0h] [rbp+18h]

  v3 = this;
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_WORD *)this + 8) = 0;
  *((_DWORD *)this + 5) = 0;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  v19 = *(_QWORD *)(v5 + 3208);
  v6 = v19;
  *(_QWORD *)(v5 + 3208) = ex_trans_cexcept_nodump;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v16, 0, 0, 0, SilentBackoutHandler, 0);
    *((_WORD *)v3 + 8) = *(_WORD *)(*((_QWORD *)a2 + 124) + 160LL);
    *((_DWORD *)v3 + 5) = *(_DWORD *)(*((_QWORD *)a2 + 76) + 3688LL);
    v7 = *((_QWORD *)a2 + 78);
    if ( v7 )
    {
      *(_DWORD *)v3 = *(_DWORD *)(v7 + 280);
      v8 = *(_QWORD *)(v7 + 296);
      if ( !v8 )
      {
        SystemThread::CreateThreadHandle((SystemThread *)v7);
        v8 = *(_QWORD *)(v7 + 296);
      }
      *((_QWORD *)v3 + 1) = v8;
    }
    ExcHandler::~ExcHandler((ExcHandler *)v16);
  }
  catch ( SQLError v15 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v14, (const struct SQLError *)v15);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v14);
    }
    catch ( ShortStackException )
    {
    }
    v3 = this;
    v6 = v19;
  }
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  if ( *(_DWORD *)(v10 + 556) )
    ExceptionPostCatchActions((struct Worker *)v10);
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  *(_QWORD *)(v12 + 3208) = v6;
  return v3;
}

```

## disassembly

```asm
0x100465270  mov     [rsp+arg_0], rcx
0x100465275  push    rsi
0x100465276  push    rdi
0x100465277  push    r14
0x100465279  sub     rsp, 90h
0x100465280  mov     [rsp+0A8h+var_78], 0FFFFFFFFFFFFFFFEh
0x100465289  mov     [rsp+0A8h+arg_8], rbx
0x100465291  mov     rsi, rdx
0x100465294  mov     rbx, rcx
0x100465297  xor     r14d, r14d
0x10046529a  mov     [rcx], r14d
0x10046529d  mov     [rcx+8], r14
0x1004652a1  mov     [rcx+10h], r14w
0x1004652a6  mov     [rcx+14h], r14d
0x1004652aa  mov     r8, gs:58h
0x1004652b3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004652ba  mov     edx, [rax]
0x1004652bc  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004652c3  mov     edi, [rax]
0x1004652c5  add     rdi, [r8+rdx*8]
0x1004652c9  mov     rcx, [rdi+100h]
0x1004652d0  test    rcx, rcx
0x1004652d3  jnz     short loc_1004652E2
0x1004652d5  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004652db  mov     rcx, [rdi+100h]
0x1004652e2  mov     rdi, [rcx+0C88h]
0x1004652e9  mov     [rsp+0A8h+arg_10], rdi
0x1004652f1  mov     rax, cs:__imp_?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept_nodump(uint,_EXCEPTION_POINTERS *)
0x1004652f8  mov     [rcx+0C88h], rax
0x1004652ff  mov     [rsp+0A8h+arg_18], rdi
0x100465307  xor     edx, edx; unsigned __int16
0x100465309  mov     [rsp+0A8h+var_80], r14; struct Worker *
0x10046530e  mov     rax, cs:__imp_?SilentBackoutHandler@@YAHHHHHPEAD@Z; SilentBackoutHandler(int,int,int,int,char *)
0x100465315  mov     [rsp+0A8h+var_88], rax; int (*)(int, int, int, int, char *)
0x10046531a  xor     r9d, r9d; unsigned __int8
0x10046531d  xor     r8d, r8d; unsigned __int8
0x100465320  lea     rcx, [rsp+0A8h+var_48]; this
0x100465325  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10046532a  nop
0x10046532b  mov     rax, [rsi+3E0h]
0x100465332  movzx   ecx, word ptr [rax+0A0h]
0x100465339  mov     [rbx+10h], cx
0x10046533d  mov     rax, [rsi+260h]
0x100465344  mov     ecx, [rax+0E68h]
0x10046534a  mov     [rbx+14h], ecx
0x10046534d  mov     rsi, [rsi+270h]
0x100465354  test    rsi, rsi
0x100465357  jz      short loc_100465381
0x100465359  mov     eax, [rsi+118h]
0x10046535f  mov     [rbx], eax
0x100465361  mov     rax, [rsi+128h]
0x100465368  test    rax, rax
0x10046536b  jnz     short loc_10046537D
0x10046536d  mov     rcx, rsi
0x100465370  call    cs:__imp_?CreateThreadHandle@SystemThread@@AEAAXXZ; SystemThread::CreateThreadHandle(void)
0x100465376  mov     rax, [rsi+128h]
0x10046537d  mov     [rbx+8], rax
0x100465381  lea     rcx, [rsp+0A8h+var_48]; this
0x100465386  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10046538b  nop
0x10046538c  jmp     short loc_10046539E
0x10046538e  mov     rbx, [rsp+0A8h+arg_0]
0x100465396  mov     rdi, [rsp+0A8h+arg_10]
0x10046539e  mov     rdx, gs:58h
0x1004653a7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004653ae  mov     ecx, [rax]
0x1004653b0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004653b7  mov     esi, [rax]
0x1004653b9  add     rsi, [rdx+rcx*8]
0x1004653bd  mov     rcx, [rsi+100h]
0x1004653c4  test    rcx, rcx
0x1004653c7  jnz     short loc_1004653D6
0x1004653c9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004653cf  mov     rcx, [rsi+100h]
0x1004653d6  cmp     dword ptr [rcx+22Ch], 0
0x1004653dd  jz      short loc_1004653E6
0x1004653df  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x1004653e5  nop
0x1004653e6  mov     rdx, gs:58h
0x1004653ef  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004653f6  mov     ecx, [rax]
0x1004653f8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004653ff  mov     esi, [rax]
0x100465401  add     rsi, [rdx+rcx*8]
0x100465405  mov     rax, [rsi+100h]
0x10046540c  test    rax, rax
0x10046540f  jnz     short loc_100465420
0x100465411  xor     ecx, ecx
0x100465413  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100465419  mov     rax, [rsi+100h]
0x100465420  mov     [rax+0C88h], rdi
0x100465427  mov     rax, rbx
0x10046542a  mov     rbx, [rsp+0A8h+arg_8]
0x100465432  add     rsp, 90h
0x100465439  pop     r14
0x10046543b  pop     rdi
0x10046543c  pop     rsi
0x10046543d  retn
```
