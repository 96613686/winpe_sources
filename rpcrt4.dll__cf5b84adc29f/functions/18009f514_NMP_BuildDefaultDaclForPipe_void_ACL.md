# NMP_BuildDefaultDaclForPipe(void *,_ACL * *)

- ea: `0x18009f514`
- end: `0x18009f999`
- name: `?NMP_BuildDefaultDaclForPipe@@YAJPEAXPEAPEAU_ACL@@@Z`
- size: `1157`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _ACL **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180086ca4`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800295d8`
- `0x18009f514`
- `0x1800ceca9`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f5f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f90f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f5f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f90f`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009f6a8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009f6cb`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009f6e2`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009f6a8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009f6cb`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18009f6e2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009f694`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009f7ec`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009f694`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18009f7ec`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18009f679`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18009f7d4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18009f679`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18009f7d4`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18009f651`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18009f7ac`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18009f651`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18009f7ac`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009f63c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009f793`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009f63c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18009f793`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009f57c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009f5e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009f887`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009f57c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009f5e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009f887`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f741`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f76a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f812`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f8c0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f8ff`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f741`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f76a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f812`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f8c0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009f8ff`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009f720`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009f720`

## pseudocode

```c
__int64 __fastcall NMP_BuildDefaultDaclForPipe(HANDLE TokenHandle, struct _ACL **a2)
{
  int v2; // r13d
  HANDLE v4; // r15
  unsigned int v5; // ebx
  DWORD LastError; // eax
  unsigned int *v7; // rdi
  DWORD v8; // eax
  int v9; // r12d
  unsigned int v10; // esi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v12; // ecx
  UCHAR *SidSubAuthorityCount; // r15
  DWORD SidLengthRequired; // eax
  DWORD v15; // edx
  DWORD v16; // ebx
  struct _ACL *v17; // rax
  __int64 *v18; // rbx
  unsigned int i; // ebx
  PSID_IDENTIFIER_AUTHORITY v20; // rax
  int v21; // ecx
  DWORD v22; // eax
  PSID *v23; // rcx
  DWORD v24; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v27; // [rsp+34h] [rbp-CCh]
  DWORD TokenInformationLength; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+48h] [rbp-B8h]
  HANDLE v31; // [rsp+58h] [rbp-A8h]
  PSID TokenInformation[76]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  v31 = TokenHandle;
  *a2 = 0;
  TokenInformationLength = 0;
  ReturnLength = 0;
  v27 = 1280;
  v4 = TokenHandle;
  if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) )
    goto LABEL_2;
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v7 = (unsigned int *)AllocWrapper(TokenInformationLength);
    if ( !v7 )
      goto LABEL_2;
    if ( !GetTokenInformation(v4, TokenGroups, v7, TokenInformationLength, &TokenInformationLength) )
    {
      v8 = GetLastError();
      RpcpErrorAddRecord(2u, v8, 0xFDDu, 0, 0);
LABEL_8:
      v5 = 14;
LABEL_45:
      FreeWrapper(v7);
      goto LABEL_46;
    }
    v9 = 0;
    v10 = 0;
    if ( *v7 )
    {
      do
      {
        if ( IsValidSid(*(PSID *)&v7[4 * v10 + 2]) )
        {
          SidIdentifierAuthority = GetSidIdentifierAuthority(*(PSID *)&v7[4 * v10 + 2]);
          v12 = *(_DWORD *)SidIdentifierAuthority->Value - ReturnLength;
          if ( *(_DWORD *)SidIdentifierAuthority->Value == ReturnLength )
            v12 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - v27;
          if ( !v12 )
          {
            SidSubAuthorityCount = GetSidSubAuthorityCount(*(PSID *)&v7[4 * v10 + 2]);
            if ( *SidSubAuthorityCount )
            {
              if ( *GetSidSubAuthority(*(PSID *)&v7[4 * v10 + 2], 0) == 80 )
              {
                v2 += GetSidLengthRequired(*SidSubAuthorityCount);
                ++v9;
              }
            }
          }
        }
        ++v10;
      }
      while ( v10 < *v7 );
      v4 = v31;
    }
    SidLengthRequired = GetSidLengthRequired(0xFu);
    v15 = 12;
    if ( SidLengthRequired >= 0xC )
      v15 = GetSidLengthRequired(0xFu);
    v16 = v2 + 68 + v15 + 12 * v9;
    v17 = (struct _ACL *)AllocWrapper(v16);
    *a2 = v17;
    if ( !v17 )
      goto LABEL_8;
    InitializeAcl(v17, v16, 2u);
    v18 = qword_1800E8320;
    if ( AddAccessAllowedAce(*a2, 2u, 0x12019Bu, qword_1800E8320) )
    {
      v18 = qword_1800E8310;
      if ( AddAccessAllowedAce(*a2, 2u, 0x12019Bu, qword_1800E8310) )
      {
        for ( i = 0; i < *v7; ++i )
        {
          if ( IsValidSid(*(PSID *)&v7[4 * i + 2]) )
          {
            v20 = GetSidIdentifierAuthority(*(PSID *)&v7[4 * i + 2]);
            v21 = *(_DWORD *)v20->Value - ReturnLength;
            if ( *(_DWORD *)v20->Value == ReturnLength )
              v21 = *(unsigned __int16 *)&v20->Value[4] - v27;
            if ( !v21
              && *GetSidSubAuthorityCount(*(PSID *)&v7[4 * i + 2])
              && *GetSidSubAuthority(*(PSID *)&v7[4 * i + 2], 0) == 80
              && !AddAccessAllowedAce(*a2, 2u, 0x1F01FFu, *(PSID *)&v7[4 * i + 2]) )
            {
              v22 = GetLastError();
              LODWORD(v23) = 16 * i + (_DWORD)v7 + 8;
LABEL_34:
              v30 = (int)v23;
              goto LABEL_43;
            }
          }
        }
        if ( !v9 )
        {
          ReturnLength = 76;
          memset_0(TokenInformation, 0, sizeof(TokenInformation));
          if ( !GetTokenInformation(v4, TokenOwner, TokenInformation, 0x4Cu, &ReturnLength) )
          {
            v24 = GetLastError();
            RpcpErrorAddRecord(2u, v24, 0xFE9u, 0, 0);
LABEL_44:
            v5 = 1721;
            goto LABEL_45;
          }
          if ( !AddAccessAllowedAce(*a2, 2u, 0x1F01FFu, TokenInformation[0]) )
          {
            v22 = GetLastError();
            v23 = TokenInformation;
            goto LABEL_34;
          }
LABEL_49:
          FreeWrapper(v7);
          return 0;
        }
        v18 = qword_1800E8330;
        if ( AddAccessAllowedAce(*a2, 2u, 0x20000u, qword_1800E8330) )
          goto LABEL_49;
      }
    }
    v22 = GetLastError();
    v30 = (int)v18;
