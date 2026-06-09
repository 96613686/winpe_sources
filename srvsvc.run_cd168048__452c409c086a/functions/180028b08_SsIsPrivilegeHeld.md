# SsIsPrivilegeHeld

- ea: `0x180028b08`
- end: `0x180028ba3`
- name: `SsIsPrivilegeHeld`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022ff0`

## callees

- `0x18001deb0`
- `0x180028b08`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180028b6e`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180028b6e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028b43`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028b43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b84`

## pseudocode

```c
BOOL __fastcall SsIsPrivilegeHeld(void *a1)
{
  int v1; // ebx
  BOOL result; // eax
  WINBOOL pfResult; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  TokenHandle = 0;
  v1 = 1;
  pfResult = 0;
  result = OpenThreadToken(a1, 8u, 1, &TokenHandle);
  if ( result )
  {
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.PrivilegeCount = 1;
    *(_QWORD *)&RequiredPrivileges.Privilege[0].Luid.HighPart = 0;
    RequiredPrivileges.Privilege[0].Luid.LowPart = 10;
    if ( !PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult) || !pfResult )
      v1 = 0;
    CloseHandle(TokenHandle);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180028b08  mov     [rsp-8+arg_8], rbx
0x180028b0d  push    rbp
0x180028b0e  mov     rbp, rsp
0x180028b11  sub     rsp, 50h
0x180028b15  mov     rax, cs:__security_cookie
0x180028b1c  xor     rax, rsp
0x180028b1f  mov     [rbp+var_8], rax
0x180028b23  xor     eax, eax
0x180028b25  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180028b29  xorps   xmm0, xmm0
0x180028b2c  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x180028b2f  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x180028b33  mov     [rbp+TokenHandle], rax
0x180028b37  lea     ebx, [rax+1]
0x180028b3a  mov     [rbp+pfResult], eax
0x180028b3d  mov     r8d, ebx; OpenAsSelf
0x180028b40  lea     edx, [rax+8]; DesiredAccess
0x180028b43  call    cs:__imp_OpenThreadToken
0x180028b49  test    eax, eax
0x180028b4b  jz      short loc_180028B8C
0x180028b4d  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180028b51  lea     r8, [rbp+pfResult]; pfResult
0x180028b55  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180028b59  mov     [rbp+RequiredPrivileges.Control], ebx
0x180028b5c  mov     [rbp+RequiredPrivileges.PrivilegeCount], ebx
0x180028b5f  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.HighPart], 0
0x180028b67  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 0Ah
0x180028b6e  call    cs:__imp_PrivilegeCheck
0x180028b74  test    eax, eax
0x180028b76  jz      short loc_180028B7E
0x180028b78  cmp     [rbp+pfResult], 0
0x180028b7c  jnz     short loc_180028B80
0x180028b7e  xor     ebx, ebx
0x180028b80  mov     rcx, [rbp+TokenHandle]; hObject
0x180028b84  call    cs:__imp_CloseHandle
0x180028b8a  mov     eax, ebx
0x180028b8c  mov     rcx, [rbp+var_8]
0x180028b90  xor     rcx, rsp; StackCookie
0x180028b93  call    __security_check_cookie
0x180028b98  mov     rbx, [rsp+50h+arg_8]
0x180028b9d  add     rsp, 50h
0x180028ba1  pop     rbp
0x180028ba2  retn
```
