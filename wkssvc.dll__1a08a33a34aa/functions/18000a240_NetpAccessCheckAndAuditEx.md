# NetpAccessCheckAndAuditEx

- ea: `0x18000a240`
- end: `0x18000a398`
- name: `NetpAccessCheckAndAuditEx`
- size: `344`
- prototype: ``
- caller_count: `27`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022d50`
- `0x180022dd0`
- `0x1800233b0`
- `0x180023930`
- `0x180023dc0`
- `0x180029fc0`
- `0x18002a0b0`
- `0x18002a1a0`
- `0x18002a610`
- `0x18002a7a0`
- `0x18002a930`
- `0x18002aae0`
- `0x18002ac90`
- `0x18002ad80`
- `0x18002ae70`
- `0x18002b0d0`
- `0x18002b330`
- `0x18002b420`
- `0x18002b510`
- `0x18002b6c0`
- `0x18002b870`
- `0x18002b9f0`
- `0x18002c3b0`
- `0x18002c4c0`
- `0x18002ce00`
- `0x18002d000`
- `0x18002d0a0`

## callees

- `0x18000a240`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18000a2d7`
- `ntdll!RtlAdjustPrivilege` at `0x18000a2d7`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000a35b`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000a35b`
- `ntdll!RtlInitUnicodeString` at `0x18000a28d`
- `ntdll!RtlInitUnicodeString` at `0x18000a2a1`
- `ntdll!RtlInitUnicodeString` at `0x18000a2b9`
- `ntdll!RtlInitUnicodeString` at `0x18000a28d`
- `ntdll!RtlInitUnicodeString` at `0x18000a2a1`
- `ntdll!RtlInitUnicodeString` at `0x18000a2b9`
- `RPCRT4!RpcImpersonateClient` at `0x18000a2e5`
- `RPCRT4!RpcImpersonateClient` at `0x18000a2e5`
- `RPCRT4!RpcRevertToSelf` at `0x18000a369`
- `RPCRT4!RpcRevertToSelf` at `0x18000a369`

## pseudocode

