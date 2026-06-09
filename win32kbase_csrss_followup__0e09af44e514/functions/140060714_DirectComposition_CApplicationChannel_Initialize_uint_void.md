# DirectComposition::CApplicationChannel::Initialize(uint *,void * *)

- ea: `0x140060714`
- end: `0x140060ab9`
- name: `?Initialize@CApplicationChannel@DirectComposition@@IEAAJPEAIPEAPEAX@Z`
- size: `933`
- prototype: `__int64 __fastcall(DirectComposition::CApplicationChannel *__hidden this, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140060494`
- `0x1401213c4`

## callees

- `0x14005610c`
- `0x140058a94`
- `0x140060714`
- `0x140060ac0`
- `0x140060b34`
- `0x140060cdc`
- `0x140060d50`
- `0x140060dd0`
- `0x140060f80`
- `0x140061490`
- `0x1400614d0`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14006075b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14006075b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006098d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006098d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140060749`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140060749`
- `ntoskrnl!PsProcessType` at `0x14006077d`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x140060771`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x140060771`
- `ntoskrnl!MmMapViewOfSection` at `0x14006089d`
- `ntoskrnl!MmMapViewOfSection` at `0x14006089d`
- `ntoskrnl!MmCreateSection` at `0x140060815`
- `ntoskrnl!MmCreateSection` at `0x140060815`
- `ntoskrnl!MmMapViewInSessionSpace` at `0x140060839`
- `ntoskrnl!MmMapViewInSessionSpace` at `0x140060839`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14006079d`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14006079d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140060981`
- `ntoskrnl!ExReleaseResourceLite` at `0x140060981`

## pseudocode

