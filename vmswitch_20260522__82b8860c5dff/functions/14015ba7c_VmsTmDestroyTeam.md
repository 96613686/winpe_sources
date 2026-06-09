# VmsTmDestroyTeam

- ea: `0x14015ba7c`
- end: `0x14015bd6f`
- name: `VmsTmDestroyTeam`
- size: `755`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015cc28`

## callees

- `0x140027a64`
- `0x14003c378`
- `0x14008497c`
- `0x14015ba7c`
- `0x14015bd78`
- `0x14015cb58`
- `0x1401bb6a4`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14015bc03`
- `ntoskrnl!KeSetEvent` at `0x14015bc27`
- `ntoskrnl!KeSetEvent` at `0x14015bc03`
- `ntoskrnl!KeSetEvent` at `0x14015bc27`
- `ntoskrnl!RtlDeleteHashTable` at `0x14015bce9`
- `ntoskrnl!RtlDeleteHashTable` at `0x14015bcfc`
- `ntoskrnl!RtlDeleteHashTable` at `0x14015bce9`
- `ntoskrnl!RtlDeleteHashTable` at `0x14015bcfc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015bc5d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015bc5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bd55`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bd55`
- `NDIS!NdisFreeTimerObject` at `0x14015bd2c`
- `NDIS!NdisFreeTimerObject` at `0x14015bd2c`
- `NDIS!NdisCancelTimerObject` at `0x14015bbde`
- `NDIS!NdisCancelTimerObject` at `0x14015bbde`
- `NDIS!NdisReleaseRWLock` at `0x14015bb47`
- `NDIS!NdisReleaseRWLock` at `0x14015bc41`
- `NDIS!NdisReleaseRWLock` at `0x14015bcd6`
- `NDIS!NdisReleaseRWLock` at `0x14015bb47`
- `NDIS!NdisReleaseRWLock` at `0x14015bc41`
- `NDIS!NdisReleaseRWLock` at `0x14015bcd6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015baa5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bbc1`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bc78`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015baa5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bbc1`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bc78`
- `NDIS!NdisFreeRWLock` at `0x14015bd14`
- `NDIS!NdisFreeRWLock` at `0x14015bd44`
- `NDIS!NdisFreeRWLock` at `0x14015bd14`
- `NDIS!NdisFreeRWLock` at `0x14015bd44`

## pseudocode

