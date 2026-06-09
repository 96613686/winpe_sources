# MiniSOSThreadResourcesMgr::RetrieveObject(void)

- ea: `0x100435fb0`
- end: `0x1004360be`
- name: `?RetrieveObject@MiniSOSThreadResourcesMgr@@QEAAPEAVMiniSOSThreadResources@@XZ`
- size: `270`
- prototype: `struct MiniSOSThreadResources *__fastcall(MiniSOSThreadResourcesMgr *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1004360f0`

## callees

- `0x100435fb0`
- `0x1004364b0`
- `0x1004366c0`
- `0x100473970`
- `0x100473b80`
- `0x100473dc0`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x100436089`
- `KERNEL32!GetCurrentThreadId` at `0x100436089`
- `KERNEL32!QueryPerformanceCounter` at `0x10048d499`
- `KERNEL32!QueryPerformanceCounter` at `0x10048d4df`
- `KERNEL32!QueryPerformanceCounter` at `0x10048d499`
- `KERNEL32!QueryPerformanceCounter` at `0x10048d4df`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048d572`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048d572`

## string_xrefs

- `0x100435fbe`: `Out of SystemThread resources`

## pseudocode

```c
struct MiniSOSThreadResources *__fastcall MiniSOSThreadResourcesMgr::RetrieveObject(MiniSOSThreadResourcesMgr *this)
{
  volatile signed __int64 *v2; // rsi
  signed __int64 UniqueThread_low; // r14
  LARGE_INTEGER v4; // rbx
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx
  __int64 v8; // rbp
  __int64 v9; // rdx
  SpinlockBase *v10; // rcx
  LARGE_INTEGER v11; // rcx
  LONGLONG v12; // rax
  int v13; // r8d
  LARGE_INTEGER v14; // [rsp+30h] [rbp-48h] BYREF
  signed __int32 v15; // [rsp+80h] [rbp+8h]
  signed __int32 v16; // [rsp+88h] [rbp+10h]
  _QWORD *Object; // [rsp+90h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp+20h] BYREF

LABEL_1:
  Object = 0;
  do
  {
    while ( 1 )
    {
      v15 = *((_DWORD *)this + 6);
      v16 = *((_DWORD *)this + 7);
      if ( v15 > v16 )
        break;
      if ( !(unsigned int)MiniSOSThreadResourcesMgr::AllocObject((unsigned int)v16, &Object) )
        goto LABEL_4;
      if ( v15 > 0 )
        break;
      utassert_fail(1u, "FALSE", "worker_ext.cpp", 1326, "Out of SystemThread resources");
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 6, v15 - 1, v15) != v15 )
      goto LABEL_1;
    Object = (_QWORD *)TObjectPool<TMRUContainer<MiniSOSThreadResources,0>,ObjectPoolSLock>::RetrieveObject(this);
  }
  while ( !Object );
LABEL_4:
  v2 = (volatile signed __int64 *)((char *)this + 40);
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  v4.QuadPart = 0;
  if ( *((_DWORD *)this + 10) || _InterlockedCompareExchange64(v2, UniqueThread_low, 0) )
  {
    v8 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
         + (unsigned int)SystemThread_TlsOffset;
      if ( v9 && *(_QWORD *)(v9 + 272) == v9 )
        v8 = *(_QWORD *)(v9 + 256);
      if ( v8 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v4 = PerformanceCount;
        }
        else
        {
          v4.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    v10 = (MiniSOSThreadResourcesMgr *)((char *)this + 40);
    if ( (qword_1007149B5 & 0x800000) == 0 )
      Spinlock<15,1,268435714>::SpinToAcquireWithExponentialBackoff(v10);
    else
      Spinlock<15,1,268435714>::SpinToAcquireOptimistic(v10);
    if ( v8 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v14);
        v11 = v14;
      }
      else
      {
        v11.QuadPart = MEMORY[0x7FFE0008];
      }
      v12 = 0;
      if ( v11.QuadPart >= (unsigned __int64)v4.QuadPart )
        v12 = v11.QuadPart - v4.QuadPart;
      *(_QWORD *)(v8 + 3192) += v12;
    }
  }
  v5 = Object;
  *Object = *((_QWORD *)this + 6);
  *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = v5;
  *((_QWORD *)this + 6) = v5;
  v5[1] = (char *)this + 48;
  v6 = Object;
  Object[757] = NtCurrentTeb();
  *((_DWORD *)v6 + 1516) = GetCurrentThreadId();
  ++*((_DWORD *)this + 16);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v13 = rand();
    if ( v13 == 5 * (v13 / 5) )
      Spinlock<15,1,268435714>::UpdateStatSnapshot();
  }
  *v2 = 0;
  return (struct MiniSOSThreadResources *)v6;
}

