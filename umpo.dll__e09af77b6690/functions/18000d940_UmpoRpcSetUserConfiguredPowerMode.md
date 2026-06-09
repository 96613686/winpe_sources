# UmpoRpcSetUserConfiguredPowerMode

- ea: `0x18000d940`
- end: `0x18000d9e7`
- name: `UmpoRpcSetUserConfiguredPowerMode`
- size: `167`
- prototype: `__int64 __fastcall(__int64, char, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800036f0`
- `0x180004b80`
- `0x18000d940`
- `0x18000d9f0`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d9ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d9ab`

## pseudocode

```c
__int64 __fastcall UmpoRpcSetUserConfiguredPowerMode(__int64 a1, char a2, __int64 a3)
{
  DWORD v6; // ebx
  __int64 v7; // r8

  if ( a3 )
  {
    if ( UmpoIsClientLocal() )
    {
      if ( UmpoPowerPolicyInitialized )
      {
        v6 = UmpoRpcSettingAccessCheck(0, 0x1Bu, 0, 0x20006u);
        if ( !v6 )
        {
          if ( byte_180024FA8 != 1 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          EnterCriticalSection(&UmpoSchemeLock);
          LOBYTE(v7) = a2;
          v6 = UmpoSetUserConfiguredOverlayScheme(a1, a3, v7);
          if ( byte_180024FA8 != 1 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          LeaveCriticalSection(&UmpoSchemeLock);
        }
      }
      else
      {
        return 21;
      }
    }
    else
    {
      return 5;
    }
  }
  else
  {
    return 87;
  }
  return v6;
}

```

## disassembly

```asm
0x18000d940  push    rbx
0x18000d942  push    rbp
0x18000d943  push    rsi
0x18000d944  push    rdi
0x18000d945  sub     rsp, 28h
0x18000d949  mov     rdi, r8
0x18000d94c  mov     sil, dl
0x18000d94f  mov     rbp, rcx
0x18000d952  test    r8, r8
0x18000d955  jnz     short loc_18000D95D
0x18000d957  lea     ebx, [r8+57h]
0x18000d95b  jmp     short loc_18000D9DC
0x18000d95d  call    UmpoIsClientLocal
0x18000d962  test    eax, eax
0x18000d964  jnz     short loc_18000D96B
0x18000d966  lea     ebx, [rax+5]
0x18000d969  jmp     short loc_18000D9DC
0x18000d96b  mov     al, cs:UmpoPowerPolicyInitialized
0x18000d971  test    al, al
0x18000d973  jnz     short loc_18000D97C
0x18000d975  mov     ebx, 15h
0x18000d97a  jmp     short loc_18000D9DC
0x18000d97c  xor     r8d, r8d
0x18000d97f  mov     r9d, 20006h
0x18000d985  xor     ecx, ecx
0x18000d987  lea     edx, [r8+1Bh]
0x18000d98b  call    UmpoRpcSettingAccessCheck
0x18000d990  mov     ebx, eax
0x18000d992  test    eax, eax
0x18000d994  jnz     short loc_18000D9DC
0x18000d996  cmp     cs:byte_180024FA8, 1
0x18000d99d  jz      short loc_18000D9A4
0x18000d99f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d9a4  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000d9ab  call    cs:__imp_EnterCriticalSection
0x18000d9b1  mov     r8b, sil
0x18000d9b4  mov     rdx, rdi
0x18000d9b7  mov     rcx, rbp
0x18000d9ba  call    UmpoSetUserConfiguredOverlayScheme
0x18000d9bf  cmp     cs:byte_180024FA8, 1
0x18000d9c6  mov     ebx, eax
0x18000d9c8  jz      short loc_18000D9CF
0x18000d9ca  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d9cf  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000d9d6  call    cs:__imp_LeaveCriticalSection
0x18000d9dc  mov     eax, ebx
0x18000d9de  add     rsp, 28h
0x18000d9e2  pop     rdi
0x18000d9e3  pop     rsi
0x18000d9e4  pop     rbp
0x18000d9e5  pop     rbx
0x18000d9e6  retn
```
