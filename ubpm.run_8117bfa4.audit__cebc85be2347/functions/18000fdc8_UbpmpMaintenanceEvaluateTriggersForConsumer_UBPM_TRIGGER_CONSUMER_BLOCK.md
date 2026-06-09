# UbpmpMaintenanceEvaluateTriggersForConsumer(_UBPM_TRIGGER_CONSUMER_BLOCK *)

- ea: `0x18000fdc8`
- end: `0x18000fe8b`
- name: `?UbpmpMaintenanceEvaluateTriggersForConsumer@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@@Z`
- size: `195`
- prototype: `unsigned int __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011640`

## callees

- `0x18000fdc8`
- `0x18000fea0`
- `0x180015e20`
- `0x18001af64`
- `0x180036d44`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000fde0`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000fde0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000fe0f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000fe0f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000fdf7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000fdf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe1b`

## pseudocode

```c
__int64 __fastcall UbpmpMaintenanceEvaluateTriggersForConsumer(struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // ebx
  PVOID v7; // rcx

  *((_BYTE *)a1 + 41) &= ~1u;
  RtlReleaseSRWLockShared((char *)a1 + 208);
  *((_DWORD *)a1 + 14) = 0;
  RtlReleaseSRWLockExclusive((char *)a1 + 48);
  UbpmUnsubscribeFromBrokerNotifications((__int64)a1, v2, v3, v4);
  RtlAcquireSRWLockExclusive((char *)a1 + 48);
  *((_DWORD *)a1 + 14) = GetCurrentThreadId();
  v5 = UbpmSubscribeToBrokerNotifications((__int64)a1);
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids,
        *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
        v5);
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  }
  else
  {
    *((_BYTE *)a1 + 41) |= 1u;
  }
  return v5;
}

```

## disassembly

```asm
0x18000fdc8  mov     [rsp+arg_0], rbx
0x18000fdcd  push    rdi
0x18000fdce  sub     rsp, 30h
0x18000fdd2  and     byte ptr [rcx+29h], 0FEh
0x18000fdd6  mov     rdi, rcx
0x18000fdd9  add     rcx, 0D0h
0x18000fde0  call    cs:__imp_RtlReleaseSRWLockShared
0x18000fde7  nop     dword ptr [rax+rax+00h]
0x18000fdec  lea     rcx, [rdi+30h]
0x18000fdf0  mov     dword ptr [rdi+38h], 0
0x18000fdf7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000fdfe  nop     dword ptr [rax+rax+00h]
0x18000fe03  mov     rcx, rdi
0x18000fe06  call    UbpmUnsubscribeFromBrokerNotifications
0x18000fe0b  lea     rcx, [rdi+30h]
0x18000fe0f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000fe16  nop     dword ptr [rax+rax+00h]
0x18000fe1b  call    cs:__imp_GetCurrentThreadId
0x18000fe22  nop     dword ptr [rax+rax+00h]
0x18000fe27  mov     rcx, rdi
0x18000fe2a  mov     [rdi+38h], eax
0x18000fe2d  call    UbpmSubscribeToBrokerNotifications
0x18000fe32  mov     ebx, eax
0x18000fe34  test    eax, eax
0x18000fe36  jnz     short loc_18000FE4A
0x18000fe38  or      byte ptr [rdi+29h], 1
0x18000fe3c  mov     eax, ebx
0x18000fe3e  mov     rbx, [rsp+38h+arg_0]
0x18000fe43  add     rsp, 30h
0x18000fe47  pop     rdi
0x18000fe48  retn
0x18000fe4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe51  lea     rax, WPP_GLOBAL_Control
0x18000fe58  cmp     rcx, rax
0x18000fe5b  jz      short loc_18000FE84
0x18000fe5d  test    byte ptr [rcx+1Ch], 1
0x18000fe61  jz      short loc_18000FE84
0x18000fe63  mov     r9, [rdi+18h]
0x18000fe67  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x18000fe6e  mov     rcx, [rcx+10h]
0x18000fe72  mov     edx, 15h
0x18000fe77  mov     [rsp+38h+var_18], ebx
0x18000fe7b  mov     r9, [r9+8]
0x18000fe7f  call    WPP_SF_Sd
0x18000fe84  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000fe89  jmp     short loc_18000FE3C
```
