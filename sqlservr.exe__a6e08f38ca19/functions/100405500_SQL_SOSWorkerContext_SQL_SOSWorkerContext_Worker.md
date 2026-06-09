# SQL_SOSWorkerContext::SQL_SOSWorkerContext(Worker *)

- ea: `0x100405500`
- end: `0x1004056ce`
- name: `??0SQL_SOSWorkerContext@@QEAA@PEAVWorker@@@Z`
- size: `462`
- prototype: `SQL_SOSWorkerContext *__fastcall(SQL_SOSWorkerContext *__hidden this, struct Worker *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100406350`
- `0x100406750`
- `0x100406c30`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x100405500`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405565`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405659`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004056a3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405565`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405659`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004056a3`
- `sqldk!SystemThread_TlsOffset` at `0x10040554c`
- `sqldk!SystemThread_TlsOffset` at `0x100405640`
- `sqldk!SystemThread_TlsOffset` at `0x100405688`
- `sqldk!SystemThread_TlsIndex` at `0x100405543`
- `sqldk!SystemThread_TlsIndex` at `0x100405637`
- `sqldk!SystemThread_TlsIndex` at `0x10040567f`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10040566f`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10040566f`
- `sqldk!?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x100405581`
- `sqldk!?CreateThreadHandle@SystemThread@@AEAAXXZ` at `0x100405600`
- `sqldk!?CreateThreadHandle@SystemThread@@AEAAXXZ` at `0x100405600`
- `sqldk!?SilentBackoutHandler@@YAHHHHHPEAD@Z` at `0x10040559e`

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
0x100405500  mov     [rsp+arg_0], rcx
0x100405505  push    rsi
0x100405506  push    rdi
0x100405507  push    r14
0x100405509  sub     rsp, 90h
0x100405510  mov     [rsp+0A8h+var_78], 0FFFFFFFFFFFFFFFEh
0x100405519  mov     [rsp+0A8h+arg_8], rbx
0x100405521  mov     rsi, rdx
0x100405524  mov     rbx, rcx
0x100405527  xor     r14d, r14d
0x10040552a  mov     [rcx], r14d
0x10040552d  mov     [rcx+8], r14
0x100405531  mov     [rcx+10h], r14w
0x100405536  mov     [rcx+14h], r14d
0x10040553a  mov     r8, gs:58h
0x100405543  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040554a  mov     edx, [rax]
0x10040554c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405553  mov     edi, [rax]
0x100405555  add     rdi, [r8+rdx*8]
0x100405559  mov     rcx, [rdi+100h]
0x100405560  test    rcx, rcx
0x100405563  jnz     short loc_100405572
0x100405565  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040556b  mov     rcx, [rdi+100h]
0x100405572  mov     rdi, [rcx+0C88h]
0x100405579  mov     [rsp+0A8h+arg_10], rdi
0x100405581  mov     rax, cs:__imp_?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept_nodump(uint,_EXCEPTION_POINTERS *)
0x100405588  mov     [rcx+0C88h], rax
0x10040558f  mov     [rsp+0A8h+arg_18], rdi
0x100405597  xor     edx, edx; unsigned __int16
0x100405599  mov     [rsp+0A8h+var_80], r14; struct Worker *
0x10040559e  mov     rax, cs:__imp_?SilentBackoutHandler@@YAHHHHHPEAD@Z; SilentBackoutHandler(int,int,int,int,char *)
0x1004055a5  mov     [rsp+0A8h+var_88], rax; int (*)(int, int, int, int, char *)
0x1004055aa  xor     r9d, r9d; unsigned __int8
0x1004055ad  xor     r8d, r8d; unsigned __int8
0x1004055b0  lea     rcx, [rsp+0A8h+var_48]; this
0x1004055b5  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x1004055ba  nop
0x1004055bb  mov     rax, [rsi+3E0h]
0x1004055c2  movzx   ecx, word ptr [rax+0A0h]
0x1004055c9  mov     [rbx+10h], cx
0x1004055cd  mov     rax, [rsi+260h]
0x1004055d4  mov     ecx, [rax+0E68h]
0x1004055da  mov     [rbx+14h], ecx
0x1004055dd  mov     rsi, [rsi+270h]
0x1004055e4  test    rsi, rsi
0x1004055e7  jz      short loc_100405611
0x1004055e9  mov     eax, [rsi+118h]
0x1004055ef  mov     [rbx], eax
0x1004055f1  mov     rax, [rsi+128h]
0x1004055f8  test    rax, rax
0x1004055fb  jnz     short loc_10040560D
0x1004055fd  mov     rcx, rsi
0x100405600  call    cs:__imp_?CreateThreadHandle@SystemThread@@AEAAXXZ; SystemThread::CreateThreadHandle(void)
0x100405606  mov     rax, [rsi+128h]
0x10040560d  mov     [rbx+8], rax
0x100405611  lea     rcx, [rsp+0A8h+var_48]; this
0x100405616  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10040561b  nop
0x10040561c  jmp     short loc_10040562E
0x10040561e  mov     rbx, [rsp+0A8h+arg_0]
0x100405626  mov     rdi, [rsp+0A8h+arg_10]
0x10040562e  mov     rdx, gs:58h
0x100405637  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040563e  mov     ecx, [rax]
0x100405640  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405647  mov     esi, [rax]
0x100405649  add     rsi, [rdx+rcx*8]
0x10040564d  mov     rcx, [rsi+100h]
0x100405654  test    rcx, rcx
0x100405657  jnz     short loc_100405666
0x100405659  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040565f  mov     rcx, [rsi+100h]
0x100405666  cmp     dword ptr [rcx+22Ch], 0
0x10040566d  jz      short loc_100405676
0x10040566f  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x100405675  nop
0x100405676  mov     rdx, gs:58h
0x10040567f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100405686  mov     ecx, [rax]
0x100405688  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040568f  mov     esi, [rax]
0x100405691  add     rsi, [rdx+rcx*8]
0x100405695  mov     rax, [rsi+100h]
0x10040569c  test    rax, rax
0x10040569f  jnz     short loc_1004056B0
0x1004056a1  xor     ecx, ecx
0x1004056a3  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004056a9  mov     rax, [rsi+100h]
0x1004056b0  mov     [rax+0C88h], rdi
0x1004056b7  mov     rax, rbx
0x1004056ba  mov     rbx, [rsp+0A8h+arg_8]
0x1004056c2  add     rsp, 90h
0x1004056c9  pop     r14
0x1004056cb  pop     rdi
0x1004056cc  pop     rsi
0x1004056cd  retn
```
