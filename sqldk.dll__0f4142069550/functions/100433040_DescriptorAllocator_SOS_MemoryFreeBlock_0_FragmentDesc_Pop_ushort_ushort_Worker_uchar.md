# DescriptorAllocator<SOS_MemoryFreeBlock,0>::FragmentDesc::Pop(ushort,ushort,Worker *,uchar *)

- ea: `0x100433040`
- end: `0x10043326e`
- name: `?Pop@FragmentDesc@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@QEAAPEAUPageDesc@2@GGPEAVWorker@@PEAE@Z`
- size: `558`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x100433280`
- `0x10049ba90`

## callees

- `0x100413dc0`
- `0x100426a00`
- `0x100433040`
- `0x1004360f0`
- `0x100437f40`
- `0x100438050`
- `0x100438120`
- `0x10049d8e0`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x1004331d3`
- `KERNEL32!InitializeSListHead` at `0x1004331d3`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049d4ac`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049d4ac`
- `KERNEL32!InterlockedPopEntrySList` at `0x10043308c`
- `KERNEL32!InterlockedPopEntrySList` at `0x10043308c`
- `KERNEL32!QueryPerformanceCounter` at `0x10043315a`
- `KERNEL32!QueryPerformanceCounter` at `0x10043315a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSLIST_ENTRY __fastcall DescriptorAllocator<SOS_MemoryFreeBlock,0>::FragmentDesc::Pop(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int16 v5; // r12
  int v7; // ebx
  PSLIST_ENTRY v8; // rbp
  PSLIST_ENTRY v9; // rax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r15
  __int64 v13; // r14
  __int64 v14; // rdx
  unsigned int v15; // esi
  __int64 v16; // r12
  LARGE_INTEGER v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rsi
  __int64 v20; // r14
  unsigned __int64 v21; // rax
  __int64 v23; // r8
  unsigned __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rcx
  _DWORD *v27; // [rsp+20h] [rbp-78h]
  unsigned __int64 v28; // [rsp+28h] [rbp-70h]
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-68h] BYREF
  __int64 v30; // [rsp+38h] [rbp-60h]
  _DWORD v31[2]; // [rsp+40h] [rbp-58h] BYREF
  char v32[80]; // [rsp+48h] [rbp-50h] BYREF

  v30 = -2;
  v5 = a3;
  v7 = 0;
  if ( a5 )
  {
    if ( a5 < *(_QWORD *)a1 || a5 >= *(_QWORD *)(a1 + 8) )
      return 0;
    v8 = DescriptorAllocator<SOS_MemoryFreeBlock,0>::FragmentDesc::PopWithAddr((union _SLIST_HEADER *)a1, a5);
  }
  else
  {
    v8 = 0;
    v9 = InterlockedPopEntrySList((PSLIST_HEADER)(a1 + 48));
    if ( v9 )
      v8 = v9 - 1;
  }
  if ( v8 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 32));
  }
  else
  {
    v10 = *(_QWORD *)(a1 + 64);
    if ( v10 )
    {
      v11 = *(_QWORD *)(a1 + 8);
      v28 = v11;
      if ( v10 < v11 )
      {
        while ( !_InterlockedExchange((volatile __int32 *)(a1 + 72), 1) )
        {
          v27 = (_DWORD *)(a1 + 72);
          v12 = *(_QWORD *)(a1 + 64);
          if ( !v12 || v12 >= v11 )
            goto LABEL_22;
          _mm_lfence();
          v13 = v5;
          v14 = *(_QWORD *)(a1 + 80) + 192LL * v5;
          v15 = *(_DWORD *)(v14 + 1388);
          if ( v15 == -1 )
          {
            if ( (SOS_OS_sm_osProcessStatus & 1) != 0 )
            {
              v23 = 40LL * v5;
              if ( *(_DWORD *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v23 + 24) )
              {
                _BitScanForward64(
                  &v24,
                  ~(*(unsigned __int64 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v23 + 8) - 1)
                & *(unsigned __int64 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v23 + 8));
                v15 = *((_DWORD *)SOS_OS::sm_AffinityToCPUInfo
                      + 64 * *(unsigned __int16 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v23 + 16)
                      + (unsigned int)v24);
                *(_DWORD *)(v14 + 1388) = v15;
              }
              else
              {
                v15 = 0;
                *(_DWORD *)(v14 + 1388) = 0;
              }
            }
            else
            {
              v15 = 0;
            }
          }
          LOBYTE(v7) = v5 != a2;
          AutoDisableWorkerStealing::AutoDisableWorkerStealing((AutoDisableWorkerStealing *)v32);
          v31[1] = v7;
          if ( v5 != a2 )
          {
            v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                + (unsigned int)SystemThread_TlsOffset;
            v26 = *(_QWORD *)(v25 + 256);
            if ( !v26 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v26 = *(_QWORD *)(v25 + 256);
            }
            *(_DWORD *)(v26 + 76) = v15;
            v31[0] = SystemThread::ChangeCPUId(*(SystemThread **)(v26 + 624), v15);
          }
          v16 = *(_QWORD *)(a1 + 80);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v17 = PerformanceCount;
          }
          else
          {
            v17.QuadPart = MEMORY[0x7FFE0008];
          }
          v18 = a4;
          if ( !a4 )
          {
            v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                + (unsigned int)SystemThread_TlsOffset;
            v18 = *(_QWORD *)(v19 + 256);
            if ( !v18 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v18 = *(_QWORD *)(v19 + 256);
            }
          }
          v20 = v16 + 16 * v13;
          *(_QWORD *)(v20 + 40) = v18;
          v5 = a3;
          if ( !(unsigned int)DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::CommitPage(
                                *(_QWORD *)(a1 + 80),
                                v12,
                                a3) )
            goto LABEL_21;
          _mm_lfence();
          v8 = (PSLIST_ENTRY)(v12 + 8128);
          InitializeSListHead((PSLIST_HEADER)(v12 + 8128));
          *(_QWORD *)(v12 + 8152) = v12;
          *(_QWORD *)(v12 + 8160) = -1;
          *(_WORD *)(v12 + 8172) = 64;
          *(_DWORD *)(v12 + 8176) = 3;
          *(_DWORD *)(v12 + 8168) = 127;
          *(_QWORD *)(v12 + 8184) = DescriptorAllocator<SOS_MemoryFreeBlock,0>::sm_initTimeStamp ^ *(_QWORD *)(a1 + 80);
          *(_WORD *)(v12 + 8172) = a3;
          v21 = 0;
          if ( v12 + 0x2000 != v28 )
            v21 = v12 + 0x2000;
          *(_QWORD *)(a1 + 64) = v21;
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 32));
          if ( !a5 )
          {
LABEL_21:
            ((void (__fastcall *)(_QWORD, _QWORD))DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd)(
              v20 + 40,
              (LARGE_INTEGER)v17.QuadPart);
            AutoCPUId::~AutoCPUId((AutoCPUId *)v31);
LABEL_22:
            *v27 = 0;
            return v8;
          }
          ((void (__fastcall *)(_QWORD, _QWORD))DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd)(
            v20 + 40,
            (LARGE_INTEGER)v17.QuadPart);
          if ( a5 >= v12 && a5 < v12 + 0x2000 )
          {
            AutoCPUId::~AutoCPUId((AutoCPUId *)v31);
            *v27 = 0;
            return v8;
          }
          _mm_lfence();
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
          InterlockedPushEntrySList((PSLIST_HEADER)(a1 + 48), (PSLIST_ENTRY)(v12 + 8144));
          v7 = 0;
          v8 = 0;
          AutoCPUId::~AutoCPUId((AutoCPUId *)v31);
          *v27 = 0;
          v11 = v28;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x100433040  mov     rax, rsp
0x100433043  mov     [rax+20h], r9
0x100433047  mov     [rax+18h], r8w
0x10043304c  mov     [rax+10h], dx
0x100433050  push    rbp
0x100433051  push    rsi
0x100433052  push    rdi
0x100433053  push    r12
0x100433055  push    r13
0x100433057  push    r14
0x100433059  push    r15
0x10043305b  sub     rsp, 60h
0x10043305f  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x100433067  mov     [rax+8], rbx
0x10043306b  movzx   r12d, r8w
0x10043306f  mov     rdi, rcx
0x100433072  xor     ebx, ebx
0x100433074  mov     r13, [rsp+98h+arg_20]
0x10043307c  test    r13, r13
0x10043307f  jnz     loc_10049D385
0x100433085  mov     rbp, rbx
0x100433088  add     rcx, 30h ; '0'; ListHead
0x10043308c  call    cs:__imp_InterlockedPopEntrySList
0x100433092  test    rax, rax
0x100433095  jnz     loc_10042EC58
0x10043309b  test    rbp, rbp
0x10043309e  jnz     loc_10042EC62
0x1004330a4  mov     rax, [rdi+40h]
0x1004330a8  test    rax, rax
0x1004330ab  jz      loc_100433253
0x1004330b1  mov     rdx, [rdi+8]
0x1004330b5  mov     [rsp+98h+var_70], rdx
0x1004330ba  cmp     rax, rdx
0x1004330bd  jnb     loc_100433253
0x1004330c3  lea     r9, ?sm_SOSNodeInfo@SOS_PublicGlobals@@2PAVSOS_NodeInfo@@A; SOS_NodeInfo near * SOS_PublicGlobals::sm_SOSNodeInfo
0x1004330ca  lea     rcx, [rdi+48h]
0x1004330ce  mov     eax, 1
0x1004330d3  xchg    eax, [rcx]
0x1004330d5  test    eax, eax
0x1004330d7  jnz     loc_100433253
0x1004330dd  mov     [rsp+98h+var_78], rcx
0x1004330e2  mov     r15, [rdi+40h]
0x1004330e6  test    r15, r15
0x1004330e9  jz      loc_10043324C
0x1004330ef  cmp     r15, rdx
0x1004330f2  jnb     loc_10043324C
0x1004330f8  lfence
0x1004330fb  movzx   r14d, r12w
0x1004330ff  lea     rdx, [r14+r14*2]
0x100433103  shl     rdx, 6
0x100433107  add     rdx, [rdi+50h]
0x10043310b  mov     esi, [rdx+56Ch]
0x100433111  cmp     esi, 0FFFFFFFFh
0x100433114  jz      loc_10049D3A9
0x10043311a  cmp     r12w, [rsp+98h+arg_8]
0x100433123  setnz   bl
0x100433126  lea     rcx, [rsp+98h+var_50]; this
0x10043312b  call    ??0AutoDisableWorkerStealing@@QEAA@XZ; AutoDisableWorkerStealing::AutoDisableWorkerStealing(void)
0x100433130  nop
0x100433131  mov     [rsp+98h+var_54], ebx
0x100433135  cmp     r12w, [rsp+98h+arg_8]
0x10043313e  jnz     loc_10049D419
0x100433144  mov     r12, [rdi+50h]
0x100433148  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10043314f  jz      loc_10049D465
0x100433155  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x10043315a  call    cs:__imp_QueryPerformanceCounter
0x100433160  mov     rbx, qword ptr [rsp+98h+PerformanceCount]
0x100433165  jmp     short loc_100433168
0x100433168  mov     rax, [rsp+98h+arg_18]
0x100433170  test    rax, rax
0x100433173  jnz     short loc_10043319E
0x100433175  mov     rcx, gs:58h
0x10043317e  mov     eax, cs:_tls_index
0x100433184  mov     esi, cs:SystemThread_TlsOffset
0x10043318a  add     rsi, [rcx+rax*8]
0x10043318e  mov     rax, [rsi+100h]
0x100433195  test    rax, rax
0x100433198  jz      loc_10049D473
0x10043319e  shl     r14, 4
0x1004331a2  add     r14, r12
0x1004331a5  mov     [r14+28h], rax
0x1004331a9  movzx   r12d, [rsp+98h+arg_10]
0x1004331b2  movzx   r8d, r12w
0x1004331b6  mov     rdx, r15
0x1004331b9  mov     rcx, [rdi+50h]
0x1004331bd  call    ?CommitPage@FragmentDesc@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@SAHPEAV2@PEAEG@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::CommitPage(DescriptorAllocator<SOS_ParentBlockDescriptor,0> *,uchar *,ushort)
0x1004331c2  test    eax, eax
0x1004331c4  jz      short loc_100433233
0x1004331c6  lfence
0x1004331c9  lea     rbp, [r15+1FC0h]
0x1004331d0  mov     rcx, rbp; ListHead
0x1004331d3  call    cs:__imp_InitializeSListHead
0x1004331d9  mov     [rbp+18h], r15
0x1004331dd  mov     qword ptr [rbp+20h], 0FFFFFFFFFFFFFFFFh
0x1004331e5  mov     eax, 40h ; '@'
0x1004331ea  mov     [rbp+2Ch], ax
0x1004331ee  mov     dword ptr [rbp+30h], 3
0x1004331f5  mov     dword ptr [rbp+28h], 7Fh
0x1004331fc  mov     rax, [rdi+50h]
0x100433200  xor     rax, cs:?sm_initTimeStamp@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@0_KA; unsigned __int64 DescriptorAllocator<SOS_MemoryFreeBlock,0>::sm_initTimeStamp
0x100433207  mov     [rbp+38h], rax
0x10043320b  mov     [rbp+2Ch], r12w
0x100433210  lea     rsi, [r15+2000h]
0x100433217  xor     eax, eax
0x100433219  cmp     rsi, [rsp+98h+var_70]
0x10043321e  cmovnz  rax, rsi
0x100433222  mov     [rdi+40h], rax
0x100433226  lock dec dword ptr [rdi+20h]
0x10043322a  test    r13, r13
0x10043322d  jnz     loc_10049D487
0x100433233  mov     rdx, rbx
0x100433236  lea     rcx, [r14+28h]
0x10043323a  call    ?RecordAllocationEnd@AllocationTrace@DiagnosticInfo@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAXV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd(SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10043323f  nop
0x100433240  lea     rcx, [rsp+98h+var_58]; this
0x100433245  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x10043324a  xor     ebx, ebx
0x10043324c  mov     rax, [rsp+98h+var_78]
0x100433251  mov     [rax], ebx
0x100433253  mov     rax, rbp
0x100433256  mov     rbx, [rsp+98h+arg_0]
0x10043325e  add     rsp, 60h
0x100433262  pop     r15
0x100433264  pop     r14
0x100433266  pop     r13
0x100433268  pop     r12
0x10043326a  pop     rdi
0x10043326b  pop     rsi
0x10043326c  pop     rbp
0x10043326d  retn
0x10042ec58  lea     rbp, [rax-10h]
0x10042ec5c  jmp     loc_10043309B
0x10042ec62  lock dec dword ptr [rdi+20h]
0x10042ec66  jmp     loc_100433253
0x10049d385  cmp     r13, [rcx]
0x10049d388  jb      short loc_10049D3A0
0x10049d38a  cmp     r13, [rcx+8]
0x10049d38e  jnb     short loc_10049D3A0
0x10049d390  mov     rdx, r13
0x10049d393  call    ?PopWithAddr@FragmentDesc@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@QEAAPEAUPageDesc@2@PEAE@Z; DescriptorAllocator<SOS_MemoryFreeBlock,0>::FragmentDesc::PopWithAddr(uchar *)
0x10049d398  mov     rbp, rax
0x10049d39b  jmp     loc_10043309B
0x10049d3a0  mov     rax, rbx
0x10049d3a3  jmp     loc_100433256
0x10049d3a9  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x10049d3b0  jz      short loc_10049D411
0x10049d3b2  lea     rax, [r14+r14*4]
0x10049d3b6  lea     r8, ds:0[rax*8]
0x10049d3be  cmp     dword ptr [r8+r9+18h], 0
0x10049d3c4  jz      short loc_10049D404
0x10049d3c6  mov     rcx, [r8+r9+8]
0x10049d3cb  lea     rax, [rcx-1]
0x10049d3cf  not     rax
0x10049d3d2  and     rcx, rax
0x10049d3d5  bsf     rax, rcx
0x10049d3d9  mov     dword ptr [rsp+98h+arg_20], eax
0x10049d3e0  movzx   ecx, word ptr [r8+r9+10h]
0x10049d3e6  shl     rcx, 6
0x10049d3ea  add     rcx, rax
0x10049d3ed  mov     ecx, ecx
0x10049d3ef  mov     rax, cs:?sm_AffinityToCPUInfo@SOS_OS@@0PEAKEA; ulong * SOS_OS::sm_AffinityToCPUInfo
0x10049d3f6  mov     esi, [rax+rcx*4]
0x10049d3f9  mov     [rdx+56Ch], esi
0x10049d3ff  jmp     loc_10043311A
0x10049d404  mov     esi, ebx
0x10049d406  mov     [rdx+56Ch], ebx
0x10049d40c  jmp     loc_10043311A
0x10049d411  mov     esi, ebx
0x10049d413  jmp     loc_10043311A
0x10049d419  mov     rcx, gs:58h
0x10049d422  mov     eax, cs:_tls_index
0x10049d428  mov     ebx, cs:SystemThread_TlsOffset
0x10049d42e  add     rbx, [rcx+rax*8]
0x10049d432  mov     rcx, [rbx+100h]; void *
0x10049d439  test    rcx, rcx
0x10049d43c  jnz     short loc_10049D44A
0x10049d43e  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049d443  mov     rcx, [rbx+100h]
0x10049d44a  mov     [rcx+4Ch], esi
0x10049d44d  mov     edx, esi; unsigned int
0x10049d44f  mov     rcx, [rcx+270h]; this
0x10049d456  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x10049d45b  mov     [rsp+98h+var_58], eax
0x10049d45f  jmp     loc_100433144
0x10049d465  mov     rbx, ds:7FFE0008h
0x10049d46d  jmp     loc_100433168
0x10049d473  xor     ecx, ecx; void *
0x10049d475  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049d47a  mov     rax, [rsi+100h]
0x10049d481  jmp     loc_10043319E
0x10049d487  mov     rdx, rbx
0x10049d48a  lea     rcx, [r14+28h]
0x10049d48e  call    ?RecordAllocationEnd@AllocationTrace@DiagnosticInfo@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAXV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd(SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10049d493  cmp     r13, r15
0x10049d496  jb      short loc_10049D49D
0x10049d498  cmp     r13, rsi
0x10049d49b  jb      short loc_10049D4D2
0x10049d49d  lfence
0x10049d4a0  lock inc dword ptr [rdi+20h]
0x10049d4a4  lea     rdx, [rbp+10h]; ListEntry
0x10049d4a8  lea     rcx, [rdi+30h]; ListHead
0x10049d4ac  call    cs:__imp_InterlockedPushEntrySList
0x10049d4b2  xor     ebx, ebx
0x10049d4b4  mov     ebp, ebx
0x10049d4b6  lea     rcx, [rsp+98h+var_58]; this
0x10049d4bb  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x10049d4c0  nop
0x10049d4c1  mov     rax, [rsp+98h+var_78]
0x10049d4c6  mov     [rax], ebx
0x10049d4c8  mov     rdx, [rsp+98h+var_70]
0x10049d4cd  jmp     loc_1004330C3
0x10049d4d2  lea     rcx, [rsp+98h+var_58]; this
0x10049d4d7  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x10049d4dc  nop
0x10049d4dd  mov     rax, [rsp+98h+var_78]
0x10049d4e2  mov     dword ptr [rax], 0
0x10049d4e8  jmp     loc_100433253
```
