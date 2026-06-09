# TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(SOSHost *)

- ea: `0x10041e640`
- end: `0x10041e7dd`
- name: `?RemoveElem@?$TList@VHostManager@@VSOSHost@@$0A@UTListSLock@@@@QEAAXPEAVSOSHost@@@Z`
- size: `413`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100412470`
- `0x100416770`
- `0x10041d870`
- `0x10041e7f0`
- `0x10041e860`
- `0x100435700`
- `0x1004369a0`
- `0x10043f6a0`

## callees

- `0x100408910`
- `0x100408b50`
- `0x100408e00`
- `0x10041e640`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10041e6f1`
- `KERNEL32!QueryPerformanceCounter` at `0x10041e744`
- `KERNEL32!QueryPerformanceCounter` at `0x10041e6f1`
- `KERNEL32!QueryPerformanceCounter` at `0x10041e744`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10041e706`
- `sqldk!SystemThread_TlsOffset` at `0x10041e6bc`
- `sqldk!SystemThread_TlsIndex` at `0x10041e6b3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041e6e1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041e733`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10041e78a`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041e68e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041e7a6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041e7a6`

## pseudocode

```c
__int64 __fastcall TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(__int64 a1, __int64 *a2)
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
0x10041e640  push    rsi
0x10041e642  push    rdi
0x10041e643  push    r12
0x10041e645  sub     rsp, 40h
0x10041e649  mov     eax, gs:48h
0x10041e651  lea     rdi, [rcx+10h]
0x10041e655  mov     [rsp+58h+var_20], rbx
0x10041e65a  xor     r12d, r12d
0x10041e65d  mov     [rsp+58h+var_30], r14
0x10041e662  mov     rsi, rdx
0x10041e665  mov     r14d, eax
0x10041e668  mov     ebx, r12d
0x10041e66b  mov     eax, [rdi]
0x10041e66d  mov     [rsp+58h+var_38], r15
0x10041e672  mov     r15, rcx
0x10041e675  test    eax, eax
0x10041e677  jnz     short loc_10041E68E
0x10041e679  xor     eax, eax
0x10041e67b  lock cmpxchg [rdi], r14
0x10041e680  mov     eax, r12d
0x10041e683  setz    al
0x10041e686  test    eax, eax
0x10041e688  jnz     loc_10041E772
0x10041e68e  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041e695  mov     [rsp+58h+var_28], rbp
0x10041e69a  mov     rbp, r12
0x10041e69d  mov     ecx, [rax]
0x10041e69f  and     ecx, 84h
0x10041e6a5  cmp     cl, 84h
0x10041e6a8  jnz     short loc_10041E706
0x10041e6aa  mov     rdx, gs:58h
0x10041e6b3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041e6ba  mov     ecx, [rax]
0x10041e6bc  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041e6c3  mov     r8d, [rax]
0x10041e6c6  add     r8, [rdx+rcx*8]
0x10041e6ca  jz      short loc_10041E6DC
0x10041e6cc  cmp     [r8+110h], r8
0x10041e6d3  jnz     short loc_10041E6DC
0x10041e6d5  mov     rbp, [r8+100h]
0x10041e6dc  test    rbp, rbp
0x10041e6df  jz      short loc_10041E706
0x10041e6e1  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041e6e8  cmp     [rax], ebx
0x10041e6ea  jz      short loc_10041E6FE
0x10041e6ec  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x10041e6f1  call    cs:__imp_QueryPerformanceCounter
0x10041e6f7  mov     rbx, qword ptr [rsp+58h+PerformanceCount]
0x10041e6fc  jmp     short loc_10041E706
0x10041e6fe  mov     rbx, ds:7FFE0008h
0x10041e706  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x10041e70d  mov     rcx, rdi
0x10041e710  cmp     [rax+0C7h], r12b
0x10041e717  jge     short loc_10041E726
0x10041e719  mov     r8, r14
0x10041e71c  mov     rdx, rbp
0x10041e71f  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10041e724  jmp     short loc_10041E72E
0x10041e726  mov     rdx, r14
0x10041e729  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10041e72e  test    rbp, rbp
0x10041e731  jz      short loc_10041E76D
0x10041e733  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041e73a  cmp     [rax], r12d
0x10041e73d  jz      short loc_10041E751
0x10041e73f  lea     rcx, [rsp+58h+arg_8]; lpPerformanceCount
0x10041e744  call    cs:__imp_QueryPerformanceCounter
0x10041e74a  mov     rax, qword ptr [rsp+58h+arg_8]
0x10041e74f  jmp     short loc_10041E759
0x10041e751  mov     rax, ds:7FFE0008h
0x10041e759  mov     rcx, rax
0x10041e75c  sub     rcx, rbx
0x10041e75f  cmp     rax, rbx
0x10041e762  cmovb   rcx, r12
0x10041e766  add     [rbp+0C78h], rcx
0x10041e76d  mov     rbp, [rsp+58h+var_28]
0x10041e772  mov     rax, [rsi]
0x10041e775  mov     rcx, [rsi+8]
0x10041e779  mov     r14, [rsp+58h+var_30]
0x10041e77e  mov     rbx, [rsp+58h+var_20]
0x10041e783  mov     [rax+8], rcx
0x10041e787  mov     [rcx], rax
0x10041e78a  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10041e791  mov     [rsi+8], r12
0x10041e795  mov     [rsi], r12
0x10041e798  dec     dword ptr [r15+18h]
0x10041e79c  mov     r15, [rsp+58h+var_38]
0x10041e7a1  cmp     [rax], r12b
0x10041e7a4  jz      short loc_10041E7CD
0x10041e7a6  call    cs:__imp_rand
0x10041e7ac  mov     r8d, eax
0x10041e7af  mov     eax, 66666667h
0x10041e7b4  imul    r8d
0x10041e7b7  sar     edx, 1
0x10041e7b9  mov     ecx, edx
0x10041e7bb  shr     ecx, 1Fh
0x10041e7be  add     edx, ecx
0x10041e7c0  lea     ecx, [rdx+rdx*4]
0x10041e7c3  cmp     r8d, ecx
0x10041e7c6  jnz     short loc_10041E7CD
0x10041e7c8  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10041e7cd  mov     [rdi], r12
0x10041e7d0  mov     [rsi+10h], r12
0x10041e7d4  add     rsp, 40h
0x10041e7d8  pop     r12
0x10041e7da  pop     rdi
0x10041e7db  pop     rsi
0x10041e7dc  retn
```
