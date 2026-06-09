# SsCheckAccess

- ea: `0x18000a460`
- end: `0x18000a5cd`
- name: `SsCheckAccess`
- size: `365`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, ACCESS_MASK)`
- caller_count: `39`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003f60`
- `0x180012f20`
- `0x180013830`
- `0x18001fdc4`
- `0x180020a50`
- `0x180020ae0`
- `0x180021740`
- `0x180021ad0`
- `0x180021b30`
- `0x180021c60`
- `0x180021d50`
- `0x180021de0`
- `0x180021ec0`
- `0x180023a50`
- `0x1800289a4`
- `0x180028d50`
- `0x180028db0`
- `0x180028ed0`
- `0x180028fc0`
- `0x18002949c`
- `0x180029884`
- `0x18002a390`
- `0x18002abf0`
- `0x18002ad50`
- `0x18002b1dc`
- `0x18002bd40`
- `0x18002be20`
- `0x18002bf00`
- `0x18002bfe0`
- `0x18002c110`
- `0x18002f04c`
- `0x18002f0fc`
- `0x180031c8c`
- `0x180032370`
- `0x1800323f0`
- `0x180032480`
- `0x1800329f0`
- `0x180032f00`
- `0x180033420`

## callees

- `0x18000a460`
- `0x180028c24`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000a4be`
- `ntdll!RtlInitUnicodeString` at `0x18000a4cc`
- `ntdll!RtlInitUnicodeString` at `0x18000a4da`
- `ntdll!RtlInitUnicodeString` at `0x18000a4be`
- `ntdll!RtlInitUnicodeString` at `0x18000a4cc`
- `ntdll!RtlInitUnicodeString` at `0x18000a4da`
- `ntdll!RtlAdjustPrivilege` at `0x18000a4f2`
- `ntdll!RtlAdjustPrivilege` at `0x18000a4f2`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000a553`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x18000a553`
- `RPCRT4!RpcImpersonateClient` at `0x18000a4fa`
- `RPCRT4!RpcImpersonateClient` at `0x18000a4fa`
- `RPCRT4!RpcRevertToSelf` at `0x18000a55b`
- `RPCRT4!RpcRevertToSelf` at `0x18000a55b`

## pseudocode

```c
__int64 __fastcall SsCheckAccess(__int64 a1, const WCHAR *a2, ACCESS_MASK a3)
{
  struct _GENERIC_MAPPING *GenericMapping; // rbp
  void *SecurityDescriptor; // rbx
  const WCHAR *v5; // rdi
  int v9; // edx
  unsigned int v10; // edi
  int v11; // r8d
  NTSTATUS v12; // ebx
  int AccessStatus; // [rsp+60h] [rbp-68h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-64h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+68h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-50h] BYREF
  struct _UNICODE_STRING SubsystemName; // [rsp+88h] [rbp-40h] BYREF
  unsigned __int8 OldValue; // [rsp+D0h] [rbp+8h] BYREF
  unsigned __int8 GenerateOnClose; // [rsp+E8h] [rbp+20h] BYREF

  GenericMapping = *(struct _GENERIC_MAPPING **)(a1 + 8);
  SecurityDescriptor = *(void **)(a1 + 16);
  v5 = *(const WCHAR **)a1;
  GrantedAccess = 0;
  GenerateOnClose = 0;
  AccessStatus = 0;
  OldValue = 0;
  SubsystemName = 0;
  DestinationString = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&SubsystemName, L"Server");
  RtlInitUnicodeString(&DestinationString, v5);
  RtlInitUnicodeString(&ObjectName, a2);
  RtlAdjustPrivilege(0x15u, 1u, 0, &OldValue);
  v10 = RpcImpersonateClient(0);
  if ( !v10 )
  {
    v12 = NtAccessCheckAndAuditAlarm(
            &SubsystemName,
            0,
            &DestinationString,
            &ObjectName,
            SecurityDescriptor,
            a3,
            GenericMapping,
            0,
            &GrantedAccess,
            &AccessStatus,
            &GenerateOnClose);
    RpcRevertToSelf();
    if ( v12 >= 0 && !AccessStatus )
      return 0;
    v10 = 5;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_SLl(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v11, *(_QWORD *)a1, a3, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18000a460  mov     rax, rsp
0x18000a463  mov     [rax+10h], rbx
0x18000a467  mov     [rax+18h], rbp
0x18000a46b  push    rsi
0x18000a46c  push    rdi
0x18000a46d  push    r12
0x18000a46f  push    r14
0x18000a471  push    r15
0x18000a473  sub     rsp, 0A0h
0x18000a47a  mov     rbp, [rcx+8]
0x18000a47e  xorps   xmm0, xmm0
0x18000a481  mov     rbx, [rcx+10h]
0x18000a485  xor     r12d, r12d
0x18000a488  mov     rdi, [rcx]
0x18000a48b  mov     rsi, rdx
0x18000a48e  mov     r15, rcx
0x18000a491  mov     [rax-64h], r12d
0x18000a495  xorps   xmm1, xmm1
0x18000a498  mov     [rax+20h], r12b
0x18000a49c  lea     rdx, SourceName; "Server"
0x18000a4a3  mov     [rax-68h], r12d
0x18000a4a7  lea     rcx, [rax-40h]; DestinationString
0x18000a4ab  mov     byte ptr [rax+8], 0
0x18000a4af  movups  xmmword ptr [rax-40h], xmm0
0x18000a4b3  mov     r14d, r8d
0x18000a4b6  movups  xmmword ptr [rax-50h], xmm1
0x18000a4ba  movups  xmmword ptr [rax-60h], xmm0
0x18000a4be  call    cs:__imp_RtlInitUnicodeString
0x18000a4c4  mov     rdx, rdi; SourceString
0x18000a4c7  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x18000a4cc  call    cs:__imp_RtlInitUnicodeString
0x18000a4d2  mov     rdx, rsi; SourceString
0x18000a4d5  lea     rcx, [rsp+0C8h+ObjectName]; DestinationString
0x18000a4da  call    cs:__imp_RtlInitUnicodeString
0x18000a4e0  lea     r9, [rsp+0C8h+OldValue]; OldValue
0x18000a4e8  xor     r8d, r8d; ForThread
0x18000a4eb  mov     dl, 1; NewValue
0x18000a4ed  mov     ecx, 15h; Privilege
0x18000a4f2  call    cs:__imp_RtlAdjustPrivilege
0x18000a4f8  xor     ecx, ecx; BindingHandle
0x18000a4fa  call    cs:__imp_RpcImpersonateClient
0x18000a500  mov     edi, eax
0x18000a502  test    eax, eax
0x18000a504  jnz     loc_18000A590
0x18000a50a  lea     rax, [rsp+0C8h+arg_18]
0x18000a512  xor     edx, edx; HandleId
0x18000a514  mov     [rsp+0C8h+GenerateOnClose], rax; GenerateOnClose
0x18000a519  lea     r9, [rsp+0C8h+ObjectName]; ObjectName
0x18000a51e  lea     rax, [rsp+0C8h+var_68]
0x18000a523  mov     [rsp+0C8h+AccessStatus], rax; AccessStatus
0x18000a528  lea     r8, [rsp+0C8h+DestinationString]; ObjectTypeName
0x18000a52d  lea     rax, [rsp+0C8h+var_64]
0x18000a532  mov     [rsp+0C8h+GrantedAccess], rax; GrantedAccess
0x18000a537  lea     rcx, [rsp+0C8h+SubsystemName]; SubsystemName
0x18000a53f  mov     [rsp+0C8h+ObjectCreation], r12b; ObjectCreation
0x18000a544  mov     [rsp+0C8h+GenericMapping], rbp; GenericMapping
0x18000a549  mov     [rsp+0C8h+DesiredAccess], r14d; DesiredAccess
0x18000a54e  mov     [rsp+0C8h+SecurityDescriptor], rbx; SecurityDescriptor
0x18000a553  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x18000a559  mov     ebx, eax
0x18000a55b  call    cs:__imp_RpcRevertToSelf
0x18000a561  test    ebx, ebx
0x18000a563  js      short loc_18000A58B
0x18000a565  cmp     [rsp+0C8h+var_68], r12d
0x18000a56a  jnz     short loc_18000A58B
0x18000a56c  mov     eax, r12d
0x18000a56f  lea     r11, [rsp+0C8h+var_28]
0x18000a577  mov     rbx, [r11+38h]
0x18000a57b  mov     rbp, [r11+40h]
0x18000a57f  mov     rsp, r11
0x18000a582  pop     r15
0x18000a584  pop     r14
0x18000a586  pop     r12
0x18000a588  pop     rdi
0x18000a589  pop     rsi
0x18000a58a  retn
0x18000a58b  mov     edi, 5
0x18000a590  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a597  lea     rax, WPP_GLOBAL_Control
0x18000a59e  cmp     rcx, rax
0x18000a5a1  jz      short loc_18000A5AC
0x18000a5a3  test    dword ptr [rcx+1Ch], 200h
0x18000a5aa  jnz     short loc_18000A5B0
0x18000a5ac  mov     eax, edi
0x18000a5ae  jmp     short loc_18000A56F
0x18000a5b0  cmp     byte ptr [rcx+19h], 1
0x18000a5b4  jb      short loc_18000A5AC
0x18000a5b6  mov     r9, [r15]
0x18000a5b9  mov     rcx, [rcx+10h]
0x18000a5bd  mov     [rsp+0C8h+DesiredAccess], edi
0x18000a5c1  mov     dword ptr [rsp+0C8h+SecurityDescriptor], r14d
0x18000a5c6  call    WPP_SF_SLl
0x18000a5cb  jmp     short loc_18000A5AC
```
