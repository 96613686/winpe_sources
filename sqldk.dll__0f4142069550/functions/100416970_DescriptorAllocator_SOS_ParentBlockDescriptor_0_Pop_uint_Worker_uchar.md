# DescriptorAllocator<SOS_ParentBlockDescriptor,0>::Pop(uint,Worker *,uchar *)

- ea: `0x100416970`
- end: `0x100416ab1`
- name: `?Pop@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAPEAVSOS_ParentBlockDescriptor@@IPEAVWorker@@PEAE@Z`
- size: `321`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1004167c0`
- `0x1004aab70`
- `0x1004aaf80`

## callees

- `0x100414400`
- `0x100416970`
- `0x1004360f0`
- `0x100437e40`
- `0x100438440`
- `0x10049bf60`
- `0x10049c010`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x100416a10`
- `KERNEL32!InterlockedPopEntrySList` at `0x100416a10`
- `KERNEL32!QueryPerformanceCounter` at `0x100437c32`
- `KERNEL32!QueryPerformanceCounter` at `0x100437dcf`
- `KERNEL32!QueryPerformanceCounter` at `0x100437df5`
- `KERNEL32!QueryPerformanceCounter` at `0x100437c32`
- `KERNEL32!QueryPerformanceCounter` at `0x100437dcf`
- `KERNEL32!QueryPerformanceCounter` at `0x100437df5`

## pseudocode

```c
__int64 __fastcall DescriptorAllocator<SOS_ParentBlockDescriptor,0>::Pop(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
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
  unsigned __int16 v17; // bp
  LARGE_INTEGER v18; // rcx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  unsigned __int64 j; // rax
  unsigned __int16 *v22; // rdx
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
            v15 = v14 + 144;
            if ( v14 + 144 == v12 )
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
              goto LABEL_28;
          }
        }
        if ( v13 )
          goto LABEL_12;
LABEL_28:
        v7 = a2;
      }
      v22 = (unsigned __int16 *)(*(_QWORD *)(a1 + 1216) + ((unsigned __int64)v7 << *(_BYTE *)(a1 + 1228)));
      v17 = *v22;
      if ( *v22 == 64 )
      {
        if ( (SOS_OS_sm_osProcessStatus & 1) != 0 )
        {
          v17 = *((_WORD *)SOS_PublicGlobals::sm_CPUInfo + 16 * v7);
          *v22 = v17;
        }
        else
        {
          v17 = 0;
        }
      }
      if ( !DescriptorAllocator<SOS_ParentBlockDescriptor,0>::InstallPartialPageAsActive(a1, v12, v7, v17, v6) )
      {
        LOBYTE(v36) = v6;
        if ( !DescriptorAllocator<SOS_ParentBlockDescriptor,0>::InstallNewPageAsActive(a1, v12, a2, v17, v36, a3) )
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
      v18 = PerformanceCount;
    }
    else
    {
      v18.QuadPart = MEMORY[0x7FFE0008];
    }
    if ( v18.QuadPart < (unsigned __int64)v11.QuadPart )
    {
      v19 = 0;
    }
    else
    {
      v19 = v18.QuadPart - v11.QuadPart;
      if ( v19 == -1 )
      {
        v20 = -1;
        goto LABEL_23;
      }
    }
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
      v20 = 1000 * v19 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    else
      v20 = v19 / 0x2710;
LABEL_23:
    for ( j = *(_QWORD *)(a1 + 32); v20 > j; j = *(_QWORD *)(a1 + 32) )
    {
      if ( j == _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 32), v20, j) )
        break;
    }
    return (__int64)v13;
  }
  return DescriptorAllocator<SOS_ParentBlockDescriptor,0>::PopWithAddr(a1, a2, a4);
}

```

## disassembly

