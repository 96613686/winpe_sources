# VMX_PACK::CommitChangeIdentityTransaction(void)

- ea: `0x14004e3ac`
- end: `0x14004e947`
- name: `?CommitChangeIdentityTransaction@VMX_PACK@@QEAAJXZ`
- size: `1435`
- prototype: `__int64 __fastcall(VMX_PACK *__hidden this)`
- caller_count: `4`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002b13c`
- `0x14002b964`
- `0x14002c3dc`
- `0x14002caf8`

## callees

- `0x140007600`
- `0x140007b08`
- `0x1400099d8`
- `0x14002a920`
- `0x14002ab44`
- `0x14002ac1c`
- `0x14002b0c4`
- `0x14003d81c`
- `0x14003e0ec`
- `0x140043340`
- `0x140048b84`
- `0x14004a5dc`
- `0x14004a6b0`
- `0x14004af34`
- `0x14004b010`
- `0x14004b0e4`
- `0x14004dbfc`
- `0x14004e3ac`
- `0x140053b8c`
- `0x140054328`
- `0x140054b2c`
- `0x140055878`
- `0x14005818c`
- `0x140058518`
- `0x140058660`
- `0x14005890c`
- `0x140059528`
- `0x140059724`
- `0x14005b3fc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004e52a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e5af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e650`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e808`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e8c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e52a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e5af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e650`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e808`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e8c5`

## pseudocode

```c
__int64 __fastcall VMX_PACK::CommitChangeIdentityTransaction(VMX_PACK *this)
{
  __int64 v1; // rax
  __int64 v2; // rsi
  __int64 v4; // r14
  int updated; // ebx
  VMX_NOTIFICATION_QUEUE *v6; // r10
  __int64 v7; // rdx
  unsigned int v8; // r8d
  int v9; // ecx
  unsigned int i; // edx
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // r12
  struct VMX_CONFIG_COPY *v14; // rdx
  unsigned int j; // ebx
  __int64 v16; // r12
  VMX_PHYSICAL_DISK *v17; // r13
  int v18; // eax
  VMX_LOG *v19; // rcx
  struct VMX_CHANGE_IDENTITY_TRANSACTION *v20; // r15
  VMX_LOG *v21; // rbx
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // edx
  unsigned int v26; // [rsp+60h] [rbp+40h] BYREF
  PVOID P; // [rsp+68h] [rbp+48h] BYREF

  v1 = *((_QWORD *)this + 2);
  v2 = *((_QWORD *)this + 6);
  v26 = 0;
  P = 0;
  v4 = *(_QWORD *)(v1 + 8);
  *(_QWORD *)(v2 + 40) = MEMORY[0xFFFFF78000000014];
  updated = VMX_CHANGE_IDENTITY_TRANSACTION::AtomicUpdateHeadersPhase0((VMX_CHANGE_IDENTITY_TRANSACTION *)v2);
  if ( updated < 0 )
  {
    VMX_CONFIG::AbortRecords(*((VMX_CONFIG **)this + 2));
    *((_QWORD *)this + 6) = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)updated;
    }
    v7 = 35;
