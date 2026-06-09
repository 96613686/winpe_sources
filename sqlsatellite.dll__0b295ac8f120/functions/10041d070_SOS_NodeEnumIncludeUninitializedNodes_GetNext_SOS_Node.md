# SOS_NodeEnumIncludeUninitializedNodes::GetNext(SOS_Node *)

- ea: `0x10041d070`
- end: `0x10041d4e6`
- name: `?GetNext@SOS_NodeEnumIncludeUninitializedNodes@@QEAAPEAVSOS_Node@@PEAV2@@Z`
- size: `1142`
- prototype: `struct SOS_Node *__fastcall(SOS_NodeEnumIncludeUninitializedNodes *__hidden this, struct SOS_Node *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x100424860`

## callees

- `0x100403420`
- `0x100403520`
- `0x100403760`
- `0x10040bf30`
- `0x10041d070`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10041d142`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d19b`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d363`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d3b6`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d142`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d19b`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d363`
- `KERNEL32!QueryPerformanceCounter` at `0x10041d3b6`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041d229`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041d449`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d12f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d188`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d353`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041d3a6`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041d15a`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041d378`
- `sqldk!SystemThread_TlsIndex` at `0x10041d101`
- `sqldk!SystemThread_TlsIndex` at `0x10041d325`
- `sqldk!SystemThread_TlsOffset` at `0x10041d10a`
- `sqldk!SystemThread_TlsOffset` at `0x10041d32e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041d0e4`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041d305`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041d235`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041d455`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041d235`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041d455`

## pseudocode

```c
struct SOS_Node *__fastcall SOS_NodeEnumIncludeUninitializedNodes::GetNext(
        SOS_NodeEnumIncludeUninitializedNodes *this,
        struct SOS_Node *a2)
{
  __int64 v2; // rsi
  SOS_NodeEnumIncludeUninitializedNodes *v4; // rbp
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // r15
  LARGE_INTEGER v8; // rbx
  signed __int64 UniqueThread_low; // rbp
  __int64 v10; // r8
  __int64 v11; // rcx
  LARGE_INTEGER v12; // rcx
  LONGLONG v13; // rax
  __int64 v14; // rcx
  signed __int32 v15; // ecx
  __int64 v16; // rcx
  int v17; // eax
  LARGE_INTEGER v18; // rbx
  __int64 v19; // r15
  signed __int64 v20; // r14
  __int64 v21; // rbp
  __int64 v22; // r8
  __int64 v23; // rcx
  LARGE_INTEGER v24; // rcx
  LONGLONG v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  signed __int32 v28; // ecx
  __int64 v29; // rcx
  int v30; // eax
  LARGE_INTEGER v32; // [rsp+20h] [rbp-58h] BYREF
  LARGE_INTEGER v33; // [rsp+28h] [rbp-50h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+18h] BYREF
  LARGE_INTEGER v36; // [rsp+98h] [rbp+20h] BYREF