```c
RPC_STATUS NetpAccessCheckAndAuditEx(__int64 a1, __int64 a2, const WCHAR *a3, ...)
{
  RPC_STATUS result; // eax
  NTSTATUS v5; // ebx
  DWORD GrantedAccess; // [rsp+60h] [rbp-48h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+68h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-30h] BYREF
  struct _UNICODE_STRING SubsystemName; // [rsp+88h] [rbp-20h] BYREF
  int AccessStatus; // [rsp+B0h] [rbp+8h] BYREF
  int v11; // [rsp+B4h] [rbp+Ch]
  __int64 GenerateOnClose; // [rsp+B8h] [rbp+10h] BYREF
  __int64 OldValue; // [rsp+C8h] [rbp+20h] BYREF
  va_list OldValuea; // [rsp+C8h] [rbp+20h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+D0h] [rbp+28h]
  __int64 DesiredAccess; // [rsp+D8h] [rbp+30h]
  PGENERIC_MAPPING GenericMapping; // [rsp+E0h] [rbp+38h]
  va_list va1; // [rsp+E8h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(OldValuea, a3);
  OldValue = va_arg(va1, _QWORD);
  SecurityDescriptor = va_arg(va1, PSECURITY_DESCRIPTOR);
  DesiredAccess = va_arg(va1, _QWORD);
  GenericMapping = va_arg(va1, PGENERIC_MAPPING);
  GenerateOnClose = a2;
  v11 = HIDWORD(a1);
  LOBYTE(OldValue) = 0;
  GrantedAccess = 0;
  LOBYTE(GenerateOnClose) = 0;
  AccessStatus = 0;
  SubsystemName = 0;
  DestinationString = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&SubsystemName, L"Workstation");
  RtlInitUnicodeString(&DestinationString, a3);
  RtlInitUnicodeString(&ObjectName, L"-");
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)OldValuea);
  result = RpcImpersonateClient(0);
  if ( !result )
  {
    v5 = NtAccessCheckAndAuditAlarm(
           &SubsystemName,
           0,
           &DestinationString,
           &ObjectName,
           SecurityDescriptor,
           DesiredAccess,
           GenericMapping,
           0,
           &GrantedAccess,
           &AccessStatus,
           (PBOOLEAN)&GenerateOnClose);
    RpcRevertToSelf();
    if ( v5 < 0 )
      return 5;
    else
      return AccessStatus != 0 ? 5 : 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a240  mov     r11, rsp
0x18000a243  mov     [r11+20h], r9
0x18000a247  mov     [r11+10h], rdx
0x18000a24b  mov     [r11+8], rcx
0x18000a24f  push    rbx
0x18000a250  sub     rsp, 0A0h
0x18000a257  xor     eax, eax
0x18000a259  mov     byte ptr [r11+20h], 0
0x18000a25e  xorps   xmm0, xmm0
0x18000a261  mov     [rsp+0A8h+var_48], eax
0x18000a265  xorps   xmm1, xmm1
0x18000a268  mov     [r11+10h], al
0x18000a26c  lea     rdx, SourceName; "Workstation"
0x18000a273  mov     [r11+8], eax
0x18000a277  lea     rcx, [r11-20h]; DestinationString
0x18000a27b  mov     rbx, r8
0x18000a27e  movups  xmmword ptr [r11-20h], xmm0
0x18000a283  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm1
0x18000a288  movups  xmmword ptr [rsp+0A8h+ObjectName.Length], xmm0
0x18000a28d  call    cs:__imp_RtlInitUnicodeString
0x18000a294  nop     dword ptr [rax+rax+00h]
0x18000a299  mov     rdx, rbx; SourceString
0x18000a29c  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x18000a2a1  call    cs:__imp_RtlInitUnicodeString
0x18000a2a8  nop     dword ptr [rax+rax+00h]
0x18000a2ad  lea     rdx, asc_18003DB90; "-"
0x18000a2b4  lea     rcx, [rsp+0A8h+ObjectName]; DestinationString
0x18000a2b9  call    cs:__imp_RtlInitUnicodeString
0x18000a2c0  nop     dword ptr [rax+rax+00h]
0x18000a2c5  lea     r9, [rsp+0A8h+OldValue]; OldValue
0x18000a2cd  xor     r8d, r8d; ForThread
0x18000a2d0  mov     dl, 1; NewValue
0x18000a2d2  mov     ecx, 15h; Privilege
0x18000a2d7  call    cs:__imp_RtlAdjustPrivilege
0x18000a2de  nop     dword ptr [rax+rax+00h]
0x18000a2e3  xor     ecx, ecx; BindingHandle
0x18000a2e5  call    cs:__imp_RpcImpersonateClient
0x18000a2ec  nop     dword ptr [rax+rax+00h]
0x18000a2f1  test    eax, eax
0x18000a2f3  jnz     loc_18000A387
0x18000a2f9  lea     rax, [rsp+0A8h+arg_8]
0x18000a301  xor     edx, edx; HandleId
0x18000a303  mov     [rsp+0A8h+GenerateOnClose], rax; GenerateOnClose
0x18000a308  lea     r9, [rsp+0A8h+ObjectName]; ObjectName
0x18000a30d  lea     rax, [rsp+0A8h+arg_0]
0x18000a315  mov     [rsp+0A8h+AccessStatus], rax; AccessStatus
0x18000a31a  lea     r8, [rsp+0A8h+DestinationString]; ObjectTypeName
0x18000a31f  lea     rax, [rsp+0A8h+var_48]
0x18000a324  mov     [rsp+0A8h+GrantedAccess], rax; GrantedAccess
0x18000a329  lea     rcx, [rsp+0A8h+SubsystemName]; SubsystemName
0x18000a331  mov     rax, [rsp+0A8h+arg_30]
0x18000a339  mov     [rsp+0A8h+ObjectCreation], 0; ObjectCreation
0x18000a33e  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x18000a343  mov     eax, dword ptr [rsp+0A8h+arg_28]
0x18000a34a  mov     [rsp+0A8h+DesiredAccess], eax; DesiredAccess
0x18000a34e  mov     rax, [rsp+0A8h+arg_20]
0x18000a356  mov     [rsp+0A8h+SecurityDescriptor], rax; SecurityDescriptor
0x18000a35b  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x18000a362  nop     dword ptr [rax+rax+00h]
0x18000a367  mov     ebx, eax
0x18000a369  call    cs:__imp_RpcRevertToSelf
0x18000a370  nop     dword ptr [rax+rax+00h]
0x18000a375  test    ebx, ebx
0x18000a377  js      short loc_18000A391
0x18000a379  mov     eax, [rsp+0A8h+arg_0]
0x18000a380  neg     eax
0x18000a382  sbb     eax, eax
0x18000a384  and     eax, 5
0x18000a387  add     rsp, 0A0h
0x18000a38e  pop     rbx
0x18000a38f  retn
0x18000a391  mov     eax, 5
0x18000a396  jmp     short loc_18000A387
```
