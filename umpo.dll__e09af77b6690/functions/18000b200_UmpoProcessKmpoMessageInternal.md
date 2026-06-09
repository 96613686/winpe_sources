# UmpoProcessKmpoMessageInternal

- ea: `0x18000b200`
- end: `0x18000b395`
- name: `UmpoProcessKmpoMessageInternal`
- size: `405`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b020`

## callees

- `0x18000b200`
- `0x18000b39c`
- `0x18000f3dc`

## import_xrefs

- `ntdll!NtClose` at `0x18000b2c2`
- `ntdll!NtClose` at `0x18000b2c2`
- `ntdll!NtAlpcCancelMessage` at `0x18000b32e`
- `ntdll!NtAlpcCancelMessage` at `0x18000b355`
- `ntdll!NtAlpcCancelMessage` at `0x18000b32e`
- `ntdll!NtAlpcCancelMessage` at `0x18000b355`
- `ntdll!DbgPrint` at `0x18000b31c`
- `ntdll!DbgPrint` at `0x18000b38a`
- `ntdll!DbgPrint` at `0x18000b31c`
- `ntdll!DbgPrint` at `0x18000b38a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b29a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b29a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b2f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b2f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2a0`

## pseudocode

```c
__int64 __fastcall UmpoProcessKmpoMessageInternal(__int64 a1, __int64 a2)
{
  int v3; // ebx
  int v4; // esi
  bool v6; // zf

  v3 = 0;
  v4 = (unsigned __int8)*(_WORD *)(a1 + 4);
  if ( v4 == 1 )
  {
    if ( *(_WORD *)(a1 + 2) >= 0x48u )
      goto LABEL_11;
    v3 = NtAlpcCancelMessage(UmpoAlpcPoPort, 0, a2);
    if ( v3 >= 0 )
      return (unsigned int)v3;
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v6 = (UmpoDebug & 1) == 0;
    goto LABEL_25;
  }
  if ( (unsigned __int8)*(_WORD *)(a1 + 4) == 3 )
  {
    if ( (*(_WORD *)(a1 + 4) & 0x2000) == 0 )
    {
      if ( *(_WORD *)(a1 + 2) < 0x48u )
        return (unsigned int)-1073741811;
LABEL_11:
      UmpoProcessPowerMessage();
      return (unsigned int)v3;
    }
    if ( (UmpoDebug & 2) != 0 )
      DbgPrint(
        "%s: ALPC message id=%x required continuation unexpectedly.Cancelling it.\n",
        "UmpoProcessKmpoMessageInternal",
        *(_DWORD *)(a2 + 20));
    v3 = NtAlpcCancelMessage(UmpoAlpcPoPort, 0, a2);
    if ( v3 < 0 )
    {
      v6 = (UmpoDebug & 1) == 0;
LABEL_25:
      if ( !v6 )
        DbgPrint(
          "%s: Unable to cancel ALPC message id=%x\n",
          "UmpoProcessKmpoMessageInternal",
          *(unsigned int *)(a2 + 20));
    }
  }
  else if ( (unsigned __int8)*(_WORD *)(a1 + 4) == 5 )
  {
    AcquireSRWLockExclusive(&UmpoAlpcPoPortLock);
    UmpoAlpcPoPortLockThread = GetCurrentThreadId();
    if ( v4 == 5 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( UmpoAlpcPoPort )
    {
      NtClose(UmpoAlpcPoPort);
      UmpoAlpcPoPort = 0;
      v3 = -1073741758;
    }
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
  else if ( (UmpoDebug & 2) != 0 )
  {
    DbgPrint(
      "%s: Unexpected ALPC message type - %x\n",
      "UmpoProcessKmpoMessageInternal",
      (unsigned __int8)*(_WORD *)(a1 + 4));
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b200  mov     [rsp+arg_0], rbx
0x18000b205  mov     [rsp+arg_8], rsi
0x18000b20a  push    rdi
0x18000b20b  sub     rsp, 20h
0x18000b20f  movzx   eax, word ptr [rcx+4]
0x18000b213  mov     rdi, rdx
0x18000b216  mov     edx, 0FFh
0x18000b21b  xor     ebx, ebx
0x18000b21d  and     ax, dx
0x18000b220  movzx   esi, ax
0x18000b223  mov     r9d, esi
0x18000b226  sub     r9d, 1
0x18000b22a  jz      short loc_18000B27E
0x18000b22c  sub     r9d, 2
0x18000b230  jnz     short loc_18000B25F
0x18000b232  mov     eax, 2000h
0x18000b237  test    [rcx+4], ax
0x18000b23b  jnz     loc_18000B300
0x18000b241  cmp     word ptr [rcx+2], 48h ; 'H'
0x18000b246  jnb     short loc_18000B289
0x18000b248  mov     ebx, 0C000000Dh
0x18000b24d  mov     rsi, [rsp+28h+arg_8]
0x18000b252  mov     eax, ebx
0x18000b254  mov     rbx, [rsp+28h+arg_0]
0x18000b259  add     rsp, 20h
0x18000b25d  pop     rdi
0x18000b25e  retn
0x18000b25f  cmp     r9d, 2
0x18000b263  jz      short loc_18000B290
0x18000b265  mov     eax, cs:UmpoDebug
0x18000b26b  test    al, 2
0x18000b26d  jz      short loc_18000B24D
0x18000b26f  mov     r8d, esi
0x18000b272  lea     rcx, aSUnexpectedAlp; "%s: Unexpected ALPC message type - %x\n"
0x18000b279  jmp     loc_18000B383
0x18000b27e  cmp     word ptr [rcx+2], 48h ; 'H'
0x18000b283  jb      loc_18000B349
0x18000b289  call    UmpoProcessPowerMessage
0x18000b28e  jmp     short loc_18000B24D
0x18000b290  lea     rdi, UmpoAlpcPoPortLock
0x18000b297  mov     rcx, rdi; SRWLock
0x18000b29a  call    cs:__imp_AcquireSRWLockExclusive
0x18000b2a0  call    cs:__imp_GetCurrentThreadId
0x18000b2a6  mov     cs:UmpoAlpcPoPortLockThread, eax
0x18000b2ac  cmp     esi, 5
0x18000b2af  jnz     short loc_18000B2B6
0x18000b2b1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b2b6  mov     rcx, cs:UmpoAlpcPoPort; Handle
0x18000b2bd  test    rcx, rcx
0x18000b2c0  jz      short loc_18000B2D4
0x18000b2c2  call    cs:__imp_NtClose
0x18000b2c8  mov     cs:UmpoAlpcPoPort, rbx
0x18000b2cf  mov     ebx, 0C0000042h
0x18000b2d4  cmp     cs:UmpoAlpcPoPortLockThread, 0
0x18000b2db  mov     rcx, rdi; SRWLock
0x18000b2de  jz      short loc_18000B2F5
0x18000b2e0  mov     cs:UmpoAlpcPoPortLockThread, 0
0x18000b2ea  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b2f0  jmp     loc_18000B24D
0x18000b2f5  call    cs:__imp_ReleaseSRWLockShared
0x18000b2fb  jmp     loc_18000B24D
0x18000b300  mov     eax, cs:UmpoDebug
0x18000b306  test    al, 2
0x18000b308  jz      short loc_18000B322
0x18000b30a  mov     r8d, [rdi+14h]
0x18000b30e  lea     rdx, aUmpoprocesskmp; "UmpoProcessKmpoMessageInternal"
0x18000b315  lea     rcx, aSAlpcMessageId; "%s: ALPC message id=%x required continu"...
0x18000b31c  call    cs:__imp_DbgPrint
0x18000b322  mov     rcx, cs:UmpoAlpcPoPort
0x18000b329  mov     r8, rdi
0x18000b32c  xor     edx, edx
0x18000b32e  call    cs:__imp_NtAlpcCancelMessage
0x18000b334  mov     ebx, eax
0x18000b336  test    eax, eax
0x18000b338  jns     loc_18000B24D
0x18000b33e  mov     ecx, cs:UmpoDebug
0x18000b344  test    cl, 1
0x18000b347  jmp     short loc_18000B372
0x18000b349  mov     rcx, cs:UmpoAlpcPoPort
0x18000b350  mov     r8, rdi
0x18000b353  xor     edx, edx
0x18000b355  call    cs:__imp_NtAlpcCancelMessage
0x18000b35b  mov     ebx, eax
0x18000b35d  test    eax, eax
0x18000b35f  jns     loc_18000B24D
0x18000b365  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b36a  mov     eax, cs:UmpoDebug
0x18000b370  test    al, 1
0x18000b372  jz      loc_18000B24D
0x18000b378  mov     r8d, [rdi+14h]
0x18000b37c  lea     rcx, aSUnableToCance; "%s: Unable to cancel ALPC message id=%x"...
0x18000b383  lea     rdx, aUmpoprocesskmp; "UmpoProcessKmpoMessageInternal"
0x18000b38a  call    cs:__imp_DbgPrint
0x18000b390  jmp     loc_18000B24D
```
