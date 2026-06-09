# DescriptorAllocator<SOS_MemoryFreeBlock,0>::Pop(uint,Worker *,uchar *)

- ea: `0x1004325b0`
- end: `0x1004326ee`
- name: `?Pop@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@QEAAPEAVSOS_MemoryFreeBlock@@IPEAVWorker@@PEAE@Z`
- size: `318`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x10040aaa0`
- `0x10040b880`
- `0x1004abdb0`

## callees

- `0x100414400`
- `0x1004325b0`
- `0x100432f40`
- `0x100433280`
- `0x1004360f0`
- `0x10049ba90`
- `0x10049bf60`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x100432650`
- `KERNEL32!InterlockedPopEntrySList` at `0x100432650`
- `KERNEL32!QueryPerformanceCounter` at `0x100432d03`
- `KERNEL32!QueryPerformanceCounter` at `0x100432ec0`
- `KERNEL32!QueryPerformanceCounter` at `0x100432ee6`
- `KERNEL32!QueryPerformanceCounter` at `0x100432d03`
- `KERNEL32!QueryPerformanceCounter` at `0x100432ec0`
- `KERNEL32!QueryPerformanceCounter` at `0x100432ee6`

## pseudocode

```c
__int64 __fastcall DescriptorAllocator<SOS_MemoryFreeBlock,0>::Pop(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  char v6; // r13
  unsigned int v7; // r10d
  unsigned __int64 v8; // rax
  char v9; // r12
  unsigned __int64 v10; // rbx
  LARGE_INTEGER v11; // rdi
  unsigned __int64 v12; // rsi
  PSLIST_ENTRY v13; // rbp
  unsigned __int64 v14; // rdx
  signed __int64 v15; // rcx
  LARGE_INTEGER v17; // rcx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 j; // rax
  unsigned __int16 *v21; // rdx
  unsigned __int16 v22; // bp
  __int64 v23; // rcx
  int v24; // ebp
  __int64 v25; // rbx
  __int64 v26; // rbx
  LARGE_INTEGER v27; // rax
  unsigned __int64 v28; // rax
  __int64 v29; // rsi
  __int64 v30; // rax
  __int64 v31; // rsi
  __int64 v32; // rbp
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rdx
  int v35; // esi
  __int32 v36; // [rsp+20h] [rbp-88h]
  LARGE_INTEGER v37; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 v38; // [rsp+38h] [rbp-70h]
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int64 v40; // [rsp+48h] [rbp-60h]
  LARGE_INTEGER v41; // [rsp+50h] [rbp-58h]
  int v42; // [rsp+58h] [rbp-50h] BYREF
  __int64 v43; // [rsp+60h] [rbp-48h]
  __int64 v44; // [rsp+68h] [rbp-40h]
  int i; // [rsp+B0h] [rbp+8h]
  LARGE_INTEGER v47; // [rsp+C8h] [rbp+20h] BYREF

  v6 = 0;
  v7 = a2;
  v8 = *(_QWORD *)(a1 + 1216) + ((unsigned __int64)a2 << *(_BYTE *)(a1 + 1228));
  v9 = 0;
  v38 = v8;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( !a4 )
  {
    v10 = v40;
    v11 = v41;
    for ( i = 1; ; i = v24 + 1 )
    {
      v12 = *(_QWORD *)(v8 + 8);
      if ( v12 )
      {
        v13 = InterlockedPopEntrySList(*(PSLIST_HEADER *)(v8 + 8));
        if ( v13 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v12 + 40));
          goto LABEL_12;
        }
        v13 = 0;
        v14 = *(_QWORD *)(v12 + 24);
        if ( v14 )
        {
          while ( 1 )
          {
            v13 = 0;
            if ( v14 >= v12 )
              break;
            _mm_lfence();
            v15 = v14 + 64;
            if ( v14 + 64 == v12 )
              v15 = 0;
            if ( v14 == _InterlockedCompareExchange64((volatile signed __int64 *)(v12 + 24), v15, v14) )
            {
              _mm_lfence();
              _InterlockedDecrement((volatile signed __int32 *)(v12 + 40));
              v13 = (PSLIST_ENTRY)v14;
              break;
            }
            v14 = *(_QWORD *)(v12 + 24);
            if ( !v14 )
              goto LABEL_26;
          }
        }
        if ( v13 )
          goto LABEL_12;
LABEL_26:
        v7 = a2;
      }
      v21 = (unsigned __int16 *)(*(_QWORD *)(a1 + 1216) + ((unsigned __int64)v7 << *(_BYTE *)(a1 + 1228)));
      v22 = *v21;
      if ( *v21 == 64 )
      {
        if ( (SOS_OS_sm_osProcessStatus & 1) != 0 )
        {
          v22 = *((_WORD *)SOS_PublicGlobals::sm_CPUInfo + 16 * v7);
          *v21 = v22;
        }
        else
        {
          v22 = 0;
        }
      }
      if ( !DescriptorAllocator<SOS_MemoryFreeBlock,0>::InstallPartialPageAsActive(a1, v12, v7, v22, v6) )
      {
        LOBYTE(v36) = v6;
        if ( !DescriptorAllocator<SOS_MemoryFreeBlock,0>::InstallNewPageAsActive(a1, v12, a2, v22, v36, a3) )
        {
          if ( v6 )
          {
            v42 = 14;
            goto LABEL_69;
          }
          v6 = 1;
        }
      }
      v24 = i;
      if ( (i & 0x1FFF) == 0 )
      {
        v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        v30 = *(_QWORD *)(v29 + 256);
        if ( !v30 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v30 = *(_QWORD *)(v29 + 256);
        }
        if ( (*(_BYTE *)(v30 + 616) & 0x40) != 0 )
          goto LABEL_70;
        v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        v32 = *(_QWORD *)(v31 + 256);
        if ( !v32 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v32 = *(_QWORD *)(v31 + 256);
        }
        v33 = __rdtsc();
        v34 = *(_QWORD *)(v32 + 832);
        if ( v33 > v34
          || (v23 = 0x7FFFFFFFFFFFFFFFLL, v34 != 0x7FFFFFFFFFFFFFFFLL)
          && (v23 = *(_QWORD *)(v32 + 608), v34 - v33 > *(_QWORD *)(v23 + 3568)) )
        {
          v35 = *(_DWORD *)(v32 + 616);
          *(_DWORD *)(v32 + 616) = v35 | 1;
          SOS_Task::Sleep(0, yieldWait);
          *(_DWORD *)(v32 + 616) &= v35 | 0xFFFFFFFE;
        }
        v24 = i;
      }
      if ( !v9 )
      {
        if ( !a3 )
        {
          v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
              + (unsigned int)SystemThread_TlsOffset;
          a3 = *(_QWORD *)(v25 + 256);
          if ( !a3 )
          {
            SystemThread::MakeMiniSOSThread(0);
            a3 = *(_QWORD *)(v25 + 256);
          }
        }
        v26 = 120000;
        v23 = (unsigned int)Base_PublicGlobals::sm_invariantTscAvailable;
        if ( (*(_DWORD *)(a3 + 616) & 0x400) != 0 )
          v26 = 30000;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
          v10 = (Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart * v26 + 999) / 0x3E8uLL;
        else
          v10 = 10000 * v26;
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v47);
          v11 = v47;
        }
        else
        {
          v11.QuadPart = MEMORY[0x7FFE0008];
        }
        v9 = 1;
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v37);
        v27 = v37;
      }
      else
      {
        v27.QuadPart = MEMORY[0x7FFE0008];
      }
      v28 = v27.QuadPart < (unsigned __int64)v11.QuadPart ? 0LL : v27.QuadPart - v11.QuadPart;
      if ( v28 > v10 )
        break;
      v8 = v38;
      v7 = a2;
    }
    v42 = 15;
LABEL_69:
    DescriptorAllocator<SOS_ParentBlockDescriptor,0>::RecordAllocationFailure(v23, a3, &v42);
LABEL_70:
    v13 = 0;
LABEL_12:
    if ( !v9 )
      return (__int64)v13;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      v17 = PerformanceCount;
    }
    else
    {
      v17.QuadPart = MEMORY[0x7FFE0008];
    }
    if ( v17.QuadPart < (unsigned __int64)v11.QuadPart )
    {
      v18 = 0;
    }
    else
    {
      v18 = v17.QuadPart - v11.QuadPart;
      if ( v18 == -1 )
      {
        v19 = -1;
        goto LABEL_21;
      }
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v19 = 1000 * v18 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v19 = v18 / 0x2710;
LABEL_21:
    for ( j = *(_QWORD *)(a1 + 32); v19 > j; j = *(_QWORD *)(a1 + 32) )
    {
      if ( j == _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 32), v19, j) )
        break;
    }
    return (__int64)v13;
  }
  return DescriptorAllocator<SOS_MemoryFreeBlock,0>::PopWithAddr(a1, a2, a4);
}

```

