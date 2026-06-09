# GetAppUserSID

- ea: `0x180018a7c`
- end: `0x180018c80`
- name: `GetAppUserSID`
- size: `516`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017ce0`
- `0x180023698`

## callees

- `0x180012290`
- `0x1800125c8`
- `0x180018a7c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180018b50`
- `ntdll!RtlCopySid` at `0x180018c1e`
- `ntdll!RtlCopySid` at `0x180018b50`
- `ntdll!RtlCopySid` at `0x180018c1e`
- `ntdll!NtQueryInformationToken` at `0x180018acd`
- `ntdll!NtQueryInformationToken` at `0x180018b12`
- `ntdll!NtQueryInformationToken` at `0x180018b7d`
- `ntdll!NtQueryInformationToken` at `0x180018baf`
- `ntdll!NtQueryInformationToken` at `0x180018bea`
- `ntdll!NtQueryInformationToken` at `0x180018acd`
- `ntdll!NtQueryInformationToken` at `0x180018b12`
- `ntdll!NtQueryInformationToken` at `0x180018b7d`
- `ntdll!NtQueryInformationToken` at `0x180018baf`
- `ntdll!NtQueryInformationToken` at `0x180018bea`
- `ntdll!RtlLengthSid` at `0x180018b25`
- `ntdll!RtlLengthSid` at `0x180018bf9`
- `ntdll!RtlLengthSid` at `0x180018b25`
- `ntdll!RtlLengthSid` at `0x180018bf9`

## pseudocode

```c
__int64 __fastcall GetAppUserSID(HANDLE TokenHandle, _QWORD *a2, _QWORD *a3)
{
  NTSTATUS v6; // ebx
  PSID *v7; // rsi
  PSID *v8; // rdi
  void *v9; // rax
  void *v10; // rax
  ULONG TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+40h] BYREF

  *a2 = 0;
  *a3 = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  v6 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( v6 != -1073741789 )
    goto LABEL_17;
  v7 = (PSID *)AccessHlprAlloc(TokenInformationLength);
  if ( v7 )
  {
    v8 = 0;
    v6 = NtQueryInformationToken(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength);
    if ( v6 < 0 )
      goto LABEL_15;
    TokenInformationLength = RtlLengthSid(*v7);
    v9 = (void *)AccessHlprAlloc(TokenInformationLength);
    *a2 = v9;
    if ( !v9 )
      goto LABEL_6;
    v6 = RtlCopySid(TokenInformationLength, v9, *v7);
    if ( v6 >= 0 )
    {
      TokenInformationLength = 0;
      v6 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength);
      if ( v6 >= 0 )
      {
        if ( TokenInformation )
        {
          TokenInformationLength = 0;
          v6 = NtQueryInformationToken(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength);
          if ( v6 == -1073741789 )
          {
            v8 = (PSID *)AccessHlprAlloc(TokenInformationLength);
            if ( !v8 )
              goto LABEL_6;
            v6 = NtQueryInformationToken(
                   TokenHandle,
                   TokenAppContainerSid,
                   v8,
                   TokenInformationLength,
                   &TokenInformationLength);
            if ( v6 < 0 )
              goto LABEL_15;
            TokenInformationLength = RtlLengthSid(*v8);
            v10 = (void *)AccessHlprAlloc(TokenInformationLength);
            *a3 = v10;
            if ( !v10 )
            {
LABEL_6:
              v6 = -1073741801;
              goto LABEL_15;
            }
            v6 = RtlCopySid(TokenInformationLength, v10, *v8);
          }
        }
      }
    }
LABEL_15:
    FreeTransientObjectSecurityDescriptor(v7);
    if ( v8 )
      FreeTransientObjectSecurityDescriptor(v8);
LABEL_17:
    if ( v6 >= 0 )
      return (unsigned int)v6;
    goto LABEL_18;
  }
  v6 = -1073741801;
