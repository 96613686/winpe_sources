# SspCreateTokenDacl

- ea: `0x18002bd34`
- end: `0x18002c35e`
- name: `SspCreateTokenDacl`
- size: `1578`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002dc18`

## callees

- `0x1800061a0`
- `0x180009770`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x1800192a8`
- `0x18002bd34`
- `0x1800328a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002c291`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002c291`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002bfc7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002bfc7`
- `ntdll!RtlEqualSid` at `0x18002c13a`
- `ntdll!RtlEqualSid` at `0x18002c152`
- `ntdll!RtlEqualSid` at `0x18002c13a`
- `ntdll!RtlEqualSid` at `0x18002c152`
- `ntdll!NtOpenThreadToken` at `0x18002bfbb`
- `ntdll!NtOpenThreadToken` at `0x18002bfbb`
- `ntdll!NtSetSecurityObject` at `0x18002c277`
- `ntdll!NtSetSecurityObject` at `0x18002c277`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002be56`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002bf29`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002be56`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002bf29`
- `ntdll!NtOpenProcessToken` at `0x18002c048`
- `ntdll!NtOpenProcessToken` at `0x18002c048`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002c253`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002c253`
- `ntdll!RtlCreateAcl` at `0x18002c1c3`
- `ntdll!RtlCreateAcl` at `0x18002c1c3`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c1e0`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c1f8`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c214`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c22c`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c244`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c1e0`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c1f8`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c214`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c22c`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002c244`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002c265`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002c265`
- `ntdll!RtlLengthSid` at `0x18002c0f3`
- `ntdll!RtlLengthSid` at `0x18002c0fe`
- `ntdll!RtlLengthSid` at `0x18002c10d`
- `ntdll!RtlLengthSid` at `0x18002c11c`
- `ntdll!RtlLengthSid` at `0x18002c163`
- `ntdll!RtlLengthSid` at `0x18002c0f3`
- `ntdll!RtlLengthSid` at `0x18002c0fe`
- `ntdll!RtlLengthSid` at `0x18002c10d`
- `ntdll!RtlLengthSid` at `0x18002c11c`
- `ntdll!RtlLengthSid` at `0x18002c163`
- `ntdll!NtClose` at `0x18002c29b`
- `ntdll!NtClose` at `0x18002c310`
- `ntdll!NtClose` at `0x18002c29b`
- `ntdll!NtClose` at `0x18002c310`
- `ntdll!RtlLeaveCriticalSection` at `0x18002bf62`
- `ntdll!RtlLeaveCriticalSection` at `0x18002bfa2`
- `ntdll!RtlLeaveCriticalSection` at `0x18002bf62`
- `ntdll!RtlLeaveCriticalSection` at `0x18002bfa2`
- `ntdll!RtlEnterCriticalSection` at `0x18002bde7`
- `ntdll!RtlEnterCriticalSection` at `0x18002bde7`

## pseudocode

