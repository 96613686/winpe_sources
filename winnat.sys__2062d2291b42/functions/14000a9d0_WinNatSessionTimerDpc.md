# WinNatSessionTimerDpc

- ea: `0x14000a9d0`
- end: `0x14000ae62`
- name: `WinNatSessionTimerDpc`
- size: `1170`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006b40`
- `0x14000a9d0`
- `0x14000ae68`
- `0x14000baf8`
- `0x14000c554`
- `0x14000caa0`
- `0x14001a0c8`
- `0x14001b050`
- `0x14001f320`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000aa35`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000aa35`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000aadb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000ad1d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000ade7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000aadb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000ad1d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000ade7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ab2e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ab2e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000aaf1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000aaf1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000ad2c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000ad2c`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14000ad50`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14000ad50`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x14000adbd`
- `NETIO!RtlGetNextExpirationTimerWheelTick` at `0x14000adbd`
- `NETIO!RtlReturnTimerWheelEntry` at `0x14000ad0d`
- `NETIO!RtlReturnTimerWheelEntry` at `0x14000ad0d`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000ad9e`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000ad9e`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14000aaa8`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14000aaa8`

## pseudocode

```c
void __fastcall WinNatSessionTimerDpc(
        struct _KDPC *Dpc,
        KSPIN_LOCK *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  char *v4; // r14
  int i; // edx
  __int64 v7; // rbx
  int v8; // eax
  ULONG CurrentProcessorNumber; // eax
  int v10; // edx
  __int64 v11; // rcx
  KSPIN_LOCK v12; // rax
  __int16 *v13; // rcx
  char v14; // dl
  int v15; // ecx
  int v16; // r9d
  __int64 **v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 NextExpiredTimerWheelEntry; // rax
  __int64 v22; // rsi
  unsigned int NextExpirationTimerWheelTick; // eax
  __int64 *v24; // rcx
  __int64 *v25; // rax
  __int64 *v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 **v27; // [rsp+78h] [rbp-88h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp-80h] BYREF
  _KDPC_WATCHDOG_INFORMATION WatchdogInformation; // [rsp+98h] [rbp-68h] BYREF
  __int16 v30[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v31[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v32[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v33[16]; // [rsp+110h] [rbp+10h] BYREF

  v4 = (char *)(DeferredContext + 8);
  v27 = &v26;
  v26 = (__int64 *)&v26;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
  KeAcquireInStackQueuedSpinLockAtDpcLevel(DeferredContext + 8, &LockHandle);
  for ( i = 0; i <= *((_DWORD *)v4 + 2); ++i )
  {
    while ( *(_DWORD *)&v4[64 * (__int64)i + 64] )
      ;
  }
  RtlUpdateCurrentTimerWheelTick(DeferredContext[59], MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8);
  do
  {
    NextExpiredTimerWheelEntry = RtlGetNextExpiredTimerWheelEntry(DeferredContext[59]);
    v22 = NextExpiredTimerWheelEntry;
    if ( !NextExpiredTimerWheelEntry )
      break;
    v7 = NextExpiredTimerWheelEntry - 144;
    if ( _InterlockedIncrement64((volatile signed __int64 *)(NextExpiredTimerWheelEntry - 144)) <= 1 )
      __fastfail(0xEu);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v7 + 240));
    RtlAcquireScalableWriteLockAtDpcLevel(v4, &LockHandle);
    v8 = *(_DWORD *)(v22 + 20);
    if ( v8 && v8 - *(_DWORD *)(v22 + 16) <= 0 )
    {
      if ( (*(_BYTE *)(v7 + 132) & 1) == 0 )
      {
        CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
        *(_BYTE *)(v7 + 132) |= 1u;
        v10 = *(_DWORD *)(v7 + 120);
        v11 = 136LL * CurrentProcessorNumber;
        v12 = DeferredContext[152];
        if ( v10 == 6 )
        {
          ++*(_DWORD *)(v11 + v12 + 20);
        }
        else if ( v10 == 17 )
        {
          ++*(_DWORD *)(v11 + v12 + 44);
        }
        else
        {
          ++*(_DWORD *)(v11 + v12 + 68);
        }
        if ( (Microsoft_Windows_WinNatEnableBits & 1) != 0 )
        {
          if ( dword_140027104 )
          {
            v13 = *(__int16 **)(v7 + 88);
            memset(v31, 0, 28);
            memset(v33, 0, 28);
            memset(v30, 0, 28);
            memset(v32, 0, 28);
            WinNatCopyTransportAddrToSockAddr(v13, v31);
            WinNatCopyTransportAddrToSockAddr(*(__int16 **)(v7 + 96), v33);
            WinNatCopyTransportAddrToSockAddr(*(__int16 **)(v7 + 104), v30);
            WinNatCopyTransportAddrToSockAddr(*(__int16 **)(v7 + 112), v32);
            if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 1) != 0 )
            {
              if ( (*(_BYTE *)(v7 + 132) & 1) != 0 )
                v14 = 0;
              else
                v14 = *(_DWORD *)(v7 + 136) - MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
              v15 = 28;
              v16 = 28;
              if ( v30[0] == 2 )
                v15 = 16;
              if ( v31[0] == 2 )
                v16 = 16;
              McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                (unsigned int)WINNAT_SESSION_TIMEOUT,
                16,
                v16,
                (__int64)v31,
                (__int64)v33,
                v15,
                (__int64)v30,
                (__int64)v32,
                *(_DWORD *)(v7 + 120),
                v14,
                *(_DWORD *)(v7 + 248),
                *(_DWORD *)(v7 + 8));
            }
          }
        }
        WinNatDeleteSessionEntryUnderLock((__int64)DeferredContext, v22 - 144);
        v17 = v27;
        if ( *v27 != (__int64 *)&v26 )
LABEL_45:
          __fastfail(3u);
        *(_QWORD *)(v7 + 176) = v27;
        *(_QWORD *)(v7 + 168) = &v26;
        *v17 = (__int64 *)(v7 + 168);
        v27 = (__int64 **)(v7 + 168);
      }
    }
    else
    {
      RtlReturnTimerWheelEntry(DeferredContext[59], v22);
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v7 + 240));
    WinNatLibDereferenceSession(v22 - 144);
    RtlAcquireScalableWriteLockAtDpcLevel(v4, &LockHandle);
    if ( KeQueryDpcWatchdogInformation(&WatchdogInformation) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v19, v18, v20);
  }
  while ( (!WatchdogInformation.DpcWatchdogLimit
        || WatchdogInformation.DpcWatchdogCount >= 25 * WatchdogInformation.DpcWatchdogLimit / 0x64)
       && (!WatchdogInformation.DpcTimeLimit
        || WatchdogInformation.DpcTimeCount >= 25 * WatchdogInformation.DpcTimeLimit / 0x64) );
  NextExpirationTimerWheelTick = RtlGetNextExpirationTimerWheelTick(DeferredContext[59]);
  if ( NextExpirationTimerWheelTick )
    WinNatRestartSessionTimer(DeferredContext, NextExpirationTimerWheelTick);
  else
    *((_DWORD *)DeferredContext + 154) = 0;
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  while ( 1 )
  {
    v24 = v26;
    if ( v26 == (__int64 *)&v26 )
      break;
    if ( (__int64 **)v26[1] != &v26 )
      goto LABEL_45;
    v25 = (__int64 *)*v26;
    if ( *(__int64 **)(*v26 + 8) != v26 )
      goto LABEL_45;
    v26 = (__int64 *)*v26;
    v25[1] = (__int64)&v26;
    WinNatLibDereferenceSession(v24 - 21);
  }
}

