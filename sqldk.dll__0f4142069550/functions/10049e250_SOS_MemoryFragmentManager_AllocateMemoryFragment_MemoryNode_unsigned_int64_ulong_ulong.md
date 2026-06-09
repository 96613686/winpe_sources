# SOS_MemoryFragmentManager::AllocateMemoryFragment(MemoryNode *,unsigned __int64,ulong,ulong)

- ea: `0x10049e250`
- end: `0x10049e926`
- name: `?AllocateMemoryFragment@SOS_MemoryFragmentManager@@AEAAPEAVSOS_MemoryFragmentDescriptor@@PEAVMemoryNode@@_KKK@Z`
- size: `1750`
- prototype: `struct SOS_MemoryFragmentDescriptor *__usercall@<rax>(SOS_MemoryFragmentManager *__hidden this@<rcx>, struct MemoryNode *@<rdx>, unsigned __int64@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10049e930`

## callees

- `0x100403070`
- `0x100413dc0`
- `0x100413e30`
- `0x100426a00`
- `0x1004360f0`
- `0x100495330`
- `0x10049dbe0`
- `0x10049dea0`
- `0x10049e250`
- `0x10049ef50`
- `0x1004a1d90`
- `0x1004a22c0`
- `0x1004a2520`
- `0x1004a3f10`
- `0x1004b3cd0`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x10049e55e`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049e5a1`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049e7d8`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049e55e`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049e5a1`
- `KERNEL32!InterlockedPushEntrySList` at `0x10049e7d8`
- `KERNEL32!VirtualQuery` at `0x10049e4d0`
- `KERNEL32!VirtualQuery` at `0x10049e4d0`
- `KERNEL32!CreateFileMappingNumaW` at `0x10049e5ea`
- `KERNEL32!CreateFileMappingNumaW` at `0x10049e5ea`
- `KERNEL32!CloseHandle` at `0x10049e656`
- `KERNEL32!CloseHandle` at `0x10049e739`
- `KERNEL32!CloseHandle` at `0x10049e656`
- `KERNEL32!CloseHandle` at `0x10049e739`
- `KERNEL32!GetLastError` at `0x10049e50c`
- `KERNEL32!GetLastError` at `0x10049e50c`
- `KERNEL32!GetCurrentProcess` at `0x10049e815`
- `KERNEL32!GetCurrentProcess` at `0x10049e815`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _SLIST_ENTRY *__fastcall SOS_MemoryFragmentManager::AllocateMemoryFragment(
        union _SLIST_HEADER *this,
        struct MemoryNode *a2,
        SIZE_T a3,
        int a4,
        unsigned int a5)
{
  PSLIST_HEADER v6; // rsi
  unsigned int v7; // r12d
  char *v8; // rdi
  SIZE_T v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rax
  struct _SLIST_ENTRY *result; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  SOS_MemoryFragmentManager *v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned int v20; // r12d
  SIZE_T v21; // r13
  bool v22; // zf
  SIZE_T v23; // rcx
  int v24; // eax
  int v25; // ecx
  unsigned int v26; // eax
  char *v27; // rbx
  unsigned __int64 v28; // rsi
  DWORD LastError; // eax
  PSLIST_ENTRY v30; // r13
  struct SOS_SharedMemoryContext *v31; // rsi
  HANDLE FileMappingNumaW; // rbx
  _QWORD *v33; // r9
  _WORD *v34; // rcx
  __int64 v35; // rdx
  __int16 v36; // ax
  _WORD *v37; // rax
  void (*v38)(const wchar_t *, ...); // rax
  void *v39; // rbx
  __int64 v40; // r8
  struct _SLIST_ENTRY *v41; // rbx
  unsigned __int64 v42; // rsi
  PSLIST_HEADER v43; // rbx
  struct _SLIST_ENTRY *v44; // r8
  union _SLIST_HEADER *v45; // rdx
  union _SLIST_HEADER *i; // rcx
  __int64 v47; // rcx
  void (*v48)(const wchar_t *, ...); // rax
  void (*v49)(const wchar_t *, ...); // rax
  __int64 v50; // rbx
  __int64 v51; // rcx
  unsigned int v52; // edx
  signed __int32 v53[8]; // [rsp+0h] [rbp-100h] BYREF
  int v54; // [rsp+70h] [rbp-90h]
  unsigned int v55; // [rsp+74h] [rbp-8Ch]
  int v56; // [rsp+78h] [rbp-88h]
  PSLIST_HEADER ListHead; // [rsp+80h] [rbp-80h]
  int v58; // [rsp+88h] [rbp-78h]
  unsigned int v59; // [rsp+8Ch] [rbp-74h]
  SIZE_T v60; // [rsp+90h] [rbp-70h]
  __int64 v61; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-60h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+A8h] [rbp-58h]
  unsigned int v64; // [rsp+B0h] [rbp-50h]
  BOOL v65; // [rsp+B4h] [rbp-4Ch]
  __int64 v66; // [rsp+B8h] [rbp-48h] BYREF
  char v67; // [rsp+C0h] [rbp-40h]
  __int64 v68; // [rsp+C8h] [rbp-38h]
  __int64 v69; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v70; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v71[6]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v72; // [rsp+110h] [rbp+10h]
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+130h] [rbp+30h] BYREF
  WCHAR Name[264]; // [rsp+160h] [rbp+60h] BYREF
  wchar_t v75[264]; // [rsp+370h] [rbp+270h] BYREF

  v68 = -2;
  v56 = a4;
  v60 = a3;
  v6 = this;
  ListHead = this;
  v59 = a5;
  v7 = 0;
  v8 = 0;
  v9 = a3;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
      + (unsigned int)SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  result = (struct _SLIST_ENTRY *)DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::Pop(
                                    &SOS_MemoryFragmentManager::sm_MemoryFragmentDescriptorAllocator,
                                    *(unsigned int *)(v11 + 76),
                                    v11,
                                    0);
  ListEntry = result;
  if ( !result )
    return result;
  v13 = 32LL * *((unsigned __int16 *)a2 + 64);
  if ( *(_DWORD *)((char *)&SOS_PublicGlobals::sm_MemoryNodeInfo + v13 + 24) )
  {
    _BitScanForward64(
      &v14,
      ~(*(unsigned __int64 *)((char *)&SOS_PublicGlobals::sm_MemoryNodeInfo + v13 + 8) - 1)
    & *(unsigned __int64 *)((char *)&SOS_PublicGlobals::sm_MemoryNodeInfo + v13 + 8));
    v58 = v14;
    v7 = *((_DWORD *)SOS_OS::sm_AffinityToCPUInfo
         + 64 * *(unsigned __int16 *)((char *)&SOS_PublicGlobals::sm_MemoryNodeInfo + v13 + 16)
         + (unsigned int)v14);
  }
  v55 = v7;
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
      + (unsigned int)SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  v54 = *(_DWORD *)(v16 + 76);
  AutoDisableWorkerStealing::AutoDisableWorkerStealing((AutoDisableWorkerStealing *)&v66);
  v65 = v7 != v54;
  if ( v7 != v54 )
  {
    v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
        + (unsigned int)SystemThread_TlsOffset;
    v19 = *(_QWORD *)(v18 + 256);
    if ( !v19 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v19 = *(_QWORD *)(v18 + 256);
    }
    *(_DWORD *)(v19 + 76) = v7;
    v64 = SystemThread::ChangeCPUId(*(SystemThread **)(v19 + 624), v7);
  }
  if ( *((_DWORD *)&v6[1].HeaderX64 + 2) == 4 )
  {
    SOS_MemoryFragmentManager::InitializeSharedMemoryNames(v17, v75, 0x104u, Name, 0x104u);
    v8 = SOS_MemoryFragmentManager::OpenSharedMemoryContextAndFragment((SOS_MemoryFragmentManager *)v6, a2, v75, Name);
  }
  v20 = 8;
  v21 = v60;
  while ( 1 )
  {
    v22 = v8 == 0;
    if ( v8 )
      break;
    v23 = v20 * (v21 >> 3);
    if ( v9 < v23 )
      v23 = v9;
    v9 = ((v23 + 0xFFFFFF) & 0xFFFFFFFFFF000000uLL) + 0x1000000;
    v24 = *((_DWORD *)&v6[1].HeaderX64 + 2);
    if ( v24 == 1 )
    {
      v25 = dword_10072F380;
      do
      {
        v26 = v25 & 0xFFFFFFFE;
        v72 = xmmword_10072F360;
        _InterlockedOr(v53, 0);
        v25 = dword_10072F380;
      }
      while ( v26 != dword_10072F380 );
      v27 = 0;
      v8 = 0;
      v28 = *((_QWORD *)&v72 + 1);
      do
      {
        v27 += 0x8000000000LL;
        if ( VirtualQuery(v27, &Buffer, 0x30u) != 48 || Buffer.State == 0x10000 && Buffer.RegionSize >= v9 )
        {
          v8 = (char *)MemoryNode::AllocateLargePageBuffer(a2, 0, v27, v9, &v69, 0);
          LastError = GetLastError();
          if ( v8 || LastError != 487 )
            break;
        }
      }
      while ( (unsigned __int64)v27 < v28 );
      v21 = v60;
    }
    else
    {
      if ( v24 != 4 )
      {
        v8 = (char *)MemoryNode::VirtualAllocNativeNoCheck(
                       a2,
                       0,
                       0,
                       ((v23 + 0xFFFFFF) & 0xFFFFFFFFFF000000uLL) + 0x1000000,
                       v56,
                       v59,
                       0,
                       0,
                       0,
                       0);
        goto LABEL_30;
      }
      v31 = SOS_OS_SharedMemoryContext;
      FileMappingNumaW = CreateFileMappingNumaW(
                           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                           0,
                           0x4000004u,
                           HIDWORD(v9),
                           ((v23 + 0xFFFFFF) & 0xFF000000) + 0x1000000,
                           Name,
                           0xFFFFFFFF);
      if ( !FileMappingNumaW )
      {
        v8 = 0;
LABEL_51:
        if ( v20 <= 5 )
        {
          v38 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
          if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
            v38 = SOS_OS_LogUnlocalizedRoutine;
          v38(L"Unable to allocate shared memory. Reverting to conventional memory.");
          if ( SOS_OS_SharedMemoryContext )
          {
            v39 = *(void **)SOS_OS_SharedMemoryContext;
            v40 = 560LL * *((int *)SOS_OS_SharedMemoryContext + 4) + 1104;
            MemoryNode::UnmapViewOfFile(a2, SOS_OS_SharedMemoryContext, v40, v40, 0, 0);
            CloseHandle(v39);
            SOS_OS_SharedMemoryContext = 0;
          }
          v6 = ListHead;
          *((_DWORD *)&ListHead[1].HeaderX64 + 2) = 3;
          v20 = 9;
          goto LABEL_30;
        }
        goto LABEL_29;
      }
      v8 = (char *)MemoryNode::MapViewOfFileEx(
                     a2,
                     FileMappingNumaW,
                     0xF001Fu,
                     0,
                     0,
                     v9,
                     0,
                     0x4000004u,
                     v71,
                     &v70,
                     0xFFFFFFFF,
                     0,
                     0);
      if ( !v8 )
      {
        CloseHandle(FileMappingNumaW);
        goto LABEL_51;
      }
      v33 = (_QWORD *)((char *)v31 + 544);
      if ( *((int *)v31 + 3) <= 0 )
        v33 = 0;
      *v33 = FileMappingNumaW;
      v34 = v33 + 5;
      v35 = 260;
      do
      {
        if ( v35 == -2147483386 )
          break;
        v36 = *(_WORD *)((char *)v34 + (char *)Name - (char *)(v33 + 5));
        if ( !v36 )
          break;
        *v34++ = v36;
        --v35;
      }
      while ( v35 );
      v37 = v34 - 1;
      if ( v35 )
        v37 = v34;
      *v37 = 0;
      v33[2] = v8;
      v33[1] = 0;
      v33[3] = v9;
      v33[4] = 0;
    }
LABEL_29:
    v6 = ListHead;
LABEL_30:
    if ( !--v20 )
    {
      v22 = v8 == 0;
      break;
    }
  }
  v30 = ListEntry;
  if ( v22 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)ListEntry & 0xFFFFFFFFFFFFE000uLL) + 8152));
    InterlockedPushEntrySList((PSLIST_HEADER)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFE000uLL) + 8112), v30 + 1);
    if ( *(_DWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFE000uLL) + 0x1FE0) == 1
      && _InterlockedCompareExchange(
           (volatile signed __int32 *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFE000uLL) + 8160),
           2,
           1) == 1 )
    {
      InterlockedPushEntrySList(
        (PSLIST_HEADER)&qword_1007B2DC0[24
                                      * *(unsigned __int16 *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFE000uLL) + 0x1FDC)
                                      + 2
                                      * (*(_DWORD *)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFE000uLL) + 0x1FD8)
                                       / 0x2Bu)],
        (PSLIST_ENTRY)(((unsigned __int64)v30 & 0xFFFFFFFFFFFFE000uLL) + 8128));
    }
    v30 = 0;
    goto LABEL_73;
  }
  v41 = (struct _SLIST_ENTRY *)((unsigned __int64)(v8 + 0xFFFFFF) & 0xFFFFFFFFFF000000uLL);
  v42 = v9 - 0x1000000;
  if ( v8 == (char *)v41 )
  {
    v42 = v9;
    v41 = (struct _SLIST_ENTRY *)v8;
  }
  if ( !PageExclusionBitmap::CommitBitmap(v41, v42) )
  {
    v62 = 0;
    v61 = 0;
    GetCurrentProcess();
    if ( (unsigned int)SOS_OS::GetVMOsRegionInfo(v47, v8, &v62, &v61) )
    {
      v48 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
      if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
        v48 = SOS_OS_LogUnlocalizedRoutine;
      v48(L"Failed to query VM region info: address 0x%p", v8);
    }
    else if ( !(unsigned int)MemoryNode::VirtualFreeNativeNoCheck(a2, v8, 0, 0x8000, v62, v61, 0, 0) )
    {
LABEL_72:
      v30 = 0;
      goto LABEL_73;
    }
    v49 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v49 = SOS_OS_LogUnlocalizedRoutine;
    v49(L"Failed to release virtual memory.\n");
    goto LABEL_72;
  }
  v30[2].Next = v41;
  *((_QWORD *)&v30[2].Next + 1) = v42;
  v43 = ListHead;
  _InterlockedIncrement((volatile signed __int32 *)&ListHead[1].HeaderX64 + 3);
  InterlockedPushEntrySList(v43, v30);
  v44 = v30 + 1;
  v45 = v43 + 1;
  for ( i = (union _SLIST_HEADER *)v43[1].Alignment; i; i = (union _SLIST_HEADER *)i->Alignment )
    v45 = i;
  v44->Next = 0;
  v45->Alignment = (ULONGLONG)v44;
LABEL_73:
  if ( v55 != v54 )
  {
    v50 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
        + (unsigned int)SystemThread_TlsOffset;
    v51 = *(_QWORD *)(v50 + 256);
    if ( !v51 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v51 = *(_QWORD *)(v50 + 256);
    }
    v52 = v64;
    *(_DWORD *)(v51 + 76) = v64;
    SystemThread::ChangeCPUId(*(SystemThread **)(v51 + 624), v52);
  }
  if ( v67 )
    *(_DWORD *)(v66 + 800) |= 0x1000000u;
  return v30;
}

```

