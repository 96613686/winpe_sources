# VmsScIPsecOffloadStateInit

- ea: `0x14014efd0`
- end: `0x14014f1e7`
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
- `0x14014efd0`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14014efeb`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f03b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f08b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f0d8`
- `ntoskrnl!RtlCreateHashTable` at `0x14014efeb`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f03b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f08b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014f0d8`
- `ntoskrnl!KeInitializeTimerEx` at `0x14014f19e`
- `ntoskrnl!KeInitializeTimerEx` at `0x14014f19e`
- `ntoskrnl!KeInitializeDpc` at `0x14014f189`
- `ntoskrnl!KeInitializeDpc` at `0x14014f189`
- `ntoskrnl!KeSetTimerEx` at `0x14014f1c1`
- `ntoskrnl!KeSetTimerEx` at `0x14014f1c1`
- `NDIS!NdisInitializeReadWriteLock` at `0x14014f146`
- `NDIS!NdisInitializeReadWriteLock` at `0x14014f159`
- `NDIS!NdisInitializeReadWriteLock` at `0x14014f146`
- `NDIS!NdisInitializeReadWriteLock` at `0x14014f159`

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
0x14014efd0  mov     [rsp+arg_0], rbx
0x14014efd5  mov     [rsp+arg_8], rsi
0x14014efda  push    rdi
0x14014efdb  sub     rsp, 30h
0x14014efdf  xor     r8d, r8d; Flags
0x14014efe2  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014efe9  xor     edx, edx; Shift
0x14014efeb  call    cs:__imp_RtlCreateHashTable
0x14014eff2  nop     dword ptr [rax+rax+00h]
0x14014eff7  test    al, al
0x14014eff9  jnz     short loc_14014F02F
0x14014effb  mov     ebx, 0C0000001h
0x14014f000  mov     esi, ebx
0x14014f002  mov     rcx, cs:VmsIfrLog
0x14014f009  lea     rdi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f010  mov     r9d, 0Ah
0x14014f016  mov     [rsp+38h+var_10], ebx
0x14014f01a  mov     dl, 2
0x14014f01c  mov     [rsp+38h+var_18], rdi
0x14014f021  lea     r8d, [r9+0Ah]
0x14014f025  call    WPP_RECORDER_SF_d
0x14014f02a  jmp     loc_14014F117
0x14014f02f  xor     r8d, r8d; Flags
0x14014f032  lea     rcx, WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014f039  xor     edx, edx; Shift
0x14014f03b  call    cs:__imp_RtlCreateHashTable
0x14014f042  nop     dword ptr [rax+rax+00h]
0x14014f047  test    al, al
0x14014f049  jnz     short loc_14014F07F
0x14014f04b  mov     ebx, 0C0000001h
0x14014f050  mov     esi, ebx
0x14014f052  mov     rcx, cs:VmsIfrLog
0x14014f059  lea     rdi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f060  mov     r9d, 0Bh
0x14014f066  mov     [rsp+38h+var_10], ebx
0x14014f06a  mov     dl, 2
0x14014f06c  mov     [rsp+38h+var_18], rdi
0x14014f071  lea     r8d, [r9+9]
0x14014f075  call    WPP_RECORDER_SF_d
0x14014f07a  jmp     loc_14014F117
0x14014f07f  xor     r8d, r8d; Flags
0x14014f082  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; HashTable
0x14014f089  xor     edx, edx; Shift
0x14014f08b  call    cs:__imp_RtlCreateHashTable
0x14014f092  nop     dword ptr [rax+rax+00h]
0x14014f097  test    al, al
0x14014f099  jnz     short loc_14014F0CC
0x14014f09b  mov     ebx, 0C0000001h
0x14014f0a0  mov     esi, ebx
0x14014f0a2  mov     rcx, cs:VmsIfrLog
0x14014f0a9  lea     rdi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f0b0  mov     r9d, 0Ch
0x14014f0b6  mov     [rsp+38h+var_10], ebx
0x14014f0ba  mov     dl, 2
0x14014f0bc  mov     [rsp+38h+var_18], rdi
0x14014f0c1  lea     r8d, [r9+8]
0x14014f0c5  call    WPP_RECORDER_SF_d
0x14014f0ca  jmp     short loc_14014F117
0x14014f0cc  xor     r8d, r8d; Flags
0x14014f0cf  lea     rcx, BannedIpPairsTable; HashTable
0x14014f0d6  xor     edx, edx; Shift
0x14014f0d8  call    cs:__imp_RtlCreateHashTable
0x14014f0df  nop     dword ptr [rax+rax+00h]
0x14014f0e4  test    al, al
0x14014f0e6  jnz     short loc_14014F13D
0x14014f0e8  mov     ebx, 0C0000001h
0x14014f0ed  mov     esi, ebx
0x14014f0ef  mov     rcx, cs:VmsIfrLog
0x14014f0f6  lea     rdi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014f0fd  mov     r9d, 0Dh
0x14014f103  mov     [rsp+38h+var_10], ebx
0x14014f107  mov     dl, 2
0x14014f109  mov     [rsp+38h+var_18], rdi
0x14014f10e  lea     r8d, [r9+7]
0x14014f112  call    WPP_RECORDER_SF_d
0x14014f117  mov     rcx, cs:VmsIfrLog
0x14014f11e  mov     r9d, 0Eh
0x14014f124  mov     [rsp+38h+var_10], ebx
0x14014f128  mov     dl, 2
0x14014f12a  mov     [rsp+38h+var_18], rdi
0x14014f12f  lea     r8d, [r9+6]
0x14014f133  call    WPP_RECORDER_SF_d
0x14014f138  jmp     loc_14014F1D4
0x14014f13d  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014f144  xor     esi, esi
0x14014f146  call    cs:__imp_NdisInitializeReadWriteLock
0x14014f14d  nop     dword ptr [rax+rax+00h]
0x14014f152  lea     rcx, IPsecGlobalBannedIPPairsRWLock; Lock
0x14014f159  call    cs:__imp_NdisInitializeReadWriteLock
0x14014f160  nop     dword ptr [rax+rax+00h]
0x14014f165  cmp     cs:InitializedBannedIpCleanup, sil
0x14014f16c  jnz     short loc_14014F1D4
0x14014f16e  xor     r8d, r8d; DeferredContext
0x14014f171  lea     rdx, VmsScpIpsecCleanupLruBannedIpEntriesAtDpc; DeferredRoutine
0x14014f178  lea     rcx, BannedIpCleanupTimer; Dpc
0x14014f17f  mov     rbx, 0FFFFFFFF4D2FA200h
0x14014f189  call    cs:__imp_KeInitializeDpc
0x14014f190  nop     dword ptr [rax+rax+00h]
0x14014f195  xor     edx, edx; Type
0x14014f197  lea     rcx, Timer; Timer
0x14014f19e  call    cs:__imp_KeInitializeTimerEx
0x14014f1a5  nop     dword ptr [rax+rax+00h]
0x14014f1aa  lea     r9, BannedIpCleanupTimer; Dpc
0x14014f1b1  mov     r8d, 493E0h; Period
0x14014f1b7  mov     rdx, rbx; DueTime
0x14014f1ba  lea     rcx, Timer; Timer
0x14014f1c1  call    cs:__imp_KeSetTimerEx
0x14014f1c8  nop     dword ptr [rax+rax+00h]
0x14014f1cd  mov     cs:InitializedBannedIpCleanup, 1
0x14014f1d4  mov     rbx, [rsp+38h+arg_0]
0x14014f1d9  mov     eax, esi
0x14014f1db  mov     rsi, [rsp+38h+arg_8]
0x14014f1e0  add     rsp, 30h
0x14014f1e4  pop     rdi
0x14014f1e5  retn
```
