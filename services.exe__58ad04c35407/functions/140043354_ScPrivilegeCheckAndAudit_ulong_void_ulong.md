# ScPrivilegeCheckAndAudit(ulong,void *,ulong)

- ea: `0x140043354`
- end: `0x140043489`
- name: `?ScPrivilegeCheckAndAudit@@YAJKPEAXK@Z`
- size: `309`
- prototype: `int(unsigned int, void *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400432dc`
- `0x14006b060`

## callees

- `0x140043354`
- `0x1400575b0`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x140043392`
- `RPCRT4!I_RpcMapWin32Status` at `0x140043460`
- `RPCRT4!I_RpcMapWin32Status` at `0x140043392`
- `RPCRT4!I_RpcMapWin32Status` at `0x140043460`
- `RPCRT4!RpcImpersonateClient` at `0x14004338a`
- `RPCRT4!RpcImpersonateClient` at `0x14004338a`
- `RPCRT4!RpcRevertToSelf` at `0x140043458`
- `RPCRT4!RpcRevertToSelf` at `0x140043458`
- `ntdll!NtPrivilegeObjectAuditAlarm` at `0x14004343a`
- `ntdll!NtPrivilegeObjectAuditAlarm` at `0x14004343a`
- `ntdll!NtPrivilegeCheck` at `0x1400433fe`
- `ntdll!NtPrivilegeCheck` at `0x1400433fe`
- `ntdll!NtOpenThreadToken` at `0x1400433b5`
- `ntdll!NtOpenThreadToken` at `0x1400433b5`
- `ntdll!NtClose` at `0x140043452`
- `ntdll!NtClose` at `0x140043452`
- `ntdll!RtlInitUnicodeString` at `0x14004340f`
- `ntdll!RtlInitUnicodeString` at `0x14004340f`

## pseudocode

```c
__int64 __fastcall ScPrivilegeCheckAndAudit(int a1, unsigned __int64 a2, ACCESS_MASK a3)
{
  LUID v3; // rdi
  RPC_STATUS v6; // eax
  int v7; // ebx
  RPC_STATUS v8; // eax
  unsigned __int8 Result[8]; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+50h] [rbp-20h] BYREF

  v3 = (LUID)a1;
  TokenHandle = 0;
  v6 = RpcImpersonateClient(0);
  v7 = I_RpcMapWin32Status(v6);
  if ( v7 >= 0 )
  {
    v7 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( v7 >= 0 )
    {
      Result[0] = 0;
      RequiredPrivileges.PrivilegeCount = 1;
      DestinationString = 0;
      RequiredPrivileges.Control = 1;
      RequiredPrivileges.Privilege[0].Luid = v3;
      RequiredPrivileges.Privilege[0].Attributes = 0;
      NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
      RtlInitUnicodeString(&DestinationString, L"SC Manager");
      v7 = NtPrivilegeObjectAuditAlarm(
             &DestinationString,
             (PVOID)(a2 & -(__int64)(Result[0] != 0)),
             TokenHandle,
             a3,
             &RequiredPrivileges,
             Result[0]);
      if ( !Result[0] )
        v7 = -1073741727;
      NtClose(TokenHandle);
    }
    v8 = RpcRevertToSelf();
    I_RpcMapWin32Status(v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140043354  mov     [rsp-18h+arg_0], rbx
0x140043359  mov     [rsp-18h+arg_18], rsi
0x14004335e  push    rbp
0x14004335f  push    rdi
0x140043360  push    r14
0x140043362  mov     rbp, rsp
0x140043365  sub     rsp, 70h
0x140043369  mov     rax, cs:__security_cookie
0x140043370  xor     rax, rsp
0x140043373  mov     [rbp+var_8], rax
0x140043377  movsxd  rdi, ecx
0x14004337a  mov     r14d, r8d
0x14004337d  xor     ecx, ecx; BindingHandle
0x14004337f  mov     [rbp+TokenHandle], 0
0x140043387  mov     rsi, rdx
0x14004338a  call    cs:__imp_RpcImpersonateClient
0x140043390  mov     ecx, eax; Status
0x140043392  call    cs:__imp_I_RpcMapWin32Status
0x140043398  mov     ebx, eax
0x14004339a  test    eax, eax
0x14004339c  js      loc_140043466
0x1400433a2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1400433a6  mov     r8b, 1; OpenAsSelf
0x1400433a9  mov     edx, 8; DesiredAccess
0x1400433ae  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400433b5  call    cs:__imp_NtOpenThreadToken
0x1400433bb  mov     ebx, eax
0x1400433bd  test    eax, eax
0x1400433bf  js      loc_140043458
0x1400433c5  xorps   xmm0, xmm0
0x1400433c8  mov     [rbp+Result], 0
0x1400433cc  mov     rcx, rdi
0x1400433cf  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x1400433d6  shr     rcx, 20h
0x1400433da  lea     r8, [rbp+Result]; Result
0x1400433de  mov     [rbp+RequiredPrivileges.Privilege.Luid.HighPart], ecx
0x1400433e1  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1400433e5  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1400433e9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400433ed  mov     [rbp+RequiredPrivileges.Control], 1
0x1400433f4  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], edi
0x1400433f7  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x1400433fe  call    cs:__imp_NtPrivilegeCheck
0x140043404  lea     rdx, aScManager; "SC Manager"
0x14004340b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004340f  call    cs:__imp_RtlInitUnicodeString
0x140043415  mov     cl, [rbp+Result]
0x140043418  mov     r9d, r14d; DesiredAccess
0x14004341b  mov     r8, [rbp+TokenHandle]; ClientToken
0x14004341f  mov     al, cl
0x140043421  neg     al
0x140043423  mov     [rsp+70h+AccessGranted], cl; AccessGranted
0x140043427  lea     rax, [rbp+RequiredPrivileges]
0x14004342b  sbb     rdx, rdx
0x14004342e  mov     [rsp+70h+Privileges], rax; Privileges
0x140043433  and     rdx, rsi; HandleId
0x140043436  lea     rcx, [rbp+DestinationString]; SubsystemName
0x14004343a  call    cs:__imp_NtPrivilegeObjectAuditAlarm
0x140043440  cmp     [rbp+Result], 0
0x140043444  mov     ebx, eax
0x140043446  mov     rcx, [rbp+TokenHandle]; Handle
0x14004344a  mov     eax, 0C0000061h
0x14004344f  cmovz   ebx, eax
0x140043452  call    cs:__imp_NtClose
0x140043458  call    cs:__imp_RpcRevertToSelf
0x14004345e  mov     ecx, eax; Status
0x140043460  call    cs:__imp_I_RpcMapWin32Status
0x140043466  mov     eax, ebx
0x140043468  mov     rcx, [rbp+var_8]
0x14004346c  xor     rcx, rsp; StackCookie
0x14004346f  call    __security_check_cookie
0x140043474  lea     r11, [rsp+70h+var_s0]
0x140043479  mov     rbx, [r11+20h]
0x14004347d  mov     rsi, [r11+38h]
0x140043481  mov     rsp, r11
0x140043484  pop     r14
0x140043486  pop     rdi
0x140043487  pop     rbp
0x140043488  retn
```
