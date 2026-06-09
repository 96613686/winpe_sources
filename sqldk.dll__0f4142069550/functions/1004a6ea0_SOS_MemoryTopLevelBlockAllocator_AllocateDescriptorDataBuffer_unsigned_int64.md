# SOS_MemoryTopLevelBlockAllocator::AllocateDescriptorDataBuffer(unsigned __int64)

- ea: `0x1004a6ea0`
- end: `0x1004a747d`
- name: `?AllocateDescriptorDataBuffer@SOS_MemoryTopLevelBlockAllocator@@AEAAPEAX_K@Z`
- size: `1501`
- prototype: `void *(SOS_MemoryTopLevelBlockAllocator *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1004a6a60`
- `0x1004a7a20`

## callees

- `0x100404bf2`
- `0x1004060e0`
- `0x100414400`
- `0x100417620`
- `0x1004360f0`
- `0x1004a6ea0`
- `0x1004a7490`
- `0x1004a76e0`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1004a6fd8`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a6fd8`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a6f50`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a714b`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a6f50`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a714b`
- `KERNEL32!InterlockedFlushSList` at `0x1004a6f88`
- `KERNEL32!InterlockedFlushSList` at `0x1004a6f88`
- `KERNEL32!GetCurrentProcess` at `0x1004a720b`
- `KERNEL32!GetCurrentProcess` at `0x1004a72dc`
- `KERNEL32!GetCurrentProcess` at `0x1004a720b`
- `KERNEL32!GetCurrentProcess` at `0x1004a72dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _SLIST_ENTRY *__fastcall SOS_MemoryTopLevelBlockAllocator::AllocateDescriptorDataBuffer(
        SOS_MemoryTopLevelBlockAllocator *this,
        size_t a2)
{
  SOS_MemoryTopLevelBlockAllocator *v3; // r14
  unsigned __int64 v4; // rdi
  PSLIST_ENTRY v5; // rbx
  unsigned int v6; // ecx
  unsigned int v7; // r8d
  union _SLIST_HEADER *v8; // rdx
  PSLIST_ENTRY v9; // rax
  struct _SLIST_ENTRY *v10; // rsi
  struct _SLIST_ENTRY *v11; // rbx
  struct _SLIST_ENTRY *v12; // rsi
  PSLIST_ENTRY v13; // rax
  char *ThreadLocalStoragePointer; // rcx
  int v15; // r12d
  union _SLIST_HEADER *v16; // r14
  struct _SLIST_ENTRY *v17; // rdx
  struct _SLIST_ENTRY *Next; // rax
  struct _SLIST_ENTRY *v19; // r15
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdi
  unsigned __int64 v24; // rax
  int v25; // ebx
  PSLIST_ENTRY v26; // rbx
  unsigned int v27; // ecx
  unsigned int v28; // r8d
  union _SLIST_HEADER *v29; // rdx
  PSLIST_ENTRY v30; // rax
  size_t v31; // r15
  unsigned __int64 v32; // rdx
  __int64 v33; // rax
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rdi
  HANDLE CurrentProcess; // rbx
  __int64 v37; // rax
  unsigned __int64 v38; // r12
  unsigned __int64 v39; // rdi
  HANDLE v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  char *v44; // rbx
  bool v45; // zf
  char *v46; // rcx
  signed __int32 v48[8]; // [rsp+0h] [rbp-69h] BYREF
  unsigned __int64 v49; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v50; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int64 v51; // [rsp+60h] [rbp-9h] BYREF
  PSLIST_HEADER ListHead[2]; // [rsp+68h] [rbp-1h] BYREF
  char *v53; // [rsp+78h] [rbp+Fh] BYREF
  int v54; // [rsp+80h] [rbp+17h]
  SOS_MemoryTopLevelBlockAllocator *v55; // [rsp+D0h] [rbp+67h] BYREF
  struct _SLIST_ENTRY *v56; // [rsp+E0h] [rbp+77h]
  unsigned __int64 v57; // [rsp+E8h] [rbp+7Fh]

  v55 = this;
  ListHead[1] = (PSLIST_HEADER)-2LL;
  v3 = this;
  v4 = 8 * (0x1000000 / SOS_TopLevelBlockDescriptor::sm_SmallestBlockAllocatorSize);
  v57 = v4;
  if ( dword_100720F58 != 1 )
  {
    v4 += 1024LL;
    v57 = v4;
    if ( dword_100720F58 == 2 )
    {
      v4 += 0x8000LL;
      v57 = v4;
    }
  }
  v5 = 0;
  v6 = 0;
  v7 = *((_DWORD *)v3 + 8);
  if ( v7 )
  {
    while ( 1 )
    {
      v8 = (union _SLIST_HEADER *)(*(_QWORD *)v3 + 32LL * v6);
      if ( v8->Alignment == a2 )
        break;
      if ( ++v6 >= v7 )
        goto LABEL_14;
    }
    if ( v8 )
    {
      v9 = InterlockedPopEntrySList(v8 + 1);
      if ( v9 )
        v5 = v9 - 1;
    }
  }
  v10 = v5 + 1;
  if ( !v5 )
    v10 = 0;
  if ( v10 )
    goto LABEL_86;
LABEL_14:
  v11 = 0;
  v56 = 0;
  v12 = 0;
  ListHead[0] = (PSLIST_HEADER)((char *)v3 + 16);
  v13 = InterlockedFlushSList((PSLIST_HEADER)v3 + 1);
  if ( v13 )
    v12 = v13 - 1;
  v15 = 0;
  if ( v12 )
  {
    v16 = ListHead[0];
    do
    {
      v17 = v12 + 1;
      Next = v12[1].Next;
      v19 = Next - 1;
      if ( !Next )
        v19 = 0;
      v17->Next = 0;
      if ( v12->Next < (struct _SLIST_ENTRY *)a2 )
        InterlockedPushEntrySList(v16, v17);
      else
        v56 = v12;
      v12 = v19;
      if ( (++v15 & 0x7F) == 0 )
      {
        ThreadLocalStoragePointer = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v20 = *(_QWORD *)&ThreadLocalStoragePointer[8 * tls_index] + (unsigned int)SystemThread_TlsOffset;
        v21 = *(_QWORD *)(v20 + 256);
        if ( !v21 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v21 = *(_QWORD *)(v20 + 256);
        }
        if ( (*(_BYTE *)(v21 + 616) & 0x40) == 0 )
        {
          v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
              + (unsigned int)SystemThread_TlsOffset;
          v23 = *(_QWORD *)(v22 + 256);
          if ( !v23 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v23 = *(_QWORD *)(v22 + 256);
          }
          v24 = __rdtsc();
          ThreadLocalStoragePointer = *(char **)(v23 + 832);
          if ( v24 > (unsigned __int64)ThreadLocalStoragePointer
            || ThreadLocalStoragePointer != (char *)0x7FFFFFFFFFFFFFFFLL
            && (ThreadLocalStoragePointer -= v24,
                (unsigned __int64)ThreadLocalStoragePointer > *(_QWORD *)(*(_QWORD *)(v23 + 608) + 3568LL)) )
          {
            v25 = *(_DWORD *)(v23 + 616) & 1;
            *(_DWORD *)(v23 + 616) |= 1u;
            SOS_Task::Sleep(0, yieldWait);
            *(_DWORD *)(v23 + 616) &= ~(v25 ^ 1);
          }
        }
      }
    }
    while ( v19 );
    v3 = v55;
    v11 = v56;
    v4 = v57;
  }
  v10 = v11 + 1;
  if ( !v11 )
    v10 = 0;
  v56 = v10;
  if ( v10 )
  {
LABEL_86:
    memset_0(v10, 0, a2);
    return v10;
  }
  v53 = (char *)v3 + 96;
  v54 = 0;
  if ( (unsigned int)SOS_MemoryTopLevelBlockAllocator::AcquireMutexNoAbort(ThreadLocalStoragePointer, &v53) )
  {
LABEL_77:
    v44 = v53;
    goto LABEL_78;
  }
  v26 = 0;
  v27 = 0;
  v28 = *((_DWORD *)v3 + 8);
  if ( v28 )
  {
    while ( 1 )
    {
      v29 = (union _SLIST_HEADER *)(*(_QWORD *)v3 + 32LL * v27);
      if ( v29->Alignment == a2 )
        break;
      if ( ++v27 >= v28 )
      {
        v10 = 0;
        v56 = 0;
        goto LABEL_49;
      }
    }
    if ( v29 )
    {
      v26 = 0;
      v30 = InterlockedPopEntrySList(v29 + 1);
      if ( v30 )
        v26 = v30 - 1;
    }
  }
  v10 = v26 + 1;
  if ( !v26 )
    v10 = 0;
  v56 = v10;
  if ( !v10 )
  {
LABEL_49:
    v31 = a2 + 16;
    v32 = *((_QWORD *)v3 + 7);
    v33 = *((_QWORD *)v3 + 6);
    if ( v32 >= a2 + 16 && v33 )
      goto LABEL_64;
    if ( dword_100720F68 )
    {
      if ( v32 || v33 )
        v34 = a2 + 16;
      else
        v34 = (unsigned int)dword_100720F68 * (v4 >> 1);
    }
    else
    {
      v34 = (((qword_100720F60 + 0xFFFFFF) & 0xFFFFFFFFFF000000uLL) >> 24) * (v4 + 16);
    }
    *((_QWORD *)v3 + 7) = v34;
    if ( !*(_QWORD *)v3 )
    {
      v34 += 0x8000LL;
      *((_QWORD *)v3 + 7) = v34;
    }
    v35 = v34
        + (unsigned int)dword_1007153F0
        - 1LL
        - (v34 + (unsigned int)dword_1007153F0 - 1LL) % (unsigned int)dword_1007153F0;
    *((_QWORD *)v3 + 7) = v35;
    v49 = 0;
    v50 = 0;
    CurrentProcess = GetCurrentProcess();
    v37 = (*(__int64 (__fastcall **)(void *))(qword_1007B9C00 + 32LL))(&qword_1007B9C00);
    v33 = MemoryNode::VirtualAlloc(v37, CurrentProcess, 0, v35, 0x2000, 4, HIDWORD(qword_1007BA188), &v49, &v50);
    if ( v49 )
      _InterlockedExchangeAdd64(&qword_1007BA1A8, v49);
    if ( v50 )
      _InterlockedExchangeAdd64((volatile signed __int64 *)&xmmword_1007BA1B0, v50);
    *((_QWORD *)v3 + 6) = v33;
    if ( v33 )
    {
LABEL_64:
      v38 = (v33 + 4095) & 0xFFFFFFFFFFFFF000uLL;
      v39 = ((v33 + a2 + 4111) & 0xFFFFFFFFFFFFF000uLL) - v38;
      if ( !*(_QWORD *)v3 )
        v39 = (v39 + 36863) & 0xFFFFFFFFFFFFF000uLL;
      if ( !v39 )
        goto LABEL_90;
      v51 = 0;
      ListHead[0] = 0;
      v40 = GetCurrentProcess();
      v41 = (*(__int64 (__fastcall **)(void *))(qword_1007B9C00 + 32LL))(&qword_1007B9C00);
      v42 = MemoryNode::VirtualAlloc(v41, v40, v38, v39, 4096, 4, HIDWORD(qword_1007BA188), &v51, ListHead);
      if ( v51 )
        _InterlockedExchangeAdd64(&qword_1007BA1A8, v51);
      if ( ListHead[0] )
        _InterlockedExchangeAdd64((volatile signed __int64 *)&xmmword_1007BA1B0, (unsigned __int64)ListHead[0]);
      if ( v42 )
      {
LABEL_90:
        if ( !*(_QWORD *)v3 )
        {
          v43 = *((_QWORD *)v3 + 6);
          *(_QWORD *)v3 = v43;
          *((_QWORD *)v3 + 6) = v43 + 0x8000;
          *((_QWORD *)v3 + 7) -= 0x8000LL;
          if ( !SOS_MemoryTopLevelBlockAllocator::AllocateBufferList(v3, v57, (unsigned int *)&v55) )
            utassert_fail(1u, "list", "TopLevelBlock.cpp", 1410, 0);
        }
        v10 = (struct _SLIST_ENTRY *)*((_QWORD *)v3 + 6);
        v56 = v10;
        *((_QWORD *)v3 + 6) = (char *)v10 + v31;
        *((_QWORD *)v3 + 7) -= v31;
        if ( v10 )
        {
          v10->Next = (struct _SLIST_ENTRY *)a2;
          *((_DWORD *)&v10->Next + 2) = -1;
          v56 = ++v10;
        }
      }
    }
    goto LABEL_77;
  }
  v44 = v53;
  v45 = (*((_QWORD *)v53 + 8))-- == 1;
  if ( v45 )
  {
    _InterlockedOr(v48, 0);
    v44 = v53;
    *((_QWORD *)v53 + 6) = 0;
    *((_QWORD *)v44 + 7) = 0;
    EventAutoInternal<SuspendQueueSLock>::Signal(v44, 0);
  }
  --v54;
  memset_0(v10, 0, a2);
LABEL_78:
  if ( !v54 )
    return v10;
  do
  {
    v45 = (*((_QWORD *)v44 + 8))-- == 1;
    if ( v45 )
    {
      _InterlockedOr(v48, 0);
      v46 = v53;
      *((_QWORD *)v53 + 6) = 0;
      *((_QWORD *)v46 + 7) = 0;
      EventAutoInternal<SuspendQueueSLock>::Signal(v46, 0);
    }
    --v54;
  }
  while ( v54 );
  return v56;
}

```