LABEL_77:
    WPP_SF_d(*((_QWORD *)v6 + 3), v7, WPP_b525482092043ba595507d12d78e6f73_Traceguids, (unsigned int)updated);
    return (unsigned int)updated;
  }
  updated = VMX_PACK::PreCommitLog(this);
  if ( updated < 0 )
  {
    VMX_CONFIG::AbortRecords(*((VMX_CONFIG **)this + 2));
    *((_QWORD *)this + 6) = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)updated;
    }
    v7 = 36;
    goto LABEL_77;
  }
  *(_OWORD *)(v4 + 8) = *(_OWORD *)(v2 + 112);
  updated = VMX_PACK::PreCommitDevices(this, &v26, (struct _VM_DEVICE_CHANGE **)&P);
  *(_OWORD *)(v4 + 8) = *(_OWORD *)(v2 + 64);
  if ( updated < 0 )
  {
    VMX_PACK::AbortLog((VMX_LOG **)this);
    VMX_CONFIG::AbortRecords(*((VMX_CONFIG **)this + 2));
    *((_QWORD *)this + 6) = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)updated;
    }
    v7 = 37;
    goto LABEL_77;
  }
  updated = VMX_RAW_CONFIG::PrepareForUpdate((VMX_RAW_CONFIG *)v4);
  if ( updated < 0 )
  {
    if ( v26 )
    {
      ExFreePoolWithTag(P, 0);
      VMX_PACK::AbortDevices(this);
    }
    VMX_PACK::AbortLog((VMX_LOG **)this);
    VMX_CONFIG::AbortRecords(*((VMX_CONFIG **)this + 2));
    *((_QWORD *)this + 6) = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)updated;
    }
    v7 = 38;
    goto LABEL_77;
  }
  updated = VMX_CHANGE_IDENTITY_TRANSACTION::AtomicUpdateHeadersPhase1((VMX_CHANGE_IDENTITY_TRANSACTION *)v2);
  if ( updated < 0 )
  {
    VMX_RAW_CONFIG::CleanAfterUpdate((VMX_RAW_CONFIG *)v4);
    if ( v26 )
    {
      ExFreePoolWithTag(P, 0);
      VMX_PACK::AbortDevices(this);
    }
    VMX_PACK::AbortLog((VMX_LOG **)this);
    VMX_CONFIG::AbortRecords(*((VMX_CONFIG **)this + 2));
    *((_QWORD *)this + 6) = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)updated;
    }
    v7 = 39;
    goto LABEL_77;
  }
  updated = VMX_RAW_CONFIG::AtomicUpdatePhase1((VMX_RAW_CONFIG *)v4, (struct VMX_TRANSACTION *)v2);
  VMX_PACK::UpdateCounters(this);
  if ( updated < 0 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::AtomicUpdateHeadersRevertPhase1((VMX_CHANGE_IDENTITY_TRANSACTION *)v2);
    VMX_CHANGE_IDENTITY_TRANSACTION::CheckFailedIo((VMX_CHANGE_IDENTITY_TRANSACTION *)v2);
    VMX_RAW_CONFIG::CleanAfterUpdate((VMX_RAW_CONFIG *)v4);
    if ( v26 )
    {
      ExFreePoolWithTag(P, 0);
      VMX_PACK::AbortDevices(this);
    }
    VMX_PACK::AbortLog((VMX_LOG **)this);
    VMX_CONFIG::AbortRecords(*((VMX_CONFIG **)this + 2));
    *((_QWORD *)this + 6) = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)updated;
    }
    v7 = 40;
    goto LABEL_77;
  }
  v8 = *(_DWORD *)(v2 + 160);
  if ( !v8 )
    goto LABEL_71;
  v9 = 0;
  for ( i = 0; i < v8; ++i )
  {
    v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 168) + 48LL * i + 32) + 104LL);
    if ( v11 && *(_BYTE *)(v11 + 19) )
      ++v9;
  }
  if ( !v9 )
  {
LABEL_71:
    VMX_RAW_CONFIG::AtomicUpdateRevertPhase1((VMX_RAW_CONFIG *)v4, (struct VMX_TRANSACTION *)v2);
    VMX_CHANGE_IDENTITY_TRANSACTION::AtomicUpdateHeadersRevertPhase1((VMX_CHANGE_IDENTITY_TRANSACTION *)v2);
    VMX_PACK::UpdateCounters(this);
    VMX_CHANGE_IDENTITY_TRANSACTION::CheckFailedIo((VMX_CHANGE_IDENTITY_TRANSACTION *)v2);
    VMX_RAW_CONFIG::CleanAfterUpdate((VMX_RAW_CONFIG *)v4);
    if ( v26 )
    {
      ExFreePoolWithTag(P, 0);
      VMX_PACK::AbortDevices(this);
    }
    VMX_PACK::AbortLog((VMX_LOG **)this);
    VMX_CONFIG::AbortRecords(*((VMX_CONFIG **)this + 2));
    *((_QWORD *)this + 6) = 0;
    v6 = WPP_GLOBAL_Control;
    updated = -1070071804;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)updated;
    }
    v7 = 41;
    goto LABEL_77;
  }
  if ( v9 != v8 )
  {
    v12 = 0;
    do
    {
      v13 = *(_QWORD *)(v2 + 168);
      v14 = *(struct VMX_CONFIG_COPY **)(*(_QWORD *)(v13 + 48LL * v12 + 32) + 104LL);
      if ( !*((_BYTE *)v14 + 19) && (int)VMX_RAW_CONFIG::MarkStale((VMX_RAW_CONFIG *)v4, v14) < 0 )
        *(_BYTE *)(v13 + 48LL * v12 + 40) = 1;
      ++v12;
    }
    while ( v12 < *(_DWORD *)(v2 + 160) );
  }
  for ( j = 0; j < *(_DWORD *)(v2 + 160); ++j )
  {
    v16 = *(_QWORD *)(v2 + 168);
    if ( !*(_BYTE *)(v16 + 48LL * j + 40) )
    {
      v17 = *(VMX_PHYSICAL_DISK **)(v16 + 48LL * j + 32);
      v18 = VMX_PHYSICAL_DISK::ChangeIdentityPhase2(v17);
      if ( v18 < 0 )
      {
        if ( v18 != -1073741670 )
          *((_BYTE *)v17 + 125) = 0;
        *(_BYTE *)(v16 + 48LL * j + 40) = 1;
      }
    }
  }
  VMX_RAW_CONFIG::AtomicUpdatePhase3((VMX_RAW_CONFIG *)v4, (struct VMX_TRANSACTION *)v2);
  v19 = (VMX_LOG *)*((_QWORD *)this + 3);
  if ( v19 )
  {
    v20 = (struct VMX_CHANGE_IDENTITY_TRANSACTION *)*((_QWORD *)this + 6);
    v21 = *(VMX_LOG **)(*((_QWORD *)v20 + 7) + 24LL);
    VMX_LOG::Acquire(v19);
    VMX_LOG::Acquire(v21);
    VMX_LOG::ChangeIdentityLog(*((VMX_LOG **)this + 3), v21, v20);
    VMX_LOG::Release(v21);
    v22 = *((_QWORD *)this + 3);
    if ( *(_BYTE *)(v22 + 96) )
      *(_QWORD *)(v22 + 72) = *(_QWORD *)v20;
    VMX_LOG::Release(*((VMX_LOG **)this + 3));
  }
  if ( v26 )
  {
    VMX_PACK::CommitDevices(v19, v26, (struct _VM_DEVICE_CHANGE *)P);
    ExFreePoolWithTag(P, 0);
  }
  VMX_RAW_CONFIG::CleanAfterUpdate((VMX_RAW_CONFIG *)v4);
  VMX_PACK::PostCommitLog(this);
  if ( v26 )
    VMX_PACK::PostCommitDevices(this);
  VmxpSendChangeIdentityTransactionNotifications(
    *((struct VMX_CONFIG **)this + 2),
    (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v2);
  VMX_CONFIG::CommitRecords(*((VMX_CONFIG **)this + 2));
  VMX_PACK::UpdateCounters(this);
  VMX_CHANGE_IDENTITY_TRANSACTION::CheckFailedIo((VMX_CHANGE_IDENTITY_TRANSACTION *)v2);
  if ( *((_BYTE *)this + 57) && !VMX_PACK::QuorumInSync(this) )
    *((_BYTE *)this + 57) = 0;
  *((_QWORD *)this + 6) = 0;
  v23 = VMX_CHANGE_IDENTITY_TRANSACTION::RemoveInvalidDisks((VMX_CHANGE_IDENTITY_TRANSACTION *)v2, this);
  v24 = -2143813630;
  if ( v23 != -2143813630 )
    return 0;
  return v24;
}

