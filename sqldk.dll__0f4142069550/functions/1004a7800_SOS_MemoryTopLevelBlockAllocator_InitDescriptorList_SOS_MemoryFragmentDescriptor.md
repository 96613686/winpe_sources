# SOS_MemoryTopLevelBlockAllocator::InitDescriptorList(SOS_MemoryFragmentDescriptor *)

- ea: `0x1004a7800`
- end: `0x1004a7a0b`
- name: `?InitDescriptorList@SOS_MemoryTopLevelBlockAllocator@@AEAA_NPEAVSOS_MemoryFragmentDescriptor@@@Z`
- size: `523`
- prototype: `bool __fastcall(SOS_MemoryTopLevelBlockAllocator *__hidden this, struct SOS_MemoryFragmentDescriptor *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1004378f0`
- `0x1004a9580`
- `0x1004aab70`

## callees

- `0x100403070`
- `0x1004360f0`
- `0x1004a7800`
- `0x1004a7a20`
- `0x1004a7b10`
- `0x1004a7c90`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x1004a7878`
- `KERNEL32!InitializeSListHead` at `0x1004a7878`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a7919`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a79ad`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a7919`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a79ad`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a798d`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a79c4`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a798d`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a79c4`

## pseudocode

```c
_BOOL8 __fastcall SOS_MemoryTopLevelBlockAllocator::InitDescriptorList(
        union _SLIST_HEADER *this,
        struct SOS_MemoryFragmentDescriptor *a2)
{
  int v2; // r14d
  __int64 v4; // rbx
  unsigned __int64 v7; // rsi
  unsigned __int64 i; // rdi
  __int64 v9; // r15
  __int64 v10; // rbp
  __int64 v11; // rax
  __int64 v12; // rax
  struct _SLIST_ENTRY *v13; // rbp
  unsigned __int64 v14; // rdx
  __int64 v15; // rbx
  void (*v16)(const wchar_t *, ...); // rax
  unsigned __int64 v17; // rdx
  struct _SLIST_ENTRY *v18; // rbx
  PSLIST_ENTRY v19; // rax
  union _SLIST_HEADER ListHead; // [rsp+30h] [rbp-48h] BYREF

  v2 = dword_100720F58;
  v4 = *((_QWORD *)a2 + 4);
  if ( dword_100720F58 == 1 )
    return 1;
  v7 = *((_QWORD *)a2 + 5) >> 24;
  if ( dword_100720F58 == 4 )
    v4 = (v7 << 24) + v4 - 0x1000000;
  InitializeSListHead(&ListHead);
  for ( i = 0; i < v7; ++i )
  {
    v9 = v4;
    v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
        + (unsigned int)SystemThread_TlsOffset;
    v11 = *(_QWORD *)(v10 + 256);
    if ( !v11 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v11 = *(_QWORD *)(v10 + 256);
    }
    v12 = DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::Pop(
            &SOS_MemoryTopLevelBlockAllocator::sm_TopLevelBlockDescriptorAllocator,
            *(unsigned int *)(v11 + 76),
            v11,
            0);
    v13 = (struct _SLIST_ENTRY *)v12;
    if ( !v12 )
      break;
    if ( !(unsigned int)SOS_TopLevelBlockDescriptor::Init(v12, v4, a2, 0, v2) )
    {
      SOS_TopLevelBlockDescriptor::Release(v13, v14);
      break;
    }
    InterlockedPushEntrySList(&ListHead, v13);
    v15 = -16777216;
    if ( v2 != 4 )
      v15 = 0x1000000;
    v4 = v9 + v15;
    if ( i > 0x6000 && (i & 0xFFF) == 0 )
    {
      v16 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
      if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
        v16 = SOS_OS_LogUnlocalizedRoutine;
      v16(L"Top level memory blocks allocated=%#Ix\n", i);
    }
  }
  v18 = InterlockedPopEntrySList(&ListHead);
  while ( v18 )
  {
    if ( i < v7 )
      SOS_TopLevelBlockDescriptor::Release(v18, v17);
    else
      InterlockedPushEntrySList(this + 4, v18);
    v18 = 0;
    v19 = InterlockedPopEntrySList(&ListHead);
    if ( v19 )
      v18 = v19;
  }
  return i >= v7;
}

