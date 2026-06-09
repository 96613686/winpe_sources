# SOS_Task::GetThreadIdNoLock(void)

- ea: `0x1004052b0`
- end: `0x100405452`
- name: `?GetThreadIdNoLock@SOS_Task@@AEAAKXZ`
- size: `418`
- prototype: `unsigned int __fastcall(SOS_Task *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x100405100`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x1004052b0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040531e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004053cc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405416`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040531e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004053cc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405416`
- `sqldk!SystemThread_TlsOffset` at `0x100405305`
- `sqldk!SystemThread_TlsOffset` at `0x1004053b3`
- `sqldk!SystemThread_TlsOffset` at `0x1004053fb`
- `sqldk!SystemThread_TlsIndex` at `0x1004052fc`
- `sqldk!SystemThread_TlsIndex` at `0x1004053aa`
- `sqldk!SystemThread_TlsIndex` at `0x1004053f2`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004053e2`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004053e2`
- `sqldk!?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z` at `0x10040533a`
- `sqldk!?SilentBackoutHandler@@YAHHHHHPEAD@Z` at `0x100405357`

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
0x1004052b0  push    rdi
0x1004052b2  sub     rsp, 90h
0x1004052b9  mov     [rsp+98h+var_60], 0FFFFFFFFFFFFFFFEh
0x1004052c2  mov     [rsp+98h+arg_10], rbx
0x1004052ca  mov     rdi, rcx
0x1004052cd  mov     [rsp+98h+var_68], 0
0x1004052d5  mov     rax, [rcx+98h]
0x1004052dc  test    rax, rax
0x1004052df  jz      loc_10040543F
0x1004052e5  cmp     qword ptr [rax+270h], 0
0x1004052ed  jz      loc_10040543F
0x1004052f3  mov     rdx, gs:58h
0x1004052fc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100405303  mov     ecx, [rax]
0x100405305  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040530c  mov     ebx, [rax]
0x10040530e  add     rbx, [rdx+rcx*8]
0x100405312  mov     rcx, [rbx+100h]
0x100405319  test    rcx, rcx
0x10040531c  jnz     short loc_10040532B
0x10040531e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100405324  mov     rcx, [rbx+100h]
0x10040532b  mov     rbx, [rcx+0C88h]
0x100405332  mov     [rsp+98h+arg_0], rbx
0x10040533a  mov     rax, cs:__imp_?ex_trans_cexcept_nodump@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; ex_trans_cexcept_nodump(uint,_EXCEPTION_POINTERS *)
0x100405341  mov     [rcx+0C88h], rax
0x100405348  mov     [rsp+98h+arg_8], rbx
0x100405350  xor     edx, edx; unsigned __int16
0x100405352  mov     [rsp+98h+var_70], rdx; struct Worker *
0x100405357  mov     rax, cs:__imp_?SilentBackoutHandler@@YAHHHHHPEAD@Z; SilentBackoutHandler(int,int,int,int,char *)
0x10040535e  mov     [rsp+98h+var_78], rax; int (*)(int, int, int, int, char *)
0x100405363  xor     r9d, r9d; unsigned __int8
0x100405366  xor     r8d, r8d; unsigned __int8
0x100405369  lea     rcx, [rsp+98h+var_30]; this
0x10040536e  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100405373  nop
0x100405374  mov     rax, [rdi+98h]
0x10040537b  mov     rcx, [rax+270h]
0x100405382  mov     eax, [rcx+118h]
0x100405388  mov     [rsp+98h+var_68], eax
0x10040538c  lea     rcx, [rsp+98h+var_30]; this
0x100405391  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x100405396  nop
0x100405397  jmp     short loc_1004053A1
0x100405399  mov     rbx, [rsp+98h+arg_0]
0x1004053a1  mov     rdx, gs:58h
0x1004053aa  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004053b1  mov     ecx, [rax]
0x1004053b3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004053ba  mov     edi, [rax]
0x1004053bc  add     rdi, [rdx+rcx*8]
0x1004053c0  mov     rcx, [rdi+100h]
0x1004053c7  test    rcx, rcx
0x1004053ca  jnz     short loc_1004053D9
0x1004053cc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004053d2  mov     rcx, [rdi+100h]
0x1004053d9  cmp     dword ptr [rcx+22Ch], 0
0x1004053e0  jz      short loc_1004053E9
0x1004053e2  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x1004053e8  nop
0x1004053e9  mov     rdx, gs:58h
0x1004053f2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004053f9  mov     ecx, [rax]
0x1004053fb  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100405402  mov     edi, [rax]
0x100405404  add     rdi, [rdx+rcx*8]
0x100405408  mov     rax, [rdi+100h]
0x10040540f  test    rax, rax
0x100405412  jnz     short loc_100405423
0x100405414  xor     ecx, ecx
0x100405416  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040541c  mov     rax, [rdi+100h]
0x100405423  mov     [rax+0C88h], rbx
0x10040542a  mov     eax, [rsp+98h+var_68]
0x10040542e  mov     rbx, [rsp+98h+arg_10]
0x100405436  add     rsp, 90h
0x10040543d  pop     rdi
0x10040543e  retn
0x10040543f  xor     eax, eax
0x100405441  mov     rbx, [rsp+98h+arg_10]
0x100405449  add     rsp, 90h
0x100405450  pop     rdi
0x100405451  retn
```