## disassembly

```asm
0x1004a6ea0  mov     [rsp-8+arg_0], rcx
0x1004a6ea5  push    rbp
0x1004a6ea6  push    rsi
0x1004a6ea7  push    rdi
0x1004a6ea8  push    r12
0x1004a6eaa  push    r13
0x1004a6eac  push    r14
0x1004a6eae  push    r15
0x1004a6eb0  lea     rbp, [rsp-27h]
0x1004a6eb5  sub     rsp, 90h
0x1004a6ebc  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1004a6ec4  mov     [rsp+0C0h+arg_8], rbx
0x1004a6ecc  mov     r13, rdx
0x1004a6ecf  mov     r14, rcx
0x1004a6ed2  mov     ecx, cs:dword_100720F58
0x1004a6ed8  xor     edx, edx
0x1004a6eda  mov     eax, 1000000h
0x1004a6edf  div     cs:?sm_SmallestBlockAllocatorSize@SOS_TopLevelBlockDescriptor@@0_KA; unsigned __int64 SOS_TopLevelBlockDescriptor::sm_SmallestBlockAllocatorSize
0x1004a6ee6  mov     rdi, rax
0x1004a6ee9  shl     rdi, 3
0x1004a6eed  mov     [rbp+57h+arg_18], rdi
0x1004a6ef1  cmp     ecx, 1
0x1004a6ef4  jz      short loc_1004A6F11
0x1004a6ef6  add     rdi, 400h
0x1004a6efd  mov     [rbp+57h+arg_18], rdi
0x1004a6f01  cmp     ecx, 2
0x1004a6f04  jnz     short loc_1004A6F11
0x1004a6f06  add     rdi, 8000h
0x1004a6f0d  mov     [rbp+57h+arg_18], rdi
0x1004a6f11  xor     r15d, r15d
0x1004a6f14  mov     ebx, r15d
0x1004a6f17  mov     ecx, r15d
0x1004a6f1a  mov     r8d, [r14+20h]
0x1004a6f1e  test    r8d, r8d
0x1004a6f21  jz      short loc_1004A6F5F
0x1004a6f23  mov     r9, [r14]
0x1004a6f26  nop     word ptr [rax+rax+00000000h]
0x1004a6f30  mov     edx, ecx
0x1004a6f32  shl     rdx, 5
0x1004a6f36  add     rdx, r9
0x1004a6f39  cmp     [rdx], r13
0x1004a6f3c  jz      short loc_1004A6F47
0x1004a6f3e  inc     ecx
0x1004a6f40  cmp     ecx, r8d
0x1004a6f43  jb      short loc_1004A6F30
0x1004a6f45  jmp     short loc_1004A6F73
0x1004a6f47  test    rdx, rdx
0x1004a6f4a  jz      short loc_1004A6F5F
0x1004a6f4c  lea     rcx, [rdx+10h]; ListHead
0x1004a6f50  call    cs:__imp_InterlockedPopEntrySList
0x1004a6f56  test    rax, rax
0x1004a6f59  jz      short loc_1004A6F5F
0x1004a6f5b  lea     rbx, [rax-10h]
0x1004a6f5f  lea     rsi, [rbx+10h]
0x1004a6f63  test    rbx, rbx
0x1004a6f66  cmovz   rsi, r15
0x1004a6f6a  test    rsi, rsi
0x1004a6f6d  jnz     loc_1004A7452
0x1004a6f73  mov     rbx, r15
0x1004a6f76  mov     [rbp+57h+arg_10], rbx
0x1004a6f7a  mov     rsi, r15
0x1004a6f7d  lea     rax, [r14+10h]
0x1004a6f81  mov     [rbp+57h+ListHead], rax
0x1004a6f85  mov     rcx, rax; ListHead
0x1004a6f88  call    cs:__imp_InterlockedFlushSList
0x1004a6f8e  test    rax, rax
0x1004a6f91  jz      short loc_1004A6F97
0x1004a6f93  lea     rsi, [rax-10h]
0x1004a6f97  mov     r12d, r15d
0x1004a6f9a  test    rsi, rsi
0x1004a6f9d  jz      loc_1004A70DA
0x1004a6fa3  mov     r14, [rbp+57h+ListHead]
0x1004a6fa7  nop     word ptr [rax+rax+00000000h]
0x1004a6fb0  lea     rdx, [rsi+10h]; ListEntry
0x1004a6fb4  mov     rax, [rdx]
0x1004a6fb7  lea     r15, [rax-10h]
0x1004a6fbb  test    rax, rax
0x1004a6fbe  mov     eax, 0
0x1004a6fc3  cmovz   r15, rax
0x1004a6fc7  mov     [rdx], rax
0x1004a6fca  cmp     [rsi], r13
0x1004a6fcd  jb      short loc_1004A6FD5
0x1004a6fcf  mov     [rbp+57h+arg_10], rsi
0x1004a6fd3  jmp     short loc_1004A6FDE
0x1004a6fd5  mov     rcx, r14; ListHead
0x1004a6fd8  call    cs:__imp_InterlockedPushEntrySList
0x1004a6fde  mov     rsi, r15
0x1004a6fe1  inc     r12d
0x1004a6fe4  test    r12b, 7Fh
0x1004a6fe8  jnz     loc_1004A70C5
0x1004a6fee  mov     rcx, gs:58h
0x1004a6ff7  mov     eax, cs:_tls_index
0x1004a6ffd  mov     ebx, cs:SystemThread_TlsOffset
0x1004a7003  add     rbx, [rcx+rax*8]
0x1004a7007  mov     rax, [rbx+100h]
0x1004a700e  test    rax, rax
0x1004a7011  jnz     short loc_1004A7021
0x1004a7013  xor     ecx, ecx; void *
0x1004a7015  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a701a  mov     rax, [rbx+100h]
0x1004a7021  test    byte ptr [rax+268h], 40h
0x1004a7028  jnz     loc_1004A70C5
0x1004a702e  mov     rcx, gs:58h
0x1004a7037  mov     eax, cs:_tls_index
0x1004a703d  mov     ebx, cs:SystemThread_TlsOffset
0x1004a7043  add     rbx, [rcx+rax*8]
0x1004a7047  mov     rdi, [rbx+100h]
0x1004a704e  test    rdi, rdi
0x1004a7051  jnz     short loc_1004A7061
0x1004a7053  xor     ecx, ecx; void *
0x1004a7055  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a705a  mov     rdi, [rbx+100h]
0x1004a7061  rdtsc
0x1004a7063  shl     rdx, 20h
0x1004a7067  or      rax, rdx
0x1004a706a  mov     rcx, [rdi+340h]
0x1004a7071  cmp     rax, rcx
0x1004a7074  ja      short loc_1004A7098
0x1004a7076  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1004a7080  cmp     rcx, rdx
0x1004a7083  jz      short loc_1004A70C5
0x1004a7085  sub     rcx, rax
0x1004a7088  mov     rax, [rdi+260h]
0x1004a708f  cmp     rcx, [rax+0DF0h]
0x1004a7096  jbe     short loc_1004A70C5
0x1004a7098  mov     eax, [rdi+268h]
0x1004a709e  mov     ebx, eax
0x1004a70a0  and     ebx, 1
0x1004a70a3  or      eax, 1
0x1004a70a6  mov     [rdi+268h], eax
0x1004a70ac  lea     rdx, ?yieldWait@@3VSOS_WaitInfo@@B; "c@"
0x1004a70b3  xor     ecx, ecx
0x1004a70b5  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x1004a70ba  xor     ebx, 1
0x1004a70bd  not     ebx
0x1004a70bf  and     [rdi+268h], ebx
0x1004a70c5  test    r15, r15
0x1004a70c8  jnz     loc_1004A6FB0
0x1004a70ce  mov     r14, [rbp+57h+arg_0]
0x1004a70d2  mov     rbx, [rbp+57h+arg_10]
0x1004a70d6  mov     rdi, [rbp+57h+arg_18]
0x1004a70da  lea     rsi, [rbx+10h]
0x1004a70de  test    rbx, rbx
0x1004a70e1  cmovz   rsi, r15
0x1004a70e5  mov     [rbp+57h+arg_10], rsi
0x1004a70e9  test    rsi, rsi
0x1004a70ec  jnz     loc_1004A7452
0x1004a70f2  lea     rax, [r14+60h]
0x1004a70f6  mov     [rbp+57h+var_48], rax
0x1004a70fa  mov     [rbp+57h+var_40], r15d
0x1004a70fe  lea     rdx, [rbp+57h+var_48]
0x1004a7102  call    ?AcquireMutexNoAbort@SOS_MemoryTopLevelBlockAllocator@@AEAA?AW4SOS_RESULT@@PEAV?$TAutoMutex@VSOS_RecursiveMutex@@$0PPPPPPPP@@@@Z; SOS_MemoryTopLevelBlockAllocator::AcquireMutexNoAbort(TAutoMutex<SOS_RecursiveMutex,4294967295> *)
0x1004a7107  test    eax, eax
0x1004a7109  jnz     loc_1004A73E0
0x1004a710f  mov     rbx, r15
0x1004a7112  mov     ecx, r15d
0x1004a7115  mov     r8d, [r14+20h]
0x1004a7119  test    r8d, r8d
0x1004a711c  jz      short loc_1004A715A
0x1004a711e  mov     r9, [r14]
0x1004a7121  mov     edx, ecx
0x1004a7123  shl     rdx, 5
0x1004a7127  add     rdx, r9
0x1004a712a  cmp     [rdx], r13
0x1004a712d  jz      short loc_1004A713F
0x1004a712f  inc     ecx
0x1004a7131  cmp     ecx, r8d
0x1004a7134  jb      short loc_1004A7121
0x1004a7136  mov     rsi, r15
0x1004a7139  mov     [rbp+57h+arg_10], r15
0x1004a713d  jmp     short loc_1004A7172
0x1004a713f  test    rdx, rdx
0x1004a7142  jz      short loc_1004A715A
0x1004a7144  mov     rbx, r15
0x1004a7147  lea     rcx, [rdx+10h]; ListHead
0x1004a714b  call    cs:__imp_InterlockedPopEntrySList
0x1004a7151  test    rax, rax
0x1004a7154  jz      short loc_1004A715A
0x1004a7156  lea     rbx, [rax-10h]
0x1004a715a  lea     rsi, [rbx+10h]
0x1004a715e  test    rbx, rbx
0x1004a7161  cmovz   rsi, r15
0x1004a7165  mov     [rbp+57h+arg_10], rsi
0x1004a7169  test    rsi, rsi
0x1004a716c  jnz     loc_1004A741A
0x1004a7172  lea     r15, [r13+10h]
0x1004a7176  mov     rdx, [r14+38h]
0x1004a717a  mov     rax, [r14+30h]
0x1004a717e  cmp     rdx, r15
0x1004a7181  jb      short loc_1004A718C
0x1004a7183  test    rax, rax
0x1004a7186  jnz     loc_1004A7293
0x1004a718c  mov     ecx, cs:dword_100720F68
0x1004a7192  test    ecx, ecx
0x1004a7194  jz      short loc_1004A71B1
0x1004a7196  test    rdx, rdx
0x1004a7199  jnz     short loc_1004A71AC
0x1004a719b  test    rax, rax
0x1004a719e  jnz     short loc_1004A71AC
0x1004a71a0  mov     rdx, rdi
0x1004a71a3  shr     rdx, 1
0x1004a71a6  imul    rdx, rcx
0x1004a71aa  jmp     short loc_1004A71D0
0x1004a71ac  mov     rdx, r15
0x1004a71af  jmp     short loc_1004A71D0
0x1004a71b1  mov     rax, cs:qword_100720F60
0x1004a71b8  add     rax, 0FFFFFFh
0x1004a71be  and     rax, 0FFFFFFFFFF000000h
0x1004a71c4  lea     rdx, [rdi+10h]
0x1004a71c8  shr     rax, 18h
0x1004a71cc  imul    rdx, rax
0x1004a71d0  mov     [r14+38h], rdx
0x1004a71d4  cmp     qword ptr [r14], 0
0x1004a71d8  jnz     short loc_1004A71E5
0x1004a71da  add     rdx, 8000h
0x1004a71e1  mov     [r14+38h], rdx
0x1004a71e5  mov     ecx, cs:dword_1007153F0
0x1004a71eb  lea     rdi, [rcx-1]
0x1004a71ef  add     rdi, rdx
0x1004a71f2  xor     edx, edx
0x1004a71f4  mov     rax, rdi
0x1004a71f7  div     rcx
0x1004a71fa  sub     rdi, rdx
0x1004a71fd  mov     [r14+38h], rdi
0x1004a7201  xor     eax, eax
0x1004a7203  mov     [rbp+57h+var_70], rax
0x1004a7207  mov     [rbp+57h+var_68], rax
0x1004a720b  call    cs:__imp_GetCurrentProcess
0x1004a7211  mov     rbx, rax
0x1004a7214  lea     rcx, qword_1007B9C00
0x1004a721b  mov     rdx, cs:qword_1007B9C00
0x1004a7222  call    qword ptr [rdx+20h]
0x1004a7225  mov     rcx, rax
0x1004a7228  lea     rax, [rbp+57h+var_68]
0x1004a722c  mov     [rsp+0C0h+var_80], rax
0x1004a7231  lea     rax, [rbp+57h+var_70]
0x1004a7235  mov     [rsp+0C0h+var_88], rax
0x1004a723a  mov     edx, dword ptr cs:qword_1007BA188+4
0x1004a7240  mov     [rsp+0C0h+var_90], edx
0x1004a7244  mov     [rsp+0C0h+var_98], 4
0x1004a724c  mov     dword ptr [rsp+0C0h+Format], 2000h
0x1004a7254  mov     r9, rdi
0x1004a7257  xor     r8d, r8d
0x1004a725a  mov     rdx, rbx
0x1004a725d  call    ?VirtualAlloc@MemoryNode@@AEAAPEAXPEAX0_KKKW4AllocationFailMode@@PEA_J3@Z; MemoryNode::VirtualAlloc(void *,void *,unsigned __int64,ulong,ulong,AllocationFailMode,__int64 *,__int64 *)
0x1004a7262  mov     rcx, [rbp+57h+var_70]
0x1004a7266  test    rcx, rcx
0x1004a7269  jz      short loc_1004A7274
0x1004a726b  lock xadd cs:qword_1007BA1A8, rcx
0x1004a7274  mov     rcx, [rbp+57h+var_68]
0x1004a7278  test    rcx, rcx
0x1004a727b  jz      short loc_1004A7286
0x1004a727d  lock xadd qword ptr cs:xmmword_1007BA1B0, rcx
0x1004a7286  mov     [r14+30h], rax
0x1004a728a  test    rax, rax
0x1004a728d  jz      loc_1004A73E0
0x1004a7293  lea     r12, [rax+0FFFh]
0x1004a729a  and     r12, 0FFFFFFFFFFFFF000h
0x1004a72a1  lea     rdi, [r15+0FFFh]
0x1004a72a8  add     rdi, rax
0x1004a72ab  and     rdi, 0FFFFFFFFFFFFF000h
0x1004a72b2  sub     rdi, r12
0x1004a72b5  cmp     qword ptr [r14], 0
0x1004a72b9  jnz     short loc_1004A72C9
0x1004a72bb  add     rdi, 8FFFh
0x1004a72c2  and     rdi, 0FFFFFFFFFFFFF000h
0x1004a72c9  test    rdi, rdi
0x1004a72cc  jz      loc_1004A7360
0x1004a72d2  xor     eax, eax
0x1004a72d4  mov     [rbp+57h+var_60], rax
0x1004a72d8  mov     [rbp+57h+ListHead], rax
0x1004a72dc  call    cs:__imp_GetCurrentProcess
0x1004a72e2  mov     rbx, rax
0x1004a72e5  lea     rcx, qword_1007B9C00
0x1004a72ec  mov     rdx, cs:qword_1007B9C00
0x1004a72f3  call    qword ptr [rdx+20h]
0x1004a72f6  mov     rcx, rax
0x1004a72f9  lea     rax, [rbp+57h+ListHead]
0x1004a72fd  mov     [rsp+0C0h+var_80], rax
0x1004a7302  lea     rax, [rbp+57h+var_60]
0x1004a7306  mov     [rsp+0C0h+var_88], rax
0x1004a730b  mov     edx, dword ptr cs:qword_1007BA188+4
0x1004a7311  mov     [rsp+0C0h+var_90], edx
0x1004a7315  mov     [rsp+0C0h+var_98], 4
0x1004a731d  mov     dword ptr [rsp+0C0h+Format], 1000h
0x1004a7325  mov     r9, rdi
0x1004a7328  mov     r8, r12
0x1004a732b  mov     rdx, rbx
0x1004a732e  call    ?VirtualAlloc@MemoryNode@@AEAAPEAXPEAX0_KKKW4AllocationFailMode@@PEA_J3@Z; MemoryNode::VirtualAlloc(void *,void *,unsigned __int64,ulong,ulong,AllocationFailMode,__int64 *,__int64 *)
0x1004a7333  mov     rcx, [rbp+57h+var_60]
0x1004a7337  test    rcx, rcx
0x1004a733a  jz      short loc_1004A7345
0x1004a733c  lock xadd cs:qword_1007BA1A8, rcx
0x1004a7345  mov     rcx, [rbp+57h+ListHead]
0x1004a7349  test    rcx, rcx
0x1004a734c  jz      short loc_1004A7357
0x1004a734e  lock xadd qword ptr cs:xmmword_1007BA1B0, rcx
0x1004a7357  test    rax, rax
0x1004a735a  jz      loc_1004A73E0
0x1004a7360  cmp     qword ptr [r14], 0
  ... truncated ...
```
