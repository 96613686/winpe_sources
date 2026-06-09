# InitializeSdFromProcessToken(int,int,int,int,void * *,_ACL * *)

- ea: `0x140007b28`
- end: `0x140007eb3`
- name: `?InitializeSdFromProcessToken@@YAKHHHHPEAPEAXPEAPEAU_ACL@@@Z`
- size: `907`
- prototype: `unsigned int __fastcall(int, int, int, int, void **, struct _ACL **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140007ebc`

## callees

- `0x140007b28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140007b93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140007b93`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140007ba5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140007ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007c0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007bd3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007c05`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007c8e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007cb8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007bd3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007c05`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007c8e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007cb8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140007e2e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140007e2e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140007ccf`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140007ccf`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140007c63`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140007c63`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140007d87`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140007d87`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007cfc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007d11`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007d28`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007d3f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007cfc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007d11`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007d28`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140007d3f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140007daa`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140007dcd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140007df0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140007e13`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140007daa`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140007dcd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140007df0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140007e13`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140007ce7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140007ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007e59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007e59`
- `ntdll!RtlAllocateHeap` at `0x140007c4b`
- `ntdll!RtlAllocateHeap` at `0x140007d63`
- `ntdll!RtlAllocateHeap` at `0x140007c4b`
- `ntdll!RtlAllocateHeap` at `0x140007d63`
- `ntdll!RtlFreeHeap` at `0x140007e76`
- `ntdll!RtlFreeHeap` at `0x140007e93`
- `ntdll!RtlFreeHeap` at `0x140007e76`
- `ntdll!RtlFreeHeap` at `0x140007e93`

## pseudocode

```c
__int64 __fastcall InitializeSdFromProcessToken(int a1, int a2, int a3, int a4, void **a5, struct _ACL **a6)
{
  PSID *v6; // rsi
  struct _ACL *v7; // rdi
  DWORD v8; // r15d
  DWORD v9; // r14d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  __int64 v13; // r12
  PSID *Heap; // rax
  PSID *v15; // rbx
  PSID *v16; // r12
  DWORD v17; // ebx
  struct _ACL *v18; // rax
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+40h] BYREF
  DWORD ReturnLength; // [rsp+88h] [rbp+48h] BYREF

  v6 = 0;
  TokenInformationLength = 0;
  v7 = 0;
  ReturnLength = 0;
  v8 = 0;
  TokenHandle = 0;
  v9 = 0;
  if ( a2 )
  {
    v8 = 7;
    if ( a4 )
      v8 = 39;
  }
  if ( a1 )
  {
    v9 = 7;
    if ( a4 )
      v9 = 39;
  }
  *a5 = 0;
  *a6 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    goto LABEL_8;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
    || (LastError = GetLastError(), LastError == 122) )
  {
    if ( GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &ReturnLength)
      || (LastError = GetLastError(), LastError == 122) )
    {
      LastError = 8;
      v13 = (TokenInformationLength + 7) & 0xFFFFFFF8;
      Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v13 + ReturnLength + 40);
      v6 = Heap;
      if ( Heap )
      {
        if ( !InitializeSecurityDescriptor(Heap, 1u) )
          goto LABEL_8;
        v15 = v6 + 5;
        if ( !GetTokenInformation(TokenHandle, TokenUser, v6 + 5, TokenInformationLength, &TokenInformationLength) )
          goto LABEL_8;
        v16 = (PSID *)((char *)v15 + v13);
        if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, v16, ReturnLength, &ReturnLength)
          || !SetSecurityDescriptorOwner(v6, *v15, 0)
          || !SetSecurityDescriptorGroup(v6, *v16, 0) )
        {
          goto LABEL_8;
        }
        v17 = GetLengthSid(&unk_14000B5B0) + 16;
        if ( v9 )
          v17 += GetLengthSid(&unk_14000B590) + 8;
        if ( v8 )
          v17 += GetLengthSid(&unk_14000B5A0) + 8;
        if ( a3 )
          v17 += GetLengthSid(&unk_14000B560) + 8;
        v18 = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v17);
        v7 = v18;
        if ( !v18 )
        {
          LastError = 8;
          goto LABEL_37;
        }
        if ( !InitializeAcl(v18, v17, 2u)
          || !AddAccessAllowedAce(v7, 2u, 7u, &unk_14000B5B0)
          || v9 && !AddAccessAllowedAce(v7, 2u, v9, &unk_14000B590)
          || v8 && !AddAccessAllowedAce(v7, 2u, v8, &unk_14000B5A0)
          || a3 && !AddAccessAllowedAce(v7, 2u, 7u, &unk_14000B560)
          || !SetSecurityDescriptorDacl(v6, 1, v7, 0) )
        {
LABEL_8:
          LastError = GetLastError();
          goto LABEL_37;
        }
        *a5 = v6;
        v6 = 0;
        *a6 = v7;
        v7 = 0;
        LastError = 0;
      }
    }
  }
