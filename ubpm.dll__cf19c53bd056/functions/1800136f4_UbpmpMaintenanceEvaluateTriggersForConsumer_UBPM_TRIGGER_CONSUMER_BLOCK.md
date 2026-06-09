# UbpmpMaintenanceEvaluateTriggersForConsumer(_UBPM_TRIGGER_CONSUMER_BLOCK *)

- ea: `0x1800136f4`
- end: `0x18001379e`
- name: `?UbpmpMaintenanceEvaluateTriggersForConsumer@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@@Z`
- size: `170`
- prototype: `unsigned int __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a8b0`

## callees

- `0x180013510`
- `0x1800136f4`
- `0x180013b60`
- `0x18001e9f4`
- `0x18003488c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18001370c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001370c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001372f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001372f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001371d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001371d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013735`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013735`

## pseudocode

```c
__int64 __fastcall UbpmpMaintenanceEvaluateTriggersForConsumer(struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1)
{
  unsigned int v2; // ebx
  PVOID v4; // rcx

  *((_BYTE *)a1 + 41) &= ~1u;
  RtlReleaseSRWLockShared((char *)a1 + 208);
  *((_DWORD *)a1 + 14) = 0;
  RtlReleaseSRWLockExclusive((char *)a1 + 48);
  UbpmUnsubscribeFromBrokerNotifications((__int64)a1);
  RtlAcquireSRWLockExclusive((char *)a1 + 48);
  *((_DWORD *)a1 + 14) = GetCurrentThreadId();
  v2 = UbpmSubscribeToBrokerNotifications((__int64)a1);
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids,
        *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
        v2);
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  }
  else
  {
    *((_BYTE *)a1 + 41) |= 1u;
  }
  return v2;
}

```

## disassembly

```asm
0x1800136f4  mov     [rsp+arg_0], rbx
0x1800136f9  push    rdi
0x1800136fa  sub     rsp, 30h
0x1800136fe  and     byte ptr [rcx+29h], 0FEh
0x180013702  mov     rdi, rcx
0x180013705  add     rcx, 0D0h
0x18001370c  call    cs:__imp_RtlReleaseSRWLockShared
0x180013712  lea     rcx, [rdi+30h]
0x180013716  mov     dword ptr [rdi+38h], 0
0x18001371d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180013723  mov     rcx, rdi
0x180013726  call    UbpmUnsubscribeFromBrokerNotifications
0x18001372b  lea     rcx, [rdi+30h]
0x18001372f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180013735  call    cs:__imp_GetCurrentThreadId
0x18001373b  mov     rcx, rdi
0x18001373e  mov     [rdi+38h], eax
0x180013741  call    UbpmSubscribeToBrokerNotifications
0x180013746  mov     ebx, eax
0x180013748  test    eax, eax
0x18001374a  jnz     short loc_18001375D
0x18001374c  or      byte ptr [rdi+29h], 1
0x180013750  mov     eax, ebx
0x180013752  mov     rbx, [rsp+38h+arg_0]
0x180013757  add     rsp, 30h
0x18001375b  pop     rdi
0x18001375c  retn
0x18001375d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013764  lea     rax, WPP_GLOBAL_Control
0x18001376b  cmp     rcx, rax
0x18001376e  jz      short loc_180013797
0x180013770  test    byte ptr [rcx+1Ch], 1
0x180013774  jz      short loc_180013797
0x180013776  mov     r9, [rdi+18h]
0x18001377a  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x180013781  mov     rcx, [rcx+10h]
0x180013785  mov     edx, 15h
0x18001378a  mov     [rsp+38h+var_18], ebx
0x18001378e  mov     r9, [r9+8]
0x180013792  call    WPP_SF_Sd
0x180013797  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001379c  jmp     short loc_180013750
```
