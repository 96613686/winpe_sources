# TpmScheduler::Run(void *)

- ea: `0x1400110f0`
- end: `0x14001154e`
- name: `?Run@TpmScheduler@@CAXPEAX@Z`
- size: `1118`
- prototype: `void __fastcall(TpmScheduler *this)`
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x140006838`
- `0x14000a4f0`
- `0x140010420`
- `0x1400110f0`
- `0x140011554`
- `0x1400116fc`
- `0x1400120d0`
- `0x14001240c`
- `0x140012568`
- `0x140013ab4`
- `0x14001982c`
- `0x140019874`
- `0x1400199e4`
- `0x140019a94`
- `0x14001a49c`
- `0x14001a8d4`
- `0x1400211dc`
- `0x140039740`
- `0x1400454cc`
- `0x1400454f0`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400112a0`
- `ntoskrnl!KeClearEvent` at `0x1400112a0`
- `ntoskrnl!KeReadStateEvent` at `0x14001121e`
- `ntoskrnl!KeReadStateEvent` at `0x14001121e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400112e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400112e6`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140011152`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400111a8`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140011152`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400111a8`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001120b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14001120b`
- `ntoskrnl!PsTerminateSystemThread` at `0x140011402`
- `ntoskrnl!PsTerminateSystemThread` at `0x140011402`
- `ntoskrnl!KeSetEvent` at `0x1400112bf`
- `ntoskrnl!KeSetEvent` at `0x1400112bf`
- `cng!EntropyUnregisterSource` at `0x140011536`
- `cng!EntropyUnregisterSource` at `0x140011536`

## pseudocode

```c
void __fastcall TpmScheduler::Run(TpmScheduler *this)
{
  PRKEVENT *v1; // rbp
  __int64 v3; // rdi
  __int64 v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rbx
  unsigned int v7; // eax
  union _LARGE_INTEGER *Timeout; // rcx
  NTSTATUS v9; // r13d
  struct TpmRequest *NextRequest; // rax
  PRKEVENT v11; // rcx
  _QWORD *v12; // rbp
  _QWORD *i; // r14
  unsigned int *v14; // r8
  unsigned int *v15; // r8
  unsigned int *v16; // r8
  unsigned __int64 v17; // rcx
  struct _ENTROPY_SOURCE_STATE *v18; // rcx
  int v19; // eax
  KPROCESSOR_MODE WaitMode[8]; // [rsp+20h] [rbp-B8h]
  __int64 Alertable; // [rsp+28h] [rbp-B0h]
  PRKEVENT *v22; // [rsp+40h] [rbp-98h]
  __int64 v23; // [rsp+48h] [rbp-90h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v25; // [rsp+70h] [rbp-68h] BYREF
  __int64 v26; // [rsp+78h] [rbp-60h]
  unsigned int v27; // [rsp+80h] [rbp-58h]

  v1 = *(PRKEVENT **)this;
  Object[0] = *((PVOID *)this + 11);
  v22 = v1;
  Object[1] = v1[5];
  TpmCore::SelfTest((TpmCore *)v1, 1);
  v3 = MEMORY[0xFFFFF78000000320];
  v4 = KeQueryTimeIncrement() * v3;
  TpmScheduler::ReportTpmStateOnStartup(this);
  *((_DWORD *)this + 10) = (TpmScheduler::UefiPcr5Fixup(this) & 0xC0000000) == -1073741824;
  TpmFreshOsBoot();
  *((_DWORD *)this + 8) = 1;
  *((_DWORD *)this + 9) = 20;
  while ( 1 )
  {
    v5 = 1;
    if ( v4 != 1 )
    {
      v6 = MEMORY[0xFFFFF78000000320];
      v5 = v4 - v6 * KeQueryTimeIncrement();
      if ( v5 < 0 )
        v5 = 0;
    }
    v7 = *((_DWORD *)this + 9);
    if ( v7 > 1 && (v5 == 1 || v5 > 5000000) )
    {
      v5 = 5000000;
      *((_DWORD *)this + 9) = v7 - 1;
    }
    Timeout = (union _LARGE_INTEGER *)&v23;
    v23 = -v5;
    if ( v5 == 1 )
      Timeout = 0;
    v9 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, Timeout, 0);
    if ( KeReadStateEvent(v1[5]) )
      break;
LABEL_9:
    if ( !v5 || v9 == 258 )
      v4 = *(_QWORD *)TpmScheduler::ProvideEntropy(this).QuadPart;
    if ( *((_DWORD *)this + 10) )
      *((_DWORD *)this + 10) = (TpmScheduler::UefiPcr5Fixup(this) & 0xC0000000) == -1073741824;
    if ( *((_DWORD *)this + 8) )
    {
      *((_DWORD *)this + 8) = 0;
      TpmScheduler::PerformTrustpoints(this);
    }
    if ( *((_DWORD *)this + 9) )
    {
      v19 = TpmArchiveLog();
      if ( v19 != -1073741772 && v19 != -1073741766 )
        *((_DWORD *)this + 9) = 0;
    }
    NextRequest = TpmScheduler::GetNextRequest(this);
    if ( NextRequest )
      TpmScheduler::Execute(this, 0, NextRequest);
  }
  v11 = v1[6];
  if ( v11 )
    TpmTransport::SetCancelState(v11, 0);
  KeClearEvent(v1[5]);
  if ( *((_DWORD *)this + 7) )
  {
    TpmCore::PcrRead((TpmCore *)v1, 0xCu, (unsigned __int8 *)this + 96);
    TpmCore::Execute((TpmCore *)v1, 0x98u, 0);
  }
  KeSetEvent(*((PRKEVENT *)this + 6), 0, 0);
  if ( !*((_DWORD *)this + 6) )
  {
    KeWaitForSingleObject(*((PVOID *)this + 7), Executive, 0, 0, 0);
    TpmCore::SelfTest((TpmCore *)v1, 0);
    TpmScheduler::ProvideEntropy(this);
    if ( !*(_DWORD *)(*((_QWORD *)this + 1) + 808LL) )
    {
      v12 = (_QWORD *)*((_QWORD *)this + 2);
      GuardedMutex::Acquire((GuardedMutex *)(v12 + 147));
      for ( i = (_QWORD *)v12[148]; i != v12 + 148; i = (_QWORD *)*i )
        TpmResourceManager::ReclaimResources((TpmResourceManager *)(v12 + 9), (struct TpmContext *)(i - 2), 1u, 0);
      GuardedMutex::Release((GuardedMutex *)(v12 + 147));
      TpmDevice::SyncResources(*((TpmDevice **)this + 2), 1u, v14);
      TpmDevice::SyncResources(*((TpmDevice **)this + 2), 2u, v15);
      TpmDevice::SyncResources(*((TpmDevice **)this + 2), 5u, v16);
      LODWORD(Alertable) = 20;
      *(_DWORD *)WaitMode = 12;
      TpmCore::Execute(
        *(TpmCore **)this,
        (bool (*)(int))TpmCore::IsTpmDisabledStatus,
        0x15u,
        "u32pAu8",
        *(_QWORD *)WaitMode,
        Alertable,
        &v25);
      v17 = v25 - *((_QWORD *)this + 12);
      if ( v25 == *((_QWORD *)this + 12) )
      {
        v17 = v26 - *((_QWORD *)this + 13);
        if ( v26 == *((_QWORD *)this + 13) )
          v17 = v27 - (unsigned __int64)*((unsigned int *)this + 28);
      }
      if ( v17 )
      {
        *((_DWORD *)this + 10) = (TpmScheduler::UefiPcr5Fixup(this) & 0xC0000000) == -1073741824;
        TpmResumeFromHibernation();
        *((_DWORD *)this + 8) = 1;
        *((_DWORD *)this + 9) = 20;
      }
      else
      {
        *((_DWORD *)this + 9) = 0;
      }
      v1 = v22;
    }
    goto LABEL_9;
  }
  v18 = (struct _ENTROPY_SOURCE_STATE *)*((_QWORD *)this + 27);
  if ( v18 )
  {
    EntropyUnregisterSource(v18);
    *((_QWORD *)this + 27) = 0;
  }
  *((_DWORD *)this + 20) = 0;
  PsTerminateSystemThread(v9);
}

