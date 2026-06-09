# InitializeSdFromProcessToken(int,int,int,int,void * *,_ACL * *)

- ea: `0x140008040`
- end: `0x14000846e`
- name: `?InitializeSdFromProcessToken@@YAKHHHHPEAPEAXPEAPEAU_ACL@@@Z`
- size: `1070`
- prototype: `unsigned int __fastcall(int, int, int, int, void **, struct _ACL **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140008474`

## callees

- `0x140008040`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400080ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400080ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400080c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400080c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400080d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000810d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000814b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400080d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000810d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000814b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400080fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000813b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400081dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000820c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400080fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000813b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400081dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000820c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400083d0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400083d0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140008229`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140008229`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400081ab`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400081ab`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14000830b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14000830b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140008262`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000827d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000829a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400082b7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140008262`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000827d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14000829a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400082b7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140008334`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x14000835d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140008386`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1400083af`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140008334`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x14000835d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140008386`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1400083af`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140008247`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140008247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008401`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008401`
- `ntdll!RtlAllocateHeap` at `0x14000818d`
- `ntdll!RtlAllocateHeap` at `0x1400082e1`
- `ntdll!RtlAllocateHeap` at `0x14000818d`
- `ntdll!RtlAllocateHeap` at `0x1400082e1`
- `ntdll!RtlFreeHeap` at `0x140008424`
- `ntdll!RtlFreeHeap` at `0x140008447`
- `ntdll!RtlFreeHeap` at `0x140008424`
- `ntdll!RtlFreeHeap` at `0x140008447`

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
0x140008040  mov     [rsp-38h+arg_10], rbx
0x140008045  push    rbp
0x140008046  push    rsi
0x140008047  push    rdi
0x140008048  push    r12
0x14000804a  push    r13
0x14000804c  push    r14
0x14000804e  push    r15
0x140008050  mov     rbp, rsp
0x140008053  sub     rsp, 40h
0x140008057  xor     esi, esi
0x140008059  mov     [rbp+TokenInformationLength], 0
0x140008060  xor     edi, edi
0x140008062  mov     [rbp+arg_8], 0
0x140008069  xor     r15d, r15d
0x14000806c  mov     [rbp+TokenHandle], 0
0x140008074  xor     r14d, r14d
0x140008077  mov     r13d, r8d
0x14000807a  lea     eax, [rsi+27h]
0x14000807d  lea     r8d, [rsi+7]
0x140008081  test    edx, edx
0x140008083  jz      short loc_14000808F
0x140008085  test    r9d, r9d
0x140008088  mov     r15d, r8d
0x14000808b  cmovnz  r15d, eax
0x14000808f  test    ecx, ecx
0x140008091  jz      short loc_14000809D
0x140008093  test    r9d, r9d
0x140008096  mov     r14d, r8d
0x140008099  cmovnz  r14d, eax
0x14000809d  mov     rax, [rbp+arg_20]
0x1400080a1  mov     [rax], rsi
0x1400080a4  mov     rax, [rbp+arg_28]
0x1400080a8  mov     [rax], rsi
0x1400080ab  call    cs:__imp_GetCurrentProcess
0x1400080b2  nop     dword ptr [rax+rax+00h]
0x1400080b7  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400080bb  mov     edx, 8; DesiredAccess
0x1400080c0  mov     rcx, rax; ProcessHandle
0x1400080c3  call    cs:__imp_OpenProcessToken
0x1400080ca  nop     dword ptr [rax+rax+00h]
0x1400080cf  test    eax, eax
0x1400080d1  jnz     short loc_1400080E6
0x1400080d3  call    cs:__imp_GetLastError
0x1400080da  nop     dword ptr [rax+rax+00h]
0x1400080df  mov     ebx, eax
0x1400080e1  jmp     loc_1400083F8
0x1400080e6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400080ea  lea     rax, [rbp+TokenInformationLength]
0x1400080ee  xor     r9d, r9d; TokenInformationLength
0x1400080f1  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1400080f6  xor     r8d, r8d; TokenInformation
0x1400080f9  lea     edx, [r9+1]; TokenInformationClass
0x1400080fd  call    cs:__imp_GetTokenInformation
0x140008104  nop     dword ptr [rax+rax+00h]
0x140008109  test    eax, eax
0x14000810b  jnz     short loc_140008124
0x14000810d  call    cs:__imp_GetLastError
0x140008114  nop     dword ptr [rax+rax+00h]
0x140008119  mov     ebx, eax
0x14000811b  cmp     eax, 7Ah ; 'z'
0x14000811e  jnz     loc_1400083F8
0x140008124  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140008128  lea     rax, [rbp+arg_8]
0x14000812c  xor     r9d, r9d; TokenInformationLength
0x14000812f  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140008134  xor     r8d, r8d; TokenInformation
0x140008137  lea     edx, [r9+5]; TokenInformationClass
0x14000813b  call    cs:__imp_GetTokenInformation
0x140008142  nop     dword ptr [rax+rax+00h]
0x140008147  test    eax, eax
0x140008149  jnz     short loc_140008162
0x14000814b  call    cs:__imp_GetLastError
0x140008152  nop     dword ptr [rax+rax+00h]
0x140008157  mov     ebx, eax
0x140008159  cmp     eax, 7Ah ; 'z'
0x14000815c  jnz     loc_1400083F8
0x140008162  mov     r12d, [rbp+TokenInformationLength]
0x140008166  mov     ebx, 8
0x14000816b  mov     rcx, gs:60h
0x140008174  add     r12d, 7
0x140008178  mov     r8d, [rbp+arg_8]
0x14000817c  and     r12d, 0FFFFFFF8h
0x140008180  add     r8d, 28h ; '('
0x140008184  mov     edx, ebx; Flags
0x140008186  add     r8d, r12d; Size
0x140008189  mov     rcx, [rcx+30h]; HeapHandle
0x14000818d  call    cs:__imp_RtlAllocateHeap
0x140008194  nop     dword ptr [rax+rax+00h]
0x140008199  mov     rsi, rax
0x14000819c  test    rax, rax
0x14000819f  jz      loc_1400083F8
0x1400081a5  lea     edx, [rbx-7]; dwRevision
0x1400081a8  mov     rcx, rax; pSecurityDescriptor
0x1400081ab  call    cs:__imp_InitializeSecurityDescriptor
0x1400081b2  nop     dword ptr [rax+rax+00h]
0x1400081b7  test    eax, eax
0x1400081b9  jz      loc_1400080D3
0x1400081bf  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400081c3  lea     rax, [rbp+TokenInformationLength]
0x1400081c7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400081cb  lea     rbx, [rsi+28h]
0x1400081cf  mov     r8, rbx; TokenInformation
0x1400081d2  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1400081d7  mov     edx, 1; TokenInformationClass
0x1400081dc  call    cs:__imp_GetTokenInformation
0x1400081e3  nop     dword ptr [rax+rax+00h]
0x1400081e8  test    eax, eax
0x1400081ea  jz      loc_1400080D3
0x1400081f0  mov     r9d, [rbp+arg_8]; TokenInformationLength
0x1400081f4  lea     rax, [rbp+arg_8]
0x1400081f8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400081fc  add     r12, rbx
0x1400081ff  mov     r8, r12; TokenInformation
0x140008202  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140008207  mov     edx, 5; TokenInformationClass
0x14000820c  call    cs:__imp_GetTokenInformation
0x140008213  nop     dword ptr [rax+rax+00h]
0x140008218  test    eax, eax
0x14000821a  jz      loc_1400080D3
0x140008220  mov     rdx, [rbx]; pOwner
0x140008223  xor     r8d, r8d; bOwnerDefaulted
0x140008226  mov     rcx, rsi; pSecurityDescriptor
0x140008229  call    cs:__imp_SetSecurityDescriptorOwner
0x140008230  nop     dword ptr [rax+rax+00h]
0x140008235  test    eax, eax
0x140008237  jz      loc_1400080D3
0x14000823d  mov     rdx, [r12]; pGroup
0x140008241  xor     r8d, r8d; bGroupDefaulted
0x140008244  mov     rcx, rsi; pSecurityDescriptor
0x140008247  call    cs:__imp_SetSecurityDescriptorGroup
0x14000824e  nop     dword ptr [rax+rax+00h]
0x140008253  test    eax, eax
0x140008255  jz      loc_1400080D3
0x14000825b  lea     rcx, unk_14000B5B0; pSid
0x140008262  call    cs:__imp_GetLengthSid
0x140008269  nop     dword ptr [rax+rax+00h]
0x14000826e  lea     ebx, [rax+10h]
0x140008271  test    r14d, r14d
0x140008274  jz      short loc_14000828E
0x140008276  lea     rcx, unk_14000B590; pSid
0x14000827d  call    cs:__imp_GetLengthSid
0x140008284  nop     dword ptr [rax+rax+00h]
0x140008289  add     ebx, 8
0x14000828c  add     ebx, eax
0x14000828e  test    r15d, r15d
0x140008291  jz      short loc_1400082AB
0x140008293  lea     rcx, unk_14000B5A0; pSid
0x14000829a  call    cs:__imp_GetLengthSid
0x1400082a1  nop     dword ptr [rax+rax+00h]
0x1400082a6  add     eax, 8
0x1400082a9  add     ebx, eax
0x1400082ab  test    r13d, r13d
0x1400082ae  jz      short loc_1400082C8
0x1400082b0  lea     rcx, unk_14000B560; pSid
0x1400082b7  call    cs:__imp_GetLengthSid
0x1400082be  nop     dword ptr [rax+rax+00h]
0x1400082c3  add     eax, 8
0x1400082c6  add     ebx, eax
0x1400082c8  mov     rcx, gs:60h
0x1400082d1  mov     r12d, 8
0x1400082d7  mov     r8d, ebx; Size
0x1400082da  mov     edx, r12d; Flags
0x1400082dd  mov     rcx, [rcx+30h]; HeapHandle
0x1400082e1  call    cs:__imp_RtlAllocateHeap
0x1400082e8  nop     dword ptr [rax+rax+00h]
0x1400082ed  mov     rdi, rax
0x1400082f0  test    rax, rax
0x1400082f3  jnz     short loc_1400082FD
0x1400082f5  mov     ebx, r12d
0x1400082f8  jmp     loc_1400083F8
0x1400082fd  mov     r12d, 2
0x140008303  mov     edx, ebx; nAclLength
0x140008305  mov     r8d, r12d; dwAclRevision
0x140008308  mov     rcx, rdi; pAcl
0x14000830b  call    cs:__imp_InitializeAcl
0x140008312  nop     dword ptr [rax+rax+00h]
0x140008317  test    eax, eax
0x140008319  jz      loc_1400080D3
0x14000831f  lea     ebx, [r12+5]
0x140008324  mov     edx, r12d; dwAceRevision
0x140008327  mov     r8d, ebx; AccessMask
0x14000832a  lea     r9, unk_14000B5B0; pSid
0x140008331  mov     rcx, rdi; pAcl
0x140008334  call    cs:__imp_AddAccessAllowedAce
0x14000833b  nop     dword ptr [rax+rax+00h]
0x140008340  test    eax, eax
0x140008342  jz      loc_1400080D3
0x140008348  test    r14d, r14d
0x14000834b  jz      short loc_140008371
0x14000834d  lea     r9, unk_14000B590; pSid
0x140008354  mov     r8d, r14d; AccessMask
0x140008357  mov     edx, r12d; dwAceRevision
0x14000835a  mov     rcx, rdi; pAcl
0x14000835d  call    cs:__imp_AddAccessAllowedAce
0x140008364  nop     dword ptr [rax+rax+00h]
0x140008369  test    eax, eax
0x14000836b  jz      loc_1400080D3
0x140008371  test    r15d, r15d
0x140008374  jz      short loc_14000839A
0x140008376  lea     r9, unk_14000B5A0; pSid
0x14000837d  mov     r8d, r15d; AccessMask
0x140008380  mov     edx, r12d; dwAceRevision
0x140008383  mov     rcx, rdi; pAcl
0x140008386  call    cs:__imp_AddAccessAllowedAce
0x14000838d  nop     dword ptr [rax+rax+00h]
0x140008392  test    eax, eax
0x140008394  jz      loc_1400080D3
0x14000839a  test    r13d, r13d
0x14000839d  jz      short loc_1400083C3
0x14000839f  lea     r9, unk_14000B560; pSid
0x1400083a6  mov     r8d, ebx; AccessMask
0x1400083a9  mov     edx, r12d; dwAceRevision
0x1400083ac  mov     rcx, rdi; pAcl
0x1400083af  call    cs:__imp_AddAccessAllowedAce
0x1400083b6  nop     dword ptr [rax+rax+00h]
0x1400083bb  test    eax, eax
0x1400083bd  jz      loc_1400080D3
0x1400083c3  xor     r9d, r9d; bDaclDefaulted
0x1400083c6  mov     r8, rdi; pDacl
0x1400083c9  mov     rcx, rsi; pSecurityDescriptor
0x1400083cc  lea     edx, [r9+1]; bDaclPresent
0x1400083d0  call    cs:__imp_SetSecurityDescriptorDacl
0x1400083d7  nop     dword ptr [rax+rax+00h]
0x1400083dc  test    eax, eax
0x1400083de  jz      loc_1400080D3
0x1400083e4  mov     rax, [rbp+arg_20]
0x1400083e8  mov     [rax], rsi
0x1400083eb  xor     esi, esi
0x1400083ed  mov     rax, [rbp+arg_28]
0x1400083f1  mov     [rax], rdi
0x1400083f4  xor     edi, edi
0x1400083f6  xor     ebx, ebx
0x1400083f8  mov     rcx, [rbp+TokenHandle]; hObject
0x1400083fc  test    rcx, rcx
0x1400083ff  jz      short loc_14000840D
0x140008401  call    cs:__imp_CloseHandle
0x140008408  nop     dword ptr [rax+rax+00h]
0x14000840d  test    rsi, rsi
0x140008410  jz      short loc_140008430
0x140008412  mov     rcx, gs:60h
0x14000841b  mov     r8, rsi; P
0x14000841e  xor     edx, edx; Flags
0x140008420  mov     rcx, [rcx+30h]; HeapHandle
0x140008424  call    cs:__imp_RtlFreeHeap
0x14000842b  nop     dword ptr [rax+rax+00h]
0x140008430  test    rdi, rdi
0x140008433  jz      short loc_140008453
0x140008435  mov     rcx, gs:60h
0x14000843e  mov     r8, rdi; P
0x140008441  xor     edx, edx; Flags
0x140008443  mov     rcx, [rcx+30h]; HeapHandle
0x140008447  call    cs:__imp_RtlFreeHeap
0x14000844e  nop     dword ptr [rax+rax+00h]
0x140008453  mov     eax, ebx
0x140008455  mov     rbx, [rsp+40h+arg_10]
0x14000845d  add     rsp, 40h
0x140008461  pop     r15
0x140008463  pop     r14
0x140008465  pop     r13
0x140008467  pop     r12
0x140008469  pop     rdi
0x14000846a  pop     rsi
0x14000846b  pop     rbp
0x14000846c  retn
```
