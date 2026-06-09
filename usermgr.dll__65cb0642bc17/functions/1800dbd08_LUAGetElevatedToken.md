# LUAGetElevatedToken

- ea: `0x1800dbd08`
- end: `0x1800dbe1b`
- name: `LUAGetElevatedToken`
- size: `275`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003a3c0`

## callees

- `0x1800dbd08`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x1800dbde6`
- `ntdll!NtDuplicateToken` at `0x1800dbde6`
- `ntdll!NtQueryInformationToken` at `0x1800dbd63`
- `ntdll!NtQueryInformationToken` at `0x1800dbd95`
- `ntdll!NtQueryInformationToken` at `0x1800dbe06`
- `ntdll!NtQueryInformationToken` at `0x1800dbd63`
- `ntdll!NtQueryInformationToken` at `0x1800dbd95`
- `ntdll!NtQueryInformationToken` at `0x1800dbe06`

## pseudocode

```c
__int64 __fastcall LUAGetElevatedToken(HANDLE TokenHandle, PHANDLE NewTokenHandle)
{
  NTSTATUS v4; // ecx
  void *v6; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
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
0x1800dbd08  push    rbp
0x1800dbd0a  push    rbx
0x1800dbd0b  push    rdi
0x1800dbd0c  mov     rbp, rsp
0x1800dbd0f  sub     rsp, 70h
0x1800dbd13  xorps   xmm0, xmm0
0x1800dbd16  mov     qword ptr [rdx], 0
0x1800dbd1d  mov     r9d, 4; TokenInformationLength
0x1800dbd23  mov     [rbp+arg_10], 0
0x1800dbd2a  mov     rdi, rdx
0x1800dbd2d  mov     [rbp+arg_18], 0
0x1800dbd34  lea     rax, [rbp+arg_10]
0x1800dbd38  mov     [rbp+TokenInformation], 0
0x1800dbd3f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800dbd43  mov     [rbp+var_40], 0
0x1800dbd4b  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800dbd4f  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800dbd54  mov     rbx, rcx
0x1800dbd57  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800dbd5b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800dbd5f  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800dbd63  call    cs:__imp_NtQueryInformationToken
0x1800dbd69  mov     ecx, eax
0x1800dbd6b  test    eax, eax
0x1800dbd6d  js      short loc_1800DBDEE
0x1800dbd6f  cmp     [rbp+TokenInformation], 2
0x1800dbd73  jz      short loc_1800DBDA7
0x1800dbd75  cmp     [rbp+TokenInformation], 1
0x1800dbd79  lea     rax, [rbp+arg_10]
0x1800dbd7d  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800dbd82  mov     rcx, rbx; TokenHandle
0x1800dbd85  jnz     short loc_1800DBDF8
0x1800dbd87  mov     r9d, 4; TokenInformationLength
0x1800dbd8d  lea     r8, [rbp+arg_18]; TokenInformation
0x1800dbd91  lea     edx, [r9+10h]; TokenInformationClass
0x1800dbd95  call    cs:__imp_NtQueryInformationToken
0x1800dbd9b  mov     ecx, eax
0x1800dbd9d  test    eax, eax
0x1800dbd9f  js      short loc_1800DBDEE
0x1800dbda1  cmp     [rbp+arg_18], 0
0x1800dbda5  jz      short loc_1800DBDEE
0x1800dbda7  xorps   xmm0, xmm0
0x1800dbdaa  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x1800dbdaf  xor     r9d, r9d; EffectiveOnly
0x1800dbdb2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800dbdb9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800dbdbd  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800dbdc5  xor     edx, edx; DesiredAccess
0x1800dbdc7  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800dbdce  mov     rcx, rbx; ExistingTokenHandle
0x1800dbdd1  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1800dbdd9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800dbdde  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x1800dbde6  call    cs:__imp_NtDuplicateToken
0x1800dbdec  mov     ecx, eax
0x1800dbdee  mov     eax, ecx
0x1800dbdf0  add     rsp, 70h
0x1800dbdf4  pop     rdi
0x1800dbdf5  pop     rbx
0x1800dbdf6  pop     rbp
0x1800dbdf7  retn
0x1800dbdf8  mov     r9d, 8; TokenInformationLength
0x1800dbdfe  lea     r8, [rbp+var_40]; TokenInformation
0x1800dbe02  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800dbe06  call    cs:__imp_NtQueryInformationToken
0x1800dbe0c  mov     ecx, eax
0x1800dbe0e  test    eax, eax
0x1800dbe10  js      short loc_1800DBDEE
0x1800dbe12  mov     rax, [rbp+var_40]
0x1800dbe16  mov     [rdi], rax
0x1800dbe19  jmp     short loc_1800DBDEE
```
