# VmsScIPsecOffloadStateInit

- ea: `0x14014ef60`
- end: `0x14014f177`
- name: `VmsScIPsecOffloadStateInit`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400a2918`

## callees

- `0x14003a450`
- `0x14014ef60`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14014ef7b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014efcb`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f01b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f068`
- `ntoskrnl!RtlCreateHashTable` at `0x14014ef7b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014efcb`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f01b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f068`
- `ntoskrnl!KeInitializeTimerEx` at `0x14014f12e`
- `ntoskrnl!KeInitializeTimerEx` at `0x14014f12e`
- `ntoskrnl!KeInitializeDpc` at `0x14014f119`
- `ntoskrnl!KeInitializeDpc` at `0x14014f119`
- `ntoskrnl!KeSetTimerEx` at `0x14014f151`
- `ntoskrnl!KeSetTimerEx` at `0x14014f151`
- `NDIS!NdisInitializeReadWriteLock` at `0x14014f0d6`
- `NDIS!NdisInitializeReadWriteLock` at `0x14014f0e9`
- `NDIS!NdisInitializeReadWriteLock` at `0x14014f0d6`
- `NDIS!NdisInitializeReadWriteLock` at `0x14014f0e9`

## pseudocode

```c
__int64 VmsScIPsecOffloadStateInit()
{
  int v0; // edx
  unsigned int v1; // esi
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx

  if ( !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)&WPP_MAIN_CB.Dpc.DeferredRoutine, 0, 0) )
  {
    v1 = -1073741823;
    LOBYTE(v0) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v0, 20, 10, (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids, 1);
LABEL_9:
    LOBYTE(v2) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v2, 20, 14, (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids, 1);
    return v1;
  }
  if ( !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)&WPP_MAIN_CB.Dpc.SystemArgument1, 0, 0) )
  {
    v1 = -1073741823;
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v3, 20, 11, (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids, 1);
    goto LABEL_9;
  }
  if ( !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)&WPP_MAIN_CB.Dpc.DeferredContext, 0, 0) )
  {
    v1 = -1073741823;
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v4, 20, 12, (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids, 1);
    goto LABEL_9;
  }
  if ( !RtlCreateHashTable(&BannedIpPairsTable, 0, 0) )
  {
    v1 = -1073741823;
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v5, 20, 13, (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids, 1);
    goto LABEL_9;
  }
  v1 = 0;
  NdisInitializeReadWriteLock((PNDIS_RW_LOCK)&WPP_MAIN_CB.Dpc.DpcData);
  NdisInitializeReadWriteLock(&IPsecGlobalBannedIPPairsRWLock);
  if ( !InitializedBannedIpCleanup )
  {
    KeInitializeDpc(&BannedIpCleanupTimer, VmsScpIpsecCleanupLruBannedIpEntriesAtDpc, 0);
    KeInitializeTimerEx(&Timer, NotificationTimer);
    KeSetTimerEx(&Timer, (LARGE_INTEGER)-3000000000LL, 300000, &BannedIpCleanupTimer);
    InitializedBannedIpCleanup = 1;
  }
  return v1;
}

```

## disassembly

