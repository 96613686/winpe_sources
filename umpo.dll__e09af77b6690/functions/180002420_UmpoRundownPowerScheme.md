# UmpoRundownPowerScheme

- ea: `0x180002420`
- end: `0x18000251d`
- name: `UmpoRundownPowerScheme`
- size: `253`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008c80`

## callees

- `0x180002420`
- `0x1800034c0`
- `0x1800061d0`
- `0x18000886c`
- `0x18000f3dc`
- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180002475`
- `ntdll!EtwEventWrite` at `0x1800024f2`
- `ntdll!EtwEventWrite` at `0x180002475`
- `ntdll!EtwEventWrite` at `0x1800024f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000248f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000248f`

## pseudocode

```c
void __fastcall UmpoRundownPowerScheme(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  int PlatformRole; // [rsp+20h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-28h] BYREF
  UUID *p_PlatformRole; // [rsp+38h] [rbp-18h] BYREF
  __int64 v7; // [rsp+40h] [rbp-10h]

  Uuid = 0;
  PlatformRole = UmpoInternalGetPlatformRole(a1, a2, a3);
  v7 = 4;
  p_PlatformRole = (UUID *)&PlatformRole;
  EtwEventWrite(UmpoProviderHandle, UMPO_EVT_RUNDOWN_PLATFORM_ROLE, 1, &p_PlatformRole);
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoSchemeLock);
  if ( !(unsigned int)UmpoGetActiveScheme(&Uuid, v3) )
  {
    p_PlatformRole = &Uuid;
    v7 = 16;
    EtwEventWrite(UmpoProviderHandle, UMPO_EVT_RUNDOWN_ACTIVE_POWER_SCHEME, 1, &p_PlatformRole);
    UmpoEnumeratePowerSettings(
      0,
      (__int64 (__fastcall *)(UUID *, UUID *, __int64))&UmpoRundownPowerSettingCallback,
      (__int64)&Uuid);
  }
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoSchemeLock);
}

```

## disassembly

```asm
0x180002420  push    rbp
0x180002422  mov     rbp, rsp
0x180002425  sub     rsp, 50h
0x180002429  mov     rax, cs:__security_cookie
0x180002430  xor     rax, rsp
0x180002433  mov     [rbp+var_8], rax
0x180002437  xorps   xmm0, xmm0
0x18000243a  mov     [rbp+var_30], 0
0x180002441  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180002445  call    UmpoInternalGetPlatformRole
0x18000244a  mov     rcx, cs:UmpoProviderHandle
0x180002451  lea     r9, [rbp+var_18]
0x180002455  mov     [rbp+var_30], eax
0x180002458  lea     rdx, UMPO_EVT_RUNDOWN_PLATFORM_ROLE
0x18000245f  lea     rax, [rbp+var_30]
0x180002463  mov     [rbp+var_10], 4
0x18000246b  mov     r8d, 1
0x180002471  mov     [rbp+var_18], rax
0x180002475  call    cs:__imp_EtwEventWrite
0x18000247b  cmp     cs:byte_180024FA8, 1
0x180002482  jnz     loc_180002513
0x180002488  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000248f  call    cs:__imp_EnterCriticalSection
0x180002495  lea     rcx, [rbp+Uuid]; Uuid
0x180002499  call    UmpoGetActiveScheme
0x18000249e  test    eax, eax
0x1800024a0  jz      short loc_1800024CA
0x1800024a2  cmp     cs:byte_180024FA8, 1
0x1800024a9  jnz     short loc_18000250C
0x1800024ab  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x1800024b2  call    cs:__imp_LeaveCriticalSection
0x1800024b8  mov     rcx, [rbp+var_8]
0x1800024bc  xor     rcx, rsp; StackCookie
0x1800024bf  call    __security_check_cookie
0x1800024c4  add     rsp, 50h
0x1800024c8  pop     rbp
0x1800024c9  retn
0x1800024ca  mov     rcx, cs:UmpoProviderHandle
0x1800024d1  lea     rax, [rbp+Uuid]
0x1800024d5  lea     r9, [rbp+var_18]
0x1800024d9  mov     [rbp+var_18], rax
0x1800024dd  mov     r8d, 1
0x1800024e3  mov     [rbp+var_10], 10h
0x1800024eb  lea     rdx, UMPO_EVT_RUNDOWN_ACTIVE_POWER_SCHEME
0x1800024f2  call    cs:__imp_EtwEventWrite
0x1800024f8  lea     r8, [rbp+Uuid]
0x1800024fc  xor     ecx, ecx
0x1800024fe  lea     rdx, UmpoRundownPowerSettingCallback
0x180002505  call    UmpoEnumeratePowerSettings
0x18000250a  jmp     short loc_1800024A2
0x18000250c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002511  jmp     short loc_1800024AB
0x180002513  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002518  jmp     loc_180002488
```
