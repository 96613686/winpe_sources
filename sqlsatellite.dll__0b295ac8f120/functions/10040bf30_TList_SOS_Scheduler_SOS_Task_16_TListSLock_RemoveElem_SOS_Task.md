# TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(SOS_Task *)

- ea: `0x10040bf30`
- end: `0x10040c0cf`
- name: `?RemoveElem@?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@QEAAXPEAVSOS_Task@@@Z`
- size: `415`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x10040c0e0`
- `0x10041ced0`
- `0x10041d070`
- `0x100421c00`

## callees

- `0x100403420`
- `0x100403520`
- `0x100403760`
- `0x10040bf30`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040bfe1`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c034`
- `KERNEL32!QueryPerformanceCounter` at `0x10040bfe1`
- `KERNEL32!QueryPerformanceCounter` at `0x10040c034`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10040c07b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040bfd1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040c023`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10040bff6`
- `sqldk!SystemThread_TlsIndex` at `0x10040bfa3`
- `sqldk!SystemThread_TlsOffset` at `0x10040bfac`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040bf7e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040c098`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040c098`

## pseudocode

```c
__int64 __fastcall TList<SOS_Scheduler,SOS_Task,16,TListSLock>::RemoveElem(__int64 a1, _QWORD *a2)
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
  v11 = a2[2];
  v12 = (_QWORD *)a2[3];
  *(_QWORD *)(v11 + 8) = v12;
  *v12 = v11;
  result = *(_QWORD *)&SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  a2[3] = 0;
  a2[2] = 0;
  --*(_DWORD *)(a1 + 24);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v14 = rand();
    result = (unsigned int)(1717986919 * v14);
    if ( v14 == 5 * (v14 / 5) )
      result = Spinlock<19,1,268435714>::UpdateStatSnapshot();
  }
  *v2 = 0;
  a2[4] = 0;
  return result;
}

```

## disassembly

```asm
0x10040bf30  push    rsi
0x10040bf32  push    rdi
0x10040bf33  push    r12
0x10040bf35  sub     rsp, 40h
0x10040bf39  mov     eax, gs:48h
0x10040bf41  lea     rdi, [rcx+10h]
0x10040bf45  mov     [rsp+58h+var_20], rbx
0x10040bf4a  xor     r12d, r12d
0x10040bf4d  mov     [rsp+58h+var_30], r14
0x10040bf52  mov     rsi, rdx
0x10040bf55  mov     r14d, eax
0x10040bf58  mov     ebx, r12d
0x10040bf5b  mov     eax, [rdi]
0x10040bf5d  mov     [rsp+58h+var_38], r15
0x10040bf62  mov     r15, rcx
0x10040bf65  test    eax, eax
0x10040bf67  jnz     short loc_10040BF7E
0x10040bf69  xor     eax, eax
0x10040bf6b  lock cmpxchg [rdi], r14
0x10040bf70  mov     eax, r12d
0x10040bf73  setz    al
0x10040bf76  test    eax, eax
0x10040bf78  jnz     loc_10040C062
0x10040bf7e  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040bf85  mov     [rsp+58h+var_28], rbp
0x10040bf8a  mov     rbp, r12
0x10040bf8d  mov     ecx, [rax]
0x10040bf8f  and     ecx, 84h
0x10040bf95  cmp     cl, 84h
0x10040bf98  jnz     short loc_10040BFF6
0x10040bf9a  mov     rdx, gs:58h
0x10040bfa3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040bfaa  mov     ecx, [rax]
0x10040bfac  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040bfb3  mov     r8d, [rax]
0x10040bfb6  add     r8, [rdx+rcx*8]
0x10040bfba  jz      short loc_10040BFCC
0x10040bfbc  cmp     [r8+110h], r8
0x10040bfc3  jnz     short loc_10040BFCC
0x10040bfc5  mov     rbp, [r8+100h]
0x10040bfcc  test    rbp, rbp
0x10040bfcf  jz      short loc_10040BFF6
0x10040bfd1  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040bfd8  cmp     [rax], ebx
0x10040bfda  jz      short loc_10040BFEE
0x10040bfdc  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x10040bfe1  call    cs:__imp_QueryPerformanceCounter
0x10040bfe7  mov     rbx, qword ptr [rsp+58h+PerformanceCount]
0x10040bfec  jmp     short loc_10040BFF6
0x10040bfee  mov     rbx, ds:7FFE0008h
0x10040bff6  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10040bffd  mov     rcx, rdi
0x10040c000  cmp     [rax+0C7h], r12b
0x10040c007  jge     short loc_10040C016
0x10040c009  mov     r8, r14
0x10040c00c  mov     rdx, rbp
0x10040c00f  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10040c014  jmp     short loc_10040C01E
0x10040c016  mov     rdx, r14
0x10040c019  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10040c01e  test    rbp, rbp
0x10040c021  jz      short loc_10040C05D
0x10040c023  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040c02a  cmp     [rax], r12d
0x10040c02d  jz      short loc_10040C041
0x10040c02f  lea     rcx, [rsp+58h+arg_8]; lpPerformanceCount
0x10040c034  call    cs:__imp_QueryPerformanceCounter
0x10040c03a  mov     rax, qword ptr [rsp+58h+arg_8]
0x10040c03f  jmp     short loc_10040C049
0x10040c041  mov     rax, ds:7FFE0008h
0x10040c049  mov     rcx, rax
0x10040c04c  sub     rcx, rbx
0x10040c04f  cmp     rax, rbx
0x10040c052  cmovb   rcx, r12
0x10040c056  add     [rbp+0C78h], rcx
0x10040c05d  mov     rbp, [rsp+58h+var_28]
0x10040c062  mov     rax, [rsi+10h]
0x10040c066  mov     rcx, [rsi+18h]
0x10040c06a  mov     r14, [rsp+58h+var_30]
0x10040c06f  mov     rbx, [rsp+58h+var_20]
0x10040c074  mov     [rax+8], rcx
0x10040c078  mov     [rcx], rax
0x10040c07b  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10040c082  mov     [rsi+18h], r12
0x10040c086  mov     [rsi+10h], r12
0x10040c08a  dec     dword ptr [r15+18h]
0x10040c08e  mov     r15, [rsp+58h+var_38]
0x10040c093  cmp     [rax], r12b
0x10040c096  jz      short loc_10040C0BF
0x10040c098  call    cs:__imp_rand
0x10040c09e  mov     r8d, eax
0x10040c0a1  mov     eax, 66666667h
0x10040c0a6  imul    r8d
0x10040c0a9  sar     edx, 1
0x10040c0ab  mov     ecx, edx
0x10040c0ad  shr     ecx, 1Fh
0x10040c0b0  add     edx, ecx
0x10040c0b2  lea     ecx, [rdx+rdx*4]
0x10040c0b5  cmp     r8d, ecx
0x10040c0b8  jnz     short loc_10040C0BF
0x10040c0ba  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10040c0bf  mov     [rdi], r12
0x10040c0c2  mov     [rsi+20h], r12
0x10040c0c6  add     rsp, 40h
0x10040c0ca  pop     r12
0x10040c0cc  pop     rdi
0x10040c0cd  pop     rsi
0x10040c0ce  retn
```
