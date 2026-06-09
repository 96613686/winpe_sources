# WepCheckCallerPrivilege(ulong)

- ea: `0x180002148`
- end: `0x1800021f2`
- name: `?WepCheckCallerPrivilege@@YAJK@Z`
- size: `170`
- prototype: `__int64 __fastcall()`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002c40`
- `0x180002f90`

## callees

- `0x180002148`
- `0x180003be0`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x1800021b7`
- `ntdll!NtPrivilegeCheck` at `0x1800021b7`
- `ntdll!NtOpenThreadToken` at `0x18000217e`
- `ntdll!NtOpenThreadToken` at `0x18000217e`
- `ntdll!NtClose` at `0x1800021d3`
- `ntdll!NtClose` at `0x1800021d3`

## pseudocode

```c
__int64 __fastcall WepCheckCallerPrivilege()
{
  NTSTATUS v0; // ebx
  unsigned __int8 Result[8]; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  TokenHandle = 0;
  v0 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v0 >= 0 )
  {
    Result[0] = 0;
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Luid = (LUID)7LL;
    RequiredPrivileges.Privilege[0].Attributes = 0;
    v0 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
    if ( v0 >= 0 && !Result[0] )
      v0 = -1073741727;
    NtClose(TokenHandle);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180002148  mov     [rsp-8+arg_0], rbx
0x18000214d  push    rbp
0x18000214e  mov     rbp, rsp
0x180002151  sub     rsp, 50h
0x180002155  mov     rax, cs:__security_cookie
0x18000215c  xor     rax, rsp
0x18000215f  mov     [rbp+var_8], rax
0x180002163  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180002167  mov     [rbp+TokenHandle], 0
0x18000216f  mov     r8b, 1; OpenAsSelf
0x180002172  mov     edx, 8; DesiredAccess
0x180002177  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000217e  call    cs:__imp_NtOpenThreadToken
0x180002184  mov     ebx, eax
0x180002186  test    eax, eax
0x180002188  js      short loc_1800021D9
0x18000218a  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18000218e  lea     r8, [rbp+Result]; Result
0x180002192  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180002196  mov     [rbp+Result], 0
0x18000219a  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x1800021a1  mov     [rbp+RequiredPrivileges.Control], 1
0x1800021a8  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x1800021b0  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x1800021b7  call    cs:__imp_NtPrivilegeCheck
0x1800021bd  mov     ebx, eax
0x1800021bf  test    eax, eax
0x1800021c1  js      short loc_1800021CF
0x1800021c3  cmp     [rbp+Result], 0
0x1800021c7  mov     eax, 0C0000061h
0x1800021cc  cmovz   ebx, eax
0x1800021cf  mov     rcx, [rbp+TokenHandle]; Handle
0x1800021d3  call    cs:__imp_NtClose
0x1800021d9  mov     eax, ebx
0x1800021db  mov     rcx, [rbp+var_8]
0x1800021df  xor     rcx, rsp; StackCookie
0x1800021e2  call    __security_check_cookie
0x1800021e7  mov     rbx, [rsp+50h+arg_0]
0x1800021ec  add     rsp, 50h
0x1800021f0  pop     rbp
0x1800021f1  retn
```