```asm
0x14014ef60  mov     [rsp+arg_0], rbx
0x14014ef65  mov     [rsp+arg_8], rsi
0x14014ef6a  push    rdi
0x14014ef6b  sub     rsp, 30h
0x14014ef6f  xor     r8d, r8d; Flags
0x14014ef72  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014ef79  xor     edx, edx; Shift
0x14014ef7b  call    cs:__imp_RtlCreateHashTable
0x14014ef82  nop     dword ptr [rax+rax+00h]
0x14014ef87  test    al, al
0x14014ef89  jnz     short loc_14014EFBF
0x14014ef8b  mov     ebx, 0C0000001h
0x14014ef90  mov     esi, ebx
0x14014ef92  mov     rcx, cs:VmsIfrLog
0x14014ef99  lea     rdi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014efa0  mov     r9d, 0Ah
0x14014efa6  mov     [rsp+38h+var_10], ebx
0x14014efaa  mov     dl, 2
0x14014efac  mov     [rsp+38h+var_18], rdi
0x14014efb1  lea     r8d, [r9+0Ah]
0x14014efb5  call    WPP_RECORDER_SF_d
0x14014efba  jmp     loc_14014F0A7
0x14014efbf  xor     r8d, r8d; Flags
0x14014efc2  lea     rcx, WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014efc9  xor     edx, edx; Shift
0x14014efcb  call    cs:__imp_RtlCreateHashTable
0x14014efd2  nop     dword ptr [rax+rax+00h]
0x14014efd7  test    al, al
0x14014efd9  jnz     short loc_14014F00F
0x14014efdb  mov     ebx, 0C0000001h
0x14014efe0  mov     esi, ebx
0x14014efe2  mov     rcx, cs:VmsIfrLog
0x14014efe9  lea     rdi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014eff0  mov     r9d, 0Bh
0x14014eff6  mov     [rsp+38h+var_10], ebx
0x14014effa  mov     dl, 2
0x14014effc  mov     [rsp+38h+var_18], rdi
0x14014f001  lea     r8d, [r9+9]
0x14014f005  call    WPP_RECORDER_SF_d
0x14014f00a  jmp     loc_14014F0A7
0x14014f00f  xor     r8d, r8d; Flags
0x14014f012  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; HashTable
0x14014f019  xor     edx, edx; Shift
0x14014f01b  call    cs:__imp_RtlCreateHashTable
0x14014f022  nop     dword ptr [rax+rax+00h]
0x14014f027  test    al, al
0x14014f029  jnz     short loc_14014F05C
0x14014f02b  mov     ebx, 0C0000001h
0x14014f030  mov     esi, ebx
0x14014f032  mov     rcx, cs:VmsIfrLog
0x14014f039  lea     rdi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f040  mov     r9d, 0Ch
0x14014f046  mov     [rsp+38h+var_10], ebx
0x14014f04a  mov     dl, 2
0x14014f04c  mov     [rsp+38h+var_18], rdi
0x14014f051  lea     r8d, [r9+8]
0x14014f055  call    WPP_RECORDER_SF_d
0x14014f05a  jmp     short loc_14014F0A7
0x14014f05c  xor     r8d, r8d; Flags
0x14014f05f  lea     rcx, BannedIpPairsTable; HashTable
0x14014f066  xor     edx, edx; Shift
0x14014f068  call    cs:__imp_RtlCreateHashTable
0x14014f06f  nop     dword ptr [rax+rax+00h]
0x14014f074  test    al, al
0x14014f076  jnz     short loc_14014F0CD
0x14014f078  mov     ebx, 0C0000001h
0x14014f07d  mov     esi, ebx
0x14014f07f  mov     rcx, cs:VmsIfrLog
0x14014f086  lea     rdi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f08d  mov     r9d, 0Dh
0x14014f093  mov     [rsp+38h+var_10], ebx
0x14014f097  mov     dl, 2
0x14014f099  mov     [rsp+38h+var_18], rdi
0x14014f09e  lea     r8d, [r9+7]
0x14014f0a2  call    WPP_RECORDER_SF_d
0x14014f0a7  mov     rcx, cs:VmsIfrLog
0x14014f0ae  mov     r9d, 0Eh
0x14014f0b4  mov     [rsp+38h+var_10], ebx
0x14014f0b8  mov     dl, 2
0x14014f0ba  mov     [rsp+38h+var_18], rdi
0x14014f0bf  lea     r8d, [r9+6]
0x14014f0c3  call    WPP_RECORDER_SF_d
0x14014f0c8  jmp     loc_14014F164
0x14014f0cd  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014f0d4  xor     esi, esi
0x14014f0d6  call    cs:__imp_NdisInitializeReadWriteLock
0x14014f0dd  nop     dword ptr [rax+rax+00h]
0x14014f0e2  lea     rcx, IPsecGlobalBannedIPPairsRWLock; Lock
0x14014f0e9  call    cs:__imp_NdisInitializeReadWriteLock
0x14014f0f0  nop     dword ptr [rax+rax+00h]
0x14014f0f5  cmp     cs:InitializedBannedIpCleanup, sil
0x14014f0fc  jnz     short loc_14014F164
0x14014f0fe  xor     r8d, r8d; DeferredContext
0x14014f101  lea     rdx, VmsScpIpsecCleanupLruBannedIpEntriesAtDpc; DeferredRoutine
0x14014f108  lea     rcx, BannedIpCleanupTimer; Dpc
0x14014f10f  mov     rbx, 0FFFFFFFF4D2FA200h
0x14014f119  call    cs:__imp_KeInitializeDpc
0x14014f120  nop     dword ptr [rax+rax+00h]
0x14014f125  xor     edx, edx; Type
0x14014f127  lea     rcx, Timer; Timer
0x14014f12e  call    cs:__imp_KeInitializeTimerEx
0x14014f135  nop     dword ptr [rax+rax+00h]
0x14014f13a  lea     r9, BannedIpCleanupTimer; Dpc
0x14014f141  mov     r8d, 493E0h; Period
0x14014f147  mov     rdx, rbx; DueTime
0x14014f14a  lea     rcx, Timer; Timer
0x14014f151  call    cs:__imp_KeSetTimerEx
0x14014f158  nop     dword ptr [rax+rax+00h]
0x14014f15d  mov     cs:InitializedBannedIpCleanup, 1
0x14014f164  mov     rbx, [rsp+38h+arg_0]
0x14014f169  mov     eax, esi
0x14014f16b  mov     rsi, [rsp+38h+arg_8]
0x14014f170  add     rsp, 30h
0x14014f174  pop     rdi
0x14014f175  retn
```
