# UmpoRpcApplyPowerSetting

- ea: `0x180001580`
- end: `0x180001717`
- name: `UmpoRpcApplyPowerSetting`
- size: `407`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001580`
- `0x180002d8c`
- `0x1800034c0`
- `0x180004b80`
- `0x180008640`
- `0x18000f3dc`
- `0x180010070`
- `0x1800132cc`
- `0x18001337c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000160a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000160a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800015e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800015e1`
- `RPCRT4!RpcRevertToSelf` at `0x18000163f`
- `RPCRT4!RpcRevertToSelf` at `0x18000163f`
- `RPCRT4!RpcImpersonateClient` at `0x180001669`
- `RPCRT4!RpcImpersonateClient` at `0x180001669`

## pseudocode

```c
__int64 __fastcall UmpoRpcApplyPowerSetting(__int64 a1, int a2, __int64 a3)
{
  char v5; // di
  __int64 v6; // rdx
  __int64 v7; // rdx
  unsigned int ActiveScheme; // ebx
  __int64 v9; // r8
  __int64 v11; // rdx
  unsigned int SuspensionPowerMode; // eax
  _BYTE v13[8]; // [rsp+30h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-28h] BYREF
  UUID v15; // [rsp+48h] [rbp-18h] BYREF

  Uuid = 0;
  v15 = 0;
  if ( !UmpoIsClientLocal() )
    return 5;
  if ( !UmpoPowerPolicyInitialized )
    return 21;
  v5 = 0;
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoSchemeLock);
  ActiveScheme = UmpoGetActiveScheme(&v15, v6);
  if ( !ActiveScheme )
  {
    v13[0] = 0;
    if ( (_DWORD)UmpoOverlaySchemeSuspendMask )
    {
      ActiveScheme = UmpoInternalGetPowerModeSchema(v13, v7, v9);
      if ( ActiveScheme )
        goto LABEL_6;
      LOBYTE(v11) = v13[0];
      SuspensionPowerMode = UmpoInternalGetSuspensionPowerMode((int)UmpoOverlaySchemeSuspendMask, v11, &Uuid);
    }
    else
    {
      LOBYTE(v7) = UmpoOnAcPower;
      SuspensionPowerMode = UmpoGetActualOverlayScheme(&Uuid, v7);
    }
    ActiveScheme = SuspensionPowerMode;
    if ( !SuspensionPowerMode )
    {
      ActiveScheme = RpcImpersonateClient(0);
      if ( !ActiveScheme )
      {
        v5 = 1;
        ActiveScheme = UmpoSendKernelPowerPolicyNotification((unsigned int)&Uuid, (unsigned int)&v15, a2, 0, a3, 1);
        if ( !ActiveScheme )
          ActiveScheme = UmpoSendKernelPowerPolicyNotification((unsigned int)&Uuid, (unsigned int)&v15, a2, 0, a3, 0);
      }
    }
  }
LABEL_6:
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoSchemeLock);
  if ( v5 && RpcRevertToSelf() )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return ActiveScheme;
}

