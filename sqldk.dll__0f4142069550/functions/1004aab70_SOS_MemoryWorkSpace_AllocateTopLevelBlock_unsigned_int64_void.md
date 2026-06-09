# SOS_MemoryWorkSpace::AllocateTopLevelBlock(unsigned __int64,void * *)

- ea: `0x1004aab70`
- end: `0x1004aaf6c`
- name: `?AllocateTopLevelBlock@SOS_MemoryWorkSpace@@AEAAPEAX_KPEAPEAX@Z`
- size: `1020`
- prototype: `void *(SOS_MemoryWorkSpace *__hidden this, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x10040bc40`

## callees

- `0x1004060e0`
- `0x100416970`
- `0x100416ad0`
- `0x100432830`
- `0x1004360f0`
- `0x10049db30`
- `0x1004a76e0`
- `0x1004a7800`
- `0x1004aa560`
- `0x1004aab70`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1004aacf1`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aad67`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aadbd`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aaedf`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aaf00`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aaf4b`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aacf1`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aad67`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aadbd`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aaedf`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aaf00`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aaf4b`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004aac4a`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004aac6d`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004aac4a`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004aac6d`
- `KERNEL32!QueryDepthSList` at `0x1004aaca0`
- `KERNEL32!QueryDepthSList` at `0x1004aacb2`
- `KERNEL32!QueryDepthSList` at `0x1004aaca0`
- `KERNEL32!QueryDepthSList` at `0x1004aacb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall SOS_MemoryWorkSpace::AllocateTopLevelBlock(SOS_MemoryWorkSpace *this, unsigned __int64 a2, void **a3)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rdx
  unsigned __int16 v7; // r15
  __int64 v8; // r14
  int v9; // r12d
  char v10; // si
  union _SLIST_HEADER *v11; // rbx
  void **v12; // rdi
  __int64 v13; // rcx
  struct SOS_MemoryFragmentDescriptor *Fragment; // rax
  struct _SLIST_ENTRY *v15; // rbx
  int v16; // eax
  __int64 *v17; // rbx
  bool v18; // zf
  __int64 *v19; // rcx
  void *v20; // rsi
  __int64 v22; // rbx
  __int64 v23; // rax
  int v24; // ecx
  signed __int32 v25[8]; // [rsp+0h] [rbp-98h] BYREF
  __int64 v26; // [rsp+40h] [rbp-58h]
  __int64 *v27; // [rsp+48h] [rbp-50h] BYREF
  int v28; // [rsp+50h] [rbp-48h]

  v26 = -2;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
     + (unsigned int)SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  v6 = *(unsigned int *)(v5 + 76);
  if ( (SOS_OS_sm_osProcessStatus & 1) != 0 )
  {
    v7 = *((_WORD *)SOS_PublicGlobals::sm_CPUInfo + 16 * v6 + 1);
  }
  else if ( SOS_OS_InitialMemoryNode )
  {
    v7 = *((_WORD *)SOS_OS_InitialMemoryNode + 64);
  }
  else
  {
    v7 = 0;
  }
  v8 = DescriptorAllocator<SOS_ParentBlockDescriptor,0>::Pop(
         &SOS_MemoryBlockAllocator::sm_ParentBlockDescriptorAllocator,
         v6,
         0,
         0);
  if ( v8 )
  {
    v9 = dword_100720F58;
    while ( 1 )
    {
      v10 = 0;
      v11 = (union _SLIST_HEADER *)(qword_1007B9350 + ((unsigned __int64)v7 << byte_1007B935C));
      v12 = (void **)InterlockedPopEntrySList(v11);
      if ( v12 )
        break;
      if ( v9 == 1 )
        goto LABEL_27;
      v12 = (void **)InterlockedPopEntrySList(&stru_1007B9340);
      if ( v12 )
        goto LABEL_32;
      v27 = &qword_1007B9360;
      v28 = 0;
      if ( !(unsigned int)SOS_MemoryTopLevelBlockAllocator::AcquireMutexNoAbort(v13, &v27) )
      {
        if ( QueryDepthSList(v11) || QueryDepthSList(&stru_1007B9340) )
        {
          v10 = 1;
        }
        else
        {
          v10 = 1;
          Fragment = SOS_MemoryFragmentManager::AllocateFragment(&SOS_MemoryFragmentManager::sm_MemoryFragmentManager);
          v15 = (struct _SLIST_ENTRY *)Fragment;
          if ( Fragment )
          {
            if ( !SOS_MemoryTopLevelBlockAllocator::InitDescriptorList(
                    (union _SLIST_HEADER *)&SOS_MemoryTopLevelBlockAllocator::sm_MemoryTopLevelBlockAllocator,
                    Fragment) )
              InterlockedPushEntrySList(&SOS_MemoryFragmentManager::sm_MemoryFragmentManager, v15);
          }
          else
          {
            v10 = 0;
          }
        }
      }
      v16 = v28;
      if ( v28 )
      {
        v17 = v27;
        do
        {
          v18 = v17[8]-- == 1;
          if ( v18 )
          {
            _InterlockedOr(v25, 0);
            v19 = v27;
            v27[6] = 0;
            v19[7] = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v19, 0);
            v16 = v28;
          }
          v18 = v16-- == 1;
          v28 = v16;
        }
        while ( !v18 );
      }
      if ( !v10 )
      {
LABEL_27:
        v20 = 0;
        goto LABEL_28;
      }
    }
    _InterlockedExchangeAdd64(
      (volatile signed __int64 *)(qword_1007B9350 + ((unsigned __int64)v7 << byte_1007B935C) + 24),
      0xFFFFFFFFFFFFFFFFuLL);
LABEL_32:
    v20 = v12[5];
    if ( !v20 )
    {
LABEL_28:
      _InterlockedIncrement((volatile signed __int32 *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 8104));
      InterlockedPushEntrySList((PSLIST_HEADER)((v8 & 0xFFFFFFFFFFFFE000uLL) + 8064), (PSLIST_ENTRY)v8);
      if ( *(_DWORD *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 0x1FB0) == 1
        && _InterlockedCompareExchange((volatile signed __int32 *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 8112), 2, 1) == 1 )
      {
        InterlockedPushEntrySList(
          (PSLIST_HEADER)&qword_100734400[24 * *(unsigned __int16 *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 0x1FAC)
                                        + 2 * (*(_DWORD *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 0x1FA8) / 0xEu)],
          (PSLIST_ENTRY)((v8 & 0xFFFFFFFFFFFFE000uLL) + 8080));
        return v20;
      }
      return v20;
    }
    if ( (unsigned int)SOS_MemoryWorkSpace::CommitBlock(v12[5], a2, (struct SOS_TopLevelBlockDescriptor *)v12) )
    {
      v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
          + (unsigned int)SystemThread_TlsOffset;
      v23 = *(_QWORD *)(v22 + 256);
      if ( !v23 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v23 = *(_QWORD *)(v22 + 256);
      }
      v24 = *(_DWORD *)(v23 + 76);
      *(_QWORD *)v8 = 0;
      *(_QWORD *)(v8 + 8) = 0;
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 0;
      *(_QWORD *)(v8 + 32) = v20;
      *(_QWORD *)(v8 + 48) = 0;
      *(_QWORD *)(v8 + 56) = v12;
      *(_QWORD *)(v8 + 40) = v20;
      *(_DWORD *)(v8 + 80) = v24;
      *(_WORD *)(v8 + 84) = v7;
      *(_DWORD *)(v8 + 88) = 0;
      *(_QWORD *)(v8 + 64) = 0;
      *(_WORD *)(v8 + 86) = -1;
      *(_QWORD *)(v8 + 72) = 0;
      *(_QWORD *)(v8 + 96) = 1;
      *(_QWORD *)(v8 + 64) = 0x1000000;
      SOS_MemoryWorkSpace::Insert((struct SOS_ParentBlockDescriptor *)v8);
      *a3 = (void *)v8;
      return v20;
    }
    SOS_MemoryWorkSpace::DeCommitBlock(v20, a2, (struct SOS_TopLevelBlockDescriptor *)v12, v7, v7, 0, 0, 0);
    InterlockedPushEntrySList(&stru_1007B9340, (PSLIST_ENTRY)v12);
    _InterlockedIncrement((volatile signed __int32 *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 8104));
    InterlockedPushEntrySList((PSLIST_HEADER)((v8 & 0xFFFFFFFFFFFFE000uLL) + 8064), (PSLIST_ENTRY)v8);
    if ( *(_DWORD *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 0x1FB0) == 1
      && _InterlockedCompareExchange((volatile signed __int32 *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 8112), 2, 1) == 1 )
    {
      InterlockedPushEntrySList(
        (PSLIST_HEADER)&qword_100734400[24 * *(unsigned __int16 *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 0x1FAC)
                                      + 2 * (*(_DWORD *)((v8 & 0xFFFFFFFFFFFFE000uLL) + 0x1FA8) / 0xEu)],
        (PSLIST_ENTRY)((v8 & 0xFFFFFFFFFFFFE000uLL) + 8080));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1004aab70  mov     [rsp+arg_10], r8
0x1004aab75  push    rbp
0x1004aab76  push    rsi
0x1004aab77  push    rdi
0x1004aab78  push    r12
0x1004aab7a  push    r13
0x1004aab7c  push    r14
0x1004aab7e  push    r15
0x1004aab80  sub     rsp, 60h
0x1004aab84  mov     [rsp+98h+var_58], 0FFFFFFFFFFFFFFFEh
0x1004aab8d  mov     [rsp+98h+arg_8], rbx
0x1004aab95  mov     r13, rdx
0x1004aab98  xor     ebp, ebp
0x1004aab9a  mov     rcx, gs:58h
0x1004aaba3  mov     eax, cs:_tls_index
0x1004aaba9  mov     ebx, cs:SystemThread_TlsOffset
0x1004aabaf  add     rbx, [rcx+rax*8]
0x1004aabb3  mov     rax, [rbx+100h]
0x1004aabba  test    rax, rax
0x1004aabbd  jnz     short loc_1004AABCD
0x1004aabbf  xor     ecx, ecx; void *
0x1004aabc1  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004aabc6  mov     rax, [rbx+100h]
0x1004aabcd  mov     edx, [rax+4Ch]
0x1004aabd0  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x1004aabd7  jnz     short loc_1004AABF4
0x1004aabd9  mov     rax, cs:?SOS_OS_InitialMemoryNode@@3PEAVMemoryNode@@EA; MemoryNode * SOS_OS_InitialMemoryNode
0x1004aabe0  test    rax, rax
0x1004aabe3  jz      short loc_1004AABEF
0x1004aabe5  movzx   r15d, word ptr [rax+80h]
0x1004aabed  jmp     short loc_1004AAC07
0x1004aabef  mov     r15d, ebp
0x1004aabf2  jmp     short loc_1004AAC07
0x1004aabf4  mov     rax, rdx
0x1004aabf7  shl     rax, 5
0x1004aabfb  add     rax, cs:?sm_CPUInfo@SOS_PublicGlobals@@2PEAVSOS_CPUInfo@@EA; SOS_CPUInfo * SOS_PublicGlobals::sm_CPUInfo
0x1004aac02  movzx   r15d, word ptr [rax+2]
0x1004aac07  xor     r9d, r9d
0x1004aac0a  xor     r8d, r8d
0x1004aac0d  lea     rcx, ?sm_ParentBlockDescriptorAllocator@SOS_MemoryBlockAllocator@@0V?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@A; DescriptorAllocator<SOS_ParentBlockDescriptor,0> SOS_MemoryBlockAllocator::sm_ParentBlockDescriptorAllocator
0x1004aac14  call    ?Pop@?$DescriptorAllocator@VSOS_ParentBlockDescriptor@@$0A@@@QEAAPEAVSOS_ParentBlockDescriptor@@IPEAVWorker@@PEAE@Z; DescriptorAllocator<SOS_ParentBlockDescriptor,0>::Pop(uint,Worker *,uchar *)
0x1004aac19  mov     r14, rax
0x1004aac1c  test    rax, rax
0x1004aac1f  jz      loc_1004AAF51
0x1004aac25  mov     r12d, cs:dword_100720F58
0x1004aac2c  movzx   ebp, r15w
0x1004aac30  xor     sil, sil
0x1004aac33  movzx   ecx, cs:byte_1007B935C
0x1004aac3a  mov     rbx, rbp
0x1004aac3d  shl     rbx, cl
0x1004aac40  add     rbx, cs:qword_1007B9350
0x1004aac47  mov     rcx, rbx; ListHead
0x1004aac4a  call    cs:__imp_InterlockedPopEntrySList
0x1004aac50  mov     rdi, rax
0x1004aac53  test    rax, rax
0x1004aac56  jnz     loc_1004AADCB
0x1004aac5c  cmp     r12d, 1
0x1004aac60  jz      loc_1004AAD47
0x1004aac66  lea     rcx, stru_1007B9340; ListHead
0x1004aac6d  call    cs:__imp_InterlockedPopEntrySList
0x1004aac73  mov     rdi, rax
0x1004aac76  test    rax, rax
0x1004aac79  jnz     loc_1004AADE9
0x1004aac7f  lea     rax, qword_1007B9360
0x1004aac86  mov     [rsp+98h+var_50], rax
0x1004aac8b  mov     [rsp+98h+var_48], edi
0x1004aac8f  lea     rdx, [rsp+98h+var_50]
0x1004aac94  call    ?AcquireMutexNoAbort@SOS_MemoryTopLevelBlockAllocator@@AEAA?AW4SOS_RESULT@@PEAV?$TAutoMutex@VSOS_RecursiveMutex@@$0PPPPPPPP@@@@Z; SOS_MemoryTopLevelBlockAllocator::AcquireMutexNoAbort(TAutoMutex<SOS_RecursiveMutex,4294967295> *)
0x1004aac99  test    eax, eax
0x1004aac9b  jnz     short loc_1004AAD01
0x1004aac9d  mov     rcx, rbx; ListHead
0x1004aaca0  call    cs:__imp_QueryDepthSList
0x1004aaca6  test    ax, ax
0x1004aaca9  jnz     short loc_1004AACFE
0x1004aacab  lea     rcx, stru_1007B9340; ListHead
0x1004aacb2  call    cs:__imp_QueryDepthSList
0x1004aacb8  test    ax, ax
0x1004aacbb  jnz     short loc_1004AACFE
0x1004aacbd  mov     sil, 1
0x1004aacc0  lea     rcx, ?sm_MemoryFragmentManager@SOS_MemoryFragmentManager@@2V1@A; ListHead
0x1004aacc7  call    ?AllocateFragment@SOS_MemoryFragmentManager@@QEAAPEAVSOS_MemoryFragmentDescriptor@@XZ; SOS_MemoryFragmentManager::AllocateFragment(void)
0x1004aaccc  mov     rbx, rax
0x1004aaccf  test    rax, rax
0x1004aacd2  jz      short loc_1004AACF9
0x1004aacd4  mov     rdx, rax; struct SOS_MemoryFragmentDescriptor *
0x1004aacd7  lea     rcx, ?sm_MemoryTopLevelBlockAllocator@SOS_MemoryTopLevelBlockAllocator@@2V1@A; this
0x1004aacde  call    ?InitDescriptorList@SOS_MemoryTopLevelBlockAllocator@@AEAA_NPEAVSOS_MemoryFragmentDescriptor@@@Z; SOS_MemoryTopLevelBlockAllocator::InitDescriptorList(SOS_MemoryFragmentDescriptor *)
0x1004aace3  test    al, al
0x1004aace5  jnz     short loc_1004AAD01
0x1004aace7  mov     rdx, rbx; ListEntry
0x1004aacea  lea     rcx, ?sm_MemoryFragmentManager@SOS_MemoryFragmentManager@@2V1@A; ListHead
0x1004aacf1  call    cs:__imp_InterlockedPushEntrySList
0x1004aacf7  jmp     short loc_1004AAD01
0x1004aacf9  xor     sil, sil
0x1004aacfc  jmp     short loc_1004AAD01
0x1004aacfe  mov     sil, 1
0x1004aad01  mov     eax, [rsp+98h+var_48]
0x1004aad05  test    eax, eax
0x1004aad07  jz      short loc_1004AAD3D
0x1004aad09  mov     rbx, [rsp+98h+var_50]
0x1004aad0e  xchg    ax, ax
0x1004aad10  sub     qword ptr [rbx+40h], 1
0x1004aad15  jnz     short loc_1004AAD34
0x1004aad17  lock or [rsp+98h+var_98], 0
0x1004aad1c  mov     rcx, [rsp+98h+var_50]
0x1004aad21  mov     [rcx+30h], rdi
0x1004aad25  mov     [rcx+38h], rdi
0x1004aad29  xor     edx, edx
0x1004aad2b  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x1004aad30  mov     eax, [rsp+98h+var_48]
0x1004aad34  add     eax, 0FFFFFFFFh
0x1004aad37  mov     [rsp+98h+var_48], eax
0x1004aad3b  jnz     short loc_1004AAD10
0x1004aad3d  test    sil, sil
0x1004aad40  jz      short loc_1004AAD49
0x1004aad42  jmp     loc_1004AAC30
0x1004aad47  xor     edi, edi
0x1004aad49  mov     rsi, rdi
0x1004aad4c  mov     rbx, r14
0x1004aad4f  and     rbx, 0FFFFFFFFFFFFE000h
0x1004aad56  add     rbx, 1F80h
0x1004aad5d  lock inc dword ptr [rbx+28h]
0x1004aad61  mov     rdx, r14; ListEntry
0x1004aad64  mov     rcx, rbx; ListHead
0x1004aad67  call    cs:__imp_InterlockedPushEntrySList
0x1004aad6d  mov     eax, [rbx+30h]
0x1004aad70  cmp     eax, 1
0x1004aad73  jnz     loc_1004AAEA5
0x1004aad79  mov     ecx, 2
0x1004aad7e  lock cmpxchg [rbx+30h], ecx
0x1004aad83  jnz     loc_1004AAEA5
0x1004aad89  mov     ecx, [rbx+28h]
0x1004aad8c  mov     eax, 24924925h
0x1004aad91  mul     ecx
0x1004aad93  sub     ecx, edx
0x1004aad95  shr     ecx, 1
0x1004aad97  lea     r8d, [rdx+rcx]
0x1004aad9b  shr     r8d, 3
0x1004aad9f  movzx   eax, word ptr [rbx+2Ch]
0x1004aada3  lea     rcx, [rax+rax*2]
0x1004aada7  lea     rcx, [r8+rcx*4]
0x1004aadab  shl     rcx, 4
0x1004aadaf  lea     rdx, qword_100734400
0x1004aadb6  add     rcx, rdx; ListHead
0x1004aadb9  lea     rdx, [rbx+10h]; ListEntry
0x1004aadbd  call    cs:__imp_InterlockedPushEntrySList
0x1004aadc3  mov     rax, rsi
0x1004aadc6  jmp     loc_1004AAF54
0x1004aadcb  movzx   ecx, cs:byte_1007B935C
0x1004aadd2  shl     rbp, cl
0x1004aadd5  add     rbp, cs:qword_1007B9350
0x1004aaddc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1004aade3  lock xadd [rbp+18h], rax
0x1004aade9  mov     rsi, [rdi+28h]
0x1004aaded  test    rsi, rsi
0x1004aadf0  jz      loc_1004AAD4C
0x1004aadf6  mov     r8, rdi; struct SOS_TopLevelBlockDescriptor *
0x1004aadf9  mov     rdx, r13; unsigned __int64
0x1004aadfc  mov     rcx, rsi; void *
0x1004aadff  call    ?CommitBlock@SOS_MemoryWorkSpace@@CAHPEAX_KPEAVSOS_TopLevelBlockDescriptor@@@Z; SOS_MemoryWorkSpace::CommitBlock(void *,unsigned __int64,SOS_TopLevelBlockDescriptor *)
0x1004aae04  test    eax, eax
0x1004aae06  jz      loc_1004AAEAD
0x1004aae0c  mov     rcx, gs:58h
0x1004aae15  mov     eax, cs:_tls_index
0x1004aae1b  mov     ebx, cs:SystemThread_TlsOffset
0x1004aae21  add     rbx, [rcx+rax*8]
0x1004aae25  mov     rax, [rbx+100h]
0x1004aae2c  test    rax, rax
0x1004aae2f  jnz     short loc_1004AAE3F
0x1004aae31  xor     ecx, ecx; void *
0x1004aae33  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004aae38  mov     rax, [rbx+100h]
0x1004aae3f  mov     ecx, [rax+4Ch]
0x1004aae42  xor     ebp, ebp
0x1004aae44  mov     [r14], rbp
0x1004aae47  mov     [r14+8], rbp
0x1004aae4b  mov     [r14+10h], rbp
0x1004aae4f  mov     [r14+18h], rbp
0x1004aae53  mov     [r14+20h], rsi
0x1004aae57  mov     [r14+30h], rbp
0x1004aae5b  mov     [r14+38h], rdi
0x1004aae5f  mov     [r14+28h], rsi
0x1004aae63  mov     [r14+50h], ecx
0x1004aae67  mov     [r14+54h], r15w
0x1004aae6c  mov     [r14+58h], ebp
0x1004aae70  mov     [r14+40h], rbp
0x1004aae74  mov     eax, 0FFFFh
0x1004aae79  mov     [r14+56h], ax
0x1004aae7e  mov     [r14+48h], rbp
0x1004aae82  mov     qword ptr [r14+60h], 1
0x1004aae8a  mov     qword ptr [r14+40h], 1000000h
0x1004aae92  mov     rcx, r14; struct SOS_ParentBlockDescriptor *
0x1004aae95  call    ?Insert@SOS_MemoryWorkSpace@@SAXPEAVSOS_ParentBlockDescriptor@@@Z; SOS_MemoryWorkSpace::Insert(SOS_ParentBlockDescriptor *)
0x1004aae9a  mov     rax, [rsp+98h+arg_10]
0x1004aaea2  mov     [rax], r14
0x1004aaea5  mov     rax, rsi
0x1004aaea8  jmp     loc_1004AAF54
0x1004aaead  xor     ebp, ebp
0x1004aaeaf  mov     [rsp+98h+var_60], rbp; unsigned __int64 *
0x1004aaeb4  mov     [rsp+98h+var_68], rbp; unsigned __int64 *
0x1004aaeb9  mov     [rsp+98h+var_70], ebp; int
0x1004aaebd  mov     [rsp+98h+var_78], r15w; unsigned __int16
0x1004aaec3  movzx   r9d, r15w; unsigned __int16
0x1004aaec7  mov     r8, rdi; struct SOS_TopLevelBlockDescriptor *
0x1004aaeca  mov     rdx, r13; unsigned __int64
0x1004aaecd  mov     rcx, rsi; void *
0x1004aaed0  call    ?DeCommitBlock@SOS_MemoryWorkSpace@@CAXPEAX_KPEAVSOS_TopLevelBlockDescriptor@@GGHPEA_K3@Z; SOS_MemoryWorkSpace::DeCommitBlock(void *,unsigned __int64,SOS_TopLevelBlockDescriptor *,ushort,ushort,int,unsigned __int64 *,unsigned __int64 *)
0x1004aaed5  mov     rdx, rdi; ListEntry
0x1004aaed8  lea     rcx, stru_1007B9340; ListHead
0x1004aaedf  call    cs:__imp_InterlockedPushEntrySList
0x1004aaee5  mov     rbx, r14
0x1004aaee8  and     rbx, 0FFFFFFFFFFFFE000h
0x1004aaeef  add     rbx, 1F80h
0x1004aaef6  lock inc dword ptr [rbx+28h]
0x1004aaefa  mov     rdx, r14; ListEntry
0x1004aaefd  mov     rcx, rbx; ListHead
0x1004aaf00  call    cs:__imp_InterlockedPushEntrySList
0x1004aaf06  mov     eax, [rbx+30h]
0x1004aaf09  cmp     eax, 1
0x1004aaf0c  jnz     short loc_1004AAF51
0x1004aaf0e  mov     ecx, 2
0x1004aaf13  lock cmpxchg [rbx+30h], ecx
0x1004aaf18  jnz     short loc_1004AAF51
0x1004aaf1a  movzx   eax, word ptr [rbx+2Ch]
0x1004aaf1e  lea     r8, [rax+rax*2]
0x1004aaf22  mov     ecx, [rbx+28h]
0x1004aaf25  mov     eax, 24924925h
0x1004aaf2a  mul     ecx
0x1004aaf2c  sub     ecx, edx
0x1004aaf2e  shr     ecx, 1
0x1004aaf30  add     ecx, edx
0x1004aaf32  shr     ecx, 3
0x1004aaf35  lea     rcx, [rcx+r8*4]
0x1004aaf39  shl     rcx, 4
0x1004aaf3d  lea     rdx, qword_100734400
0x1004aaf44  add     rcx, rdx; ListHead
0x1004aaf47  lea     rdx, [rbx+10h]; ListEntry
0x1004aaf4b  call    cs:__imp_InterlockedPushEntrySList
0x1004aaf51  mov     rax, rbp
0x1004aaf54  mov     rbx, [rsp+98h+arg_8]
0x1004aaf5c  add     rsp, 60h
0x1004aaf60  pop     r15
0x1004aaf62  pop     r14
0x1004aaf64  pop     r13
0x1004aaf66  pop     r12
0x1004aaf68  pop     rdi
0x1004aaf69  pop     rsi
0x1004aaf6a  pop     rbp
0x1004aaf6b  retn
```
