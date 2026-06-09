# TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(SOS_RingBuffer *)

- ea: `0x100408160`
- end: `0x100408318`
- name: `?AppendElem@?$TList@VSOS_Node@@VSOS_RingBuffer@@$0A@UTListSLock@@@@QEAAXPEAVSOS_RingBuffer@@@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100407030`

## callees

- `0x100408160`
- `0x100408910`
- `0x100408b50`
- `0x100408e00`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100408224`
- `KERNEL32!QueryPerformanceCounter` at `0x100408277`
- `KERNEL32!QueryPerformanceCounter` at `0x100408224`
- `KERNEL32!QueryPerformanceCounter` at `0x100408277`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100408239`
- `sqldk!SystemThread_TlsOffset` at `0x1004081ef`
- `sqldk!SystemThread_TlsIndex` at `0x1004081e6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100408214`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100408266`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004082bc`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004081c1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004082e6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004082e6`

## pseudocode

```c
__int64 __fastcall TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(
        volatile signed __int64 *a1,
        volatile signed __int64 *a2)
{
  volatile signed __int64 *v2; // rdi
  LARGE_INTEGER v3; // rbx
  volatile signed __int64 *v4; // r12
  signed __int64 UniqueThread_low; // rbp
  __int64 v8; // rsi
  __int64 v9; // r8
  LARGE_INTEGER v10; // rax
  LONGLONG v11; // rcx
  __int64 result; // rax
  int v13; // r8d
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp+8h] BYREF
  LARGE_INTEGER v15; // [rsp+68h] [rbp+10h] BYREF

  v2 = a1 + 2;
  v3.QuadPart = 0;
  v4 = a1 - 12;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( !a1 )
    v4 = 0;
  if ( *(_DWORD *)v2 || _InterlockedCompareExchange64(v2, UniqueThread_low, 0) )
  {
    v8 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v9 && *(_QWORD *)(v9 + 272) == v9 )
        v8 = *(_QWORD *)(v9 + 256);
      if ( v8 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v3 = PerformanceCount;
        }
        else
        {
          v3.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(v2, UniqueThread_low);
    else
      Spinlock<19,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)v2, v8, UniqueThread_low);
    if ( v8 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v15);
        v10 = v15;
      }
      else
      {
        v10.QuadPart = MEMORY[0x7FFE0008];
      }
      v11 = v10.QuadPart - v3.QuadPart;
      if ( v10.QuadPart < (unsigned __int64)v3.QuadPart )
        v11 = 0;
      *(_QWORD *)(v8 + 3192) += v11;
    }
  }
  *a2 = *a1;
  *(_QWORD *)(*a1 + 8) = a2;
  result = *(_QWORD *)&SOS_PublicGlobals::sm_SpinlockStatSnapshot;
  *a1 = (volatile signed __int64)a2;
  *((_QWORD *)a2 + 1) = a1;
  ++*((_DWORD *)a1 + 6);
  *((_QWORD *)a2 + 2) = v4;
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v13 = rand();
    result = (unsigned int)(1717986919 * v13);
    if ( v13 == 5 * (v13 / 5) )
      result = Spinlock<19,1,268435714>::UpdateStatSnapshot();
  }
  *v2 = 0;
  return result;
}

