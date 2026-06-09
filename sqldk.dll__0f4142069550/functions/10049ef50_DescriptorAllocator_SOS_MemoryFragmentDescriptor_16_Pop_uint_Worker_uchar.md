# DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::Pop(uint,Worker *,uchar *)

- ea: `0x10049ef50`
- end: `0x10049efbe`
- name: `?Pop@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@QEAAPEAVSOS_MemoryFragmentDescriptor@@IPEAVWorker@@PEAE@Z`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x10049e250`
- `0x1004aaf80`

## callees

- `0x100414400`
- `0x1004360f0`
- `0x10049bf60`
- `0x10049ef50`
- `0x10049f3e0`
- `0x10049f5e0`
- `0x10049f7c0`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x10049efff`
- `KERNEL32!InterlockedPopEntrySList` at `0x10049efff`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f286`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f2af`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f342`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f286`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f2af`
- `KERNEL32!QueryPerformanceCounter` at `0x10049f342`

## pseudocode

```c
__int64 __fastcall DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::Pop(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  char v6; // r13
  unsigned int v7; // r10d
  unsigned __int64 v8; // rax
  char v9; // r12
  unsigned __int64 v11; // rbx
  LARGE_INTEGER v12; // rdi
  unsigned __int64 v13; // rsi
  PSLIST_ENTRY v14; // rbp
  PSLIST_ENTRY v15; // rax
  unsigned __int64 v16; // rdx
  signed __int64 v17; // rcx
  unsigned __int16 *v18; // rdx
  unsigned __int16 v19; // bp
  __int64 v20; // rcx
  int v21; // ebp
  __int64 v22; // rsi
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // rbp
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rdx
  int v28; // esi
  __int64 v29; // rbx
  __int64 v30; // rbx
  LARGE_INTEGER v31; // rax
  unsigned __int64 v32; // rax
  LARGE_INTEGER v33; // rcx
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  unsigned __int64 j; // rax
  __int32 v37; // [rsp+20h] [rbp-88h]
  LARGE_INTEGER v38; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 v39; // [rsp+38h] [rbp-70h]
  LARGE_INTEGER v40; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int64 v41; // [rsp+48h] [rbp-60h]
  LARGE_INTEGER v42; // [rsp+50h] [rbp-58h]
  int v43; // [rsp+58h] [rbp-50h] BYREF
  __int64 v44; // [rsp+60h] [rbp-48h]
  __int64 v45; // [rsp+68h] [rbp-40h]
  int i; // [rsp+B0h] [rbp+8h]
  LARGE_INTEGER PerformanceCount; // [rsp+C8h] [rbp+20h] BYREF

  v6 = 0;
  v7 = a2;
  v8 = *(_QWORD *)(a1 + 1216) + ((unsigned __int64)a2 << *(_BYTE *)(a1 + 1228));
  v9 = 0;
  v39 = v8;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  if ( a4 )
    return DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::PopWithAddr(a1, a2, a4);
  v11 = v41;
  v12 = v42;
  for ( i = 1; ; i = v21 + 1 )
  {
    v13 = *(_QWORD *)(v8 + 8);
    if ( v13 )
    {
      v14 = 0;
      v15 = InterlockedPopEntrySList(*(PSLIST_HEADER *)(v8 + 8));
      if ( v15 )
        v14 = v15 - 1;
      if ( v14 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v13 + 40));
        goto LABEL_63;
      }
      v16 = *(_QWORD *)(v13 + 24);
      if ( v16 )
      {
        while ( v16 < v13 )
        {
          _mm_lfence();
          v17 = v16 + 48;
          if ( v16 + 48 == v13 )
            v17 = 0;
          if ( v16 == _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 24), v17, v16) )
          {
            _mm_lfence();
            _InterlockedDecrement((volatile signed __int32 *)(v13 + 40));
            v14 = (PSLIST_ENTRY)v16;
            break;
          }
          v16 = *(_QWORD *)(v13 + 24);
          if ( !v16 )
            goto LABEL_17;
        }
      }
      if ( v14 )
        goto LABEL_63;
