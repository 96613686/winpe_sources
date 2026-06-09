# DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::FragmentDesc::Pop(ushort,ushort,Worker *,uchar *)

- ea: `0x1004a8d70`
- end: `0x1004a90d1`
- name: `?Pop@FragmentDesc@?$DescriptorAllocator@VSOS_TopLevelBlockDescriptor@@$0A@@@QEAAPEAUPageDesc@2@GGPEAVWorker@@PEAE@Z`
- size: `865`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1004a8200`
- `0x1004a8460`

## callees

- `0x100413dc0`
- `0x100426a00`
- `0x1004360f0`
- `0x100437f40`
- `0x100438050`
- `0x100438120`
- `0x10049d8e0`
- `0x1004a8d70`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x1004a8fd7`
- `KERNEL32!InitializeSListHead` at `0x1004a8fd7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a9058`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a9058`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a8dd8`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a8dd8`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a8f49`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a8f49`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSLIST_ENTRY __fastcall DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::FragmentDesc::Pop(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int16 v5; // r12
  int v7; // ebx
  PSLIST_ENTRY v8; // rbp
  PSLIST_ENTRY v10; // rax
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r15
  __int64 v14; // r14
  __int64 v15; // rdx
  unsigned int v16; // esi
  __int64 v17; // r8
  unsigned __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // r12
  LARGE_INTEGER v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // r14
  unsigned __int64 v26; // rax
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
    v10 = InterlockedPopEntrySList((PSLIST_HEADER)(a1 + 48));
    if ( v10 )
      v8 = v10 - 1;
  }
  if ( v8 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 32));
  }
  else
  {
    v11 = *(_QWORD *)(a1 + 64);
    if ( v11 )
    {
      v12 = *(_QWORD *)(a1 + 8);
      v28 = v12;
      if ( v11 < v12 )
      {
        while ( !_InterlockedExchange((volatile __int32 *)(a1 + 72), 1) )
        {
          v27 = (_DWORD *)(a1 + 72);
          v13 = *(_QWORD *)(a1 + 64);
          if ( !v13 || v13 >= v12 )
            goto LABEL_40;
          _mm_lfence();
          v14 = v5;
          v15 = *(_QWORD *)(a1 + 80) + 192LL * v5;
          v16 = *(_DWORD *)(v15 + 1388);
          if ( v16 == -1 )
          {
            if ( (SOS_OS_sm_osProcessStatus & 1) != 0 )
            {
              v17 = 40LL * v5;
              if ( *(_DWORD *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v17 + 24) )
              {
                _BitScanForward64(
                  &v18,
                  ~(*(unsigned __int64 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v17 + 8) - 1)
                & *(unsigned __int64 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v17 + 8));
                v16 = *((_DWORD *)SOS_OS::sm_AffinityToCPUInfo
                      + 64 * *(unsigned __int16 *)((char *)&SOS_PublicGlobals::sm_SOSNodeInfo + v17 + 16)
                      + (unsigned int)v18);
                *(_DWORD *)(v15 + 1388) = v16;
              }
              else
              {
                v16 = 0;
                *(_DWORD *)(v15 + 1388) = 0;
              }
            }
            else
            {
              v16 = 0;
            }
          }
          LOBYTE(v7) = v5 != a2;
          AutoDisableWorkerStealing::AutoDisableWorkerStealing((AutoDisableWorkerStealing *)v32);
          v31[1] = v7;
          if ( v5 != a2 )
          {
            v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                + (unsigned int)SystemThread_TlsOffset;
            v20 = *(_QWORD *)(v19 + 256);
            if ( !v20 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v20 = *(_QWORD *)(v19 + 256);
            }
            *(_DWORD *)(v20 + 76) = v16;
            v31[0] = SystemThread::ChangeCPUId(*(SystemThread **)(v20 + 624), v16);
          }
          v21 = *(_QWORD *)(a1 + 80);
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v22 = PerformanceCount;
          }
          else
          {
            v22.QuadPart = MEMORY[0x7FFE0008];
          }
          v23 = a4;
          if ( !a4 )
          {
            v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                + (unsigned int)SystemThread_TlsOffset;
            v23 = *(_QWORD *)(v24 + 256);
            if ( !v23 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v23 = *(_QWORD *)(v24 + 256);
            }
          }
          v25 = v21 + 16 * v14;
          *(_QWORD *)(v25 + 40) = v23;
          v5 = a3;
          if ( !(unsigned int)DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::CommitPage(
                                *(_QWORD *)(a1 + 80),
                                v13,
                                a3) )
            goto LABEL_39;
          _mm_lfence();
          v8 = (PSLIST_ENTRY)(v13 + 8128);
          InitializeSListHead((PSLIST_HEADER)(v13 + 8128));
          *(_QWORD *)(v13 + 8152) = v13;
          *(_QWORD *)(v13 + 8160) = -1;
          *(_WORD *)(v13 + 8172) = 64;
          *(_DWORD *)(v13 + 8176) = 3;
          *(_DWORD *)(v13 + 8168) = 127;
          *(_QWORD *)(v13 + 8184) = DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::sm_initTimeStamp
                                  ^ *(_QWORD *)(a1 + 80);
          *(_WORD *)(v13 + 8172) = a3;
          v26 = 0;
          if ( v13 + 0x2000 != v28 )
            v26 = v13 + 0x2000;
          *(_QWORD *)(a1 + 64) = v26;
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 32));
          if ( !a5 )
          {
LABEL_39:
            ((void (__fastcall *)(_QWORD, _QWORD))DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd)(
              v25 + 40,
              (LARGE_INTEGER)v22.QuadPart);
            AutoCPUId::~AutoCPUId((AutoCPUId *)v31);
LABEL_40:
            *v27 = 0;
            return v8;
          }
          ((void (__fastcall *)(_QWORD, _QWORD))DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd)(
            v25 + 40,
            (LARGE_INTEGER)v22.QuadPart);
          if ( a5 >= v13 && a5 < v13 + 0x2000 )
          {
            AutoCPUId::~AutoCPUId((AutoCPUId *)v31);
            *v27 = 0;
            return v8;
          }
          _mm_lfence();
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
          InterlockedPushEntrySList((PSLIST_HEADER)(a1 + 48), (PSLIST_ENTRY)(v13 + 8144));
          v7 = 0;
          v8 = 0;
          AutoCPUId::~AutoCPUId((AutoCPUId *)v31);
          *v27 = 0;
          v12 = v28;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1004a8d70  mov     rax, rsp
0x1004a8d73  mov     [rax+20h], r9
0x1004a8d77  mov     [rax+18h], r8w
0x1004a8d7c  mov     [rax+10h], dx
0x1004a8d80  push    rbp
0x1004a8d81  push    rsi
0x1004a8d82  push    rdi
0x1004a8d83  push    r12
0x1004a8d85  push    r13
0x1004a8d87  push    r14
0x1004a8d89  push    r15
0x1004a8d8b  sub     rsp, 60h
0x1004a8d8f  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x1004a8d97  mov     [rax+8], rbx
0x1004a8d9b  movzx   r12d, r8w
0x1004a8d9f  mov     rdi, rcx
0x1004a8da2  xor     ebx, ebx
0x1004a8da4  mov     r13, [rsp+98h+arg_20]
0x1004a8dac  test    r13, r13
0x1004a8daf  jz      short loc_1004A8DD1
0x1004a8db1  cmp     r13, [rcx]
0x1004a8db4  jb      short loc_1004A8DC9
0x1004a8db6  cmp     r13, [rcx+8]
0x1004a8dba  jnb     short loc_1004A8DC9
0x1004a8dbc  mov     rdx, r13
0x1004a8dbf  call    ?PopWithAddr@FragmentDesc@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@QEAAPEAUPageDesc@2@PEAE@Z; DescriptorAllocator<SOS_MemoryFreeBlock,0>::FragmentDesc::PopWithAddr(uchar *)
0x1004a8dc4  mov     rbp, rax
0x1004a8dc7  jmp     short loc_1004A8DE7
0x1004a8dc9  mov     rax, rbx
0x1004a8dcc  jmp     loc_1004A90B9
0x1004a8dd1  mov     rbp, rbx
0x1004a8dd4  add     rcx, 30h ; '0'; ListHead
0x1004a8dd8  call    cs:__imp_InterlockedPopEntrySList
0x1004a8dde  test    rax, rax
0x1004a8de1  jz      short loc_1004A8DE7
0x1004a8de3  lea     rbp, [rax-10h]
0x1004a8de7  test    rbp, rbp
0x1004a8dea  jz      short loc_1004A8DF5
0x1004a8dec  lock dec dword ptr [rdi+20h]
0x1004a8df0  jmp     loc_1004A90B6
0x1004a8df5  mov     rax, [rdi+40h]
0x1004a8df9  test    rax, rax
0x1004a8dfc  jz      loc_1004A90B6
0x1004a8e02  mov     rdx, [rdi+8]
0x1004a8e06  mov     [rsp+98h+var_70], rdx
0x1004a8e0b  cmp     rax, rdx
0x1004a8e0e  jnb     loc_1004A90B6
0x1004a8e14  lea     r9, ?sm_SOSNodeInfo@SOS_PublicGlobals@@2PAVSOS_NodeInfo@@A; SOS_NodeInfo near * SOS_PublicGlobals::sm_SOSNodeInfo
0x1004a8e1b  lea     rcx, [rdi+48h]
0x1004a8e1f  mov     eax, 1
0x1004a8e24  xchg    eax, [rcx]
0x1004a8e26  test    eax, eax
0x1004a8e28  jnz     loc_1004A90B6
0x1004a8e2e  mov     [rsp+98h+var_78], rcx
0x1004a8e33  mov     r15, [rdi+40h]
0x1004a8e37  test    r15, r15
0x1004a8e3a  jz      loc_1004A90AF
0x1004a8e40  cmp     r15, rdx
0x1004a8e43  jnb     loc_1004A90AF
0x1004a8e49  lfence
0x1004a8e4c  movzx   r14d, r12w
0x1004a8e50  lea     rdx, [r14+r14*2]
0x1004a8e54  shl     rdx, 6
0x1004a8e58  add     rdx, [rdi+50h]
0x1004a8e5c  mov     esi, [rdx+56Ch]
0x1004a8e62  cmp     esi, 0FFFFFFFFh
0x1004a8e65  jnz     short loc_1004A8ECB
0x1004a8e67  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x1004a8e6e  jz      short loc_1004A8EC9
0x1004a8e70  lea     rax, [r14+r14*4]
0x1004a8e74  lea     r8, ds:0[rax*8]
0x1004a8e7c  cmp     dword ptr [r8+r9+18h], 0
0x1004a8e82  jz      short loc_1004A8EBF
0x1004a8e84  mov     rcx, [r8+r9+8]
0x1004a8e89  lea     rax, [rcx-1]
0x1004a8e8d  not     rax
0x1004a8e90  and     rcx, rax
0x1004a8e93  bsf     rax, rcx
0x1004a8e97  mov     dword ptr [rsp+98h+arg_20], eax
0x1004a8e9e  movzx   ecx, word ptr [r8+r9+10h]
0x1004a8ea4  shl     rcx, 6
0x1004a8ea8  add     rcx, rax
0x1004a8eab  mov     ecx, ecx
0x1004a8ead  mov     rax, cs:?sm_AffinityToCPUInfo@SOS_OS@@0PEAKEA; ulong * SOS_OS::sm_AffinityToCPUInfo
0x1004a8eb4  mov     esi, [rax+rcx*4]
0x1004a8eb7  mov     [rdx+56Ch], esi
0x1004a8ebd  jmp     short loc_1004A8ECB
0x1004a8ebf  mov     esi, ebx
0x1004a8ec1  mov     [rdx+56Ch], ebx
0x1004a8ec7  jmp     short loc_1004A8ECB
0x1004a8ec9  mov     esi, ebx
0x1004a8ecb  cmp     r12w, [rsp+98h+arg_8]
0x1004a8ed4  setnz   bl
0x1004a8ed7  lea     rcx, [rsp+98h+var_50]; this
0x1004a8edc  call    ??0AutoDisableWorkerStealing@@QEAA@XZ; AutoDisableWorkerStealing::AutoDisableWorkerStealing(void)
0x1004a8ee1  nop
0x1004a8ee2  mov     [rsp+98h+var_54], ebx
0x1004a8ee6  cmp     r12w, [rsp+98h+arg_8]
0x1004a8eef  jz      short loc_1004A8F37
0x1004a8ef1  mov     rcx, gs:58h
0x1004a8efa  mov     eax, cs:_tls_index
0x1004a8f00  mov     ebx, cs:SystemThread_TlsOffset
0x1004a8f06  add     rbx, [rcx+rax*8]
0x1004a8f0a  mov     rcx, [rbx+100h]; void *
0x1004a8f11  test    rcx, rcx
0x1004a8f14  jnz     short loc_1004A8F22
0x1004a8f16  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a8f1b  mov     rcx, [rbx+100h]
0x1004a8f22  mov     [rcx+4Ch], esi
0x1004a8f25  mov     edx, esi; unsigned int
0x1004a8f27  mov     rcx, [rcx+270h]; this
0x1004a8f2e  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x1004a8f33  mov     [rsp+98h+var_58], eax
0x1004a8f37  mov     r12, [rdi+50h]
0x1004a8f3b  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004a8f42  jz      short loc_1004A8F56
0x1004a8f44  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x1004a8f49  call    cs:__imp_QueryPerformanceCounter
0x1004a8f4f  mov     rbx, qword ptr [rsp+98h+PerformanceCount]
0x1004a8f54  jmp     short loc_1004A8F5E
0x1004a8f56  mov     rbx, ds:7FFE0008h
0x1004a8f5e  mov     rax, [rsp+98h+arg_18]
0x1004a8f66  test    rax, rax
0x1004a8f69  jnz     short loc_1004A8F9E
0x1004a8f6b  mov     rcx, gs:58h
0x1004a8f74  mov     eax, cs:_tls_index
0x1004a8f7a  mov     esi, cs:SystemThread_TlsOffset
0x1004a8f80  add     rsi, [rcx+rax*8]
0x1004a8f84  mov     rax, [rsi+100h]
0x1004a8f8b  test    rax, rax
0x1004a8f8e  jnz     short loc_1004A8F9E
0x1004a8f90  xor     ecx, ecx; void *
0x1004a8f92  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a8f97  mov     rax, [rsi+100h]
0x1004a8f9e  shl     r14, 4
0x1004a8fa2  add     r14, r12
0x1004a8fa5  mov     [r14+28h], rax
0x1004a8fa9  movzx   r12d, [rsp+98h+arg_10]
0x1004a8fb2  movzx   r8d, r12w
0x1004a8fb6  mov     rdx, r15
0x1004a8fb9  mov     rcx, [rdi+50h]
0x1004a8fbd  call    ?CommitPage@FragmentDesc@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@SAHPEAV2@PEAEG@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::CommitPage(DescriptorAllocator<SOS_ParentBlockDescriptor,0> *,uchar *,ushort)
0x1004a8fc2  test    eax, eax
0x1004a8fc4  jz      loc_1004A9096
0x1004a8fca  lfence
0x1004a8fcd  lea     rbp, [r15+1FC0h]
0x1004a8fd4  mov     rcx, rbp; ListHead
0x1004a8fd7  call    cs:__imp_InitializeSListHead
0x1004a8fdd  mov     [rbp+18h], r15
0x1004a8fe1  mov     qword ptr [rbp+20h], 0FFFFFFFFFFFFFFFFh
0x1004a8fe9  mov     eax, 40h ; '@'
0x1004a8fee  mov     [rbp+2Ch], ax
0x1004a8ff2  mov     dword ptr [rbp+30h], 3
0x1004a8ff9  mov     dword ptr [rbp+28h], 7Fh
0x1004a9000  mov     rax, [rdi+50h]
0x1004a9004  xor     rax, cs:?sm_initTimeStamp@?$DescriptorAllocator@VSOS_TopLevelBlockDescriptor@@$0A@@@0_KA; unsigned __int64 DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::sm_initTimeStamp
0x1004a900b  mov     [rbp+38h], rax
0x1004a900f  mov     [rbp+2Ch], r12w
0x1004a9014  lea     rsi, [r15+2000h]
0x1004a901b  xor     eax, eax
0x1004a901d  cmp     rsi, [rsp+98h+var_70]
0x1004a9022  cmovnz  rax, rsi
0x1004a9026  mov     [rdi+40h], rax
0x1004a902a  lock dec dword ptr [rdi+20h]
0x1004a902e  test    r13, r13
0x1004a9031  jz      short loc_1004A9096
0x1004a9033  mov     rdx, rbx
0x1004a9036  lea     rcx, [r14+28h]
0x1004a903a  call    ?RecordAllocationEnd@AllocationTrace@DiagnosticInfo@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAXV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd(SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004a903f  cmp     r13, r15
0x1004a9042  jb      short loc_1004A9049
0x1004a9044  cmp     r13, rsi
0x1004a9047  jb      short loc_1004A907E
0x1004a9049  lfence
0x1004a904c  lock inc dword ptr [rdi+20h]
0x1004a9050  lea     rdx, [rbp+10h]; ListEntry
0x1004a9054  lea     rcx, [rdi+30h]; ListHead
0x1004a9058  call    cs:__imp_InterlockedPushEntrySList
0x1004a905e  xor     ebx, ebx
0x1004a9060  mov     ebp, ebx
0x1004a9062  lea     rcx, [rsp+98h+var_58]; this
0x1004a9067  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x1004a906c  nop
0x1004a906d  mov     rax, [rsp+98h+var_78]
0x1004a9072  mov     [rax], ebx
0x1004a9074  mov     rdx, [rsp+98h+var_70]
0x1004a9079  jmp     loc_1004A8E14
0x1004a907e  lea     rcx, [rsp+98h+var_58]; this
0x1004a9083  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x1004a9088  nop
0x1004a9089  mov     rax, [rsp+98h+var_78]
0x1004a908e  mov     dword ptr [rax], 0
0x1004a9094  jmp     short loc_1004A90B6
0x1004a9096  mov     rdx, rbx
0x1004a9099  lea     rcx, [r14+28h]
0x1004a909d  call    ?RecordAllocationEnd@AllocationTrace@DiagnosticInfo@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAXV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd(SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004a90a2  nop
0x1004a90a3  lea     rcx, [rsp+98h+var_58]; this
0x1004a90a8  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x1004a90ad  xor     ebx, ebx
0x1004a90af  mov     rax, [rsp+98h+var_78]
0x1004a90b4  mov     [rax], ebx
0x1004a90b6  mov     rax, rbp
0x1004a90b9  mov     rbx, [rsp+98h+arg_0]
0x1004a90c1  add     rsp, 60h
0x1004a90c5  pop     r15
0x1004a90c7  pop     r14
0x1004a90c9  pop     r13
0x1004a90cb  pop     r12
0x1004a90cd  pop     rdi
0x1004a90ce  pop     rsi
0x1004a90cf  pop     rbp
0x1004a90d0  retn
```
