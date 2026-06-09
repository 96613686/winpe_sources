# UmpoApplyAllPowerRequestOverride

- ea: `0x18000c534`
- end: `0x18000c64f`
- name: `UmpoApplyAllPowerRequestOverride`
- size: `283`
- prototype: `void __fastcall(char, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e5b4`
- `0x1800146c0`
- `0x180016a3c`

## callees

- `0x180004170`
- `0x180004380`
- `0x18000c534`
- `0x18000f3dc`
- `0x180010946`
- `0x180016b40`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000c618`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000c618`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c648`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c558`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c558`

## pseudocode

```c
void __fastcall UmpoApplyAllPowerRequestOverride(char a1, char a2)
{
  BOOLEAN i; // dl
  int v5; // ecx
  int v6; // eax
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  _DWORD v9[22]; // [rsp+20h] [rbp-58h] BYREF
  int v10; // [rsp+88h] [rbp+10h] BYREF

  if ( byte_180024AC8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&PowerRequestLock);
  v10 = 0;
  memset_0(v9, 0, 0x48u);
  v9[0] = 8;
  if ( a2 )
  {
    if ( (unsigned int)UmpopCacheRegistryPowerRequestOverride(0) )
      UmpoDriverOverrideCacheOn = 0;
    if ( (unsigned int)UmpopCacheRegistryPowerRequestOverride(1) )
      UmpoProcessOverrideCacheOn = 0;
    if ( (unsigned int)UmpopCacheRegistryPowerRequestOverride(2) )
      UmpoServiceOverrideCacheOn = 0;
  }
  for ( i = 1; ; i = 0 )
  {
    v7 = RtlEnumerateGenericTableAvl(&UmpoPowerRequestTable, i);
    v8 = v7;
    if ( !v7 )
      break;
    if ( (unsigned __int8)UmpopCheckPowerRequestOverride((__int64)v7, &v10) || a1 )
    {
      v5 = UmpoPowerRequestOverridePolicyMask | v10;
      v6 = v8[8];
      v10 = v5;
      v8[7] = v5;
      v9[4] = v5;
      v9[2] = v6;
      UmpoAlpcSendPowerMessage(v9, 0x48u);
    }
  }
  if ( byte_180024AC8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&PowerRequestLock);
}

```

## disassembly

```asm
0x18000c534  mov     [rsp+arg_0], rbx
0x18000c539  push    rdi
0x18000c53a  sub     rsp, 70h
0x18000c53e  cmp     cs:byte_180024AC8, 1
0x18000c545  mov     bl, dl
0x18000c547  mov     dil, cl
0x18000c54a  jz      short loc_18000C551
0x18000c54c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c551  lea     rcx, PowerRequestLock; lpCriticalSection
0x18000c558  call    cs:__imp_EnterCriticalSection
0x18000c55e  xor     edx, edx; Val
0x18000c560  mov     [rsp+78h+arg_8], 0
0x18000c56b  lea     rcx, [rsp+78h+var_58]; void *
0x18000c570  lea     r8d, [rdx+48h]; Size
0x18000c574  call    memset_0
0x18000c579  mov     [rsp+78h+var_58], 8
0x18000c581  test    bl, bl
0x18000c583  jz      short loc_18000C5C1
0x18000c585  xor     ecx, ecx
0x18000c587  call    UmpopCacheRegistryPowerRequestOverride
0x18000c58c  test    eax, eax
0x18000c58e  jz      short loc_18000C597
0x18000c590  mov     cs:UmpoDriverOverrideCacheOn, 0
0x18000c597  mov     ecx, 1
0x18000c59c  call    UmpopCacheRegistryPowerRequestOverride
0x18000c5a1  test    eax, eax
0x18000c5a3  jz      short loc_18000C5AC
0x18000c5a5  mov     cs:UmpoProcessOverrideCacheOn, 0
0x18000c5ac  mov     ecx, 2
0x18000c5b1  call    UmpopCacheRegistryPowerRequestOverride
0x18000c5b6  test    eax, eax
0x18000c5b8  jz      short loc_18000C5C1
0x18000c5ba  mov     cs:UmpoServiceOverrideCacheOn, 0
0x18000c5c1  mov     dl, 1
0x18000c5c3  jmp     short loc_18000C611
0x18000c5c5  lea     rdx, [rsp+78h+arg_8]
0x18000c5cd  mov     rcx, rbx
0x18000c5d0  call    UmpopCheckPowerRequestOverride
0x18000c5d5  test    al, al
0x18000c5d7  jnz     short loc_18000C5DE
0x18000c5d9  test    dil, dil
0x18000c5dc  jz      short loc_18000C60F
0x18000c5de  mov     ecx, [rsp+78h+arg_8]
0x18000c5e5  mov     edx, 48h ; 'H'
0x18000c5ea  or      ecx, cs:UmpoPowerRequestOverridePolicyMask
0x18000c5f0  mov     eax, [rbx+20h]
0x18000c5f3  mov     [rsp+78h+arg_8], ecx
0x18000c5fa  mov     [rbx+1Ch], ecx
0x18000c5fd  mov     [rsp+78h+var_48], ecx
0x18000c601  lea     rcx, [rsp+78h+var_58]
0x18000c606  mov     [rsp+78h+var_50], eax
0x18000c60a  call    UmpoAlpcSendPowerMessage
0x18000c60f  xor     edx, edx; Restart
0x18000c611  lea     rcx, UmpoPowerRequestTable; Table
0x18000c618  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18000c61e  mov     rbx, rax
0x18000c621  test    rax, rax
0x18000c624  jnz     short loc_18000C5C5
0x18000c626  cmp     cs:byte_180024AC8, 1
0x18000c62d  jz      short loc_18000C634
0x18000c62f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000c634  lea     rcx, PowerRequestLock
0x18000c63b  mov     rbx, [rsp+78h+arg_0]
0x18000c643  add     rsp, 70h
0x18000c647  pop     rdi
0x18000c648  jmp     cs:__imp_LeaveCriticalSection
```
