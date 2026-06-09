# CSatelliteCargoContext::PopDataChunk(CSatelliteRowChunkWrapper * *,ulong)

- ea: `0x100412320`
- end: `0x100412782`
- name: `?PopDataChunk@CSatelliteCargoContext@@QEAA?AW4SOS_RESULT@@PEAPEAVCSatelliteRowChunkWrapper@@K@Z`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x100404860`

## callees

- `0x100412320`
- `0x100415950`
- `0x100415a50`
- `0x100415c70`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004123f1`
- `KERNEL32!QueryPerformanceCounter` at `0x100412442`
- `KERNEL32!QueryPerformanceCounter` at `0x10041261b`
- `KERNEL32!QueryPerformanceCounter` at `0x10041266c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004123f1`
- `KERNEL32!QueryPerformanceCounter` at `0x100412442`
- `KERNEL32!QueryPerformanceCounter` at `0x10041261b`
- `KERNEL32!QueryPerformanceCounter` at `0x10041266c`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004124c2`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004126ec`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004123e2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100412432`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041260b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041265c`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100412405`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041262f`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10041255c`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10041255c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004124b8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004126e2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100412765`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004124b8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004126e2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100412765`
- `sqldk!SystemThread_TlsIndex` at `0x1004123b4`
- `sqldk!SystemThread_TlsIndex` at `0x1004125dd`
- `sqldk!SystemThread_TlsOffset` at `0x1004123bd`
- `sqldk!SystemThread_TlsOffset` at `0x1004125e6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100412394`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004125bd`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004124ce`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004126f8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004124ce`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004126f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSatelliteCargoContext::PopDataChunk(__int64 a1, _QWORD *a2, unsigned int a3)
{
  unsigned int v3; // edi
  unsigned int v5; // r12d
  volatile signed __int64 *v6; // rsi
  LARGE_INTEGER v7; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v9; // rdi
  __int64 v10; // r8
  LARGE_INTEGER v11; // rax
  LONGLONG v12; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  volatile signed __int64 *v17; // rsi
  LARGE_INTEGER v18; // rbx
  signed __int64 v19; // r14
  __int64 v20; // rdi
  __int64 v21; // r8
  LARGE_INTEGER v22; // rax
  LONGLONG v23; // rcx
  _QWORD *v24; // rbx
  _QWORD *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v29; // [rsp+20h] [rbp-69h]
  LARGE_INTEGER v30; // [rsp+50h] [rbp-39h] BYREF
  LARGE_INTEGER v31; // [rsp+58h] [rbp-31h] BYREF
  LARGE_INTEGER v32; // [rsp+60h] [rbp-29h] BYREF
  int v33; // [rsp+70h] [rbp-19h] BYREF
  __int64 v34; // [rsp+78h] [rbp-11h]
  __int64 v35; // [rsp+80h] [rbp-9h]
  __int64 v36; // [rsp+88h] [rbp-1h]
  __int64 v37; // [rsp+90h] [rbp+7h]
  __int64 v38; // [rsp+98h] [rbp+Fh]
  _QWORD *v39; // [rsp+F0h] [rbp+67h]
  LARGE_INTEGER PerformanceCount; // [rsp+108h] [rbp+7Fh] BYREF

  v38 = -2;
  v3 = a3;
  *a2 = 0;
  v5 = 0;
  v6 = *(volatile signed __int64 **)(a1 + 3304);
  v7.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *(_DWORD *)v6 || _InterlockedCompareExchange64(v6, UniqueThread_low, 0) )
  {
    v9 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v10 && *(_QWORD *)(v10 + 272) == v10 )
        v9 = *(_QWORD *)(v10 + 256);
      if ( v9 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v7 = PerformanceCount;
        }
        else
        {
          v7.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(v6, UniqueThread_low);
    else
      Spinlock<8,19,258>::SpinToAcquireOptimistic(v6, v9, UniqueThread_low);
    if ( v9 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v30);
        v11 = v30;
      }
      else
      {
        v11.QuadPart = MEMORY[0x7FFE0008];
      }
      v12 = v11.QuadPart - v7.QuadPart;
      if ( v11.QuadPart < (unsigned __int64)v7.QuadPart )
        v12 = 0;
      *(_QWORD *)(v9 + 3192) += v12;
      v3 = a3;
    }
    else
    {
      v3 = a3;
    }
  }
  v13 = *(_QWORD **)(a1 + 3368);
  if ( v13 == (_QWORD *)(a1 + 3360) )
  {
    v13 = 0;
  }
  else if ( v13 )
  {
    v14 = (_QWORD *)v13[1];
    v15 = *v13;
    *(_QWORD *)(v15 + 8) = v14;
    *v14 = v15;
    v13[1] = 0;
    *v13 = 0;
    operator delete(0, 0x18u);
  }
  v39 = v13;
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v16 = rand();
    if ( v16 == 5 * (v16 / 5) )
      Spinlock<8,19,258>::UpdateStatSnapshot();
  }
  *v6 = 0;
  if ( !v13 )
  {
    do
    {
      if ( *(_BYTE *)(a1 + 3376) || *(_BYTE *)(a1 + 3377) )
        break;
      v33 = 4195479;
      v34 = 0;
      v36 = 0;
      v35 = 0;
      v37 = 0;
      LOBYTE(v29) = 1;
      v5 = WaitableBase::Wait(*(_QWORD *)(a1 + 3312), v3, &v33, 0, v29);
      if ( v5 || *(_BYTE *)(a1 + 3377) )
      {
        v24 = v39;
      }
      else
      {
        v17 = *(volatile signed __int64 **)(a1 + 3304);
        v18.QuadPart = 0;
        v19 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v17 || _InterlockedCompareExchange64(v17, v19, 0) )
        {
          v20 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v21 && *(_QWORD *)(v21 + 272) == v21 )
              v20 = *(_QWORD *)(v21 + 256);
            if ( v20 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v31);
                v18 = v31;
              }
              else
              {
                v18.QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(v17, v19);
          else
            Spinlock<8,19,258>::SpinToAcquireOptimistic(v17, v20, v19);
          if ( v20 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v32);
              v22 = v32;
            }
            else
            {
              v22.QuadPart = MEMORY[0x7FFE0008];
            }
            v23 = v22.QuadPart - v18.QuadPart;
            if ( v22.QuadPart < (unsigned __int64)v18.QuadPart )
              v23 = 0;
            *(_QWORD *)(v20 + 3192) += v23;
            v3 = a3;
          }
          else
          {
            v3 = a3;
          }
        }
        v24 = *(_QWORD **)(a1 + 3368);
        if ( v24 == (_QWORD *)(a1 + 3360) )
        {
          v24 = 0;
        }
        else if ( v24 )
        {
          v25 = (_QWORD *)v24[1];
          v26 = *v24;
          *(_QWORD *)(v26 + 8) = v25;
          *v25 = v26;
          v24[1] = 0;
          *v24 = 0;
        }
        if ( v39 != v24 )
          operator delete(v39, 0x18u);
        v39 = v24;
        if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v27 = rand();
          if ( v27 == 5 * (v27 / 5) )
            Spinlock<8,19,258>::UpdateStatSnapshot();
        }
        *v17 = 0;
      }
    }
    while ( !v24 );
  }
  if ( *(_BYTE *)(a1 + 3377) )
    v5 = 2;
  if ( v39 )
    *a2 = v39[2];
  operator delete(v39, 0x18u);
  return v5;
}