```

## disassembly

```asm
0x180001580  mov     [rsp-18h+arg_0], rbx
0x180001585  mov     [rsp-18h+arg_18], rsi
0x18000158a  push    rbp
0x18000158b  push    rdi
0x18000158c  push    r14
0x18000158e  mov     rbp, rsp
0x180001591  sub     rsp, 60h
0x180001595  mov     rax, cs:__security_cookie
0x18000159c  xor     rax, rsp
0x18000159f  mov     [rbp+var_8], rax
0x1800015a3  xorps   xmm0, xmm0
0x1800015a6  xorps   xmm1, xmm1
0x1800015a9  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1800015ad  mov     r14, r8
0x1800015b0  mov     rsi, rdx
0x1800015b3  movups  xmmword ptr [rbp+var_18.Data1], xmm1
0x1800015b7  call    UmpoIsClientLocal
0x1800015bc  test    eax, eax
0x1800015be  jz      short loc_180001638
0x1800015c0  mov     al, cs:UmpoPowerPolicyInitialized
0x1800015c6  test    al, al
0x1800015c8  jz      loc_1800016C2
0x1800015ce  xor     dil, dil
0x1800015d1  cmp     cs:byte_180024FA8, 1
0x1800015d8  jnz     short loc_180001657
0x1800015da  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x1800015e1  call    cs:__imp_EnterCriticalSection
0x1800015e7  lea     rcx, [rbp+var_18]; Uuid
0x1800015eb  call    UmpoGetActiveScheme
0x1800015f0  mov     ebx, eax
0x1800015f2  test    eax, eax
0x1800015f4  jz      loc_1800016CC
0x1800015fa  cmp     cs:byte_180024FA8, 1
0x180001601  jnz     short loc_180001650
0x180001603  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000160a  call    cs:__imp_LeaveCriticalSection
0x180001610  test    dil, dil
0x180001613  jnz     short loc_18000163F
0x180001615  mov     eax, ebx
0x180001617  mov     rcx, [rbp+var_8]
0x18000161b  xor     rcx, rsp; StackCookie
0x18000161e  call    __security_check_cookie
0x180001623  lea     r11, [rsp+60h+var_s0]
0x180001628  mov     rbx, [r11+20h]
0x18000162c  mov     rsi, [r11+38h]
0x180001630  mov     rsp, r11
0x180001633  pop     r14
0x180001635  pop     rdi
0x180001636  pop     rbp
0x180001637  retn
0x180001638  mov     ebx, 5
0x18000163d  jmp     short loc_180001615
0x18000163f  call    cs:__imp_RpcRevertToSelf
0x180001645  test    eax, eax
0x180001647  jz      short loc_180001615
0x180001649  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000164e  jmp     short loc_180001615
0x180001650  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001655  jmp     short loc_180001603
0x180001657  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000165c  jmp     loc_1800015DA
0x180001661  mov     ebx, eax
0x180001663  test    eax, eax
0x180001665  jnz     short loc_1800015FA
0x180001667  xor     ecx, ecx; BindingHandle
0x180001669  call    cs:__imp_RpcImpersonateClient
0x18000166f  mov     ebx, eax
0x180001671  test    eax, eax
0x180001673  jnz     short loc_1800015FA
0x180001675  mov     dil, 1
0x180001678  lea     rdx, [rbp+var_18]
0x18000167c  mov     [rsp+60h+var_38], dil
0x180001681  lea     rcx, [rbp+Uuid]
0x180001685  xor     r9d, r9d
0x180001688  mov     [rsp+60h+var_40], r14
0x18000168d  mov     r8, rsi
0x180001690  call    UmpoSendKernelPowerPolicyNotification
0x180001695  mov     ebx, eax
0x180001697  test    eax, eax
0x180001699  jnz     loc_1800015FA
0x18000169f  mov     [rsp+60h+var_38], al
0x1800016a3  lea     rdx, [rbp+var_18]
0x1800016a7  xor     r9d, r9d
0x1800016aa  mov     [rsp+60h+var_40], r14
0x1800016af  mov     r8, rsi
0x1800016b2  lea     rcx, [rbp+Uuid]
0x1800016b6  call    UmpoSendKernelPowerPolicyNotification
0x1800016bb  mov     ebx, eax
0x1800016bd  jmp     loc_1800015FA
0x1800016c2  mov     ebx, 15h
0x1800016c7  jmp     loc_180001615
0x1800016cc  cmp     cs:UmpoOverlaySchemeSuspendMask, 0
0x1800016d3  mov     [rbp+var_30], dil
0x1800016d7  jz      short loc_180001703
0x1800016d9  lea     rcx, [rbp+var_30]
0x1800016dd  call    UmpoInternalGetPowerModeSchema
0x1800016e2  mov     ebx, eax
0x1800016e4  test    eax, eax
0x1800016e6  jnz     loc_1800015FA
0x1800016ec  mov     dl, [rbp+var_30]
0x1800016ef  lea     r8, [rbp+Uuid]
0x1800016f3  mov     ecx, cs:UmpoOverlaySchemeSuspendMask
0x1800016f9  call    UmpoInternalGetSuspensionPowerMode
0x1800016fe  jmp     loc_180001661
0x180001703  mov     dl, cs:UmpoOnAcPower
0x180001709  lea     rcx, [rbp+Uuid]; Uuid
0x18000170d  call    UmpoGetActualOverlayScheme
0x180001712  jmp     loc_180001661
```
