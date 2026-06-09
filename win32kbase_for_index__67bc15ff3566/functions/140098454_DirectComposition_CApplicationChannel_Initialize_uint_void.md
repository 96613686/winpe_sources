# DirectComposition::CApplicationChannel::Initialize(uint *,void * *)

- ea: `0x140098454`
- end: `0x1400987f9`
- name: `?Initialize@CApplicationChannel@DirectComposition@@IEAAJPEAIPEAPEAX@Z`
- size: `933`
- prototype: `__int64 __fastcall(DirectComposition::CApplicationChannel *__hidden this, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400981d4`
- `0x140124da4`

## callees

- `0x1400878fc`
- `0x14008a284`
- `0x140098454`
- `0x140098800`
- `0x140098874`
- `0x140098a1c`
- `0x140098a90`
- `0x140098b10`
- `0x140098cc0`
- `0x1400991d0`
- `0x140099210`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14009849b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14009849b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400986cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400986cd`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140098489`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140098489`
- `ntoskrnl!PsProcessType` at `0x1400984bd`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400984b1`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400984b1`
- `ntoskrnl!MmMapViewOfSection` at `0x1400985dd`
- `ntoskrnl!MmMapViewOfSection` at `0x1400985dd`
- `ntoskrnl!MmCreateSection` at `0x140098555`
- `ntoskrnl!MmCreateSection` at `0x140098555`
- `ntoskrnl!MmMapViewInSessionSpace` at `0x140098579`
- `ntoskrnl!MmMapViewInSessionSpace` at `0x140098579`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x1400984dd`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x1400984dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400986c1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400986c1`

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
0x140098454  mov     [rsp-28h+arg_8], rbx
0x140098459  mov     [rsp-28h+arg_10], rsi
0x14009845e  push    rbp
0x14009845f  push    rdi
0x140098460  push    r12
0x140098462  push    r14
0x140098464  push    r15
0x140098466  mov     rbp, rsp
0x140098469  sub     rsp, 50h
0x14009846d  mov     r15, r8
0x140098470  mov     r12, rdx
0x140098473  mov     rdi, rcx
0x140098476  call    ?Initialize@CChannel@DirectComposition@@MEAAJXZ; DirectComposition::CChannel::Initialize(void)
0x14009847b  mov     [rbp+ViewSize], 0
0x140098483  mov     ebx, eax
0x140098485  test    eax, eax
0x140098487  js      short loc_1400984EB
0x140098489  call    cs:__imp_PsGetCurrentProcessId
0x140098490  nop     dword ptr [rax+rax+00h]
0x140098495  mov     [rdi+0AC0h], eax
0x14009849b  call    cs:__imp_PsGetCurrentProcess
0x1400984a2  nop     dword ptr [rax+rax+00h]
0x1400984a7  mov     rcx, rax
0x1400984aa  mov     [rdi+0AA8h], rax
0x1400984b1  call    cs:__imp_PsGetProcessSequenceNumber
0x1400984b8  nop     dword ptr [rax+rax+00h]
0x1400984bd  mov     r8, cs:__imp_PsProcessType
0x1400984c4  xor     r9d, r9d; AccessMode
0x1400984c7  mov     rcx, [rdi+0AA8h]; Object
0x1400984ce  mov     edx, 1FFFFFh; DesiredAccess
0x1400984d3  mov     [rdi+0AB8h], rax
0x1400984da  mov     r8, [r8]; ObjectType
0x1400984dd  call    cs:__imp_ObReferenceObjectByPointer
0x1400984e4  nop     dword ptr [rax+rax+00h]
0x1400984e9  mov     ebx, eax
0x1400984eb  mov     eax, [rdi+0AD0h]
0x1400984f1  test    eax, eax
0x1400984f3  jz      loc_1400985EB
0x1400984f9  test    ebx, ebx
0x1400984fb  js      loc_140098631
0x140098501  add     eax, 0FFFh
0x140098506  and     eax, 0FFFFF000h
0x14009850b  mov     [rdi+0AD0h], eax
0x140098511  jz      loc_1400987D6
0x140098517  mov     [rsp+50h+var_18], 0
0x140098520  lea     rsi, [rdi+0AC8h]
0x140098527  mov     r14d, 4
0x14009852d  mov     [rsp+50h+var_20], 0
0x140098536  mov     dword ptr [rsp+50h+var_28], 8400000h
0x14009853e  lea     r9, [rbp+arg_18]
0x140098542  xor     r8d, r8d
0x140098545  mov     [rbp+arg_18], rax
0x140098549  mov     rcx, rsi
0x14009854c  mov     dword ptr [rsp+50h+var_30], r14d
0x140098551  lea     edx, [r14+2]
0x140098555  call    cs:__imp_MmCreateSection
0x14009855c  nop     dword ptr [rax+rax+00h]
0x140098561  mov     ebx, eax
0x140098563  test    eax, eax
0x140098565  js      loc_140098614
0x14009856b  mov     rcx, [rsi]; Section
0x14009856e  lea     rdx, [rdi+0AD8h]; MappedBase
0x140098575  lea     r8, [rbp+ViewSize]; ViewSize
0x140098579  call    cs:__imp_MmMapViewInSessionSpace
0x140098580  nop     dword ptr [rax+rax+00h]
0x140098585  mov     ebx, eax
0x140098587  test    eax, eax
0x140098589  js      loc_140098614
0x14009858f  mov     eax, [rdi+0AD0h]
0x140098595  lea     rcx, [rbp+ViewSize]
0x140098599  mov     rdx, [rdi+0AA8h]
0x1400985a0  lea     r8, [rdi+0AE0h]
0x1400985a7  mov     [rsp+50h+var_8], r14d
0x1400985ac  xor     r9d, r9d
0x1400985af  mov     [rsp+50h+var_10], 400000h
0x1400985b7  mov     dword ptr [rsp+50h+var_18], 2
0x1400985bf  mov     [rsp+50h+var_20], rcx
0x1400985c4  lea     rcx, [rbp+arg_18]
0x1400985c8  mov     [rsp+50h+var_28], rcx
0x1400985cd  mov     rcx, [rsi]
0x1400985d0  mov     [rbp+arg_18], 0
0x1400985d8  mov     [rsp+50h+var_30], rax
0x1400985dd  call    cs:__imp_MmMapViewOfSection
0x1400985e4  nop     dword ptr [rax+rax+00h]
0x1400985e9  mov     ebx, eax
0x1400985eb  test    ebx, ebx
0x1400985ed  js      short loc_140098631
0x1400985ef  mov     rax, [rdi]
0x1400985f2  mov     rcx, rdi
0x1400985f5  mov     rax, [rax+8]
0x1400985f9  call    _guard_dispatch_icall
0x1400985fe  xor     edx, edx
0x140098600  lea     r8, [rdi+0F0h]; struct DirectComposition::CEvent **
0x140098607  cmp     eax, 2
0x14009860a  setnz   dl; int
0x14009860d  call    ?Create@CEvent@DirectComposition@@SAJW4_EVENT_TYPE@@HPEAPEAV12@@Z; DirectComposition::CEvent::Create(_EVENT_TYPE,int,DirectComposition::CEvent * *)
0x140098612  mov     ebx, eax
0x140098614  test    ebx, ebx
0x140098616  js      short loc_140098631
0x140098618  lea     rsi, [rdi+0A58h]
0x14009861f  mov     rcx, rsi; this
0x140098622  call    ?ReservePools@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::ReservePools(unsigned __int64)
0x140098627  mov     ebx, eax
0x140098629  test    eax, eax
0x14009862b  jns     loc_140098708
0x140098631  and     byte ptr [rdi+109h], 0EFh
0x140098638  mov     byte ptr [rdi+10Bh], 0
0x14009863f  test    ebx, ebx
0x140098641  jns     short loc_14009865F
0x140098643  lea     r11, [rsp+50h+var_s0]
0x140098648  mov     eax, ebx
0x14009864a  mov     rbx, [r11+38h]
0x14009864e  mov     rsi, [r11+40h]
0x140098652  mov     rsp, r11
0x140098655  pop     r15
0x140098657  pop     r14
0x140098659  pop     r12
0x14009865b  pop     rdi
0x14009865c  pop     rbp
0x14009865d  retn
0x14009865f  mov     rax, [rdi]
0x140098662  mov     rcx, rdi
0x140098665  mov     rax, [rax+8]
0x140098669  call    _guard_dispatch_icall
0x14009866e  cmp     eax, 2
0x140098671  jz      short loc_14009868A
0x140098673  lea     r8, [rdi+0E8h]; struct DirectComposition::CEvent **
0x14009867a  mov     edx, 1; int
0x14009867f  call    ?Create@CEvent@DirectComposition@@SAJW4_EVENT_TYPE@@HPEAPEAV12@@Z; DirectComposition::CEvent::Create(_EVENT_TYPE,int,DirectComposition::CEvent * *)
0x140098684  mov     ebx, eax
0x140098686  test    eax, eax
0x140098688  js      short loc_140098643
0x14009868a  mov     rcx, [rdi+28h]
0x14009868e  mov     rcx, [rcx+10h]; Resource
0x140098692  call    ?AcquireShared@CCriticalSection@DirectComposition@@QEAAXXZ; DirectComposition::CCriticalSection::AcquireShared(void)
0x140098697  mov     rcx, [rdi+28h]; this
0x14009869b  lea     r8, [rdi+1Ch]; unsigned int *
0x14009869f  mov     rdx, rdi; struct DirectComposition::CChannel *
0x1400986a2  call    ?RegisterChannel@CConnection@DirectComposition@@QEAAJPEAVCChannel@2@PEAI@Z; DirectComposition::CConnection::RegisterChannel(DirectComposition::CChannel *,uint *)
0x1400986a7  mov     ebx, eax
0x1400986a9  test    eax, eax
0x1400986ab  js      loc_1400987E0
0x1400986b1  mov     rcx, rdi; this
0x1400986b4  call    ?OpenChannel@CApplicationChannel@DirectComposition@@IEAAXXZ; DirectComposition::CApplicationChannel::OpenChannel(void)
0x1400986b9  mov     rcx, [rdi+28h]
0x1400986bd  mov     rcx, [rcx+10h]; Resource
0x1400986c1  call    cs:__imp_ExReleaseResourceLite
0x1400986c8  nop     dword ptr [rax+rax+00h]
0x1400986cd  call    cs:__imp_KeLeaveCriticalRegion
0x1400986d4  nop     dword ptr [rax+rax+00h]
0x1400986d9  test    ebx, ebx
0x1400986db  js      loc_140098643
0x1400986e1  test    r12, r12
0x1400986e4  jz      short loc_1400986F0
0x1400986e6  mov     eax, [rdi+0AD0h]
0x1400986ec  mov     [r12], eax
0x1400986f0  test    r15, r15
0x1400986f3  jz      loc_140098643
0x1400986f9  mov     rax, [rdi+0AE0h]
0x140098700  mov     [r15], rax
0x140098703  jmp     loc_140098643
0x140098708  lea     rbx, [rdi+0A80h]
0x14009870f  mov     rcx, rsi; this
0x140098712  lea     r14, [rdi+0A78h]
0x140098719  mov     r9, rbx; unsigned __int64 *
0x14009871c  mov     r8, r14; struct DirectComposition::CBatchSharedMemoryPool **
0x14009871f  call    ?StaticAllocate@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_KPEAPEAVCBatchSharedMemoryPool@2@PEA_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::StaticAllocate(unsigned __int64,DirectComposition::CBatchSharedMemoryPool * *,unsigned __int64 *)
0x140098724  lea     r9, [rbx+8]; unsigned __int64 *
0x140098728  mov     [rbp+arg_18], 0
0x140098730  mov     ebx, 28h ; '('
0x140098735  lea     r8, [rbp+arg_18]; struct DirectComposition::CBatchSharedMemoryPool **
0x140098739  mov     edx, ebx; unsigned __int64
0x14009873b  mov     rcx, rsi; this
0x14009873e  call    ?BeginDynamicAllocation@CBatchSharedMemoryPoolSet@DirectComposition@@QEAAJ_KPEAPEAVCBatchSharedMemoryPool@2@PEA_K@Z; DirectComposition::CBatchSharedMemoryPoolSet::BeginDynamicAllocation(unsigned __int64,DirectComposition::CBatchSharedMemoryPool * *,unsigned __int64 *)
0x140098743  test    eax, eax
0x140098745  js      short loc_140098756
0x140098747  mov     rcx, [rbp+arg_18]; this
0x14009874b  mov     edx, ebx; unsigned __int64
0x14009874d  call    ?UseSpace@CBatchSharedMemoryPool@DirectComposition@@QEAAPEAX_K@Z; DirectComposition::CBatchSharedMemoryPool::UseSpace(unsigned __int64)
0x140098752  mov     byte ptr [rcx+40h], 0
0x140098756  lea     rsi, [rdi+0C8h]
0x14009875d  mov     rcx, rdi; this
0x140098760  mov     rdx, rsi; struct DirectComposition::CBatch **
0x140098763  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x140098768  mov     ebx, eax
0x14009876a  test    eax, eax
0x14009876c  js      loc_140098631
0x140098772  lea     rdx, [rbp+arg_18]; struct DirectComposition::CBatch **
0x140098776  mov     [rbp+arg_18], 0
0x14009877e  mov     rcx, rdi; this
0x140098781  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x140098786  mov     ebx, eax
0x140098788  test    eax, eax
0x14009878a  js      loc_140098631
0x140098790  mov     rcx, [rsi]
0x140098793  lea     rsi, [rdi+0C0h]
0x14009879a  mov     rax, [rbp+arg_18]
0x14009879e  mov     rdx, rsi; struct DirectComposition::CBatch **
0x1400987a1  mov     [rcx], rax
0x1400987a4  mov     rcx, rdi; this
0x1400987a7  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x1400987ac  mov     ebx, eax
0x1400987ae  test    eax, eax
0x1400987b0  js      loc_140098631
0x1400987b6  mov     rdx, [rsi]
0x1400987b9  mov     rcx, [rdi+0A88h]
0x1400987c0  mov     rax, [r14]
0x1400987c3  mov     [rdx+88h], rax
0x1400987ca  mov     [rdx+90h], rcx
0x1400987d1  jmp     loc_140098631
0x1400987d6  mov     ebx, 0C0000017h
0x1400987db  jmp     loc_140098631
0x1400987e0  cmp     eax, 0C000020Ch
0x1400987e5  jnz     loc_1400986B9
0x1400987eb  mov     dword ptr [rdi+18h], 3
0x1400987f2  xor     ebx, ebx
0x1400987f4  jmp     loc_1400986B9
```
