# DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::FragmentDesc::Pop(ushort,ushort,Worker *,uchar *)

- ea: `0x10049ff90`
- end: `0x1004a02f1`
- name: `?Pop@FragmentDesc@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@QEAAPEAUPageDesc@2@GGPEAVWorker@@PEAE@Z`
- size: `865`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x10049f3e0`
- `0x10049f7c0`

## callees

- `0x100413dc0`
- `0x100426a00`
- `0x1004360f0`
- `0x100437f40`
- `0x100438050`
- `0x100438120`
- `0x10049ff90`
- `0x1004a05a0`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x1004a01f7`
- `KERNEL32!InitializeSListHead` at `0x1004a01f7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a0278`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a0278`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049fff8`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049fff8`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a0169`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a0169`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSLIST_ENTRY __fastcall DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::FragmentDesc::Pop(
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
    v8 = DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::FragmentDesc::PopWithAddr((union _SLIST_HEADER *)a1, a5);
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
          v8 = (PSLIST_ENTRY)(v13 + 8112);
          InitializeSListHead((PSLIST_HEADER)(v13 + 8112));
          *(_QWORD *)(v13 + 8136) = v13;
          *(_QWORD *)(v13 + 8144) = -1;
          *(_WORD *)(v13 + 8156) = 64;
          *(_DWORD *)(v13 + 8160) = 3;
          *(_DWORD *)(v13 + 8152) = 169;
          *(_QWORD *)(v13 + 8168) = DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::sm_initTimeStamp
                                  ^ *(_QWORD *)(a1 + 80);
          *(_WORD *)(v13 + 8156) = a3;
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
          InterlockedPushEntrySList((PSLIST_HEADER)(a1 + 48), (PSLIST_ENTRY)(v13 + 8128));
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
0x10049ff90  mov     rax, rsp
0x10049ff93  mov     [rax+20h], r9
0x10049ff97  mov     [rax+18h], r8w
0x10049ff9c  mov     [rax+10h], dx
0x10049ffa0  push    rbp
0x10049ffa1  push    rsi
0x10049ffa2  push    rdi
0x10049ffa3  push    r12
0x10049ffa5  push    r13
0x10049ffa7  push    r14
0x10049ffa9  push    r15
0x10049ffab  sub     rsp, 60h
0x10049ffaf  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x10049ffb7  mov     [rax+8], rbx
0x10049ffbb  movzx   r12d, r8w
0x10049ffbf  mov     rdi, rcx
0x10049ffc2  xor     ebx, ebx
0x10049ffc4  mov     r13, [rsp+98h+arg_20]
0x10049ffcc  test    r13, r13
0x10049ffcf  jz      short loc_10049FFF1
0x10049ffd1  cmp     r13, [rcx]
0x10049ffd4  jb      short loc_10049FFE9
0x10049ffd6  cmp     r13, [rcx+8]
0x10049ffda  jnb     short loc_10049FFE9
0x10049ffdc  mov     rdx, r13
0x10049ffdf  call    ?PopWithAddr@FragmentDesc@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@QEAAPEAUPageDesc@2@PEAE@Z; DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::FragmentDesc::PopWithAddr(uchar *)
0x10049ffe4  mov     rbp, rax
0x10049ffe7  jmp     short loc_1004A0007
0x10049ffe9  mov     rax, rbx
0x10049ffec  jmp     loc_1004A02D9
0x10049fff1  mov     rbp, rbx
0x10049fff4  add     rcx, 30h ; '0'; ListHead
0x10049fff8  call    cs:__imp_InterlockedPopEntrySList
0x10049fffe  test    rax, rax
0x1004a0001  jz      short loc_1004A0007
0x1004a0003  lea     rbp, [rax-10h]
0x1004a0007  test    rbp, rbp
0x1004a000a  jz      short loc_1004A0015
0x1004a000c  lock dec dword ptr [rdi+20h]
0x1004a0010  jmp     loc_1004A02D6
0x1004a0015  mov     rax, [rdi+40h]
0x1004a0019  test    rax, rax
0x1004a001c  jz      loc_1004A02D6
0x1004a0022  mov     rdx, [rdi+8]
0x1004a0026  mov     [rsp+98h+var_70], rdx
0x1004a002b  cmp     rax, rdx
0x1004a002e  jnb     loc_1004A02D6
0x1004a0034  lea     r9, ?sm_SOSNodeInfo@SOS_PublicGlobals@@2PAVSOS_NodeInfo@@A; SOS_NodeInfo near * SOS_PublicGlobals::sm_SOSNodeInfo
0x1004a003b  lea     rcx, [rdi+48h]
0x1004a003f  mov     eax, 1
0x1004a0044  xchg    eax, [rcx]
0x1004a0046  test    eax, eax
0x1004a0048  jnz     loc_1004A02D6
0x1004a004e  mov     [rsp+98h+var_78], rcx
0x1004a0053  mov     r15, [rdi+40h]
0x1004a0057  test    r15, r15
0x1004a005a  jz      loc_1004A02CF
0x1004a0060  cmp     r15, rdx
0x1004a0063  jnb     loc_1004A02CF
0x1004a0069  lfence
0x1004a006c  movzx   r14d, r12w
0x1004a0070  lea     rdx, [r14+r14*2]
0x1004a0074  shl     rdx, 6
0x1004a0078  add     rdx, [rdi+50h]
0x1004a007c  mov     esi, [rdx+56Ch]
0x1004a0082  cmp     esi, 0FFFFFFFFh
0x1004a0085  jnz     short loc_1004A00EB
0x1004a0087  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x1004a008e  jz      short loc_1004A00E9
0x1004a0090  lea     rax, [r14+r14*4]
0x1004a0094  lea     r8, ds:0[rax*8]
0x1004a009c  cmp     dword ptr [r8+r9+18h], 0
0x1004a00a2  jz      short loc_1004A00DF
0x1004a00a4  mov     rcx, [r8+r9+8]
0x1004a00a9  lea     rax, [rcx-1]
0x1004a00ad  not     rax
0x1004a00b0  and     rcx, rax
0x1004a00b3  bsf     rax, rcx
0x1004a00b7  mov     dword ptr [rsp+98h+arg_20], eax
0x1004a00be  movzx   ecx, word ptr [r8+r9+10h]
0x1004a00c4  shl     rcx, 6
0x1004a00c8  add     rcx, rax
0x1004a00cb  mov     ecx, ecx
0x1004a00cd  mov     rax, cs:?sm_AffinityToCPUInfo@SOS_OS@@0PEAKEA; ulong * SOS_OS::sm_AffinityToCPUInfo
0x1004a00d4  mov     esi, [rax+rcx*4]
0x1004a00d7  mov     [rdx+56Ch], esi
0x1004a00dd  jmp     short loc_1004A00EB
0x1004a00df  mov     esi, ebx
0x1004a00e1  mov     [rdx+56Ch], ebx
0x1004a00e7  jmp     short loc_1004A00EB
0x1004a00e9  mov     esi, ebx
0x1004a00eb  cmp     r12w, [rsp+98h+arg_8]
0x1004a00f4  setnz   bl
0x1004a00f7  lea     rcx, [rsp+98h+var_50]; this
0x1004a00fc  call    ??0AutoDisableWorkerStealing@@QEAA@XZ; AutoDisableWorkerStealing::AutoDisableWorkerStealing(void)
0x1004a0101  nop
0x1004a0102  mov     [rsp+98h+var_54], ebx
0x1004a0106  cmp     r12w, [rsp+98h+arg_8]
0x1004a010f  jz      short loc_1004A0157
0x1004a0111  mov     rcx, gs:58h
0x1004a011a  mov     eax, cs:_tls_index
0x1004a0120  mov     ebx, cs:SystemThread_TlsOffset
0x1004a0126  add     rbx, [rcx+rax*8]
0x1004a012a  mov     rcx, [rbx+100h]; void *
0x1004a0131  test    rcx, rcx
0x1004a0134  jnz     short loc_1004A0142
0x1004a0136  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a013b  mov     rcx, [rbx+100h]
0x1004a0142  mov     [rcx+4Ch], esi
0x1004a0145  mov     edx, esi; unsigned int
0x1004a0147  mov     rcx, [rcx+270h]; this
0x1004a014e  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x1004a0153  mov     [rsp+98h+var_58], eax
0x1004a0157  mov     r12, [rdi+50h]
0x1004a015b  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004a0162  jz      short loc_1004A0176
0x1004a0164  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x1004a0169  call    cs:__imp_QueryPerformanceCounter
0x1004a016f  mov     rbx, qword ptr [rsp+98h+PerformanceCount]
0x1004a0174  jmp     short loc_1004A017E
0x1004a0176  mov     rbx, ds:7FFE0008h
0x1004a017e  mov     rax, [rsp+98h+arg_18]
0x1004a0186  test    rax, rax
0x1004a0189  jnz     short loc_1004A01BE
0x1004a018b  mov     rcx, gs:58h
0x1004a0194  mov     eax, cs:_tls_index
0x1004a019a  mov     esi, cs:SystemThread_TlsOffset
0x1004a01a0  add     rsi, [rcx+rax*8]
0x1004a01a4  mov     rax, [rsi+100h]
0x1004a01ab  test    rax, rax
0x1004a01ae  jnz     short loc_1004A01BE
0x1004a01b0  xor     ecx, ecx; void *
0x1004a01b2  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a01b7  mov     rax, [rsi+100h]
0x1004a01be  shl     r14, 4
0x1004a01c2  add     r14, r12
0x1004a01c5  mov     [r14+28h], rax
0x1004a01c9  movzx   r12d, [rsp+98h+arg_10]
0x1004a01d2  movzx   r8d, r12w
0x1004a01d6  mov     rdx, r15
0x1004a01d9  mov     rcx, [rdi+50h]
0x1004a01dd  call    ?CommitPage@FragmentDesc@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@SAHPEAV2@PEAEG@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::FragmentDesc::CommitPage(DescriptorAllocator<SOS_ParentBlockDescriptor,0> *,uchar *,ushort)
0x1004a01e2  test    eax, eax
0x1004a01e4  jz      loc_1004A02B6
0x1004a01ea  lfence
0x1004a01ed  lea     rbp, [r15+1FB0h]
0x1004a01f4  mov     rcx, rbp; ListHead
0x1004a01f7  call    cs:__imp_InitializeSListHead
0x1004a01fd  mov     [rbp+18h], r15
0x1004a0201  mov     qword ptr [rbp+20h], 0FFFFFFFFFFFFFFFFh
0x1004a0209  mov     eax, 40h ; '@'
0x1004a020e  mov     [rbp+2Ch], ax
0x1004a0212  mov     dword ptr [rbp+30h], 3
0x1004a0219  mov     dword ptr [rbp+28h], 0A9h
0x1004a0220  mov     rax, [rdi+50h]
0x1004a0224  xor     rax, cs:?sm_initTimeStamp@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@0_KA; unsigned __int64 DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::sm_initTimeStamp
0x1004a022b  mov     [rbp+38h], rax
0x1004a022f  mov     [rbp+2Ch], r12w
0x1004a0234  lea     rsi, [r15+2000h]
0x1004a023b  xor     eax, eax
0x1004a023d  cmp     rsi, [rsp+98h+var_70]
0x1004a0242  cmovnz  rax, rsi
0x1004a0246  mov     [rdi+40h], rax
0x1004a024a  lock dec dword ptr [rdi+20h]
0x1004a024e  test    r13, r13
0x1004a0251  jz      short loc_1004A02B6
0x1004a0253  mov     rdx, rbx
0x1004a0256  lea     rcx, [r14+28h]
0x1004a025a  call    ?RecordAllocationEnd@AllocationTrace@DiagnosticInfo@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAXV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd(SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004a025f  cmp     r13, r15
0x1004a0262  jb      short loc_1004A0269
0x1004a0264  cmp     r13, rsi
0x1004a0267  jb      short loc_1004A029E
0x1004a0269  lfence
0x1004a026c  lock inc dword ptr [rdi+20h]
0x1004a0270  lea     rdx, [rbp+10h]; ListEntry
0x1004a0274  lea     rcx, [rdi+30h]; ListHead
0x1004a0278  call    cs:__imp_InterlockedPushEntrySList
0x1004a027e  xor     ebx, ebx
0x1004a0280  mov     ebp, ebx
0x1004a0282  lea     rcx, [rsp+98h+var_58]; this
0x1004a0287  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x1004a028c  nop
0x1004a028d  mov     rax, [rsp+98h+var_78]
0x1004a0292  mov     [rax], ebx
0x1004a0294  mov     rdx, [rsp+98h+var_70]
0x1004a0299  jmp     loc_1004A0034
0x1004a029e  lea     rcx, [rsp+98h+var_58]; this
0x1004a02a3  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x1004a02a8  nop
0x1004a02a9  mov     rax, [rsp+98h+var_78]
0x1004a02ae  mov     dword ptr [rax], 0
0x1004a02b4  jmp     short loc_1004A02D6
0x1004a02b6  mov     rdx, rbx
0x1004a02b9  lea     rcx, [r14+28h]
0x1004a02bd  call    ?RecordAllocationEnd@AllocationTrace@DiagnosticInfo@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAXV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::DiagnosticInfo::AllocationTrace::RecordAllocationEnd(SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004a02c2  nop
0x1004a02c3  lea     rcx, [rsp+98h+var_58]; this
0x1004a02c8  call    ??1AutoCPUId@@QEAA@XZ; AutoCPUId::~AutoCPUId(void)
0x1004a02cd  xor     ebx, ebx
0x1004a02cf  mov     rax, [rsp+98h+var_78]
0x1004a02d4  mov     [rax], ebx
0x1004a02d6  mov     rax, rbp
0x1004a02d9  mov     rbx, [rsp+98h+arg_0]
0x1004a02e1  add     rsp, 60h
0x1004a02e5  pop     r15
0x1004a02e7  pop     r14
0x1004a02e9  pop     r13
0x1004a02eb  pop     r12
0x1004a02ed  pop     rdi
0x1004a02ee  pop     rsi
0x1004a02ef  pop     rbp
0x1004a02f0  retn
```