```c
__int64 __fastcall DirectComposition::CApplicationChannel::Initialize(
        DirectComposition::CApplicationChannel *this,
        unsigned int *a2,
        void **a3)
{
  int v6; // eax
  NTSTATUS Batch; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 CurrentProcess; // rax
  __int64 ProcessSequenceNumber; // rax
  void *v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  PVOID *v16; // rsi
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdx
  PVOID v20; // rcx
  int v21; // eax
  enum _EVENT_TYPE v22; // ecx
  unsigned __int64 v23; // rdx
  enum _EVENT_TYPE v25; // ecx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  ULONG_PTR ViewSize; // [rsp+80h] [rbp+30h] BYREF
  DirectComposition::CBatchSharedMemoryPool *v31; // [rsp+98h] [rbp+48h] BYREF

  v6 = DirectComposition::CChannel::Initialize(this);
  ViewSize = 0;
  Batch = v6;
  if ( v6 >= 0 )
  {
    *((_DWORD *)this + 688) = (unsigned int)PsGetCurrentProcessId();
    CurrentProcess = PsGetCurrentProcess(v9, v8, v10);
    *((_QWORD *)this + 341) = CurrentProcess;
    ProcessSequenceNumber = PsGetProcessSequenceNumber(CurrentProcess);
    v13 = (void *)*((_QWORD *)this + 341);
    *((_QWORD *)this + 343) = ProcessSequenceNumber;
    Batch = ObReferenceObjectByPointer(v13, 0x1FFFFFu, (POBJECT_TYPE)PsProcessType, 0);
  }
  v14 = *((_DWORD *)this + 692);
  if ( !v14 )
    goto LABEL_9;
  if ( Batch < 0 )
    goto LABEL_13;
  v15 = (v14 + 4095) & 0xFFFFF000;
  *((_DWORD *)this + 692) = v15;
  if ( !v15 )
  {
    Batch = -1073741801;
    goto LABEL_13;
  }
  v16 = (PVOID *)((char *)this + 2760);
  v31 = (DirectComposition::CBatchSharedMemoryPool *)v15;
  Batch = MmCreateSection((char *)this + 2760, 6, 0, &v31, 4, 138412032, 0, 0);
  if ( Batch >= 0 )
  {
    Batch = MmMapViewInSessionSpace(*v16, (PVOID *)this + 347, &ViewSize);
    if ( Batch >= 0 )
    {
      v18 = *((unsigned int *)this + 692);
      v19 = *((_QWORD *)this + 341);
      v20 = *v16;
      v31 = 0;
      Batch = MmMapViewOfSection(v20, v19, (char *)this + 2784, 0, v18, &v31, &ViewSize, 2, 0x400000, 4);
LABEL_9:
      if ( Batch < 0 )
        goto LABEL_13;
      v21 = (*(__int64 (__fastcall **)(DirectComposition::CApplicationChannel *))(*(_QWORD *)this + 8LL))(this);
      Batch = DirectComposition::CEvent::Create(v22, v21 != 2, (struct DirectComposition::CEvent **)this + 30);
    }
  }
  if ( Batch >= 0 )
  {
    Batch = DirectComposition::CBatchSharedMemoryPoolSet::ReservePools(
              (DirectComposition::CApplicationChannel *)((char *)this + 2648),
              v17);
    if ( Batch >= 0 )
    {
      DirectComposition::CBatchSharedMemoryPoolSet::StaticAllocate(
        (DirectComposition::CApplicationChannel *)((char *)this + 2648),
        v23,
        (struct DirectComposition::CBatchSharedMemoryPool **)this + 335,
        (unsigned __int64 *)this + 336);
      v31 = 0;
      if ( (int)DirectComposition::CBatchSharedMemoryPoolSet::BeginDynamicAllocation(
                  (DirectComposition::CApplicationChannel *)((char *)this + 2648),
                  0x28u,
                  &v31,
                  (unsigned __int64 *)this + 337) >= 0 )
      {
        DirectComposition::CBatchSharedMemoryPool::UseSpace(v31, 0x28u);
        *(_BYTE *)(v27 + 64) = 0;
      }
      Batch = DirectComposition::CApplicationChannel::CreateBatch(this, (struct DirectComposition::CBatch **)this + 25);
      if ( Batch >= 0 )
      {
        v31 = 0;
        Batch = DirectComposition::CApplicationChannel::CreateBatch(this, &v31);
        if ( Batch >= 0 )
        {
          **((_QWORD **)this + 25) = v31;
          Batch = DirectComposition::CApplicationChannel::CreateBatch(
                    this,
                    (struct DirectComposition::CBatch **)this + 24);
          if ( Batch >= 0 )
          {
            v28 = *((_QWORD *)this + 24);
            v29 = *((_QWORD *)this + 337);
            *(_QWORD *)(v28 + 136) = *((_QWORD *)this + 335);
            *(_QWORD *)(v28 + 144) = v29;
          }
        }
      }
    }
  }
LABEL_13:
  *((_BYTE *)this + 265) &= ~0x10u;
  *((_BYTE *)this + 267) = 0;
  if ( Batch >= 0 )
  {
    if ( (*(unsigned int (__fastcall **)(DirectComposition::CApplicationChannel *))(*(_QWORD *)this + 8LL))(this) == 2
      || (Batch = DirectComposition::CEvent::Create(v25, 1, (struct DirectComposition::CEvent **)this + 29), Batch >= 0) )
    {
      DirectComposition::CCriticalSection::AcquireShared(*(PERESOURCE *)(*((_QWORD *)this + 5) + 16LL));
      v26 = DirectComposition::CConnection::RegisterChannel(
              *((DirectComposition::CConnection **)this + 5),
              this,
              (unsigned int *)this + 7);
      Batch = v26;
      if ( v26 < 0 )
      {
        if ( v26 == -1073741300 )
        {
          *((_DWORD *)this + 6) = 3;
          Batch = 0;
        }
      }
      else
      {
        DirectComposition::CApplicationChannel::OpenChannel(this);
      }
      ExReleaseResourceLite(*(PERESOURCE *)(*((_QWORD *)this + 5) + 16LL));
      KeLeaveCriticalRegion();
      if ( Batch >= 0 )
      {
        if ( a2 )
          *a2 = *((_DWORD *)this + 692);
        if ( a3 )
          *a3 = (void *)*((_QWORD *)this + 348);
      }
    }
  }
  return (unsigned int)Batch;
}

```

## disassembly

