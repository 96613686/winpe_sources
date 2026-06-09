# VmsTmDestroyTeam

- ea: `0x14015baec`
- end: `0x14015bddf`
- name: `VmsTmDestroyTeam`
- size: `755`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015cc98`

## callees

- `0x140027a64`
- `0x14003c378`
- `0x14008497c`
- `0x14015baec`
- `0x14015bde8`
- `0x14015cbc8`
- `0x1401bb714`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14015bc73`
- `ntoskrnl!KeSetEvent` at `0x14015bc97`
- `ntoskrnl!KeSetEvent` at `0x14015bc73`
- `ntoskrnl!KeSetEvent` at `0x14015bc97`
- `ntoskrnl!RtlDeleteHashTable` at `0x14015bd59`
- `ntoskrnl!RtlDeleteHashTable` at `0x14015bd6c`
- `ntoskrnl!RtlDeleteHashTable` at `0x14015bd59`
- `ntoskrnl!RtlDeleteHashTable` at `0x14015bd6c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015bccd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015bccd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bdc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015bdc5`
- `NDIS!NdisFreeTimerObject` at `0x14015bd9c`
- `NDIS!NdisFreeTimerObject` at `0x14015bd9c`
- `NDIS!NdisCancelTimerObject` at `0x14015bc4e`
- `NDIS!NdisCancelTimerObject` at `0x14015bc4e`
- `NDIS!NdisReleaseRWLock` at `0x14015bbb7`
- `NDIS!NdisReleaseRWLock` at `0x14015bcb1`
- `NDIS!NdisReleaseRWLock` at `0x14015bd46`
- `NDIS!NdisReleaseRWLock` at `0x14015bbb7`
- `NDIS!NdisReleaseRWLock` at `0x14015bcb1`
- `NDIS!NdisReleaseRWLock` at `0x14015bd46`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bb15`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bc31`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bce8`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bb15`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bc31`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015bce8`
- `NDIS!NdisFreeRWLock` at `0x14015bd84`
- `NDIS!NdisFreeRWLock` at `0x14015bdb4`
- `NDIS!NdisFreeRWLock` at `0x14015bd84`
- `NDIS!NdisFreeRWLock` at `0x14015bdb4`

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
0x14015baec  mov     [rsp+arg_10], rbx
0x14015baf1  push    rbp
0x14015baf2  push    rsi
0x14015baf3  push    rdi
0x14015baf4  sub     rsp, 30h
0x14015baf8  xor     eax, eax
0x14015bafa  lea     rdx, [rsp+48h+LockState]; LockState
0x14015baff  mov     rbx, rcx
0x14015bb02  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14015bb07  mov     rcx, [rcx+630h]; Lock
0x14015bb0e  xor     r8d, r8d; Flags
0x14015bb11  mov     [rsp+48h+LockState.Flags], al
0x14015bb15  call    cs:__imp_NdisAcquireRWLockWrite
0x14015bb1c  nop     dword ptr [rax+rax+00h]
0x14015bb21  mov     rcx, cs:WPP_GLOBAL_Control
0x14015bb28  lea     rbp, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015bb2f  xor     esi, esi
0x14015bb31  mov     al, [rcx+29h]
0x14015bb34  dec     al
0x14015bb36  cmp     al, 2
0x14015bb38  ja      short loc_14015BB40
0x14015bb3a  cmp     [rcx+48h], si
0x14015bb3e  jz      short loc_14015BB5F
0x14015bb40  mov     rcx, [rcx+40h]
0x14015bb44  mov     r9d, 2Bh ; '+'
0x14015bb4a  mov     [rsp+48h+var_20], rbx
0x14015bb4f  xor     edx, edx
0x14015bb51  mov     [rsp+48h+Timeout], rbp
0x14015bb56  lea     r8d, [r9-14h]
0x14015bb5a  call    WPP_RECORDER_SF_I
0x14015bb5f  cmp     [rbx+902h], si
0x14015bb66  jz      short loc_14015BB9D
0x14015bb68  mov     rcx, cs:VmsIfrLog
0x14015bb6f  lea     rax, aTeamNiccount0; "Team->NicCount == 0"
0x14015bb76  mov     r9d, 2Ch ; ','
0x14015bb7c  mov     [rsp+48h+var_20], rax
0x14015bb81  mov     [rsp+48h+Timeout], rbp
0x14015bb86  lea     r8d, [r9-19h]
0x14015bb8a  call    WPP_RECORDER_SF_s
0x14015bb8f  cmp     [rbx+902h], si
0x14015bb96  jz      short loc_14015BB9D
0x14015bb98  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Team->NicCount == 0")
0x14015bb9d  mov     rcx, rbx
0x14015bba0  mov     dword ptr [rbx], 3
0x14015bba6  call    VmsTmRemoveAllAggregators
0x14015bbab  mov     rcx, [rbx+630h]; Lock
0x14015bbb2  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bbb7  call    cs:__imp_NdisReleaseRWLock
0x14015bbbe  nop     dword ptr [rax+rax+00h]
0x14015bbc3  mov     rcx, [rbx+0F80h]; void *
0x14015bbca  test    rcx, rcx
0x14015bbcd  jz      short loc_14015BBDB
0x14015bbcf  call    NvIoShutdownWorkerQueue
0x14015bbd4  mov     [rbx+0F80h], rsi
0x14015bbdb  movsxd  rax, dword ptr [rbx+5F0h]
0x14015bbe2  lea     rdi, cs:140000000h
0x14015bbe9  lea     rcx, [rax+rax*8]
0x14015bbed  mov     rax, rva qword_1401F39E8[rdi+rcx*8]
0x14015bbf5  test    rax, rax
0x14015bbf8  jz      short loc_14015BC02
0x14015bbfa  mov     rcx, rbx
0x14015bbfd  call    _guard_dispatch_icall
0x14015bc02  movsxd  rax, dword ptr [rbx+5ECh]
0x14015bc09  imul    rcx, rax, 70h ; 'p'
0x14015bc0d  mov     rax, [rcx+rdi+1F3AC8h]
0x14015bc15  test    rax, rax
0x14015bc18  jz      short loc_14015BC22
0x14015bc1a  mov     rcx, rbx
0x14015bc1d  call    _guard_dispatch_icall
0x14015bc22  mov     rcx, [rbx+630h]; Lock
0x14015bc29  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bc2e  xor     r8d, r8d; Flags
0x14015bc31  call    cs:__imp_NdisAcquireRWLockWrite
0x14015bc38  nop     dword ptr [rax+rax+00h]
0x14015bc3d  mov     rcx, [rbx+918h]; TimerObject
0x14015bc44  mov     edi, 0FFFFh
0x14015bc49  test    rcx, rcx
0x14015bc4c  jz      short loc_14015BC7F
0x14015bc4e  call    cs:__imp_NdisCancelTimerObject
0x14015bc55  nop     dword ptr [rax+rax+00h]
0x14015bc5a  test    al, al
0x14015bc5c  jz      short loc_14015BC7F
0x14015bc5e  add     [rbx+938h], di
0x14015bc65  jnz     short loc_14015BC7F
0x14015bc67  lea     rcx, [rbx+920h]; Event
0x14015bc6e  xor     r8d, r8d; Wait
0x14015bc71  xor     edx, edx; Increment
0x14015bc73  call    cs:__imp_KeSetEvent
0x14015bc7a  nop     dword ptr [rax+rax+00h]
0x14015bc7f  add     [rbx+938h], di
0x14015bc86  lea     rdi, [rbx+920h]
0x14015bc8d  jnz     short loc_14015BCA5
0x14015bc8f  xor     r8d, r8d; Wait
0x14015bc92  xor     edx, edx; Increment
0x14015bc94  mov     rcx, rdi; Event
0x14015bc97  call    cs:__imp_KeSetEvent
0x14015bc9e  nop     dword ptr [rax+rax+00h]
0x14015bca3  jmp     short loc_14015BCF4
0x14015bca5  mov     rcx, [rbx+630h]; Lock
0x14015bcac  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bcb1  call    cs:__imp_NdisReleaseRWLock
0x14015bcb8  nop     dword ptr [rax+rax+00h]
0x14015bcbd  xor     r9d, r9d; Alertable
0x14015bcc0  mov     [rsp+48h+Timeout], rsi; Timeout
0x14015bcc5  xor     r8d, r8d; WaitMode
0x14015bcc8  xor     edx, edx; WaitReason
0x14015bcca  mov     rcx, rdi; Object
0x14015bccd  call    cs:__imp_KeWaitForSingleObject
0x14015bcd4  nop     dword ptr [rax+rax+00h]
0x14015bcd9  mov     rcx, [rbx+630h]; Lock
0x14015bce0  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bce5  xor     r8d, r8d; Flags
0x14015bce8  call    cs:__imp_NdisAcquireRWLockWrite
0x14015bcef  nop     dword ptr [rax+rax+00h]
0x14015bcf4  cmp     [rbx+938h], si
0x14015bcfb  jz      short loc_14015BD32
0x14015bcfd  mov     rcx, cs:VmsIfrLog
0x14015bd04  lea     rax, aTeamRefcount0_0; "Team->RefCount == 0"
0x14015bd0b  mov     r9d, 2Dh ; '-'
0x14015bd11  mov     [rsp+48h+var_20], rax
0x14015bd16  mov     [rsp+48h+Timeout], rbp
0x14015bd1b  lea     r8d, [r9-1Ah]
0x14015bd1f  call    WPP_RECORDER_SF_s
0x14015bd24  cmp     [rbx+938h], si
0x14015bd2b  jz      short loc_14015BD32
0x14015bd2d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Team->RefCount == 0")
0x14015bd32  mov     rcx, rbx
0x14015bd35  call    VmsTmFreeAllVMSPortsAndMacs
0x14015bd3a  mov     rcx, [rbx+630h]; Lock
0x14015bd41  lea     rdx, [rsp+48h+LockState]; LockState
0x14015bd46  call    cs:__imp_NdisReleaseRWLock
0x14015bd4d  nop     dword ptr [rax+rax+00h]
0x14015bd52  lea     rcx, [rbx+648h]; HashTable
0x14015bd59  call    cs:__imp_RtlDeleteHashTable
0x14015bd60  nop     dword ptr [rax+rax+00h]
0x14015bd65  lea     rcx, [rbx+670h]; HashTable
0x14015bd6c  call    cs:__imp_RtlDeleteHashTable
0x14015bd73  nop     dword ptr [rax+rax+00h]
0x14015bd78  mov     rcx, [rbx+638h]; Lock
0x14015bd7f  test    rcx, rcx
0x14015bd82  jz      short loc_14015BD90
0x14015bd84  call    cs:__imp_NdisFreeRWLock
0x14015bd8b  nop     dword ptr [rax+rax+00h]
0x14015bd90  mov     rcx, [rbx+918h]; TimerObject
0x14015bd97  test    rcx, rcx
0x14015bd9a  jz      short loc_14015BDA8
0x14015bd9c  call    cs:__imp_NdisFreeTimerObject
0x14015bda3  nop     dword ptr [rax+rax+00h]
0x14015bda8  mov     rcx, [rbx+630h]; Lock
0x14015bdaf  test    rcx, rcx
0x14015bdb2  jz      short loc_14015BDC0
0x14015bdb4  call    cs:__imp_NdisFreeRWLock
0x14015bdbb  nop     dword ptr [rax+rax+00h]
0x14015bdc0  xor     edx, edx; Tag
0x14015bdc2  mov     rcx, rbx; P
0x14015bdc5  call    cs:__imp_ExFreePoolWithTag
0x14015bdcc  nop     dword ptr [rax+rax+00h]
0x14015bdd1  mov     rbx, [rsp+48h+arg_10]
0x14015bdd6  add     rsp, 30h
0x14015bdda  pop     rdi
0x14015bddb  pop     rsi
0x14015bddc  pop     rbp
0x14015bddd  retn
```