```

## disassembly

```asm
0x1400110f0  push    rbx
0x1400110f2  push    rbp
0x1400110f3  push    rsi
0x1400110f4  push    rdi
0x1400110f5  push    r12
0x1400110f7  push    r13
0x1400110f9  push    r14
0x1400110fb  push    r15
0x1400110fd  sub     rsp, 98h
0x140011104  mov     rax, cs:__security_cookie
0x14001110b  xor     rax, rsp
0x14001110e  mov     [rsp+0D8h+var_50], rax
0x140011116  mov     rbp, [rcx]
0x140011119  mov     rsi, rcx
0x14001111c  mov     rax, [rcx+58h]
0x140011120  mov     r15d, 1
0x140011126  mov     [rsp+0D8h+Object], rax
0x14001112b  mov     dl, r15b; bool
0x14001112e  mov     rcx, rbp; this
0x140011131  mov     [rsp+0D8h+var_98], rbp
0x140011136  mov     rax, [rbp+28h]
0x14001113a  mov     [rsp+0D8h+var_80], rax
0x14001113f  call    ?SelfTest@TpmCore@@QEAAJ_N@Z; TpmCore::SelfTest(bool)
0x140011144  mov     r13, 0FFFFF78000000320h
0x14001114e  mov     rdi, [r13+0]
0x140011152  call    cs:__imp_KeQueryTimeIncrement
0x140011159  nop     dword ptr [rax+rax+00h]
0x14001115e  mov     eax, eax
0x140011160  mov     rcx, rsi; this
0x140011163  imul    rdi, rax
0x140011167  call    ?ReportTpmStateOnStartup@TpmScheduler@@AEAAJXZ; TpmScheduler::ReportTpmStateOnStartup(void)
0x14001116c  mov     rcx, rsi; struct TpmScheduler *
0x14001116f  call    ?UefiPcr5Fixup@TpmScheduler@@SAJPEAV1@@Z; TpmScheduler::UefiPcr5Fixup(TpmScheduler *)
0x140011174  xor     r14d, r14d
0x140011177  mov     r12d, 0C0000000h
0x14001117d  mov     ecx, r14d
0x140011180  and     eax, r12d
0x140011183  cmp     eax, r12d
0x140011186  setz    cl
0x140011189  mov     [rsi+28h], ecx
0x14001118c  call    TpmFreshOsBoot
0x140011191  mov     [rsi+20h], r15d
0x140011195  mov     dword ptr [rsi+24h], 14h
0x14001119c  mov     rbx, r15
0x14001119f  cmp     rdi, r15
0x1400111a2  jz      short loc_1400111C4
0x1400111a4  mov     rbx, [r13+0]
0x1400111a8  call    cs:__imp_KeQueryTimeIncrement
0x1400111af  nop     dword ptr [rax+rax+00h]
0x1400111b4  mov     eax, eax
0x1400111b6  imul    rax, rbx
0x1400111ba  mov     rbx, rdi
0x1400111bd  sub     rbx, rax
0x1400111c0  cmovs   rbx, r14
0x1400111c4  mov     eax, [rsi+24h]
0x1400111c7  cmp     eax, r15d
0x1400111ca  ja      loc_140011433
0x1400111d0  mov     [rsp+0D8h+WaitBlockArray], r14; WaitBlockArray
0x1400111d5  lea     rcx, [rsp+0D8h+var_90]
0x1400111da  mov     rdx, rbx
0x1400111dd  mov     r8d, r15d; WaitType
0x1400111e0  neg     rdx
0x1400111e3  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400111e7  mov     [rsp+0D8h+var_90], rdx
0x1400111ec  lea     rdx, [rsp+0D8h+Object]; Object
0x1400111f1  cmovz   rcx, r14
0x1400111f5  xor     r9d, r9d; WaitReason
0x1400111f8  mov     [rsp+0D8h+Timeout], rcx; Timeout
0x1400111fd  mov     [rsp+0D8h+Alertable], r14b; Alertable
0x140011202  mov     [rsp+0D8h+WaitMode], r14b; WaitMode
0x140011207  lea     ecx, [r9+2]; Count
0x14001120b  call    cs:__imp_KeWaitForMultipleObjects
0x140011212  nop     dword ptr [rax+rax+00h]
0x140011217  mov     rcx, [rbp+28h]; Event
0x14001121b  mov     r13d, eax
0x14001121e  call    cs:__imp_KeReadStateEvent
0x140011225  nop     dword ptr [rax+rax+00h]
0x14001122a  test    eax, eax
0x14001122c  jnz     short loc_14001128F
0x14001122e  test    rbx, rbx
0x140011231  jz      loc_1400114D0
0x140011237  cmp     r13d, 102h
0x14001123e  jz      loc_1400114D0
0x140011244  cmp     [rsi+28h], r14d
0x140011248  jnz     loc_1400114E5
0x14001124e  cmp     [rsi+20h], r14d
0x140011252  jnz     loc_140011501
0x140011258  cmp     [rsi+24h], r14d
0x14001125c  jnz     loc_140011512
0x140011262  mov     rcx, rsi; this
0x140011265  call    ?GetNextRequest@TpmScheduler@@AEAAPEAVTpmRequest@@XZ; TpmScheduler::GetNextRequest(void)
0x14001126a  mov     r13, 0FFFFF78000000320h
0x140011274  test    rax, rax
0x140011277  jz      loc_14001119C
0x14001127d  mov     r8, rax; struct TpmRequest *
0x140011280  xor     edx, edx; bool
0x140011282  mov     rcx, rsi; this
0x140011285  call    ?Execute@TpmScheduler@@AEAAX_NPEAVTpmRequest@@@Z; TpmScheduler::Execute(bool,TpmRequest *)
0x14001128a  jmp     loc_14001119C
0x14001128f  mov     rcx, [rbp+30h]
0x140011293  test    rcx, rcx
0x140011296  jnz     loc_140011454
0x14001129c  mov     rcx, [rbp+28h]; Event
0x1400112a0  call    cs:__imp_KeClearEvent
0x1400112a7  nop     dword ptr [rax+rax+00h]
0x1400112ac  cmp     [rsi+1Ch], r14d
0x1400112b0  jnz     loc_140011460
0x1400112b6  mov     rcx, [rsi+30h]; Event
0x1400112ba  xor     r8d, r8d; Wait
0x1400112bd  xor     edx, edx; Increment
0x1400112bf  call    cs:__imp_KeSetEvent
0x1400112c6  nop     dword ptr [rax+rax+00h]
0x1400112cb  cmp     [rsi+18h], r14d
0x1400112cf  jnz     loc_1400113EB
0x1400112d5  mov     rcx, [rsi+38h]; Object
0x1400112d9  xor     r9d, r9d; Alertable
0x1400112dc  xor     r8d, r8d; WaitMode
0x1400112df  mov     qword ptr [rsp+0D8h+WaitMode], r14; Timeout
0x1400112e4  xor     edx, edx; WaitReason
0x1400112e6  call    cs:__imp_KeWaitForSingleObject
0x1400112ed  nop     dword ptr [rax+rax+00h]
0x1400112f2  xor     edx, edx; bool
0x1400112f4  mov     rcx, rbp; this
0x1400112f7  call    ?SelfTest@TpmCore@@QEAAJ_N@Z; TpmCore::SelfTest(bool)
0x1400112fc  lea     rdx, [rsp+0D8h+var_78]
0x140011301  mov     rcx, rsi; this
0x140011304  call    ?ProvideEntropy@TpmScheduler@@AEAA?AT_LARGE_INTEGER@@XZ; TpmScheduler::ProvideEntropy(void)
0x140011309  mov     rax, [rsi+8]
0x14001130d  cmp     [rax+328h], r14d
0x140011314  jnz     loc_14001122E
0x14001131a  mov     rbp, [rsi+10h]
0x14001131e  lea     r12, [rbp+498h]
0x140011325  mov     rcx, r12; this
0x140011328  call    ?Acquire@GuardedMutex@@QEAAXXZ; GuardedMutex::Acquire(void)
0x14001132d  lea     r15, [rbp+4A0h]
0x140011334  mov     r14, [r15]
0x140011337  cmp     r14, r15
0x14001133a  jnz     loc_140011486
0x140011340  mov     rcx, r12; this
0x140011343  call    ?Release@GuardedMutex@@QEAAXXZ; GuardedMutex::Release(void)
0x140011348  mov     rcx, [rsi+10h]; this
0x14001134c  mov     r15d, 1
0x140011352  mov     edx, r15d; unsigned int
0x140011355  call    ?SyncResources@TpmDevice@@QEAAJIPEAI@Z; TpmDevice::SyncResources(uint,uint *)
0x14001135a  mov     rcx, [rsi+10h]; this
0x14001135e  lea     edx, [r15+1]; unsigned int
0x140011362  call    ?SyncResources@TpmDevice@@QEAAJIPEAI@Z; TpmDevice::SyncResources(uint,uint *)
0x140011367  mov     rcx, [rsi+10h]; this
0x14001136b  lea     edx, [r15+4]; unsigned int
0x14001136f  call    ?SyncResources@TpmDevice@@QEAAJIPEAI@Z; TpmDevice::SyncResources(uint,uint *)
0x140011374  mov     rcx, [rsi]; this
0x140011377  lea     rax, [rsp+0D8h+var_68]
0x14001137c  mov     [rsp+0D8h+Timeout], rax
0x140011381  lea     ebp, [r15+13h]
0x140011385  mov     dword ptr [rsp+0D8h+Alertable], ebp
0x140011389  lea     r9, aU32pau8; "u32pAu8"
0x140011390  lea     r8d, [r15+14h]; unsigned int
0x140011394  mov     dword ptr [rsp+0D8h+WaitMode], 0Ch
0x14001139c  lea     rdx, ?IsTpmDisabledStatus@TpmCore@@SA_NJ@Z; bool (*)(int)
0x1400113a3  call    ?Execute@TpmCore@@QEAAJP6A_NJ@ZIPEBDZZ; TpmCore::Execute(bool (*)(long),uint,char const *,...)
0x1400113a8  mov     rcx, [rsp+0D8h+var_68]
0x1400113ad  sub     rcx, [rsi+60h]
0x1400113b1  jnz     short loc_1400113CB
0x1400113b3  mov     rcx, [rsp+0D8h+var_60]
0x1400113b8  sub     rcx, [rsi+68h]
0x1400113bc  jnz     short loc_1400113CB
0x1400113be  mov     ecx, [rsp+0D8h+var_58]
0x1400113c5  mov     eax, [rsi+70h]
0x1400113c8  sub     rcx, rax
0x1400113cb  xor     r14d, r14d
0x1400113ce  test    rcx, rcx
0x1400113d1  jnz     loc_1400114A2
0x1400113d7  mov     [rsi+24h], r14d
0x1400113db  mov     r12d, 0C0000000h
0x1400113e1  mov     rbp, [rsp+0D8h+var_98]
0x1400113e6  jmp     loc_14001122E
0x1400113eb  mov     rcx, [rsi+0D8h]; hEntropySource
0x1400113f2  test    rcx, rcx
0x1400113f5  jnz     loc_140011536
0x1400113fb  mov     ecx, r13d; ExitStatus
0x1400113fe  mov     [rsi+50h], r14d
0x140011402  call    cs:__imp_PsTerminateSystemThread
0x140011409  nop     dword ptr [rax+rax+00h]
0x14001140e  mov     rcx, [rsp+0D8h+var_50]
0x140011416  xor     rcx, rsp; StackCookie
0x140011419  call    __security_check_cookie
0x14001141e  add     rsp, 98h
0x140011425  pop     r15
0x140011427  pop     r14
0x140011429  pop     r13
0x14001142b  pop     r12
0x14001142d  pop     rdi
0x14001142e  pop     rsi
0x14001142f  pop     rbp
0x140011430  pop     rbx
0x140011431  retn
0x140011433  cmp     rbx, r15
0x140011436  jz      short loc_140011445
0x140011438  cmp     rbx, 4C4B40h
0x14001143f  jle     loc_1400111D0
0x140011445  dec     eax
0x140011447  mov     ebx, 4C4B40h
0x14001144c  mov     [rsi+24h], eax
0x14001144f  jmp     loc_1400111D0
0x140011454  xor     edx, edx
0x140011456  call    ?SetCancelState@TpmTransport@@QEAAXW4TPM_TRANSPORT_CANCEL_STATE@1@@Z; TpmTransport::SetCancelState(TpmTransport::TPM_TRANSPORT_CANCEL_STATE)
0x14001145b  jmp     loc_14001129C
0x140011460  lea     r8, [rsi+60h]; unsigned __int8 *
0x140011464  mov     edx, 0Ch; unsigned int
0x140011469  mov     rcx, rbp; this
0x14001146c  call    ?PcrRead@TpmCore@@QEAAJIPEAE@Z; TpmCore::PcrRead(uint,uchar *)
0x140011471  xor     r8d, r8d; char *
0x140011474  mov     edx, 98h; unsigned int
0x140011479  mov     rcx, rbp; this
0x14001147c  call    ?Execute@TpmCore@@QEAAJIPEBDZZ; TpmCore::Execute(uint,char const *,...)
0x140011481  jmp     loc_1400112B6
0x140011486  xor     r9d, r9d; bool
0x140011489  lea     rdx, [r14-10h]; struct TpmContext *
0x14001148d  lea     rcx, [rbp+48h]; this
0x140011491  lea     r8d, [r9+1]; unsigned int
0x140011495  call    ?ReclaimResources@TpmResourceManager@@QEAAXPEAVTpmContext@@I_N@Z; TpmResourceManager::ReclaimResources(TpmContext *,uint,bool)
0x14001149a  mov     r14, [r14]
0x14001149d  jmp     loc_140011337
0x1400114a2  mov     rcx, rsi; struct TpmScheduler *
0x1400114a5  call    ?UefiPcr5Fixup@TpmScheduler@@SAJPEAV1@@Z; TpmScheduler::UefiPcr5Fixup(TpmScheduler *)
0x1400114aa  mov     ecx, r14d
0x1400114ad  mov     r12d, 0C0000000h
0x1400114b3  and     eax, r12d
0x1400114b6  cmp     eax, r12d
0x1400114b9  setz    cl
0x1400114bc  mov     [rsi+28h], ecx
0x1400114bf  call    TpmResumeFromHibernation
0x1400114c4  mov     [rsi+20h], r15d
0x1400114c8  mov     [rsi+24h], ebp
0x1400114cb  jmp     loc_1400113E1
0x1400114d0  lea     rdx, [rsp+0D8h+var_70]
0x1400114d5  mov     rcx, rsi; this
0x1400114d8  call    ?ProvideEntropy@TpmScheduler@@AEAA?AT_LARGE_INTEGER@@XZ; TpmScheduler::ProvideEntropy(void)
0x1400114dd  mov     rdi, [rax]
0x1400114e0  jmp     loc_140011244
0x1400114e5  mov     rcx, rsi; struct TpmScheduler *
0x1400114e8  call    ?UefiPcr5Fixup@TpmScheduler@@SAJPEAV1@@Z; TpmScheduler::UefiPcr5Fixup(TpmScheduler *)
0x1400114ed  mov     ecx, r14d
0x1400114f0  and     eax, r12d
0x1400114f3  cmp     eax, r12d
0x1400114f6  setz    cl
0x1400114f9  mov     [rsi+28h], ecx
0x1400114fc  jmp     loc_14001124E
0x140011501  mov     rcx, rsi; this
0x140011504  mov     [rsi+20h], r14d
0x140011508  call    ?PerformTrustpoints@TpmScheduler@@QEAAJXZ; TpmScheduler::PerformTrustpoints(void)
0x14001150d  jmp     loc_140011258
0x140011512  call    TpmArchiveLog
0x140011517  cmp     eax, 0C0000034h
0x14001151c  jz      loc_140011262
0x140011522  cmp     eax, 0C000003Ah
0x140011527  jz      loc_140011262
0x14001152d  mov     [rsi+24h], r14d
0x140011531  jmp     loc_140011262
0x140011536  call    cs:__imp_EntropyUnregisterSource
0x14001153d  nop     dword ptr [rax+rax+00h]
0x140011542  mov     [rsi+0D8h], r14
0x140011549  jmp     loc_1400113FB
```