```c
void __fastcall VmsTmDestroyTeam(int *P)
{
  struct _NDIS_RW_LOCK_EX *v2; // rcx
  int v3; // edx
  void *v4; // rcx
  void (__fastcall *v5)(int *); // rax
  void (__fastcall *v6)(int *); // rax
  void *v7; // rcx
  bool v8; // zf
  int v9; // edx
  struct _NDIS_RW_LOCK_EX *v10; // rcx
  void *v11; // rcx
  struct _NDIS_RW_LOCK_EX *v12; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  v2 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)P + 198);
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v2, &LockState, 0);
  if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_I(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      23,
      43,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      (char)P);
  if ( *((_WORD *)P + 1153) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v3,
      19,
      44,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      (__int64)"Team->NicCount == 0");
    if ( *((_WORD *)P + 1153) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  *P = 3;
  VmsTmRemoveAllAggregators(P);
  NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)P + 198), &LockState);
  v4 = (void *)*((_QWORD *)P + 496);
  if ( v4 )
  {
    NvIoShutdownWorkerQueue(v4);
    *((_QWORD *)P + 496) = 0;
  }
  v5 = (void (__fastcall *)(int *))qword_1401F39E8[9 * P[380]];
  if ( v5 )
    v5(P);
  v6 = *(void (__fastcall **)(int *))&algn_1401F3AC8[112 * P[379]];
  if ( v6 )
    v6(P);
  NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)P + 198), &LockState, 0);
  v7 = (void *)*((_QWORD *)P + 291);
  if ( v7 )
  {
    if ( NdisCancelTimerObject(v7) )
    {
      v8 = (*((_WORD *)P + 1180))-- == 1;
      if ( v8 )
        KeSetEvent((PRKEVENT)(P + 584), 0, 0);
    }
  }
  v8 = (*((_WORD *)P + 1180))-- == 1;
  if ( v8 )
  {
    KeSetEvent((PRKEVENT)(P + 584), 0, 0);
  }
  else
  {
    NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)P + 198), &LockState);
    KeWaitForSingleObject(P + 584, Executive, 0, 0, 0);
    NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)P + 198), &LockState, 0);
  }
  if ( *((_WORD *)P + 1180) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v9,
      19,
      45,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      (__int64)"Team->RefCount == 0");
    if ( *((_WORD *)P + 1180) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  VmsTmFreeAllVMSPortsAndMacs(P);
  NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)P + 198), &LockState);
  RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(P + 402));
  RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(P + 412));
  v10 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)P + 199);
  if ( v10 )
    NdisFreeRWLock(v10);
  v11 = (void *)*((_QWORD *)P + 291);
  if ( v11 )
    NdisFreeTimerObject(v11);
  v12 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)P + 198);
  if ( v12 )
    NdisFreeRWLock(v12);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14015ba7c  mov     [rsp+arg_10], rbx
0x14015ba81  push    rbp
0x14015ba82  push    rsi
0x14015ba83  push    rdi
0x14015ba84  sub     rsp, 30h
0x14015ba88  xor     eax, eax
0x14015ba8a  lea     rdx, [rsp+48h+LockState]; LockState
0x14015ba8f  mov     rbx, rcx
0x14015ba92  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14015ba97  mov     rcx, [rcx+630h]; Lock
0x14015ba9e  xor     r8d, r8d; Flags
0x14015baa1  mov     [rsp+48h+LockState.Flags], al
0x14015baa5  call    cs:__imp_NdisAcquireRWLockWrite
0x14015baac  nop     dword ptr [rax+rax+00h]
0x14015bab1  mov     rcx, cs:WPP_GLOBAL_Control
0x14015bab8  lea     rbp, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015babf  xor     esi, esi
0x14015bac1  mov     al, [rcx+29h]
0x14015bac4  dec     al
0x14015bac6  cmp     al, 2
0x14015bac8  ja      short loc_14015BAD0
0x14015baca  cmp     [rcx+48h], si
0x14015bace  jz      short loc_14015BAEF
0x14015bad0  mov     rcx, [rcx+40h]
0x14015bad4  mov     r9d, 2Bh ; '+'
0x14015bada  mov     [rsp+48h+var_20], rbx
0x14015badf  xor     edx, edx
0x14015bae1  mov     [rsp+48h+Timeout], rbp
0x14015bae6  lea     r8d, [r9-14h]
0x14015baea  call    WPP_RECORDER_SF_I
0x14015baef  cmp     [rbx+902h], si
0x14015baf6  jz      short loc_14015BB2D
0x14015baf8  mov     rcx, cs:VmsIfrLog
0x14015baff  lea     rax, aTeamNiccount0; "Team->NicCount == 0"
0x14015bb06  mov     r9d, 2Ch ; ','
0x14015bb0c  mov     [rsp+48h+var_20], rax
0x14015bb11  mov     [rsp+48h+Timeout], rbp
0x14015bb16  lea     r8d, [r9-19h]
0x14015bb1a  call    WPP_RECORDER_SF_s
0x14015bb1f  cmp     [rbx+902h], si
0x14015bb26  jz      short loc_14015BB2D
0x14015bb28  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Team->NicCount == 0")
0x14015bb2d  mov     rcx, rbx
0x14015bb30  mov     dword ptr [rbx], 3
0x14015bb36  call    VmsTmRemoveAllAggregators
0x14015bb3b  mov     rcx, [rbx+630h]; Lock
0x14015bb42  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bb47  call    cs:__imp_NdisReleaseRWLock
0x14015bb4e  nop     dword ptr [rax+rax+00h]
0x14015bb53  mov     rcx, [rbx+0F80h]; void *
0x14015bb5a  test    rcx, rcx
0x14015bb5d  jz      short loc_14015BB6B
0x14015bb5f  call    NvIoShutdownWorkerQueue
0x14015bb64  mov     [rbx+0F80h], rsi
0x14015bb6b  movsxd  rax, dword ptr [rbx+5F0h]
0x14015bb72  lea     rdi, cs:140000000h
0x14015bb79  lea     rcx, [rax+rax*8]
0x14015bb7d  mov     rax, rva qword_1401F39E8[rdi+rcx*8]
0x14015bb85  test    rax, rax
0x14015bb88  jz      short loc_14015BB92
0x14015bb8a  mov     rcx, rbx
0x14015bb8d  call    _guard_dispatch_icall
0x14015bb92  movsxd  rax, dword ptr [rbx+5ECh]
0x14015bb99  imul    rcx, rax, 70h ; 'p'
0x14015bb9d  mov     rax, [rcx+rdi+1F3AC8h]
0x14015bba5  test    rax, rax
0x14015bba8  jz      short loc_14015BBB2
0x14015bbaa  mov     rcx, rbx
0x14015bbad  call    _guard_dispatch_icall
0x14015bbb2  mov     rcx, [rbx+630h]; Lock
0x14015bbb9  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bbbe  xor     r8d, r8d; Flags
0x14015bbc1  call    cs:__imp_NdisAcquireRWLockWrite
0x14015bbc8  nop     dword ptr [rax+rax+00h]
0x14015bbcd  mov     rcx, [rbx+918h]; TimerObject
0x14015bbd4  mov     edi, 0FFFFh
0x14015bbd9  test    rcx, rcx
0x14015bbdc  jz      short loc_14015BC0F
0x14015bbde  call    cs:__imp_NdisCancelTimerObject
0x14015bbe5  nop     dword ptr [rax+rax+00h]
0x14015bbea  test    al, al
0x14015bbec  jz      short loc_14015BC0F
0x14015bbee  add     [rbx+938h], di
0x14015bbf5  jnz     short loc_14015BC0F
0x14015bbf7  lea     rcx, [rbx+920h]; Event
0x14015bbfe  xor     r8d, r8d; Wait
0x14015bc01  xor     edx, edx; Increment
0x14015bc03  call    cs:__imp_KeSetEvent
0x14015bc0a  nop     dword ptr [rax+rax+00h]
0x14015bc0f  add     [rbx+938h], di
0x14015bc16  lea     rdi, [rbx+920h]
0x14015bc1d  jnz     short loc_14015BC35
0x14015bc1f  xor     r8d, r8d; Wait
0x14015bc22  xor     edx, edx; Increment
0x14015bc24  mov     rcx, rdi; Event
0x14015bc27  call    cs:__imp_KeSetEvent
0x14015bc2e  nop     dword ptr [rax+rax+00h]
0x14015bc33  jmp     short loc_14015BC84
0x14015bc35  mov     rcx, [rbx+630h]; Lock
0x14015bc3c  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bc41  call    cs:__imp_NdisReleaseRWLock
0x14015bc48  nop     dword ptr [rax+rax+00h]
0x14015bc4d  xor     r9d, r9d; Alertable
0x14015bc50  mov     [rsp+48h+Timeout], rsi; Timeout
0x14015bc55  xor     r8d, r8d; WaitMode
0x14015bc58  xor     edx, edx; WaitReason
0x14015bc5a  mov     rcx, rdi; Object
0x14015bc5d  call    cs:__imp_KeWaitForSingleObject
0x14015bc64  nop     dword ptr [rax+rax+00h]
0x14015bc69  mov     rcx, [rbx+630h]; Lock
0x14015bc70  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bc75  xor     r8d, r8d; Flags
0x14015bc78  call    cs:__imp_NdisAcquireRWLockWrite
0x14015bc7f  nop     dword ptr [rax+rax+00h]
0x14015bc84  cmp     [rbx+938h], si
0x14015bc8b  jz      short loc_14015BCC2
0x14015bc8d  mov     rcx, cs:VmsIfrLog
0x14015bc94  lea     rax, aTeamRefcount0_0; "Team->RefCount == 0"
0x14015bc9b  mov     r9d, 2Dh ; '-'
0x14015bca1  mov     [rsp+48h+var_20], rax
0x14015bca6  mov     [rsp+48h+Timeout], rbp
0x14015bcab  lea     r8d, [r9-1Ah]
0x14015bcaf  call    WPP_RECORDER_SF_s
0x14015bcb4  cmp     [rbx+938h], si
0x14015bcbb  jz      short loc_14015BCC2
0x14015bcbd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Team->RefCount == 0")
0x14015bcc2  mov     rcx, rbx
0x14015bcc5  call    VmsTmFreeAllVMSPortsAndMacs
0x14015bcca  mov     rcx, [rbx+630h]; Lock
0x14015bcd1  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bcd6  call    cs:__imp_NdisReleaseRWLock
0x14015bcdd  nop     dword ptr [rax+rax+00h]
0x14015bce2  lea     rcx, [rbx+648h]; HashTable
0x14015bce9  call    cs:__imp_RtlDeleteHashTable
0x14015bcf0  nop     dword ptr [rax+rax+00h]
0x14015bcf5  lea     rcx, [rbx+670h]; HashTable
0x14015bcfc  call    cs:__imp_RtlDeleteHashTable
0x14015bd03  nop     dword ptr [rax+rax+00h]
0x14015bd08  mov     rcx, [rbx+638h]; Lock
0x14015bd0f  test    rcx, rcx
0x14015bd12  jz      short loc_14015BD20
0x14015bd14  call    cs:__imp_NdisFreeRWLock
0x14015bd1b  nop     dword ptr [rax+rax+00h]
0x14015bd20  mov     rcx, [rbx+918h]; TimerObject
0x14015bd27  test    rcx, rcx
0x14015bd2a  jz      short loc_14015BD38
0x14015bd2c  call    cs:__imp_NdisFreeTimerObject
0x14015bd33  nop     dword ptr [rax+rax+00h]
0x14015bd38  mov     rcx, [rbx+630h]; Lock
0x14015bd3f  test    rcx, rcx
0x14015bd42  jz      short loc_14015BD50
0x14015bd44  call    cs:__imp_NdisFreeRWLock
0x14015bd4b  nop     dword ptr [rax+rax+00h]
0x14015bd50  xor     edx, edx; Tag
0x14015bd52  mov     rcx, rbx; P
0x14015bd55  call    cs:__imp_ExFreePoolWithTag
0x14015bd5c  nop     dword ptr [rax+rax+00h]
0x14015bd61  mov     rbx, [rsp+48h+arg_10]
0x14015bd66  add     rsp, 30h
0x14015bd6a  pop     rdi
0x14015bd6b  pop     rsi
0x14015bd6c  pop     rbp
0x14015bd6d  retn
```