LABEL_17:
      v7 = a2;
    }
    v18 = (unsigned __int16 *)(*(_QWORD *)(a1 + 1216) + ((unsigned __int64)v7 << *(_BYTE *)(a1 + 1228)));
    v19 = *v18;
    if ( *v18 == 64 )
    {
      if ( (SOS_OS_sm_osProcessStatus & 1) != 0 )
      {
        v19 = *((_WORD *)SOS_PublicGlobals::sm_CPUInfo + 16 * v7);
        *v18 = v19;
      }
      else
      {
        v19 = 0;
      }
    }
    if ( !DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::InstallPartialPageAsActive(a1, v13, v7, v19, v6) )
    {
      LOBYTE(v37) = v6;
      if ( !DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::InstallNewPageAsActive(a1, v13, a2, v19, v37, a3) )
      {
        if ( v6 )
        {
          v43 = 14;
          goto LABEL_61;
        }
        v6 = 1;
      }
    }
    v21 = i;
    if ( (i & 0x1FFF) == 0 )
    {
      v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      v23 = *(_QWORD *)(v22 + 256);
      if ( !v23 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v23 = *(_QWORD *)(v22 + 256);
      }
      if ( (*(_BYTE *)(v23 + 616) & 0x40) != 0 )
        goto LABEL_62;
      v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      v25 = *(_QWORD *)(v24 + 256);
      if ( !v25 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v25 = *(_QWORD *)(v24 + 256);
      }
      v26 = __rdtsc();
      v27 = *(_QWORD *)(v25 + 832);
      if ( v26 > v27
        || (v20 = 0x7FFFFFFFFFFFFFFFLL, v27 != 0x7FFFFFFFFFFFFFFFLL)
        && (v20 = *(_QWORD *)(v25 + 608), v27 - v26 > *(_QWORD *)(v20 + 3568)) )
      {
        v28 = *(_DWORD *)(v25 + 616);
        *(_DWORD *)(v25 + 616) = v28 | 1;
        SOS_Task::Sleep(0, yieldWait);
        *(_DWORD *)(v25 + 616) &= v28 | 0xFFFFFFFE;
      }
      v21 = i;
    }
    if ( !v9 )
    {
      if ( !a3 )
      {
        v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        a3 = *(_QWORD *)(v29 + 256);
        if ( !a3 )
        {
          SystemThread::MakeMiniSOSThread(0);
          a3 = *(_QWORD *)(v29 + 256);
        }
      }
      v30 = 120000;
      v20 = (unsigned int)Base_PublicGlobals::sm_invariantTscAvailable;
      if ( (*(_DWORD *)(a3 + 616) & 0x400) != 0 )
        v30 = 30000;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
        v11 = (Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart * v30 + 999) / 0x3E8uLL;
      else
        v11 = 10000 * v30;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&PerformanceCount);
        v12 = PerformanceCount;
      }
      else
      {
        v12.QuadPart = MEMORY[0x7FFE0008];
      }
      v9 = 1;
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v38);
      v31 = v38;
    }
    else
    {
      v31.QuadPart = MEMORY[0x7FFE0008];
    }
    v32 = v31.QuadPart < (unsigned __int64)v12.QuadPart ? 0LL : v31.QuadPart - v12.QuadPart;
    if ( v32 > v11 )
      break;
    v8 = v39;
    v7 = a2;
  }
  v43 = 15;
LABEL_61:
  DescriptorAllocator<SOS_ParentBlockDescriptor,0>::RecordAllocationFailure(v20, a3, &v43);
LABEL_62:
  v14 = 0;
