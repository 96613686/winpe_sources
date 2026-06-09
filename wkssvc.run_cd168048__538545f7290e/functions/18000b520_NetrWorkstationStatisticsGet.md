# NetrWorkstationStatisticsGet

- ea: `0x18000b520`
- end: `0x18000b6ff`
- name: `NetrWorkstationStatisticsGet`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800081b0`
- `0x18000b520`
- `0x18000b710`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18000b5c9`
- `ntdll!RtlAdjustPrivilege` at `0x18000b5c9`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000b63e`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000b63e`
- `ntdll!RtlInitUnicodeString` at `0x18000b578`
- `ntdll!RtlInitUnicodeString` at `0x18000b593`
- `ntdll!RtlInitUnicodeString` at `0x18000b5ab`
- `ntdll!RtlInitUnicodeString` at `0x18000b578`
- `ntdll!RtlInitUnicodeString` at `0x18000b593`
- `ntdll!RtlInitUnicodeString` at `0x18000b5ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b66c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b66c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b6ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b6ea`
- `RPCRT4!RpcImpersonateClient` at `0x18000b5d7`
- `RPCRT4!RpcImpersonateClient` at `0x18000b5d7`
- `RPCRT4!RpcRevertToSelf` at `0x18000b64c`
- `RPCRT4!RpcRevertToSelf` at `0x18000b64c`

## string_xrefs

