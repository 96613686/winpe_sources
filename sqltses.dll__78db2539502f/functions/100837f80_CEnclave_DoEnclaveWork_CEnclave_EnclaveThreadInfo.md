# CEnclave::DoEnclaveWork(CEnclave::EnclaveThreadInfo *)

- ea: `0x100837f80`
- end: `0x1008381f7`
- name: `?DoEnclaveWork@CEnclave@@QEAAXPEAUEnclaveThreadInfo@1@@Z`
- size: `631`
- prototype: `void __fastcall(CEnclave *__hidden this, struct CEnclave::EnclaveThreadInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x100837ac0`

## callees

- `0x10049fb80`
- `0x10049fbf0`
- `0x10049fe30`
- `0x1008109c0`
- `0x100836c60`
- `0x100837f80`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10083812f`
- `KERNEL32!QueryPerformanceCounter` at `0x100838184`
- `KERNEL32!QueryPerformanceCounter` at `0x10083812f`
- `KERNEL32!QueryPerformanceCounter` at `0x100838184`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1008380d1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10083811f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100838173`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10083805f`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10083805f`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100838144`
- `sqldk!SystemThread_TlsIndex` at `0x1008380f1`
- `sqldk!SystemThread_TlsOffset` at `0x1008380fa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100838087`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100838087`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall __noreturn CEnclave::DoEnclaveWork(CEnclave *this, struct CEnclave::EnclaveThreadInfo *a2)
{
  LARGE_INTEGER v4; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v6; // rdi
  __int64 v7; // r8
  LARGE_INTEGER v8; // rax
  LONGLONG v9; // rcx
  int v10; // [rsp+20h] [rbp-E0h]
  volatile signed __int64 *v11; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+38h] [rbp-C8h]
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-C0h] BYREF
  LARGE_INTEGER v14; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  char *v18; // [rsp+68h] [rbp-98h]
  char *v19; // [rsp+70h] [rbp-90h]
  _DWORD *v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+80h] [rbp-80h] BYREF
  __int64 v22; // [rsp+88h] [rbp-78h]
  __int64 v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+98h] [rbp-68h]
  __int64 v25; // [rsp+A0h] [rbp-60h]
  __int64 v26; // [rsp+A8h] [rbp-58h]
  _DWORD v27[28]; // [rsp+C0h] [rbp-40h] BYREF
  char v28; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v29[2]; // [rsp+530h] [rbp+430h] BYREF

  v26 = -2;
  v27[0] = 0;
  v27[17] = 0;
  v29[0] = &v28;
  v29[1] = v29;
  v17 = *(_DWORD *)a2;
  v18 = (char *)a2 + 16;
  v19 = (char *)a2 + 16400;
  v20 = v27;
  v15 = (char *)this + 216;
  v16 = 0;
  if ( !*(_DWORD *)a2 )
    TAutoMutex<SOS_Mutex,1>::GetAccess((__int64)&v15, 4195752);
  while ( 1 )
  {
    v21 = 4195807;
    v22 = 0;
    v24 = 0;
    v23 = 0;
    v25 = 0;
    LOBYTE(v10) = 1;
    if ( (unsigned int)WaitableBase::Wait((char *)a2 + 16416, 0xFFFFFFFFLL, &v21, 0, v10) )
      utassert_fail(1u, "SOS_OK == status", "enclavewrapper.cpp", 402, 0);
    v11 = (volatile signed __int64 *)((char *)a2 + 16488);
    v12 = 0;
    v4.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *((_DWORD *)a2 + 4122) || _InterlockedCompareExchange64(v11, UniqueThread_low, 0) )
    {
      v6 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v7 && *(_QWORD *)(v7 + 272) == v7 )
          v6 = *(_QWORD *)(v7 + 256);
        if ( v6 )
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
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v11, UniqueThread_low);
      else
        Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v11, v6, UniqueThread_low);
      if ( v6 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v14);
          v8 = v14;
        }
        else
        {
          v8.QuadPart = MEMORY[0x7FFE0008];
        }
        v9 = v8.QuadPart - v4.QuadPart;
        if ( v8.QuadPart < (unsigned __int64)v4.QuadPart )
          v9 = 0;
        *(_QWORD *)(v6 + 3192) += v9;
      }
    }
    v12 = 1;
    *((_DWORD *)a2 + 4124) = 0;
    *((_QWORD *)a2 + 2063) = 0;
    SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v11);
    (*(void (__fastcall **)(CEnclave *, int *))(*(_QWORD *)this + 16LL))(this, &v17);
    EventManualInternal<SuspendQueueSLock>::Signal((char *)a2 + 16464, 0);
    _InterlockedIncrement64((volatile signed __int64 *)this + 26);
  }
}