LABEL_43:
    v29 = 3;
    RpcpErrorAddRecord(2u, v22, 0xFE9u, 1, (struct tagParam *)&v29);
    goto LABEL_44;
  }
  RpcpErrorAddRecord(2u, LastError, 0xFDCu, 0, 0);
LABEL_2:
  v5 = 14;
LABEL_46:
  if ( *a2 )
    FreeWrapper(*a2);
  return v5;
}

```

## disassembly

```asm
0x18009f514  mov     [rsp-8+arg_10], rbx
0x18009f519  push    rbp
0x18009f51a  push    rsi
0x18009f51b  push    rdi
0x18009f51c  push    r12
0x18009f51e  push    r13
0x18009f520  push    r14
0x18009f522  push    r15
0x18009f524  lea     rbp, [rsp-1D0h]
0x18009f52c  sub     rsp, 2D0h
0x18009f533  mov     rax, cs:__security_cookie
0x18009f53a  xor     rax, rsp
0x18009f53d  mov     [rbp+200h+var_40], rax
0x18009f544  xor     r13d, r13d
0x18009f547  mov     [rsp+300h+var_2A8], rcx
0x18009f54c  mov     r14, rdx
0x18009f54f  mov     [rdx], r13
0x18009f552  lea     rax, [rsp+300h+TokenInformationLength]
0x18009f557  mov     [rsp+300h+TokenInformationLength], r13d
0x18009f55c  xor     r9d, r9d; TokenInformationLength
0x18009f55f  mov     [rsp+300h+var_2D0], r13d
0x18009f564  lea     ebx, [r13+2]
0x18009f568  mov     [rsp+300h+var_2CC], 500h
0x18009f56f  mov     edx, ebx; TokenInformationClass
0x18009f571  mov     [rsp+300h+ReturnLength], rax; ReturnLength
0x18009f576  xor     r8d, r8d; TokenInformation
0x18009f579  mov     r15, rcx
0x18009f57c  call    cs:__imp_GetTokenInformation
0x18009f583  nop     dword ptr [rax+rax+00h]
0x18009f588  test    eax, eax
0x18009f58a  jz      short loc_18009F596
0x18009f58c  mov     ebx, 0Eh
0x18009f591  jmp     loc_18009F953
0x18009f596  call    cs:__imp_GetLastError
0x18009f59d  nop     dword ptr [rax+rax+00h]
0x18009f5a2  cmp     eax, 7Ah ; 'z'
0x18009f5a5  jz      short loc_18009F5C0
0x18009f5a7  mov     r8d, 0FDCh; unsigned __int16
0x18009f5ad  mov     [rsp+300h+ReturnLength], r13; struct tagParam *
0x18009f5b2  xor     r9d, r9d; int
0x18009f5b5  mov     edx, eax; int
0x18009f5b7  mov     ecx, ebx; unsigned int
0x18009f5b9  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18009f5be  jmp     short loc_18009F58C
0x18009f5c0  mov     ecx, [rsp+300h+TokenInformationLength]; dwBytes
0x18009f5c4  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009f5c9  mov     rdi, rax
0x18009f5cc  test    rax, rax
0x18009f5cf  jz      short loc_18009F58C
0x18009f5d1  mov     r9d, [rsp+300h+TokenInformationLength]; TokenInformationLength
0x18009f5d6  lea     rax, [rsp+300h+TokenInformationLength]
0x18009f5db  mov     r8, rdi; TokenInformation
0x18009f5de  mov     [rsp+300h+ReturnLength], rax; ReturnLength
0x18009f5e3  mov     edx, ebx; TokenInformationClass
0x18009f5e5  mov     rcx, r15; TokenHandle
0x18009f5e8  call    cs:__imp_GetTokenInformation
0x18009f5ef  nop     dword ptr [rax+rax+00h]
0x18009f5f4  test    eax, eax
0x18009f5f6  jnz     short loc_18009F625
0x18009f5f8  call    cs:__imp_GetLastError
0x18009f5ff  nop     dword ptr [rax+rax+00h]
0x18009f604  mov     r8d, 0FDDh; unsigned __int16
0x18009f60a  mov     [rsp+300h+ReturnLength], r13; struct tagParam *
0x18009f60f  mov     edx, eax; int
0x18009f611  xor     r9d, r9d; int
0x18009f614  mov     ecx, ebx; unsigned int
0x18009f616  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18009f61b  mov     ebx, 0Eh
0x18009f620  jmp     loc_18009F94B
0x18009f625  xor     r12d, r12d
0x18009f628  xor     esi, esi
0x18009f62a  cmp     [rdi], esi
0x18009f62c  jbe     loc_18009F6C9
0x18009f632  mov     ebx, esi
0x18009f634  add     rbx, rbx
0x18009f637  mov     rcx, [rdi+rbx*8+8]; pSid
0x18009f63c  call    cs:__imp_IsValidSid
0x18009f643  nop     dword ptr [rax+rax+00h]
0x18009f648  test    eax, eax
0x18009f64a  jz      short loc_18009F6BA
0x18009f64c  mov     rcx, [rdi+rbx*8+8]; pSid
0x18009f651  call    cs:__imp_GetSidIdentifierAuthority
0x18009f658  nop     dword ptr [rax+rax+00h]
0x18009f65d  mov     ecx, [rax]
0x18009f65f  sub     ecx, [rsp+300h+var_2D0]
0x18009f663  jnz     short loc_18009F670
0x18009f665  movzx   ecx, word ptr [rax+4]
0x18009f669  movzx   eax, [rsp+300h+var_2CC]
0x18009f66e  sub     ecx, eax
0x18009f670  test    ecx, ecx
0x18009f672  jnz     short loc_18009F6BA
0x18009f674  mov     rcx, [rdi+rbx*8+8]; pSid
0x18009f679  call    cs:__imp_GetSidSubAuthorityCount
0x18009f680  nop     dword ptr [rax+rax+00h]
0x18009f685  mov     r15, rax
0x18009f688  cmp     byte ptr [rax], 1
0x18009f68b  jb      short loc_18009F6BA
0x18009f68d  mov     rcx, [rdi+rbx*8+8]; pSid
0x18009f692  xor     edx, edx; nSubAuthority
0x18009f694  call    cs:__imp_GetSidSubAuthority
0x18009f69b  nop     dword ptr [rax+rax+00h]
0x18009f6a0  cmp     dword ptr [rax], 50h ; 'P'
0x18009f6a3  jnz     short loc_18009F6BA
0x18009f6a5  mov     cl, [r15]; nSubAuthorityCount
0x18009f6a8  call    cs:__imp_GetSidLengthRequired
0x18009f6af  nop     dword ptr [rax+rax+00h]
0x18009f6b4  add     r13d, eax
0x18009f6b7  inc     r12d
0x18009f6ba  inc     esi
0x18009f6bc  cmp     esi, [rdi]
0x18009f6be  jb      loc_18009F632
0x18009f6c4  mov     r15, [rsp+300h+var_2A8]
0x18009f6c9  mov     cl, 0Fh; nSubAuthorityCount
0x18009f6cb  call    cs:__imp_GetSidLengthRequired
0x18009f6d2  nop     dword ptr [rax+rax+00h]
0x18009f6d7  mov     edx, 0Ch
0x18009f6dc  cmp     eax, edx
0x18009f6de  jb      short loc_18009F6F0
0x18009f6e0  mov     cl, 0Fh; nSubAuthorityCount
0x18009f6e2  call    cs:__imp_GetSidLengthRequired
0x18009f6e9  nop     dword ptr [rax+rax+00h]
0x18009f6ee  mov     edx, eax
0x18009f6f0  lea     ecx, [r12+r12*2]
0x18009f6f4  add     r13d, 44h ; 'D'
0x18009f6f8  lea     ebx, [rdx+rcx*4]
0x18009f6fb  add     ebx, r13d
0x18009f6fe  mov     ecx, ebx; dwBytes
0x18009f700  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009f705  xor     r13d, r13d
0x18009f708  mov     [r14], rax
0x18009f70b  test    rax, rax
0x18009f70e  jz      loc_18009F61B
0x18009f714  lea     esi, [r13+2]
0x18009f718  mov     edx, ebx; nAclLength
0x18009f71a  mov     r8d, esi; dwAclRevision
0x18009f71d  mov     rcx, rax; pAcl
0x18009f720  call    cs:__imp_InitializeAcl
0x18009f727  nop     dword ptr [rax+rax+00h]
0x18009f72c  mov     rcx, [r14]; pAcl
0x18009f72f  lea     rbx, qword_1800E8320
0x18009f736  mov     r9, rbx; pSid
0x18009f739  mov     r8d, 12019Bh; AccessMask
0x18009f73f  mov     edx, esi; dwAceRevision
0x18009f741  call    cs:__imp_AddAccessAllowedAce
0x18009f748  nop     dword ptr [rax+rax+00h]
0x18009f74d  test    eax, eax
0x18009f74f  jz      loc_18009F90F
0x18009f755  mov     rcx, [r14]; pAcl
0x18009f758  lea     rbx, qword_1800E8310
0x18009f75f  mov     r9, rbx; pSid
0x18009f762  mov     r8d, 12019Bh; AccessMask
0x18009f768  mov     edx, esi; dwAceRevision
0x18009f76a  call    cs:__imp_AddAccessAllowedAce
0x18009f771  nop     dword ptr [rax+rax+00h]
0x18009f776  test    eax, eax
0x18009f778  jz      loc_18009F90F
0x18009f77e  mov     ebx, r13d
0x18009f781  cmp     ebx, [rdi]
0x18009f783  jnb     loc_18009F84B
0x18009f789  mov     esi, ebx
0x18009f78b  add     rsi, rsi
0x18009f78e  mov     rcx, [rdi+rsi*8+8]; pSid
0x18009f793  call    cs:__imp_IsValidSid
0x18009f79a  nop     dword ptr [rax+rax+00h]
0x18009f79f  test    eax, eax
0x18009f7a1  jz      loc_18009F83F
0x18009f7a7  mov     rcx, [rdi+rsi*8+8]; pSid
0x18009f7ac  call    cs:__imp_GetSidIdentifierAuthority
0x18009f7b3  nop     dword ptr [rax+rax+00h]
0x18009f7b8  mov     ecx, [rax]
0x18009f7ba  sub     ecx, [rsp+300h+var_2D0]
0x18009f7be  jnz     short loc_18009F7CB
0x18009f7c0  movzx   ecx, word ptr [rax+4]
0x18009f7c4  movzx   eax, [rsp+300h+var_2CC]
0x18009f7c9  sub     ecx, eax
0x18009f7cb  test    ecx, ecx
0x18009f7cd  jnz     short loc_18009F83F
0x18009f7cf  mov     rcx, [rdi+rsi*8+8]; pSid
0x18009f7d4  call    cs:__imp_GetSidSubAuthorityCount
0x18009f7db  nop     dword ptr [rax+rax+00h]
0x18009f7e0  cmp     byte ptr [rax], 1
0x18009f7e3  jb      short loc_18009F83F
0x18009f7e5  mov     rcx, [rdi+rsi*8+8]; pSid
0x18009f7ea  xor     edx, edx; nSubAuthority
0x18009f7ec  call    cs:__imp_GetSidSubAuthority
0x18009f7f3  nop     dword ptr [rax+rax+00h]
0x18009f7f8  cmp     dword ptr [rax], 50h ; 'P'
0x18009f7fb  jnz     short loc_18009F83F
0x18009f7fd  mov     r9, [rdi+rsi*8+8]; pSid
0x18009f802  mov     r8d, 1F01FFh; AccessMask
0x18009f808  mov     rcx, [r14]; pAcl
0x18009f80b  mov     esi, 2
0x18009f810  mov     edx, esi; dwAceRevision
0x18009f812  call    cs:__imp_AddAccessAllowedAce
0x18009f819  nop     dword ptr [rax+rax+00h]
0x18009f81e  test    eax, eax
0x18009f820  jnz     short loc_18009F844
0x18009f822  call    cs:__imp_GetLastError
0x18009f829  nop     dword ptr [rax+rax+00h]
0x18009f82e  lea     ecx, [rdi+8]
0x18009f831  shl     ebx, 4
0x18009f834  add     ecx, ebx
0x18009f836  mov     [rsp+300h+var_2B8], ecx
0x18009f83a  jmp     loc_18009F91F
0x18009f83f  mov     esi, 2
0x18009f844  inc     ebx
0x18009f846  jmp     loc_18009F781
0x18009f84b  test    r12d, r12d
0x18009f84e  jnz     loc_18009F8EA
0x18009f854  lea     ebx, [r12+4Ch]
0x18009f859  xor     edx, edx; Val
0x18009f85b  mov     r8d, 260h; Size
0x18009f861  mov     [rsp+300h+var_2D0], ebx
0x18009f865  lea     rcx, [rsp+300h+TokenInformation]; void *
0x18009f86a  call    memset_0
0x18009f86f  lea     rax, [rsp+300h+var_2D0]
0x18009f874  mov     r9d, ebx; TokenInformationLength
0x18009f877  lea     r8, [rsp+300h+TokenInformation]; TokenInformation
0x18009f87c  mov     [rsp+300h+ReturnLength], rax; ReturnLength
0x18009f881  lea     edx, [rbx-48h]; TokenInformationClass
0x18009f884  mov     rcx, r15; TokenHandle
0x18009f887  call    cs:__imp_GetTokenInformation
0x18009f88e  nop     dword ptr [rax+rax+00h]
0x18009f893  test    eax, eax
0x18009f895  jnz     short loc_18009F8B0
0x18009f897  call    cs:__imp_GetLastError
0x18009f89e  nop     dword ptr [rax+rax+00h]
0x18009f8a3  xor     r9d, r9d
0x18009f8a6  mov     [rsp+300h+ReturnLength], r13
0x18009f8ab  jmp     loc_18009F937
0x18009f8b0  mov     r9, [rsp+300h+TokenInformation]; pSid
0x18009f8b5  mov     r8d, 1F01FFh; AccessMask
0x18009f8bb  mov     rcx, [r14]; pAcl
0x18009f8be  mov     edx, esi; dwAceRevision
0x18009f8c0  call    cs:__imp_AddAccessAllowedAce
0x18009f8c7  nop     dword ptr [rax+rax+00h]
0x18009f8cc  test    eax, eax
0x18009f8ce  jnz     loc_18009F964
0x18009f8d4  call    cs:__imp_GetLastError
0x18009f8db  nop     dword ptr [rax+rax+00h]
0x18009f8e0  lea     rcx, [rsp+300h+TokenInformation]
0x18009f8e5  jmp     loc_18009F836
0x18009f8ea  mov     rcx, [r14]; pAcl
0x18009f8ed  lea     rbx, qword_1800E8330
0x18009f8f4  mov     r9, rbx; pSid
0x18009f8f7  mov     r8d, 20000h; AccessMask
0x18009f8fd  mov     edx, esi; dwAceRevision
0x18009f8ff  call    cs:__imp_AddAccessAllowedAce
0x18009f906  nop     dword ptr [rax+rax+00h]
0x18009f90b  test    eax, eax
0x18009f90d  jnz     short loc_18009F964
0x18009f90f  call    cs:__imp_GetLastError
0x18009f916  nop     dword ptr [rax+rax+00h]
0x18009f91b  mov     [rsp+300h+var_2B8], ebx
0x18009f91f  lea     rcx, [rsp+300h+var_2C0]
0x18009f924  mov     [rsp+300h+var_2C0], 3
0x18009f92c  mov     [rsp+300h+ReturnLength], rcx; struct tagParam *
0x18009f931  mov     r9d, 1; int
0x18009f937  mov     r8d, 0FE9h; unsigned __int16
0x18009f93d  mov     edx, eax; int
0x18009f93f  mov     ecx, esi; unsigned int
0x18009f941  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18009f946  mov     ebx, 6B9h
0x18009f94b  mov     rcx, rdi; lpMem
0x18009f94e  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009f953  mov     rcx, [r14]; lpMem
0x18009f956  test    rcx, rcx
0x18009f959  jz      short loc_18009F960
0x18009f95b  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009f960  mov     eax, ebx
0x18009f962  jmp     short loc_18009F96E
0x18009f964  mov     rcx, rdi; lpMem
0x18009f967  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009f96c  xor     eax, eax
0x18009f96e  mov     rcx, [rbp+200h+var_40]
0x18009f975  xor     rcx, rsp; StackCookie
0x18009f978  call    __security_check_cookie
0x18009f97d  mov     rbx, [rsp+300h+arg_10]
0x18009f985  add     rsp, 2D0h
0x18009f98c  pop     r15
0x18009f98e  pop     r14
0x18009f990  pop     r13
0x18009f992  pop     r12
0x18009f994  pop     rdi
0x18009f995  pop     rsi
0x18009f996  pop     rbp
0x18009f997  retn
```