```

## disassembly

```asm
0x100412320  mov     [rsp-8+arg_10], r8d
0x100412325  mov     [rsp-8+arg_8], rdx
0x10041232a  push    rbp
0x10041232b  push    rbx
0x10041232c  push    rsi
0x10041232d  push    rdi
0x10041232e  push    r12
0x100412330  push    r13
0x100412332  push    r14
0x100412334  push    r15
0x100412336  lea     rbp, [rsp-1Fh]
0x10041233b  sub     rsp, 0A8h
0x100412342  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x10041234a  mov     edi, r8d
0x10041234d  mov     rax, rdx
0x100412350  mov     r15, rcx
0x100412353  xor     edx, edx
0x100412355  mov     [rax], rdx
0x100412358  mov     r12d, edx
0x10041235b  mov     [rbp+57h+arg_0], rdx
0x10041235f  mov     rsi, [rcx+0CE8h]
0x100412366  mov     [rbp+57h+var_B0], rsi
0x10041236a  mov     [rbp+57h+var_A8], edx
0x10041236d  mov     ebx, edx
0x10041236f  mov     eax, gs:48h
0x100412377  mov     r14d, eax
0x10041237a  mov     eax, [rsi]
0x10041237c  test    eax, eax
0x10041237e  jnz     short loc_100412394
0x100412380  xor     eax, eax
0x100412382  lock cmpxchg [rsi], r14
0x100412387  mov     eax, edx
0x100412389  setz    al
0x10041238c  test    eax, eax
0x10041238e  jnz     loc_100412478
0x100412394  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041239b  mov     ecx, [rax]
0x10041239d  and     ecx, 84h
0x1004123a3  mov     rdi, rdx
0x1004123a6  cmp     cl, 84h
0x1004123a9  jnz     short loc_100412405
0x1004123ab  mov     rdx, gs:58h
0x1004123b4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004123bb  mov     ecx, [rax]
0x1004123bd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004123c4  mov     r8d, [rax]
0x1004123c7  add     r8, [rdx+rcx*8]
0x1004123cb  jz      short loc_1004123DD
0x1004123cd  cmp     [r8+110h], r8
0x1004123d4  jnz     short loc_1004123DD
0x1004123d6  mov     rdi, [r8+100h]
0x1004123dd  test    rdi, rdi
0x1004123e0  jz      short loc_100412405
0x1004123e2  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004123e9  cmp     [rax], ebx
0x1004123eb  jz      short loc_1004123FD
0x1004123ed  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1004123f1  call    cs:__imp_QueryPerformanceCounter
0x1004123f7  mov     rbx, qword ptr [rbp+57h+PerformanceCount]
0x1004123fb  jmp     short loc_100412405
0x1004123fd  mov     rbx, ds:7FFE0008h
0x100412405  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041240c  mov     rcx, rsi
0x10041240f  cmp     byte ptr [rax+0C7h], 0
0x100412416  jge     short loc_100412425
0x100412418  mov     r8, r14
0x10041241b  mov     rdx, rdi
0x10041241e  call    ?SpinToAcquireOptimistic@?$Spinlock@$07$0BD@$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<8,19,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100412423  jmp     short loc_10041242D
0x100412425  mov     rdx, r14
0x100412428  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$07$0BD@$0BAC@@@AEAAX_K@Z; Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041242d  test    rdi, rdi
0x100412430  jz      short loc_100412475
0x100412432  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100412439  cmp     dword ptr [rax], 0
0x10041243c  jz      short loc_10041244E
0x10041243e  lea     rcx, [rbp+57h+var_90]; lpPerformanceCount
0x100412442  call    cs:__imp_QueryPerformanceCounter
0x100412448  mov     rax, qword ptr [rbp+57h+var_90]
0x10041244c  jmp     short loc_100412456
0x10041244e  mov     rax, ds:7FFE0008h
0x100412456  mov     rcx, rax
0x100412459  sub     rcx, rbx
0x10041245c  cmp     rax, rbx
0x10041245f  mov     r14d, 0
0x100412465  cmovb   rcx, r14
0x100412469  add     [rdi+0C78h], rcx
0x100412470  mov     edi, [rbp+57h+arg_10]
0x100412473  jmp     short loc_10041247B
0x100412475  mov     edi, [rbp+57h+arg_10]
0x100412478  xor     r14d, r14d
0x10041247b  mov     [rbp+57h+var_A8], 1
0x100412482  lea     r13, [r15+0D20h]
0x100412489  mov     rbx, [r13+8]
0x10041248d  cmp     rbx, r13
0x100412490  jnz     short loc_100412497
0x100412492  mov     rbx, r14
0x100412495  jmp     short loc_1004124BE
0x100412497  test    rbx, rbx
0x10041249a  jz      short loc_1004124BE
0x10041249c  mov     rcx, [rbx+8]
0x1004124a0  mov     rax, [rbx]
0x1004124a3  mov     [rax+8], rcx
0x1004124a7  mov     [rcx], rax
0x1004124aa  mov     [rbx+8], r14
0x1004124ae  mov     [rbx], r14
0x1004124b1  mov     edx, 18h
0x1004124b6  xor     ecx, ecx
0x1004124b8  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1004124be  mov     [rbp+57h+arg_0], rbx
0x1004124c2  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004124c9  cmp     byte ptr [rax], 0
0x1004124cc  jz      short loc_1004124F5
0x1004124ce  call    cs:__imp_rand
0x1004124d4  mov     r8d, eax
0x1004124d7  mov     eax, 66666667h
0x1004124dc  imul    r8d
0x1004124df  sar     edx, 1
0x1004124e1  mov     ecx, edx
0x1004124e3  shr     ecx, 1Fh
0x1004124e6  add     edx, ecx
0x1004124e8  lea     ecx, [rdx+rdx*4]
0x1004124eb  cmp     r8d, ecx
0x1004124ee  jnz     short loc_1004124F5
0x1004124f0  call    ?UpdateStatSnapshot@?$Spinlock@$07$0BD@$0BAC@@@AEAAXXZ; Spinlock<8,19,258>::UpdateStatSnapshot(void)
0x1004124f5  mov     [rsi], r14
0x1004124f8  mov     [rbp+57h+var_B0], r14
0x1004124fc  mov     [rbp+57h+var_A8], r14d
0x100412500  test    rbx, rbx
0x100412503  jnz     loc_100412739
0x100412509  nop     dword ptr [rax+00000000h]
0x100412510  movzx   eax, byte ptr [r15+0D30h]
0x100412518  test    al, al
0x10041251a  jnz     loc_100412739
0x100412520  movzx   eax, byte ptr [r15+0D31h]
0x100412528  test    al, al
0x10041252a  jnz     loc_100412739
0x100412530  mov     [rbp+57h+var_70], 400497h
0x100412537  mov     [rbp+57h+var_68], r14
0x10041253b  mov     [rbp+57h+var_58], r14
0x10041253f  mov     [rbp+57h+var_60], r14
0x100412543  mov     [rbp+57h+var_50], r14
0x100412547  mov     byte ptr [rsp+0E0h+var_C0], 1
0x10041254c  xor     r9d, r9d
0x10041254f  lea     r8, [rbp+57h+var_70]
0x100412553  mov     edx, edi
0x100412555  mov     rcx, [r15+0CF0h]
0x10041255c  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100412562  mov     r12d, eax
0x100412565  test    eax, eax
0x100412567  jnz     loc_10041272C
0x10041256d  movzx   eax, byte ptr [r15+0D31h]
0x100412575  test    al, al
0x100412577  jnz     loc_10041272C
0x10041257d  mov     rsi, [r15+0CE8h]
0x100412584  mov     [rbp+57h+var_A0], rsi
0x100412588  mov     [rbp+57h+var_98], r14d
0x10041258c  mov     rbx, r14
0x10041258f  mov     eax, gs:48h
0x100412597  mov     r14d, eax
0x10041259a  mov     eax, [rsi]
0x10041259c  test    eax, eax
0x10041259e  jnz     short loc_1004125BB
0x1004125a0  xor     eax, eax
0x1004125a2  lock cmpxchg [rsi], r14
0x1004125a7  mov     edx, 0
0x1004125ac  mov     eax, edx
0x1004125ae  setz    al
0x1004125b1  test    eax, eax
0x1004125b3  jnz     loc_1004126A2
0x1004125b9  jmp     short loc_1004125BD
0x1004125bb  xor     edx, edx
0x1004125bd  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004125c4  mov     ecx, [rax]
0x1004125c6  and     ecx, 84h
0x1004125cc  mov     rdi, rdx
0x1004125cf  cmp     cl, 84h
0x1004125d2  jnz     short loc_10041262F
0x1004125d4  mov     rdx, gs:58h
0x1004125dd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004125e4  mov     ecx, [rax]
0x1004125e6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004125ed  mov     r8d, [rax]
0x1004125f0  add     r8, [rdx+rcx*8]
0x1004125f4  jz      short loc_100412606
0x1004125f6  cmp     [r8+110h], r8
0x1004125fd  jnz     short loc_100412606
0x1004125ff  mov     rdi, [r8+100h]
0x100412606  test    rdi, rdi
0x100412609  jz      short loc_10041262F
0x10041260b  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100412612  cmp     dword ptr [rax], 0
0x100412615  jz      short loc_100412627
0x100412617  lea     rcx, [rbp+57h+var_88]; lpPerformanceCount
0x10041261b  call    cs:__imp_QueryPerformanceCounter
0x100412621  mov     rbx, qword ptr [rbp+57h+var_88]
0x100412625  jmp     short loc_10041262F
0x100412627  mov     rbx, ds:7FFE0008h
0x10041262f  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100412636  mov     rcx, rsi
0x100412639  cmp     byte ptr [rax+0C7h], 0
0x100412640  jge     short loc_10041264F
0x100412642  mov     r8, r14
0x100412645  mov     rdx, rdi
0x100412648  call    ?SpinToAcquireOptimistic@?$Spinlock@$07$0BD@$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<8,19,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041264d  jmp     short loc_100412657
0x10041264f  mov     rdx, r14
0x100412652  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$07$0BD@$0BAC@@@AEAAX_K@Z; Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100412657  test    rdi, rdi
0x10041265a  jz      short loc_10041269F
0x10041265c  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100412663  cmp     dword ptr [rax], 0
0x100412666  jz      short loc_100412678
0x100412668  lea     rcx, [rbp+57h+var_80]; lpPerformanceCount
0x10041266c  call    cs:__imp_QueryPerformanceCounter
0x100412672  mov     rax, qword ptr [rbp+57h+var_80]
0x100412676  jmp     short loc_100412680
0x100412678  mov     rax, ds:7FFE0008h
0x100412680  mov     rcx, rax
0x100412683  sub     rcx, rbx
0x100412686  cmp     rax, rbx
0x100412689  mov     r14d, 0
0x10041268f  cmovb   rcx, r14
0x100412693  add     [rdi+0C78h], rcx
0x10041269a  mov     edi, [rbp+57h+arg_10]
0x10041269d  jmp     short loc_1004126A5
0x10041269f  mov     edi, [rbp+57h+arg_10]
0x1004126a2  xor     r14d, r14d
0x1004126a5  mov     [rbp+57h+var_98], 1
0x1004126ac  mov     rbx, [r13+8]
0x1004126b0  cmp     rbx, r13
0x1004126b3  jnz     short loc_1004126BA
0x1004126b5  mov     rbx, r14
0x1004126b8  jmp     short loc_1004126D4
0x1004126ba  test    rbx, rbx
0x1004126bd  jz      short loc_1004126D4
0x1004126bf  mov     rcx, [rbx+8]
0x1004126c3  mov     rax, [rbx]
0x1004126c6  mov     [rax+8], rcx
0x1004126ca  mov     [rcx], rax
0x1004126cd  mov     [rbx+8], r14
0x1004126d1  mov     [rbx], r14
0x1004126d4  mov     rcx, [rbp+57h+arg_0]
0x1004126d8  cmp     rcx, rbx
0x1004126db  jz      short loc_1004126E8
0x1004126dd  mov     edx, 18h
0x1004126e2  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1004126e8  mov     [rbp+57h+arg_0], rbx
0x1004126ec  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004126f3  cmp     byte ptr [rax], 0
0x1004126f6  jz      short loc_10041271F
0x1004126f8  call    cs:__imp_rand
0x1004126fe  mov     r8d, eax
0x100412701  mov     eax, 66666667h
0x100412706  imul    r8d
0x100412709  sar     edx, 1
0x10041270b  mov     ecx, edx
0x10041270d  shr     ecx, 1Fh
0x100412710  add     edx, ecx
0x100412712  lea     ecx, [rdx+rdx*4]
0x100412715  cmp     r8d, ecx
0x100412718  jnz     short loc_10041271F
0x10041271a  call    ?UpdateStatSnapshot@?$Spinlock@$07$0BD@$0BAC@@@AEAAXXZ; Spinlock<8,19,258>::UpdateStatSnapshot(void)
0x10041271f  mov     [rsi], r14
0x100412722  mov     [rbp+57h+var_A0], r14
0x100412726  mov     [rbp+57h+var_98], r14d
0x10041272a  jmp     short loc_100412730
0x10041272c  mov     rbx, [rbp+57h+arg_0]
0x100412730  test    rbx, rbx
0x100412733  jz      loc_100412510
0x100412739  movzx   eax, byte ptr [r15+0D31h]
0x100412741  mov     ecx, 2
0x100412746  test    al, al
0x100412748  cmovnz  r12d, ecx
0x10041274c  mov     rcx, [rbp+57h+arg_0]
0x100412750  test    rcx, rcx
0x100412753  jz      short loc_100412760
0x100412755  mov     r8, [rcx+10h]
0x100412759  mov     rax, [rbp+57h+arg_8]
0x10041275d  mov     [rax], r8
0x100412760  mov     edx, 18h
0x100412765  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10041276b  mov     eax, r12d
0x10041276e  add     rsp, 0A8h
0x100412775  pop     r15
0x100412777  pop     r14
0x100412779  pop     r13
0x10041277b  pop     r12
0x10041277d  pop     rdi
0x10041277e  pop     rsi
0x10041277f  pop     rbx
0x100412780  pop     rbp
0x100412781  retn
```
