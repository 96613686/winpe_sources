# SrvLibApplyDeviceAcl

- ea: `0x140056010`
- end: `0x1400564e7`
- name: `SrvLibApplyDeviceAcl`
- size: `1239`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK, ACCESS_MASK)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000fc18`
- `0x14005b3c8`

## callees

- `0x140007c60`
- `0x140007ec0`
- `0x14002a3e0`
- `0x140056010`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14005606e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400560d6`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140056109`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140056137`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14005606e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400560d6`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140056109`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140056137`
- `ntoskrnl!RtlInitializeSid` at `0x14005616d`
- `ntoskrnl!RtlInitializeSid` at `0x140056183`
- `ntoskrnl!RtlInitializeSid` at `0x140056199`
- `ntoskrnl!RtlInitializeSid` at `0x1400561af`
- `ntoskrnl!RtlInitializeSid` at `0x1400561c5`
- `ntoskrnl!RtlInitializeSid` at `0x14005616d`
- `ntoskrnl!RtlInitializeSid` at `0x140056183`
- `ntoskrnl!RtlInitializeSid` at `0x140056199`
- `ntoskrnl!RtlInitializeSid` at `0x1400561af`
- `ntoskrnl!RtlInitializeSid` at `0x1400561c5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400561d6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400561f0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005620a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056226`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005623e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056256`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005626d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056285`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005629d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400562b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400562cc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400562e4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400562fb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056312`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005632a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056341`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400561d6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400561f0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005620a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056226`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005623e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056256`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005626d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056285`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005629d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400562b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400562cc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400562e4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400562fb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056312`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14005632a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140056341`
- `ntoskrnl!RtlCreateAcl` at `0x14005638e`
- `ntoskrnl!RtlCreateAcl` at `0x14005638e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400563b1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400563cf`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400563ed`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14005640a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140056427`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400563b1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400563cf`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400563ed`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14005640a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140056427`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14005643c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14005643c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140056454`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140056454`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14005646d`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14005646d`

## pseudocode

```c
__int64 __fastcall SrvLibApplyDeviceAcl(
        __int64 a1,
        ACCESS_MASK a2,
        ACCESS_MASK a3,
        ACCESS_MASK a4,
        ACCESS_MASK a5,
        ACCESS_MASK a6)
{
  void *v6; // rsi
  void *PoolWithTag; // r13
  unsigned int v8; // ebx
  void *v9; // r14
  void *v10; // r15
  struct _ACL *v11; // rdi
  void *v12; // r12
  ULONG v13; // ebx
  ULONG v14; // ebx
  struct _ACL *v15; // rax
  ULONG v17; // [rsp+20h] [rbp-69h]
  __int64 v21; // [rsp+30h] [rbp-59h]
  __int64 v22; // [rsp+38h] [rbp-51h]
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v25; // [rsp+68h] [rbp-21h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v27; // [rsp+78h] [rbp-11h] BYREF

  v6 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v27.Value = 0;
  *(_WORD *)&v27.Value[4] = 256;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v25 = 0;
  v17 = RtlLengthRequiredSid(6u);
  PoolWithTag = (void *)SrvNetAllocatePoolWithTag(258, v17, 1280529228);
  if ( PoolWithTag )
  {
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v12 = (void *)SrvNetAllocatePoolWithTag(258, v17, 1280529228);
    if ( !v12 )
      goto LABEL_4;
    v22 = RtlLengthRequiredSid(1u);
    v6 = (void *)SrvNetAllocatePoolWithTag(258, v22, 1280529228);
    if ( !v6 )
      goto LABEL_4;
    v21 = RtlLengthRequiredSid(2u);
    v9 = (void *)SrvNetAllocatePoolWithTag(258, v21, 1280529228);
    if ( !v9 )
      goto LABEL_4;
    v13 = RtlLengthRequiredSid(1u);
    v10 = (void *)SrvNetAllocatePoolWithTag(258, v13, 1280529228);
    if ( !v10 )
      goto LABEL_4;
    RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 6u);
    RtlInitializeSid(v12, &IdentifierAuthority, 6u);
    RtlInitializeSid(v6, &IdentifierAuthority, 1u);
    RtlInitializeSid(v9, &IdentifierAuthority, 2u);
    RtlInitializeSid(v10, &v27, 1u);
    *RtlSubAuthoritySid(PoolWithTag, 0) = 80;
    *RtlSubAuthoritySid(PoolWithTag, 1u) = -706794499;
    *RtlSubAuthoritySid(PoolWithTag, 2u) = 86763527;
    *RtlSubAuthoritySid(PoolWithTag, 3u) = 1375198215;
    *RtlSubAuthoritySid(PoolWithTag, 4u) = -2127910739;
    *RtlSubAuthoritySid(PoolWithTag, 5u) = -1589530409;
    *RtlSubAuthoritySid(v12, 0) = 80;
    *RtlSubAuthoritySid(v12, 1u) = 879696042;
    *RtlSubAuthoritySid(v12, 2u) = -1943298450;
    *RtlSubAuthoritySid(v12, 3u) = 370232824;
    *RtlSubAuthoritySid(v12, 4u) = -1770678392;
    *RtlSubAuthoritySid(v12, 5u) = -271430585;
    *RtlSubAuthoritySid(v6, 0) = 18;
    *RtlSubAuthoritySid(v9, 0) = 32;
    *RtlSubAuthoritySid(v9, 1u) = 544;
    *RtlSubAuthoritySid(v10, 0) = 0;
    v14 = v22 + v21 + v13 + 2 * v17 + 48;
    v15 = (struct _ACL *)SrvNetAllocatePoolWithTag(258, v14, 1280529228);
    v11 = v15;
    if ( v15 )
    {
      RtlCreateAcl(v15, v14, 2u);
      if ( a3 )
        RtlAddAccessAllowedAce(v11, 2u, a3, PoolWithTag);
      if ( a4 )
        RtlAddAccessAllowedAce(v11, 2u, a4, v12);
      if ( a2 )
        RtlAddAccessAllowedAce(v11, 2u, a2, v6);
      if ( a5 )
        RtlAddAccessAllowedAce(v11, 2u, a5, v9);
      if ( a6 )
        RtlAddAccessAllowedAce(v11, 2u, a6, v10);
      RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
      v8 = ObSetSecurityObjectByPointer(a1, 4, SecurityDescriptor);
    }
    else
    {
LABEL_4:
      v8 = -1073741670;
    }
    SrvNetWskNotifyCleanupProviderContext(PoolWithTag);
    if ( v12 )
      SrvNetWskNotifyCleanupProviderContext(v12);
    if ( v6 )
      SrvNetWskNotifyCleanupProviderContext(v6);
    if ( v9 )
      SrvNetWskNotifyCleanupProviderContext(v9);
    if ( v10 )
      SrvNetWskNotifyCleanupProviderContext(v10);
    if ( v11 )
      SrvNetWskNotifyCleanupProviderContext(v11);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v8;
}

