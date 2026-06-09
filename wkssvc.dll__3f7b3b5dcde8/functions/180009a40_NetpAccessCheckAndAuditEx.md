# NetpAccessCheckAndAuditEx

- ea: `0x180009a40`
- end: `0x180009b6d`
- name: `NetpAccessCheckAndAuditEx`
- size: `301`
- prototype: `RPC_STATUS(__int64, __int64, const WCHAR *, ...)`
- caller_count: `27`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800214c0`
- `0x180021540`
- `0x180021ad0`
- `0x180021ff0`
- `0x180022460`
- `0x180027c90`
- `0x180027d80`
- `0x180027e70`
- `0x180028260`
- `0x1800283e0`
- `0x180028560`
- `0x180028700`
- `0x1800288a0`
- `0x180028990`
- `0x180028a80`
- `0x180028cb0`
- `0x180028ee0`
- `0x180028fd0`
- `0x1800290c0`
- `0x180029250`
- `0x1800293e0`
- `0x180029540`
- `0x180029e80`
- `0x180029f90`
- `0x18002a810`
- `0x18002aa00`
- `0x18002aaa0`

## callees

- `0x180009a40`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180009ac5`
- `ntdll!RtlAdjustPrivilege` at `0x180009ac5`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180009b3d`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x180009b3d`
- `ntdll!RtlInitUnicodeString` at `0x180009a8d`
- `ntdll!RtlInitUnicodeString` at `0x180009a9b`
- `ntdll!RtlInitUnicodeString` at `0x180009aad`
- `ntdll!RtlInitUnicodeString` at `0x180009a8d`
- `ntdll!RtlInitUnicodeString` at `0x180009a9b`
- `ntdll!RtlInitUnicodeString` at `0x180009aad`
- `RPCRT4!RpcImpersonateClient` at `0x180009acd`
- `RPCRT4!RpcImpersonateClient` at `0x180009acd`
- `RPCRT4!RpcRevertToSelf` at `0x180009b45`
- `RPCRT4!RpcRevertToSelf` at `0x180009b45`

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
0x180009a40  mov     r11, rsp
0x180009a43  mov     [r11+20h], r9
0x180009a47  mov     [r11+10h], rdx
0x180009a4b  mov     [r11+8], rcx
0x180009a4f  push    rbx
0x180009a50  sub     rsp, 0A0h
0x180009a57  xor     eax, eax
0x180009a59  mov     byte ptr [r11+20h], 0
0x180009a5e  xorps   xmm0, xmm0
0x180009a61  mov     [rsp+0A8h+var_48], eax
0x180009a65  xorps   xmm1, xmm1
0x180009a68  mov     [r11+10h], al
0x180009a6c  lea     rdx, SourceName; "Workstation"
0x180009a73  mov     [r11+8], eax
0x180009a77  lea     rcx, [r11-20h]; DestinationString
0x180009a7b  mov     rbx, r8
0x180009a7e  movups  xmmword ptr [r11-20h], xmm0
0x180009a83  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm1
0x180009a88  movups  xmmword ptr [rsp+0A8h+ObjectName.Length], xmm0
0x180009a8d  call    cs:__imp_RtlInitUnicodeString
0x180009a93  mov     rdx, rbx; SourceString
0x180009a96  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180009a9b  call    cs:__imp_RtlInitUnicodeString
0x180009aa1  lea     rdx, asc_18003AB90; "-"
0x180009aa8  lea     rcx, [rsp+0A8h+ObjectName]; DestinationString
0x180009aad  call    cs:__imp_RtlInitUnicodeString
0x180009ab3  lea     r9, [rsp+0A8h+OldValue]; OldValue
0x180009abb  xor     r8d, r8d; ForThread
0x180009abe  mov     dl, 1; NewValue
0x180009ac0  mov     ecx, 15h; Privilege
0x180009ac5  call    cs:__imp_RtlAdjustPrivilege
0x180009acb  xor     ecx, ecx; BindingHandle
0x180009acd  call    cs:__imp_RpcImpersonateClient
0x180009ad3  test    eax, eax
0x180009ad5  jnz     loc_180009B5D
0x180009adb  lea     rax, [rsp+0A8h+arg_8]
0x180009ae3  xor     edx, edx; HandleId
0x180009ae5  mov     [rsp+0A8h+GenerateOnClose], rax; GenerateOnClose
0x180009aea  lea     r9, [rsp+0A8h+ObjectName]; ObjectName
0x180009aef  lea     rax, [rsp+0A8h+arg_0]
0x180009af7  mov     [rsp+0A8h+AccessStatus], rax; AccessStatus
0x180009afc  lea     r8, [rsp+0A8h+DestinationString]; ObjectTypeName
0x180009b01  lea     rax, [rsp+0A8h+var_48]
0x180009b06  mov     [rsp+0A8h+GrantedAccess], rax; GrantedAccess
0x180009b0b  lea     rcx, [rsp+0A8h+SubsystemName]; SubsystemName
0x180009b13  mov     rax, [rsp+0A8h+arg_30]
0x180009b1b  mov     [rsp+0A8h+ObjectCreation], 0; ObjectCreation
0x180009b20  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x180009b25  mov     eax, dword ptr [rsp+0A8h+arg_28]
0x180009b2c  mov     [rsp+0A8h+DesiredAccess], eax; DesiredAccess
0x180009b30  mov     rax, [rsp+0A8h+arg_20]
0x180009b38  mov     [rsp+0A8h+SecurityDescriptor], rax; SecurityDescriptor
0x180009b3d  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x180009b43  mov     ebx, eax
0x180009b45  call    cs:__imp_RpcRevertToSelf
0x180009b4b  test    ebx, ebx
0x180009b4d  js      short loc_180009B66
0x180009b4f  mov     eax, [rsp+0A8h+arg_0]
0x180009b56  neg     eax
0x180009b58  sbb     eax, eax
0x180009b5a  and     eax, 5
0x180009b5d  add     rsp, 0A0h
0x180009b64  pop     rbx
0x180009b65  retn
0x180009b66  mov     eax, 5
0x180009b6b  jmp     short loc_180009B5D
```
