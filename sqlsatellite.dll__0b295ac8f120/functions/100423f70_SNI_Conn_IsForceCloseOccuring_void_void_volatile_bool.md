# SNI_Conn::IsForceCloseOccuring(void *,void * volatile *,bool &)

- ea: `0x100423f70`
- end: `0x100424108`
- name: `?IsForceCloseOccuring@SNI_Conn@@QEAA_NPEAXPECREAXAEA_N@Z`
- size: `408`
- prototype: `bool __fastcall(SNI_Conn *__hidden this, void *, void *volatile *, bool *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100425c40`
- `0x100425ef0`

## callees

- `0x100423f70`

## import_xrefs

- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x100424035`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x1004240dc`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x100424035`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x1004240dc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100424020`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004240c7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100424020`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004240c7`
- `sqldk!SystemThread_TlsIndex` at `0x100423fcb`
- `sqldk!SystemThread_TlsIndex` at `0x100424072`
- `sqldk!SystemThread_TlsOffset` at `0x100423fd4`
- `sqldk!SystemThread_TlsOffset` at `0x10042407b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100423fef`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424096`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100423fef`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100424096`

## string_xrefs

- `0x10042400d`: `Sql\DkTemp\sos\include\sossync.inl`
- `0x1004240b4`: `Sql\DkTemp\sos\include\sossync.inl`

## pseudocode

```c
char __fastcall SNI_Conn::IsForceCloseOccuring(SNI_Conn *this, void *a2, void *volatile *a3, bool *a4)
{
  char *v7; // rbp
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v11; // rsi
  __int64 v12; // rax
  int v13; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-40h]
  __int64 v15; // [rsp+40h] [rbp-38h]
  __int64 v16; // [rsp+48h] [rbp-30h]
  __int64 v17; // [rsp+50h] [rbp-28h]

  *a4 = 0;
  if ( !*((_BYTE *)this + 12904) )
    return 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v7 = (char *)this + 12912;
  v13 = 4194679;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  if ( *((_QWORD *)v7 + 3) == v9 )
    utassert_fail(1u, "m_pExclusiveOwner != pWorker", "Sql\\DkTemp\\sos\\include\\sossync.inl", 1833, 0);
  if ( (unsigned int)SOS_RWLock::GetLongWait(v7, 1, 0, &v13) )
  {
    *a3 = a2;
    v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v12 = *(_QWORD *)(v11 + 256);
    if ( !v12 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v12 = *(_QWORD *)(v11 + 256);
    }
    if ( *((_QWORD *)v7 + 3) == v12 )
      utassert_fail(1u, "m_pExclusiveOwner != pWorker", "Sql\\DkTemp\\sos\\include\\sossync.inl", 1833, 0);
    if ( (unsigned int)SOS_RWLock::GetLongWait(v7, 1, 0, &v13) )
      return 1;
    *a4 = 1;
    if ( !_InterlockedExchange64((volatile __int64 *)a3, 0) )
      return 1;
  }
  else
  {
    *a4 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x100423f70  mov     rax, rsp
0x100423f73  push    rdi
0x100423f74  push    r14
0x100423f76  push    r15
0x100423f78  sub     rsp, 60h
0x100423f7c  mov     byte ptr [r9], 0
0x100423f80  mov     rdi, r9
0x100423f83  cmp     byte ptr [rcx+3268h], 0
0x100423f8a  mov     r14, r8
0x100423f8d  mov     r15, rdx
0x100423f90  jz      loc_1004240FC
0x100423f96  mov     [rax+8], rbx
0x100423f9a  xor     ebx, ebx
0x100423f9c  mov     [rax-40h], rbx
0x100423fa0  mov     [rax-30h], rbx
0x100423fa4  mov     [rax-38h], rbx
0x100423fa8  mov     [rax-28h], rbx
0x100423fac  mov     [rax+10h], rbp
0x100423fb0  lea     rbp, [rcx+3270h]
0x100423fb7  mov     dword ptr [rax-48h], 400177h
0x100423fbe  mov     rdx, gs:58h
0x100423fc7  mov     [rax+18h], rsi
0x100423fcb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100423fd2  mov     ecx, [rax]
0x100423fd4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100423fdb  mov     esi, [rax]
0x100423fdd  add     rsi, [rdx+rcx*8]
0x100423fe1  mov     rax, [rsi+100h]
0x100423fe8  test    rax, rax
0x100423feb  jnz     short loc_100423FFC
0x100423fed  xor     ecx, ecx
0x100423fef  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100423ff5  mov     rax, [rsi+100h]
0x100423ffc  cmp     [rbp+18h], rax
0x100424000  jnz     short loc_100424026
0x100424002  mov     r9d, 729h
0x100424008  mov     [rsp+78h+var_58], rbx
0x10042400d  lea     r8, ?szFileName@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "Sql\\DkTemp\\sos\\include\\sossync.inl"
0x100424014  mov     ecx, 1
0x100424019  lea     rdx, ?szExpression@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "m_pExclusiveOwner != pWorker"
0x100424020  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100424026  xor     r8d, r8d
0x100424029  lea     r9, [rsp+78h+var_48]
0x10042402e  mov     rcx, rbp
0x100424031  lea     edx, [r8+1]
0x100424035  call    cs:__imp_?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLongWait(RWLockMode,ulong,SOS_WaitInfo const *)
0x10042403b  test    eax, eax
0x10042403d  jnz     short loc_100424066
0x10042403f  mov     byte ptr [rdi], 1
0x100424042  xor     al, al
0x100424044  mov     rbp, [rsp+78h+arg_8]
0x10042404c  mov     rbx, [rsp+78h+arg_0]
0x100424054  mov     rsi, [rsp+78h+arg_10]
0x10042405c  add     rsp, 60h
0x100424060  pop     r15
0x100424062  pop     r14
0x100424064  pop     rdi
0x100424065  retn
0x100424066  mov     [r14], r15
0x100424069  mov     rdx, gs:58h
0x100424072  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100424079  mov     ecx, [rax]
0x10042407b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100424082  mov     esi, [rax]
0x100424084  add     rsi, [rdx+rcx*8]
0x100424088  mov     rax, [rsi+100h]
0x10042408f  test    rax, rax
0x100424092  jnz     short loc_1004240A3
0x100424094  xor     ecx, ecx
0x100424096  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042409c  mov     rax, [rsi+100h]
0x1004240a3  cmp     [rbp+18h], rax
0x1004240a7  jnz     short loc_1004240CD
0x1004240a9  mov     r9d, 729h
0x1004240af  mov     [rsp+78h+var_58], rbx
0x1004240b4  lea     r8, ?szFileName@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "Sql\\DkTemp\\sos\\include\\sossync.inl"
0x1004240bb  mov     ecx, 1
0x1004240c0  lea     rdx, ?szExpression@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "m_pExclusiveOwner != pWorker"
0x1004240c7  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004240cd  xor     r8d, r8d
0x1004240d0  lea     r9, [rsp+78h+var_48]
0x1004240d5  mov     rcx, rbp
0x1004240d8  lea     edx, [r8+1]
0x1004240dc  call    cs:__imp_?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLongWait(RWLockMode,ulong,SOS_WaitInfo const *)
0x1004240e2  test    eax, eax
0x1004240e4  jnz     short loc_1004240F5
0x1004240e6  mov     byte ptr [rdi], 1
0x1004240e9  xchg    rbx, [r14]
0x1004240ec  test    rbx, rbx
0x1004240ef  jnz     loc_100424042
0x1004240f5  mov     al, 1
0x1004240f7  jmp     loc_100424044
0x1004240fc  xor     al, al
0x1004240fe  add     rsp, 60h
0x100424102  pop     r15
0x100424104  pop     r14
0x100424106  pop     rdi
0x100424107  retn
```