LABEL_18:
  if ( *a2 )
  {
    FreeTransientObjectSecurityDescriptor(*a2);
    *a2 = 0;
  }
  if ( *a3 )
  {
    FreeTransientObjectSecurityDescriptor(*a3);
    *a3 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018a7c  mov     [rsp-28h+arg_0], rbx
0x180018a81  mov     [rsp-28h+arg_18], rsi
0x180018a86  push    rbp
0x180018a87  push    rdi
0x180018a88  push    r12
0x180018a8a  push    r14
0x180018a8c  push    r15
0x180018a8e  mov     rbp, rsp
0x180018a91  sub     rsp, 30h
0x180018a95  xor     r9d, r9d; TokenInformationLength
0x180018a98  mov     qword ptr [rdx], 0
0x180018a9f  mov     r14, r8
0x180018aa2  mov     qword ptr [r8], 0
0x180018aa9  mov     r15, rdx
0x180018aac  mov     [rbp+TokenInformation], 0
0x180018ab3  lea     rax, [rbp+TokenInformationLength]
0x180018ab7  mov     [rbp+TokenInformationLength], 0
0x180018abe  lea     edx, [r9+1]; TokenInformationClass
0x180018ac2  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180018ac7  xor     r8d, r8d; TokenInformation
0x180018aca  mov     r12, rcx
0x180018acd  call    cs:__imp_NtQueryInformationToken
0x180018ad3  mov     ebx, eax
0x180018ad5  cmp     eax, 0C0000023h
0x180018ada  jnz     loc_180018C3B
0x180018ae0  mov     ecx, [rbp+TokenInformationLength]
0x180018ae3  call    AccessHlprAlloc
0x180018ae8  mov     rsi, rax
0x180018aeb  test    rax, rax
0x180018aee  jnz     short loc_180018AFA
0x180018af0  mov     ebx, 0C0000017h
0x180018af5  jmp     loc_180018C3F
0x180018afa  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180018afe  lea     rax, [rbp+TokenInformationLength]
0x180018b02  xor     edi, edi
0x180018b04  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180018b09  mov     r8, rsi; TokenInformation
0x180018b0c  mov     rcx, r12; TokenHandle
0x180018b0f  lea     edx, [rdi+1]; TokenInformationClass
0x180018b12  call    cs:__imp_NtQueryInformationToken
0x180018b18  mov     ebx, eax
0x180018b1a  test    eax, eax
0x180018b1c  js      loc_180018C26
0x180018b22  mov     rcx, [rsi]; Sid
0x180018b25  call    cs:__imp_RtlLengthSid
0x180018b2b  mov     ecx, eax
0x180018b2d  mov     [rbp+TokenInformationLength], ecx
0x180018b30  call    AccessHlprAlloc
0x180018b35  mov     [r15], rax
0x180018b38  test    rax, rax
0x180018b3b  jnz     short loc_180018B47
0x180018b3d  mov     ebx, 0C0000017h
0x180018b42  jmp     loc_180018C26
0x180018b47  mov     r8, [rsi]; SourceSid
0x180018b4a  mov     rdx, rax; DestinationSid
0x180018b4d  mov     ecx, [rbp+TokenInformationLength]; DestinationSidLength
0x180018b50  call    cs:__imp_RtlCopySid
0x180018b56  mov     ebx, eax
0x180018b58  test    eax, eax
0x180018b5a  js      loc_180018C26
0x180018b60  mov     r9d, 4; TokenInformationLength
0x180018b66  mov     [rbp+TokenInformationLength], edi
0x180018b69  lea     rax, [rbp+TokenInformationLength]
0x180018b6d  mov     rcx, r12; TokenHandle
0x180018b70  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180018b74  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180018b79  lea     edx, [r9+19h]; TokenInformationClass
0x180018b7d  call    cs:__imp_NtQueryInformationToken
0x180018b83  mov     ebx, eax
0x180018b85  test    eax, eax
0x180018b87  js      loc_180018C26
0x180018b8d  cmp     [rbp+TokenInformation], edi
0x180018b90  jz      loc_180018C26
0x180018b96  xor     r9d, r9d; TokenInformationLength
0x180018b99  mov     [rbp+TokenInformationLength], edi
0x180018b9c  lea     rax, [rbp+TokenInformationLength]
0x180018ba0  xor     r8d, r8d; TokenInformation
0x180018ba3  mov     rcx, r12; TokenHandle
0x180018ba6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180018bab  lea     edx, [r9+1Fh]; TokenInformationClass
0x180018baf  call    cs:__imp_NtQueryInformationToken
0x180018bb5  mov     ebx, eax
0x180018bb7  cmp     eax, 0C0000023h
0x180018bbc  jnz     short loc_180018C26
0x180018bbe  mov     ecx, [rbp+TokenInformationLength]
0x180018bc1  call    AccessHlprAlloc
0x180018bc6  mov     rdi, rax
0x180018bc9  test    rax, rax
0x180018bcc  jz      loc_180018B3D
0x180018bd2  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180018bd6  lea     rax, [rbp+TokenInformationLength]
0x180018bda  mov     r8, rdi; TokenInformation
0x180018bdd  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180018be2  mov     edx, 1Fh; TokenInformationClass
0x180018be7  mov     rcx, r12; TokenHandle
0x180018bea  call    cs:__imp_NtQueryInformationToken
0x180018bf0  mov     ebx, eax
0x180018bf2  test    eax, eax
0x180018bf4  js      short loc_180018C26
0x180018bf6  mov     rcx, [rdi]; Sid
0x180018bf9  call    cs:__imp_RtlLengthSid
0x180018bff  mov     ecx, eax
0x180018c01  mov     [rbp+TokenInformationLength], ecx
0x180018c04  call    AccessHlprAlloc
0x180018c09  mov     [r14], rax
0x180018c0c  test    rax, rax
0x180018c0f  jz      loc_180018B3D
0x180018c15  mov     r8, [rdi]; SourceSid
0x180018c18  mov     rdx, rax; DestinationSid
0x180018c1b  mov     ecx, [rbp+TokenInformationLength]; DestinationSidLength
0x180018c1e  call    cs:__imp_RtlCopySid
0x180018c24  mov     ebx, eax
0x180018c26  mov     rcx, rsi
0x180018c29  call    FreeTransientObjectSecurityDescriptor
0x180018c2e  test    rdi, rdi
0x180018c31  jz      short loc_180018C3B
0x180018c33  mov     rcx, rdi
0x180018c36  call    FreeTransientObjectSecurityDescriptor
0x180018c3b  test    ebx, ebx
0x180018c3d  jns     short loc_180018C67
0x180018c3f  mov     rcx, [r15]
0x180018c42  test    rcx, rcx
0x180018c45  jz      short loc_180018C53
0x180018c47  call    FreeTransientObjectSecurityDescriptor
0x180018c4c  mov     qword ptr [r15], 0
0x180018c53  mov     rcx, [r14]
0x180018c56  test    rcx, rcx
0x180018c59  jz      short loc_180018C67
0x180018c5b  call    FreeTransientObjectSecurityDescriptor
0x180018c60  mov     qword ptr [r14], 0
0x180018c67  mov     rsi, [rsp+30h+arg_18]
0x180018c6c  mov     eax, ebx
0x180018c6e  mov     rbx, [rsp+30h+arg_0]
0x180018c73  add     rsp, 30h
0x180018c77  pop     r15
0x180018c79  pop     r14
0x180018c7b  pop     r12
0x180018c7d  pop     rdi
0x180018c7e  pop     rbp
0x180018c7f  retn
```