  v2 = 0;
  v4 = this;
  v5 = 0;
  if ( a2 )
  {
    v6 = *(_QWORD *)this;
    if ( v6 )
    {
      if ( v6 == *((_QWORD *)v4 + 1) )
      {
        *(_QWORD *)v4 = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 40), 0xFFFFFFFF) == 1 && *(_QWORD *)(v6 + 24) )
          goto LABEL_92;
      }
      else
      {
        v7 = *((_QWORD *)v4 + 2);
        v8.QuadPart = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)(v7 + 16)
          || _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 16), UniqueThread_low, 0) )
        {
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v10 && *(_QWORD *)(v10 + 272) == v10 )
              v5 = *(_QWORD *)(v10 + 256);
            if ( v5 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&PerformanceCount);
                v8 = PerformanceCount;
              }
              else
              {
                v8.QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          v11 = v7 + 16;
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v11, UniqueThread_low);
          else
            Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v11, v5, UniqueThread_low);
          if ( v5 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v36);
              v12 = v36;
            }
            else
            {
              v12.QuadPart = MEMORY[0x7FFE0008];
            }
            v13 = 0;
            if ( v12.QuadPart >= (unsigned __int64)v8.QuadPart )
              v13 = v12.QuadPart - v8.QuadPart;
            *(_QWORD *)(v5 + 3192) += v13;
          }
        }
        v14 = *((_QWORD *)a2 + 3);
        v5 = 0;
        if ( v14 != v7 )
        {
          if ( v14 )
            v5 = v14 - 16;
          if ( v5 )
          {
            while ( 1 )
            {
              v15 = *(_DWORD *)(v5 + 40);
              if ( v15 )
              {
                while ( v15 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 40), v15 + 1, v15) )
                {
                  _mm_pause();
                  v15 = *(_DWORD *)(v5 + 40);
                  if ( !v15 )
                    goto LABEL_34;
                }
                if ( v15 != -1 )
                  break;
              }
LABEL_34:
              v16 = *(_QWORD *)(v5 + 24);
              v5 = 0;
              if ( v16 != v7 )
              {
                if ( v16 )
                  v5 = v16 - 16;
                if ( v5 )
                  continue;
              }
              break;
            }
          }
        }
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v17 = rand();
          if ( v17 == 5 * (v17 / 5) )
            Spinlock<19,1,268435714>::UpdateStatSnapshot();
        }
        v4 = this;
        *(_QWORD *)(v7 + 16) = 0;
        *(_QWORD *)this = v5;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 10, 0xFFFFFFFF) == 1 && *((_QWORD *)a2 + 3) )
          TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(*((_QWORD *)a2 + 4), a2);
      }
    }
  }
  else
  {
    v5 = *(_QWORD *)this;
  }
  if ( v5 && (*(_BYTE *)(v5 + 1568) & 4) != 0 )
  {
    v6 = *(_QWORD *)v4;
    if ( !*(_QWORD *)v4 )
      return (struct SOS_Node *)v2;
    if ( v6 != *((_QWORD *)v4 + 1) )
    {
      v18.QuadPart = 0;
      v19 = *((_QWORD *)v4 + 2);
      v20 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v19 + 16) || _InterlockedCompareExchange64((volatile signed __int64 *)(v19 + 16), v20, 0) )
      {
        v21 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v22 && *(_QWORD *)(v22 + 272) == v22 )
            v21 = *(_QWORD *)(v22 + 256);
          if ( v21 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v32);
              v18 = v32;
            }
            else
            {
              v18.QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        v23 = v19 + 16;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v23, v20);
        else
          Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v23, v21, v20);
        if ( v21 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v33);
            v24 = v33;
          }
          else
          {
            v24.QuadPart = MEMORY[0x7FFE0008];
          }
          v25 = 0;
          if ( v24.QuadPart >= (unsigned __int64)v18.QuadPart )
            v25 = v24.QuadPart - v18.QuadPart;
          *(_QWORD *)(v21 + 3192) += v25;
        }
        v4 = this;
      }
      v26 = *(_QWORD *)(v5 + 24);
      v27 = 0;
      if ( v26 != v19 )
      {
        if ( v26 )
          v27 = v26 - 16;
        if ( v27 )
        {
          while ( 1 )
          {
            v28 = *(_DWORD *)(v27 + 40);
            if ( v28 )
            {
              while ( v28 != _InterlockedCompareExchange((volatile signed __int32 *)(v27 + 40), v28 + 1, v28) )
              {
                _mm_pause();
                v28 = *(_DWORD *)(v27 + 40);
                if ( !v28 )
                  goto LABEL_80;
              }
              if ( v28 != -1 )
                break;
            }
LABEL_80:
            v29 = *(_QWORD *)(v27 + 24);
            v27 = 0;
            if ( v29 != v19 )
            {
              if ( v29 )
                v27 = v29 - 16;
              if ( v27 )
                continue;
            }
            break;
          }
        }
      }
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v30 = rand();
        if ( v30 == 5 * (v30 / 5) )
          Spinlock<19,1,268435714>::UpdateStatSnapshot();
      }
      *(_QWORD *)(v19 + 16) = 0;
      v2 = v27;
      *(_QWORD *)v4 = v27;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 40), 0xFFFFFFFF) == 1 && *(_QWORD *)(v5 + 24) )
      {
        TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(*(_QWORD *)(v5 + 32), v5);
        return (struct SOS_Node *)v27;
      }
      return (struct SOS_Node *)v2;
    }
    *(_QWORD *)v4 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 40), 0xFFFFFFFF) != 1 || !*(_QWORD *)(v6 + 24) )
      return (struct SOS_Node *)v2;