```asm
0x100416970  mov     [rsp+arg_8], edx
0x100416974  push    r12
0x100416976  push    r13
0x100416978  push    r14
0x10041697a  push    r15
0x10041697c  sub     rsp, 88h
0x100416983  mov     r14, rcx
0x100416986  mov     eax, edx
0x100416988  movzx   ecx, byte ptr [rcx+4CCh]
0x10041698f  mov     r15, r8
0x100416992  xor     r8d, r8d
0x100416995  shl     rax, cl
0x100416998  xor     r13b, r13b
0x10041699b  mov     r10d, edx
0x10041699e  add     rax, [r14+4C0h]
0x1004169a5  xor     r12b, r12b
0x1004169a8  mov     [rsp+0A8h+var_70], rax
0x1004169ad  mov     [rsp+0A8h+var_50], r8d
0x1004169b2  mov     [rsp+0A8h+var_48], r8
0x1004169b7  mov     [rsp+0A8h+var_40], r8
0x1004169bc  test    r9, r9
0x1004169bf  jnz     loc_10049B6FB
0x1004169c5  mov     [rsp+0A8h+arg_10], rbx
0x1004169cd  mov     rbx, [rsp+0A8h+var_60]
0x1004169d2  mov     [rsp+0A8h+var_28], rbp
0x1004169da  mov     [rsp+0A8h+var_30], rsi
0x1004169df  mov     [rsp+0A8h+var_38], rdi
0x1004169e4  mov     rdi, [rsp+0A8h+var_58]
0x1004169e9  mov     [rsp+0A8h+arg_0], 1
0x1004169f4  nop     dword ptr [rax+00h]
0x1004169f8  nop     dword ptr [rax+rax+00000000h]
0x100416a00  mov     rsi, [rax+8]
0x100416a04  test    rsi, rsi
0x100416a07  jz      loc_100437CBA
0x100416a0d  mov     rcx, rsi; ListHead
0x100416a10  call    cs:__imp_InterlockedPopEntrySList
0x100416a16  mov     rbp, rax
0x100416a19  test    rax, rax
0x100416a1c  jnz     loc_10040D197
0x100416a22  xor     r8d, r8d
0x100416a25  mov     ebp, r8d
0x100416a28  mov     rdx, [rsi+18h]
0x100416a2c  test    rdx, rdx
0x100416a2f  jz      short loc_100416A72
0x100416a31  nop     dword ptr [rax]
0x100416a34  nop     dword ptr [rax+00h]
0x100416a38  nop     dword ptr [rax+rax+00000000h]
0x100416a40  mov     rbp, r8
0x100416a43  cmp     rdx, rsi
0x100416a46  jnb     short loc_100416A72
0x100416a48  lfence
0x100416a4b  lea     rcx, [rdx+90h]
0x100416a52  mov     rax, rdx
0x100416a55  cmp     rcx, rsi
0x100416a58  cmovz   rcx, r8
0x100416a5c  lock cmpxchg [rsi+18h], rcx
0x100416a62  jnz     loc_100437CA2
0x100416a68  lfence
0x100416a6b  lock dec dword ptr [rsi+28h]
0x100416a6f  mov     rbp, rdx
0x100416a72  test    rbp, rbp
0x100416a75  jz      loc_100437CB2
0x100416a7b  mov     rsi, [rsp+0A8h+var_30]
0x100416a80  mov     rbx, [rsp+0A8h+arg_10]
0x100416a88  test    r12b, r12b
0x100416a8b  jnz     loc_100437C20
0x100416a91  mov     rdi, [rsp+0A8h+var_38]
0x100416a96  mov     rax, rbp
0x100416a99  mov     rbp, [rsp+0A8h+var_28]
0x100416aa1  add     rsp, 88h
0x100416aa8  pop     r15
0x100416aaa  pop     r14
0x100416aac  pop     r13
0x100416aae  pop     r12
0x100416ab0  retn
0x10040d197  lock dec dword ptr [rsi+28h]
0x10040d19b  jmp     loc_100416A7B
0x100421b01  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x100421b08  jz      loc_10049B719
0x100421b0e  mov     ecx, eax
0x100421b10  mov     rax, cs:?sm_CPUInfo@SOS_PublicGlobals@@2PEAVSOS_CPUInfo@@EA; SOS_CPUInfo * SOS_PublicGlobals::sm_CPUInfo
0x100421b17  shl     rcx, 5
0x100421b1b  movzx   ebp, word ptr [rcx+rax]
0x100421b1f  mov     [rdx], bp
0x100421b22  jmp     loc_100437CDF
0x100437c20  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x100437c27  jz      loc_10049B887
0x100437c2d  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x100437c32  call    cs:__imp_QueryPerformanceCounter
0x100437c38  mov     rcx, qword ptr [rsp+0A8h+PerformanceCount]
0x100437c3d  jmp     short loc_100437C40
0x100437c40  cmp     rcx, rdi
0x100437c43  jb      loc_10049B89D
0x100437c49  sub     rcx, rdi
0x100437c4c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x100437c50  jz      loc_10049B895
0x100437c56  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x100437c5d  jz      loc_10049B8A5
0x100437c63  xor     edx, edx
0x100437c65  imul    rax, rcx, 3E8h
0x100437c6c  div     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x100437c73  mov     rdx, rax
0x100437c76  jmp     short loc_100437C79
0x100437c79  mov     rax, [r14+20h]
0x100437c7d  cmp     rdx, rax
0x100437c80  jbe     loc_100416A91
0x100437c86  lock cmpxchg [r14+20h], rdx
0x100437c8c  jz      loc_100416A91
0x100437c92  mov     rax, [r14+20h]
0x100437c96  cmp     rdx, rax
0x100437c99  jbe     loc_100416A91
0x100437c9f  jmp     short loc_100437C86
0x100437ca2  mov     rdx, [rsi+18h]
0x100437ca6  test    rdx, rdx
0x100437ca9  jnz     loc_100416A40
0x100437caf  jmp     short loc_100437CB2
0x100437cb2  mov     r10d, [rsp+0A8h+arg_8]
0x100437cba  movzx   ecx, byte ptr [r14+4CCh]
0x100437cc2  mov     edx, r10d
0x100437cc5  shl     rdx, cl
0x100437cc8  add     rdx, [r14+4C0h]
0x100437ccf  mov     eax, r10d
0x100437cd2  movzx   ebp, word ptr [rdx]
0x100437cd5  cmp     bp, 40h ; '@'
0x100437cd9  jz      loc_100421B01
0x100437cdf  movzx   r9d, bp
0x100437ce3  mov     [rsp+0A8h+var_88], r13b
0x100437ce8  mov     r8d, r10d
0x100437ceb  mov     rdx, rsi
0x100437cee  mov     rcx, r14
0x100437cf1  call    ?InstallPartialPageAsActive@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@AEAA_NPEAUPageDesc@1@IG_N@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::InstallPartialPageAsActive(DescriptorAllocator<SOS_ParentBlockDescriptor,0>::PageDesc *,uint,ushort,bool)
0x100437cf6  test    al, al
0x100437cf8  jnz     short loc_100437D23
0x100437cfa  mov     r8d, [rsp+0A8h+arg_8]
0x100437d02  movzx   r9d, bp
0x100437d06  mov     [rsp+0A8h+var_80], r15
0x100437d0b  mov     rdx, rsi
0x100437d0e  mov     rcx, r14
0x100437d11  mov     [rsp+0A8h+var_88], r13b
0x100437d16  call    ?InstallNewPageAsActive@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@AEAA_NPEAUPageDesc@1@IG_NPEAVWorker@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::InstallNewPageAsActive(DescriptorAllocator<SOS_ParentBlockDescriptor,0>::PageDesc *,uint,ushort,bool,Worker *)
0x100437d1b  test    al, al
0x100437d1d  jz      loc_10049B722
0x100437d23  mov     ebp, [rsp+0A8h+arg_0]
0x100437d2a  test    ebp, 1FFFh
0x100437d30  jz      loc_10049B734
0x100437d36  test    r12b, r12b
0x100437d39  jnz     loc_100437DE3
0x100437d3f  test    r15, r15
0x100437d42  jnz     short loc_100437D6D
0x100437d44  mov     rcx, gs:58h
0x100437d4d  mov     eax, cs:_tls_index
0x100437d53  mov     ebx, cs:SystemThread_TlsOffset
0x100437d59  add     rbx, [rcx+rax*8]
0x100437d5d  mov     r15, [rbx+100h]
0x100437d64  test    r15, r15
0x100437d67  jz      loc_10049B813
0x100437d6d  test    dword ptr [r15+268h], 400h
0x100437d78  mov     ebx, 1D4C0h
0x100437d7d  mov     ecx, cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100437d83  mov     eax, 7530h
0x100437d88  cmovnz  ebx, eax
0x100437d8b  test    ecx, ecx
0x100437d8d  jz      loc_10049B827
0x100437d93  imul    rbx, cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x100437d9b  mov     rax, 624DD2F1A9FBE77h
0x100437da5  add     rbx, 3E7h
0x100437dac  mul     rbx
0x100437daf  sub     rbx, rdx
0x100437db2  shr     rbx, 1
0x100437db5  add     rbx, rdx
0x100437db8  shr     rbx, 9
0x100437dbc  jmp     short loc_100437DBF
0x100437dbf  test    ecx, ecx
0x100437dc1  jz      loc_10049B834
0x100437dc7  lea     rcx, [rsp+0A8h+arg_18]; lpPerformanceCount
0x100437dcf  call    cs:__imp_QueryPerformanceCounter
0x100437dd5  mov     rdi, qword ptr [rsp+0A8h+arg_18]
0x100437ddd  jmp     short loc_100437DE0
0x100437de0  mov     r12b, 1
0x100437de3  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x100437dea  jz      loc_10049B842
0x100437df0  lea     rcx, [rsp+0A8h+var_78]; lpPerformanceCount
0x100437df5  call    cs:__imp_QueryPerformanceCounter
0x100437dfb  mov     rax, qword ptr [rsp+0A8h+var_78]
0x100437e00  jmp     short loc_100437E03
0x100437e03  cmp     rax, rdi
0x100437e06  jb      loc_10049B850
0x100437e0c  sub     rax, rdi
0x100437e0f  xor     r8d, r8d
0x100437e12  jmp     short loc_100437E15
0x100437e15  cmp     rax, rbx
0x100437e18  ja      loc_10049B87C
0x100437e1e  mov     rax, [rsp+0A8h+var_70]
0x100437e23  inc     ebp
0x100437e25  mov     r10d, [rsp+0A8h+arg_8]
0x100437e2d  mov     [rsp+0A8h+arg_0], ebp
0x100437e34  jmp     loc_100416A00
0x10049b6fb  mov     r8, r9
0x10049b6fe  mov     edx, r10d
0x10049b701  mov     rcx, r14
0x10049b704  add     rsp, 88h
0x10049b70b  pop     r15
0x10049b70d  pop     r14
0x10049b70f  pop     r13
0x10049b711  pop     r12
0x10049b713  jmp     ?PopWithAddr@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAPEAVSOS_ParentBlockDescriptor@@IPEAE@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::PopWithAddr(uint,uchar *)
0x10049b719  mov     ebp, r8d
0x10049b71c  jmp     loc_100437CDF
0x10049b722  test    r13b, r13b
0x10049b725  jnz     loc_10049B85C
0x10049b72b  mov     r13b, 1
0x10049b72e  jmp     loc_100437D23
0x10049b734  mov     rcx, gs:58h
0x10049b73d  mov     eax, cs:_tls_index
0x10049b743  mov     esi, cs:SystemThread_TlsOffset
0x10049b749  add     rsi, [rcx+rax*8]
0x10049b74d  mov     rax, [rsi+100h]
0x10049b754  test    rax, rax
0x10049b757  jnz     short loc_10049B767
0x10049b759  xor     ecx, ecx; void *
0x10049b75b  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049b760  mov     rax, [rsi+100h]
0x10049b767  test    byte ptr [rax+268h], 40h
0x10049b76e  jnz     loc_10049B874
0x10049b774  mov     rcx, gs:58h
0x10049b77d  mov     eax, cs:_tls_index
0x10049b783  mov     esi, cs:SystemThread_TlsOffset
0x10049b789  add     rsi, [rcx+rax*8]
0x10049b78d  mov     rbp, [rsi+100h]
0x10049b794  test    rbp, rbp
0x10049b797  jnz     short loc_10049B7A7
0x10049b799  xor     ecx, ecx; void *
0x10049b79b  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049b7a0  mov     rbp, [rsi+100h]
0x10049b7a7  rdtsc
0x10049b7a9  shl     rdx, 20h
0x10049b7ad  or      rax, rdx
0x10049b7b0  mov     rdx, [rbp+340h]
0x10049b7b7  cmp     rax, rdx
0x10049b7ba  ja      short loc_10049B7DE
0x10049b7bc  mov     rcx, 7FFFFFFFFFFFFFFFh
0x10049b7c6  cmp     rdx, rcx
0x10049b7c9  jz      short loc_10049B806
0x10049b7cb  mov     rcx, [rbp+260h]
0x10049b7d2  sub     rdx, rax
0x10049b7d5  cmp     rdx, [rcx+0DF0h]
0x10049b7dc  jbe     short loc_10049B806
0x10049b7de  mov     esi, [rbp+268h]
0x10049b7e4  lea     rdx, ?yieldWait@@3VSOS_WaitInfo@@B; "c@"
0x10049b7eb  mov     eax, esi
0x10049b7ed  xor     ecx, ecx
0x10049b7ef  or      eax, 1
0x10049b7f2  mov     [rbp+268h], eax
0x10049b7f8  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x10049b7fd  or      esi, 0FFFFFFFEh
0x10049b800  and     [rbp+268h], esi
0x10049b806  mov     ebp, [rsp+0A8h+arg_0]
0x10049b80d  jmp     loc_100437D36
0x10049b813  xor     ecx, ecx; void *
0x10049b815  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049b81a  mov     r15, [rbx+100h]
0x10049b821  jmp     loc_100437D6D
0x10049b827  imul    rbx, 2710h
0x10049b82e  jmp     loc_100437DBF
0x10049b834  mov     rdi, ds:7FFE0008h
0x10049b83c  jmp     loc_100437DE0
0x10049b842  mov     rax, ds:7FFE0008h
0x10049b84a  jmp     loc_100437E03
0x10049b850  xor     r8d, r8d
0x10049b853  mov     eax, r8d
0x10049b856  jmp     loc_100437E15
0x10049b85c  mov     [rsp+0A8h+var_50], 0Eh
0x10049b864  jmp     short loc_10049B867
0x10049b867  lea     r8, [rsp+0A8h+var_50]
0x10049b86c  mov     rdx, r15
0x10049b86f  call    ?RecordAllocationFailure@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@AEAAXPEAVWorker@@AEBUAllocationFailureInfo@@@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::RecordAllocationFailure(Worker *,AllocationFailureInfo const &)
0x10049b874  xor     ebp, ebp
0x10049b876  jmp     loc_100416A7B
0x10049b87c  mov     [rsp+0A8h+var_50], 0Fh
0x10049b884  jmp     short loc_10049B867
0x10049b887  mov     rcx, ds:7FFE0008h
0x10049b88f  jmp     loc_100437C40
0x10049b895  mov     rdx, rcx
0x10049b898  jmp     loc_100437C79
0x10049b89d  xor     ecx, ecx
0x10049b89f  jmp     loc_100437C56
0x10049b8a5  mov     rax, 346DC5D63886594Bh
0x10049b8af  mul     rcx
0x10049b8b2  shr     rdx, 0Bh
0x10049b8b6  jmp     loc_100437C79
```
