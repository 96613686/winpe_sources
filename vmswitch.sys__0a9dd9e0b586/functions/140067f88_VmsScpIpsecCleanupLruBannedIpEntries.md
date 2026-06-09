# VmsScpIpsecCleanupLruBannedIpEntries

- ea: `0x140067f88`
- end: `0x140068148`
- name: `VmsScpIpsecCleanupLruBannedIpEntries`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140067f70`

## callees

- `0x140027a64`
- `0x140046e5c`
- `0x140067f88`
- `0x14008497c`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140068111`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140068111`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400680d6`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400680d6`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140068029`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140068029`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14006800a`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400680fe`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14006800a`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400680fe`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140067fe8`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140067fe8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400680e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400680e7`
- `NDIS!NdisReleaseReadWriteLock` at `0x140068040`
- `NDIS!NdisReleaseReadWriteLock` at `0x140068040`
- `NDIS!NdisAcquireReadWriteLock` at `0x140067fd1`
- `NDIS!NdisAcquireReadWriteLock` at `0x140067fd1`

## pseudocode

```c
void VmsScpIpsecCleanupLruBannedIpEntries()
{
  int v0; // edx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v1; // rbx
  _LOCK_STATE LockState; // [rsp+30h] [rbp-19h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+38h] [rbp-11h] BYREF
  struct _KDPC_WATCHDOG_INFORMATION WatchdogInformation; // [rsp+60h] [rbp+17h] BYREF

  LockState = 0;
  memset(&Enumerator, 0, sizeof(Enumerator));
  memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
  NdisAcquireReadWriteLock(&IPsecGlobalBannedIPPairsRWLock, 1u, &LockState);
  if ( !RtlInitEnumerationHashTable(BannedIpPairsTable, &Enumerator) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v0,
      19,
      55,
      (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
      (__int64)"success");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v1 = RtlEnumerateEntryHashTable(BannedIpPairsTable, &Enumerator);
  if ( v1 )
  {
    do
    {
      if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          21,
          56,
          (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids);
      RtlRemoveEntryHashTable(BannedIpPairsTable, v1, 0);
      ExFreePoolWithTag(v1, 0);
      v1 = RtlEnumerateEntryHashTable(BannedIpPairsTable, &Enumerator);
      KeQueryDpcWatchdogInformation(&WatchdogInformation);
    }
    while ( (!WatchdogInformation.DpcWatchdogLimit
          || WatchdogInformation.DpcWatchdogCount <= 75 * WatchdogInformation.DpcWatchdogLimit / 0x64)
         && v1 );
  }
  RtlEndEnumerationHashTable(BannedIpPairsTable, &Enumerator);
  NdisReleaseReadWriteLock(&IPsecGlobalBannedIPPairsRWLock, &LockState);
}

```

## disassembly

```asm
0x140067f88  push    rbp
0x140067f8a  push    rbx
0x140067f8b  push    rsi
0x140067f8c  push    rdi
0x140067f8d  lea     rbp, [rsp-3Fh]
0x140067f92  sub     rsp, 88h
0x140067f99  mov     rax, cs:__security_cookie
0x140067fa0  xor     rax, rsp
0x140067fa3  mov     [rbp+57h+var_28], rax
0x140067fa7  xorps   xmm0, xmm0
0x140067faa  lea     r8, [rbp+57h+LockState]; LockState
0x140067fae  xor     eax, eax
0x140067fb0  lea     rcx, IPsecGlobalBannedIPPairsRWLock; Lock
0x140067fb7  xor     edi, edi
0x140067fb9  mov     qword ptr [rbp+57h+Enumerator.BucketIndex], rax
0x140067fbd  mov     dl, 1; fWrite
0x140067fbf  mov     dword ptr [rbp+57h+LockState.LockState], edi
0x140067fc2  movups  xmmword ptr [rbp+57h+Enumerator.___u0], xmm0
0x140067fc6  mov     [rbp+57h+WatchdogInformation.Reserved], eax
0x140067fc9  movups  xmmword ptr [rbp+57h+Enumerator.___u0+10h], xmm0
0x140067fcd  movups  xmmword ptr [rbp+57h+WatchdogInformation.DpcTimeLimit], xmm0
0x140067fd1  call    cs:__imp_NdisAcquireReadWriteLock
0x140067fd8  nop     dword ptr [rax+rax+00h]
0x140067fdd  mov     rcx, cs:BannedIpPairsTable; HashTable
0x140067fe4  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x140067fe8  call    cs:__imp_RtlInitEnumerationHashTable
0x140067fef  nop     dword ptr [rax+rax+00h]
0x140067ff4  lea     rsi, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x140067ffb  test    al, al
0x140067ffd  jz      short loc_140068065
0x140067fff  mov     rcx, cs:BannedIpPairsTable; HashTable
0x140068006  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x14006800a  call    cs:__imp_RtlEnumerateEntryHashTable
0x140068011  nop     dword ptr [rax+rax+00h]
0x140068016  mov     rbx, rax
0x140068019  test    rax, rax
0x14006801c  jnz     short loc_140068096
0x14006801e  mov     rcx, cs:BannedIpPairsTable; HashTable
0x140068025  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x140068029  call    cs:__imp_RtlEndEnumerationHashTable
0x140068030  nop     dword ptr [rax+rax+00h]
0x140068035  lea     rdx, [rbp+57h+LockState]; LockState
0x140068039  lea     rcx, IPsecGlobalBannedIPPairsRWLock; Lock
0x140068040  call    cs:__imp_NdisReleaseReadWriteLock
0x140068047  nop     dword ptr [rax+rax+00h]
0x14006804c  mov     rcx, [rbp+57h+var_28]
0x140068050  xor     rcx, rsp; StackCookie
0x140068053  call    __security_check_cookie
0x140068058  add     rsp, 88h
0x14006805f  pop     rdi
0x140068060  pop     rsi
0x140068061  pop     rbx
0x140068062  pop     rbp
0x140068063  retn
0x140068065  mov     rcx, cs:VmsIfrLog
0x14006806c  lea     rax, aSuccess; "success"
0x140068073  mov     r9d, 37h ; '7'
0x140068079  mov     [rsp+0A0h+var_78], rax
0x14006807e  mov     [rsp+0A0h+var_80], rsi
0x140068083  lea     r8d, [r9-24h]
0x140068087  call    WPP_RECORDER_SF_s
0x14006808c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x140068091  jmp     loc_140067FFF
0x140068096  mov     r10, cs:WPP_GLOBAL_Control
0x14006809d  mov     cl, [r10+29h]
0x1400680a1  dec     cl
0x1400680a3  cmp     cl, 2
0x1400680a6  ja      short loc_1400680AF
0x1400680a8  cmp     [r10+48h], di
0x1400680ad  jz      short loc_1400680C9
0x1400680af  mov     rcx, [r10+40h]
0x1400680b3  mov     r9d, 38h ; '8'
0x1400680b9  xor     edx, edx
0x1400680bb  mov     [rsp+0A0h+var_80], rsi
0x1400680c0  lea     r8d, [r9-23h]
0x1400680c4  call    WPP_RECORDER_SF_
0x1400680c9  mov     rcx, cs:BannedIpPairsTable; HashTable
0x1400680d0  xor     r8d, r8d; Context
0x1400680d3  mov     rdx, rbx; Entry
0x1400680d6  call    cs:__imp_RtlRemoveEntryHashTable
0x1400680dd  nop     dword ptr [rax+rax+00h]
0x1400680e2  xor     edx, edx; Tag
0x1400680e4  mov     rcx, rbx; P
0x1400680e7  call    cs:__imp_ExFreePoolWithTag
0x1400680ee  nop     dword ptr [rax+rax+00h]
0x1400680f3  mov     rcx, cs:BannedIpPairsTable; HashTable
0x1400680fa  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x1400680fe  call    cs:__imp_RtlEnumerateEntryHashTable
0x140068105  nop     dword ptr [rax+rax+00h]
0x14006810a  lea     rcx, [rbp+57h+WatchdogInformation]; WatchdogInformation
0x14006810e  mov     rbx, rax
0x140068111  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140068118  nop     dword ptr [rax+rax+00h]
0x14006811d  mov     eax, [rbp+57h+WatchdogInformation.DpcWatchdogLimit]
0x140068120  test    eax, eax
0x140068122  jz      short loc_14006813A
0x140068124  imul    ecx, eax, 4Bh ; 'K'
0x140068127  mov     eax, 51EB851Fh
0x14006812c  mul     ecx
0x14006812e  shr     edx, 5
0x140068131  cmp     [rbp+57h+WatchdogInformation.DpcWatchdogCount], edx
0x140068134  ja      loc_14006801E
0x14006813a  test    rbx, rbx
0x14006813d  jnz     loc_140068096
0x140068143  jmp     loc_14006801E
```