LABEL_37:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return LastError;
}

```

## disassembly

```asm
0x140007b28  mov     [rsp-38h+arg_10], rbx
0x140007b2d  push    rbp
0x140007b2e  push    rsi
0x140007b2f  push    rdi
0x140007b30  push    r12
0x140007b32  push    r13
0x140007b34  push    r14
0x140007b36  push    r15
0x140007b38  mov     rbp, rsp
0x140007b3b  sub     rsp, 40h
0x140007b3f  xor     esi, esi
0x140007b41  mov     [rbp+TokenInformationLength], 0
0x140007b48  xor     edi, edi
0x140007b4a  mov     [rbp+arg_8], 0
0x140007b51  xor     r15d, r15d
0x140007b54  mov     [rbp+TokenHandle], 0
0x140007b5c  xor     r14d, r14d
0x140007b5f  mov     r13d, r8d
0x140007b62  lea     eax, [rsi+27h]
0x140007b65  lea     r8d, [rsi+7]
0x140007b69  test    edx, edx
0x140007b6b  jz      short loc_140007B77
0x140007b6d  test    r9d, r9d
0x140007b70  mov     r15d, r8d
0x140007b73  cmovnz  r15d, eax
0x140007b77  test    ecx, ecx
0x140007b79  jz      short loc_140007B85
0x140007b7b  test    r9d, r9d
0x140007b7e  mov     r14d, r8d
0x140007b81  cmovnz  r14d, eax
0x140007b85  mov     rax, [rbp+arg_20]
0x140007b89  mov     [rax], rsi
0x140007b8c  mov     rax, [rbp+arg_28]
0x140007b90  mov     [rax], rsi
0x140007b93  call    cs:__imp_GetCurrentProcess
0x140007b99  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140007b9d  mov     edx, 8; DesiredAccess
0x140007ba2  mov     rcx, rax; ProcessHandle
0x140007ba5  call    cs:__imp_OpenProcessToken
0x140007bab  test    eax, eax
0x140007bad  jnz     short loc_140007BBC
0x140007baf  call    cs:__imp_GetLastError
0x140007bb5  mov     ebx, eax
0x140007bb7  jmp     loc_140007E50
0x140007bbc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140007bc0  lea     rax, [rbp+TokenInformationLength]
0x140007bc4  xor     r9d, r9d; TokenInformationLength
0x140007bc7  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140007bcc  xor     r8d, r8d; TokenInformation
0x140007bcf  lea     edx, [r9+1]; TokenInformationClass
0x140007bd3  call    cs:__imp_GetTokenInformation
0x140007bd9  test    eax, eax
0x140007bdb  jnz     short loc_140007BEE
0x140007bdd  call    cs:__imp_GetLastError
0x140007be3  mov     ebx, eax
0x140007be5  cmp     eax, 7Ah ; 'z'
0x140007be8  jnz     loc_140007E50
0x140007bee  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140007bf2  lea     rax, [rbp+arg_8]
0x140007bf6  xor     r9d, r9d; TokenInformationLength
0x140007bf9  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140007bfe  xor     r8d, r8d; TokenInformation
0x140007c01  lea     edx, [r9+5]; TokenInformationClass
0x140007c05  call    cs:__imp_GetTokenInformation
0x140007c0b  test    eax, eax
0x140007c0d  jnz     short loc_140007C20
0x140007c0f  call    cs:__imp_GetLastError
0x140007c15  mov     ebx, eax
0x140007c17  cmp     eax, 7Ah ; 'z'
0x140007c1a  jnz     loc_140007E50
0x140007c20  mov     r12d, [rbp+TokenInformationLength]
0x140007c24  mov     ebx, 8
0x140007c29  mov     rcx, gs:60h
0x140007c32  add     r12d, 7
0x140007c36  mov     r8d, [rbp+arg_8]
0x140007c3a  and     r12d, 0FFFFFFF8h
0x140007c3e  add     r8d, 28h ; '('
0x140007c42  mov     edx, ebx; Flags
0x140007c44  add     r8d, r12d; Size
0x140007c47  mov     rcx, [rcx+30h]; HeapHandle
0x140007c4b  call    cs:__imp_RtlAllocateHeap
0x140007c51  mov     rsi, rax
0x140007c54  test    rax, rax
0x140007c57  jz      loc_140007E50
0x140007c5d  lea     edx, [rbx-7]; dwRevision
0x140007c60  mov     rcx, rax; pSecurityDescriptor
0x140007c63  call    cs:__imp_InitializeSecurityDescriptor
0x140007c69  test    eax, eax
0x140007c6b  jz      loc_140007BAF
0x140007c71  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140007c75  lea     rax, [rbp+TokenInformationLength]
0x140007c79  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140007c7d  lea     rbx, [rsi+28h]
0x140007c81  mov     r8, rbx; TokenInformation
0x140007c84  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140007c89  mov     edx, 1; TokenInformationClass
0x140007c8e  call    cs:__imp_GetTokenInformation
0x140007c94  test    eax, eax
0x140007c96  jz      loc_140007BAF
0x140007c9c  mov     r9d, [rbp+arg_8]; TokenInformationLength
0x140007ca0  lea     rax, [rbp+arg_8]
0x140007ca4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140007ca8  add     r12, rbx
0x140007cab  mov     r8, r12; TokenInformation
0x140007cae  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140007cb3  mov     edx, 5; TokenInformationClass
0x140007cb8  call    cs:__imp_GetTokenInformation
0x140007cbe  test    eax, eax
0x140007cc0  jz      loc_140007BAF
0x140007cc6  mov     rdx, [rbx]; pOwner
0x140007cc9  xor     r8d, r8d; bOwnerDefaulted
0x140007ccc  mov     rcx, rsi; pSecurityDescriptor
0x140007ccf  call    cs:__imp_SetSecurityDescriptorOwner
0x140007cd5  test    eax, eax
0x140007cd7  jz      loc_140007BAF
0x140007cdd  mov     rdx, [r12]; pGroup
0x140007ce1  xor     r8d, r8d; bGroupDefaulted
0x140007ce4  mov     rcx, rsi; pSecurityDescriptor
0x140007ce7  call    cs:__imp_SetSecurityDescriptorGroup
0x140007ced  test    eax, eax
0x140007cef  jz      loc_140007BAF
0x140007cf5  lea     rcx, unk_14000B5B0; pSid
0x140007cfc  call    cs:__imp_GetLengthSid
0x140007d02  lea     ebx, [rax+10h]
0x140007d05  test    r14d, r14d
0x140007d08  jz      short loc_140007D1C
0x140007d0a  lea     rcx, unk_14000B590; pSid
0x140007d11  call    cs:__imp_GetLengthSid
0x140007d17  add     ebx, 8
0x140007d1a  add     ebx, eax
0x140007d1c  test    r15d, r15d
0x140007d1f  jz      short loc_140007D33
0x140007d21  lea     rcx, unk_14000B5A0; pSid
0x140007d28  call    cs:__imp_GetLengthSid
0x140007d2e  add     eax, 8
0x140007d31  add     ebx, eax
0x140007d33  test    r13d, r13d
0x140007d36  jz      short loc_140007D4A
0x140007d38  lea     rcx, unk_14000B560; pSid
0x140007d3f  call    cs:__imp_GetLengthSid
0x140007d45  add     eax, 8
0x140007d48  add     ebx, eax
0x140007d4a  mov     rcx, gs:60h
0x140007d53  mov     r12d, 8
0x140007d59  mov     r8d, ebx; Size
0x140007d5c  mov     edx, r12d; Flags
0x140007d5f  mov     rcx, [rcx+30h]; HeapHandle
0x140007d63  call    cs:__imp_RtlAllocateHeap
0x140007d69  mov     rdi, rax
0x140007d6c  test    rax, rax
0x140007d6f  jnz     short loc_140007D79
0x140007d71  mov     ebx, r12d
0x140007d74  jmp     loc_140007E50
0x140007d79  mov     r12d, 2
0x140007d7f  mov     edx, ebx; nAclLength
0x140007d81  mov     r8d, r12d; dwAclRevision
0x140007d84  mov     rcx, rdi; pAcl
0x140007d87  call    cs:__imp_InitializeAcl
0x140007d8d  test    eax, eax
0x140007d8f  jz      loc_140007BAF
0x140007d95  lea     ebx, [r12+5]
0x140007d9a  mov     edx, r12d; dwAceRevision
0x140007d9d  mov     r8d, ebx; AccessMask
0x140007da0  lea     r9, unk_14000B5B0; pSid
0x140007da7  mov     rcx, rdi; pAcl
0x140007daa  call    cs:__imp_AddAccessAllowedAce
0x140007db0  test    eax, eax
0x140007db2  jz      loc_140007BAF
0x140007db8  test    r14d, r14d
0x140007dbb  jz      short loc_140007DDB
0x140007dbd  lea     r9, unk_14000B590; pSid
0x140007dc4  mov     r8d, r14d; AccessMask
0x140007dc7  mov     edx, r12d; dwAceRevision
0x140007dca  mov     rcx, rdi; pAcl
0x140007dcd  call    cs:__imp_AddAccessAllowedAce
0x140007dd3  test    eax, eax
0x140007dd5  jz      loc_140007BAF
0x140007ddb  test    r15d, r15d
0x140007dde  jz      short loc_140007DFE
0x140007de0  lea     r9, unk_14000B5A0; pSid
0x140007de7  mov     r8d, r15d; AccessMask
0x140007dea  mov     edx, r12d; dwAceRevision
0x140007ded  mov     rcx, rdi; pAcl
0x140007df0  call    cs:__imp_AddAccessAllowedAce
0x140007df6  test    eax, eax
0x140007df8  jz      loc_140007BAF
0x140007dfe  test    r13d, r13d
0x140007e01  jz      short loc_140007E21
0x140007e03  lea     r9, unk_14000B560; pSid
0x140007e0a  mov     r8d, ebx; AccessMask
0x140007e0d  mov     edx, r12d; dwAceRevision
0x140007e10  mov     rcx, rdi; pAcl
0x140007e13  call    cs:__imp_AddAccessAllowedAce
0x140007e19  test    eax, eax
0x140007e1b  jz      loc_140007BAF
0x140007e21  xor     r9d, r9d; bDaclDefaulted
0x140007e24  mov     r8, rdi; pDacl
0x140007e27  mov     rcx, rsi; pSecurityDescriptor
0x140007e2a  lea     edx, [r9+1]; bDaclPresent
0x140007e2e  call    cs:__imp_SetSecurityDescriptorDacl
0x140007e34  test    eax, eax
0x140007e36  jz      loc_140007BAF
0x140007e3c  mov     rax, [rbp+arg_20]
0x140007e40  mov     [rax], rsi
0x140007e43  xor     esi, esi
0x140007e45  mov     rax, [rbp+arg_28]
0x140007e49  mov     [rax], rdi
0x140007e4c  xor     edi, edi
0x140007e4e  xor     ebx, ebx
0x140007e50  mov     rcx, [rbp+TokenHandle]; hObject
0x140007e54  test    rcx, rcx
0x140007e57  jz      short loc_140007E5F
0x140007e59  call    cs:__imp_CloseHandle
0x140007e5f  test    rsi, rsi
0x140007e62  jz      short loc_140007E7C
0x140007e64  mov     rcx, gs:60h
0x140007e6d  mov     r8, rsi; P
0x140007e70  xor     edx, edx; Flags
0x140007e72  mov     rcx, [rcx+30h]; HeapHandle
0x140007e76  call    cs:__imp_RtlFreeHeap
0x140007e7c  test    rdi, rdi
0x140007e7f  jz      short loc_140007E99
0x140007e81  mov     rcx, gs:60h
0x140007e8a  mov     r8, rdi; P
0x140007e8d  xor     edx, edx; Flags
0x140007e8f  mov     rcx, [rcx+30h]; HeapHandle
0x140007e93  call    cs:__imp_RtlFreeHeap
0x140007e99  mov     eax, ebx
0x140007e9b  mov     rbx, [rsp+40h+arg_10]
0x140007ea3  add     rsp, 40h
0x140007ea7  pop     r15
0x140007ea9  pop     r14
0x140007eab  pop     r13
0x140007ead  pop     r12
0x140007eaf  pop     rdi
0x140007eb0  pop     rsi
0x140007eb1  pop     rbp
0x140007eb2  retn
```
