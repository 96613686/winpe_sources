# CRdpDrUtil::CreateDefaultPrinterSecuritySD(void *,int)

- ea: `0x180004190`
- end: `0x180004679`
- name: `?CreateDefaultPrinterSecuritySD@CRdpDrUtil@@QEAAPEAXPEAXH@Z`
- size: `1257`
- prototype: `void *(CRdpDrUtil *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003f20`

## callees

- `0x180004190`
- `0x180009e50`
- `0x18000a230`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000423a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000428c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000430c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000423a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000428c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000430c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004657`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004382`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004382`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000464c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000464c`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180004594`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x180004594`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800045b8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800045b8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800043a7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800043a7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800043c1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800043c1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000432f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004341`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000434c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004358`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004365`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000432f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004341`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000434c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004358`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004365`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800045e4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000460b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004619`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004630`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000463f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800045e4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000460b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004619`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004630`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000463f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004230`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004282`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800042df`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004230`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004282`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800042df`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800043ef`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004418`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004441`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000446d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004499`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800044c5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800044f1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004516`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000453e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004562`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004586`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800043ef`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004418`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004441`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000446d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004499`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800044c5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800044f1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004516`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000453e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004562`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004586`

## pseudocode

```c
struct _ACL *__fastcall CRdpDrUtil::CreateDefaultPrinterSecuritySD(CRdpDrUtil *this, void *a2, int a3)
{
  void *UserSid; // r15
  void *SessionSid; // r14
  struct _ACL *v7; // r13
  DWORD LastError; // ebx
  DWORD LengthSid; // edi
  DWORD v10; // esi
  DWORD v11; // ebx
  DWORD v12; // eax
  DWORD v13; // ebx
  struct _ACL *v14; // rax
  struct _ACL *v15; // rsi
  PSID pSid; // [rsp+68h] [rbp-9h] BYREF
  DWORD v18; // [rsp+70h] [rbp-1h]
  PSID v19; // [rsp+78h] [rbp+7h] BYREF
  PSID v20; // [rsp+80h] [rbp+Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v22; // [rsp+90h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v23; // [rsp+98h] [rbp+27h] BYREF

  UserSid = 0;
  v19 = 0;
  SessionSid = 0;
  v20 = 0;
  v7 = 0;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v23.Value = 0;
  *(_WORD *)&v23.Value[4] = 768;
  *(_DWORD *)v22.Value = 0;
  *(_WORD *)&v22.Value[4] = 3840;
  if ( !a3 && !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x226u, 0, 0, 0, 0, 0, 0, &v20) )
  {
    LastError = GetLastError();
    GetLastError();
    goto LABEL_31;
  }
  if ( !AllocateAndInitializeSid(&v22, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_30;
  UserSid = TSNUTL_GetUserSid(a2);
  if ( !UserSid )
    goto LABEL_30;
  if ( !AllocateAndInitializeSid(&v23, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v19) || (SessionSid = TSNUTL_GetSessionSid(a2)) == 0 )
  {
    LastError = GetLastError();
    GetLastError();
    goto LABEL_31;
  }
  v18 = 8;
  if ( !a3 )
    v18 = 3 * GetLengthSid(v20) + 32;
  LengthSid = GetLengthSid(SessionSid);
  v10 = GetLengthSid(UserSid);
  v11 = 2 * GetLengthSid(v19);
  v12 = GetLengthSid(pSid);
  v13 = v18 + v10 + LengthSid + v12 + 24 + v11 + 2 * (LengthSid + v12 + 24);
  v14 = (struct _ACL *)LocalAlloc(0, v13 + 40LL);
  v15 = v14;
  if ( !v14 )
  {
    LastError = 14;
LABEL_32:
    SetLastError(LastError);
LABEL_33:
    if ( !SessionSid )
      goto LABEL_35;
    goto LABEL_34;
  }
  v7 = v14;
  if ( !InitializeSecurityDescriptor(v14, 1u)
    || !InitializeAcl(v15 + 5, v13, 2u)
    || !a3
    && (!AddAccessAllowedAceEx(v15 + 5, 2u, 0, 0x20008u, v20) || !AddAccessAllowedAceEx(v15 + 5, 2u, 0, 0x80000u, v20)) )
  {
    goto LABEL_30;
  }
  if ( !AddAccessAllowedAceEx(v15 + 5, 2u, 0, 0x20008u, pSid)
    || !AddAccessAllowedAceEx(v15 + 5, 2u, 9u, 0x20000u, pSid)
    || !AddAccessAllowedAceEx(v15 + 5, 2u, 9u, 0xF0030u, pSid)
    || !AddAccessAllowedAceEx(v15 + 5, 2u, 9u, 0x20000u, v19)
    || !AddAccessAllowedAceEx(v15 + 5, 2u, 9u, 0xF0030u, v19)
    || !AddAccessAllowedAceEx(v15 + 5, 2u, 0, 0x20008u, SessionSid)
    || !AddAccessAllowedAceEx(v15 + 5, 2u, 0xAu, 0x20000u, SessionSid)
    || !AddAccessAllowedAceEx(v15 + 5, 2u, 9u, 0xF0030u, SessionSid)
    || !AddAccessAllowedAceEx(v15 + 5, 2u, 9u, 0x10000u, UserSid) )
  {
    goto LABEL_30;
  }
  if ( !IsValidAcl(v15 + 5) )
  {
    LastError = 1336;
    goto LABEL_32;
  }
  LastError = 0;
  if ( !SetSecurityDescriptorDacl(v15, 1, v15 + 5, 0) )
  {
LABEL_30:
    LastError = GetLastError();
LABEL_31:
    if ( !LastError )
      goto LABEL_33;
    goto LABEL_32;
  }
LABEL_34:
  FreeSid(SessionSid);
LABEL_35:
  if ( v19 )
    FreeSid(v19);
  if ( UserSid )
    FreeSid(UserSid);
  if ( v20 )
    FreeSid(v20);
  if ( pSid )
    FreeSid(pSid);
  if ( LastError )
  {
    LocalFree(v7);
    v7 = 0;
  }
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x180004190  mov     r11, rsp
0x180004193  push    rbp
0x180004194  push    rbx
0x180004195  push    rdi
0x180004196  push    r13
0x180004198  lea     rbp, [r11-5Fh]
0x18000419c  sub     rsp, 0A8h
0x1800041a3  mov     rax, cs:__security_cookie
0x1800041aa  xor     rax, rsp
0x1800041ad  mov     [rbp+57h+var_28], rax
0x1800041b1  xor     edi, edi
0x1800041b3  mov     [r11+8], rsi
0x1800041b7  mov     [r11+18h], r12
0x1800041bb  mov     r12d, r8d
0x1800041be  mov     [r11+20h], r14
0x1800041c2  mov     rbx, rdx
0x1800041c5  mov     [r11-28h], r15
0x1800041c9  mov     r15d, edi
0x1800041cc  mov     [rbp+57h+var_50], rdi
0x1800041d0  mov     r14d, edi
0x1800041d3  mov     [rbp+57h+var_48], rdi
0x1800041d7  mov     r13d, edi
0x1800041da  mov     [rbp+57h+pSid], rdi
0x1800041de  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1800041e1  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800041e7  mov     dword ptr [rbp+57h+var_30.Value], edi
0x1800041ea  mov     word ptr [rbp+57h+var_30.Value+4], 300h
0x1800041f0  mov     dword ptr [rbp+57h+var_38.Value], edi
0x1800041f3  mov     word ptr [rbp+57h+var_38.Value+4], 0F00h
0x1800041f9  test    r8d, r8d
0x1800041fc  jnz     short loc_18000424D
0x1800041fe  lea     rax, [rbp+57h+var_48]
0x180004202  mov     r9d, 226h; nSubAuthority1
0x180004208  mov     [r11-78h], rax
0x18000420c  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180004210  mov     [rsp+0C0h+nSubAuthority7], edi; nSubAuthority7
0x180004214  mov     r8d, 20h ; ' '; nSubAuthority0
0x18000421a  mov     [rsp+0C0h+nSubAuthority6], edi; nSubAuthority6
0x18000421e  mov     dl, 2; nSubAuthorityCount
0x180004220  mov     [rsp+0C0h+nSubAuthority5], edi; nSubAuthority5
0x180004224  mov     [rsp+0C0h+nSubAuthority4], edi; nSubAuthority4
0x180004228  mov     [rsp+0C0h+nSubAuthority3], edi; nSubAuthority3
0x18000422c  mov     [rsp+0C0h+nSubAuthority2], edi; nSubAuthority2
0x180004230  call    cs:__imp_AllocateAndInitializeSid
0x180004236  test    eax, eax
0x180004238  jnz     short loc_18000424D
0x18000423a  call    cs:__imp_GetLastError
0x180004240  mov     ebx, eax
0x180004242  call    cs:__imp_GetLastError
0x180004248  jmp     loc_1800045CC
0x18000424d  lea     rax, [rbp+57h+pSid]
0x180004251  mov     r8d, 2; nSubAuthority0
0x180004257  mov     [rsp+50h], rax; pSid
0x18000425c  lea     rcx, [rbp+57h+var_38]; pIdentifierAuthority
0x180004260  mov     [rsp+0C0h+nSubAuthority7], edi; nSubAuthority7
0x180004264  mov     r9d, 1; nSubAuthority1
0x18000426a  mov     [rsp+0C0h+nSubAuthority6], edi; nSubAuthority6
0x18000426e  movzx   edx, r8b; nSubAuthorityCount
0x180004272  mov     [rsp+0C0h+nSubAuthority5], edi; nSubAuthority5
0x180004276  mov     [rsp+0C0h+nSubAuthority4], edi; nSubAuthority4
0x18000427a  mov     [rsp+0C0h+nSubAuthority3], edi; nSubAuthority3
0x18000427e  mov     [rsp+0C0h+nSubAuthority2], edi; nSubAuthority2
0x180004282  call    cs:__imp_AllocateAndInitializeSid
0x180004288  test    eax, eax
0x18000428a  jnz     short loc_180004297
0x18000428c  call    cs:__imp_GetLastError
0x180004292  jmp     loc_1800045CA
0x180004297  mov     rcx, rbx; TokenHandle
0x18000429a  call    ?TSNUTL_GetUserSid@@YAPEAXPEAX@Z; TSNUTL_GetUserSid(void *)
0x18000429f  mov     r15, rax
0x1800042a2  test    rax, rax
0x1800042a5  jnz     short loc_1800042B2
0x1800042a7  call    cs:__imp_GetLastError
0x1800042ad  jmp     loc_1800045CA
0x1800042b2  lea     rax, [rbp+57h+var_50]
0x1800042b6  xor     r9d, r9d; nSubAuthority1
0x1800042b9  mov     [rsp+50h], rax; pSid
0x1800042be  lea     rcx, [rbp+57h+var_30]; pIdentifierAuthority
0x1800042c2  mov     [rsp+0C0h+nSubAuthority7], edi; nSubAuthority7
0x1800042c6  xor     r8d, r8d; nSubAuthority0
0x1800042c9  mov     [rsp+0C0h+nSubAuthority6], edi; nSubAuthority6
0x1800042cd  mov     dl, 1; nSubAuthorityCount
0x1800042cf  mov     [rsp+0C0h+nSubAuthority5], edi; nSubAuthority5
0x1800042d3  mov     [rsp+0C0h+nSubAuthority4], edi; nSubAuthority4
0x1800042d7  mov     [rsp+0C0h+nSubAuthority3], edi; nSubAuthority3
0x1800042db  mov     [rsp+0C0h+nSubAuthority2], edi; nSubAuthority2
0x1800042df  call    cs:__imp_AllocateAndInitializeSid
0x1800042e5  test    eax, eax
0x1800042e7  jnz     short loc_1800042FC
0x1800042e9  call    cs:__imp_GetLastError
0x1800042ef  mov     ebx, eax
0x1800042f1  call    cs:__imp_GetLastError
0x1800042f7  jmp     loc_1800045CC
0x1800042fc  mov     rcx, rbx; TokenHandle
0x1800042ff  call    ?TSNUTL_GetSessionSid@@YAPEAXPEAX@Z; TSNUTL_GetSessionSid(void *)
0x180004304  mov     r14, rax
0x180004307  test    rax, rax
0x18000430a  jnz     short loc_18000431F
0x18000430c  call    cs:__imp_GetLastError
0x180004312  mov     ebx, eax
0x180004314  call    cs:__imp_GetLastError
0x18000431a  jmp     loc_1800045CC
0x18000431f  mov     [rbp+57h+var_58], 8
0x180004326  test    r12d, r12d
0x180004329  jnz     short loc_18000433E
0x18000432b  mov     rcx, [rbp+57h+var_48]; pSid
0x18000432f  call    cs:__imp_GetLengthSid
0x180004335  lea     eax, [rax+rax*2]
0x180004338  add     eax, 20h ; ' '
0x18000433b  mov     [rbp+57h+var_58], eax
0x18000433e  mov     rcx, r14; pSid
0x180004341  call    cs:__imp_GetLengthSid
0x180004347  mov     rcx, r15; pSid
0x18000434a  mov     edi, eax
0x18000434c  call    cs:__imp_GetLengthSid
0x180004352  mov     rcx, [rbp+57h+var_50]; pSid
0x180004356  mov     esi, eax
0x180004358  call    cs:__imp_GetLengthSid
0x18000435e  mov     rcx, [rbp+57h+pSid]; pSid
0x180004362  lea     ebx, [rax+rax]
0x180004365  call    cs:__imp_GetLengthSid
0x18000436b  xor     ecx, ecx; uFlags
0x18000436d  lea     edx, [rax+18h]
0x180004370  add     edx, edi
0x180004372  lea     ebx, [rbx+rdx*2]
0x180004375  add     ebx, edx
0x180004377  add     ebx, esi
0x180004379  add     ebx, [rbp+57h+var_58]
0x18000437c  mov     edx, ebx
0x18000437e  add     rdx, 28h ; '('; uBytes
0x180004382  call    cs:__imp_LocalAlloc
0x180004388  mov     rsi, rax
0x18000438b  test    rax, rax
0x18000438e  jnz     short loc_18000439C
0x180004390  mov     ebx, 0Eh
0x180004395  xor     edi, edi
0x180004397  jmp     loc_1800045D0
0x18000439c  mov     edx, 1; dwRevision
0x1800043a1  mov     rcx, rsi; pSecurityDescriptor
0x1800043a4  mov     r13, rsi
0x1800043a7  call    cs:__imp_InitializeSecurityDescriptor
0x1800043ad  test    eax, eax
0x1800043af  jz      loc_1800045C2
0x1800043b5  mov     r8d, 2; dwAclRevision
0x1800043bb  lea     rcx, [rsi+28h]; pAcl
0x1800043bf  mov     edx, ebx; nAclLength
0x1800043c1  call    cs:__imp_InitializeAcl
0x1800043c7  test    eax, eax
0x1800043c9  jz      loc_1800045C2
0x1800043cf  test    r12d, r12d
0x1800043d2  jnz     short loc_180004426
0x1800043d4  mov     rax, [rbp+57h+var_48]
0x1800043d8  lea     rcx, [rsi+28h]; pAcl
0x1800043dc  mov     r9d, 20008h; AccessMask
0x1800043e2  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; pSid
0x1800043e7  xor     r8d, r8d; AceFlags
0x1800043ea  mov     edx, 2; dwAceRevision
0x1800043ef  call    cs:__imp_AddAccessAllowedAceEx
0x1800043f5  test    eax, eax
0x1800043f7  jz      loc_1800045C2
0x1800043fd  mov     rax, [rbp+57h+var_48]
0x180004401  lea     rcx, [rsi+28h]; pAcl
0x180004405  mov     r9d, 80000h; AccessMask
0x18000440b  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; pSid
0x180004410  xor     r8d, r8d; AceFlags
0x180004413  mov     edx, 2; dwAceRevision
0x180004418  call    cs:__imp_AddAccessAllowedAceEx
0x18000441e  test    eax, eax
0x180004420  jz      loc_1800045C2
0x180004426  mov     rax, [rbp+57h+pSid]
0x18000442a  lea     rcx, [rsi+28h]; pAcl
0x18000442e  mov     r9d, 20008h; AccessMask
0x180004434  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; pSid
0x180004439  xor     r8d, r8d; AceFlags
0x18000443c  mov     edx, 2; dwAceRevision
0x180004441  call    cs:__imp_AddAccessAllowedAceEx
0x180004447  test    eax, eax
0x180004449  jz      loc_1800045C2
0x18000444f  mov     rax, [rbp+57h+pSid]
0x180004453  lea     rcx, [rsi+28h]; pAcl
0x180004457  mov     edx, 2; dwAceRevision
0x18000445c  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; pSid
0x180004461  mov     r9d, 20000h; AccessMask
0x180004467  mov     r8d, 9; AceFlags
0x18000446d  call    cs:__imp_AddAccessAllowedAceEx
0x180004473  test    eax, eax
0x180004475  jz      loc_1800045C2
0x18000447b  mov     rax, [rbp+57h+pSid]
0x18000447f  lea     rcx, [rsi+28h]; pAcl
0x180004483  mov     edx, 2; dwAceRevision
0x180004488  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; pSid
0x18000448d  mov     r9d, 0F0030h; AccessMask
0x180004493  mov     r8d, 9; AceFlags
0x180004499  call    cs:__imp_AddAccessAllowedAceEx
0x18000449f  test    eax, eax
0x1800044a1  jz      loc_1800045C2
0x1800044a7  mov     rax, [rbp+57h+var_50]
0x1800044ab  lea     rcx, [rsi+28h]; pAcl
0x1800044af  mov     edx, 2; dwAceRevision
0x1800044b4  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; pSid
0x1800044b9  mov     r9d, 20000h; AccessMask
0x1800044bf  mov     r8d, 9; AceFlags
0x1800044c5  call    cs:__imp_AddAccessAllowedAceEx
0x1800044cb  test    eax, eax
0x1800044cd  jz      loc_1800045C2
0x1800044d3  mov     rax, [rbp+57h+var_50]
0x1800044d7  lea     rcx, [rsi+28h]; pAcl
0x1800044db  mov     edx, 2; dwAceRevision
0x1800044e0  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; pSid
0x1800044e5  mov     r9d, 0F0030h; AccessMask
0x1800044eb  mov     r8d, 9; AceFlags
0x1800044f1  call    cs:__imp_AddAccessAllowedAceEx
0x1800044f7  test    eax, eax
0x1800044f9  jz      loc_1800045C2
0x1800044ff  mov     r9d, 20008h; AccessMask
0x180004505  mov     qword ptr [rsp+0C0h+nSubAuthority2], r14; pSid
0x18000450a  xor     r8d, r8d; AceFlags
0x18000450d  lea     rcx, [rsi+28h]; pAcl
0x180004511  mov     edx, 2; dwAceRevision
0x180004516  call    cs:__imp_AddAccessAllowedAceEx
0x18000451c  test    eax, eax
0x18000451e  jz      loc_1800045C2
0x180004524  mov     edx, 2; dwAceRevision
0x180004529  mov     qword ptr [rsp+0C0h+nSubAuthority2], r14; pSid
0x18000452e  mov     r9d, 20000h; AccessMask
0x180004534  lea     rcx, [rsi+28h]; pAcl
0x180004538  mov     r8d, 0Ah; AceFlags
0x18000453e  call    cs:__imp_AddAccessAllowedAceEx
0x180004544  test    eax, eax
0x180004546  jz      short loc_1800045C2
0x180004548  mov     edx, 2; dwAceRevision
0x18000454d  mov     qword ptr [rsp+0C0h+nSubAuthority2], r14; pSid
0x180004552  mov     r9d, 0F0030h; AccessMask
0x180004558  lea     rcx, [rsi+28h]; pAcl
0x18000455c  mov     r8d, 9; AceFlags
0x180004562  call    cs:__imp_AddAccessAllowedAceEx
0x180004568  test    eax, eax
0x18000456a  jz      short loc_1800045C2
0x18000456c  mov     edx, 2; dwAceRevision
0x180004571  mov     qword ptr [rsp+0C0h+nSubAuthority2], r15; pSid
0x180004576  mov     r9d, 10000h; AccessMask
0x18000457c  lea     rcx, [rsi+28h]; pAcl
0x180004580  mov     r8d, 9; AceFlags
0x180004586  call    cs:__imp_AddAccessAllowedAceEx
0x18000458c  test    eax, eax
0x18000458e  jz      short loc_1800045C2
0x180004590  lea     rcx, [rsi+28h]; pAcl
0x180004594  call    cs:__imp_IsValidAcl
0x18000459a  test    eax, eax
0x18000459c  jnz     short loc_1800045A7
0x18000459e  mov     ebx, 538h
0x1800045a3  xor     edi, edi
0x1800045a5  jmp     short loc_1800045D0
0x1800045a7  xor     r9d, r9d; bDaclDefaulted
0x1800045aa  lea     r8, [rsi+28h]; pDacl
0x1800045ae  mov     edx, 1; bDaclPresent
0x1800045b3  mov     rcx, rsi; pSecurityDescriptor
0x1800045b6  xor     ebx, ebx
0x1800045b8  call    cs:__imp_SetSecurityDescriptorDacl
0x1800045be  test    eax, eax
0x1800045c0  jnz     short loc_1800045DF
0x1800045c2  call    cs:__imp_GetLastError
0x1800045c8  xor     edi, edi
0x1800045ca  mov     ebx, eax
0x1800045cc  test    ebx, ebx
0x1800045ce  jz      short loc_1800045D8
0x1800045d0  mov     ecx, ebx; dwErrCode
0x1800045d2  call    cs:__imp_SetLastError
0x1800045d8  test    r14, r14
0x1800045db  jnz     short loc_1800045E1
0x1800045dd  jmp     short loc_1800045EA
0x1800045df  xor     edi, edi
0x1800045e1  mov     rcx, r14; pSid
0x1800045e4  call    cs:__imp_FreeSid
0x1800045ea  mov     rcx, [rbp+57h+var_50]; pSid
0x1800045ee  mov     r14, [rsp+0C0h+arg_18]
0x1800045f6  mov     r12, [rsp+0C0h+arg_10]
0x1800045fe  mov     rsi, [rsp+0C0h+arg_0]
0x180004606  test    rcx, rcx
0x180004609  jz      short loc_180004611
0x18000460b  call    cs:__imp_FreeSid
0x180004611  test    r15, r15
0x180004614  jz      short loc_18000461F
0x180004616  mov     rcx, r15; pSid
0x180004619  call    cs:__imp_FreeSid
0x18000461f  mov     rcx, [rbp+57h+var_48]; pSid
0x180004623  mov     r15, [rsp+0A0h]
0x18000462b  test    rcx, rcx
0x18000462e  jz      short loc_180004636
0x180004630  call    cs:__imp_FreeSid
0x180004636  mov     rcx, [rbp+57h+pSid]; pSid
0x18000463a  test    rcx, rcx
0x18000463d  jz      short loc_180004645
0x18000463f  call    cs:__imp_FreeSid
0x180004645  test    ebx, ebx
0x180004647  jz      short loc_180004655
0x180004649  mov     rcx, r13; hMem
0x18000464c  call    cs:__imp_LocalFree
0x180004652  mov     r13, rdi
0x180004655  mov     ecx, ebx; dwErrCode
  ... truncated ...
```
