# UmpoRpcGetUserConfiguredPowerMode

- ea: `0x18000d7c0`
- end: `0x18000d86e`
- name: `UmpoRpcGetUserConfiguredPowerMode`
- size: `174`
- prototype: `__int64 __fastcall(__int64, char, UUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002d8c`
- `0x1800036f0`
- `0x180004b80`
- `0x18000d7c0`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d856`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d856`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d82e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d82e`

## pseudocode

```c
__int64 __fastcall UmpoRpcGetUserConfiguredPowerMode(__int64 a1, char a2, UUID *a3)
{
  unsigned int ActualOverlayScheme; // ebx
  __int64 v6; // rdx

  if ( a3 )
  {
    if ( UmpoIsClientLocal() )
    {
      if ( UmpoPowerPolicyInitialized )
      {
        ActualOverlayScheme = UmpoRpcSettingAccessCheck(0, 0x1Bu, 0, 0x20019u);
        if ( !ActualOverlayScheme )
        {
          if ( byte_180024FA8 != 1 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          EnterCriticalSection(&UmpoSchemeLock);
          LOBYTE(v6) = a2;
          ActualOverlayScheme = UmpoGetActualOverlayScheme(a3, v6);
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
  return ActualOverlayScheme;
}

```

## disassembly

```asm
0x18000d7c0  mov     [rsp+arg_0], rbx
0x18000d7c5  mov     [rsp+arg_8], rsi
0x18000d7ca  push    rdi
0x18000d7cb  sub     rsp, 20h
0x18000d7cf  mov     rdi, r8
0x18000d7d2  mov     sil, dl
0x18000d7d5  test    r8, r8
0x18000d7d8  jnz     short loc_18000D7E0
0x18000d7da  lea     ebx, [r8+57h]
0x18000d7de  jmp     short loc_18000D85C
0x18000d7e0  call    UmpoIsClientLocal
0x18000d7e5  test    eax, eax
0x18000d7e7  jnz     short loc_18000D7EE
0x18000d7e9  lea     ebx, [rax+5]
0x18000d7ec  jmp     short loc_18000D85C
0x18000d7ee  mov     al, cs:UmpoPowerPolicyInitialized
0x18000d7f4  test    al, al
0x18000d7f6  jnz     short loc_18000D7FF
0x18000d7f8  mov     ebx, 15h
0x18000d7fd  jmp     short loc_18000D85C
0x18000d7ff  xor     r8d, r8d
0x18000d802  mov     r9d, 20019h
0x18000d808  xor     ecx, ecx
0x18000d80a  lea     edx, [r8+1Bh]
0x18000d80e  call    UmpoRpcSettingAccessCheck
0x18000d813  mov     ebx, eax
0x18000d815  test    eax, eax
0x18000d817  jnz     short loc_18000D85C
0x18000d819  cmp     cs:byte_180024FA8, 1
0x18000d820  jz      short loc_18000D827
0x18000d822  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d827  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000d82e  call    cs:__imp_EnterCriticalSection
0x18000d834  mov     dl, sil
0x18000d837  mov     rcx, rdi; Uuid
0x18000d83a  call    UmpoGetActualOverlayScheme
0x18000d83f  cmp     cs:byte_180024FA8, 1
0x18000d846  mov     ebx, eax
0x18000d848  jz      short loc_18000D84F
0x18000d84a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d84f  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000d856  call    cs:__imp_LeaveCriticalSection
0x18000d85c  mov     rsi, [rsp+28h+arg_8]
0x18000d861  mov     eax, ebx
0x18000d863  mov     rbx, [rsp+28h+arg_0]
0x18000d868  add     rsp, 20h
0x18000d86c  pop     rdi
0x18000d86d  retn
```