```

## disassembly

```asm
0x140056010  push    rbp
0x140056012  push    rbx
0x140056013  push    rsi
0x140056014  push    rdi
0x140056015  push    r12
0x140056017  push    r13
0x140056019  push    r14
0x14005601b  push    r15
0x14005601d  lea     rbp, [rsp-0Fh]
0x140056022  sub     rsp, 98h
0x140056029  mov     rax, cs:__security_cookie
0x140056030  xor     rax, rsp
0x140056033  mov     [rbp+47h+var_50], rax
0x140056037  xor     esi, esi
0x140056039  mov     [rbp+47h+var_90], rcx
0x14005603d  xorps   xmm0, xmm0
0x140056040  mov     [rbp+47h+var_A8], r9d
0x140056044  xor     eax, eax
0x140056046  mov     [rbp+47h+AccessMask], r8d
0x14005604a  mov     [rbp+47h+var_A4], edx
0x14005604d  lea     ecx, [rsi+6]; SubAuthorityCount
0x140056050  mov     dword ptr [rbp+47h+IdentifierAuthority.Value], esi
0x140056053  mov     word ptr [rbp+47h+IdentifierAuthority.Value+4], 500h
0x140056059  mov     dword ptr [rbp+47h+var_58.Value], esi
0x14005605c  mov     word ptr [rbp+47h+var_58.Value+4], 100h
0x140056062  movups  [rbp+47h+SecurityDescriptor], xmm0
0x140056066  mov     [rbp+47h+var_68], rax
0x14005606a  movups  [rbp+47h+var_78], xmm0
0x14005606e  call    cs:__imp_RtlLengthRequiredSid
0x140056075  nop     dword ptr [rax+rax+00h]
0x14005607a  mov     r12d, 4C53534Ch
0x140056080  mov     edx, eax
0x140056082  mov     ecx, 102h
0x140056087  mov     [rbp+47h+var_B0], eax
0x14005608a  mov     r8d, r12d
0x14005608d  mov     ebx, eax
0x14005608f  call    SrvNetAllocatePoolWithTag
0x140056094  mov     r13, rax
0x140056097  test    rax, rax
0x14005609a  jnz     short loc_1400560A6
0x14005609c  mov     ebx, 0C000009Ah
0x1400560a1  jmp     loc_1400564C4
0x1400560a6  mov     r8d, r12d
0x1400560a9  mov     rdx, rbx
0x1400560ac  mov     ecx, 102h
0x1400560b1  mov     r14, rsi
0x1400560b4  mov     r15, rsi
0x1400560b7  mov     rdi, rsi
0x1400560ba  call    SrvNetAllocatePoolWithTag
0x1400560bf  mov     r12, rax
0x1400560c2  test    rax, rax
0x1400560c5  jnz     short loc_1400560D1
0x1400560c7  mov     ebx, 0C000009Ah
0x1400560cc  jmp     loc_14005647B
0x1400560d1  mov     ecx, 1; SubAuthorityCount
0x1400560d6  call    cs:__imp_RtlLengthRequiredSid
0x1400560dd  nop     dword ptr [rax+rax+00h]
0x1400560e2  mov     eax, eax
0x1400560e4  mov     ebx, 4C53534Ch
0x1400560e9  mov     ecx, 102h
0x1400560ee  mov     [rbp+47h+var_98], rax
0x1400560f2  mov     edx, eax
0x1400560f4  mov     r8d, ebx
0x1400560f7  call    SrvNetAllocatePoolWithTag
0x1400560fc  mov     rsi, rax
0x1400560ff  test    rax, rax
0x140056102  jz      short loc_1400560C7
0x140056104  mov     ecx, 2; SubAuthorityCount
0x140056109  call    cs:__imp_RtlLengthRequiredSid
0x140056110  nop     dword ptr [rax+rax+00h]
0x140056115  mov     eax, eax
0x140056117  mov     r8d, ebx
0x14005611a  mov     ecx, 102h
0x14005611f  mov     [rbp+47h+var_A0], rax
0x140056123  mov     edx, eax
0x140056125  call    SrvNetAllocatePoolWithTag
0x14005612a  mov     r14, rax
0x14005612d  test    rax, rax
0x140056130  jz      short loc_1400560C7
0x140056132  mov     ecx, 1; SubAuthorityCount
0x140056137  call    cs:__imp_RtlLengthRequiredSid
0x14005613e  nop     dword ptr [rax+rax+00h]
0x140056143  mov     edx, eax
0x140056145  mov     ecx, 102h
0x14005614a  mov     r8d, 4C53534Ch
0x140056150  mov     ebx, eax
0x140056152  call    SrvNetAllocatePoolWithTag
0x140056157  mov     r15, rax
0x14005615a  test    rax, rax
0x14005615d  jz      loc_1400560C7
0x140056163  mov     r8b, 6; SubAuthorityCount
0x140056166  lea     rdx, [rbp+47h+IdentifierAuthority]; IdentifierAuthority
0x14005616a  mov     rcx, r13; Sid
0x14005616d  call    cs:__imp_RtlInitializeSid
0x140056174  nop     dword ptr [rax+rax+00h]
0x140056179  mov     r8b, 6; SubAuthorityCount
0x14005617c  lea     rdx, [rbp+47h+IdentifierAuthority]; IdentifierAuthority
0x140056180  mov     rcx, r12; Sid
0x140056183  call    cs:__imp_RtlInitializeSid
0x14005618a  nop     dword ptr [rax+rax+00h]
0x14005618f  mov     r8b, 1; SubAuthorityCount
0x140056192  lea     rdx, [rbp+47h+IdentifierAuthority]; IdentifierAuthority
0x140056196  mov     rcx, rsi; Sid
0x140056199  call    cs:__imp_RtlInitializeSid
0x1400561a0  nop     dword ptr [rax+rax+00h]
0x1400561a5  mov     r8b, 2; SubAuthorityCount
0x1400561a8  lea     rdx, [rbp+47h+IdentifierAuthority]; IdentifierAuthority
0x1400561ac  mov     rcx, r14; Sid
0x1400561af  call    cs:__imp_RtlInitializeSid
0x1400561b6  nop     dword ptr [rax+rax+00h]
0x1400561bb  mov     r8b, 1; SubAuthorityCount
0x1400561be  lea     rdx, [rbp+47h+var_58]; IdentifierAuthority
0x1400561c2  mov     rcx, r15; Sid
0x1400561c5  call    cs:__imp_RtlInitializeSid
0x1400561cc  nop     dword ptr [rax+rax+00h]
0x1400561d1  xor     edx, edx; SubAuthority
0x1400561d3  mov     rcx, r13; Sid
0x1400561d6  call    cs:__imp_RtlSubAuthoritySid
0x1400561dd  nop     dword ptr [rax+rax+00h]
0x1400561e2  mov     edx, 1; SubAuthority
0x1400561e7  mov     rcx, r13; Sid
0x1400561ea  mov     dword ptr [rax], 50h ; 'P'
0x1400561f0  call    cs:__imp_RtlSubAuthoritySid
0x1400561f7  nop     dword ptr [rax+rax+00h]
0x1400561fc  mov     edx, 2; SubAuthority
0x140056201  mov     rcx, r13; Sid
0x140056204  mov     dword ptr [rax], 0D5DF2BFDh
0x14005620a  call    cs:__imp_RtlSubAuthoritySid
0x140056211  nop     dword ptr [rax+rax+00h]
0x140056216  mov     edi, 3
0x14005621b  mov     rcx, r13; Sid
0x14005621e  mov     edx, edi; SubAuthority
0x140056220  mov     dword ptr [rax], 52BE807h
0x140056226  call    cs:__imp_RtlSubAuthoritySid
0x14005622d  nop     dword ptr [rax+rax+00h]
0x140056232  lea     edx, [rdi+1]; SubAuthority
0x140056235  mov     rcx, r13; Sid
0x140056238  mov     dword ptr [rax], 51F7DC07h
0x14005623e  call    cs:__imp_RtlSubAuthoritySid
0x140056245  nop     dword ptr [rax+rax+00h]
0x14005624a  lea     edx, [rdi+2]; SubAuthority
0x14005624d  mov     rcx, r13; Sid
0x140056250  mov     dword ptr [rax], 812AA8ADh
0x140056256  call    cs:__imp_RtlSubAuthoritySid
0x14005625d  nop     dword ptr [rax+rax+00h]
0x140056262  xor     edx, edx; SubAuthority
0x140056264  mov     rcx, r12; Sid
0x140056267  mov     dword ptr [rax], 0A141B0D7h
0x14005626d  call    cs:__imp_RtlSubAuthoritySid
0x140056274  nop     dword ptr [rax+rax+00h]
0x140056279  lea     edx, [rdi-2]; SubAuthority
0x14005627c  mov     rcx, r12; Sid
0x14005627f  mov     dword ptr [rax], 50h ; 'P'
0x140056285  call    cs:__imp_RtlSubAuthoritySid
0x14005628c  nop     dword ptr [rax+rax+00h]
0x140056291  lea     edx, [rdi-1]; SubAuthority
0x140056294  mov     rcx, r12; Sid
0x140056297  mov     dword ptr [rax], 346F18AAh
0x14005629d  call    cs:__imp_RtlSubAuthoritySid
0x1400562a4  nop     dword ptr [rax+rax+00h]
0x1400562a9  mov     edx, edi; SubAuthority
0x1400562ab  mov     rcx, r12; Sid
0x1400562ae  mov     dword ptr [rax], 8C2B9E6Eh
0x1400562b4  call    cs:__imp_RtlSubAuthoritySid
0x1400562bb  nop     dword ptr [rax+rax+00h]
0x1400562c0  lea     edx, [rdi+1]; SubAuthority
0x1400562c3  mov     rcx, r12; Sid
0x1400562c6  mov     dword ptr [rax], 16114DF8h
0x1400562cc  call    cs:__imp_RtlSubAuthoritySid
0x1400562d3  nop     dword ptr [rax+rax+00h]
0x1400562d8  lea     edx, [rdi+2]; SubAuthority
0x1400562db  mov     rcx, r12; Sid
0x1400562de  mov     dword ptr [rax], 96759788h
0x1400562e4  call    cs:__imp_RtlSubAuthoritySid
0x1400562eb  nop     dword ptr [rax+rax+00h]
0x1400562f0  xor     edx, edx; SubAuthority
0x1400562f2  mov     rcx, rsi; Sid
0x1400562f5  mov     dword ptr [rax], 0EFD24C47h
0x1400562fb  call    cs:__imp_RtlSubAuthoritySid
0x140056302  nop     dword ptr [rax+rax+00h]
0x140056307  xor     edx, edx; SubAuthority
0x140056309  mov     rcx, r14; Sid
0x14005630c  mov     dword ptr [rax], 12h
0x140056312  call    cs:__imp_RtlSubAuthoritySid
0x140056319  nop     dword ptr [rax+rax+00h]
0x14005631e  lea     edx, [rdi-2]; SubAuthority
0x140056321  mov     rcx, r14; Sid
0x140056324  mov     dword ptr [rax], 20h ; ' '
0x14005632a  call    cs:__imp_RtlSubAuthoritySid
0x140056331  nop     dword ptr [rax+rax+00h]
0x140056336  mov     dword ptr [rax], 220h
0x14005633c  xor     edx, edx; SubAuthority
0x14005633e  mov     rcx, r15; Sid
0x140056341  call    cs:__imp_RtlSubAuthoritySid
0x140056348  nop     dword ptr [rax+rax+00h]
0x14005634d  mov     rcx, [rbp+47h+var_98]
0x140056351  mov     r8d, 4C53534Ch
0x140056357  mov     dword ptr [rax], 0
0x14005635d  mov     eax, [rbp+47h+var_B0]
0x140056360  lea     ebx, [rbx+rax*2]
0x140056363  add     ebx, 30h ; '0'
0x140056366  add     ebx, dword ptr [rbp+47h+var_A0]
0x140056369  add     ebx, ecx
0x14005636b  mov     ecx, 102h
0x140056370  mov     edx, ebx
0x140056372  call    SrvNetAllocatePoolWithTag
0x140056377  mov     rdi, rax
0x14005637a  test    rax, rax
0x14005637d  jz      loc_1400560C7
0x140056383  mov     r8d, 2; AclRevision
0x140056389  mov     edx, ebx; AclLength
0x14005638b  mov     rcx, rax; Acl
0x14005638e  call    cs:__imp_RtlCreateAcl
0x140056395  nop     dword ptr [rax+rax+00h]
0x14005639a  mov     eax, [rbp+47h+AccessMask]
0x14005639d  mov     ebx, 2
0x1400563a2  test    eax, eax
0x1400563a4  jz      short loc_1400563BD
0x1400563a6  mov     r9, r13; Sid
0x1400563a9  mov     r8d, eax; AccessMask
0x1400563ac  mov     edx, ebx; AceRevision
0x1400563ae  mov     rcx, rdi; Acl
0x1400563b1  call    cs:__imp_RtlAddAccessAllowedAce
0x1400563b8  nop     dword ptr [rax+rax+00h]
0x1400563bd  mov     eax, [rbp+47h+var_A8]
0x1400563c0  test    eax, eax
0x1400563c2  jz      short loc_1400563DB
0x1400563c4  mov     r9, r12; Sid
0x1400563c7  mov     r8d, eax; AccessMask
0x1400563ca  mov     edx, ebx; AceRevision
0x1400563cc  mov     rcx, rdi; Acl
0x1400563cf  call    cs:__imp_RtlAddAccessAllowedAce
0x1400563d6  nop     dword ptr [rax+rax+00h]
0x1400563db  mov     eax, [rbp+47h+var_A4]
0x1400563de  test    eax, eax
0x1400563e0  jz      short loc_1400563F9
0x1400563e2  mov     r9, rsi; Sid
0x1400563e5  mov     r8d, eax; AccessMask
0x1400563e8  mov     edx, ebx; AceRevision
0x1400563ea  mov     rcx, rdi; Acl
0x1400563ed  call    cs:__imp_RtlAddAccessAllowedAce
0x1400563f4  nop     dword ptr [rax+rax+00h]
0x1400563f9  mov     r8d, [rbp+47h+arg_20]; AccessMask
0x1400563fd  test    r8d, r8d
0x140056400  jz      short loc_140056416
0x140056402  mov     r9, r14; Sid
0x140056405  mov     edx, ebx; AceRevision
0x140056407  mov     rcx, rdi; Acl
0x14005640a  call    cs:__imp_RtlAddAccessAllowedAce
0x140056411  nop     dword ptr [rax+rax+00h]
0x140056416  mov     r8d, [rbp+47h+arg_28]; AccessMask
0x14005641a  test    r8d, r8d
0x14005641d  jz      short loc_140056433
0x14005641f  mov     r9, r15; Sid
0x140056422  mov     edx, ebx; AceRevision
0x140056424  mov     rcx, rdi; Acl
0x140056427  call    cs:__imp_RtlAddAccessAllowedAce
0x14005642e  nop     dword ptr [rax+rax+00h]
0x140056433  mov     edx, 1; Revision
0x140056438  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x14005643c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140056443  nop     dword ptr [rax+rax+00h]
0x140056448  xor     r9d, r9d; DaclDefaulted
0x14005644b  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x14005644f  mov     r8, rdi; Dacl
0x140056452  mov     dl, 1; DaclPresent
0x140056454  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14005645b  nop     dword ptr [rax+rax+00h]
0x140056460  mov     rcx, [rbp+47h+var_90]
0x140056464  lea     r8, [rbp+47h+SecurityDescriptor]
0x140056468  mov     edx, 4
0x14005646d  call    cs:__imp_ObSetSecurityObjectByPointer
0x140056474  nop     dword ptr [rax+rax+00h]
0x140056479  mov     ebx, eax
0x14005647b  mov     rcx, r13
0x14005647e  call    SrvNetWskNotifyCleanupProviderContext
0x140056483  test    r12, r12
0x140056486  jz      short loc_140056490
0x140056488  mov     rcx, r12
0x14005648b  call    SrvNetWskNotifyCleanupProviderContext
0x140056490  test    rsi, rsi
0x140056493  jz      short loc_14005649D
0x140056495  mov     rcx, rsi
0x140056498  call    SrvNetWskNotifyCleanupProviderContext
0x14005649d  test    r14, r14
0x1400564a0  jz      short loc_1400564AA
0x1400564a2  mov     rcx, r14
0x1400564a5  call    SrvNetWskNotifyCleanupProviderContext
0x1400564aa  test    r15, r15
0x1400564ad  jz      short loc_1400564B7
0x1400564af  mov     rcx, r15
0x1400564b2  call    SrvNetWskNotifyCleanupProviderContext
0x1400564b7  test    rdi, rdi
0x1400564ba  jz      short loc_1400564C4
0x1400564bc  mov     rcx, rdi
0x1400564bf  call    SrvNetWskNotifyCleanupProviderContext
0x1400564c4  mov     eax, ebx
0x1400564c6  mov     rcx, [rbp+47h+var_50]
0x1400564ca  xor     rcx, rsp; StackCookie
0x1400564cd  call    __security_check_cookie
  ... truncated ...
```