```

## disassembly

```asm
0x100837f80  push    rbp
0x100837f82  push    rsi
0x100837f83  push    rdi
0x100837f84  push    r12
0x100837f86  push    r13
0x100837f88  push    r14
0x100837f8a  push    r15
0x100837f8c  lea     rbp, [rsp-450h]
0x100837f94  sub     rsp, 550h
0x100837f9b  mov     [rbp+480h+var_4D8], 0FFFFFFFFFFFFFFFEh
0x100837fa3  mov     [rsp+580h+arg_10], rbx
0x100837fab  mov     rax, cs:__security_cookie
0x100837fb2  xor     rax, rsp
0x100837fb5  mov     [rbp+480h+var_40], rax
0x100837fbc  mov     rsi, rdx
0x100837fbf  mov     r15, rcx
0x100837fc2  xor     r13d, r13d
0x100837fc5  mov     [rbp+480h+var_4C0], r13d
0x100837fc9  mov     [rbp+480h+var_47C], r13d
0x100837fcd  lea     rax, [rbp+480h+var_450]
0x100837fd1  mov     [rbp+480h+var_50], rax
0x100837fd8  lea     rax, [rbp+480h+var_50]
0x100837fdf  mov     [rbp+480h+var_48], rax
0x100837fe6  mov     eax, [rdx]
0x100837fe8  mov     [rsp+580h+var_520], eax
0x100837fec  lea     rax, [rdx+10h]
0x100837ff0  mov     [rsp+580h+var_518], rax
0x100837ff5  lea     rax, [rdx+4010h]
0x100837ffc  mov     [rsp+580h+var_510], rax
0x100838001  lea     rax, [rbp+480h+var_4C0]
0x100838005  mov     [rsp+580h+var_508], rax
0x10083800a  lea     rax, [rcx+0D8h]
0x100838011  mov     [rsp+580h+var_530], rax
0x100838016  mov     [rsp+580h+var_528], r13d
0x10083801b  cmp     [rdx], r13d
0x10083801e  jnz     short loc_100838030
0x100838020  mov     edx, 4005A8h
0x100838025  lea     rcx, [rsp+580h+var_530]
0x10083802a  call    ?GetAccess@?$TAutoMutex@VSOS_Mutex@@$00@@QEAAXI@Z; TAutoMutex<SOS_Mutex,1>::GetAccess(uint)
0x10083802f  nop
0x100838030  mov     [rbp+480h+var_500], 4005DFh
0x100838037  mov     [rbp+480h+var_4F8], r13
0x10083803b  mov     [rbp+480h+var_4E8], r13
0x10083803f  mov     [rbp+480h+var_4F0], r13
0x100838043  mov     [rbp+480h+var_4E0], r13
0x100838047  lea     rcx, [rsi+4020h]
0x10083804e  mov     byte ptr [rsp+580h+var_560], 1
0x100838053  xor     r9d, r9d
0x100838056  lea     r8, [rbp+480h+var_500]
0x10083805a  mov     edx, 0FFFFFFFFh
0x10083805f  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100838065  test    eax, eax
0x100838067  jz      short loc_10083808D
0x100838069  mov     qword ptr [rsp+580h+var_560], r13
0x10083806e  mov     r9d, 192h
0x100838074  lea     r8, aEnclavewrapper; "enclavewrapper.cpp"
0x10083807b  lea     rdx, aSosOkStatus; "SOS_OK == status"
0x100838082  mov     ecx, 1
0x100838087  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10083808d  lea     rax, [rsi+4068h]
0x100838094  mov     [rsp+580h+var_550], rax
0x100838099  mov     [rsp+580h+var_548], r13d
0x10083809e  mov     rbx, r13
0x1008380a1  mov     eax, gs:48h
0x1008380a9  mov     r14d, eax
0x1008380ac  mov     rax, [rsp+580h+var_550]
0x1008380b1  mov     ecx, [rax]
0x1008380b3  test    ecx, ecx
0x1008380b5  jnz     short loc_1008380D1
0x1008380b7  mov     rcx, [rsp+580h+var_550]
0x1008380bc  xor     eax, eax
0x1008380be  lock cmpxchg [rcx], r14
0x1008380c3  mov     eax, r13d
0x1008380c6  setz    al
0x1008380c9  test    eax, eax
0x1008380cb  jnz     loc_1008381AD
0x1008380d1  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1008380d8  mov     ecx, [rax]
0x1008380da  and     ecx, 84h
0x1008380e0  mov     rdi, r13
0x1008380e3  cmp     cl, 84h
0x1008380e6  jnz     short loc_100838144
0x1008380e8  mov     rdx, gs:58h
0x1008380f1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1008380f8  mov     ecx, [rax]
0x1008380fa  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100838101  mov     r8d, [rax]
0x100838104  add     r8, [rdx+rcx*8]
0x100838108  jz      short loc_10083811A
0x10083810a  cmp     [r8+110h], r8
0x100838111  jnz     short loc_10083811A
0x100838113  mov     rdi, [r8+100h]
0x10083811a  test    rdi, rdi
0x10083811d  jz      short loc_100838144
0x10083811f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100838126  cmp     [rax], ebx
0x100838128  jz      short loc_10083813C
0x10083812a  lea     rcx, [rsp+580h+PerformanceCount]; lpPerformanceCount
0x10083812f  call    cs:__imp_QueryPerformanceCounter
0x100838135  mov     rbx, qword ptr [rsp+580h+PerformanceCount]
0x10083813a  jmp     short loc_100838144
0x10083813c  mov     rbx, ds:7FFE0008h
0x100838144  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10083814b  mov     rcx, [rsp+580h+var_550]
0x100838150  cmp     byte ptr [rax+0C7h], 0
0x100838157  jge     short loc_100838166
0x100838159  mov     r8, r14
0x10083815c  mov     rdx, rdi
0x10083815f  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100838164  jmp     short loc_10083816E
0x100838166  mov     rdx, r14
0x100838169  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10083816e  test    rdi, rdi
0x100838171  jz      short loc_1008381AD
0x100838173  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10083817a  cmp     dword ptr [rax], 0
0x10083817d  jz      short loc_100838191
0x10083817f  lea     rcx, [rsp+580h+var_538]; lpPerformanceCount
0x100838184  call    cs:__imp_QueryPerformanceCounter
0x10083818a  mov     rax, qword ptr [rsp+580h+var_538]
0x10083818f  jmp     short loc_100838199
0x100838191  mov     rax, ds:7FFE0008h
0x100838199  mov     rcx, rax
0x10083819c  sub     rcx, rbx
0x10083819f  cmp     rax, rbx
0x1008381a2  cmovb   rcx, r13
0x1008381a6  add     [rdi+0C78h], rcx
0x1008381ad  mov     [rsp+580h+var_548], 1
0x1008381b5  mov     [rsi+4070h], r13d
0x1008381bc  mov     [rsi+4078h], r13
0x1008381c3  lea     rcx, [rsp+580h+var_550]
0x1008381c8  call    ??1?$SpinlockHolder@$0BJ@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(void)
0x1008381cd  mov     rax, [r15]
0x1008381d0  lea     rdx, [rsp+580h+var_520]
0x1008381d5  mov     rcx, r15
0x1008381d8  call    qword ptr [rax+10h]
0x1008381db  xor     edx, edx
0x1008381dd  lea     rcx, [rsi+4050h]
0x1008381e4  call    ?Signal@?$EventManualInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventManualInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x1008381e9  lock inc qword ptr [r15+0D0h]
0x1008381f1  jmp     loc_100838030
```
