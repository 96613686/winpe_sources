# LUAGetStandardToken

- ea: `0x18006d368`
- end: `0x18006d487`
- name: `LUAGetStandardToken`
- size: `287`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180034000`

## callees

- `0x18006d324`
- `0x18006d368`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x18006d452`
- `ntdll!NtDuplicateToken` at `0x18006d452`
- `ntdll!NtQueryInformationToken` at `0x18006d3d1`
- `ntdll!NtQueryInformationToken` at `0x18006d403`
- `ntdll!NtQueryInformationToken` at `0x18006d42f`
- `ntdll!NtQueryInformationToken` at `0x18006d472`
- `ntdll!NtQueryInformationToken` at `0x18006d3d1`
- `ntdll!NtQueryInformationToken` at `0x18006d403`
- `ntdll!NtQueryInformationToken` at `0x18006d42f`
- `ntdll!NtQueryInformationToken` at `0x18006d472`

## pseudocode

```c
__int64 __fastcall LUAGetStandardToken(HANDLE TokenHandle, PHANDLE NewTokenHandle)
{
  NTSTATUS v5; // ecx
  TOKEN_TYPE TokenType; // [rsp+30h] [rbp-10h] BYREF
  void *v7; // [rsp+38h] [rbp-8h] BYREF
  ULONG ReturnLength; // [rsp+68h] [rbp+28h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+30h] BYREF
  int v10; // [rsp+78h] [rbp+38h] BYREF

  ReturnLength = 0;
  TokenType = 0;
  v10 = 0;
  TokenInformation = 0;
  v7 = 0;
  *NewTokenHandle = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    return 3221225474LL;
  v5 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v5 >= 0 )
  {
    if ( TokenInformation == 3 )
      goto LABEL_8;
    if ( TokenInformation != 1 )
    {
      v5 = NtQueryInformationToken(TokenHandle, TokenLinkedToken, &v7, 8u, &ReturnLength);
      if ( v5 >= 0 )
        *NewTokenHandle = v7;
      return (unsigned int)v5;
    }
    v5 = NtQueryInformationToken(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength);
    if ( v5 >= 0 && !v10 )
    {
LABEL_8:
      v5 = NtQueryInformationToken(TokenHandle, TokenType, &TokenType, 4u, &ReturnLength);
      if ( v5 >= 0 )
        return (unsigned int)NtDuplicateToken(TokenHandle, 0, 0, 0, TokenType, NewTokenHandle);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006d368  push    rbp
0x18006d36a  push    rbx
0x18006d36b  push    rdi
0x18006d36c  mov     rbp, rsp
0x18006d36f  sub     rsp, 40h
0x18006d373  mov     rdi, rdx
0x18006d376  mov     [rbp+arg_8], 0
0x18006d37d  mov     rbx, rcx
0x18006d380  mov     [rbp+TokenType], 0
0x18006d387  mov     [rbp+arg_18], 0
0x18006d38e  mov     [rbp+TokenInformation], 0
0x18006d395  mov     [rbp+var_8], 0
0x18006d39d  mov     qword ptr [rdx], 0
0x18006d3a4  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18006d3a9  test    eax, eax
0x18006d3ab  jnz     short loc_18006D3B7
0x18006d3ad  mov     eax, 0C0000002h
0x18006d3b2  jmp     loc_18006D45C
0x18006d3b7  mov     r9d, 4; TokenInformationLength
0x18006d3bd  lea     rax, [rbp+arg_8]
0x18006d3c1  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18006d3c5  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18006d3ca  mov     rcx, rbx; TokenHandle
0x18006d3cd  lea     edx, [r9+0Eh]; TokenInformationClass
0x18006d3d1  call    cs:__imp_NtQueryInformationToken
0x18006d3d7  mov     ecx, eax
0x18006d3d9  test    eax, eax
0x18006d3db  js      short loc_18006D45A
0x18006d3dd  cmp     [rbp+TokenInformation], 3
0x18006d3e1  jz      short loc_18006D415
0x18006d3e3  cmp     [rbp+TokenInformation], 1
0x18006d3e7  lea     rax, [rbp+arg_8]
0x18006d3eb  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18006d3f0  mov     rcx, rbx; TokenHandle
0x18006d3f3  jnz     short loc_18006D464
0x18006d3f5  mov     r9d, 4; TokenInformationLength
0x18006d3fb  lea     r8, [rbp+arg_18]; TokenInformation
0x18006d3ff  lea     edx, [r9+10h]; TokenInformationClass
0x18006d403  call    cs:__imp_NtQueryInformationToken
0x18006d409  mov     ecx, eax
0x18006d40b  test    eax, eax
0x18006d40d  js      short loc_18006D45A
0x18006d40f  cmp     [rbp+arg_18], 0
0x18006d413  jnz     short loc_18006D45A
0x18006d415  mov     r9d, 4; TokenInformationLength
0x18006d41b  lea     rax, [rbp+arg_8]
0x18006d41f  lea     r8, [rbp+TokenType]; TokenInformation
0x18006d423  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18006d428  mov     rcx, rbx; TokenHandle
0x18006d42b  lea     edx, [r9+4]; TokenInformationClass
0x18006d42f  call    cs:__imp_NtQueryInformationToken
0x18006d435  mov     ecx, eax
0x18006d437  test    eax, eax
0x18006d439  js      short loc_18006D45A
0x18006d43b  mov     eax, [rbp+TokenType]
0x18006d43e  xor     r9d, r9d; EffectiveOnly
0x18006d441  mov     [rsp+40h+NewTokenHandle], rdi; NewTokenHandle
0x18006d446  xor     r8d, r8d; ObjectAttributes
0x18006d449  xor     edx, edx; DesiredAccess
0x18006d44b  mov     dword ptr [rsp+40h+ReturnLength], eax; TokenType
0x18006d44f  mov     rcx, rbx; ExistingTokenHandle
0x18006d452  call    cs:__imp_NtDuplicateToken
0x18006d458  mov     ecx, eax
0x18006d45a  mov     eax, ecx
0x18006d45c  add     rsp, 40h
0x18006d460  pop     rdi
0x18006d461  pop     rbx
0x18006d462  pop     rbp
0x18006d463  retn
0x18006d464  mov     r9d, 8; TokenInformationLength
0x18006d46a  lea     r8, [rbp+var_8]; TokenInformation
0x18006d46e  lea     edx, [r9+0Bh]; TokenInformationClass
0x18006d472  call    cs:__imp_NtQueryInformationToken
0x18006d478  mov     ecx, eax
0x18006d47a  test    eax, eax
0x18006d47c  js      short loc_18006D45A
0x18006d47e  mov     rax, [rbp+var_8]
0x18006d482  mov     [rdi], rax
0x18006d485  jmp     short loc_18006D45A
```
