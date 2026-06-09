# LUAGetElevatedToken

- ea: `0x180011f0c`
- end: `0x18001201f`
- name: `LUAGetElevatedToken`
- size: `275`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007dd8`

## callees

- `0x180011f0c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180011f67`
- `ntdll!NtQueryInformationToken` at `0x180011f99`
- `ntdll!NtQueryInformationToken` at `0x18001200a`
- `ntdll!NtQueryInformationToken` at `0x180011f67`
- `ntdll!NtQueryInformationToken` at `0x180011f99`
- `ntdll!NtQueryInformationToken` at `0x18001200a`
- `ntdll!NtDuplicateToken` at `0x180011fea`
- `ntdll!NtDuplicateToken` at `0x180011fea`

## pseudocode

```c
__int64 __fastcall LUAGetElevatedToken(HANDLE TokenHandle, PHANDLE NewTokenHandle)
{
  NTSTATUS v4; // ecx
  void *v6; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  int TokenInformation; // [rsp+98h] [rbp+28h] BYREF
  ULONG ReturnLength; // [rsp+A0h] [rbp+30h] BYREF
  int v10; // [rsp+A8h] [rbp+38h] BYREF

  *NewTokenHandle = 0;
  ReturnLength = 0;
  v10 = 0;
  TokenInformation = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v4 >= 0 )
  {
    if ( TokenInformation == 2 )
    {
LABEL_6:
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      return (unsigned int)NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, NewTokenHandle);
    }
    if ( TokenInformation == 1 )
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength);
      if ( v4 >= 0 && v10 )
        goto LABEL_6;
    }
    else
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenLinkedToken, &v6, 8u, &ReturnLength);
      if ( v4 >= 0 )
        *NewTokenHandle = v6;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011f0c  push    rbp
0x180011f0e  push    rbx
0x180011f0f  push    rdi
0x180011f10  mov     rbp, rsp
0x180011f13  sub     rsp, 70h
0x180011f17  xorps   xmm0, xmm0
0x180011f1a  mov     qword ptr [rdx], 0
0x180011f21  mov     r9d, 4; TokenInformationLength
0x180011f27  mov     [rbp+arg_10], 0
0x180011f2e  mov     rdi, rdx
0x180011f31  mov     [rbp+arg_18], 0
0x180011f38  lea     rax, [rbp+arg_10]
0x180011f3c  mov     [rbp+TokenInformation], 0
0x180011f43  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180011f47  mov     [rbp+var_40], 0
0x180011f4f  lea     edx, [r9+0Eh]; TokenInformationClass
0x180011f53  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180011f58  mov     rbx, rcx
0x180011f5b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180011f5f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180011f63  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180011f67  call    cs:__imp_NtQueryInformationToken
0x180011f6d  mov     ecx, eax
0x180011f6f  test    eax, eax
0x180011f71  js      short loc_180011FF2
0x180011f73  cmp     [rbp+TokenInformation], 2
0x180011f77  jz      short loc_180011FAB
0x180011f79  cmp     [rbp+TokenInformation], 1
0x180011f7d  lea     rax, [rbp+arg_10]
0x180011f81  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180011f86  mov     rcx, rbx; TokenHandle
0x180011f89  jnz     short loc_180011FFC
0x180011f8b  mov     r9d, 4; TokenInformationLength
0x180011f91  lea     r8, [rbp+arg_18]; TokenInformation
0x180011f95  lea     edx, [r9+10h]; TokenInformationClass
0x180011f99  call    cs:__imp_NtQueryInformationToken
0x180011f9f  mov     ecx, eax
0x180011fa1  test    eax, eax
0x180011fa3  js      short loc_180011FF2
0x180011fa5  cmp     [rbp+arg_18], 0
0x180011fa9  jz      short loc_180011FF2
0x180011fab  xorps   xmm0, xmm0
0x180011fae  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x180011fb3  xor     r9d, r9d; EffectiveOnly
0x180011fb6  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180011fbd  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180011fc1  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180011fc9  xor     edx, edx; DesiredAccess
0x180011fcb  mov     [rbp+ObjectAttributes.Attributes], 0
0x180011fd2  mov     rcx, rbx; ExistingTokenHandle
0x180011fd5  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180011fdd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180011fe2  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180011fea  call    cs:__imp_NtDuplicateToken
0x180011ff0  mov     ecx, eax
0x180011ff2  mov     eax, ecx
0x180011ff4  add     rsp, 70h
0x180011ff8  pop     rdi
0x180011ff9  pop     rbx
0x180011ffa  pop     rbp
0x180011ffb  retn
0x180011ffc  mov     r9d, 8; TokenInformationLength
0x180012002  lea     r8, [rbp+var_40]; TokenInformation
0x180012006  lea     edx, [r9+0Bh]; TokenInformationClass
0x18001200a  call    cs:__imp_NtQueryInformationToken
0x180012010  mov     ecx, eax
0x180012012  test    eax, eax
0x180012014  js      short loc_180011FF2
0x180012016  mov     rax, [rbp+var_40]
0x18001201a  mov     [rdi], rax
0x18001201d  jmp     short loc_180011FF2
```