## disassembly

```asm
0x1004325b0  mov     [rsp+arg_8], edx
0x1004325b4  push    r12
0x1004325b6  push    r13
0x1004325b8  push    r14
0x1004325ba  push    r15
0x1004325bc  sub     rsp, 88h
0x1004325c3  mov     r14, rcx
0x1004325c6  mov     eax, edx
0x1004325c8  movzx   ecx, byte ptr [rcx+4CCh]
0x1004325cf  mov     r15, r8
0x1004325d2  xor     r8d, r8d
0x1004325d5  shl     rax, cl
0x1004325d8  xor     r13b, r13b
0x1004325db  mov     r10d, edx
0x1004325de  add     rax, [r14+4C0h]
0x1004325e5  xor     r12b, r12b
0x1004325e8  mov     [rsp+0A8h+var_70], rax
0x1004325ed  mov     [rsp+0A8h+var_50], r8d
0x1004325f2  mov     [rsp+0A8h+var_48], r8
0x1004325f7  mov     [rsp+0A8h+var_40], r8
0x1004325fc  test    r9, r9
0x1004325ff  jnz     loc_10049B53A
0x100432605  mov     [rsp+0A8h+arg_10], rbx
0x10043260d  mov     rbx, [rsp+0A8h+var_60]
0x100432612  mov     [rsp+0A8h+var_28], rbp
0x10043261a  mov     [rsp+0A8h+var_30], rsi
0x10043261f  mov     [rsp+0A8h+var_38], rdi
0x100432624  mov     rdi, [rsp+0A8h+var_58]
0x100432629  mov     [rsp+0A8h+arg_0], 1
0x100432634  nop     dword ptr [rax+00h]
0x100432638  nop     dword ptr [rax+rax+00000000h]
0x100432640  mov     rsi, [rax+8]
0x100432644  test    rsi, rsi
0x100432647  jz      loc_100432D8B
0x10043264d  mov     rcx, rsi; ListHead
0x100432650  call    cs:__imp_InterlockedPopEntrySList
0x100432656  mov     rbp, rax
0x100432659  test    rax, rax
0x10043265c  jnz     loc_100432728
0x100432662  xor     r8d, r8d
0x100432665  mov     ebp, r8d
0x100432668  mov     rdx, [rsi+18h]
0x10043266c  test    rdx, rdx
0x10043266f  jz      short loc_1004326AF
0x100432671  nop     dword ptr [rax]
0x100432674  nop     dword ptr [rax+00h]
0x100432678  nop     dword ptr [rax+rax+00000000h]
0x100432680  mov     rbp, r8
0x100432683  cmp     rdx, rsi
0x100432686  jnb     short loc_1004326AF
0x100432688  lfence
0x10043268b  lea     rcx, [rdx+40h]
0x10043268f  mov     rax, rdx
0x100432692  cmp     rcx, rsi
0x100432695  cmovz   rcx, r8
0x100432699  lock cmpxchg [rsi+18h], rcx
0x10043269f  jnz     loc_100432D73
0x1004326a5  lfence
0x1004326a8  lock dec dword ptr [rsi+28h]
0x1004326ac  mov     rbp, rdx
0x1004326af  test    rbp, rbp
0x1004326b2  jz      loc_100432D83
0x1004326b8  mov     rsi, [rsp+0A8h+var_30]
0x1004326bd  mov     rbx, [rsp+0A8h+arg_10]
0x1004326c5  test    r12b, r12b
0x1004326c8  jnz     loc_100432CF1
0x1004326ce  mov     rdi, [rsp+0A8h+var_38]
0x1004326d3  mov     rax, rbp
0x1004326d6  mov     rbp, [rsp+0A8h+var_28]
0x1004326de  add     rsp, 88h
0x1004326e5  pop     r15
0x1004326e7  pop     r14
0x1004326e9  pop     r13
0x1004326eb  pop     r12
0x1004326ed  retn
0x100432728  lock dec dword ptr [rsi+28h]
0x10043272c  jmp     short loc_1004326B8
0x100432cf1  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x100432cf8  jz      loc_10049B6C6
0x100432cfe  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x100432d03  call    cs:__imp_QueryPerformanceCounter
0x100432d09  mov     rcx, qword ptr [rsp+0A8h+PerformanceCount]
0x100432d0e  jmp     short loc_100432D11
0x100432d11  cmp     rcx, rdi
0x100432d14  jb      loc_10049B6DC
0x100432d1a  sub     rcx, rdi
0x100432d1d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x100432d21  jz      loc_10049B6D4
0x100432d27  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x100432d2e  jz      loc_10049B6E4
0x100432d34  xor     edx, edx
0x100432d36  imul    rax, rcx, 3E8h
0x100432d3d  div     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x100432d44  mov     rdx, rax
0x100432d47  jmp     short loc_100432D4A
0x100432d4a  mov     rax, [r14+20h]
0x100432d4e  cmp     rdx, rax
0x100432d51  jbe     loc_1004326CE
0x100432d57  lock cmpxchg [r14+20h], rdx
0x100432d5d  jz      loc_1004326CE
0x100432d63  mov     rax, [r14+20h]
0x100432d67  cmp     rdx, rax
0x100432d6a  jbe     loc_1004326CE
0x100432d70  jmp     short loc_100432D57
0x100432d73  mov     rdx, [rsi+18h]
0x100432d77  test    rdx, rdx
0x100432d7a  jnz     loc_100432680
0x100432d80  jmp     short loc_100432D83
0x100432d83  mov     r10d, [rsp+0A8h+arg_8]
0x100432d8b  movzx   ecx, byte ptr [r14+4CCh]
0x100432d93  mov     edx, r10d
0x100432d96  shl     rdx, cl
0x100432d99  add     rdx, [r14+4C0h]
0x100432da0  mov     eax, r10d
0x100432da3  movzx   ebp, word ptr [rdx]
0x100432da6  cmp     bp, 40h ; '@'
0x100432daa  jnz     short loc_100432DD0
0x100432dac  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x100432db3  jz      loc_10049B558
0x100432db9  mov     ecx, eax
0x100432dbb  mov     rax, cs:?sm_CPUInfo@SOS_PublicGlobals@@2PEAVSOS_CPUInfo@@EA; SOS_CPUInfo * SOS_PublicGlobals::sm_CPUInfo
0x100432dc2  shl     rcx, 5
0x100432dc6  movzx   ebp, word ptr [rcx+rax]
0x100432dca  mov     [rdx], bp
0x100432dcd  jmp     short loc_100432DD0
0x100432dd0  movzx   r9d, bp
0x100432dd4  mov     [rsp+0A8h+var_88], r13b
0x100432dd9  mov     r8d, r10d
0x100432ddc  mov     rdx, rsi
0x100432ddf  mov     rcx, r14
0x100432de2  call    ?InstallPartialPageAsActive@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@AEAA_NPEAUPageDesc@1@IG_N@Z; DescriptorAllocator<SOS_MemoryFreeBlock,0>::InstallPartialPageAsActive(DescriptorAllocator<SOS_MemoryFreeBlock,0>::PageDesc *,uint,ushort,bool)
0x100432de7  test    al, al
0x100432de9  jnz     short loc_100432E14
0x100432deb  mov     r8d, [rsp+0A8h+arg_8]
0x100432df3  movzx   r9d, bp
0x100432df7  mov     [rsp+0A8h+var_80], r15
0x100432dfc  mov     rdx, rsi
0x100432dff  mov     rcx, r14
0x100432e02  mov     [rsp+0A8h+var_88], r13b
0x100432e07  call    ?InstallNewPageAsActive@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@AEAA_NPEAUPageDesc@1@IG_NPEAVWorker@@@Z; DescriptorAllocator<SOS_MemoryFreeBlock,0>::InstallNewPageAsActive(DescriptorAllocator<SOS_MemoryFreeBlock,0>::PageDesc *,uint,ushort,bool,Worker *)
0x100432e0c  test    al, al
0x100432e0e  jz      loc_10049B561
0x100432e14  mov     ebp, [rsp+0A8h+arg_0]
0x100432e1b  test    ebp, 1FFFh
0x100432e21  jz      loc_10049B573
0x100432e27  test    r12b, r12b
0x100432e2a  jnz     loc_100432ED4
0x100432e30  test    r15, r15
0x100432e33  jnz     short loc_100432E5E
0x100432e35  mov     rcx, gs:58h
0x100432e3e  mov     eax, cs:_tls_index
0x100432e44  mov     ebx, cs:SystemThread_TlsOffset
0x100432e4a  add     rbx, [rcx+rax*8]
0x100432e4e  mov     r15, [rbx+100h]
0x100432e55  test    r15, r15
0x100432e58  jz      loc_10049B652
0x100432e5e  test    dword ptr [r15+268h], 400h
0x100432e69  mov     ebx, 1D4C0h
0x100432e6e  mov     ecx, cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100432e74  mov     eax, 7530h
0x100432e79  cmovnz  ebx, eax
0x100432e7c  test    ecx, ecx
0x100432e7e  jz      loc_10049B666
0x100432e84  imul    rbx, cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x100432e8c  mov     rax, 624DD2F1A9FBE77h
0x100432e96  add     rbx, 3E7h
0x100432e9d  mul     rbx
0x100432ea0  sub     rbx, rdx
0x100432ea3  shr     rbx, 1
0x100432ea6  add     rbx, rdx
0x100432ea9  shr     rbx, 9
0x100432ead  jmp     short loc_100432EB0
0x100432eb0  test    ecx, ecx
0x100432eb2  jz      loc_10049B673
0x100432eb8  lea     rcx, [rsp+0A8h+arg_18]; lpPerformanceCount
0x100432ec0  call    cs:__imp_QueryPerformanceCounter
0x100432ec6  mov     rdi, qword ptr [rsp+0A8h+arg_18]
0x100432ece  jmp     short loc_100432ED1
0x100432ed1  mov     r12b, 1
0x100432ed4  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x100432edb  jz      loc_10049B681
0x100432ee1  lea     rcx, [rsp+0A8h+var_78]; lpPerformanceCount
0x100432ee6  call    cs:__imp_QueryPerformanceCounter
0x100432eec  mov     rax, qword ptr [rsp+0A8h+var_78]
0x100432ef1  jmp     short loc_100432EF4
0x100432ef4  cmp     rax, rdi
0x100432ef7  jb      loc_10049B68F
0x100432efd  sub     rax, rdi
0x100432f00  xor     r8d, r8d
0x100432f03  jmp     short loc_100432F06
0x100432f06  cmp     rax, rbx
0x100432f09  ja      loc_10049B6BB
0x100432f0f  mov     rax, [rsp+0A8h+var_70]
0x100432f14  inc     ebp
0x100432f16  mov     r10d, [rsp+0A8h+arg_8]
0x100432f1e  mov     [rsp+0A8h+arg_0], ebp
0x100432f25  jmp     loc_100432640
0x10049b53a  mov     r8, r9
0x10049b53d  mov     edx, r10d
0x10049b540  mov     rcx, r14
0x10049b543  add     rsp, 88h
0x10049b54a  pop     r15
0x10049b54c  pop     r14
0x10049b54e  pop     r13
0x10049b550  pop     r12
0x10049b552  jmp     ?PopWithAddr@?$DescriptorAllocator@VSOS_MemoryFreeBlock@@$0A@@@QEAAPEAVSOS_MemoryFreeBlock@@IPEAE@Z; DescriptorAllocator<SOS_MemoryFreeBlock,0>::PopWithAddr(uint,uchar *)
0x10049b558  mov     ebp, r8d
0x10049b55b  jmp     loc_100432DD0
0x10049b561  test    r13b, r13b
0x10049b564  jnz     loc_10049B69B
0x10049b56a  mov     r13b, 1
0x10049b56d  jmp     loc_100432E14
0x10049b573  mov     rcx, gs:58h
0x10049b57c  mov     eax, cs:_tls_index
0x10049b582  mov     esi, cs:SystemThread_TlsOffset
0x10049b588  add     rsi, [rcx+rax*8]
0x10049b58c  mov     rax, [rsi+100h]
0x10049b593  test    rax, rax
0x10049b596  jnz     short loc_10049B5A6
0x10049b598  xor     ecx, ecx; void *
0x10049b59a  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049b59f  mov     rax, [rsi+100h]
0x10049b5a6  test    byte ptr [rax+268h], 40h
0x10049b5ad  jnz     loc_10049B6B3
0x10049b5b3  mov     rcx, gs:58h
0x10049b5bc  mov     eax, cs:_tls_index
0x10049b5c2  mov     esi, cs:SystemThread_TlsOffset
0x10049b5c8  add     rsi, [rcx+rax*8]
0x10049b5cc  mov     rbp, [rsi+100h]
0x10049b5d3  test    rbp, rbp
0x10049b5d6  jnz     short loc_10049B5E6
0x10049b5d8  xor     ecx, ecx; void *
0x10049b5da  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049b5df  mov     rbp, [rsi+100h]
0x10049b5e6  rdtsc
0x10049b5e8  shl     rdx, 20h
0x10049b5ec  or      rax, rdx
0x10049b5ef  mov     rdx, [rbp+340h]
0x10049b5f6  cmp     rax, rdx
0x10049b5f9  ja      short loc_10049B61D
0x10049b5fb  mov     rcx, 7FFFFFFFFFFFFFFFh
0x10049b605  cmp     rdx, rcx
0x10049b608  jz      short loc_10049B645
0x10049b60a  mov     rcx, [rbp+260h]
0x10049b611  sub     rdx, rax
0x10049b614  cmp     rdx, [rcx+0DF0h]
0x10049b61b  jbe     short loc_10049B645
0x10049b61d  mov     esi, [rbp+268h]
0x10049b623  lea     rdx, ?yieldWait@@3VSOS_WaitInfo@@B; "c@"
0x10049b62a  mov     eax, esi
0x10049b62c  xor     ecx, ecx
0x10049b62e  or      eax, 1
0x10049b631  mov     [rbp+268h], eax
0x10049b637  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x10049b63c  or      esi, 0FFFFFFFEh
0x10049b63f  and     [rbp+268h], esi
0x10049b645  mov     ebp, [rsp+0A8h+arg_0]
0x10049b64c  jmp     loc_100432E27
0x10049b652  xor     ecx, ecx; void *
0x10049b654  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049b659  mov     r15, [rbx+100h]
0x10049b660  jmp     loc_100432E5E
0x10049b666  imul    rbx, 2710h
0x10049b66d  jmp     loc_100432EB0
0x10049b673  mov     rdi, ds:7FFE0008h
0x10049b67b  jmp     loc_100432ED1
0x10049b681  mov     rax, ds:7FFE0008h
0x10049b689  jmp     loc_100432EF4
0x10049b68f  xor     r8d, r8d
0x10049b692  mov     eax, r8d
0x10049b695  jmp     loc_100432F06
0x10049b69b  mov     [rsp+0A8h+var_50], 0Eh
0x10049b6a3  jmp     short loc_10049B6A6
0x10049b6a6  lea     r8, [rsp+0A8h+var_50]
0x10049b6ab  mov     rdx, r15
0x10049b6ae  call    ?RecordAllocationFailure@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@AEAAXPEAVWorker@@AEBUAllocationFailureInfo@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::RecordAllocationFailure(Worker *,AllocationFailureInfo const &)
0x10049b6b3  xor     ebp, ebp
0x10049b6b5  jmp     loc_1004326B8
0x10049b6bb  mov     [rsp+0A8h+var_50], 0Fh
0x10049b6c3  jmp     short loc_10049B6A6
0x10049b6c6  mov     rcx, ds:7FFE0008h
0x10049b6ce  jmp     loc_100432D11
0x10049b6d4  mov     rdx, rcx
0x10049b6d7  jmp     loc_100432D4A
0x10049b6dc  xor     ecx, ecx
0x10049b6de  jmp     loc_100432D27
0x10049b6e4  mov     rax, 346DC5D63886594Bh
0x10049b6ee  mul     rcx
0x10049b6f1  shr     rdx, 0Bh
0x10049b6f5  jmp     loc_100432D4A
```
