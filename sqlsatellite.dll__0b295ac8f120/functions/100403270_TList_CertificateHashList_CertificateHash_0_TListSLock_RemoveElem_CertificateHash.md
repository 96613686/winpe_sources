# TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(CertificateHash *)

- ea: `0x100403270`
- end: `0x10040340d`
- name: `?RemoveElem@?$TList@VCertificateHashList@@VCertificateHash@@$0A@UTListSLock@@@@QEAAXPEAVCertificateHash@@@Z`
- size: `413`
- prototype: ``
- caller_count: `18`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100401d90`
- `0x100403150`
- `0x100409790`
- `0x10040af40`
- `0x10040b9b0`
- `0x10040c0e0`
- `0x10040d590`
- `0x10040d600`
- `0x10040d970`
- `0x100424110`
- `0x100446b10`
- `0x1004704c0`
- `0x1004740e0`
- `0x100476d20`
- `0x100477b20`
- `0x10047ed10`
- `0x10048e940`
- `0x10048e9b0`

## callees

- `0x100403270`
- `0x100403420`
- `0x100403520`
- `0x100403760`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100403321`
- `KERNEL32!QueryPerformanceCounter` at `0x100403374`
- `KERNEL32!QueryPerformanceCounter` at `0x100403321`
- `KERNEL32!QueryPerformanceCounter` at `0x100403374`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004033ba`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100403311`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100403363`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100403336`
- `sqldk!SystemThread_TlsIndex` at `0x1004032e3`
- `sqldk!SystemThread_TlsOffset` at `0x1004032ec`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004032be`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004033d6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004033d6`

## pseudocode

```c
__int64 __fastcall TList<CertificateHashList,CertificateHash,0,TListSLock>::RemoveElem(__int64 a1, __int64 *a2)
{
  volatile signed __int64 *v2; // rdi
  signed __int64 UniqueThread_low; // r14
  LARGE_INTEGER v5; // rbx
  __int64 v7; // rbp
  __int64 v8; // r8
  LARGE_INTEGER v9; // rax
  LONGLONG v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  __int64 result; // rax
  int v14; // r8d
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp+8h] BYREF
  LARGE_INTEGER v16; // [rsp+68h] [rbp+10h] BYREF

  v2 = (volatile signed __int64 *)(a1 + 16);
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  v5.QuadPart = 0;
  if ( *(_DWORD *)(a1 + 16) || _InterlockedCompareExchange64(v2, UniqueThread_low, 0) )
  {
    v7 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v8 && *(_QWORD *)(v8 + 272) == v8 )
        v7 = *(_QWORD *)(v8 + 256);
      if ( v7 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v5 = PerformanceCount;
        }
        else
        {
          v5.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v2, UniqueThread_low);
    else
      Spinlock<19,1,268435714>::SpinToAcquireOptimistic(v2, v7, UniqueThread_low);
    if ( v7 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v16);
        v9 = v16;
      }
      else
      {
        v9.QuadPart = MEMORY[0x7FFE0008];
      }
      v10 = v9.QuadPart - v5.QuadPart;
      if ( v9.QuadPart < (unsigned __int64)v5.QuadPart )
        v10 = 0;
      *(_QWORD *)(v7 + 3192) += v10;
    }
  }
  v11 = *a2;
  v12 = (_QWORD *)a2[1];
  *(_QWORD *)(v11 + 8) = v12;
  *v12 = v11;
  result = *(_QWORD *)&SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  a2[1] = 0;
  *a2 = 0;
  --*(_DWORD *)(a1 + 24);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v14 = rand();
    result = (unsigned int)(1717986919 * v14);
    if ( v14 == 5 * (v14 / 5) )
      result = Spinlock<19,1,268435714>::UpdateStatSnapshot();
  }
  *v2 = 0;
  a2[2] = 0;
  return result;
}

```

## disassembly