```c
__int64 __fastcall SspCreateTokenDacl(HANDLE TokenHandle)
{
  struct _ACL *v2; // rdi
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  PVOID *v7; // rcx
  NTSTATUS TokenUser; // eax
  PVOID *v9; // rcx
  __int64 v10; // rdx
  void *v11; // rdi
  ULONG v12; // ebx
  ULONG v13; // ebx
  ULONG v14; // ebx
  ULONG v15; // ebx
  struct _ACL *Memory; // rax
  PSID Sid; // [rsp+78h] [rbp-41h] BYREF
  void *TokenHandlea; // [rsp+80h] [rbp-39h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-31h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-9h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B8h] [rbp-1h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v22 = 0;
  v2 = 0;
  Handle = 0;
  TokenHandlea = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, TokenHandle);
  if ( !g_NtDigestGlobalLocalSystemSid || !g_NtDigestGlobalAliasAdminsSid )
  {
    RtlEnterCriticalSection(&l_UserCtxtCritSect);
    if ( g_NtDigestGlobalLocalSystemSid )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      Sid = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids);
      v3 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
      v4 = v3;
      if ( v3 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_28;
        v6 = 30;
LABEL_27:
        WPP_SF_d(v5[2], v6, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, (unsigned int)v3);
LABEL_28:
        RtlLeaveCriticalSection(&l_UserCtxtCritSect);
LABEL_61:
        v9 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_62;
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      g_NtDigestGlobalLocalSystemSid = Sid;
    }
    if ( !g_NtDigestGlobalAliasAdminsSid )
    {
      Sid = 0;
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
        WPP_SF_(v7[2], 32, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids);
      v3 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
      v4 = v3;
      if ( v3 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_28;
        v6 = 33;
        goto LABEL_27;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids);
      g_NtDigestGlobalAliasAdminsSid = Sid;
    }
    RtlLeaveCriticalSection(&l_UserCtxtCritSect);
  }
  TokenUser = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandlea);
  v4 = TokenUser;
  if ( TokenUser >= 0 )
  {
    RevertToSelf();
    TokenUser = SspGetTokenUser(TokenHandlea);
    v4 = TokenUser;
    if ( TokenUser < 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 35;
LABEL_39:
        WPP_SF_d(v9[2], v10, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, (unsigned int)TokenUser);
        goto LABEL_61;
      }
      goto LABEL_62;
    }
LABEL_44:
    TokenUser = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &Handle);
    v4 = TokenUser;
    if ( TokenUser >= 0 )
    {
      TokenUser = SspGetTokenUser(Handle);
      v4 = TokenUser;
      if ( TokenUser >= 0 )
      {
        TokenUser = SspGetTokenUser(TokenHandle);
        v4 = TokenUser;
        if ( TokenUser >= 0 )
        {
          v11 = (void *)MEMORY[0];
          v12 = RtlLengthSid(MEMORY[0]);
          v13 = RtlLengthSid(v11) + v12;
          v14 = RtlLengthSid(g_NtDigestGlobalAliasAdminsSid) + v13;
          v15 = RtlLengthSid(g_NtDigestGlobalLocalSystemSid) + v14 + 40;
          Memory = (struct _ACL *)DigestAllocateMemory(v15);
          v2 = Memory;
          if ( Memory )
          {
            RtlCreateAcl(Memory, v15, 2u);
            RtlAddAccessAllowedAce(v2, 2u, 0xF01FFu, MEMORY[0]);
            RtlAddAccessAllowedAce(v2, 2u, 0xF01FFu, MEMORY[0]);
            RtlAddAccessAllowedAce(v2, 2u, 0xF01FFu, g_NtDigestGlobalAliasAdminsSid);
            RtlAddAccessAllowedAce(v2, 2u, 0xF01FFu, g_NtDigestGlobalLocalSystemSid);
            RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
            RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v2, 0);
            v4 = NtSetSecurityObject(TokenHandle, 4u, SecurityDescriptor);
            goto LABEL_61;
          }
          v4 = -1073741670;
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, 0);
            goto LABEL_61;
          }
        }
        else
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 39;
            goto LABEL_39;
          }
        }
      }
      else
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 38;
          goto LABEL_39;
        }
      }
    }
    else
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 37;
        goto LABEL_39;
      }
    }
    goto LABEL_62;
  }
  if ( TokenUser == -1073741700 )
    goto LABEL_44;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 36;
    goto LABEL_39;
  }
LABEL_62:
  if ( TokenHandlea )
  {
    SetThreadToken(0, TokenHandlea);
    NtClose(TokenHandlea);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    DigestFreeMemory(v2);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Handle )
  {
    NtClose(Handle);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && *((char *)v9 + 28) < 0 )
    WPP_SF_q(v9[2], 41, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x18002bd34  push    rbp
0x18002bd36  push    rbx
0x18002bd37  push    rsi
0x18002bd38  push    rdi
0x18002bd39  push    r12
0x18002bd3b  push    r13
0x18002bd3d  push    r14
0x18002bd3f  push    r15
0x18002bd41  lea     rbp, [rsp-1Fh]
0x18002bd46  sub     rsp, 0D8h
0x18002bd4d  mov     rax, cs:__security_cookie
0x18002bd54  xor     rax, rsp
0x18002bd57  mov     [rbp+57h+var_50], rax
0x18002bd5b  xor     r15d, r15d
0x18002bd5e  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18002bd64  xorps   xmm0, xmm0
0x18002bd67  mov     [rbp+57h+var_A0], r15
0x18002bd6b  xor     eax, eax
0x18002bd6d  mov     [rbp+57h+hMem], r15
0x18002bd71  mov     [rbp+57h+var_60], rax
0x18002bd75  mov     r14, rcx
0x18002bd78  mov     [rbp+57h+var_B0], r15
0x18002bd7c  mov     edi, r15d
0x18002bd7f  mov     [rbp+57h+Handle], r15
0x18002bd83  mov     [rbp+57h+TokenHandle], r15
0x18002bd87  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r15d
0x18002bd8b  movups  [rbp+57h+SecurityDescriptor], xmm0
0x18002bd8f  movups  [rbp+57h+var_70], xmm0
0x18002bd93  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd9a  lea     r12, WPP_GLOBAL_Control
0x18002bda1  lea     r13, WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids
0x18002bda8  cmp     rcx, r12
0x18002bdab  jz      short loc_18002BDC5
0x18002bdad  test    byte ptr [rcx+1Ch], 80h
0x18002bdb1  jz      short loc_18002BDC5
0x18002bdb3  mov     rcx, [rcx+10h]
0x18002bdb7  lea     edx, [rax+1Ch]
0x18002bdba  mov     r9, r14
0x18002bdbd  mov     r8, r13
0x18002bdc0  call    WPP_SF_q
0x18002bdc5  cmp     cs:g_NtDigestGlobalLocalSystemSid, r15
0x18002bdcc  mov     esi, 1
0x18002bdd1  jz      short loc_18002BDE0
0x18002bdd3  cmp     cs:g_NtDigestGlobalAliasAdminsSid, r15
0x18002bdda  jnz     loc_18002BFA8
0x18002bde0  lea     rcx, ?l_UserCtxtCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002bde7  call    cs:__imp_RtlEnterCriticalSection
0x18002bded  cmp     cs:g_NtDigestGlobalLocalSystemSid, r15
0x18002bdf4  jnz     loc_18002BEBD
0x18002bdfa  mov     [rbp+57h+var_98], r15
0x18002bdfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be05  cmp     rcx, r12
0x18002be08  jz      short loc_18002BE21
0x18002be0a  test    byte ptr [rcx+1Ch], 4
0x18002be0e  jz      short loc_18002BE21
0x18002be10  mov     rcx, [rcx+10h]
0x18002be14  mov     edx, 1Dh
0x18002be19  mov     r8, r13
0x18002be1c  call    WPP_SF_
0x18002be21  lea     rax, [rbp+57h+var_98]
0x18002be25  xor     r9d, r9d; SubAuthority1
0x18002be28  mov     [rsp+110h+Sid], rax; Sid
0x18002be2d  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18002be31  mov     [rsp+110h+SubAuthority7], r15d; SubAuthority7
0x18002be36  mov     dl, sil; SubAuthorityCount
0x18002be39  mov     [rsp+110h+SubAuthority6], r15d; SubAuthority6
0x18002be3e  mov     [rsp+110h+SubAuthority5], r15d; SubAuthority5
0x18002be43  lea     r8d, [r9+12h]; SubAuthority0
0x18002be47  mov     [rsp+110h+SubAuthority4], r15d; SubAuthority4
0x18002be4c  mov     [rsp+110h+SubAuthority3], r15d; SubAuthority3
0x18002be51  mov     [rsp+110h+SubAuthority2], r15d; SubAuthority2
0x18002be56  call    cs:__imp_RtlAllocateAndInitializeSid
0x18002be5c  mov     ebx, eax
0x18002be5e  test    eax, eax
0x18002be60  jns     short loc_18002BE86
0x18002be62  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be69  cmp     rcx, r12
0x18002be6c  jz      loc_18002BF5B
0x18002be72  test    [rcx+1Ch], sil
0x18002be76  jz      loc_18002BF5B
0x18002be7c  mov     edx, 1Eh
0x18002be81  jmp     loc_18002BF4C
0x18002be86  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be8d  cmp     rcx, r12
0x18002be90  jz      short loc_18002BEB0
0x18002be92  test    byte ptr [rcx+1Ch], 4
0x18002be96  jz      short loc_18002BEB0
0x18002be98  mov     rcx, [rcx+10h]
0x18002be9c  mov     edx, 1Fh
0x18002bea1  mov     r8, r13
0x18002bea4  call    WPP_SF_
0x18002bea9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002beb0  mov     rax, [rbp+57h+var_98]
0x18002beb4  mov     cs:g_NtDigestGlobalLocalSystemSid, rax
0x18002bebb  jmp     short loc_18002BEC4
0x18002bebd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bec4  cmp     cs:g_NtDigestGlobalAliasAdminsSid, r15
0x18002becb  jnz     loc_18002BF9B
0x18002bed1  mov     [rbp+57h+var_98], r15
0x18002bed5  mov     ebx, 20h ; ' '
0x18002beda  cmp     rcx, r12
0x18002bedd  jz      short loc_18002BEF3
0x18002bedf  test    byte ptr [rcx+1Ch], 4
0x18002bee3  jz      short loc_18002BEF3
0x18002bee5  mov     rcx, [rcx+10h]
0x18002bee9  mov     edx, ebx
0x18002beeb  mov     r8, r13
0x18002beee  call    WPP_SF_
0x18002bef3  lea     rax, [rbp+57h+var_98]
0x18002bef7  mov     r9d, 220h; SubAuthority1
0x18002befd  mov     [rsp+110h+Sid], rax; Sid
0x18002bf02  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18002bf06  mov     [rsp+110h+SubAuthority7], r15d; SubAuthority7
0x18002bf0b  mov     r8d, ebx; SubAuthority0
0x18002bf0e  mov     [rsp+110h+SubAuthority6], r15d; SubAuthority6
0x18002bf13  mov     dl, 2; SubAuthorityCount
0x18002bf15  mov     [rsp+110h+SubAuthority5], r15d; SubAuthority5
0x18002bf1a  mov     [rsp+110h+SubAuthority4], r15d; SubAuthority4
0x18002bf1f  mov     [rsp+110h+SubAuthority3], r15d; SubAuthority3
0x18002bf24  mov     [rsp+110h+SubAuthority2], r15d; SubAuthority2
0x18002bf29  call    cs:__imp_RtlAllocateAndInitializeSid
0x18002bf2f  mov     ebx, eax
0x18002bf31  test    eax, eax
0x18002bf33  jns     short loc_18002BF6D
0x18002bf35  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf3c  cmp     rcx, r12
0x18002bf3f  jz      short loc_18002BF5B
0x18002bf41  test    [rcx+1Ch], sil
0x18002bf45  jz      short loc_18002BF5B
0x18002bf47  mov     edx, 21h ; '!'
0x18002bf4c  mov     rcx, [rcx+10h]
0x18002bf50  mov     r9d, eax
0x18002bf53  mov     r8, r13
0x18002bf56  call    WPP_SF_d
0x18002bf5b  lea     rcx, ?l_UserCtxtCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002bf62  call    cs:__imp_RtlLeaveCriticalSection
0x18002bf68  jmp     loc_18002C27F
0x18002bf6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf74  cmp     rcx, r12
0x18002bf77  jz      short loc_18002BF90
0x18002bf79  test    byte ptr [rcx+1Ch], 4
0x18002bf7d  jz      short loc_18002BF90
0x18002bf7f  mov     rcx, [rcx+10h]
0x18002bf83  mov     edx, 22h ; '"'
0x18002bf88  mov     r8, r13
0x18002bf8b  call    WPP_SF_
0x18002bf90  mov     rax, [rbp+57h+var_98]
0x18002bf94  mov     cs:g_NtDigestGlobalAliasAdminsSid, rax
0x18002bf9b  lea     rcx, ?l_UserCtxtCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002bfa2  call    cs:__imp_RtlLeaveCriticalSection
0x18002bfa8  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18002bfac  mov     r8b, sil; OpenAsSelf
0x18002bfaf  mov     edx, 0Ch; DesiredAccess
0x18002bfb4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002bfbb  call    cs:__imp_NtOpenThreadToken
0x18002bfc1  mov     ebx, eax
0x18002bfc3  test    eax, eax
0x18002bfc5  js      short loc_18002C013
0x18002bfc7  call    cs:__imp_RevertToSelf
0x18002bfcd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002bfd1  lea     rdx, [rbp+57h+var_B0]
0x18002bfd5  call    SspGetTokenUser
0x18002bfda  mov     ebx, eax
0x18002bfdc  test    eax, eax
0x18002bfde  jns     short loc_18002C03B
0x18002bfe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfe7  cmp     rcx, r12
0x18002bfea  jz      loc_18002C286
0x18002bff0  test    [rcx+1Ch], sil
0x18002bff4  jz      loc_18002C286
0x18002bffa  mov     edx, 23h ; '#'
0x18002bfff  mov     rcx, [rcx+10h]
0x18002c003  mov     r9d, eax
0x18002c006  mov     r8, r13
0x18002c009  call    WPP_SF_d
0x18002c00e  jmp     loc_18002C27F
0x18002c013  cmp     eax, 0C000007Ch
0x18002c018  jz      short loc_18002C03B
0x18002c01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c021  cmp     rcx, r12
0x18002c024  jz      loc_18002C286
0x18002c02a  test    [rcx+1Ch], sil
0x18002c02e  jz      loc_18002C286
0x18002c034  mov     edx, 24h ; '$'
0x18002c039  jmp     short loc_18002BFFF
0x18002c03b  lea     r8, [rbp+57h+Handle]; TokenHandle
0x18002c03f  mov     edx, 8; DesiredAccess
0x18002c044  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18002c048  call    cs:__imp_NtOpenProcessToken
0x18002c04e  mov     ebx, eax
0x18002c050  test    eax, eax
0x18002c052  jns     short loc_18002C075
0x18002c054  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c05b  cmp     rcx, r12
0x18002c05e  jz      loc_18002C286
0x18002c064  test    [rcx+1Ch], sil
0x18002c068  jz      loc_18002C286
0x18002c06e  mov     edx, 25h ; '%'
0x18002c073  jmp     short loc_18002BFFF
0x18002c075  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x18002c079  lea     rdx, [rbp+57h+var_A0]
0x18002c07d  call    SspGetTokenUser
0x18002c082  mov     ebx, eax
0x18002c084  test    eax, eax
0x18002c086  jns     short loc_18002C0AC
0x18002c088  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c08f  cmp     rcx, r12
0x18002c092  jz      loc_18002C286
0x18002c098  test    [rcx+1Ch], sil
0x18002c09c  jz      loc_18002C286
0x18002c0a2  mov     edx, 26h ; '&'
0x18002c0a7  jmp     loc_18002BFFF
0x18002c0ac  lea     rdx, [rbp+57h+hMem]
0x18002c0b0  mov     rcx, r14; TokenHandle
0x18002c0b3  call    SspGetTokenUser
0x18002c0b8  mov     ebx, eax
0x18002c0ba  test    eax, eax
0x18002c0bc  jns     short loc_18002C0E2
0x18002c0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0c5  cmp     rcx, r12
0x18002c0c8  jz      loc_18002C286
0x18002c0ce  test    [rcx+1Ch], sil
0x18002c0d2  jz      loc_18002C286
0x18002c0d8  mov     edx, 27h ; '''
0x18002c0dd  jmp     loc_18002BFFF
0x18002c0e2  mov     rcx, [rbp+57h+var_A0]
0x18002c0e6  mov     esi, r15d
0x18002c0e9  mov     rax, [rbp+57h+hMem]
0x18002c0ed  mov     rcx, [rcx]; Sid
0x18002c0f0  mov     rdi, [rax]
0x18002c0f3  call    cs:__imp_RtlLengthSid
0x18002c0f9  mov     rcx, rdi; Sid
0x18002c0fc  mov     ebx, eax
0x18002c0fe  call    cs:__imp_RtlLengthSid
0x18002c104  mov     rcx, cs:g_NtDigestGlobalAliasAdminsSid; Sid
0x18002c10b  add     ebx, eax
0x18002c10d  call    cs:__imp_RtlLengthSid
0x18002c113  mov     rcx, cs:g_NtDigestGlobalLocalSystemSid; Sid
0x18002c11a  add     ebx, eax
0x18002c11c  call    cs:__imp_RtlLengthSid
0x18002c122  mov     rcx, [rbp+57h+var_B0]
0x18002c126  add     ebx, 28h ; '('
0x18002c129  add     ebx, eax
0x18002c12b  test    rcx, rcx
0x18002c12e  jz      short loc_18002C173
0x18002c130  mov     rdx, [rbp+57h+var_A0]
0x18002c134  mov     rcx, [rcx]; Sid1
0x18002c137  mov     rdx, [rdx]; Sid2
0x18002c13a  call    cs:__imp_RtlEqualSid
0x18002c140  test    al, al
0x18002c142  jnz     short loc_18002C173
0x18002c144  mov     rdx, [rbp+57h+hMem]
0x18002c148  mov     rcx, [rbp+57h+var_B0]
0x18002c14c  mov     rdx, [rdx]; Sid2
0x18002c14f  mov     rcx, [rcx]; Sid1
0x18002c152  call    cs:__imp_RtlEqualSid
0x18002c158  test    al, al
0x18002c15a  jnz     short loc_18002C173
0x18002c15c  mov     rcx, [rbp+57h+var_B0]
0x18002c160  mov     rcx, [rcx]; Sid
0x18002c163  call    cs:__imp_RtlLengthSid
0x18002c169  add     ebx, 8
0x18002c16c  mov     esi, 1
0x18002c171  add     ebx, eax
0x18002c173  mov     ecx, ebx; Size
0x18002c175  call    DigestAllocateMemory
0x18002c17a  mov     rdi, rax
0x18002c17d  test    rax, rax
0x18002c180  jnz     short loc_18002C1B8
0x18002c182  mov     ebx, 0C000009Ah
0x18002c187  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c18e  cmp     rcx, r12
0x18002c191  jz      loc_18002C286
0x18002c197  test    byte ptr [rcx+1Ch], 1
0x18002c19b  jz      loc_18002C286
0x18002c1a1  mov     rcx, [rcx+10h]
0x18002c1a5  lea     edx, [rax+28h]
0x18002c1a8  xor     r9d, r9d
0x18002c1ab  mov     r8, r13
0x18002c1ae  call    WPP_SF_q
0x18002c1b3  jmp     loc_18002C27F
0x18002c1b8  mov     r8d, 2; AclRevision
0x18002c1be  mov     edx, ebx; AclSize
0x18002c1c0  mov     rcx, rdi; Acl
0x18002c1c3  call    cs:__imp_RtlCreateAcl
0x18002c1c9  mov     r9, [rbp+57h+var_A0]
0x18002c1cd  mov     ebx, 0F01FFh
0x18002c1d2  mov     r8d, ebx; AccessMask
0x18002c1d5  mov     edx, 2; Revision
0x18002c1da  mov     rcx, rdi; Acl
0x18002c1dd  mov     r9, [r9]; Sid
0x18002c1e0  call    cs:__imp_RtlAddAccessAllowedAce
0x18002c1e6  mov     r9, [rbp+57h+hMem]
0x18002c1ea  mov     r8d, ebx; AccessMask
0x18002c1ed  mov     edx, 2; Revision
0x18002c1f2  mov     rcx, rdi; Acl
0x18002c1f5  mov     r9, [r9]; Sid
0x18002c1f8  call    cs:__imp_RtlAddAccessAllowedAce
0x18002c1fe  test    esi, esi
0x18002c200  jz      short loc_18002C21A
  ... truncated ...
```