## disassembly

```asm
0x10049e250  push    rbp
0x10049e252  push    rbx
0x10049e253  push    rsi
0x10049e254  push    rdi
0x10049e255  push    r12
0x10049e257  push    r13
0x10049e259  push    r14
0x10049e25b  push    r15
0x10049e25d  lea     rbp, [rsp-498h]
0x10049e265  sub     rsp, 598h
0x10049e26c  mov     [rbp+4D0h+var_508], 0FFFFFFFFFFFFFFFEh
0x10049e274  mov     rax, cs:__security_cookie
0x10049e27b  xor     rax, rsp
0x10049e27e  mov     [rbp+4D0h+var_50], rax
0x10049e285  mov     [rsp+5D0h+var_558], r9d
0x10049e28a  mov     [rbp+4D0h+var_540], r8
0x10049e28e  mov     r15, rdx
0x10049e291  mov     rsi, rcx
0x10049e294  mov     [rbp+4D0h+ListHead], rcx
0x10049e298  mov     ecx, [rbp+4D0h+arg_20]
0x10049e29e  mov     [rbp+4D0h+var_544], ecx
0x10049e2a1  xor     r12d, r12d
0x10049e2a4  mov     edi, r12d
0x10049e2a7  mov     r14, r8
0x10049e2aa  mov     rcx, gs:58h
0x10049e2b3  mov     eax, cs:_tls_index
0x10049e2b9  mov     ebx, cs:SystemThread_TlsOffset
0x10049e2bf  add     rbx, [rcx+rax*8]
0x10049e2c3  mov     rax, [rbx+100h]
0x10049e2ca  test    rax, rax
0x10049e2cd  jnz     short loc_10049E2DD
0x10049e2cf  xor     ecx, ecx; void *
0x10049e2d1  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049e2d6  mov     rax, [rbx+100h]
0x10049e2dd  xor     r9d, r9d
0x10049e2e0  mov     r8, rax
0x10049e2e3  mov     edx, [rax+4Ch]
0x10049e2e6  lea     rcx, ?sm_MemoryFragmentDescriptorAllocator@SOS_MemoryFragmentManager@@2V?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@A; DescriptorAllocator<SOS_MemoryFragmentDescriptor,16> SOS_MemoryFragmentManager::sm_MemoryFragmentDescriptorAllocator
0x10049e2ed  call    ?Pop@?$DescriptorAllocator@VSOS_MemoryFragmentDescriptor@@$0BA@@@QEAAPEAVSOS_MemoryFragmentDescriptor@@IPEAVWorker@@PEAE@Z; DescriptorAllocator<SOS_MemoryFragmentDescriptor,16>::Pop(uint,Worker *,uchar *)
0x10049e2f2  mov     [rbp+4D0h+ListEntry], rax
0x10049e2f6  test    rax, rax
0x10049e2f9  jz      loc_10049E903
0x10049e2ff  movzx   edx, word ptr [r15+80h]
0x10049e307  shl     rdx, 5
0x10049e30b  lea     r8, ?sm_MemoryNodeInfo@SOS_PublicGlobals@@2PAVSOS_MemoryNodeInfo@@A; SOS_MemoryNodeInfo near * SOS_PublicGlobals::sm_MemoryNodeInfo
0x10049e312  cmp     [rdx+r8+18h], r12d
0x10049e317  jz      short loc_10049E349
0x10049e319  mov     rcx, [rdx+r8+8]
0x10049e31e  lea     rax, [rcx-1]
0x10049e322  not     rax
0x10049e325  and     rcx, rax
0x10049e328  bsf     rax, rcx
0x10049e32c  mov     [rbp+4D0h+var_548], eax
0x10049e32f  movzx   ecx, word ptr [rdx+r8+10h]
0x10049e335  shl     rcx, 6
0x10049e339  add     rcx, rax
0x10049e33c  mov     ecx, ecx
0x10049e33e  mov     rax, cs:?sm_AffinityToCPUInfo@SOS_OS@@0PEAKEA; ulong * SOS_OS::sm_AffinityToCPUInfo
0x10049e345  mov     r12d, [rax+rcx*4]
0x10049e349  mov     [rsp+5D0h+var_55C], r12d
0x10049e34e  mov     rcx, gs:58h
0x10049e357  mov     eax, cs:_tls_index
0x10049e35d  mov     ebx, cs:SystemThread_TlsOffset
0x10049e363  add     rbx, [rcx+rax*8]
0x10049e367  mov     rax, [rbx+100h]
0x10049e36e  test    rax, rax
0x10049e371  jnz     short loc_10049E381
0x10049e373  xor     ecx, ecx; void *
0x10049e375  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049e37a  mov     rax, [rbx+100h]
0x10049e381  mov     eax, [rax+4Ch]
0x10049e384  mov     [rsp+5D0h+var_560], eax
0x10049e388  xor     ecx, ecx
0x10049e38a  mov     ebx, ecx
0x10049e38c  cmp     r12d, eax
0x10049e38f  setnz   bl
0x10049e392  lea     rcx, [rbp+4D0h+var_518]; this
0x10049e396  call    ??0AutoDisableWorkerStealing@@QEAA@XZ; AutoDisableWorkerStealing::AutoDisableWorkerStealing(void)
0x10049e39b  nop
0x10049e39c  mov     [rbp+4D0h+var_51C], ebx
0x10049e39f  cmp     r12d, [rsp+5D0h+var_560]
0x10049e3a4  jz      short loc_10049E3ED
0x10049e3a6  mov     rcx, gs:58h
0x10049e3af  mov     eax, cs:_tls_index
0x10049e3b5  mov     ebx, cs:SystemThread_TlsOffset
0x10049e3bb  add     rbx, [rcx+rax*8]
0x10049e3bf  mov     rcx, [rbx+100h]; void *
0x10049e3c6  test    rcx, rcx
0x10049e3c9  jnz     short loc_10049E3D7
0x10049e3cb  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049e3d0  mov     rcx, [rbx+100h]
0x10049e3d7  mov     [rcx+4Ch], r12d
0x10049e3db  mov     edx, r12d; unsigned int
0x10049e3de  mov     rcx, [rcx+270h]; this
0x10049e3e5  call    ?ChangeCPUId@SystemThread@@QEAAKK@Z; SystemThread::ChangeCPUId(ulong)
0x10049e3ea  mov     [rbp+4D0h+var_520], eax
0x10049e3ed  cmp     dword ptr [rsi+18h], 4
0x10049e3f1  jnz     short loc_10049E42B
0x10049e3f3  mov     qword ptr [rsp+5D0h+dwMaximumSizeLow], 104h; unsigned __int64
0x10049e3fc  lea     r9, [rbp+4D0h+Name]; wchar_t *
0x10049e400  mov     r8d, 104h; unsigned __int64
0x10049e406  lea     rdx, [rbp+4D0h+var_260]; wchar_t *
0x10049e40d  call    ?InitializeSharedMemoryNames@SOS_MemoryFragmentManager@@AEAAXPEA_W_K01@Z; SOS_MemoryFragmentManager::InitializeSharedMemoryNames(wchar_t *,unsigned __int64,wchar_t *,unsigned __int64)
0x10049e412  lea     r9, [rbp+4D0h+Name]; wchar_t *
0x10049e416  lea     r8, [rbp+4D0h+var_260]; wchar_t *
0x10049e41d  mov     rdx, r15; struct MemoryNode *
0x10049e420  mov     rcx, rsi; this
0x10049e423  call    ?OpenSharedMemoryContextAndFragment@SOS_MemoryFragmentManager@@AEAAPEAXPEAVMemoryNode@@PEA_W1@Z; SOS_MemoryFragmentManager::OpenSharedMemoryContextAndFragment(MemoryNode *,wchar_t *,wchar_t *)
0x10049e428  mov     rdi, rax
0x10049e42b  mov     r12d, 8
0x10049e431  mov     r13, [rbp+4D0h+var_540]
0x10049e435  test    rdi, rdi
0x10049e438  jnz     loc_10049E538
0x10049e43e  mov     rcx, r13
0x10049e441  shr     rcx, 3
0x10049e445  mov     eax, r12d
0x10049e448  imul    rcx, rax
0x10049e44c  cmp     r14, rcx
0x10049e44f  cmovb   rcx, r14
0x10049e453  lea     r14, [rcx+0FFFFFFh]
0x10049e45a  and     r14, 0FFFFFFFFFF000000h
0x10049e461  add     r14, 1000000h
0x10049e468  mov     eax, [rsi+18h]
0x10049e46b  cmp     eax, 1
0x10049e46e  jnz     loc_10049E5B1
0x10049e474  mov     ecx, cs:dword_10072F380
0x10049e47a  nop     word ptr [rax+rax+00h]
0x10049e480  and     ecx, 0FFFFFFFEh
0x10049e483  mov     eax, ecx
0x10049e485  movaps  xmm0, cs:xmmword_10072F360
0x10049e48c  movaps  [rbp+4D0h+var_4C0], xmm0
0x10049e490  lock or [rsp+5D0h+var_5D0], 0
0x10049e495  mov     ecx, cs:dword_10072F380
0x10049e49b  cmp     eax, ecx
0x10049e49d  jnz     short loc_10049E480
0x10049e49f  xor     eax, eax
0x10049e4a1  mov     ebx, eax
0x10049e4a3  mov     edi, eax
0x10049e4a5  mov     rsi, qword ptr [rbp+4D0h+var_4C0+8]
0x10049e4a9  mov     r13, 8000000000h
0x10049e4b3  nop     dword ptr [rax+00h]
0x10049e4b7  nop     word ptr [rax+rax+00000000h]
0x10049e4c0  add     rbx, r13
0x10049e4c3  mov     r8d, 30h ; '0'; dwLength
0x10049e4c9  lea     rdx, [rbp+4D0h+Buffer]; lpBuffer
0x10049e4cd  mov     rcx, rbx; lpAddress
0x10049e4d0  call    cs:__imp_VirtualQuery
0x10049e4d6  cmp     rax, 30h ; '0'
0x10049e4da  jnz     short loc_10049E4EB
0x10049e4dc  cmp     [rbp+4D0h+Buffer.State], 10000h
0x10049e4e3  jnz     short loc_10049E51E
0x10049e4e5  cmp     [rbp+4D0h+Buffer.RegionSize], r14
0x10049e4e9  jb      short loc_10049E51E
0x10049e4eb  mov     byte ptr [rsp+5D0h+lpName], 0; bool
0x10049e4f0  lea     rax, [rbp+4D0h+var_500]
0x10049e4f4  mov     qword ptr [rsp+5D0h+dwMaximumSizeLow], rax; __int64 *
0x10049e4f9  mov     r9, r14; unsigned __int64
0x10049e4fc  mov     r8, rbx; void *
0x10049e4ff  xor     edx, edx; void *
0x10049e501  mov     rcx, r15; this
0x10049e504  call    ?AllocateLargePageBuffer@MemoryNode@@AEAAPEAXPEAX0_KPEA_J_N@Z; MemoryNode::AllocateLargePageBuffer(void *,void *,unsigned __int64,__int64 *,bool)
0x10049e509  mov     rdi, rax
0x10049e50c  call    cs:__imp_GetLastError
0x10049e512  test    rdi, rdi
0x10049e515  jnz     short loc_10049E523
0x10049e517  cmp     eax, 1E7h
0x10049e51c  jnz     short loc_10049E523
0x10049e51e  cmp     rbx, rsi
0x10049e521  jb      short loc_10049E4C0
0x10049e523  mov     r13, [rbp+4D0h+var_540]
0x10049e527  mov     rsi, [rbp+4D0h+ListHead]
0x10049e52b  add     r12d, 0FFFFFFFFh
0x10049e52f  jnz     loc_10049E435
0x10049e535  test    rdi, rdi
0x10049e538  mov     r13, [rbp+4D0h+ListEntry]
0x10049e53c  jnz     loc_10049E793
0x10049e542  mov     rbx, r13
0x10049e545  and     rbx, 0FFFFFFFFFFFFE000h
0x10049e54c  add     rbx, 1FB0h
0x10049e553  lock inc dword ptr [rbx+28h]
0x10049e557  lea     rdx, [r13+10h]; ListEntry
0x10049e55b  mov     rcx, rbx; ListHead
0x10049e55e  call    cs:__imp_InterlockedPushEntrySList
0x10049e564  mov     eax, [rbx+30h]
0x10049e567  cmp     eax, 1
0x10049e56a  jnz     short loc_10049E5A7
0x10049e56c  mov     ecx, 2
0x10049e571  lock cmpxchg [rbx+30h], ecx
0x10049e576  jnz     short loc_10049E5A7
0x10049e578  mov     eax, 2FA0BE83h
0x10049e57d  mul     dword ptr [rbx+28h]
0x10049e580  shr     edx, 3
0x10049e583  movzx   eax, word ptr [rbx+2Ch]
0x10049e587  lea     rcx, [rax+rax*2]
0x10049e58b  lea     rcx, [rdx+rcx*4]
0x10049e58f  shl     rcx, 4
0x10049e593  lea     rax, qword_1007B2DC0
0x10049e59a  add     rcx, rax; ListHead
0x10049e59d  lea     rdx, [rbx+10h]; ListEntry
0x10049e5a1  call    cs:__imp_InterlockedPushEntrySList
0x10049e5a7  xor     ecx, ecx
0x10049e5a9  mov     r13d, ecx
0x10049e5ac  jmp     loc_10049E89E
0x10049e5b1  mov     r9, r14
0x10049e5b4  xor     edx, edx; lpFileMappingAttributes
0x10049e5b6  cmp     eax, 4
0x10049e5b9  jnz     loc_10049E75C
0x10049e5bf  mov     rsi, cs:?SOS_OS_SharedMemoryContext@@3PEAVSOS_SharedMemoryContext@@EA; SOS_SharedMemoryContext * SOS_OS_SharedMemoryContext
0x10049e5c6  shr     r9, 20h; dwMaximumSizeHigh
0x10049e5ca  mov     [rsp+5D0h+nndPreferred], 0FFFFFFFFh; nndPreferred
0x10049e5d2  lea     rcx, [rbp+4D0h+Name]
0x10049e5d6  mov     [rsp+5D0h+lpName], rcx; lpName
0x10049e5db  mov     [rsp+5D0h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x10049e5e0  lea     rcx, [rdx-1]; hFile
0x10049e5e4  mov     r8d, 4000004h; flProtect
0x10049e5ea  call    cs:__imp_CreateFileMappingNumaW
0x10049e5f0  mov     rbx, rax
0x10049e5f3  test    rax, rax
0x10049e5f6  jz      loc_10049E6D7
0x10049e5fc  xor     ecx, ecx
0x10049e5fe  mov     [rsp+5D0h+var_570], rcx; unsigned int *
0x10049e603  mov     [rsp+5D0h+var_578], cl; bool
0x10049e607  mov     [rsp+5D0h+var_580], 0FFFFFFFFh; unsigned int
0x10049e60f  lea     rax, [rbp+4D0h+var_4F8]
0x10049e613  mov     [rsp+5D0h+var_588], rax; __int64 *
0x10049e618  lea     rax, [rbp+4D0h+var_4F0]
0x10049e61c  mov     [rsp+5D0h+var_590], rax; __int64 *
0x10049e621  mov     [rsp+5D0h+var_598], 4000004h; unsigned int
0x10049e629  mov     qword ptr [rsp+5D0h+nndPreferred], rcx; void *
0x10049e62e  mov     [rsp+5D0h+lpName], r14; unsigned __int64
0x10049e633  mov     [rsp+5D0h+dwMaximumSizeLow], ecx; unsigned int
0x10049e637  xor     r9d, r9d; unsigned int
0x10049e63a  mov     r8d, 0F001Fh; unsigned int
0x10049e640  mov     rdx, rbx; void *
0x10049e643  mov     rcx, r15; this
0x10049e646  call    ?MapViewOfFileEx@MemoryNode@@AEAAPEAXPEAXKKK_K0KPEA_J2K_NPEAI@Z; MemoryNode::MapViewOfFileEx(void *,ulong,ulong,ulong,unsigned __int64,void *,ulong,__int64 *,__int64 *,ulong,bool,uint *)
0x10049e64b  mov     rdi, rax
0x10049e64e  test    rax, rax
0x10049e651  jnz     short loc_10049E660
0x10049e653  mov     rcx, rbx; hObject
0x10049e656  call    cs:__imp_CloseHandle
0x10049e65c  xor     esi, esi
0x10049e65e  jmp     short loc_10049E6DB
0x10049e660  lea     r9, [rsi+220h]
0x10049e667  cmp     dword ptr [rsi+0Ch], 0
0x10049e66b  mov     r10d, 0
0x10049e671  cmovle  r9, r10
0x10049e675  mov     [r9], rbx
0x10049e678  lea     rcx, [r9+28h]
0x10049e67c  mov     edx, 104h
0x10049e681  lea     r8, [rbp+4D0h+Name]
0x10049e685  sub     r8, rcx
0x10049e688  nop     dword ptr [rax+rax+00000000h]
0x10049e690  lea     rax, [rdx+7FFFFEFAh]
0x10049e697  test    rax, rax
0x10049e69a  jz      short loc_10049E6B3
0x10049e69c  movzx   eax, word ptr [r8+rcx]
0x10049e6a1  test    ax, ax
0x10049e6a4  jz      short loc_10049E6B3
0x10049e6a6  mov     [rcx], ax
0x10049e6a9  add     rcx, 2
0x10049e6ad  sub     rdx, 1
0x10049e6b1  jnz     short loc_10049E690
0x10049e6b3  lea     rax, [rcx-2]
0x10049e6b7  test    rdx, rdx
0x10049e6ba  cmovnz  rax, rcx
0x10049e6be  mov     [rax], r10w
0x10049e6c2  mov     [r9+10h], rdi
0x10049e6c6  mov     [r9+8], r10
0x10049e6ca  mov     [r9+18h], r14
0x10049e6ce  mov     [r9+20h], r10
0x10049e6d2  jmp     loc_10049E527
0x10049e6d7  xor     esi, esi
0x10049e6d9  mov     edi, esi
0x10049e6db  cmp     r12d, 5
0x10049e6df  ja      loc_10049E527
0x10049e6e5  mov     rax, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x10049e6ec  test    rax, rax
0x10049e6ef  cmovz   rax, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10049e6f7  lea     rcx, aUnableToAlloca; "Unable to allocate shared memory. Rever"...
0x10049e6fe  call    rax
0x10049e700  mov     rdx, cs:?SOS_OS_SharedMemoryContext@@3PEAVSOS_SharedMemoryContext@@EA; SOS_SharedMemoryContext * SOS_OS_SharedMemoryContext
0x10049e707  test    rdx, rdx
0x10049e70a  jz      short loc_10049E746
0x10049e70c  mov     rbx, [rdx]
0x10049e70f  movsxd  rax, dword ptr [rdx+10h]
0x10049e713  imul    r8, rax, 230h
0x10049e71a  add     r8, 450h
0x10049e721  mov     [rsp+5D0h+lpName], rsi
0x10049e726  mov     qword ptr [rsp+5D0h+dwMaximumSizeLow], rsi
0x10049e72b  mov     r9, r8
0x10049e72e  mov     rcx, r15
0x10049e731  call    ?UnmapViewOfFile@MemoryNode@@AEAA?AW4SOS_RESULT@@QEAX_K1PEA_J2_N@Z; MemoryNode::UnmapViewOfFile(void * const,unsigned __int64,unsigned __int64,__int64 *,__int64 *,bool)
0x10049e736  mov     rcx, rbx; hObject
0x10049e739  call    cs:__imp_CloseHandle
0x10049e73f  mov     cs:?SOS_OS_SharedMemoryContext@@3PEAVSOS_SharedMemoryContext@@EA, rsi; SOS_SharedMemoryContext * SOS_OS_SharedMemoryContext
0x10049e746  mov     rsi, [rbp+4D0h+ListHead]
0x10049e74a  mov     dword ptr [rsi+18h], 3
0x10049e751  mov     r12d, 9
0x10049e757  jmp     loc_10049E52B
  ... truncated ...
```
