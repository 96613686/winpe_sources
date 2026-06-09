# DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::Pop(uint,Worker *,uchar *)

- ea: `0x1004a7c90`
- end: `0x1004a7cfe`
- name: `?Pop@?$DescriptorAllocator@VSOS_TopLevelBlockDescriptor@@$0A@@@QEAAPEAVSOS_TopLevelBlockDescriptor@@IPEAVWorker@@PEAE@Z`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1004a6a60`
- `0x1004a7800`
- `0x1004aaf80`

## callees

- `0x100414400`
- `0x100432f40`
- `0x1004360f0`
- `0x10049bf60`
- `0x1004a7c90`
- `0x1004a8200`
- `0x1004a8460`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x1004a7d3c`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a7d3c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a7fc3`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a7fec`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a807f`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a7fc3`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a7fec`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a807f`

## pseudocode

```c
PSLIST_ENTRY __fastcall DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::Pop(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int64 a4)
{
  char v6; // r13
  unsigned int v7; // r10d
  unsigned __int64 v8; // rax
  char v9; // r12
  unsigned __int64 v11; // rbx
  LARGE_INTEGER v12; // rdi
  unsigned __int64 v13; // rsi
  PSLIST_ENTRY v14; // rbp
  unsigned __int64 v15; // rdx
  signed __int64 v16; // rcx
  unsigned __int16 *v17; // rdx
  unsigned __int16 v18; // bp
  __int64 v19; // rcx
  int v20; // ebp
  __int64 v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rsi
  __int64 v24; // rbp
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rdx
  int v27; // esi
  __int64 v28; // rbx
  __int64 v29; // rbx
  LARGE_INTEGER v30; // rax
  unsigned __int64 v31; // rax
  LARGE_INTEGER v32; // rcx
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  unsigned __int64 j; // rax
  __int32 v36; // [rsp+20h] [rbp-88h]
  LARGE_INTEGER v37; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 v38; // [rsp+38h] [rbp-70h]
  LARGE_INTEGER v39; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int64 v40; // [rsp+48h] [rbp-60h]
  LARGE_INTEGER v41; // [rsp+50h] [rbp-58h]
  int v42; // [rsp+58h] [rbp-50h] BYREF
  __int64 v43; // [rsp+60h] [rbp-48h]
  __int64 v44; // [rsp+68h] [rbp-40h]
  int i; // [rsp+B0h] [rbp+8h]
  LARGE_INTEGER PerformanceCount; // [rsp+C8h] [rbp+20h] BYREF

  v6 = 0;
  v7 = a2;
  v8 = *(_QWORD *)(a1 + 1216) + ((unsigned __int64)a2 << *(_BYTE *)(a1 + 1228));
  v9 = 0;
  v38 = v8;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( a4 )
    return DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::PopWithAddr(a1, a2, a4);
  v11 = v40;
  v12 = v41;
  for ( i = 1; ; i = v20 + 1 )
  {
    v13 = *(_QWORD *)(v8 + 8);
    if ( v13 )
    {
      v14 = InterlockedPopEntrySList(*(PSLIST_HEADER *)(v8 + 8));
      if ( v14 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v13 + 40));
        goto LABEL_61;
      }
      v14 = 0;
      v15 = *(_QWORD *)(v13 + 24);
      if ( v15 )
      {
        while ( 1 )
        {
          v14 = 0;
          if ( v15 >= v13 )
            break;
          _mm_lfence();
          v16 = v15 + 64;
          if ( v15 + 64 == v13 )
            v16 = 0;
          if ( v15 == _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 24), v16, v15) )
          {
            _mm_lfence();
            _InterlockedDecrement((volatile signed __int32 *)(v13 + 40));
            v14 = (PSLIST_ENTRY)v15;
            break;
          }
          v15 = *(_QWORD *)(v13 + 24);
          if ( !v15 )
            goto LABEL_15;
        }
      }
      if ( v14 )
        goto LABEL_61;
LABEL_15:
      v7 = a2;
    }
    v17 = (unsigned __int16 *)(*(_QWORD *)(a1 + 1216) + ((unsigned __int64)v7 << *(_BYTE *)(a1 + 1228)));
    v18 = *v17;
    if ( *v17 == 64 )
    {
      if ( (SOS_OS_sm_osProcessStatus & 1) != 0 )
      {
        v18 = *((_WORD *)SOS_PublicGlobals::sm_CPUInfo + 16 * v7);
        *v17 = v18;
      }
      else
      {
        v18 = 0;
      }
    }
    if ( !DescriptorAllocator<SOS_MemoryFreeBlock,0>::InstallPartialPageAsActive(a1, v13, v7, v18, v6) )
    {
      LOBYTE(v36) = v6;
      if ( !DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::InstallNewPageAsActive(a1, v13, a2, v18, v36, a3) )
      {
        if ( v6 )
        {
          v42 = 14;
          goto LABEL_59;
        }
        v6 = 1;
      }
    }
    v20 = i;
    if ( (i & 0x1FFF) == 0 )
    {
      v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      v22 = *(_QWORD *)(v21 + 256);
      if ( !v22 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v22 = *(_QWORD *)(v21 + 256);
      }
      if ( (*(_BYTE *)(v22 + 616) & 0x40) != 0 )
        goto LABEL_60;
      v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      v24 = *(_QWORD *)(v23 + 256);
      if ( !v24 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v24 = *(_QWORD *)(v23 + 256);
      }
      v25 = __rdtsc();
      v26 = *(_QWORD *)(v24 + 832);
      if ( v25 > v26
        || (v19 = 0x7FFFFFFFFFFFFFFFLL, v26 != 0x7FFFFFFFFFFFFFFFLL)
        && (v19 = *(_QWORD *)(v24 + 608), v26 - v25 > *(_QWORD *)(v19 + 3568)) )
      {
        v27 = *(_DWORD *)(v24 + 616);
        *(_DWORD *)(v24 + 616) = v27 | 1;
        SOS_Task::Sleep(0, yieldWait);
        *(_DWORD *)(v24 + 616) &= v27 | 0xFFFFFFFE;
      }
      v20 = i;
    }
    if ( !v9 )
    {
      if ( !a3 )
      {
        v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        a3 = *(_QWORD *)(v28 + 256);
        if ( !a3 )
        {
          SystemThread::MakeMiniSOSThread(0);
          a3 = *(_QWORD *)(v28 + 256);
        }
      }
      v29 = 120000;
      v19 = (unsigned int)Base_PublicGlobals::sm_invariantTscAvailable;
      if ( (*(_DWORD *)(a3 + 616) & 0x400) != 0 )
        v29 = 30000;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
        v11 = (Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart * v29 + 999) / 0x3E8uLL;
      else
        v11 = 10000 * v29;
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
      QueryPerformanceCounter(&v37);
      v30 = v37;
    }
    else
    {
      v30.QuadPart = MEMORY[0x7FFE0008];
    }
    v31 = v30.QuadPart < (unsigned __int64)v12.QuadPart ? 0LL : v30.QuadPart - v12.QuadPart;
    if ( v31 > v11 )
      break;
    v8 = v38;
    v7 = a2;
  }
  v42 = 15;
LABEL_59:
  DescriptorAllocator<SOS_ParentBlockDescriptor,0>::RecordAllocationFailure(v19, a3, &v42);
LABEL_60:
  v14 = 0;
LABEL_61:
  if ( v9 )
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v39);
      v32 = v39;
    }
    else
    {
      v32.QuadPart = MEMORY[0x7FFE0008];
    }
    if ( v32.QuadPart < (unsigned __int64)v12.QuadPart )
    {
      v33 = 0;
    }
    else
    {
      v33 = v32.QuadPart - v12.QuadPart;
      if ( v33 == -1 )
      {
        v34 = -1;
        goto LABEL_72;
      }
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v34 = 1000 * v33 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v34 = v33 / 0x2710;
LABEL_72:
    for ( j = *(_QWORD *)(a1 + 32); v34 > j; j = *(_QWORD *)(a1 + 32) )
    {
      if ( j == _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 32), v34, j) )
        break;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x1004a7c90  mov     [rsp+arg_8], edx
0x1004a7c94  push    r12
0x1004a7c96  push    r13
0x1004a7c98  push    r14
0x1004a7c9a  push    r15
0x1004a7c9c  sub     rsp, 88h
0x1004a7ca3  mov     r14, rcx
0x1004a7ca6  mov     eax, edx
0x1004a7ca8  movzx   ecx, byte ptr [rcx+4CCh]
0x1004a7caf  mov     r15, r8
0x1004a7cb2  xor     r8d, r8d
0x1004a7cb5  shl     rax, cl
0x1004a7cb8  xor     r13b, r13b
0x1004a7cbb  mov     r10d, edx
0x1004a7cbe  add     rax, [r14+4C0h]
0x1004a7cc5  xor     r12b, r12b
0x1004a7cc8  mov     [rsp+0A8h+var_70], rax
0x1004a7ccd  mov     [rsp+0A8h+var_50], r8d
0x1004a7cd2  mov     [rsp+0A8h+var_48], r8
0x1004a7cd7  mov     [rsp+0A8h+var_40], r8
0x1004a7cdc  test    r9, r9
0x1004a7cdf  jz      short loc_1004A7CFF
0x1004a7ce1  mov     r8, r9
0x1004a7ce4  mov     edx, r10d
0x1004a7ce7  mov     rcx, r14
0x1004a7cea  add     rsp, 88h
0x1004a7cf1  pop     r15
0x1004a7cf3  pop     r14
0x1004a7cf5  pop     r13
0x1004a7cf7  pop     r12
0x1004a7cf9  jmp     ?PopWithAddr@?$DescriptorAllocator@VSOS_TopLevelBlockDescriptor@@$0A@@@QEAAPEAVSOS_TopLevelBlockDescriptor@@IPEAE@Z; DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::PopWithAddr(uint,uchar *)
0x1004a7cff  mov     [rsp+0A8h+arg_10], rbx
0x1004a7d07  mov     rbx, [rsp+0A8h+var_60]
0x1004a7d0c  mov     [rsp+0A8h+var_28], rbp
0x1004a7d14  mov     [rsp+0A8h+var_30], rsi
0x1004a7d19  mov     [rsp+0A8h+var_38], rdi
0x1004a7d1e  mov     rdi, [rsp+0A8h+var_58]
0x1004a7d23  mov     [rsp+0A8h+arg_0], 1
0x1004a7d2e  xchg    ax, ax
0x1004a7d30  mov     rsi, [rax+8]
0x1004a7d34  test    rsi, rsi
0x1004a7d37  jz      short loc_1004A7DA7
0x1004a7d39  mov     rcx, rsi; ListHead
0x1004a7d3c  call    cs:__imp_InterlockedPopEntrySList
0x1004a7d42  mov     rbp, rax
0x1004a7d45  test    rax, rax
0x1004a7d48  jnz     loc_1004A8034
0x1004a7d4e  xor     r8d, r8d
0x1004a7d51  mov     ebp, r8d
0x1004a7d54  mov     rdx, [rsi+18h]
0x1004a7d58  test    rdx, rdx
0x1004a7d5b  jz      short loc_1004A7D96
0x1004a7d5d  nop     dword ptr [rax]
0x1004a7d60  mov     rbp, r8
0x1004a7d63  cmp     rdx, rsi
0x1004a7d66  jnb     short loc_1004A7D96
0x1004a7d68  lfence
0x1004a7d6b  lea     rcx, [rdx+40h]
0x1004a7d6f  mov     rax, rdx
0x1004a7d72  cmp     rcx, rsi
0x1004a7d75  cmovz   rcx, r8
0x1004a7d79  lock cmpxchg [rsi+18h], rcx
0x1004a7d7f  jz      short loc_1004A7D8C
0x1004a7d81  mov     rdx, [rsi+18h]
0x1004a7d85  test    rdx, rdx
0x1004a7d88  jnz     short loc_1004A7D60
0x1004a7d8a  jmp     short loc_1004A7D9F
0x1004a7d8c  lfence
0x1004a7d8f  lock dec dword ptr [rsi+28h]
0x1004a7d93  mov     rbp, rdx
0x1004a7d96  test    rbp, rbp
0x1004a7d99  jnz     loc_1004A805B
0x1004a7d9f  mov     r10d, [rsp+0A8h+arg_8]
0x1004a7da7  movzx   ecx, byte ptr [r14+4CCh]
0x1004a7daf  mov     edx, r10d
0x1004a7db2  shl     rdx, cl
0x1004a7db5  add     rdx, [r14+4C0h]
0x1004a7dbc  mov     eax, r10d
0x1004a7dbf  movzx   ebp, word ptr [rdx]
0x1004a7dc2  cmp     bp, 40h ; '@'
0x1004a7dc6  jnz     short loc_1004A7DEA
0x1004a7dc8  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x1004a7dcf  jz      short loc_1004A7DE7
0x1004a7dd1  mov     ecx, eax
0x1004a7dd3  mov     rax, cs:?sm_CPUInfo@SOS_PublicGlobals@@2PEAVSOS_CPUInfo@@EA; SOS_CPUInfo * SOS_PublicGlobals::sm_CPUInfo
0x1004a7dda  shl     rcx, 5
0x1004a7dde  movzx   ebp, word ptr [rcx+rax]
0x1004a7de2  mov     [rdx], bp
0x1004a7de5  jmp     short loc_1004A7DEA
0x1004a7de7  mov     ebp, r8d
0x1004a7dea  movzx   r9d, bp
0x1004a7dee  mov     [rsp+0A8h+var_88], r13b
0x1004a7df3  mov     r8d, r10d
0x1004a7df6  mov     rdx, rsi
0x1004a7df9  mov     rcx, r14
0x1004a7dfc  call    ?InstallPartialPageAsActive@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@AEAA_NPEAUPageDesc@1@IG_N@Z; DescriptorAllocator<SOS_MemoryFreeBlock,0>::InstallPartialPageAsActive(DescriptorAllocator<SOS_MemoryFreeBlock,0>::PageDesc *,uint,ushort,bool)
0x1004a7e01  test    al, al
0x1004a7e03  jnz     short loc_1004A7E36
0x1004a7e05  mov     r8d, [rsp+0A8h+arg_8]
0x1004a7e0d  movzx   r9d, bp
0x1004a7e11  mov     [rsp+0A8h+var_80], r15
0x1004a7e16  mov     rdx, rsi
0x1004a7e19  mov     rcx, r14
0x1004a7e1c  mov     [rsp+0A8h+var_88], r13b
0x1004a7e21  call    ?InstallNewPageAsActive@?$DescriptorAllocator@VSOS_TopLevelBlockDescriptor@@$0A@@@AEAA_NPEAUPageDesc@1@IG_NPEAVWorker@@@Z; DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::InstallNewPageAsActive(DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::PageDesc *,uint,ushort,bool,Worker *)
0x1004a7e26  test    al, al
0x1004a7e28  jnz     short loc_1004A7E36
0x1004a7e2a  test    r13b, r13b
0x1004a7e2d  jnz     loc_1004A803A
0x1004a7e33  mov     r13b, 1
0x1004a7e36  mov     ebp, [rsp+0A8h+arg_0]
0x1004a7e3d  test    ebp, 1FFFh
0x1004a7e43  jnz     loc_1004A7F22
0x1004a7e49  mov     rcx, gs:58h
0x1004a7e52  mov     eax, cs:_tls_index
0x1004a7e58  mov     esi, cs:SystemThread_TlsOffset
0x1004a7e5e  add     rsi, [rcx+rax*8]
0x1004a7e62  mov     rax, [rsi+100h]
0x1004a7e69  test    rax, rax
0x1004a7e6c  jnz     short loc_1004A7E7C
0x1004a7e6e  xor     ecx, ecx; void *
0x1004a7e70  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a7e75  mov     rax, [rsi+100h]
0x1004a7e7c  test    byte ptr [rax+268h], 40h
0x1004a7e83  jnz     loc_1004A8059
0x1004a7e89  mov     rcx, gs:58h
0x1004a7e92  mov     eax, cs:_tls_index
0x1004a7e98  mov     esi, cs:SystemThread_TlsOffset
0x1004a7e9e  add     rsi, [rcx+rax*8]
0x1004a7ea2  mov     rbp, [rsi+100h]
0x1004a7ea9  test    rbp, rbp
0x1004a7eac  jnz     short loc_1004A7EBC
0x1004a7eae  xor     ecx, ecx; void *
0x1004a7eb0  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a7eb5  mov     rbp, [rsi+100h]
0x1004a7ebc  rdtsc
0x1004a7ebe  shl     rdx, 20h
0x1004a7ec2  or      rax, rdx
0x1004a7ec5  mov     rdx, [rbp+340h]
0x1004a7ecc  cmp     rax, rdx
0x1004a7ecf  ja      short loc_1004A7EF3
0x1004a7ed1  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1004a7edb  cmp     rdx, rcx
0x1004a7ede  jz      short loc_1004A7F1B
0x1004a7ee0  mov     rcx, [rbp+260h]
0x1004a7ee7  sub     rdx, rax
0x1004a7eea  cmp     rdx, [rcx+0DF0h]
0x1004a7ef1  jbe     short loc_1004A7F1B
0x1004a7ef3  mov     esi, [rbp+268h]
0x1004a7ef9  lea     rdx, ?yieldWait@@3VSOS_WaitInfo@@B; "c@"
0x1004a7f00  mov     eax, esi
0x1004a7f02  xor     ecx, ecx
0x1004a7f04  or      eax, 1
0x1004a7f07  mov     [rbp+268h], eax
0x1004a7f0d  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x1004a7f12  or      esi, 0FFFFFFFEh
0x1004a7f15  and     [rbp+268h], esi
0x1004a7f1b  mov     ebp, [rsp+0A8h+arg_0]
0x1004a7f22  test    r12b, r12b
0x1004a7f25  jnz     loc_1004A7FDE
0x1004a7f2b  test    r15, r15
0x1004a7f2e  jnz     short loc_1004A7F63
0x1004a7f30  mov     rcx, gs:58h
0x1004a7f39  mov     eax, cs:_tls_index
0x1004a7f3f  mov     ebx, cs:SystemThread_TlsOffset
0x1004a7f45  add     rbx, [rcx+rax*8]
0x1004a7f49  mov     r15, [rbx+100h]
0x1004a7f50  test    r15, r15
0x1004a7f53  jnz     short loc_1004A7F63
0x1004a7f55  xor     ecx, ecx; void *
0x1004a7f57  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a7f5c  mov     r15, [rbx+100h]
0x1004a7f63  test    dword ptr [r15+268h], 400h
0x1004a7f6e  mov     ebx, 1D4C0h
0x1004a7f73  mov     ecx, cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004a7f79  mov     eax, 7530h
0x1004a7f7e  cmovnz  ebx, eax
0x1004a7f81  test    ecx, ecx
0x1004a7f83  jz      short loc_1004A7FB0
0x1004a7f85  imul    rbx, cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x1004a7f8d  mov     rax, 624DD2F1A9FBE77h
0x1004a7f97  add     rbx, 3E7h
0x1004a7f9e  mul     rbx
0x1004a7fa1  sub     rbx, rdx
0x1004a7fa4  shr     rbx, 1
0x1004a7fa7  add     rbx, rdx
0x1004a7faa  shr     rbx, 9
0x1004a7fae  jmp     short loc_1004A7FB7
0x1004a7fb0  imul    rbx, 2710h
0x1004a7fb7  test    ecx, ecx
0x1004a7fb9  jz      short loc_1004A7FD3
0x1004a7fbb  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x1004a7fc3  call    cs:__imp_QueryPerformanceCounter
0x1004a7fc9  mov     rdi, qword ptr [rsp+0A8h+PerformanceCount]
0x1004a7fd1  jmp     short loc_1004A7FDB
0x1004a7fd3  mov     rdi, ds:7FFE0008h
0x1004a7fdb  mov     r12b, 1
0x1004a7fde  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004a7fe5  jz      short loc_1004A7FF9
0x1004a7fe7  lea     rcx, [rsp+0A8h+var_78]; lpPerformanceCount
0x1004a7fec  call    cs:__imp_QueryPerformanceCounter
0x1004a7ff2  mov     rax, qword ptr [rsp+0A8h+var_78]
0x1004a7ff7  jmp     short loc_1004A8001
0x1004a7ff9  mov     rax, ds:7FFE0008h
0x1004a8001  cmp     rax, rdi
0x1004a8004  jb      short loc_1004A800E
0x1004a8006  sub     rax, rdi
0x1004a8009  xor     r8d, r8d
0x1004a800c  jmp     short loc_1004A8014
0x1004a800e  xor     r8d, r8d
0x1004a8011  mov     eax, r8d
0x1004a8014  cmp     rax, rbx
0x1004a8017  ja      short loc_1004A8044
0x1004a8019  mov     rax, [rsp+0A8h+var_70]
0x1004a801e  inc     ebp
0x1004a8020  mov     r10d, [rsp+0A8h+arg_8]
0x1004a8028  mov     [rsp+0A8h+arg_0], ebp
0x1004a802f  jmp     loc_1004A7D30
0x1004a8034  lock dec dword ptr [rsi+28h]
0x1004a8038  jmp     short loc_1004A805B
0x1004a803a  mov     [rsp+0A8h+var_50], 0Eh
0x1004a8042  jmp     short loc_1004A804C
0x1004a8044  mov     [rsp+0A8h+var_50], 0Fh
0x1004a804c  lea     r8, [rsp+0A8h+var_50]
0x1004a8051  mov     rdx, r15
0x1004a8054  call    ?RecordAllocationFailure@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@AEAAXPEAVWorker@@AEBUAllocationFailureInfo@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::RecordAllocationFailure(Worker *,AllocationFailureInfo const &)
0x1004a8059  xor     ebp, ebp
0x1004a805b  mov     rsi, [rsp+0A8h+var_30]
0x1004a8060  mov     rbx, [rsp+0A8h+arg_10]
0x1004a8068  test    r12b, r12b
0x1004a806b  jz      loc_1004A80F2
0x1004a8071  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004a8078  jz      short loc_1004A808C
0x1004a807a  lea     rcx, [rsp+0A8h+var_68]; lpPerformanceCount
0x1004a807f  call    cs:__imp_QueryPerformanceCounter
0x1004a8085  mov     rcx, qword ptr [rsp+0A8h+var_68]
0x1004a808a  jmp     short loc_1004A8094
0x1004a808c  mov     rcx, ds:7FFE0008h
0x1004a8094  cmp     rcx, rdi
0x1004a8097  jb      short loc_1004A80A7
0x1004a8099  sub     rcx, rdi
0x1004a809c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1004a80a0  jnz     short loc_1004A80A9
0x1004a80a2  mov     rdx, rcx
0x1004a80a5  jmp     short loc_1004A80D8
0x1004a80a7  xor     ecx, ecx
0x1004a80a9  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004a80b0  jz      short loc_1004A80C7
0x1004a80b2  xor     edx, edx
0x1004a80b4  imul    rax, rcx, 3E8h
0x1004a80bb  div     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x1004a80c2  mov     rdx, rax
0x1004a80c5  jmp     short loc_1004A80D8
0x1004a80c7  mov     rax, 346DC5D63886594Bh
0x1004a80d1  mul     rcx
0x1004a80d4  shr     rdx, 0Bh
0x1004a80d8  mov     rax, [r14+20h]
0x1004a80dc  cmp     rdx, rax
0x1004a80df  jbe     short loc_1004A80F2
0x1004a80e1  lock cmpxchg [r14+20h], rdx
0x1004a80e7  jz      short loc_1004A80F2
0x1004a80e9  mov     rax, [r14+20h]
0x1004a80ed  cmp     rdx, rax
0x1004a80f0  ja      short loc_1004A80E1
0x1004a80f2  mov     rdi, [rsp+0A8h+var_38]
0x1004a80f7  mov     rax, rbp
0x1004a80fa  mov     rbp, [rsp+0A8h+var_28]
0x1004a8102  add     rsp, 88h
0x1004a8109  pop     r15
0x1004a810b  pop     r14
0x1004a810d  pop     r13
0x1004a810f  pop     r12
0x1004a8111  retn
```
