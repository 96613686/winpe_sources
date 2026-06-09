# LUAGetElevatedToken

- ea: `0x180034258`
- end: `0x18003436b`
- name: `LUAGetElevatedToken`
- size: `275`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ff0c`
- `0x1800300c0`

## callees

- `0x180034258`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800342b3`
- `ntdll!NtQueryInformationToken` at `0x1800342e5`
- `ntdll!NtQueryInformationToken` at `0x180034356`
- `ntdll!NtQueryInformationToken` at `0x1800342b3`
- `ntdll!NtQueryInformationToken` at `0x1800342e5`
- `ntdll!NtQueryInformationToken` at `0x180034356`
- `ntdll!NtDuplicateToken` at `0x180034336`
- `ntdll!NtDuplicateToken` at `0x180034336`

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
0x180034258  push    rbp
0x18003425a  push    rbx
0x18003425b  push    rdi
0x18003425c  mov     rbp, rsp
0x18003425f  sub     rsp, 70h
0x180034263  xorps   xmm0, xmm0
0x180034266  mov     qword ptr [rdx], 0
0x18003426d  mov     r9d, 4; TokenInformationLength
0x180034273  mov     [rbp+arg_10], 0
0x18003427a  mov     rdi, rdx
0x18003427d  mov     [rbp+arg_18], 0
0x180034284  lea     rax, [rbp+arg_10]
0x180034288  mov     [rbp+TokenInformation], 0
0x18003428f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180034293  mov     [rbp+var_40], 0
0x18003429b  lea     edx, [r9+0Eh]; TokenInformationClass
0x18003429f  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800342a4  mov     rbx, rcx
0x1800342a7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800342ab  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800342af  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800342b3  call    cs:__imp_NtQueryInformationToken
0x1800342b9  mov     ecx, eax
0x1800342bb  test    eax, eax
0x1800342bd  js      short loc_18003433E
0x1800342bf  cmp     [rbp+TokenInformation], 2
0x1800342c3  jz      short loc_1800342F7
0x1800342c5  cmp     [rbp+TokenInformation], 1
0x1800342c9  lea     rax, [rbp+arg_10]
0x1800342cd  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800342d2  mov     rcx, rbx; TokenHandle
0x1800342d5  jnz     short loc_180034348
0x1800342d7  mov     r9d, 4; TokenInformationLength
0x1800342dd  lea     r8, [rbp+arg_18]; TokenInformation
0x1800342e1  lea     edx, [r9+10h]; TokenInformationClass
0x1800342e5  call    cs:__imp_NtQueryInformationToken
0x1800342eb  mov     ecx, eax
0x1800342ed  test    eax, eax
0x1800342ef  js      short loc_18003433E
0x1800342f1  cmp     [rbp+arg_18], 0
0x1800342f5  jz      short loc_18003433E
0x1800342f7  xorps   xmm0, xmm0
0x1800342fa  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x1800342ff  xor     r9d, r9d; EffectiveOnly
0x180034302  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180034309  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003430d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180034315  xor     edx, edx; DesiredAccess
0x180034317  mov     [rbp+ObjectAttributes.Attributes], 0
0x18003431e  mov     rcx, rbx; ExistingTokenHandle
0x180034321  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180034329  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003432e  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180034336  call    cs:__imp_NtDuplicateToken
0x18003433c  mov     ecx, eax
0x18003433e  mov     eax, ecx
0x180034340  add     rsp, 70h
0x180034344  pop     rdi
0x180034345  pop     rbx
0x180034346  pop     rbp
0x180034347  retn
0x180034348  mov     r9d, 8; TokenInformationLength
0x18003434e  lea     r8, [rbp+var_40]; TokenInformation
0x180034352  lea     edx, [r9+0Bh]; TokenInformationClass
0x180034356  call    cs:__imp_NtQueryInformationToken
0x18003435c  mov     ecx, eax
0x18003435e  test    eax, eax
0x180034360  js      short loc_18003433E
0x180034362  mov     rax, [rbp+var_40]
0x180034366  mov     [rdi], rax
0x180034369  jmp     short loc_18003433E
```