```

## disassembly

```asm
0x100435fb0  push    rbx
0x100435fb2  push    rsi
0x100435fb3  push    r15
0x100435fb5  sub     rsp, 60h
0x100435fb9  mov     [rsp+78h+var_28], rdi
0x100435fbe  lea     rbx, aOutOfSystemthr; "Out of SystemThread resources"
0x100435fc5  mov     [rsp+78h+var_30], r14
0x100435fca  mov     rdi, rcx
0x100435fcd  xor     r15d, r15d
0x100435fd0  mov     [rsp+78h+arg_10], r15
0x100435fd8  nop     dword ptr [rax+rax+00000000h]
0x100435fe0  mov     eax, [rdi+18h]
0x100435fe3  mov     [rsp+78h+arg_0], eax
0x100435fea  mov     eax, [rdi+1Ch]
0x100435fed  mov     [rsp+78h+arg_8], eax
0x100435ff4  mov     ecx, [rsp+78h+arg_8]
0x100435ffb  mov     eax, [rsp+78h+arg_0]
0x100436002  cmp     eax, ecx
0x100436004  jg      loc_100436455
0x10043600a  lea     rdx, [rsp+78h+arg_10]
0x100436012  call    ?AllocObject@MiniSOSThreadResourcesMgr@@AEAA?AW4SOS_RESULT@@PEAPEAVMiniSOSThreadResources@@@Z; MiniSOSThreadResourcesMgr::AllocObject(MiniSOSThreadResources * *)
0x100436017  test    eax, eax
0x100436019  jnz     loc_10048D50F
0x10043601f  mov     eax, gs:48h
0x100436027  lea     rsi, [rdi+28h]
0x10043602b  mov     r14d, eax
0x10043602e  mov     rbx, r15
0x100436031  mov     eax, [rsi]
0x100436033  test    eax, eax
0x100436035  jnz     loc_10048D43E
0x10043603b  xor     eax, eax
0x10043603d  lock cmpxchg [rsi], r14
0x100436042  mov     eax, r15d
0x100436045  setz    al
0x100436048  test    eax, eax
0x10043604a  jz      loc_10048D43E
0x100436050  mov     rax, [rdi+30h]
0x100436054  lea     rdx, [rdi+30h]
0x100436058  mov     rcx, [rsp+78h+arg_10]
0x100436060  mov     [rcx], rax
0x100436063  mov     rax, [rdx]
0x100436066  mov     [rax+8], rcx
0x10043606a  mov     [rdx], rcx
0x10043606d  mov     [rcx+8], rdx
0x100436071  mov     rax, gs:30h
0x10043607a  mov     rbx, [rsp+78h+arg_10]
0x100436082  mov     [rbx+17A8h], rax
0x100436089  call    cs:__imp_GetCurrentThreadId
0x10043608f  mov     r14, [rsp+78h+var_30]
0x100436094  mov     [rbx+17B0h], eax
0x10043609a  inc     dword ptr [rdi+40h]
0x10043609d  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, r15b; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004360a4  mov     rdi, [rsp+78h+var_28]
0x1004360a9  jnz     loc_10048D572
0x1004360af  mov     [rsi], r15
0x1004360b2  mov     rax, rbx
0x1004360b5  add     rsp, 60h
0x1004360b9  pop     r15
0x1004360bb  pop     rsi
0x1004360bc  pop     rbx
0x1004360bd  retn
0x100436455  mov     eax, [rsp+78h+arg_0]
0x10043645c  mov     [rsp+78h+arg_0], eax
0x100436463  mov     eax, [rsp+78h+arg_0]
0x10043646a  mov     ecx, [rsp+78h+arg_0]
0x100436471  dec     ecx
0x100436473  lock cmpxchg [rdi+18h], ecx
0x100436478  mov     ecx, [rsp+78h+arg_0]
0x10043647f  cmp     eax, ecx
0x100436481  jnz     loc_100435FD0
0x100436487  mov     rcx, rdi
0x10043648a  call    ?RetrieveObject@?$TObjectPool@V?$TMRUContainer@VMiniSOSThreadResources@@$0A@@@UObjectPoolSLock@@@@QEAAPEAVMiniSOSThreadResources@@XZ; TObjectPool<TMRUContainer<MiniSOSThreadResources,0>,ObjectPoolSLock>::RetrieveObject(void)
0x10043648f  mov     [rsp+78h+arg_10], rax
0x100436497  test    rax, rax
0x10043649a  jnz     loc_10043601F
0x1004364a0  jmp     loc_100435FE0
0x10048d43e  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10048d444  and     eax, 84h
0x10048d449  mov     [rsp+78h+var_20], rbp
0x10048d44e  mov     rbp, r15
0x10048d451  cmp     al, 84h
0x10048d453  jnz     short loc_10048D4AA
0x10048d455  mov     rcx, gs:58h
0x10048d45e  mov     eax, cs:_tls_index
0x10048d464  mov     edx, cs:SystemThread_TlsOffset
0x10048d46a  add     rdx, [rcx+rax*8]
0x10048d46e  jz      short loc_10048D480
0x10048d470  cmp     [rdx+110h], rdx
0x10048d477  jnz     short loc_10048D480
0x10048d479  mov     rbp, [rdx+100h]
0x10048d480  test    rbp, rbp
0x10048d483  jz      short loc_10048D4AA
0x10048d485  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x10048d48b  jz      loc_10048D547
0x10048d491  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x10048d499  call    cs:__imp_QueryPerformanceCounter
0x10048d49f  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x10048d4a7  jmp     short loc_10048D4AA
0x10048d4aa  test    byte ptr cs:qword_1007149B5+2, 80h
0x10048d4b1  mov     rcx, rsi; this
0x10048d4b4  jz      loc_10048D555
0x10048d4ba  mov     r8, r14
0x10048d4bd  mov     rdx, rbp
0x10048d4c0  call    ?SpinToAcquireOptimistic@?$Spinlock@$0P@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<15,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10048d4c5  jmp     short loc_10048D4C8
0x10048d4c8  test    rbp, rbp
0x10048d4cb  jz      short loc_10048D504
0x10048d4cd  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, r15d; int Base_PublicGlobals::sm_invariantTscAvailable
0x10048d4d4  jz      loc_10048D564
0x10048d4da  lea     rcx, [rsp+78h+var_48]; lpPerformanceCount
0x10048d4df  call    cs:__imp_QueryPerformanceCounter
0x10048d4e5  mov     rcx, qword ptr [rsp+78h+var_48]
0x10048d4ea  jmp     short loc_10048D4ED
0x10048d4ed  mov     rdx, rcx
0x10048d4f0  mov     rax, r15
0x10048d4f3  sub     rdx, rbx
0x10048d4f6  cmp     rcx, rbx
0x10048d4f9  cmovnb  rax, rdx
0x10048d4fd  add     [rbp+0C78h], rax
0x10048d504  mov     rbp, [rsp+78h+var_20]
0x10048d509  jmp     loc_100436050
0x10048d50f  mov     eax, [rsp+78h+arg_0]
0x10048d516  test    eax, eax
0x10048d518  jg      loc_100436455
0x10048d51e  mov     r9d, 52Eh; int
0x10048d524  mov     [rsp+78h+Format], rbx; Format
0x10048d529  lea     r8, aWorkerExtCpp; "worker_ext.cpp"
0x10048d530  mov     ecx, 1; unsigned int
0x10048d535  lea     rdx, ?szExpression@?8??GetNumberOfPartitions@?$CMemPartitioned@V?$CMemDetour@V?$CMemThread@VCMemLargePageObj@@@@@@@@SAKW4PartitioningType@@@Z@4QBDB; "FALSE"
0x10048d53c  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10048d541  jmp     loc_100435FE0
0x10048d547  mov     rbx, ds:7FFE0008h
0x10048d54f  jmp     loc_10048D4AA
0x10048d555  mov     rdx, r14
0x10048d558  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0P@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<15,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10048d55d  nop
0x10048d55e  jmp     loc_10048D4C8
0x10048d564  mov     rcx, ds:7FFE0008h
0x10048d56c  jmp     loc_10048D4ED
0x10048d572  call    cs:__imp_rand
0x10048d578  mov     r8d, eax
0x10048d57b  mov     eax, 66666667h
0x10048d580  imul    r8d
0x10048d583  sar     edx, 1
0x10048d585  mov     ecx, edx
0x10048d587  shr     ecx, 1Fh
0x10048d58a  add     edx, ecx
0x10048d58c  lea     ecx, [rdx+rdx*4]
0x10048d58f  cmp     r8d, ecx
0x10048d592  jnz     loc_1004360AF
0x10048d598  call    ?UpdateStatSnapshot@?$Spinlock@$0P@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<15,1,268435714>::UpdateStatSnapshot(void)
0x10048d59d  nop
0x10048d59e  jmp     loc_1004360AF
```