```

## disassembly

```asm
0x14000a9d0  mov     [rsp-8+arg_0], rbx
0x14000a9d5  mov     [rsp-8+arg_10], rsi
0x14000a9da  push    rbp
0x14000a9db  push    rdi
0x14000a9dc  push    r13
0x14000a9de  push    r14
0x14000a9e0  push    r15
0x14000a9e2  lea     rbp, [rsp-40h]
0x14000a9e7  sub     rsp, 140h
0x14000a9ee  mov     rax, cs:__security_cookie
0x14000a9f5  xor     rax, rsp
0x14000a9f8  mov     [rbp+60h+var_30], rax
0x14000a9fc  xor     eax, eax
0x14000a9fe  lea     r14, [rdx+40h]
0x14000aa02  mov     qword ptr [rbp+60h+LockHandle.OldIrql], rax
0x14000aa06  mov     rdi, rdx
0x14000aa09  mov     [rbp+60h+WatchdogInformation.Reserved], eax
0x14000aa0c  lea     rdx, [rbp+60h+LockHandle]; LockHandle
0x14000aa10  lea     rax, [rsp+160h+var_F0]
0x14000aa15  xorps   xmm0, xmm0
0x14000aa18  mov     [rsp+160h+var_E8], rax
0x14000aa1d  xorps   xmm1, xmm1
0x14000aa20  lea     rax, [rsp+160h+var_F0]
0x14000aa25  mov     rcx, r14; SpinLock
0x14000aa28  mov     [rsp+160h+var_F0], rax
0x14000aa2d  movups  xmmword ptr [rbp+60h+LockHandle.LockQueue.Next], xmm0
0x14000aa31  movups  xmmword ptr [rbp+60h+WatchdogInformation.DpcTimeLimit], xmm1
0x14000aa35  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000aa3c  nop     dword ptr [rax+rax+00h]
0x14000aa41  xor     edx, edx
0x14000aa43  lea     r13d, [rdx+1]
0x14000aa47  cmp     [r14+8], edx
0x14000aa4b  jl      short loc_14000AA66
0x14000aa4d  movsxd  rcx, edx
0x14000aa50  shl     rcx, 6
0x14000aa54  mov     eax, [rcx+r14+40h]
0x14000aa59  test    eax, eax
0x14000aa5b  jnz     short loc_14000AA54
0x14000aa5d  add     edx, r13d
0x14000aa60  cmp     edx, [r14+8]
0x14000aa64  jle     short loc_14000AA4D
0x14000aa66  mov     rax, 0FFFFF78000000008h
0x14000aa70  mov     rcx, [rax]
0x14000aa73  mov     rax, 346DC5D63886594Bh
0x14000aa7d  mul     rcx
0x14000aa80  mov     rax, 624DD2F1A9FBE77h
0x14000aa8a  mov     rcx, rdx
0x14000aa8d  shr     rcx, 0Bh
0x14000aa91  mul     rcx
0x14000aa94  sub     rcx, rdx
0x14000aa97  shr     rcx, 1
0x14000aa9a  add     rdx, rcx
0x14000aa9d  mov     rcx, [rdi+1D8h]
0x14000aaa4  shr     rdx, 9
0x14000aaa8  call    cs:__imp_RtlUpdateCurrentTimerWheelTick
0x14000aaaf  nop     dword ptr [rax+rax+00h]
0x14000aab4  jmp     loc_14000AD97
0x14000aab9  lea     rbx, [rsi-90h]
0x14000aac0  mov     rcx, r13
0x14000aac3  lock xadd [rbx], rcx
0x14000aac8  add     rcx, r13
0x14000aacb  cmp     rcx, r13
0x14000aace  jg      short loc_14000AAD7
0x14000aad0  mov     ecx, 0Eh
0x14000aad5  int     29h; Win8: RtlFailFast(ecx)
0x14000aad7  lea     rcx, [rbp+60h+LockHandle]; LockHandle
0x14000aadb  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000aae2  nop     dword ptr [rax+rax+00h]
0x14000aae7  lea     r15, [rbx+0F0h]
0x14000aaee  mov     rcx, r15; SpinLock
0x14000aaf1  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000aaf8  nop     dword ptr [rax+rax+00h]
0x14000aafd  lea     rdx, [rbp+60h+LockHandle]
0x14000ab01  mov     rcx, r14
0x14000ab04  call    RtlAcquireScalableWriteLockAtDpcLevel
0x14000ab09  mov     eax, [rsi+14h]
0x14000ab0c  test    eax, eax
0x14000ab0e  jz      loc_14000AD03
0x14000ab14  sub     eax, [rsi+10h]
0x14000ab17  test    eax, eax
0x14000ab19  jg      loc_14000AD03
0x14000ab1f  test    [rbx+84h], r13b
0x14000ab26  jnz     loc_14000AD19
0x14000ab2c  xor     ecx, ecx; ProcNumber
0x14000ab2e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000ab35  nop     dword ptr [rax+rax+00h]
0x14000ab3a  or      [rbx+84h], r13b
0x14000ab41  mov     edx, [rbx+78h]
0x14000ab44  mov     eax, eax
0x14000ab46  imul    rcx, rax, 88h
0x14000ab4d  mov     rax, [rdi+4C0h]
0x14000ab54  cmp     edx, 6
0x14000ab57  jnz     short loc_14000AB60
0x14000ab59  add     [rcx+rax+14h], r13d
0x14000ab5e  jmp     short loc_14000AB71
0x14000ab60  cmp     edx, 11h
0x14000ab63  jnz     short loc_14000AB6C
0x14000ab65  add     [rcx+rax+2Ch], r13d
0x14000ab6a  jmp     short loc_14000AB71
0x14000ab6c  add     [rcx+rax+44h], r13d
0x14000ab71  test    cs:Microsoft_Windows_WinNatEnableBits, r13b
0x14000ab78  jz      loc_14000ACC8
0x14000ab7e  cmp     cs:dword_140027104, 0
0x14000ab85  jz      loc_14000ACC8
0x14000ab8b  mov     rcx, [rbx+58h]
0x14000ab8f  lea     rdx, [rbp+60h+var_90]
0x14000ab93  xorps   xmm0, xmm0
0x14000ab96  xorps   xmm1, xmm1
0x14000ab99  movups  xmmword ptr [rbp+60h+var_90], xmm0
0x14000ab9d  xor     eax, eax
0x14000ab9f  movups  xmmword ptr [rbp+60h+var_50], xmm1
0x14000aba3  movups  xmmword ptr [rbp+60h+var_B0], xmm0
0x14000aba7  movups  xmmword ptr [rbp+60h+var_70], xmm1
0x14000abab  movups  xmmword ptr [rbp+60h+var_90+0Ch], xmm0
0x14000abaf  movups  xmmword ptr [rbp+60h+var_50+0Ch], xmm1
0x14000abb3  movups  xmmword ptr [rbp+60h+var_B0+0Ch], xmm0
0x14000abb7  movups  xmmword ptr [rbp+60h+var_70+0Ch], xmm1
0x14000abbb  call    WinNatCopyTransportAddrToSockAddr
0x14000abc0  mov     rcx, [rbx+60h]
0x14000abc4  lea     rdx, [rbp+60h+var_50]
0x14000abc8  call    WinNatCopyTransportAddrToSockAddr
0x14000abcd  mov     rcx, [rbx+68h]
0x14000abd1  lea     rdx, [rbp+60h+var_B0]
0x14000abd5  call    WinNatCopyTransportAddrToSockAddr
0x14000abda  mov     rcx, [rbx+70h]
0x14000abde  lea     rdx, [rbp+60h+var_70]
0x14000abe2  call    WinNatCopyTransportAddrToSockAddr
0x14000abe7  cmp     cs:dword_140027104, r13d
0x14000abee  jnz     loc_14000ACC8
0x14000abf4  test    cs:Microsoft_Windows_WinNatEnableBits, r13b
0x14000abfb  jz      loc_14000ACC8
0x14000ac01  test    [rbx+84h], r13b
0x14000ac08  jz      short loc_14000AC0E
0x14000ac0a  xor     edx, edx
0x14000ac0c  jmp     short loc_14000AC51
0x14000ac0e  mov     rax, 0FFFFF78000000008h
0x14000ac18  mov     rcx, [rax]
0x14000ac1b  mov     rax, 346DC5D63886594Bh
0x14000ac25  mul     rcx
0x14000ac28  mov     rax, 624DD2F1A9FBE77h
0x14000ac32  mov     rcx, rdx
0x14000ac35  shr     rcx, 0Bh
0x14000ac39  mul     rcx
0x14000ac3c  sub     rcx, rdx
0x14000ac3f  shr     rcx, 1
0x14000ac42  add     rcx, rdx
0x14000ac45  mov     edx, [rbx+88h]
0x14000ac4b  shr     rcx, 9
0x14000ac4f  sub     edx, ecx
0x14000ac51  cmp     [rbp+60h+var_B0], 2
0x14000ac56  mov     eax, 1Ch
0x14000ac5b  mov     ecx, eax
0x14000ac5d  mov     r9d, eax
0x14000ac60  lea     r8d, [rax-0Ch]
0x14000ac64  mov     eax, [rbx+8]
0x14000ac67  mov     [rsp+160h+var_100], eax
0x14000ac6b  cmovz   ecx, r8d
0x14000ac6f  mov     eax, [rbx+0F8h]
0x14000ac75  cmp     [rbp+60h+var_90], 2
0x14000ac7a  mov     [rsp+160h+var_108], eax
0x14000ac7e  mov     eax, [rbx+78h]
0x14000ac81  cmovz   r9d, r8d
0x14000ac85  mov     [rsp+160h+var_110], edx
0x14000ac89  lea     rdx, WINNAT_SESSION_TIMEOUT
0x14000ac90  mov     [rsp+160h+var_118], eax
0x14000ac94  lea     rax, [rbp+60h+var_70]
0x14000ac98  mov     [rsp+160h+var_120], rax
0x14000ac9d  lea     rax, [rbp+60h+var_B0]
0x14000aca1  mov     [rsp+160h+var_128], rax
0x14000aca6  lea     rax, [rbp+60h+var_50]
0x14000acaa  mov     [rsp+160h+var_130], ecx
0x14000acae  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000acb5  mov     [rsp+160h+var_138], rax
0x14000acba  lea     rax, [rbp+60h+var_90]
0x14000acbe  mov     [rsp+160h+var_140], rax
0x14000acc3  call    McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer
0x14000acc8  mov     rdx, rbx
0x14000accb  mov     rcx, rdi
0x14000acce  call    WinNatDeleteSessionEntryUnderLock
0x14000acd3  mov     rcx, [rsp+160h+var_E8]
0x14000acd8  lea     rax, [rsp+160h+var_F0]
0x14000acdd  cmp     [rcx], rax
0x14000ace0  jnz     loc_14000AE32
0x14000ace6  lea     rax, [rbx+0A8h]
0x14000aced  mov     [rax+8], rcx
0x14000acf1  lea     rdx, [rsp+160h+var_F0]
0x14000acf6  mov     [rax], rdx
0x14000acf9  mov     [rcx], rax
0x14000acfc  mov     [rsp+160h+var_E8], rax
0x14000ad01  jmp     short loc_14000AD19
0x14000ad03  mov     rcx, [rdi+1D8h]
0x14000ad0a  mov     rdx, rsi
0x14000ad0d  call    cs:__imp_RtlReturnTimerWheelEntry
0x14000ad14  nop     dword ptr [rax+rax+00h]
0x14000ad19  lea     rcx, [rbp+60h+LockHandle]; LockHandle
0x14000ad1d  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000ad24  nop     dword ptr [rax+rax+00h]
0x14000ad29  mov     rcx, r15; SpinLock
0x14000ad2c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000ad33  nop     dword ptr [rax+rax+00h]
0x14000ad38  mov     rcx, rbx
0x14000ad3b  call    WinNatLibDereferenceSession
0x14000ad40  lea     rdx, [rbp+60h+LockHandle]
0x14000ad44  mov     rcx, r14
0x14000ad47  call    RtlAcquireScalableWriteLockAtDpcLevel
0x14000ad4c  lea     rcx, [rbp+60h+WatchdogInformation]; WatchdogInformation
0x14000ad50  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14000ad57  nop     dword ptr [rax+rax+00h]
0x14000ad5c  test    eax, eax
0x14000ad5e  jz      short loc_14000AD65
0x14000ad60  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000ad65  mov     eax, [rbp+60h+WatchdogInformation.DpcWatchdogLimit]
0x14000ad68  test    eax, eax
0x14000ad6a  jz      short loc_14000AD7E
0x14000ad6c  imul    ecx, eax, 19h
0x14000ad6f  mov     eax, 51EB851Fh
0x14000ad74  mul     ecx
0x14000ad76  shr     edx, 5
0x14000ad79  cmp     [rbp+60h+WatchdogInformation.DpcWatchdogCount], edx
0x14000ad7c  jb      short loc_14000ADB6
0x14000ad7e  mov     eax, [rbp+60h+WatchdogInformation.DpcTimeLimit]
0x14000ad81  test    eax, eax
0x14000ad83  jz      short loc_14000AD97
0x14000ad85  imul    ecx, eax, 19h
0x14000ad88  mov     eax, 51EB851Fh
0x14000ad8d  mul     ecx
0x14000ad8f  shr     edx, 5
0x14000ad92  cmp     [rbp+60h+WatchdogInformation.DpcTimeCount], edx
0x14000ad95  jb      short loc_14000ADB6
0x14000ad97  mov     rcx, [rdi+1D8h]
0x14000ad9e  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x14000ada5  nop     dword ptr [rax+rax+00h]
0x14000adaa  mov     rsi, rax
0x14000adad  test    rax, rax
0x14000adb0  jnz     loc_14000AAB9
0x14000adb6  mov     rcx, [rdi+1D8h]
0x14000adbd  call    cs:__imp_RtlGetNextExpirationTimerWheelTick
0x14000adc4  nop     dword ptr [rax+rax+00h]
0x14000adc9  test    eax, eax
0x14000adcb  jz      short loc_14000ADD9
0x14000adcd  mov     edx, eax
0x14000adcf  mov     rcx, rdi
0x14000add2  call    WinNatRestartSessionTimer
0x14000add7  jmp     short loc_14000ADE3
0x14000add9  mov     dword ptr [rdi+268h], 0
0x14000ade3  lea     rcx, [rbp+60h+LockHandle]; LockHandle
0x14000ade7  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000adee  nop     dword ptr [rax+rax+00h]
0x14000adf3  mov     rcx, [rsp+160h+var_F0]
0x14000adf8  lea     rax, [rsp+160h+var_F0]
0x14000adfd  cmp     rcx, rax
0x14000ae00  jz      short loc_14000AE39
0x14000ae02  lea     rax, [rsp+160h+var_F0]
0x14000ae07  cmp     [rcx+8], rax
0x14000ae0b  jnz     short loc_14000AE32
0x14000ae0d  mov     rax, [rcx]
0x14000ae10  cmp     [rax+8], rcx
0x14000ae14  jnz     short loc_14000AE32
0x14000ae16  lea     rdx, [rsp+160h+var_F0]
0x14000ae1b  mov     [rsp+160h+var_F0], rax
0x14000ae20  add     rcx, 0FFFFFFFFFFFFFF58h
0x14000ae27  mov     [rax+8], rdx
0x14000ae2b  call    WinNatLibDereferenceSession
0x14000ae30  jmp     short loc_14000ADF3
0x14000ae32  mov     ecx, 3
0x14000ae37  int     29h; Win8: RtlFailFast(ecx)
0x14000ae39  mov     rcx, [rbp+60h+var_30]
0x14000ae3d  xor     rcx, rsp; StackCookie
0x14000ae40  call    __security_check_cookie
0x14000ae45  lea     r11, [rsp+160h+var_20]
0x14000ae4d  mov     rbx, [r11+30h]
0x14000ae51  mov     rsi, [r11+40h]
0x14000ae55  mov     rsp, r11
0x14000ae58  pop     r15
0x14000ae5a  pop     r14
0x14000ae5c  pop     r13
0x14000ae5e  pop     rdi
0x14000ae5f  pop     rbp
0x14000ae60  retn
```
