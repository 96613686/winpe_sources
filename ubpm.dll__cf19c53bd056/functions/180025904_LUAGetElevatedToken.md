# LUAGetElevatedToken

- ea: `0x180025904`
- end: `0x180025a17`
- name: `LUAGetElevatedToken`
- size: `275`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002576c`

## callees

- `0x180025904`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x180025a0d`
- `ntdll!NtDuplicateToken` at `0x180025a0d`
- `ntdll!NtQueryInformationToken` at `0x18002595f`
- `ntdll!NtQueryInformationToken` at `0x180025991`
- `ntdll!NtQueryInformationToken` at `0x1800259bc`
- `ntdll!NtQueryInformationToken` at `0x18002595f`
- `ntdll!NtQueryInformationToken` at `0x180025991`
- `ntdll!NtQueryInformationToken` at `0x1800259bc`

## pseudocode

```c
__int64 __fastcall LUAGetElevatedToken(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)
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
  v4 = NtQueryInformationToken(ExistingTokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v4 < 0 )
    return (unsigned int)v4;
  if ( TokenInformation == 2 )
  {
LABEL_9:
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)NtDuplicateToken(ExistingTokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, NewTokenHandle);
  }
  if ( TokenInformation == 1 )
  {
    v4 = NtQueryInformationToken(ExistingTokenHandle, TokenElevation, &v10, 4u, &ReturnLength);
    if ( v4 < 0 || !v10 )
      return (unsigned int)v4;
    goto LABEL_9;
  }
  v4 = NtQueryInformationToken(ExistingTokenHandle, TokenLinkedToken, &v6, 8u, &ReturnLength);
  if ( v4 >= 0 )
    *NewTokenHandle = v6;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025904  push    rbp
0x180025906  push    rbx
0x180025907  push    rdi
0x180025908  mov     rbp, rsp
0x18002590b  sub     rsp, 70h
0x18002590f  xorps   xmm0, xmm0
0x180025912  mov     qword ptr [rdx], 0
0x180025919  mov     r9d, 4; TokenInformationLength
0x18002591f  mov     [rbp+arg_10], 0
0x180025926  mov     rdi, rdx
0x180025929  mov     [rbp+arg_18], 0
0x180025930  lea     rax, [rbp+arg_10]
0x180025934  mov     [rbp+TokenInformation], 0
0x18002593b  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002593f  mov     [rbp+var_40], 0
0x180025947  lea     edx, [r9+0Eh]; TokenInformationClass
0x18002594b  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180025950  mov     rbx, rcx
0x180025953  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180025957  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002595b  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002595f  call    cs:__imp_NtQueryInformationToken
0x180025965  mov     ecx, eax
0x180025967  test    eax, eax
0x180025969  js      short loc_1800259A4
0x18002596b  cmp     [rbp+TokenInformation], 2
0x18002596f  jz      short loc_1800259CE
0x180025971  cmp     [rbp+TokenInformation], 1
0x180025975  lea     rax, [rbp+arg_10]
0x180025979  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002597e  mov     rcx, rbx; TokenHandle
0x180025981  jz      short loc_1800259AE
0x180025983  mov     r9d, 8; TokenInformationLength
0x180025989  lea     r8, [rbp+var_40]; TokenInformation
0x18002598d  lea     edx, [r9+0Bh]; TokenInformationClass
0x180025991  call    cs:__imp_NtQueryInformationToken
0x180025997  mov     ecx, eax
0x180025999  test    eax, eax
0x18002599b  js      short loc_1800259A4
0x18002599d  mov     rax, [rbp+var_40]
0x1800259a1  mov     [rdi], rax
0x1800259a4  mov     eax, ecx
0x1800259a6  add     rsp, 70h
0x1800259aa  pop     rdi
0x1800259ab  pop     rbx
0x1800259ac  pop     rbp
0x1800259ad  retn
0x1800259ae  mov     r9d, 4; TokenInformationLength
0x1800259b4  lea     r8, [rbp+arg_18]; TokenInformation
0x1800259b8  lea     edx, [r9+10h]; TokenInformationClass
0x1800259bc  call    cs:__imp_NtQueryInformationToken
0x1800259c2  mov     ecx, eax
0x1800259c4  test    eax, eax
0x1800259c6  js      short loc_1800259A4
0x1800259c8  cmp     [rbp+arg_18], 0
0x1800259cc  jz      short loc_1800259A4
0x1800259ce  xorps   xmm0, xmm0
0x1800259d1  mov     [rsp+70h+NewTokenHandle], rdi; NewTokenHandle
0x1800259d6  xor     r9d, r9d; EffectiveOnly
0x1800259d9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800259e0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800259e4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800259ec  xor     edx, edx; DesiredAccess
0x1800259ee  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800259f5  mov     rcx, rbx; ExistingTokenHandle
0x1800259f8  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180025a00  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180025a05  mov     dword ptr [rsp+70h+ReturnLength], 1; TokenType
0x180025a0d  call    cs:__imp_NtDuplicateToken
0x180025a13  mov     ecx, eax
0x180025a15  jmp     short loc_1800259A4
```
