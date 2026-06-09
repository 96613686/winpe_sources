# DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::Pop(ushort,ushort,Worker *,uchar *)

- ea: `0x1004381b0`
- end: `0x10043843a`
- name: `?Pop@FragmentDesc@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAPEAUPageDesc@2@GGPEAVWorker@@PEAE@Z`
- size: `650`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x100438440`
- `0x10049c010`

## callees

- `0x100413dc0`
- `0x100426a00`
- `0x1004360f0`
- `0x100437f40`
- `0x100438050`
- `0x100438120`
- `0x1004381b0`
- `0x10049d5d0`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x100438347`
- `KERNEL32!InitializeSListHead` at `0x100438395`
- `KERNEL32!InitializeSListHead` at `0x10043839f`
- `KERNEL32!InitializeSListHead` at `0x100438347`
- `KERNEL32!InitializeSListHead` at `0x100438395`
- `KERNEL32!InitializeSListHead` at `0x10043839f`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049d0b1`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049d0b1`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004381fc`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004381fc`
- `KERNEL32!QueryPerformanceCounter` at `0x1004382ca`
- `KERNEL32!QueryPerformanceCounter` at `0x1004382ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSLIST_ENTRY __fastcall DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::Pop(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  __int64 v5; // r8
  unsigned __int64 v6; // rax
  unsigned __int16 v7; // r12
  int v9; // ebx
  PSLIST_ENTRY v10; // rsi
  PSLIST_ENTRY v11; // rax
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // r14
  __int64 v15; // r15
  __int64 v16; // rdx
  unsigned int v17; // edi
  __int64 v18; // r12
  LARGE_INTEGER v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // r15
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rax
  __int64 v26; // rbx
  __int64 v27; // rcx
  _DWORD *v28; // [rsp+20h] [rbp-78h]
  unsigned __int64 v29; // [rsp+28h] [rbp-70h]
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-68h] BYREF
  __int64 v31; // [rsp+38h] [rbp-60h]
  _DWORD v32[2]; // [rsp+40h] [rbp-58h] BYREF
  char v33[80]; // [rsp+48h] [rbp-50h] BYREF

  v31 = -2;
  v7 = a3;
  v9 = 0;
  if ( a5 )
  {
    if ( a5 < *(_QWORD *)a1 || a5 >= *(_QWORD *)(a1 + 8) )
      return 0;
    v10 = DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::PopWithAddr((union _SLIST_HEADER *)a1, a5);
  }
  else
  {
    v10 = 0;
    v11 = InterlockedPopEntrySList((PSLIST_HEADER)(a1 + 48));
    if ( v11 )
      v10 = v11 - 1;
  }
  if ( v10 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 32));
  }
  else
  {
    v12 = *(_QWORD *)(a1 + 64);
    if ( v12 )
    {
      v13 = *(_QWORD *)(a1 + 8);
      v29 = v13;
      if ( v12 < v13 )
      {
        while ( !_InterlockedExchange((volatile __int32 *)(a1 + 72), 1) )
        {
          v28 = (_DWORD *)(a1 + 72);
          v14 = *(_QWORD *)(a1 + 64);
          if ( !v14 || v14 >= v13 )
            goto LABEL_25;
          _mm_lfence();
          v15 = v7;
          v16 = *(_QWORD *)(a1 + 80) + 192LL * v7;
          v17 = *(_DWORD *)(v16 + 1388);
          if ( v17 == -1 )
          {
            if ( (SOS_OS_sm_osProcessStatus & 1) != 0 )
            {
              v5 = 40LL * v7;
              if ( *(_DWORD *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v5 + 24) )
              {
                _BitScanForward64(
                  &v6,
                  ~(*(unsigned __int64 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v5 + 8) - 1)
                & *(unsigned __int64 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v5 + 8));
                v17 = *((_DWORD *)SOS_OS::sm_AffinityToCPUInfo
                      + 64 * *(unsigned __int16 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v5 + 16)
                      + (unsigned int)v6);
                *(_DWORD *)(v16 + 1388) = v17;
              }
              else
              {
                v17 = 0;
                *(_DWORD *)(v16 + 1388) = 0;
              }
            }
            else
            {
              v17 = 0;
            }
          }
          LOBYTE(v9) = v7 != a2;
          AutoDisableWorkerStealing::AutoDisableWorkerStealing((AutoDisableWorkerStealing *)v33);
          v32[1] = v9;
          if ( v7 != a2 )
          {
            v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                + (unsigned int)SystemThread_TlsOffset;
            v27 = *(_QWORD *)(v26 + 256);
            if ( !v27 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v27 = *(_QWORD *)(v26 + 256);
            }
            *(_DWORD *)(v27 + 76) = v17;
            v32[0] = SystemThread::ChangeCPUId(*(SystemThread **)(v27 + 624), v17);
          }
          v18 = *(_QWORD *)(a1 + 80);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v19 = PerformanceCount;
          }
          else
          {
            v19.QuadPart = MEMORY[0x7FFE0008];
          }
          v20 = a4;
          if ( !a4 )
          {
            v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                + (unsigned int)SystemThread_TlsOffset;
            v20 = *(_QWORD *)(v21 + 256);
            if ( !v20 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v20 = *(_QWORD *)(v21 + 256);
            }
          }
          v22 = v18 + 16 * v15;
          *(_QWORD *)(v22 + 40) = v20;
          v7 = a3;
          if ( !(unsigned int)DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::CommitPage(
                                *(_QWORD *)(a1 + 80),
                                v14,
                                a3) )
            goto LABEL_24;
          _mm_lfence();
          v10 = (PSLIST_ENTRY)(v14 + 8064);
          InitializeSListHead((PSLIST_HEADER)(v14 + 8064));
          *(_QWORD *)(v14 + 8088) = v14;
          *(_QWORD *)(v14 + 8096) = -1;
          *(_WORD *)(v14 + 8108) = 64;
          *(_DWORD *)(v14 + 8112) = 3;
          *(_DWORD *)(v14 + 8104) = 56;
          if ( v14 < v14 + 8064 )
          {
            v23 = v14 + 8;
            do
            {
              *(_QWORD *)(v23 - 8) = 0;
              *(_QWORD *)v23 = 0;
              *(_QWORD *)(v23 + 8) = 0;
              *(_QWORD *)(v23 + 16) = 0;
              InitializeSListHead((PSLIST_HEADER)(v23 + 104));
              InitializeSListHead((PSLIST_HEADER)(v23 + 120));
              v23 += 144LL;
            }
            while ( v23 - 8 < (unsigned __int64)v10 );
          }
          *(_QWORD *)(v14 + 8120) = DescriptorAllocator<SOS_ParentBlockDescriptor,0>::sm_initTimeStamp
                                  ^ *(_QWORD *)(a1 + 80);
          *(_WORD *)(v14 + 8108) = a3;
          v24 = 0;
          if ( v14 + 0x2000 != v29 )
            v24 = v14 + 0x2000;
          *(_QWORD *)(a1 + 64) = v24;
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 32));
          if ( !a5 )
          {
LABEL_24:
            ((void (__fastcall *)(_QWORD, _QWORD))DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd)(
              v22 + 40,
              (LARGE_INTEGER)v19.QuadPart);
            AutoCPUId::~AutoCPUId((AutoCPUId *)v32);
LABEL_25:
            *v28 = 0;
            return v10;
          }
          ((void (__fastcall *)(_QWORD, _QWORD))DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd)(
            v22 + 40,
            (LARGE_INTEGER)v19.QuadPart);
          if ( a5 >= v14 && a5 < v14 + 0x2000 )
          {
            AutoCPUId::~AutoCPUId((AutoCPUId *)v32);
            *v28 = 0;
            return v10;
          }
          _mm_lfence();
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
          InterlockedPushEntrySList((PSLIST_HEADER)(a1 + 48), (PSLIST_ENTRY)(v14 + 8080));
          v9 = 0;
          v10 = 0;
          AutoCPUId::~AutoCPUId((AutoCPUId *)v32);
          *v28 = 0;
          v13 = v29;
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1004381b0  mov     rax, rsp
0x1004381b3  mov     [rax+20h], r9
0x1004381b7  mov     [rax+18h], r8w
0x1004381bc  mov     [rax+10h], dx
0x1004381c0  push    rbp
0x1004381c1  push    rsi
0x1004381c2  push    rdi
0x1004381c3  push    r12
0x1004381c5  push    r13
0x1004381c7  push    r14
0x1004381c9  push    r15
0x1004381cb  sub     rsp, 60h
0x1004381cf  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x1004381d7  mov     [rax+8], rbx
0x1004381db  movzx   r12d, r8w
0x1004381df  mov     rbp, rcx
0x1004381e2  xor     ebx, ebx
0x1004381e4  mov     r13, [rsp+98h+arg_20]
0x1004381ec  test    r13, r13
0x1004381ef  jnz     loc_10049CFE5
0x1004381f5  mov     rsi, rbx
0x1004381f8  add     rcx, 30h ; '0'; ListHead
0x1004381fc  call    cs:__imp_InterlockedPopEntrySList
0x100438202  test    rax, rax
0x100438205  jnz     loc_1004386A9
0x10043820b  test    rsi, rsi
0x10043820e  jnz     loc_10043840F
0x100438214  mov     rax, [rbp+40h]
0x100438218  test    rax, rax
0x10043821b  jz      loc_100438416
0x100438221  mov     rdx, [rbp+8]
0x100438225  mov     [rsp+98h+var_70], rdx
0x10043822a  cmp     rax, rdx
0x10043822d  jnb     loc_100438416
0x100438233  lea     r9, ?sm_SOSNodeInfo@SOS_PublicGlobals@@2PAVSOS_NodeInfo@@A; SOS_NodeInfo near * SOS_PublicGlobals::sm_SOSNodeInfo
0x10043823a  lea     rcx, [rbp+48h]
0x10043823e  mov     eax, 1
0x100438243  xchg    eax, [rcx]
0x100438245  test    eax, eax
0x100438247  jnz     loc_100438416
0x10043824d  mov     [rsp+98h+var_78], rcx
0x100438252  mov     r14, [rbp+40h]
0x100438256  test    r14, r14
0x100438259  jz      loc_100438405
0x10043825f  cmp     r14, rdx
0x100438262  jnb     loc_100438405
0x100438268  lfence
0x10043826b  movzx   r15d, r12w
0x10043826f  lea     rdx, [r15+r15*2]
0x100438273  shl     rdx, 6
0x100438277  add     rdx, [rbp+50h]
0x10043827b  mov     edi, [rdx+56Ch]
0x100438281  cmp     edi, 0FFFFFFFFh
0x100438284  jz      loc_100426C21
0x10043828a  cmp     r12w, [rsp+98h+arg_8]
0x100438293  setnz   bl
0x100438296  lea     rcx, [rsp+98h+var_50]; this
0x10043829b  call    ??0AutoDisableWorkerStealing@@QEAA@XZ; AutoDisableWorkerStealing::AutoDisableWorkerStealing(void)
0x1004382a0  nop
0x1004382a1  mov     [rsp+98h+var_54], ebx
0x1004382a5  cmp     r12w, [rsp+98h+arg_8]
0x1004382ae  jnz     loc_10049D01E
0x1004382b4  mov     r12, [rbp+50h]
0x1004382b8  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004382bf  jz      loc_10049D06A
0x1004382c5  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x1004382ca  call    cs:__imp_QueryPerformanceCounter
0x1004382d0  mov     rbx, qword ptr [rsp+98h+PerformanceCount]
0x1004382d5  jmp     short loc_1004382D8
0x1004382d8  mov     rax, [rsp+98h+arg_18]
0x1004382e0  test    rax, rax
0x1004382e3  jnz     short loc_10043830E
0x1004382e5  mov     rcx, gs:58h
0x1004382ee  mov     eax, cs:_tls_index
0x1004382f4  mov     edi, cs:SystemThread_TlsOffset
0x1004382fa  add     rdi, [rcx+rax*8]
0x1004382fe  mov     rax, [rdi+100h]
0x100438305  test    rax, rax
0x100438308  jz      loc_10049D078
0x10043830e  shl     r15, 4
0x100438312  add     r15, r12
0x100438315  mov     [r15+28h], rax
0x100438319  movzx   r12d, [rsp+98h+arg_10]
0x100438322  movzx   r8d, r12w
0x100438326  mov     rdx, r14
0x100438329  mov     rcx, [rbp+50h]
0x10043832d  call    ?CommitPage@FragmentDesc@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@SAHPEAV2@PEAEG@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::CommitPage(DescriptorAllocator<SOS_ParentBlockDescriptor,0> *,uchar *,ushort)
0x100438332  test    eax, eax
0x100438334  jz      loc_1004383EC
0x10043833a  lfence
0x10043833d  lea     rsi, [r14+1F80h]
0x100438344  mov     rcx, rsi; ListHead
0x100438347  call    cs:__imp_InitializeSListHead
0x10043834d  mov     [rsi+18h], r14
0x100438351  mov     qword ptr [rsi+20h], 0FFFFFFFFFFFFFFFFh
0x100438359  mov     eax, 40h ; '@'
0x10043835e  mov     [rsi+2Ch], ax
0x100438362  mov     dword ptr [rsi+30h], 3
0x100438369  mov     dword ptr [rsi+28h], 38h ; '8'
0x100438370  cmp     r14, rsi
0x100438373  jnb     short loc_1004383B5
0x100438375  lea     rdi, [r14+8]
0x100438379  nop     dword ptr [rax+00000000h]
0x100438380  xor     eax, eax
0x100438382  mov     [rdi-8], rax
0x100438386  mov     [rdi], rax
0x100438389  mov     [rdi+8], rax
0x10043838d  mov     [rdi+10h], rax
0x100438391  lea     rcx, [rdi+68h]; ListHead
0x100438395  call    cs:__imp_InitializeSListHead
0x10043839b  lea     rcx, [rdi+78h]; ListHead
0x10043839f  call    cs:__imp_InitializeSListHead
0x1004383a5  lea     rdi, [rdi+90h]
0x1004383ac  lea     rax, [rdi-8]
0x1004383b0  cmp     rax, rsi
0x1004383b3  jb      short loc_100438380
0x1004383b5  mov     rax, [rbp+50h]
0x1004383b9  xor     rax, cs:?sm_initTimeStamp@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@0_KA; unsigned __int64 DescriptorAllocator<SOS_ParentBlockDescriptor,0>::sm_initTimeStamp
0x1004383c0  mov     [rsi+38h], rax
0x1004383c4  mov     [rsi+2Ch], r12w
0x1004383c9  lea     rdi, [r14+2000h]
0x1004383d0  xor     eax, eax
0x1004383d2  cmp     rdi, [rsp+98h+var_70]
0x1004383d7  cmovnz  rax, rdi
0x1004383db  mov     [rbp+40h], rax
0x1004383df  lock dec dword ptr [rbp+20h]
0x1004383e3  test    r13, r13
0x1004383e6  jnz     loc_10049D08C
0x1004383ec  mov     rdx, rbx
0x1004383ef  lea     rcx, [r15+28h]
0x1004383f3  call    ?RecordAllocationEnd@AllocationTrace@DiagnosticInfo@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAXV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd(SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004383f8  nop
0x1004383f9  lea     rcx, [rsp+98h+var_58]; this
0x1004383fe  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x100438403  xor     ebx, ebx
0x100438405  mov     rax, [rsp+98h+var_78]
0x10043840a  mov     [rax], ebx
0x10043840c  jmp     short loc_100438416
0x10043840f  lock dec dword ptr [rbp+20h]
0x100438413  jmp     short loc_100438416
0x100438416  mov     rax, rsi
0x100438419  jmp     short loc_100438422
0x10043841c  mov     rax, rbx
0x10043841f  jmp     short loc_100438422
0x100438422  mov     rbx, [rsp+98h+arg_0]
0x10043842a  add     rsp, 60h
0x10043842e  pop     r15
0x100438430  pop     r14
0x100438432  pop     r13
0x100438434  pop     r12
0x100438436  pop     rdi
0x100438437  pop     rsi
0x100438438  pop     rbp
0x100438439  retn
0x100426c21  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x100426c28  jz      loc_10049D016
0x100426c2e  lea     rax, [r15+r15*4]
0x100426c32  lea     r8, ds:0[rax*8]
0x100426c3a  cmp     dword ptr [r8+r9+18h], 0
0x100426c40  jz      loc_10049D009
0x100426c46  mov     rcx, [r8+r9+8]
0x100426c4b  lea     rax, [rcx-1]
0x100426c4f  not     rax
0x100426c52  and     rcx, rax
0x100426c55  bsf     rax, rcx
0x100426c59  mov     dword ptr [rsp+98h+arg_20], eax
0x100426c60  movzx   ecx, word ptr [r8+r9+10h]
0x100426c66  shl     rcx, 6
0x100426c6a  add     rcx, rax
0x100426c6d  mov     ecx, ecx
0x100426c6f  mov     rax, cs:?sm_AffinityToCPUInfo@SOS_OS@@0PEAKEA; ulong * SOS_OS::sm_AffinityToCPUInfo
0x100426c76  mov     edi, [rax+rcx*4]
0x100426c79  mov     [rdx+56Ch], edi
0x100426c7f  jmp     loc_10043828A
0x1004386a9  lea     rsi, [rax-10h]
0x1004386ad  jmp     loc_10043820B
0x10049cfe5  cmp     r13, [rcx]
0x10049cfe8  jb      loc_10043841C
0x10049cfee  cmp     r13, [rcx+8]
0x10049cff2  jnb     loc_10043841C
0x10049cff8  mov     rdx, r13
0x10049cffb  call    ?PopWithAddr@FragmentDesc@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAPEAUPageDesc@2@PEAE@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::PopWithAddr(uchar *)
0x10049d000  mov     rsi, rax
0x10049d003  jmp     loc_10043820B
0x10049d009  mov     edi, ebx
0x10049d00b  mov     [rdx+56Ch], ebx
0x10049d011  jmp     loc_10043828A
0x10049d016  mov     edi, ebx
0x10049d018  jmp     loc_10043828A
0x10049d01e  mov     rcx, gs:58h
0x10049d027  mov     eax, cs:_tls_index
0x10049d02d  mov     ebx, cs:SystemThread_TlsOffset
0x10049d033  add     rbx, [rcx+rax*8]
0x10049d037  mov     rcx, [rbx+100h]; void *
0x10049d03e  test    rcx, rcx
0x10049d041  jnz     short loc_10049D04F
0x10049d043  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049d048  mov     rcx, [rbx+100h]
0x10049d04f  mov     [rcx+4Ch], edi
0x10049d052  mov     edx, edi; unsigned int
0x10049d054  mov     rcx, [rcx+270h]; this
0x10049d05b  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x10049d060  mov     [rsp+98h+var_58], eax
0x10049d064  jmp     loc_1004382B4
0x10049d06a  mov     rbx, ds:7FFE0008h
0x10049d072  jmp     loc_1004382D8
0x10049d078  xor     ecx, ecx; void *
0x10049d07a  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049d07f  mov     rax, [rdi+100h]
0x10049d086  jmp     loc_10043830E
0x10049d08c  mov     rdx, rbx
0x10049d08f  lea     rcx, [r15+28h]
0x10049d093  call    ?RecordAllocationEnd@AllocationTrace@DiagnosticInfo@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAXV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd(SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10049d098  cmp     r13, r14
0x10049d09b  jb      short loc_10049D0A2
0x10049d09d  cmp     r13, rdi
0x10049d0a0  jb      short loc_10049D0D7
0x10049d0a2  lfence
0x10049d0a5  lock inc dword ptr [rbp+20h]
0x10049d0a9  lea     rdx, [rsi+10h]; ListEntry
0x10049d0ad  lea     rcx, [rbp+30h]; ListHead
0x10049d0b1  call    cs:__imp_InterlockedPushEntrySList
0x10049d0b7  xor     ebx, ebx
0x10049d0b9  mov     esi, ebx
0x10049d0bb  lea     rcx, [rsp+98h+var_58]; this
0x10049d0c0  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x10049d0c5  nop
0x10049d0c6  mov     rax, [rsp+98h+var_78]
0x10049d0cb  mov     [rax], ebx
0x10049d0cd  mov     rdx, [rsp+98h+var_70]
0x10049d0d2  jmp     loc_100438233
0x10049d0d7  lea     rcx, [rsp+98h+var_58]; this
0x10049d0dc  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x10049d0e1  nop
0x10049d0e2  mov     rax, [rsp+98h+var_78]
0x10049d0e7  mov     dword ptr [rax], 0
0x10049d0ed  jmp     loc_100438416
```