- `0x18000b584`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWorkstationStatisticsGet(__int64 a1, __int64 a2, int a3, int a4, _QWORD *a5)
{
  PSECURITY_DESCRIPTOR SecurityDescriptor; // rbx
  NTSTATUS v6; // ebx
  HLOCAL v7; // rax
  void *v8; // rbx
  NTSTATUS StatisticsFromRedir; // edi
  unsigned __int8 GenerateOnClose[4]; // [rsp+60h] [rbp-48h] BYREF
  int AccessStatus; // [rsp+64h] [rbp-44h] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-40h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-28h] BYREF
  struct _UNICODE_STRING SubsystemName; // [rsp+90h] [rbp-18h] BYREF
  unsigned __int8 OldValue; // [rsp+C0h] [rbp+18h] BYREF

  if ( a3 )
    return 124;
  if ( a4 )
    return 87;
  SecurityDescriptor = ConfigurationInfoSd;
  OldValue = 0;
  GrantedAccess = 0;
  GenerateOnClose[0] = 0;
  AccessStatus = 0;
  SubsystemName = 0;
  DestinationString = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&SubsystemName, L"Workstation");
  RtlInitUnicodeString(&DestinationString, L"WkstaConfigurationInfo");
  RtlInitUnicodeString(&ObjectName, L"-");
  RtlAdjustPrivilege(0x15u, 1u, 0, &OldValue);
  if ( RpcImpersonateClient(0) )
    return 5;
  v6 = NtAccessCheckAndAuditAlarm(
         &SubsystemName,
         0,
         &DestinationString,
         &ObjectName,
         SecurityDescriptor,
         2u,
         &WsConfigInfoMapping,
         0,
         &GrantedAccess,
         &AccessStatus,
         GenerateOnClose);
  RpcRevertToSelf();
  if ( v6 < 0 || AccessStatus )
    return 5;
  v7 = LocalAlloc(0x40u, 0xD8u);
  v8 = v7;
  if ( !v7 )
    return 8;
  StatisticsFromRedir = GetStatisticsFromRedir(v7);
  if ( StatisticsFromRedir < 0 )
  {
    LocalFree(v8);
    return NetpNtStatusToApiStatus(StatisticsFromRedir);
  }
  else
  {
    *a5 = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x18000b520  mov     rax, rsp
0x18000b523  sub     rsp, 0A8h
0x18000b52a  test    r8d, r8d
0x18000b52d  jnz     loc_18000B6D2
0x18000b533  test    r9d, r9d
0x18000b536  jnz     loc_18000B6E0
0x18000b53c  mov     [rax+8], rbx
0x18000b540  lea     rdx, SourceName; "Workstation"
0x18000b547  mov     rbx, cs:ConfigurationInfoSd
0x18000b54e  lea     rcx, [rax-18h]; DestinationString
0x18000b552  xorps   xmm0, xmm0
0x18000b555  mov     [rax+10h], rsi
0x18000b559  xor     esi, esi
0x18000b55b  mov     [rax+18h], r9b
0x18000b55f  xorps   xmm1, xmm1
0x18000b562  mov     [rax-40h], esi
0x18000b565  mov     [rax-48h], sil
0x18000b569  mov     [rax-44h], esi
0x18000b56c  movups  xmmword ptr [rax-18h], xmm0
0x18000b570  movups  xmmword ptr [rax-28h], xmm1
0x18000b574  movups  xmmword ptr [rax-38h], xmm0
0x18000b578  call    cs:__imp_RtlInitUnicodeString
0x18000b57f  nop     dword ptr [rax+rax+00h]
0x18000b584  lea     rdx, aWkstaconfigura; "WkstaConfigurationInfo"
0x18000b58b  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x18000b593  call    cs:__imp_RtlInitUnicodeString
0x18000b59a  nop     dword ptr [rax+rax+00h]
0x18000b59f  lea     rdx, asc_18003DB90; "-"
0x18000b5a6  lea     rcx, [rsp+0A8h+ObjectName]; DestinationString
0x18000b5ab  call    cs:__imp_RtlInitUnicodeString
0x18000b5b2  nop     dword ptr [rax+rax+00h]
0x18000b5b7  lea     r9, [rsp+0A8h+OldValue]; OldValue
0x18000b5bf  xor     r8d, r8d; ForThread
0x18000b5c2  mov     dl, 1; NewValue
0x18000b5c4  mov     ecx, 15h; Privilege
0x18000b5c9  call    cs:__imp_RtlAdjustPrivilege
0x18000b5d0  nop     dword ptr [rax+rax+00h]
0x18000b5d5  xor     ecx, ecx; BindingHandle
0x18000b5d7  call    cs:__imp_RpcImpersonateClient
0x18000b5de  nop     dword ptr [rax+rax+00h]
0x18000b5e3  test    eax, eax
0x18000b5e5  jnz     loc_18000B6CB
0x18000b5eb  lea     rax, [rsp+0A8h+var_48]
0x18000b5f0  xor     edx, edx; HandleId
0x18000b5f2  mov     [rsp+0A8h+GenerateOnClose], rax; GenerateOnClose
0x18000b5f7  lea     r9, [rsp+0A8h+ObjectName]; ObjectName
0x18000b5fc  lea     rax, [rsp+0A8h+var_44]
0x18000b601  mov     [rsp+0A8h+AccessStatus], rax; AccessStatus
0x18000b606  lea     r8, [rsp+0A8h+DestinationString]; ObjectTypeName
0x18000b60e  lea     rax, [rsp+0A8h+var_40]
0x18000b613  mov     [rsp+0A8h+GrantedAccess], rax; GrantedAccess
0x18000b618  lea     rcx, [rsp+0A8h+SubsystemName]; SubsystemName
0x18000b620  mov     [rsp+0A8h+ObjectCreation], sil; ObjectCreation
0x18000b625  lea     rax, WsConfigInfoMapping
0x18000b62c  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x18000b631  mov     [rsp+0A8h+DesiredAccess], 2; DesiredAccess
0x18000b639  mov     [rsp+0A8h+SecurityDescriptor], rbx; SecurityDescriptor
0x18000b63e  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x18000b645  nop     dword ptr [rax+rax+00h]
0x18000b64a  mov     ebx, eax
0x18000b64c  call    cs:__imp_RpcRevertToSelf
0x18000b653  nop     dword ptr [rax+rax+00h]
0x18000b658  test    ebx, ebx
0x18000b65a  js      short loc_18000B6CB
0x18000b65c  cmp     [rsp+0A8h+var_44], esi
0x18000b660  jnz     short loc_18000B6CB
0x18000b662  mov     edx, 0D8h; uBytes
0x18000b667  mov     ecx, 40h ; '@'; uFlags
0x18000b66c  call    cs:__imp_LocalAlloc
0x18000b673  nop     dword ptr [rax+rax+00h]
0x18000b678  mov     rbx, rax
0x18000b67b  test    rax, rax
0x18000b67e  jz      short loc_18000B6C4
0x18000b680  mov     rcx, rax; OutputBuffer
0x18000b683  mov     [rsp+0A8h+var_8], rdi
0x18000b68b  call    GetStatisticsFromRedir
0x18000b690  mov     edi, eax
0x18000b692  test    eax, eax
0x18000b694  js      short loc_18000B6E7
0x18000b696  mov     rax, [rsp+0A8h+arg_20]
0x18000b69e  mov     [rax], rbx
0x18000b6a1  mov     eax, esi
0x18000b6a3  mov     rdi, [rsp+0A8h+var_8]
0x18000b6ab  mov     rbx, [rsp+0A8h+arg_0]
0x18000b6b3  mov     rsi, [rsp+0A8h+arg_8]
0x18000b6bb  add     rsp, 0A8h
0x18000b6c2  retn
0x18000b6c4  mov     eax, 8
0x18000b6c9  jmp     short loc_18000B6AB
0x18000b6cb  mov     eax, 5
0x18000b6d0  jmp     short loc_18000B6AB
0x18000b6d2  mov     eax, 7Ch ; '|'
0x18000b6d7  add     rsp, 0A8h
0x18000b6de  retn
0x18000b6e0  mov     eax, 57h ; 'W'
0x18000b6e5  jmp     short loc_18000B6BB
0x18000b6e7  mov     rcx, rbx; hMem
0x18000b6ea  call    cs:__imp_LocalFree
0x18000b6f1  nop     dword ptr [rax+rax+00h]
0x18000b6f6  mov     ecx, edi; Status
0x18000b6f8  call    NetpNtStatusToApiStatus
0x18000b6fd  jmp     short loc_18000B6A3
```