```

## disassembly

```asm
0x100408160  push    rdi
0x100408162  push    r13
0x100408164  sub     rsp, 48h
0x100408168  mov     eax, gs:48h
0x100408170  lea     rdi, [rcx+10h]
0x100408174  mov     [rsp+58h+arg_18], rbx
0x100408179  xor     r13d, r13d
0x10040817c  mov     [rsp+58h+var_18], rbp
0x100408181  test    rcx, rcx
0x100408184  mov     [rsp+58h+var_28], r12
0x100408189  mov     ebx, r13d
0x10040818c  mov     [rsp+58h+var_30], r14
0x100408191  lea     r12, [rcx-60h]
0x100408195  mov     ebp, eax
0x100408197  cmovz   r12, r13
0x10040819b  mov     eax, [rdi]
0x10040819d  mov     r14, rcx
0x1004081a0  mov     [rsp+58h+var_38], r15
0x1004081a5  mov     r15, rdx
0x1004081a8  test    eax, eax
0x1004081aa  jnz     short loc_1004081C1
0x1004081ac  xor     eax, eax
0x1004081ae  lock cmpxchg [rdi], rbp
0x1004081b3  mov     eax, r13d
0x1004081b6  setz    al
0x1004081b9  test    eax, eax
0x1004081bb  jnz     loc_1004082A5
0x1004081c1  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004081c8  mov     [rsp+58h+var_20], rsi
0x1004081cd  mov     rsi, r13
0x1004081d0  mov     ecx, [rax]
0x1004081d2  and     ecx, 84h
0x1004081d8  cmp     cl, 84h
0x1004081db  jnz     short loc_100408239
0x1004081dd  mov     rdx, gs:58h
0x1004081e6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004081ed  mov     ecx, [rax]
0x1004081ef  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004081f6  mov     r8d, [rax]
0x1004081f9  add     r8, [rdx+rcx*8]
0x1004081fd  jz      short loc_10040820F
0x1004081ff  cmp     [r8+110h], r8
0x100408206  jnz     short loc_10040820F
0x100408208  mov     rsi, [r8+100h]
0x10040820f  test    rsi, rsi
0x100408212  jz      short loc_100408239
0x100408214  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040821b  cmp     [rax], ebx
0x10040821d  jz      short loc_100408231
0x10040821f  lea     rcx, [rsp+58h+PerformanceCount]; lpPerformanceCount
0x100408224  call    cs:__imp_QueryPerformanceCounter
0x10040822a  mov     rbx, qword ptr [rsp+58h+PerformanceCount]
0x10040822f  jmp     short loc_100408239
0x100408231  mov     rbx, ds:7FFE0008h
0x100408239  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100408240  mov     rcx, rdi
0x100408243  cmp     [rax+0C7h], r13b
0x10040824a  jge     short loc_100408259
0x10040824c  mov     r8, rbp
0x10040824f  mov     rdx, rsi
0x100408252  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100408257  jmp     short loc_100408261
0x100408259  mov     rdx, rbp
0x10040825c  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x100408261  test    rsi, rsi
0x100408264  jz      short loc_1004082A0
0x100408266  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040826d  cmp     [rax], r13d
0x100408270  jz      short loc_100408284
0x100408272  lea     rcx, [rsp+58h+arg_8]; lpPerformanceCount
0x100408277  call    cs:__imp_QueryPerformanceCounter
0x10040827d  mov     rax, qword ptr [rsp+58h+arg_8]
0x100408282  jmp     short loc_10040828C
0x100408284  mov     rax, ds:7FFE0008h
0x10040828c  mov     rcx, rax
0x10040828f  sub     rcx, rbx
0x100408292  cmp     rax, rbx
0x100408295  cmovb   rcx, r13
0x100408299  add     [rsi+0C78h], rcx
0x1004082a0  mov     rsi, [rsp+58h+var_20]
0x1004082a5  mov     rax, [r14]
0x1004082a8  mov     rbp, [rsp+58h+var_18]
0x1004082ad  mov     rbx, [rsp+58h+arg_18]
0x1004082b2  mov     [r15], rax
0x1004082b5  mov     rax, [r14]
0x1004082b8  mov     [rax+8], r15
0x1004082bc  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004082c3  mov     [r14], r15
0x1004082c6  mov     [r15+8], r14
0x1004082ca  inc     dword ptr [r14+18h]
0x1004082ce  mov     r14, [rsp+58h+var_30]
0x1004082d3  mov     [r15+10h], r12
0x1004082d7  mov     r15, [rsp+58h+var_38]
0x1004082dc  mov     r12, [rsp+58h+var_28]
0x1004082e1  cmp     [rax], r13b
0x1004082e4  jz      short loc_10040830D
0x1004082e6  call    cs:__imp_rand
0x1004082ec  mov     r8d, eax
0x1004082ef  mov     eax, 66666667h
0x1004082f4  imul    r8d
0x1004082f7  sar     edx, 1
0x1004082f9  mov     ecx, edx
0x1004082fb  shr     ecx, 1Fh
0x1004082fe  add     edx, ecx
0x100408300  lea     ecx, [rdx+rdx*4]
0x100408303  cmp     r8d, ecx
0x100408306  jnz     short loc_10040830D
0x100408308  call    ?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<19,1,268435714>::UpdateStatSnapshot(void)
0x10040830d  mov     [rdi], r13
0x100408310  add     rsp, 48h
0x100408314  pop     r13
0x100408316  pop     rdi
0x100408317  retn
```
