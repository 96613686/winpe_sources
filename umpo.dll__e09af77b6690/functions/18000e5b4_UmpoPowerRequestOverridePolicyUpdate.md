# UmpoPowerRequestOverridePolicyUpdate

- ea: `0x18000e5b4`
- end: `0x18000e62b`
- name: `UmpoPowerRequestOverridePolicyUpdate`
- size: `119`
- prototype: `void __fastcall(char, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a680`

## callees

- `0x18000c534`
- `0x18000e5b4`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e612`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e5dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e5dd`

## pseudocode

```c
void __fastcall UmpoPowerRequestOverridePolicyUpdate(char a1, __int64 a2)
{
  int v2; // edi
  int v3; // ebx
  int v4; // ebx

  v2 = *(_DWORD *)(a2 + 20);
  v3 = 1 << a1;
  if ( byte_180024AC8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&PowerRequestLock);
  if ( v2 )
    v4 = UmpoPowerRequestOverridePolicyMask & ~v3;
  else
    v4 = UmpoPowerRequestOverridePolicyMask | v3;
  UmpoPowerRequestOverridePolicyMask = v4;
  if ( byte_180024AC8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&PowerRequestLock);
  UmpoApplyAllPowerRequestOverride(1, 0);
}

```

## disassembly

```asm
0x18000e5b4  mov     [rsp+arg_0], rbx
0x18000e5b9  push    rdi
0x18000e5ba  sub     rsp, 20h
0x18000e5be  mov     edi, [rdx+14h]
0x18000e5c1  mov     ebx, 1
0x18000e5c6  shl     ebx, cl
0x18000e5c8  cmp     cs:byte_180024AC8, 1
0x18000e5cf  jz      short loc_18000E5D6
0x18000e5d1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e5d6  lea     rcx, PowerRequestLock; lpCriticalSection
0x18000e5dd  call    cs:__imp_EnterCriticalSection
0x18000e5e3  test    edi, edi
0x18000e5e5  jnz     short loc_18000E5EF
0x18000e5e7  or      ebx, cs:UmpoPowerRequestOverridePolicyMask
0x18000e5ed  jmp     short loc_18000E5F7
0x18000e5ef  not     ebx
0x18000e5f1  and     ebx, cs:UmpoPowerRequestOverridePolicyMask
0x18000e5f7  cmp     cs:byte_180024AC8, 1
0x18000e5fe  mov     cs:UmpoPowerRequestOverridePolicyMask, ebx
0x18000e604  jz      short loc_18000E60B
0x18000e606  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e60b  lea     rcx, PowerRequestLock; lpCriticalSection
0x18000e612  call    cs:__imp_LeaveCriticalSection
0x18000e618  xor     edx, edx
0x18000e61a  mov     cl, 1
0x18000e61c  mov     rbx, [rsp+28h+arg_0]
0x18000e621  add     rsp, 20h
0x18000e625  pop     rdi
0x18000e626  jmp     UmpoApplyAllPowerRequestOverride
```