LABEL_63:
  if ( v9 )
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v40);
      v33 = v40;
    }
    else
    {
      v33.QuadPart = MEMORY[0x7FFE0008];
    }
    if ( v33.QuadPart < (unsigned __int64)v12.QuadPart )
    {
      v34 = 0;
    }
    else
    {
      v34 = v33.QuadPart - v12.QuadPart;
      if ( v34 == -1 )
      {
        v35 = -1;
        goto LABEL_74;
      }
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v35 = 1000 * v34 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v35 = v34 / 0x2710;
LABEL_74:
    for ( j = *(_QWORD *)(a1 + 32); v35 > j; j = *(_QWORD *)(a1 + 32) )
    {
      if ( j == _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 32), v35, j) )
        break;
    }
  }
  return (__int64)v14;
}

```

## disassembly

```asm
0x10049ef50  mov     [rsp+arg_8], edx
0x10049ef54  push    r12
0x10049ef56  push    r13
0x10049ef58  push    r14
0x10049ef5a  push    r15
0x10049ef5c  sub     rsp, 88h
0x10049ef63  mov     r14, rcx
0x10049ef66  mov     eax, edx
0x10049ef68  movzx   ecx, byte ptr [rcx+4CCh]
0x10049ef6f  mov     r15, r8
0x10049ef72  xor     r8d, r8d
0x10049ef75  shl     rax, cl
0x10049ef78  xor     r13b, r13b
0x10049ef7b  mov     r10d, edx
0x10049ef7e  add     rax, [r14+4C0h]
0x10049ef85  xor     r12b, r12b
0x10049ef88  mov     [rsp+0A8h+var_70], rax
0x10049ef8d  mov     [rsp+0A8h+var_50], r8d
0x10049ef92  mov     [rsp+0A8h+var_48], r8
0x10049ef97  mov     [rsp+0A8h+var_40], r8
0x10049ef9c  test    r9, r9
0x10049ef9f  jz      short loc_10049EFBF
0x10049efa1  mov     r8, r9
0x10049efa4  mov     edx, r10d
0x10049efa7  mov     rcx, r14
0x10049efaa  add     rsp, 88h
0x10049efb1  pop     r15
0x10049efb3  pop     r14
0x10049efb5  pop     r13
0x10049efb7  pop     r12
0x10049efb9  jmp     ?PopWithAddr@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@QEAAPEAVSOS_MemoryFragmentDescriptor@@IPEAE@Z; DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::PopWithAddr(uint,uchar *)
0x10049efbf  mov     [rsp+0A8h+arg_10], rbx
0x10049efc7  mov     rbx, [rsp+0A8h+var_60]
0x10049efcc  mov     [rsp+0A8h+var_30], rsi
0x10049efd1  mov     [rsp+0A8h+var_38], rdi
0x10049efd6  mov     rdi, [rsp+0A8h+var_58]
0x10049efdb  mov     [rsp+0A8h+var_28], rbp
0x10049efe3  mov     [rsp+0A8h+arg_0], 1
0x10049efee  xchg    ax, ax
0x10049eff0  mov     rsi, [rax+8]
0x10049eff4  test    rsi, rsi
0x10049eff7  jz      short loc_10049F06A
0x10049eff9  mov     rcx, rsi; ListHead
0x10049effc  mov     rbp, r8
0x10049efff  call    cs:__imp_InterlockedPopEntrySList
0x10049f005  test    rax, rax
0x10049f008  jz      short loc_10049F00E
0x10049f00a  lea     rbp, [rax-10h]
0x10049f00e  test    rbp, rbp
0x10049f011  jnz     loc_10049F2F7
0x10049f017  mov     rdx, [rsi+18h]
0x10049f01b  test    rdx, rdx
0x10049f01e  jz      short loc_10049F056
0x10049f020  xor     r8d, r8d
0x10049f023  cmp     rdx, rsi
0x10049f026  jnb     short loc_10049F056
0x10049f028  lfence
0x10049f02b  lea     rcx, [rdx+30h]
0x10049f02f  mov     rax, rdx
0x10049f032  cmp     rcx, rsi
0x10049f035  cmovz   rcx, r8
0x10049f039  lock cmpxchg [rsi+18h], rcx
0x10049f03f  jz      short loc_10049F04C
0x10049f041  mov     rdx, [rsi+18h]
0x10049f045  test    rdx, rdx
0x10049f048  jnz     short loc_10049F023
0x10049f04a  jmp     short loc_10049F062
0x10049f04c  lfence
0x10049f04f  lock dec dword ptr [rsi+28h]
0x10049f053  mov     rbp, rdx
0x10049f056  test    rbp, rbp
0x10049f059  jnz     loc_10049F31E
0x10049f05f  xor     r8d, r8d
0x10049f062  mov     r10d, [rsp+0A8h+arg_8]
0x10049f06a  movzx   ecx, byte ptr [r14+4CCh]
0x10049f072  mov     edx, r10d
0x10049f075  shl     rdx, cl
0x10049f078  add     rdx, [r14+4C0h]
0x10049f07f  mov     eax, r10d
0x10049f082  movzx   ebp, word ptr [rdx]
0x10049f085  cmp     bp, 40h ; '@'
0x10049f089  jnz     short loc_10049F0AD
0x10049f08b  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x10049f092  jz      short loc_10049F0AA
0x10049f094  mov     ecx, eax
0x10049f096  mov     rax, cs:?sm_CPUInfo@SOS_PublicGlobals@@2PEAVSOS_CPUInfo@@EA; SOS_CPUInfo * SOS_PublicGlobals::sm_CPUInfo
0x10049f09d  shl     rcx, 5
0x10049f0a1  movzx   ebp, word ptr [rcx+rax]
0x10049f0a5  mov     [rdx], bp
0x10049f0a8  jmp     short loc_10049F0AD
0x10049f0aa  mov     ebp, r8d
0x10049f0ad  movzx   r9d, bp
0x10049f0b1  mov     [rsp+0A8h+var_88], r13b
0x10049f0b6  mov     r8d, r10d
0x10049f0b9  mov     rdx, rsi
0x10049f0bc  mov     rcx, r14
0x10049f0bf  call    ?InstallPartialPageAsActive@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@AEAA_NPEAUPageDesc@1@IG_N@Z; DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::InstallPartialPageAsActive(DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::PageDesc *,uint,ushort,bool)
0x10049f0c4  test    al, al
0x10049f0c6  jnz     short loc_10049F0F9
0x10049f0c8  mov     r8d, [rsp+0A8h+arg_8]
0x10049f0d0  movzx   r9d, bp
0x10049f0d4  mov     [rsp+0A8h+var_80], r15
0x10049f0d9  mov     rdx, rsi
0x10049f0dc  mov     rcx, r14
0x10049f0df  mov     [rsp+0A8h+var_88], r13b
0x10049f0e4  call    ?InstallNewPageAsActive@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@AEAA_NPEAUPageDesc@1@IG_NPEAVWorker@@@Z; DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::InstallNewPageAsActive(DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::PageDesc *,uint,ushort,bool,Worker *)
0x10049f0e9  test    al, al
0x10049f0eb  jnz     short loc_10049F0F9
0x10049f0ed  test    r13b, r13b
0x10049f0f0  jnz     loc_10049F2FD
0x10049f0f6  mov     r13b, 1
0x10049f0f9  mov     ebp, [rsp+0A8h+arg_0]
0x10049f100  test    ebp, 1FFFh
0x10049f106  jnz     loc_10049F1E5
0x10049f10c  mov     rcx, gs:58h
0x10049f115  mov     eax, cs:_tls_index
0x10049f11b  mov     esi, cs:SystemThread_TlsOffset
0x10049f121  add     rsi, [rcx+rax*8]
0x10049f125  mov     rax, [rsi+100h]
0x10049f12c  test    rax, rax
0x10049f12f  jnz     short loc_10049F13F
0x10049f131  xor     ecx, ecx; void *
0x10049f133  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049f138  mov     rax, [rsi+100h]
0x10049f13f  test    byte ptr [rax+268h], 40h
0x10049f146  jnz     loc_10049F31C
0x10049f14c  mov     rcx, gs:58h
0x10049f155  mov     eax, cs:_tls_index
0x10049f15b  mov     esi, cs:SystemThread_TlsOffset
0x10049f161  add     rsi, [rcx+rax*8]
0x10049f165  mov     rbp, [rsi+100h]
0x10049f16c  test    rbp, rbp
0x10049f16f  jnz     short loc_10049F17F
0x10049f171  xor     ecx, ecx; void *
0x10049f173  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049f178  mov     rbp, [rsi+100h]
0x10049f17f  rdtsc
0x10049f181  shl     rdx, 20h
0x10049f185  or      rax, rdx
0x10049f188  mov     rdx, [rbp+340h]
0x10049f18f  cmp     rax, rdx
0x10049f192  ja      short loc_10049F1B6
0x10049f194  mov     rcx, 7FFFFFFFFFFFFFFFh
0x10049f19e  cmp     rdx, rcx
0x10049f1a1  jz      short loc_10049F1DE
0x10049f1a3  mov     rcx, [rbp+260h]
0x10049f1aa  sub     rdx, rax
0x10049f1ad  cmp     rdx, [rcx+0DF0h]
0x10049f1b4  jbe     short loc_10049F1DE
0x10049f1b6  mov     esi, [rbp+268h]
0x10049f1bc  lea     rdx, ?yieldWait@@3VSOS_WaitInfo@@B; "c@"
0x10049f1c3  mov     eax, esi
0x10049f1c5  xor     ecx, ecx
0x10049f1c7  or      eax, 1
0x10049f1ca  mov     [rbp+268h], eax
0x10049f1d0  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x10049f1d5  or      esi, 0FFFFFFFEh
0x10049f1d8  and     [rbp+268h], esi
0x10049f1de  mov     ebp, [rsp+0A8h+arg_0]
0x10049f1e5  test    r12b, r12b
0x10049f1e8  jnz     loc_10049F2A1
0x10049f1ee  test    r15, r15
0x10049f1f1  jnz     short loc_10049F226
0x10049f1f3  mov     rcx, gs:58h
0x10049f1fc  mov     eax, cs:_tls_index
0x10049f202  mov     ebx, cs:SystemThread_TlsOffset
0x10049f208  add     rbx, [rcx+rax*8]
0x10049f20c  mov     r15, [rbx+100h]
0x10049f213  test    r15, r15
0x10049f216  jnz     short loc_10049F226
0x10049f218  xor     ecx, ecx; void *
0x10049f21a  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049f21f  mov     r15, [rbx+100h]
0x10049f226  test    dword ptr [r15+268h], 400h
0x10049f231  mov     ebx, 1D4C0h
0x10049f236  mov     ecx, cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049f23c  mov     eax, 7530h
0x10049f241  cmovnz  ebx, eax
0x10049f244  test    ecx, ecx
0x10049f246  jz      short loc_10049F273
0x10049f248  imul    rbx, cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x10049f250  mov     rax, 624DD2F1A9FBE77h
0x10049f25a  add     rbx, 3E7h
0x10049f261  mul     rbx
0x10049f264  sub     rbx, rdx
0x10049f267  shr     rbx, 1
0x10049f26a  add     rbx, rdx
0x10049f26d  shr     rbx, 9
0x10049f271  jmp     short loc_10049F27A
0x10049f273  imul    rbx, 2710h
0x10049f27a  test    ecx, ecx
0x10049f27c  jz      short loc_10049F296
0x10049f27e  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x10049f286  call    cs:__imp_QueryPerformanceCounter
0x10049f28c  mov     rdi, qword ptr [rsp+0A8h+PerformanceCount]
0x10049f294  jmp     short loc_10049F29E
0x10049f296  mov     rdi, ds:7FFE0008h
0x10049f29e  mov     r12b, 1
0x10049f2a1  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049f2a8  jz      short loc_10049F2BC
0x10049f2aa  lea     rcx, [rsp+0A8h+var_78]; lpPerformanceCount
0x10049f2af  call    cs:__imp_QueryPerformanceCounter
0x10049f2b5  mov     rax, qword ptr [rsp+0A8h+var_78]
0x10049f2ba  jmp     short loc_10049F2C4
0x10049f2bc  mov     rax, ds:7FFE0008h
0x10049f2c4  cmp     rax, rdi
0x10049f2c7  jb      short loc_10049F2D1
0x10049f2c9  sub     rax, rdi
0x10049f2cc  xor     r8d, r8d
0x10049f2cf  jmp     short loc_10049F2D7
0x10049f2d1  xor     r8d, r8d
0x10049f2d4  mov     eax, r8d
0x10049f2d7  cmp     rax, rbx
0x10049f2da  ja      short loc_10049F307
0x10049f2dc  mov     rax, [rsp+0A8h+var_70]
0x10049f2e1  inc     ebp
0x10049f2e3  mov     r10d, [rsp+0A8h+arg_8]
0x10049f2eb  mov     [rsp+0A8h+arg_0], ebp
0x10049f2f2  jmp     loc_10049EFF0
0x10049f2f7  lock dec dword ptr [rsi+28h]
0x10049f2fb  jmp     short loc_10049F31E
0x10049f2fd  mov     [rsp+0A8h+var_50], 0Eh
0x10049f305  jmp     short loc_10049F30F
0x10049f307  mov     [rsp+0A8h+var_50], 0Fh
0x10049f30f  lea     r8, [rsp+0A8h+var_50]
0x10049f314  mov     rdx, r15
0x10049f317  call    ?RecordAllocationFailure@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@AEAAXPEAVWorker@@AEBUAllocationFailureInfo@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::RecordAllocationFailure(Worker *,AllocationFailureInfo const &)
0x10049f31c  xor     ebp, ebp
0x10049f31e  mov     rsi, [rsp+0A8h+var_30]
0x10049f323  mov     rbx, [rsp+0A8h+arg_10]
0x10049f32b  test    r12b, r12b
0x10049f32e  jz      loc_10049F3B5
0x10049f334  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049f33b  jz      short loc_10049F34F
0x10049f33d  lea     rcx, [rsp+0A8h+var_68]; lpPerformanceCount
0x10049f342  call    cs:__imp_QueryPerformanceCounter
0x10049f348  mov     rcx, qword ptr [rsp+0A8h+var_68]
0x10049f34d  jmp     short loc_10049F357
0x10049f34f  mov     rcx, ds:7FFE0008h
0x10049f357  cmp     rcx, rdi
0x10049f35a  jb      short loc_10049F36A
0x10049f35c  sub     rcx, rdi
0x10049f35f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x10049f363  jnz     short loc_10049F36C
0x10049f365  mov     rdx, rcx
0x10049f368  jmp     short loc_10049F39B
0x10049f36a  xor     ecx, ecx
0x10049f36c  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10049f373  jz      short loc_10049F38A
0x10049f375  xor     edx, edx
0x10049f377  imul    rax, rcx, 3E8h
0x10049f37e  div     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x10049f385  mov     rdx, rax
0x10049f388  jmp     short loc_10049F39B
0x10049f38a  mov     rax, 346DC5D63886594Bh
0x10049f394  mul     rcx
0x10049f397  shr     rdx, 0Bh
0x10049f39b  mov     rax, [r14+20h]
0x10049f39f  cmp     rdx, rax
0x10049f3a2  jbe     short loc_10049F3B5
0x10049f3a4  lock cmpxchg [r14+20h], rdx
0x10049f3aa  jz      short loc_10049F3B5
0x10049f3ac  mov     rax, [r14+20h]
0x10049f3b0  cmp     rdx, rax
0x10049f3b3  ja      short loc_10049F3A4
0x10049f3b5  mov     rdi, [rsp+0A8h+var_38]
0x10049f3ba  mov     rax, rbp
0x10049f3bd  mov     rbp, [rsp+0A8h+var_28]
0x10049f3c5  add     rsp, 88h
0x10049f3cc  pop     r15
0x10049f3ce  pop     r14
0x10049f3d0  pop     r13
0x10049f3d2  pop     r12
0x10049f3d4  retn
```
