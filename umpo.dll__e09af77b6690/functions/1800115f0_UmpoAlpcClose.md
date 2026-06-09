# UmpoAlpcClose

- ea: `0x1800115f0`
- end: `0x180011788`
- name: `UmpoAlpcClose`
- size: `408`
- prototype: `int()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015280`

## callees

- `0x18000f3dc`
- `0x1800115f0`
- `0x180011918`

## import_xrefs

- `ntdll!NtAlpcDisconnectPort` at `0x180011656`
- `ntdll!NtAlpcDisconnectPort` at `0x180011656`
- `ntdll!TpWaitForAlpcCompletion` at `0x180011723`
- `ntdll!TpWaitForAlpcCompletion` at `0x180011723`
- `ntdll!NtAlpcQueryInformation` at `0x180011675`
- `ntdll!NtAlpcQueryInformation` at `0x180011675`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001163b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011695`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001170e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001163b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011695`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001170e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800116c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800116c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800116e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800116e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011611`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011611`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011646`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001169d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011716`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011646`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001169d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011716`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800116e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800116e7`

## pseudocode

```c
int UmpoAlpcClose()
{
  DWORD CurrentThreadId; // eax
  HANDLE v1; // rbx
  int result; // eax
  __int128 v3; // [rsp+30h] [rbp-18h] BYREF

  v3 = 0;
  AcquireSRWLockShared(&UmpoAlpcPoPortLock);
  if ( UmpoAlpcPoPort )
  {
    NtAlpcDisconnectPort(UmpoAlpcPoPort, 1);
    if ( (int)NtAlpcQueryInformation(UmpoAlpcPoPort, 0, &v3, 16, 0) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( UmpoAlpcPoPortLockThread )
    {
      UmpoAlpcPoPortLockThread = 0;
      ReleaseSRWLockExclusive(&UmpoAlpcPoPortLock);
    }
    else
    {
      ReleaseSRWLockShared(&UmpoAlpcPoPortLock);
    }
    UmpoFinalSequenceCount = DWORD1(v3);
    if ( DWORD1(v3) != UmpoSequenceCount )
      WaitForSingleObject(UmpoAlpcEvent, 0xFFFFFFFF);
    if ( UmpoFinalSequenceCount != DWORD1(v3) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( UmpoAlpcPoPortLockThread )
    {
      UmpoAlpcPoPortLockThread = 0;
      ReleaseSRWLockExclusive(&UmpoAlpcPoPortLock);
    }
    else
    {
      ReleaseSRWLockShared(&UmpoAlpcPoPortLock);
    }
  }
  AcquireSRWLockExclusive(&UmpoAlpcPoPortLock);
  CurrentThreadId = GetCurrentThreadId();
  v1 = UmpoAlpcPoPort;
  UmpoAlpcPoPortLockThread = CurrentThreadId;
  UmpoAlpcPoPort = 0;
  if ( CurrentThreadId )
  {
    UmpoAlpcPoPortLockThread = 0;
    ReleaseSRWLockExclusive(&UmpoAlpcPoPortLock);
  }
  else
  {
    ReleaseSRWLockShared(&UmpoAlpcPoPortLock);
  }
  TpWaitForAlpcCompletion(UmpoAlpcCompletion);
  result = UmpoAlpcReleaseResources(v1);
  if ( UmpoAlpcPoPort )
    result = MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( UmpoAlpcEvent )
    result = MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( UmpoAlpcPoPortLockThread )
    result = MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( UmpoAlpcCompletion )
    result = MicrosoftTelemetryAssertTriggeredNoArgs();
  UmpoFinalSequenceCount = 0;
  UmpoSequenceCount = 1;
  return result;
}

```

## disassembly

```asm
0x1800115f0  mov     [rsp+arg_0], rbx
0x1800115f5  mov     [rsp+arg_8], rsi
0x1800115fa  push    rdi
0x1800115fb  sub     rsp, 40h
0x1800115ff  xorps   xmm0, xmm0
0x180011602  lea     rsi, UmpoAlpcPoPortLock
0x180011609  mov     rcx, rsi; SRWLock
0x18001160c  movups  [rsp+48h+var_18], xmm0
0x180011611  call    cs:__imp_AcquireSRWLockShared
0x180011617  mov     rcx, cs:UmpoAlpcPoPort
0x18001161e  xor     edi, edi
0x180011620  test    rcx, rcx
0x180011623  jnz     short loc_180011651
0x180011625  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001162a  cmp     cs:UmpoAlpcPoPortLockThread, edi
0x180011630  mov     rcx, rsi; SRWLock
0x180011633  jz      short loc_180011646
0x180011635  mov     cs:UmpoAlpcPoPortLockThread, edi
0x18001163b  call    cs:__imp_ReleaseSRWLockExclusive
0x180011641  jmp     loc_1800116DE
0x180011646  call    cs:__imp_ReleaseSRWLockShared
0x18001164c  jmp     loc_1800116DE
0x180011651  mov     edx, 1
0x180011656  call    cs:__imp_NtAlpcDisconnectPort
0x18001165c  mov     rcx, cs:UmpoAlpcPoPort
0x180011663  lea     r8, [rsp+48h+var_18]
0x180011668  mov     r9d, 10h
0x18001166e  mov     [rsp+48h+var_28], rdi
0x180011673  xor     edx, edx
0x180011675  call    cs:__imp_NtAlpcQueryInformation
0x18001167b  test    eax, eax
0x18001167d  jns     short loc_180011684
0x18001167f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011684  cmp     cs:UmpoAlpcPoPortLockThread, edi
0x18001168a  mov     rcx, rsi; SRWLock
0x18001168d  jz      short loc_18001169D
0x18001168f  mov     cs:UmpoAlpcPoPortLockThread, edi
0x180011695  call    cs:__imp_ReleaseSRWLockExclusive
0x18001169b  jmp     short loc_1800116A3
0x18001169d  call    cs:__imp_ReleaseSRWLockShared
0x1800116a3  mov     eax, dword ptr [rsp+48h+var_18+4]
0x1800116a7  mov     cs:UmpoFinalSequenceCount, eax
0x1800116ad  mov     ecx, cs:UmpoSequenceCount
0x1800116b3  mov     eax, cs:UmpoFinalSequenceCount
0x1800116b9  cmp     eax, ecx
0x1800116bb  jz      short loc_1800116CD
0x1800116bd  mov     rcx, cs:UmpoAlpcEvent; hHandle
0x1800116c4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800116c7  call    cs:__imp_WaitForSingleObject
0x1800116cd  mov     eax, cs:UmpoFinalSequenceCount
0x1800116d3  cmp     eax, dword ptr [rsp+48h+var_18+4]
0x1800116d7  jz      short loc_1800116DE
0x1800116d9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800116de  mov     rcx, rsi; SRWLock
0x1800116e1  call    cs:__imp_AcquireSRWLockExclusive
0x1800116e7  call    cs:__imp_GetCurrentThreadId
0x1800116ed  mov     rbx, cs:UmpoAlpcPoPort
0x1800116f4  mov     rcx, rsi; SRWLock
0x1800116f7  mov     cs:UmpoAlpcPoPortLockThread, eax
0x1800116fd  mov     cs:UmpoAlpcPoPort, rdi
0x180011704  test    eax, eax
0x180011706  jz      short loc_180011716
0x180011708  mov     cs:UmpoAlpcPoPortLockThread, edi
0x18001170e  call    cs:__imp_ReleaseSRWLockExclusive
0x180011714  jmp     short loc_18001171C
0x180011716  call    cs:__imp_ReleaseSRWLockShared
0x18001171c  mov     rcx, cs:UmpoAlpcCompletion
0x180011723  call    cs:__imp_TpWaitForAlpcCompletion
0x180011729  mov     rcx, rbx; hObject
0x18001172c  call    UmpoAlpcReleaseResources
0x180011731  cmp     cs:UmpoAlpcPoPort, rdi
0x180011738  jz      short loc_18001173F
0x18001173a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001173f  cmp     cs:UmpoAlpcEvent, rdi
0x180011746  jz      short loc_18001174D
0x180011748  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001174d  cmp     cs:UmpoAlpcPoPortLockThread, edi
0x180011753  jz      short loc_18001175A
0x180011755  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001175a  cmp     cs:UmpoAlpcCompletion, rdi
0x180011761  jz      short loc_180011768
0x180011763  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011768  mov     rbx, [rsp+48h+arg_0]
0x18001176d  mov     rsi, [rsp+48h+arg_8]
0x180011772  mov     cs:UmpoFinalSequenceCount, edi
0x180011778  mov     cs:UmpoSequenceCount, 1
0x180011782  add     rsp, 40h
0x180011786  pop     rdi
0x180011787  retn
```