```asm
0x140060714  mov     [rsp-28h+arg_8], rbx
0x140060719  mov     [rsp-28h+arg_10], rsi
0x14006071e  push    rbp
0x14006071f  push    rdi
0x140060720  push    r12
0x140060722  push    r14
0x140060724  push    r15
0x140060726  mov     rbp, rsp
0x140060729  sub     rsp, 50h
0x14006072d  mov     r15, r8
0x140060730  mov     r12, rdx
0x140060733  mov     rdi, rcx
0x140060736  call    ?Initialize@CChannel@DirectComposition@@MEAAJXZ; DirectComposition::CChannel::Initialize(void)
0x14006073b  mov     [rbp+ViewSize], 0
0x140060743  mov     ebx, eax
0x140060745  test    eax, eax
0x140060747  js      short loc_1400607AB
0x140060749  call    cs:__imp_PsGetCurrentProcessId
0x140060750  nop     dword ptr [rax+rax+00h]
0x140060755  mov     [rdi+0AC0h], eax
0x14006075b  call    cs:__imp_PsGetCurrentProcess
0x140060762  nop     dword ptr [rax+rax+00h]
0x140060767  mov     rcx, rax
0x14006076a  mov     [rdi+0AA8h], rax
0x140060771  call    cs:__imp_PsGetProcessSequenceNumber
0x140060778  nop     dword ptr [rax+rax+00h]
0x14006077d  mov     r8, cs:__imp_PsProcessType
0x140060784  xor     r9d, r9d; AccessMode
0x140060787  mov     rcx, [rdi+0AA8h]; Object
0x14006078e  mov     edx, 1FFFFFh; DesiredAccess
0x140060793  mov     [rdi+0AB8h], rax
0x14006079a  mov     r8, [r8]; ObjectType
0x14006079d  call    cs:__imp_ObReferenceObjectByPointer
0x1400607a4  nop     dword ptr [rax+rax+00h]
0x1400607a9  mov     ebx, eax
0x1400607ab  mov     eax, [rdi+0AD0h]
0x1400607b1  test    eax, eax
0x1400607b3  jz      loc_1400608AB
0x1400607b9  test    ebx, ebx
0x1400607bb  js      loc_1400608F1
0x1400607c1  add     eax, 0FFFh
0x1400607c6  and     eax, 0FFFFF000h
0x1400607cb  mov     [rdi+0AD0h], eax
0x1400607d1  jz      loc_140060A96
0x1400607d7  mov     [rsp+50h+var_18], 0
0x1400607e0  lea     rsi, [rdi+0AC8h]
0x1400607e7  mov     r14d, 4
0x1400607ed  mov     [rsp+50h+var_20], 0
0x1400607f6  mov     dword ptr [rsp+50h+var_28], 8400000h
0x1400607fe  lea     r9, [rbp+arg_18]
0x140060802  xor     r8d, r8d
0x140060805  mov     [rbp+arg_18], rax
0x140060809  mov     rcx, rsi
0x14006080c  mov     dword ptr [rsp+50h+var_30], r14d
0x140060811  lea     edx, [r14+2]
0x140060815  call    cs:__imp_MmCreateSection
0x14006081c  nop     dword ptr [rax+rax+00h]
0x140060821  mov     ebx, eax
0x140060823  test    eax, eax
0x140060825  js      loc_1400608D4
0x14006082b  mov     rcx, [rsi]; Section
0x14006082e  lea     rdx, [rdi+0AD8h]; MappedBase
0x140060835  lea     r8, [rbp+ViewSize]; ViewSize
0x140060839  call    cs:__imp_MmMapViewInSessionSpace
0x140060840  nop     dword ptr [rax+rax+00h]
0x140060845  mov     ebx, eax
0x140060847  test    eax, eax
0x140060849  js      loc_1400608D4
0x14006084f  mov     eax, [rdi+0AD0h]
0x140060855  lea     rcx, [rbp+ViewSize]
0x140060859  mov     rdx, [rdi+0AA8h]
0x140060860  lea     r8, [rdi+0AE0h]
0x140060867  mov     [rsp+50h+var_8], r14d
0x14006086c  xor     r9d, r9d
0x14006086f  mov     [rsp+50h+var_10], 400000h
0x140060877  mov     dword ptr [rsp+50h+var_18], 2
0x14006087f  mov     [rsp+50h+var_20], rcx
0x140060884  lea     rcx, [rbp+arg_18]
0x140060888  mov     [rsp+50h+var_28], rcx
0x14006088d  mov     rcx, [rsi]
0x140060890  mov     [rbp+arg_18], 0
0x140060898  mov     [rsp+50h+var_30], rax
0x14006089d  call    cs:__imp_MmMapViewOfSection
0x1400608a4  nop     dword ptr [rax+rax+00h]
0x1400608a9  mov     ebx, eax
0x1400608ab  test    ebx, ebx
0x1400608ad  js      short loc_1400608F1
0x1400608af  mov     rax, [rdi]
0x1400608b2  mov     rcx, rdi
0x1400608b5  mov     rax, [rax+8]
0x1400608b9  call    _guard_dispatch_icall
0x1400608be  xor     edx, edx
0x1400608c0  lea     r8, [rdi+0F0h]; struct DirectComposition::CEvent **
0x1400608c7  cmp     eax, 2
0x1400608ca  setnz   dl; int
0x1400608cd  call    ?Create@CEvent@DirectComposition@@SAJW4_EVENT_TYPE@@HPEAPEAV12@@Z; DirectComposition::CEvent::Create(_EVENT_TYPE,int,DirectComposition::CEvent * *)
0x1400608d2  mov     ebx, eax
0x1400608d4  test    ebx, ebx
0x1400608d6  js      short loc_1400608F1
0x1400608d8  lea     rsi, [rdi+0A58h]
0x1400608df  mov     rcx, rsi; this
0x1400608e2  call    ?ReservePools@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::ReservePools(unsigned __int64)
0x1400608e7  mov     ebx, eax
0x1400608e9  test    eax, eax
0x1400608eb  jns     loc_1400609C8
0x1400608f1  and     byte ptr [rdi+109h], 0EFh
0x1400608f8  mov     byte ptr [rdi+10Bh], 0
0x1400608ff  test    ebx, ebx
0x140060901  jns     short loc_14006091F
0x140060903  lea     r11, [rsp+50h+var_s0]
0x140060908  mov     eax, ebx
0x14006090a  mov     rbx, [r11+38h]
0x14006090e  mov     rsi, [r11+40h]
0x140060912  mov     rsp, r11
0x140060915  pop     r15
0x140060917  pop     r14
0x140060919  pop     r12
0x14006091b  pop     rdi
0x14006091c  pop     rbp
0x14006091d  retn
0x14006091f  mov     rax, [rdi]
0x140060922  mov     rcx, rdi
0x140060925  mov     rax, [rax+8]
0x140060929  call    _guard_dispatch_icall
0x14006092e  cmp     eax, 2
0x140060931  jz      short loc_14006094A
0x140060933  lea     r8, [rdi+0E8h]; struct DirectComposition::CEvent **
0x14006093a  mov     edx, 1; int
0x14006093f  call    ?Create@CEvent@DirectComposition@@SAJW4_EVENT_TYPE@@HPEAPEAV12@@Z; DirectComposition::CEvent::Create(_EVENT_TYPE,int,DirectComposition::CEvent * *)
0x140060944  mov     ebx, eax
0x140060946  test    eax, eax
0x140060948  js      short loc_140060903
0x14006094a  mov     rcx, [rdi+28h]
0x14006094e  mov     rcx, [rcx+10h]; Resource
0x140060952  call    ?AcquireShared@CCriticalSection@DirectComposition@@QEAAXXZ; DirectComposition::CCriticalSection::AcquireShared(void)
0x140060957  mov     rcx, [rdi+28h]; this
0x14006095b  lea     r8, [rdi+1Ch]; unsigned int *
0x14006095f  mov     rdx, rdi; struct DirectComposition::CChannel *
0x140060962  call    ?RegisterChannel@CConnection@DirectComposition@@QEAAJPEAVCChannel@2@PEAI@Z; DirectComposition::CConnection::RegisterChannel(DirectComposition::CChannel *,uint *)
0x140060967  mov     ebx, eax
0x140060969  test    eax, eax
0x14006096b  js      loc_140060AA0
0x140060971  mov     rcx, rdi; this
0x140060974  call    ?OpenChannel@CApplicationChannel@DirectComposition@@IEAAXXZ; DirectComposition::CApplicationChannel::OpenChannel(void)
0x140060979  mov     rcx, [rdi+28h]
0x14006097d  mov     rcx, [rcx+10h]; Resource
0x140060981  call    cs:__imp_ExReleaseResourceLite
0x140060988  nop     dword ptr [rax+rax+00h]
0x14006098d  call    cs:__imp_KeLeaveCriticalRegion
0x140060994  nop     dword ptr [rax+rax+00h]
0x140060999  test    ebx, ebx
0x14006099b  js      loc_140060903
0x1400609a1  test    r12, r12
0x1400609a4  jz      short loc_1400609B0
0x1400609a6  mov     eax, [rdi+0AD0h]
0x1400609ac  mov     [r12], eax
0x1400609b0  test    r15, r15
0x1400609b3  jz      loc_140060903
0x1400609b9  mov     rax, [rdi+0AE0h]
0x1400609c0  mov     [r15], rax
0x1400609c3  jmp     loc_140060903
0x1400609c8  lea     rbx, [rdi+0A80h]
0x1400609cf  mov     rcx, rsi; this
0x1400609d2  lea     r14, [rdi+0A78h]
0x1400609d9  mov     r9, rbx; unsigned __int64 *
0x1400609dc  mov     r8, r14; struct DirectComposition::CBatchSharedMemoryPool **
0x1400609df  call    ?StaticAllocate@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_KPEAPEAVCBatchSharedMemoryPool@2@PEA_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::StaticAllocate(unsigned __int64,DirectComposition::CBatchSharedMemoryPool * *,unsigned __int64 *)
0x1400609e4  lea     r9, [rbx+8]; unsigned __int64 *
0x1400609e8  mov     [rbp+arg_18], 0
0x1400609f0  mov     ebx, 28h ; '('
0x1400609f5  lea     r8, [rbp+arg_18]; struct DirectComposition::CBatchSharedMemoryPool **
0x1400609f9  mov     edx, ebx; unsigned __int64
0x1400609fb  mov     rcx, rsi; this
0x1400609fe  call    ?BeginDynamicAllocation@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_KPEAPEAVCBatchSharedMemoryPool@2@PEA_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::BeginDynamicAllocation(unsigned __int64,DirectComposition::CBatchSharedMemoryPool * *,unsigned __int64 *)
0x140060a03  test    eax, eax
0x140060a05  js      short loc_140060A16
0x140060a07  mov     rcx, [rbp+arg_18]; this
0x140060a0b  mov     edx, ebx; unsigned __int64
0x140060a0d  call    ?UseSpace@CBatchSharedMemoryPool@DirectComposition@@QEAAPEAX_K@Z; DirectComposition::CBatchSharedMemoryPool::UseSpace(unsigned __int64)
0x140060a12  mov     byte ptr [rcx+40h], 0
0x140060a16  lea     rsi, [rdi+0C8h]
0x140060a1d  mov     rcx, rdi; this
0x140060a20  mov     rdx, rsi; struct DirectComposition::CBatch **
0x140060a23  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x140060a28  mov     ebx, eax
0x140060a2a  test    eax, eax
0x140060a2c  js      loc_1400608F1
0x140060a32  lea     rdx, [rbp+arg_18]; struct DirectComposition::CBatch **
0x140060a36  mov     [rbp+arg_18], 0
0x140060a3e  mov     rcx, rdi; this
0x140060a41  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x140060a46  mov     ebx, eax
0x140060a48  test    eax, eax
0x140060a4a  js      loc_1400608F1
0x140060a50  mov     rcx, [rsi]
0x140060a53  lea     rsi, [rdi+0C0h]
0x140060a5a  mov     rax, [rbp+arg_18]
0x140060a5e  mov     rdx, rsi; struct DirectComposition::CBatch **
0x140060a61  mov     [rcx], rax
0x140060a64  mov     rcx, rdi; this
0x140060a67  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x140060a6c  mov     ebx, eax
0x140060a6e  test    eax, eax
0x140060a70  js      loc_1400608F1
0x140060a76  mov     rdx, [rsi]
0x140060a79  mov     rcx, [rdi+0A88h]
0x140060a80  mov     rax, [r14]
0x140060a83  mov     [rdx+88h], rax
0x140060a8a  mov     [rdx+90h], rcx
0x140060a91  jmp     loc_1400608F1
0x140060a96  mov     ebx, 0C0000017h
0x140060a9b  jmp     loc_1400608F1
0x140060aa0  cmp     eax, 0C000020Ch
0x140060aa5  jnz     loc_140060979
0x140060aab  mov     dword ptr [rdi+18h], 3
0x140060ab2  xor     ebx, ebx
0x140060ab4  jmp     loc_140060979
```