```asm
0x100403270  push    rsi
0x100403272  push    rdi
0x100403273  push    r12
0x100403275  sub     rsp, 40h
0x100403279  mov     eax, gs:48h
0x100403281  lea     rdi, [rcx+10h]
0x100403285  mov     [rsp+58h+var_20], rbx
0x10040328a  xor     r12d, r12d
0x10040328d  mov     [rsp+58h+var_30], r14
0x100403292  mov     rsi, rdx
0x100403295  mov     r14d, eax
0x100403298  mov     ebx, r12d
0x10040329b  mov     eax, [rdi]
0x10040329d  mov     [rsp+58h+var_38], r15
0x1004032a2  mov     r15, rcx
0x1004032a5  test    eax, eax
0x1004032a7  jnz     short loc_1004032BE
0x1004032a9  xor     eax, eax
0x1004032ab  lock cmpxchg [rdi], r14
0x1004032b0  mov     eax, r12d
0x1004032b3  setz    al
0x1004032b6  test    eax, eax
0x1004032b8  jnz     loc_1004033A2
0x1004032be  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004032c5  mov     [rsp+58h+var_28], rbp
0x1004032ca  mov     rbp, r12
0x1004032cd  mov     ecx, [rax]
0x1004032cf  and     ecx, 84h
0x1004032d5  cmp     cl, 84h
0x1004032d8  jnz     short loc_100403336
0x1004032da  mov     rdx, gs:58h
0x1004032e3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004032ea  mov     ecx, [rax]
0x1004032ec  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004032f3  mov     r8d, [rax]
0x1004032f6  add     r8, [rdx+rcx*8]
0x1004032fa  jz      short loc_10040330C
0x1004032fc  cmp     [r8+110h], r8
0x100403303  jnz     short loc_10040330C
0x100403305  mov     rbp, [r8+100h]
0x10040330c  test    rbp, rbp
0x10040330f  jz      short loc_100403336
0x100403311  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100403318  cmp     [rax], ebx
0x10040331a  jz      short loc_10040332E
0x10040331c  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x100403321  call    cs:__imp_QueryPerformanceCounter
0x100403327  mov     rbx, qword ptr [rsp+58h+PerformanceCount]
0x10040332c  jmp     short loc_100403336
0x10040332e  mov     rbx, ds:7FFE0008h
0x100403336  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040333d  mov     rcx, rdi
0x100403340  cmp     [rax+0C7h], r12b
0x100403347  jge     short loc_100403356
0x100403349  mov     r8, r14
0x10040334c  mov     rdx, rbp
0x10040334f  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100403354  jmp     short loc_10040335E
0x100403356  mov     rdx, r14
0x100403359  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040335e  test    rbp, rbp
0x100403361  jz      short loc_10040339D
0x100403363  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040336a  cmp     [rax], r12d
0x10040336d  jz      short loc_100403381
0x10040336f  lea     rcx, [rsp+58h+arg_8]; lpPerformanceCount
0x100403374  call    cs:__imp_QueryPerformanceCounter
0x10040337a  mov     rax, qword ptr [rsp+58h+arg_8]
0x10040337f  jmp     short loc_100403389
0x100403381  mov     rax, ds:7FFE0008h
0x100403389  mov     rcx, rax
0x10040338c  sub     rcx, rbx
0x10040338f  cmp     rax, rbx
0x100403392  cmovb   rcx, r12
0x100403396  add     [rbp+0C78h], rcx
0x10040339d  mov     rbp, [rsp+58h+var_28]
0x1004033a2  mov     rax, [rsi]
0x1004033a5  mov     rcx, [rsi+8]
0x1004033a9  mov     r14, [rsp+58h+var_30]
0x1004033ae  mov     rbx, [rsp+58h+var_20]
0x1004033b3  mov     [rax+8], rcx
0x1004033b7  mov     [rcx], rax
0x1004033ba  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004033c1  mov     [rsi+8], r12
0x1004033c5  mov     [rsi], r12
0x1004033c8  dec     dword ptr [r15+18h]
0x1004033cc  mov     r15, [rsp+58h+var_38]
0x1004033d1  cmp     [rax], r12b
0x1004033d4  jz      short loc_1004033FD
0x1004033d6  call    cs:__imp_rand
0x1004033dc  mov     r8d, eax
0x1004033df  mov     eax, 66666667h
0x1004033e4  imul    r8d
0x1004033e7  sar     edx, 1
0x1004033e9  mov     ecx, edx
0x1004033eb  shr     ecx, 1Fh
0x1004033ee  add     edx, ecx
0x1004033f0  lea     ecx, [rdx+rdx*4]
0x1004033f3  cmp     r8d, ecx
0x1004033f6  jnz     short loc_1004033FD
0x1004033f8  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x1004033fd  mov     [rdi], r12
0x100403400  mov     [rsi+10h], r12
0x100403404  add     rsp, 40h
0x100403408  pop     r12
0x10040340a  pop     rdi
0x10040340b  pop     rsi
0x10040340c  retn
```