LABEL_92:
    TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(*(_QWORD *)(v6 + 32), v6);
    return (struct SOS_Node *)v2;
  }
  return (struct SOS_Node *)v5;
}

```

## disassembly

```asm
0x10041d070  mov     [rsp+arg_0], rcx
0x10041d075  push    rbx
0x10041d076  push    rbp
0x10041d077  push    rsi
0x10041d078  push    rdi
0x10041d079  push    r12
0x10041d07b  push    r13
0x10041d07d  push    r14
0x10041d07f  push    r15
0x10041d081  sub     rsp, 38h
0x10041d085  xor     esi, esi
0x10041d087  mov     r14, rdx
0x10041d08a  mov     rbp, rcx
0x10041d08d  mov     edi, esi
0x10041d08f  lea     r13d, [rsi-1]
0x10041d093  test    rdx, rdx
0x10041d096  jnz     short loc_10041D0A0
0x10041d098  mov     rdi, [rcx]
0x10041d09b  jmp     loc_10041D2A9
0x10041d0a0  mov     rcx, [rcx]
0x10041d0a3  test    rcx, rcx
0x10041d0a6  jz      loc_10041D2A9
0x10041d0ac  cmp     rcx, [rbp+8]
0x10041d0b0  jz      loc_10041D28E
0x10041d0b6  mov     r15, [rbp+10h]
0x10041d0ba  mov     rbx, rsi
0x10041d0bd  mov     eax, gs:48h
0x10041d0c5  mov     ebp, eax
0x10041d0c7  mov     eax, [r15+10h]
0x10041d0cb  test    eax, eax
0x10041d0cd  jnz     short loc_10041D0E4
0x10041d0cf  xor     eax, eax
0x10041d0d1  lock cmpxchg [r15+10h], rbp
0x10041d0d7  mov     eax, esi
0x10041d0d9  setz    al
0x10041d0dc  test    eax, eax
0x10041d0de  jnz     loc_10041D1CA
0x10041d0e4  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041d0eb  mov     ecx, [rax]
0x10041d0ed  and     ecx, 84h
0x10041d0f3  cmp     cl, 84h
0x10041d0f6  jnz     short loc_10041D15A
0x10041d0f8  mov     rdx, gs:58h
0x10041d101  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d108  mov     ecx, [rax]
0x10041d10a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041d111  mov     r8d, [rax]
0x10041d114  add     r8, [rdx+rcx*8]
0x10041d118  jz      short loc_10041D12A
0x10041d11a  cmp     [r8+110h], r8
0x10041d121  jnz     short loc_10041D12A
0x10041d123  mov     rdi, [r8+100h]
0x10041d12a  test    rdi, rdi
0x10041d12d  jz      short loc_10041D15A
0x10041d12f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d136  cmp     [rax], ebx
0x10041d138  jz      short loc_10041D152
0x10041d13a  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x10041d142  call    cs:__imp_QueryPerformanceCounter
0x10041d148  mov     rbx, qword ptr [rsp+78h+PerformanceCount]
0x10041d150  jmp     short loc_10041D15A
0x10041d152  mov     rbx, ds:7FFE0008h
0x10041d15a  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041d161  lea     rcx, [r15+10h]
0x10041d165  cmp     [rax+0C7h], sil
0x10041d16c  jge     short loc_10041D17B
0x10041d16e  mov     r8, rbp
0x10041d171  mov     rdx, rdi
0x10041d174  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041d179  jmp     short loc_10041D183
0x10041d17b  mov     rdx, rbp
0x10041d17e  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041d183  test    rdi, rdi
0x10041d186  jz      short loc_10041D1CA
0x10041d188  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d18f  cmp     [rax], esi
0x10041d191  jz      short loc_10041D1AB
0x10041d193  lea     rcx, [rsp+78h+arg_18]; lpPerformanceCount
0x10041d19b  call    cs:__imp_QueryPerformanceCounter
0x10041d1a1  mov     rcx, qword ptr [rsp+78h+arg_18]
0x10041d1a9  jmp     short loc_10041D1B3
0x10041d1ab  mov     rcx, ds:7FFE0008h
0x10041d1b3  mov     rdx, rcx
0x10041d1b6  mov     rax, rsi
0x10041d1b9  sub     rdx, rbx
0x10041d1bc  cmp     rcx, rbx
0x10041d1bf  cmovnb  rax, rdx
0x10041d1c3  add     [rdi+0C78h], rax
0x10041d1ca  mov     rcx, [r14+18h]
0x10041d1ce  mov     rdi, rsi
0x10041d1d1  cmp     rcx, r15
0x10041d1d4  jz      short loc_10041D229
0x10041d1d6  test    rcx, rcx
0x10041d1d9  lea     rax, [rcx-10h]
0x10041d1dd  cmovnz  rdi, rax
0x10041d1e1  test    rdi, rdi
0x10041d1e4  jz      short loc_10041D229
0x10041d1e6  mov     ecx, [rdi+28h]
0x10041d1e9  test    ecx, ecx
0x10041d1eb  jz      short loc_10041D20D
0x10041d1ed  nop     dword ptr [rax]
0x10041d1f0  lea     edx, [rcx+1]
0x10041d1f3  mov     eax, ecx
0x10041d1f5  lock cmpxchg [rdi+28h], edx
0x10041d1fa  cmp     ecx, eax
0x10041d1fc  jz      short loc_10041D209
0x10041d1fe  pause
0x10041d200  mov     ecx, [rdi+28h]
0x10041d203  test    ecx, ecx
0x10041d205  jnz     short loc_10041D1F0
0x10041d207  jmp     short loc_10041D20D
0x10041d209  test    edx, edx
0x10041d20b  jnz     short loc_10041D229
0x10041d20d  mov     rcx, [rdi+18h]
0x10041d211  mov     rdi, rsi
0x10041d214  cmp     rcx, r15
0x10041d217  jz      short loc_10041D229
0x10041d219  test    rcx, rcx
0x10041d21c  lea     rax, [rcx-10h]
0x10041d220  cmovnz  rdi, rax
0x10041d224  test    rdi, rdi
0x10041d227  jnz     short loc_10041D1E6
0x10041d229  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10041d230  cmp     [rax], sil
0x10041d233  jz      short loc_10041D25C
0x10041d235  call    cs:__imp_rand
0x10041d23b  mov     r8d, eax
0x10041d23e  mov     eax, 66666667h
0x10041d243  imul    r8d
0x10041d246  sar     edx, 1
0x10041d248  mov     ecx, edx
0x10041d24a  shr     ecx, 1Fh
0x10041d24d  add     edx, ecx
0x10041d24f  lea     ecx, [rdx+rdx*4]
0x10041d252  cmp     r8d, ecx
0x10041d255  jnz     short loc_10041D25C
0x10041d257  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10041d25c  mov     rbp, [rsp+78h+arg_0]
0x10041d264  mov     eax, r13d
0x10041d267  mov     [r15+10h], rsi
0x10041d26b  mov     [rbp+0], rdi
0x10041d26f  lock xadd [r14+28h], eax
0x10041d275  cmp     eax, 1
0x10041d278  jnz     short loc_10041D2A9
0x10041d27a  cmp     [r14+18h], rsi
0x10041d27e  jz      short loc_10041D2A9
0x10041d280  mov     rcx, [r14+20h]
0x10041d284  mov     rdx, r14
0x10041d287  call    ?RemoveElem@?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_Task@@@Z; TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(SOS_Task *)
0x10041d28c  jmp     short loc_10041D2A9
0x10041d28e  mov     [rbp+0], rsi
0x10041d292  mov     eax, r13d
0x10041d295  lock xadd [rcx+28h], eax
0x10041d29a  cmp     eax, 1
0x10041d29d  jnz     short loc_10041D2A9
0x10041d29f  cmp     [rcx+18h], rsi
0x10041d2a3  jnz     loc_10041D4C1
0x10041d2a9  test    rdi, rdi
0x10041d2ac  jz      loc_10041D4D2
0x10041d2b2  test    byte ptr [rdi+620h], 4
0x10041d2b9  jz      loc_10041D4D2
0x10041d2bf  mov     rcx, [rbp+0]
0x10041d2c3  test    rcx, rcx
0x10041d2c6  jz      loc_10041D4CD
0x10041d2cc  cmp     rcx, [rbp+8]
0x10041d2d0  jz      loc_10041D4AB
0x10041d2d6  mov     eax, gs:48h
0x10041d2de  mov     rbx, rsi
0x10041d2e1  mov     r15, [rbp+10h]
0x10041d2e5  mov     r14d, eax
0x10041d2e8  mov     eax, [r15+10h]
0x10041d2ec  test    eax, eax
0x10041d2ee  jnz     short loc_10041D305
0x10041d2f0  xor     eax, eax
0x10041d2f2  lock cmpxchg [r15+10h], r14
0x10041d2f8  mov     eax, esi
0x10041d2fa  setz    al
0x10041d2fd  test    eax, eax
0x10041d2ff  jnz     loc_10041D3EA
0x10041d305  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041d30c  mov     rbp, rsi
0x10041d30f  mov     ecx, [rax]
0x10041d311  and     ecx, 84h
0x10041d317  cmp     cl, 84h
0x10041d31a  jnz     short loc_10041D378
0x10041d31c  mov     rdx, gs:58h
0x10041d325  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041d32c  mov     ecx, [rax]
0x10041d32e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041d335  mov     r8d, [rax]
0x10041d338  add     r8, [rdx+rcx*8]
0x10041d33c  jz      short loc_10041D34E
0x10041d33e  cmp     [r8+110h], r8
0x10041d345  jnz     short loc_10041D34E
0x10041d347  mov     rbp, [r8+100h]
0x10041d34e  test    rbp, rbp
0x10041d351  jz      short loc_10041D378
0x10041d353  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d35a  cmp     [rax], ebx
0x10041d35c  jz      short loc_10041D370
0x10041d35e  lea     rcx, [rsp+78h+var_58]; lpPerformanceCount
0x10041d363  call    cs:__imp_QueryPerformanceCounter
0x10041d369  mov     rbx, qword ptr [rsp+78h+var_58]
0x10041d36e  jmp     short loc_10041D378
0x10041d370  mov     rbx, ds:7FFE0008h
0x10041d378  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041d37f  lea     rcx, [r15+10h]
0x10041d383  cmp     [rax+0C7h], sil
0x10041d38a  jge     short loc_10041D399
0x10041d38c  mov     r8, r14
0x10041d38f  mov     rdx, rbp
0x10041d392  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041d397  jmp     short loc_10041D3A1
0x10041d399  mov     rdx, r14
0x10041d39c  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041d3a1  test    rbp, rbp
0x10041d3a4  jz      short loc_10041D3E2
0x10041d3a6  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041d3ad  cmp     [rax], esi
0x10041d3af  jz      short loc_10041D3C3
0x10041d3b1  lea     rcx, [rsp+78h+var_50]; lpPerformanceCount
0x10041d3b6  call    cs:__imp_QueryPerformanceCounter
0x10041d3bc  mov     rcx, qword ptr [rsp+78h+var_50]
0x10041d3c1  jmp     short loc_10041D3CB
0x10041d3c3  mov     rcx, ds:7FFE0008h
0x10041d3cb  mov     rdx, rcx
0x10041d3ce  mov     rax, rsi
0x10041d3d1  sub     rdx, rbx
0x10041d3d4  cmp     rcx, rbx
0x10041d3d7  cmovnb  rax, rdx
0x10041d3db  add     [rbp+0C78h], rax
0x10041d3e2  mov     rbp, [rsp+78h+arg_0]
0x10041d3ea  mov     rcx, [rdi+18h]
0x10041d3ee  mov     rbx, rsi
0x10041d3f1  cmp     rcx, r15
0x10041d3f4  jz      short loc_10041D449
0x10041d3f6  test    rcx, rcx
0x10041d3f9  lea     rax, [rcx-10h]
0x10041d3fd  cmovnz  rbx, rax
0x10041d401  test    rbx, rbx
0x10041d404  jz      short loc_10041D449
0x10041d406  mov     ecx, [rbx+28h]
0x10041d409  test    ecx, ecx
0x10041d40b  jz      short loc_10041D42D
0x10041d40d  nop     dword ptr [rax]
0x10041d410  lea     edx, [rcx+1]
0x10041d413  mov     eax, ecx
0x10041d415  lock cmpxchg [rbx+28h], edx
0x10041d41a  cmp     ecx, eax
0x10041d41c  jz      short loc_10041D429
0x10041d41e  pause
0x10041d420  mov     ecx, [rbx+28h]
0x10041d423  test    ecx, ecx
0x10041d425  jnz     short loc_10041D410
0x10041d427  jmp     short loc_10041D42D
0x10041d429  test    edx, edx
0x10041d42b  jnz     short loc_10041D449
0x10041d42d  mov     rcx, [rbx+18h]
0x10041d431  mov     rbx, rsi
0x10041d434  cmp     rcx, r15
0x10041d437  jz      short loc_10041D449
0x10041d439  test    rcx, rcx
0x10041d43c  lea     rax, [rcx-10h]
0x10041d440  cmovnz  rbx, rax
0x10041d444  test    rbx, rbx
0x10041d447  jnz     short loc_10041D406
0x10041d449  mov     rcx, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10041d450  cmp     [rcx], sil
0x10041d453  jz      short loc_10041D47C
0x10041d455  call    cs:__imp_rand
0x10041d45b  mov     r8d, eax
0x10041d45e  mov     eax, 66666667h
0x10041d463  imul    r8d
0x10041d466  sar     edx, 1
0x10041d468  mov     ecx, edx
0x10041d46a  shr     ecx, 1Fh
0x10041d46d  add     edx, ecx
0x10041d46f  lea     ecx, [rdx+rdx*4]
0x10041d472  cmp     r8d, ecx
0x10041d475  jnz     short loc_10041D47C
0x10041d477  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10041d47c  mov     [r15+10h], rsi
0x10041d480  mov     rsi, rbx
0x10041d483  mov     [rbp+0], rbx
0x10041d487  lock xadd [rdi+28h], r13d
0x10041d48d  cmp     r13d, 1
0x10041d491  jnz     short loc_10041D4CD
0x10041d493  cmp     qword ptr [rdi+18h], 0
0x10041d498  jz      short loc_10041D4CD
0x10041d49a  mov     rcx, [rdi+20h]
0x10041d49e  mov     rdx, rdi
0x10041d4a1  call    ?RemoveElem@?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_Task@@@Z; TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(SOS_Task *)
0x10041d4a6  mov     rax, rbx
0x10041d4a9  jmp     short loc_10041D4D5
0x10041d4ab  mov     [rbp+0], rsi
0x10041d4af  lock xadd [rcx+28h], r13d
0x10041d4b5  cmp     r13d, 1
0x10041d4b9  jnz     short loc_10041D4CD
0x10041d4bb  cmp     [rcx+18h], rsi
0x10041d4bf  jz      short loc_10041D4CD
  ... truncated ...
```
