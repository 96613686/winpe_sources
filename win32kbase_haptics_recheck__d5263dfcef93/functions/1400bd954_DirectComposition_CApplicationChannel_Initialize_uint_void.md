# DirectComposition::CApplicationChannel::Initialize(uint *,void * *)

- ea: `0x1400bd954`
- end: `0x1400bdcf9`
- name: `?Initialize@CApplicationChannel@DirectComposition@@IEAAJPEAIPEAPEAX@Z`
- size: `933`
- prototype: `__int64 __fastcall(DirectComposition::CApplicationChannel *__hidden this, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400bd6d4`
- `0x140121334`

## callees

- `0x14004d34c`
- `0x14004fcd4`
- `0x1400bd954`
- `0x1400bdd00`
- `0x1400bdd74`
- `0x1400bdf1c`
- `0x1400bdf90`
- `0x1400be010`
- `0x1400be1c0`
- `0x1400be6d0`
- `0x1400be710`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400bd99b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400bd99b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bdbcd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bdbcd`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400bd989`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400bd989`
- `ntoskrnl!PsProcessType` at `0x1400bd9bd`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400bd9b1`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400bd9b1`
- `ntoskrnl!MmMapViewOfSection` at `0x1400bdadd`
- `ntoskrnl!MmMapViewOfSection` at `0x1400bdadd`
- `ntoskrnl!MmCreateSection` at `0x1400bda55`
- `ntoskrnl!MmCreateSection` at `0x1400bda55`
- `ntoskrnl!MmMapViewInSessionSpace` at `0x1400bda79`
- `ntoskrnl!MmMapViewInSessionSpace` at `0x1400bda79`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x1400bd9dd`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x1400bd9dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400bdbc1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400bdbc1`

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
0x1400bd954  mov     [rsp-28h+arg_8], rbx
0x1400bd959  mov     [rsp-28h+arg_10], rsi
0x1400bd95e  push    rbp
0x1400bd95f  push    rdi
0x1400bd960  push    r12
0x1400bd962  push    r14
0x1400bd964  push    r15
0x1400bd966  mov     rbp, rsp
0x1400bd969  sub     rsp, 50h
0x1400bd96d  mov     r15, r8
0x1400bd970  mov     r12, rdx
0x1400bd973  mov     rdi, rcx
0x1400bd976  call    ?Initialize@CChannel@DirectComposition@@MEAAJXZ; DirectComposition::CChannel::Initialize(void)
0x1400bd97b  mov     [rbp+ViewSize], 0
0x1400bd983  mov     ebx, eax
0x1400bd985  test    eax, eax
0x1400bd987  js      short loc_1400BD9EB
0x1400bd989  call    cs:__imp_PsGetCurrentProcessId
0x1400bd990  nop     dword ptr [rax+rax+00h]
0x1400bd995  mov     [rdi+0AC0h], eax
0x1400bd99b  call    cs:__imp_PsGetCurrentProcess
0x1400bd9a2  nop     dword ptr [rax+rax+00h]
0x1400bd9a7  mov     rcx, rax
0x1400bd9aa  mov     [rdi+0AA8h], rax
0x1400bd9b1  call    cs:__imp_PsGetProcessSequenceNumber
0x1400bd9b8  nop     dword ptr [rax+rax+00h]
0x1400bd9bd  mov     r8, cs:__imp_PsProcessType
0x1400bd9c4  xor     r9d, r9d; AccessMode
0x1400bd9c7  mov     rcx, [rdi+0AA8h]; Object
0x1400bd9ce  mov     edx, 1FFFFFh; DesiredAccess
0x1400bd9d3  mov     [rdi+0AB8h], rax
0x1400bd9da  mov     r8, [r8]; ObjectType
0x1400bd9dd  call    cs:__imp_ObReferenceObjectByPointer
0x1400bd9e4  nop     dword ptr [rax+rax+00h]
0x1400bd9e9  mov     ebx, eax
0x1400bd9eb  mov     eax, [rdi+0AD0h]
0x1400bd9f1  test    eax, eax
0x1400bd9f3  jz      loc_1400BDAEB
0x1400bd9f9  test    ebx, ebx
0x1400bd9fb  js      loc_1400BDB31
0x1400bda01  add     eax, 0FFFh
0x1400bda06  and     eax, 0FFFFF000h
0x1400bda0b  mov     [rdi+0AD0h], eax
0x1400bda11  jz      loc_1400BDCD6
0x1400bda17  mov     [rsp+50h+var_18], 0
0x1400bda20  lea     rsi, [rdi+0AC8h]
0x1400bda27  mov     r14d, 4
0x1400bda2d  mov     [rsp+50h+var_20], 0
0x1400bda36  mov     dword ptr [rsp+50h+var_28], 8400000h
0x1400bda3e  lea     r9, [rbp+arg_18]
0x1400bda42  xor     r8d, r8d
0x1400bda45  mov     [rbp+arg_18], rax
0x1400bda49  mov     rcx, rsi
0x1400bda4c  mov     dword ptr [rsp+50h+var_30], r14d
0x1400bda51  lea     edx, [r14+2]
0x1400bda55  call    cs:__imp_MmCreateSection
0x1400bda5c  nop     dword ptr [rax+rax+00h]
0x1400bda61  mov     ebx, eax
0x1400bda63  test    eax, eax
0x1400bda65  js      loc_1400BDB14
0x1400bda6b  mov     rcx, [rsi]; Section
0x1400bda6e  lea     rdx, [rdi+0AD8h]; MappedBase
0x1400bda75  lea     r8, [rbp+ViewSize]; ViewSize
0x1400bda79  call    cs:__imp_MmMapViewInSessionSpace
0x1400bda80  nop     dword ptr [rax+rax+00h]
0x1400bda85  mov     ebx, eax
0x1400bda87  test    eax, eax
0x1400bda89  js      loc_1400BDB14
0x1400bda8f  mov     eax, [rdi+0AD0h]
0x1400bda95  lea     rcx, [rbp+ViewSize]
0x1400bda99  mov     rdx, [rdi+0AA8h]
0x1400bdaa0  lea     r8, [rdi+0AE0h]
0x1400bdaa7  mov     [rsp+50h+var_8], r14d
0x1400bdaac  xor     r9d, r9d
0x1400bdaaf  mov     [rsp+50h+var_10], 400000h
0x1400bdab7  mov     dword ptr [rsp+50h+var_18], 2
0x1400bdabf  mov     [rsp+50h+var_20], rcx
0x1400bdac4  lea     rcx, [rbp+arg_18]
0x1400bdac8  mov     [rsp+50h+var_28], rcx
0x1400bdacd  mov     rcx, [rsi]
0x1400bdad0  mov     [rbp+arg_18], 0
0x1400bdad8  mov     [rsp+50h+var_30], rax
0x1400bdadd  call    cs:__imp_MmMapViewOfSection
0x1400bdae4  nop     dword ptr [rax+rax+00h]
0x1400bdae9  mov     ebx, eax
0x1400bdaeb  test    ebx, ebx
0x1400bdaed  js      short loc_1400BDB31
0x1400bdaef  mov     rax, [rdi]
0x1400bdaf2  mov     rcx, rdi
0x1400bdaf5  mov     rax, [rax+8]
0x1400bdaf9  call    _guard_dispatch_icall
0x1400bdafe  xor     edx, edx
0x1400bdb00  lea     r8, [rdi+0F0h]; struct DirectComposition::CEvent **
0x1400bdb07  cmp     eax, 2
0x1400bdb0a  setnz   dl; int
0x1400bdb0d  call    ?Create@CEvent@DirectComposition@@SAJW4_EVENT_TYPE@@HPEAPEAV12@@Z; DirectComposition::CEvent::Create(_EVENT_TYPE,int,DirectComposition::CEvent * *)
0x1400bdb12  mov     ebx, eax
0x1400bdb14  test    ebx, ebx
0x1400bdb16  js      short loc_1400BDB31
0x1400bdb18  lea     rsi, [rdi+0A58h]
0x1400bdb1f  mov     rcx, rsi; this
0x1400bdb22  call    ?ReservePools@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::ReservePools(unsigned __int64)
0x1400bdb27  mov     ebx, eax
0x1400bdb29  test    eax, eax
0x1400bdb2b  jns     loc_1400BDC08
0x1400bdb31  and     byte ptr [rdi+109h], 0EFh
0x1400bdb38  mov     byte ptr [rdi+10Bh], 0
0x1400bdb3f  test    ebx, ebx
0x1400bdb41  jns     short loc_1400BDB5F
0x1400bdb43  lea     r11, [rsp+50h+var_s0]
0x1400bdb48  mov     eax, ebx
0x1400bdb4a  mov     rbx, [r11+38h]
0x1400bdb4e  mov     rsi, [r11+40h]
0x1400bdb52  mov     rsp, r11
0x1400bdb55  pop     r15
0x1400bdb57  pop     r14
0x1400bdb59  pop     r12
0x1400bdb5b  pop     rdi
0x1400bdb5c  pop     rbp
0x1400bdb5d  retn
0x1400bdb5f  mov     rax, [rdi]
0x1400bdb62  mov     rcx, rdi
0x1400bdb65  mov     rax, [rax+8]
0x1400bdb69  call    _guard_dispatch_icall
0x1400bdb6e  cmp     eax, 2
0x1400bdb71  jz      short loc_1400BDB8A
0x1400bdb73  lea     r8, [rdi+0E8h]; struct DirectComposition::CEvent **
0x1400bdb7a  mov     edx, 1; int
0x1400bdb7f  call    ?Create@CEvent@DirectComposition@@SAJW4_EVENT_TYPE@@HPEAPEAV12@@Z; DirectComposition::CEvent::Create(_EVENT_TYPE,int,DirectComposition::CEvent * *)
0x1400bdb84  mov     ebx, eax
0x1400bdb86  test    eax, eax
0x1400bdb88  js      short loc_1400BDB43
0x1400bdb8a  mov     rcx, [rdi+28h]
0x1400bdb8e  mov     rcx, [rcx+10h]; Resource
0x1400bdb92  call    ?AcquireShared@CCriticalSection@DirectComposition@@QEAAXXZ; DirectComposition::CCriticalSection::AcquireShared(void)
0x1400bdb97  mov     rcx, [rdi+28h]; this
0x1400bdb9b  lea     r8, [rdi+1Ch]; unsigned int *
0x1400bdb9f  mov     rdx, rdi; struct DirectComposition::CChannel *
0x1400bdba2  call    ?RegisterChannel@CConnection@DirectComposition@@QEAAJPEAVCChannel@2@PEAI@Z; DirectComposition::CConnection::RegisterChannel(DirectComposition::CChannel *,uint *)
0x1400bdba7  mov     ebx, eax
0x1400bdba9  test    eax, eax
0x1400bdbab  js      loc_1400BDCE0
0x1400bdbb1  mov     rcx, rdi; this
0x1400bdbb4  call    ?OpenChannel@CApplicationChannel@DirectComposition@@IEAAXXZ; DirectComposition::CApplicationChannel::OpenChannel(void)
0x1400bdbb9  mov     rcx, [rdi+28h]
0x1400bdbbd  mov     rcx, [rcx+10h]; Resource
0x1400bdbc1  call    cs:__imp_ExReleaseResourceLite
0x1400bdbc8  nop     dword ptr [rax+rax+00h]
0x1400bdbcd  call    cs:__imp_KeLeaveCriticalRegion
0x1400bdbd4  nop     dword ptr [rax+rax+00h]
0x1400bdbd9  test    ebx, ebx
0x1400bdbdb  js      loc_1400BDB43
0x1400bdbe1  test    r12, r12
0x1400bdbe4  jz      short loc_1400BDBF0
0x1400bdbe6  mov     eax, [rdi+0AD0h]
0x1400bdbec  mov     [r12], eax
0x1400bdbf0  test    r15, r15
0x1400bdbf3  jz      loc_1400BDB43
0x1400bdbf9  mov     rax, [rdi+0AE0h]
0x1400bdc00  mov     [r15], rax
0x1400bdc03  jmp     loc_1400BDB43
0x1400bdc08  lea     rbx, [rdi+0A80h]
0x1400bdc0f  mov     rcx, rsi; this
0x1400bdc12  lea     r14, [rdi+0A78h]
0x1400bdc19  mov     r9, rbx; unsigned __int64 *
0x1400bdc1c  mov     r8, r14; struct DirectComposition::CBatchSharedMemoryPool **
0x1400bdc1f  call    ?StaticAllocate@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_KPEAPEAVCBatchSharedMemoryPool@2@PEA_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::StaticAllocate(unsigned __int64,DirectComposition::CBatchSharedMemoryPool * *,unsigned __int64 *)
0x1400bdc24  lea     r9, [rbx+8]; unsigned __int64 *
0x1400bdc28  mov     [rbp+arg_18], 0
0x1400bdc30  mov     ebx, 28h ; '('
0x1400bdc35  lea     r8, [rbp+arg_18]; struct DirectComposition::CBatchSharedMemoryPool **
0x1400bdc39  mov     edx, ebx; unsigned __int64
0x1400bdc3b  mov     rcx, rsi; this
0x1400bdc3e  call    ?BeginDynamicAllocation@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_KPEAPEAVCBatchSharedMemoryPool@2@PEA_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::BeginDynamicAllocation(unsigned __int64,DirectComposition::CBatchSharedMemoryPool * *,unsigned __int64 *)
0x1400bdc43  test    eax, eax
0x1400bdc45  js      short loc_1400BDC56
0x1400bdc47  mov     rcx, [rbp+arg_18]; this
0x1400bdc4b  mov     edx, ebx; unsigned __int64
0x1400bdc4d  call    ?UseSpace@CBatchSharedMemoryPool@DirectComposition@@QEAAPEAX_K@Z; DirectComposition::CBatchSharedMemoryPool::UseSpace(unsigned __int64)
0x1400bdc52  mov     byte ptr [rcx+40h], 0
0x1400bdc56  lea     rsi, [rdi+0C8h]
0x1400bdc5d  mov     rcx, rdi; this
0x1400bdc60  mov     rdx, rsi; struct DirectComposition::CBatch **
0x1400bdc63  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x1400bdc68  mov     ebx, eax
0x1400bdc6a  test    eax, eax
0x1400bdc6c  js      loc_1400BDB31
0x1400bdc72  lea     rdx, [rbp+arg_18]; struct DirectComposition::CBatch **
0x1400bdc76  mov     [rbp+arg_18], 0
0x1400bdc7e  mov     rcx, rdi; this
0x1400bdc81  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x1400bdc86  mov     ebx, eax
0x1400bdc88  test    eax, eax
0x1400bdc8a  js      loc_1400BDB31
0x1400bdc90  mov     rcx, [rsi]
0x1400bdc93  lea     rsi, [rdi+0C0h]
0x1400bdc9a  mov     rax, [rbp+arg_18]
0x1400bdc9e  mov     rdx, rsi; struct DirectComposition::CBatch **
0x1400bdca1  mov     [rcx], rax
0x1400bdca4  mov     rcx, rdi; this
0x1400bdca7  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x1400bdcac  mov     ebx, eax
0x1400bdcae  test    eax, eax
0x1400bdcb0  js      loc_1400BDB31
0x1400bdcb6  mov     rdx, [rsi]
0x1400bdcb9  mov     rcx, [rdi+0A88h]
0x1400bdcc0  mov     rax, [r14]
0x1400bdcc3  mov     [rdx+88h], rax
0x1400bdcca  mov     [rdx+90h], rcx
0x1400bdcd1  jmp     loc_1400BDB31
0x1400bdcd6  mov     ebx, 0C0000017h
0x1400bdcdb  jmp     loc_1400BDB31
0x1400bdce0  cmp     eax, 0C000020Ch
0x1400bdce5  jnz     loc_1400BDBB9
0x1400bdceb  mov     dword ptr [rdi+18h], 3
0x1400bdcf2  xor     ebx, ebx
0x1400bdcf4  jmp     loc_1400BDBB9
```