```

## disassembly

```asm
0x14004e3ac  mov     [rsp-38h+arg_10], rbx
0x14004e3b1  push    rbp
0x14004e3b2  push    rsi
0x14004e3b3  push    rdi
0x14004e3b4  push    r12
0x14004e3b6  push    r13
0x14004e3b8  push    r14
0x14004e3ba  push    r15
0x14004e3bc  mov     rbp, rsp
0x14004e3bf  sub     rsp, 20h
0x14004e3c3  mov     rax, [rcx+10h]
0x14004e3c7  xor     r13d, r13d
0x14004e3ca  mov     rsi, [rcx+30h]
0x14004e3ce  mov     rdi, rcx
0x14004e3d1  mov     [rbp+arg_0], r13d
0x14004e3d5  mov     rcx, rsi; this
0x14004e3d8  mov     [rbp+P], r13
0x14004e3dc  mov     r14, [rax+8]
0x14004e3e0  mov     rax, 0FFFFF78000000014h
0x14004e3ea  mov     rax, [rax]
0x14004e3ed  mov     [rsi+28h], rax
0x14004e3f1  call    ?AtomicUpdateHeadersPhase0@VMX_CHANGE_IDENTITY_TRANSACTION@@QEAAJXZ; VMX_CHANGE_IDENTITY_TRANSACTION::AtomicUpdateHeadersPhase0(void)
0x14004e3f6  mov     ebx, eax
0x14004e3f8  test    eax, eax
0x14004e3fa  jns     short loc_14004E442
0x14004e3fc  mov     rcx, [rdi+10h]; this
0x14004e400  call    ?AbortRecords@VMX_CONFIG@@QEAAXXZ; VMX_CONFIG::AbortRecords(void)
0x14004e405  mov     [rdi+30h], r13
0x14004e409  mov     r10, cs:WPP_GLOBAL_Control
0x14004e410  lea     rcx, WPP_GLOBAL_Control
0x14004e417  cmp     r10, rcx
0x14004e41a  jz      loc_14004E92F
0x14004e420  test    dword ptr [r10+2Ch], 200h
0x14004e428  jz      loc_14004E92F
0x14004e42e  cmp     byte ptr [r10+29h], 2
0x14004e433  jb      loc_14004E92F
0x14004e439  lea     edx, [r13+23h]
0x14004e43d  jmp     loc_14004E91C
0x14004e442  mov     rcx, rdi; this
0x14004e445  call    ?PreCommitLog@VMX_PACK@@AEAAJXZ; VMX_PACK::PreCommitLog(void)
0x14004e44a  mov     ebx, eax
0x14004e44c  test    eax, eax
0x14004e44e  jns     short loc_14004E497
0x14004e450  mov     rcx, [rdi+10h]; this
0x14004e454  call    ?AbortRecords@VMX_CONFIG@@QEAAXXZ; VMX_CONFIG::AbortRecords(void)
0x14004e459  mov     [rdi+30h], r13
0x14004e45d  mov     r10, cs:WPP_GLOBAL_Control
0x14004e464  lea     rcx, WPP_GLOBAL_Control
0x14004e46b  cmp     r10, rcx
0x14004e46e  jz      loc_14004E92F
0x14004e474  test    dword ptr [r10+2Ch], 200h
0x14004e47c  jz      loc_14004E92F
0x14004e482  cmp     byte ptr [r10+29h], 2
0x14004e487  jb      loc_14004E92F
0x14004e48d  mov     edx, 24h ; '$'
0x14004e492  jmp     loc_14004E91C
0x14004e497  movups  xmm0, xmmword ptr [rsi+70h]
0x14004e49b  lea     r8, [rbp+P]; struct _VM_DEVICE_CHANGE **
0x14004e49f  mov     rcx, rdi; this
0x14004e4a2  lea     rdx, [rbp+arg_0]; unsigned int *
0x14004e4a6  movdqu  xmmword ptr [r14+8], xmm0
0x14004e4ac  call    ?PreCommitDevices@VMX_PACK@@AEAAJPEAKPEAPEAU_VM_DEVICE_CHANGE@@@Z; VMX_PACK::PreCommitDevices(ulong *,_VM_DEVICE_CHANGE * *)
0x14004e4b1  mov     ebx, eax
0x14004e4b3  movups  xmm0, xmmword ptr [rsi+40h]
0x14004e4b7  movdqu  xmmword ptr [r14+8], xmm0
0x14004e4bd  test    eax, eax
0x14004e4bf  jns     short loc_14004E510
0x14004e4c1  mov     rcx, rdi; this
0x14004e4c4  call    ?AbortLog@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortLog(void)
0x14004e4c9  mov     rcx, [rdi+10h]; this
0x14004e4cd  call    ?AbortRecords@VMX_CONFIG@@QEAAXXZ; VMX_CONFIG::AbortRecords(void)
0x14004e4d2  mov     [rdi+30h], r13
0x14004e4d6  mov     r10, cs:WPP_GLOBAL_Control
0x14004e4dd  lea     rcx, WPP_GLOBAL_Control
0x14004e4e4  cmp     r10, rcx
0x14004e4e7  jz      loc_14004E92F
0x14004e4ed  test    dword ptr [r10+2Ch], 200h
0x14004e4f5  jz      loc_14004E92F
0x14004e4fb  cmp     byte ptr [r10+29h], 2
0x14004e500  jb      loc_14004E92F
0x14004e506  mov     edx, 25h ; '%'
0x14004e50b  jmp     loc_14004E91C
0x14004e510  mov     rcx, r14; this
0x14004e513  call    ?PrepareForUpdate@VMX_RAW_CONFIG@@QEAAJXZ; VMX_RAW_CONFIG::PrepareForUpdate(void)
0x14004e518  mov     ebx, eax
0x14004e51a  test    eax, eax
0x14004e51c  jns     short loc_14004E58D
0x14004e51e  cmp     [rbp+arg_0], r13d
0x14004e522  jz      short loc_14004E53E
0x14004e524  mov     rcx, [rbp+P]; P
0x14004e528  xor     edx, edx; Tag
0x14004e52a  call    cs:__imp_ExFreePoolWithTag
0x14004e531  nop     dword ptr [rax+rax+00h]
0x14004e536  mov     rcx, rdi; this
0x14004e539  call    ?AbortDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortDevices(void)
0x14004e53e  mov     rcx, rdi; this
0x14004e541  call    ?AbortLog@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortLog(void)
0x14004e546  mov     rcx, [rdi+10h]; this
0x14004e54a  call    ?AbortRecords@VMX_CONFIG@@QEAAXXZ; VMX_CONFIG::AbortRecords(void)
0x14004e54f  mov     [rdi+30h], r13
0x14004e553  mov     r10, cs:WPP_GLOBAL_Control
0x14004e55a  lea     rcx, WPP_GLOBAL_Control
0x14004e561  cmp     r10, rcx
0x14004e564  jz      loc_14004E92F
0x14004e56a  test    dword ptr [r10+2Ch], 200h
0x14004e572  jz      loc_14004E92F
0x14004e578  cmp     byte ptr [r10+29h], 2
0x14004e57d  jb      loc_14004E92F
0x14004e583  mov     edx, 26h ; '&'
0x14004e588  jmp     loc_14004E91C
0x14004e58d  mov     rcx, rsi; this
0x14004e590  call    ?AtomicUpdateHeadersPhase1@VMX_CHANGE_IDENTITY_TRANSACTION@@QEAAJXZ; VMX_CHANGE_IDENTITY_TRANSACTION::AtomicUpdateHeadersPhase1(void)
0x14004e595  mov     ebx, eax
0x14004e597  mov     rcx, r14; this
0x14004e59a  test    eax, eax
0x14004e59c  jns     short loc_14004E612
0x14004e59e  call    ?CleanAfterUpdate@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::CleanAfterUpdate(void)
0x14004e5a3  cmp     [rbp+arg_0], r13d
0x14004e5a7  jz      short loc_14004E5C3
0x14004e5a9  mov     rcx, [rbp+P]; P
0x14004e5ad  xor     edx, edx; Tag
0x14004e5af  call    cs:__imp_ExFreePoolWithTag
0x14004e5b6  nop     dword ptr [rax+rax+00h]
0x14004e5bb  mov     rcx, rdi; this
0x14004e5be  call    ?AbortDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortDevices(void)
0x14004e5c3  mov     rcx, rdi; this
0x14004e5c6  call    ?AbortLog@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortLog(void)
0x14004e5cb  mov     rcx, [rdi+10h]; this
0x14004e5cf  call    ?AbortRecords@VMX_CONFIG@@QEAAXXZ; VMX_CONFIG::AbortRecords(void)
0x14004e5d4  mov     [rdi+30h], r13
0x14004e5d8  mov     r10, cs:WPP_GLOBAL_Control
0x14004e5df  lea     rcx, WPP_GLOBAL_Control
0x14004e5e6  cmp     r10, rcx
0x14004e5e9  jz      loc_14004E92F
0x14004e5ef  test    dword ptr [r10+2Ch], 200h
0x14004e5f7  jz      loc_14004E92F
0x14004e5fd  cmp     byte ptr [r10+29h], 2
0x14004e602  jb      loc_14004E92F
0x14004e608  mov     edx, 27h ; '''
0x14004e60d  jmp     loc_14004E91C
0x14004e612  mov     rdx, rsi; struct VMX_TRANSACTION *
0x14004e615  call    ?AtomicUpdatePhase1@VMX_RAW_CONFIG@@QEAAJPEAVVMX_TRANSACTION@@@Z; VMX_RAW_CONFIG::AtomicUpdatePhase1(VMX_TRANSACTION *)
0x14004e61a  mov     rcx, rdi; this
0x14004e61d  mov     ebx, eax
0x14004e61f  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x14004e624  test    ebx, ebx
0x14004e626  jns     loc_14004E6B3
0x14004e62c  mov     rcx, rsi; this
0x14004e62f  call    ?AtomicUpdateHeadersRevertPhase1@VMX_CHANGE_IDENTITY_TRANSACTION@@QEAAXXZ; VMX_CHANGE_IDENTITY_TRANSACTION::AtomicUpdateHeadersRevertPhase1(void)
0x14004e634  mov     rcx, rsi; this
0x14004e637  call    ?CheckFailedIo@VMX_CHANGE_IDENTITY_TRANSACTION@@QEAAXXZ; VMX_CHANGE_IDENTITY_TRANSACTION::CheckFailedIo(void)
0x14004e63c  mov     rcx, r14; this
0x14004e63f  call    ?CleanAfterUpdate@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::CleanAfterUpdate(void)
0x14004e644  cmp     [rbp+arg_0], r13d
0x14004e648  jz      short loc_14004E664
0x14004e64a  mov     rcx, [rbp+P]; P
0x14004e64e  xor     edx, edx; Tag
0x14004e650  call    cs:__imp_ExFreePoolWithTag
0x14004e657  nop     dword ptr [rax+rax+00h]
0x14004e65c  mov     rcx, rdi; this
0x14004e65f  call    ?AbortDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortDevices(void)
0x14004e664  mov     rcx, rdi; this
0x14004e667  call    ?AbortLog@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortLog(void)
0x14004e66c  mov     rcx, [rdi+10h]; this
0x14004e670  call    ?AbortRecords@VMX_CONFIG@@QEAAXXZ; VMX_CONFIG::AbortRecords(void)
0x14004e675  mov     [rdi+30h], r13
0x14004e679  mov     r10, cs:WPP_GLOBAL_Control
0x14004e680  lea     rcx, WPP_GLOBAL_Control
0x14004e687  cmp     r10, rcx
0x14004e68a  jz      loc_14004E92F
0x14004e690  test    dword ptr [r10+2Ch], 200h
0x14004e698  jz      loc_14004E92F
0x14004e69e  cmp     byte ptr [r10+29h], 2
0x14004e6a3  jb      loc_14004E92F
0x14004e6a9  mov     edx, 28h ; '('
0x14004e6ae  jmp     loc_14004E91C
0x14004e6b3  mov     r8d, [rsi+0A0h]
0x14004e6ba  test    r8d, r8d
0x14004e6bd  jz      loc_14004E88E
0x14004e6c3  mov     r10, [rsi+0A8h]
0x14004e6ca  mov     ecx, r13d
0x14004e6cd  mov     edx, r13d
0x14004e6d0  mov     eax, edx
0x14004e6d2  lea     rax, [rax+rax*2]
0x14004e6d6  add     rax, rax
0x14004e6d9  mov     rax, [r10+rax*8+20h]
0x14004e6de  mov     r9, [rax+68h]
0x14004e6e2  test    r9, r9
0x14004e6e5  jz      short loc_14004E6EF
0x14004e6e7  cmp     [r9+13h], r13b
0x14004e6eb  jz      short loc_14004E6EF
0x14004e6ed  inc     ecx
0x14004e6ef  inc     edx
0x14004e6f1  cmp     edx, r8d
0x14004e6f4  jb      short loc_14004E6D0
0x14004e6f6  test    ecx, ecx
0x14004e6f8  jz      loc_14004E88E
0x14004e6fe  cmp     ecx, r8d
0x14004e701  jz      short loc_14004E741
0x14004e703  mov     ebx, r13d
0x14004e706  mov     r12, [rsi+0A8h]
0x14004e70d  mov     eax, ebx
0x14004e70f  lea     r15, [rax+rax*2]
0x14004e713  add     r15, r15
0x14004e716  mov     rax, [r12+r15*8+20h]
0x14004e71b  mov     rdx, [rax+68h]; struct VMX_CONFIG_COPY *
0x14004e71f  cmp     [rdx+13h], r13b
0x14004e723  jnz     short loc_14004E737
0x14004e725  mov     rcx, r14; this
0x14004e728  call    ?MarkStale@VMX_RAW_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_RAW_CONFIG::MarkStale(VMX_CONFIG_COPY *)
0x14004e72d  test    eax, eax
0x14004e72f  jns     short loc_14004E737
0x14004e731  mov     byte ptr [r12+r15*8+28h], 1
0x14004e737  inc     ebx
0x14004e739  cmp     ebx, [rsi+0A0h]
0x14004e73f  jb      short loc_14004E706
0x14004e741  mov     ebx, r13d
0x14004e744  cmp     [rsi+0A0h], r13d
0x14004e74b  jbe     short loc_14004E794
0x14004e74d  mov     r12, [rsi+0A8h]
0x14004e754  mov     eax, ebx
0x14004e756  lea     r15, [rax+rax*2]
0x14004e75a  add     r15, r15
0x14004e75d  cmp     [r12+r15*8+28h], r13b
0x14004e762  jnz     short loc_14004E78A
0x14004e764  mov     r13, [r12+r15*8+20h]
0x14004e769  mov     rcx, r13; this
0x14004e76c  call    ?ChangeIdentityPhase2@VMX_PHYSICAL_DISK@@QEAAJXZ; VMX_PHYSICAL_DISK::ChangeIdentityPhase2(void)
0x14004e771  test    eax, eax
0x14004e773  jns     short loc_14004E787
0x14004e775  cmp     eax, 0C000009Ah
0x14004e77a  jz      short loc_14004E781
0x14004e77c  mov     byte ptr [r13+7Dh], 0
0x14004e781  mov     byte ptr [r12+r15*8+28h], 1
0x14004e787  xor     r13d, r13d
0x14004e78a  inc     ebx
0x14004e78c  cmp     ebx, [rsi+0A0h]
0x14004e792  jb      short loc_14004E74D
0x14004e794  mov     rdx, rsi; struct VMX_TRANSACTION *
0x14004e797  mov     rcx, r14; this
0x14004e79a  call    ?AtomicUpdatePhase3@VMX_RAW_CONFIG@@QEAAXPEAVVMX_TRANSACTION@@@Z; VMX_RAW_CONFIG::AtomicUpdatePhase3(VMX_TRANSACTION *)
0x14004e79f  mov     rcx, [rdi+18h]; this
0x14004e7a3  test    rcx, rcx
0x14004e7a6  jz      short loc_14004E7F2
0x14004e7a8  mov     r15, [rdi+30h]
0x14004e7ac  mov     rax, [r15+38h]
0x14004e7b0  mov     rbx, [rax+18h]
0x14004e7b4  call    ?Acquire@VMX_LOG@@QEAAXXZ; VMX_LOG::Acquire(void)
0x14004e7b9  mov     rcx, rbx; this
0x14004e7bc  call    ?Acquire@VMX_LOG@@QEAAXXZ; VMX_LOG::Acquire(void)
0x14004e7c1  mov     rcx, [rdi+18h]; this
0x14004e7c5  mov     r8, r15; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x14004e7c8  mov     rdx, rbx; struct VMX_LOG *
0x14004e7cb  call    ?ChangeIdentityLog@VMX_LOG@@QEAAXPEAV1@PEAVVMX_CHANGE_IDENTITY_TRANSACTION@@@Z; VMX_LOG::ChangeIdentityLog(VMX_LOG *,VMX_CHANGE_IDENTITY_TRANSACTION *)
0x14004e7d0  mov     rcx, rbx; this
0x14004e7d3  call    ?Release@VMX_LOG@@QEAAXXZ; VMX_LOG::Release(void)
0x14004e7d8  mov     rcx, [rdi+18h]
0x14004e7dc  cmp     [rcx+60h], r13b
0x14004e7e0  jz      short loc_14004E7E9
0x14004e7e2  mov     rax, [r15]
0x14004e7e5  mov     [rcx+48h], rax
0x14004e7e9  mov     rcx, [rdi+18h]; this
0x14004e7ed  call    ?Release@VMX_LOG@@QEAAXXZ; VMX_LOG::Release(void)
0x14004e7f2  mov     edx, [rbp+arg_0]; unsigned int
0x14004e7f5  test    edx, edx
0x14004e7f7  jz      short loc_14004E814
0x14004e7f9  mov     r8, [rbp+P]; struct _VM_DEVICE_CHANGE *
0x14004e7fd  call    ?CommitDevices@VMX_PACK@@AEAAXKPEAU_VM_DEVICE_CHANGE@@@Z; VMX_PACK::CommitDevices(ulong,_VM_DEVICE_CHANGE *)
0x14004e802  mov     rcx, [rbp+P]; P
0x14004e806  xor     edx, edx; Tag
0x14004e808  call    cs:__imp_ExFreePoolWithTag
0x14004e80f  nop     dword ptr [rax+rax+00h]
0x14004e814  mov     rcx, r14; this
0x14004e817  call    ?CleanAfterUpdate@VMX_RAW_CONFIG@@QEAAXXZ; VMX_RAW_CONFIG::CleanAfterUpdate(void)
0x14004e81c  mov     rcx, rdi; this
0x14004e81f  call    ?PostCommitLog@VMX_PACK@@AEAAXXZ; VMX_PACK::PostCommitLog(void)
0x14004e824  cmp     [rbp+arg_0], r13d
0x14004e828  jz      short loc_14004E832
0x14004e82a  mov     rcx, rdi; this
0x14004e82d  call    ?PostCommitDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::PostCommitDevices(void)
0x14004e832  mov     rcx, [rdi+10h]; struct VMX_CONFIG *
0x14004e836  mov     rdx, rsi; struct VMX_CHANGE_IDENTITY_TRANSACTION *
0x14004e839  call    ?VmxpSendChangeIdentityTransactionNotifications@@YAXPEAVVMX_CONFIG@@PEAVVMX_CHANGE_IDENTITY_TRANSACTION@@@Z; VmxpSendChangeIdentityTransactionNotifications(VMX_CONFIG *,VMX_CHANGE_IDENTITY_TRANSACTION *)
0x14004e83e  mov     rcx, [rdi+10h]; this
0x14004e842  call    ?CommitRecords@VMX_CONFIG@@QEAAXXZ; VMX_CONFIG::CommitRecords(void)
0x14004e847  mov     rcx, rdi; this
0x14004e84a  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x14004e84f  mov     rcx, rsi; this
0x14004e852  call    ?CheckFailedIo@VMX_CHANGE_IDENTITY_TRANSACTION@@QEAAXXZ; VMX_CHANGE_IDENTITY_TRANSACTION::CheckFailedIo(void)
0x14004e857  cmp     [rdi+39h], r13b
0x14004e85b  jz      short loc_14004E86D
0x14004e85d  mov     rcx, rdi; this
0x14004e860  call    ?QuorumInSync@VMX_PACK@@QEAAEXZ; VMX_PACK::QuorumInSync(void)
0x14004e865  test    al, al
0x14004e867  jnz     short loc_14004E86D
0x14004e869  mov     [rdi+39h], r13b
0x14004e86d  mov     rdx, rdi; struct VMX_PACK *
0x14004e870  mov     [rdi+30h], r13
0x14004e874  mov     rcx, rsi; this
0x14004e877  call    ?RemoveInvalidDisks@VMX_CHANGE_IDENTITY_TRANSACTION@@QEAAJPEAVVMX_PACK@@@Z; VMX_CHANGE_IDENTITY_TRANSACTION::RemoveInvalidDisks(VMX_PACK *)
  ... truncated ...
```