```

## disassembly

```asm
0x1004a7800  push    rbx
0x1004a7802  push    r12
0x1004a7804  push    r13
0x1004a7806  push    r14
0x1004a7808  sub     rsp, 58h
0x1004a780c  mov     rax, cs:__security_cookie
0x1004a7813  xor     rax, rsp
0x1004a7816  mov     [rsp+78h+var_38], rax
0x1004a781b  mov     r14d, cs:dword_100720F58
0x1004a7822  mov     r13, rdx
0x1004a7825  mov     rbx, [rdx+20h]
0x1004a7829  mov     r12, rcx
0x1004a782c  cmp     r14d, 1
0x1004a7830  jnz     short loc_1004A783C
0x1004a7832  movzx   eax, r14b
0x1004a7836  jmp     loc_1004A79F2
0x1004a783c  mov     [rsp+78h+arg_8], rbp
0x1004a7844  mov     [rsp+78h+arg_10], rsi
0x1004a784c  mov     rsi, [rdx+28h]
0x1004a7850  shr     rsi, 18h
0x1004a7854  mov     [rsp+78h+arg_18], rdi
0x1004a785c  cmp     r14d, 4
0x1004a7860  jnz     short loc_1004A7873
0x1004a7862  mov     rax, rsi
0x1004a7865  add     rbx, 0FFFFFFFFFF000000h
0x1004a786c  shl     rax, 18h
0x1004a7870  add     rbx, rax
0x1004a7873  lea     rcx, [rsp+78h+ListHead]; ListHead
0x1004a7878  call    cs:__imp_InitializeSListHead
0x1004a787e  xor     edi, edi
0x1004a7880  test    rsi, rsi
0x1004a7883  jz      loc_1004A7981
0x1004a7889  mov     [rsp+78h+var_28], r15
0x1004a788e  nop     dword ptr [rax]
0x1004a7891  nop     dword ptr [rax+00h]
0x1004a7895  nop     word ptr [rax+rax+00000000h]
0x1004a78a0  mov     rcx, gs:58h
0x1004a78a9  mov     r15, rbx
0x1004a78ac  mov     eax, cs:_tls_index
0x1004a78b2  mov     ebp, cs:SystemThread_TlsOffset
0x1004a78b8  add     rbp, [rcx+rax*8]
0x1004a78bc  mov     rax, [rbp+100h]
0x1004a78c3  test    rax, rax
0x1004a78c6  jnz     short loc_1004A78D6
0x1004a78c8  xor     ecx, ecx; void *
0x1004a78ca  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a78cf  mov     rax, [rbp+100h]
0x1004a78d6  mov     edx, [rax+4Ch]
0x1004a78d9  lea     rcx, ?sm_TopLevelBlockDescriptorAllocator@SOS_MemoryTopLevelBlockAllocator@@2V?$DescriptorAllocator@VSOS_TopLevelBlockDescriptor@@$0A@@@A; DescriptorAllocator<SOS_TopLevelBlockDescriptor,0> SOS_MemoryTopLevelBlockAllocator::sm_TopLevelBlockDescriptorAllocator
0x1004a78e0  xor     r9d, r9d
0x1004a78e3  mov     r8, rax
0x1004a78e6  call    ?Pop@?$DescriptorAllocator@VSOS_TopLevelBlockDescriptor@@$0A@@@QEAAPEAVSOS_TopLevelBlockDescriptor@@IPEAVWorker@@PEAE@Z; DescriptorAllocator<SOS_TopLevelBlockDescriptor,0>::Pop(uint,Worker *,uchar *)
0x1004a78eb  mov     rbp, rax
0x1004a78ee  test    rax, rax
0x1004a78f1  jz      loc_1004A797C
0x1004a78f7  xor     r9d, r9d
0x1004a78fa  mov     [rsp+78h+var_58], r14d
0x1004a78ff  mov     r8, r13
0x1004a7902  mov     rdx, rbx
0x1004a7905  mov     rcx, rax
0x1004a7908  call    ?Init@SOS_TopLevelBlockDescriptor@@QEAAHPEAXPEAVSOS_MemoryFragmentDescriptor@@_KW4SOS_MemoryModel@@@Z; SOS_TopLevelBlockDescriptor::Init(void *,SOS_MemoryFragmentDescriptor *,unsigned __int64,SOS_MemoryModel)
0x1004a790d  test    eax, eax
0x1004a790f  jz      short loc_1004A7974
0x1004a7911  mov     rdx, rbp; ListEntry
0x1004a7914  lea     rcx, [rsp+78h+ListHead]; ListHead
0x1004a7919  call    cs:__imp_InterlockedPushEntrySList
0x1004a791f  cmp     r14d, 4
0x1004a7923  mov     rbx, 0FFFFFFFFFF000000h
0x1004a792a  mov     eax, 1000000h
0x1004a792f  cmovnz  rbx, rax
0x1004a7933  add     rbx, r15
0x1004a7936  cmp     rdi, 6000h
0x1004a793d  jbe     short loc_1004A7966
0x1004a793f  test    rdi, 0FFFh
0x1004a7946  jnz     short loc_1004A7966
0x1004a7948  mov     rax, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x1004a794f  lea     rcx, aTopLevelMemory; "Top level memory blocks allocated=%#Ix"...
0x1004a7956  test    rax, rax
0x1004a7959  mov     rdx, rdi
0x1004a795c  cmovz   rax, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x1004a7964  call    rax
0x1004a7966  inc     rdi
0x1004a7969  cmp     rdi, rsi
0x1004a796c  jb      loc_1004A78A0
0x1004a7972  jmp     short loc_1004A797C
0x1004a7974  mov     rcx, rbp; ListEntry
0x1004a7977  call    ?Release@SOS_TopLevelBlockDescriptor@@QEAAX_K@Z; SOS_TopLevelBlockDescriptor::Release(unsigned __int64)
0x1004a797c  mov     r15, [rsp+78h+var_28]
0x1004a7981  cmp     rdi, rsi
0x1004a7984  lea     rcx, [rsp+78h+ListHead]; ListHead
0x1004a7989  setnb   bpl
0x1004a798d  call    cs:__imp_InterlockedPopEntrySList
0x1004a7993  mov     rbx, rax
0x1004a7996  test    rax, rax
0x1004a7999  jz      short loc_1004A79D6
0x1004a799b  nop     dword ptr [rax+rax]
0x1004a799f  nop
0x1004a79a0  cmp     rdi, rsi
0x1004a79a3  jb      short loc_1004A79B5
0x1004a79a5  lea     rcx, [r12+40h]; ListHead
0x1004a79aa  mov     rdx, rbx; ListEntry
0x1004a79ad  call    cs:__imp_InterlockedPushEntrySList
0x1004a79b3  jmp     short loc_1004A79BD
0x1004a79b5  mov     rcx, rbx; ListEntry
0x1004a79b8  call    ?Release@SOS_TopLevelBlockDescriptor@@QEAAX_K@Z; SOS_TopLevelBlockDescriptor::Release(unsigned __int64)
0x1004a79bd  lea     rcx, [rsp+78h+ListHead]; ListHead
0x1004a79c2  xor     ebx, ebx
0x1004a79c4  call    cs:__imp_InterlockedPopEntrySList
0x1004a79ca  test    rax, rax
0x1004a79cd  cmovnz  rbx, rax
0x1004a79d1  test    rbx, rbx
0x1004a79d4  jnz     short loc_1004A79A0
0x1004a79d6  mov     rdi, [rsp+78h+arg_18]
0x1004a79de  movzx   eax, bpl
0x1004a79e2  mov     rbp, [rsp+78h+arg_8]
0x1004a79ea  mov     rsi, [rsp+78h+arg_10]
0x1004a79f2  mov     rcx, [rsp+78h+var_38]
0x1004a79f7  xor     rcx, rsp; StackCookie
0x1004a79fa  call    __security_check_cookie
0x1004a79ff  add     rsp, 58h
0x1004a7a03  pop     r14
0x1004a7a05  pop     r13
0x1004a7a07  pop     r12
0x1004a7a09  pop     rbx
0x1004a7a0a  retn
```
