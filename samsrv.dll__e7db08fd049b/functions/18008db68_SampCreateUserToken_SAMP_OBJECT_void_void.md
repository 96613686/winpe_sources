# SampCreateUserToken(_SAMP_OBJECT *,void *,void * *)

- ea: `0x18008db68`
- end: `0x18008de5c`
- name: `?SampCreateUserToken@@YAJPEAU_SAMP_OBJECT@@PEAXPEAPEAX@Z`
- size: `756`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, HANDLE TokenHandle, PHANDLE)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180017a60`

## callees

- `0x180016d50`
- `0x18001ca48`
- `0x18001f900`
- `0x180022530`
- `0x18002421c`
- `0x180027e24`
- `0x18002cd80`
- `0x18008db68`
- `0x18008e098`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18008dc98`
- `ntdll!RtlEqualSid` at `0x18008dc98`
- `ntdll!NtCreateToken` at `0x18008ddf3`
- `ntdll!NtCreateToken` at `0x18008ddf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008dcaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008de0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008dcaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008de0a`

## pseudocode

```c
__int64 __fastcall SampCreateUserToken(struct _SAMP_OBJECT *a1, HANDLE TokenHandle, PHANDLE a3)
{
  PSID v3; // rbx
  char v7; // si
  int CurrentClientSid; // edi
  char v9; // di
  PSID v10; // rax
  char v12; // [rsp+70h] [rbp-90h] BYREF
  _WORD v13[3]; // [rsp+71h] [rbp-8Fh] BYREF
  PSID Sid1; // [rsp+78h] [rbp-88h] BYREF
  int v15; // [rsp+80h] [rbp-80h] BYREF
  struct _TOKEN_PRIMARY_GROUP TokenPrimaryGroup; // [rsp+88h] [rbp-78h] BYREF
  union _LARGE_INTEGER ExpirationTime; // [rsp+90h] [rbp-70h] BYREF
  struct _TOKEN_USER TokenUser; // [rsp+98h] [rbp-68h] BYREF
  struct _LUID AuthenticationId; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-20h] BYREF
  int v22; // [rsp+E8h] [rbp-18h]
  struct _TOKEN_GROUPS TokenGroups; // [rsp+F0h] [rbp-10h] BYREF
  struct _TOKEN_PRIVILEGES TokenPrivileges; // [rsp+108h] [rbp+8h] BYREF
  struct _LM_OWF_PASSWORD v25; // [rsp+118h] [rbp+18h] BYREF
  struct _LM_OWF_PASSWORD v26; // [rsp+128h] [rbp+28h] BYREF

  AuthenticationId = (struct _LUID)999LL;
  TokenPrimaryGroup.PrimaryGroup = 0;
  v3 = 0;
  v21 = 0;
  Sid1 = 0;
  v22 = 0;
  ExpirationTime.QuadPart = 0;
  TokenUser = 0;
  v7 = 0;
  memset(&TokenGroups, 0, sizeof(TokenGroups));
  TokenPrivileges = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( SampLimitBlankPasswordUse && !(unsigned __int8)SampUsingDsData() )
  {
    v15 = 0;
    v13[0] = 0;
    v12 = 0;
    v25 = 0;
    v26 = 0;
    CurrentClientSid = SampGetCurrentClientSid(TokenHandle, &Sid1, &v15);
    if ( CurrentClientSid < 0 )
      goto LABEL_24;
    CurrentClientSid = SampRetrieveUserPasswords(a1, &v26, (_BYTE *)v13 + 1, &v25, &v12, (bool *)v13);
    if ( CurrentClientSid < 0 )
      goto LABEL_24;
    if ( v12 && LOBYTE(v13[0]) || (v9 = 0, HIBYTE(v13[0])) )
      v9 = 1;
    v3 = Sid1;
    if ( v15 || RtlEqualSid(Sid1, SampLocalSystemSid) || v9 )
    {
      LocalFree(v3);
      v3 = 0;
      Sid1 = 0;
    }
    else
    {
      v7 = 1;
    }
  }
  if ( SampIsForceGuestEnabled() || v7 )
  {
    if ( !SampIsClientLocal() )
    {
      TokenUser.User.Sid = SampAnonymousSid;
      v10 = (PSID)SampNetworkSid;
LABEL_22:
      TokenPrimaryGroup.PrimaryGroup = v10;
      TokenGroups.Groups[0].Attributes = 7;
      TokenGroups.Groups[0].Sid = v10;
      TokenGroups.GroupCount = 1;
      goto LABEL_23;
    }
    if ( v7 )
    {
      TokenUser.User.Sid = v3;
      TokenPrimaryGroup.PrimaryGroup = v3;
      TokenGroups.GroupCount = 0;
LABEL_23:
      TokenUser.User.Attributes = 0;
      ObjectAttributes.SecurityQualityOfService = &v21;
      TokenPrivileges.PrivilegeCount = 0;
      ExpirationTime.LowPart = 0x7FFFFFF;
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      ObjectAttributes.SecurityDescriptor = 0;
      LOWORD(v22) = 256;
      v21 = 0x20000000CLL;
      CurrentClientSid = NtCreateToken(
                           a3,
                           0xF01FFu,
                           &ObjectAttributes,
                           TokenImpersonation,
                           &AuthenticationId,
                           &ExpirationTime,
                           &TokenUser,
                           &TokenGroups,
                           &TokenPrivileges,
                           0,
                           &TokenPrimaryGroup,
                           0,
                           &SourceContext);
      goto LABEL_25;
    }
  }
  CurrentClientSid = SampCreateFullSid(*((PSID *)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50) + 1));
  if ( CurrentClientSid >= 0 )
  {
    v3 = Sid1;
    v10 = SampWorldSid;
    TokenUser.User.Sid = Sid1;
    goto LABEL_22;
  }
LABEL_24:
  v3 = Sid1;
LABEL_25:
  if ( v3 )
    LocalFree(v3);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      28,
      WPP_5505de3e48bd33375e96ca021b170945_Traceguids,
      (unsigned int)CurrentClientSid,
      CurrentClientSid);
  return (unsigned int)CurrentClientSid;
}

```

## disassembly

```asm
0x18008db68  push    rbp
0x18008db6a  push    rbx
0x18008db6b  push    rsi
0x18008db6c  push    rdi
0x18008db6d  push    r12
0x18008db6f  push    r14
0x18008db71  push    r15
0x18008db73  lea     rbp, [rsp-40h]
0x18008db78  sub     rsp, 140h
0x18008db7f  mov     rax, cs:__security_cookie
0x18008db86  xor     rax, rsp
0x18008db89  mov     [rbp+70h+var_38], rax
0x18008db8d  xor     r12d, r12d
0x18008db90  mov     qword ptr [rbp+70h+var_C8.LowPart], 3E7h
0x18008db98  xor     eax, eax
0x18008db9a  mov     [rbp+70h+var_E8.PrimaryGroup], r12
0x18008db9e  cmp     cs:?SampLimitBlankPasswordUse@@3EA, r12b; uchar SampLimitBlankPasswordUse
0x18008dba5  xorps   xmm0, xmm0
0x18008dba8  xorps   xmm1, xmm1
0x18008dbab  mov     qword ptr [rbp+70h+var_80.Groups.Attributes], rax
0x18008dbaf  mov     ebx, r12d
0x18008dbb2  mov     [rbp+70h+var_90], rax
0x18008dbb6  mov     [rsp+170h+Sid1], rbx
0x18008dbbb  mov     r15, r8
0x18008dbbe  mov     rdi, rdx
0x18008dbc1  mov     [rbp+70h+var_88], eax
0x18008dbc4  mov     r14, rcx
0x18008dbc7  mov     qword ptr [rbp+70h+var_E0], r12
0x18008dbcb  movups  xmmword ptr [rbp+70h+var_D8.User.Sid], xmm0
0x18008dbcf  mov     sil, r12b
0x18008dbd2  movups  xmmword ptr [rbp+70h+var_80.GroupCount], xmm0
0x18008dbd6  movups  xmmword ptr [rbp+70h+var_68.PrivilegeCount], xmm0
0x18008dbda  movups  xmmword ptr [rbp+70h+ObjectAttributes.Length], xmm1
0x18008dbde  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm1
0x18008dbe2  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm1
0x18008dbe6  jz      loc_18008DCBD
0x18008dbec  call    SampUsingDsData
0x18008dbf1  test    al, al
0x18008dbf3  jnz     loc_18008DCBD
0x18008dbf9  xorps   xmm0, xmm0
0x18008dbfc  mov     [rbp+70h+var_F0], r12d
0x18008dc00  xorps   xmm1, xmm1
0x18008dc03  mov     byte ptr [rsp+170h+var_100+2], r12b
0x18008dc08  lea     r8, [rbp+70h+var_F0]; int *
0x18008dc0c  mov     byte ptr [rsp+170h+var_100+1], r12b
0x18008dc11  lea     rdx, [rsp+170h+Sid1]; void **
0x18008dc16  mov     byte ptr [rsp+170h+var_100], r12b
0x18008dc1b  mov     rcx, rdi; TokenHandle
0x18008dc1e  movups  [rbp+70h+var_58], xmm0
0x18008dc22  movups  [rbp+70h+var_48], xmm1
0x18008dc26  call    ?SampGetCurrentClientSid@@YAJPEAXPEAPEAXPEAH@Z; SampGetCurrentClientSid(void *,void * *,int *)
0x18008dc2b  mov     edi, eax
0x18008dc2d  test    eax, eax
0x18008dc2f  js      loc_18008DDFD
0x18008dc35  lea     rax, [rsp+170h+var_100+1]
0x18008dc3a  mov     rcx, r14; struct _SAMP_OBJECT *
0x18008dc3d  mov     [rsp+170h+ExpirationTime], rax; __int64
0x18008dc42  lea     r9, [rbp+70h+var_58]
0x18008dc46  lea     rax, [rsp+170h+var_100]
0x18008dc4b  lea     r8, [rsp+170h+var_100+2]
0x18008dc50  mov     [rsp+170h+AuthenticationId], rax; __int64
0x18008dc55  lea     rdx, [rbp+70h+var_48]
0x18008dc59  call    SampRetrieveUserPasswords
0x18008dc5e  mov     edi, eax
0x18008dc60  test    eax, eax
0x18008dc62  js      loc_18008DDFD
0x18008dc68  cmp     byte ptr [rsp+170h+var_100], r12b
0x18008dc6d  jz      short loc_18008DC76
0x18008dc6f  cmp     byte ptr [rsp+170h+var_100+1], r12b
0x18008dc74  jnz     short loc_18008DC80
0x18008dc76  mov     dil, r12b
0x18008dc79  cmp     byte ptr [rsp+170h+var_100+2], r12b
0x18008dc7e  jz      short loc_18008DC83
0x18008dc80  mov     dil, 1
0x18008dc83  mov     rbx, [rsp+170h+Sid1]
0x18008dc88  cmp     [rbp+70h+var_F0], r12d
0x18008dc8c  jnz     short loc_18008DCAC
0x18008dc8e  mov     rdx, cs:SampLocalSystemSid; Sid2
0x18008dc95  mov     rcx, rbx; Sid1
0x18008dc98  call    cs:__imp_RtlEqualSid
0x18008dc9e  test    al, al
0x18008dca0  jnz     short loc_18008DCAC
0x18008dca2  test    dil, dil
0x18008dca5  jnz     short loc_18008DCAC
0x18008dca7  mov     sil, 1
0x18008dcaa  jmp     short loc_18008DCBD
0x18008dcac  mov     rcx, rbx; hMem
0x18008dcaf  call    cs:__imp_LocalFree
0x18008dcb5  mov     rbx, r12
0x18008dcb8  mov     [rsp+170h+Sid1], rbx
0x18008dcbd  call    ?SampIsForceGuestEnabled@@YAEXZ; SampIsForceGuestEnabled(void)
0x18008dcc2  test    al, al
0x18008dcc4  jnz     short loc_18008DCCB
0x18008dcc6  test    sil, sil
0x18008dcc9  jz      short loc_18008DCFB
0x18008dccb  call    ?SampIsClientLocal@@YAEXZ; SampIsClientLocal(void)
0x18008dcd0  test    al, al
0x18008dcd2  jnz     short loc_18008DCE8
0x18008dcd4  mov     rax, cs:SampAnonymousSid
0x18008dcdb  mov     [rbp+70h+var_D8.User.Sid], rax
0x18008dcdf  mov     rax, cs:SampNetworkSid
0x18008dce6  jmp     short loc_18008DD40
0x18008dce8  test    sil, sil
0x18008dceb  jz      short loc_18008DCFB
0x18008dced  mov     [rbp+70h+var_D8.User.Sid], rbx
0x18008dcf1  mov     [rbp+70h+var_E8.PrimaryGroup], rbx
0x18008dcf5  mov     [rbp+70h+var_80.GroupCount], r12d
0x18008dcf9  jmp     short loc_18008DD56
0x18008dcfb  mov     eax, [r14+0C8h]
0x18008dd02  lea     r8, [rsp+170h+Sid1]
0x18008dd07  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008dd0e  mov     edx, [r14+0F8h]
0x18008dd15  imul    r9, rax, 550h
0x18008dd1c  mov     rcx, [r9+rcx+8]; SourceSid
0x18008dd21  call    SampCreateFullSid
0x18008dd26  mov     edi, eax
0x18008dd28  test    eax, eax
0x18008dd2a  js      loc_18008DDFD
0x18008dd30  mov     rbx, [rsp+170h+Sid1]
0x18008dd35  mov     rax, cs:SampWorldSid
0x18008dd3c  mov     [rbp+70h+var_D8.User.Sid], rbx
0x18008dd40  mov     [rbp+70h+var_E8.PrimaryGroup], rax
0x18008dd44  mov     [rbp+70h+var_80.Groups.Attributes], 7
0x18008dd4b  mov     [rbp+70h+var_80.Groups.Sid], rax
0x18008dd4f  mov     [rbp+70h+var_80.GroupCount], 1
0x18008dd56  lea     rax, [rbp+70h+var_90]
0x18008dd5a  mov     [rbp+70h+var_D8.User.Attributes], r12d
0x18008dd5e  mov     [rbp+70h+ObjectAttributes.SecurityQualityOfService], rax
0x18008dd62  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x18008dd66  lea     rax, ?SourceContext@@3U_TOKEN_SOURCE@@A; _TOKEN_SOURCE SourceContext
0x18008dd6d  mov     [rbp+70h+var_68.PrivilegeCount], r12d
0x18008dd71  mov     [rsp+170h+TokenSource], rax; TokenSource
0x18008dd76  mov     r9d, 2; TokenType
0x18008dd7c  mov     [rsp+170h+TokenDefaultDacl], r12; TokenDefaultDacl
0x18008dd81  lea     rax, [rbp+70h+var_E8]
0x18008dd85  mov     [rsp+170h+TokenPrimaryGroup], rax; TokenPrimaryGroup
0x18008dd8a  mov     edx, 0F01FFh; DesiredAccess
0x18008dd8f  mov     [rsp+170h+TokenOwner], r12; TokenOwner
0x18008dd94  lea     rax, [rbp+70h+var_68]
0x18008dd98  mov     [rsp+170h+TokenPrivileges], rax; TokenPrivileges
0x18008dd9d  mov     rcx, r15; TokenHandle
0x18008dda0  lea     rax, [rbp+70h+var_80]
0x18008dda4  mov     dword ptr [rbp+70h+var_E0], 7FFFFFFh
0x18008ddab  mov     [rsp+170h+TokenGroups], rax; TokenGroups
0x18008ddb0  lea     rax, [rbp+70h+var_D8]
0x18008ddb4  mov     [rsp+170h+TokenUser], rax; TokenUser
0x18008ddb9  lea     rax, [rbp+70h+var_E0]
0x18008ddbd  mov     [rsp+170h+ExpirationTime], rax; ExpirationTime
0x18008ddc2  lea     rax, [rbp+70h+var_C8]
0x18008ddc6  mov     [rsp+170h+AuthenticationId], rax; AuthenticationId
0x18008ddcb  mov     [rbp+70h+ObjectAttributes.Length], 30h ; '0'
0x18008ddd2  mov     [rbp+70h+ObjectAttributes.RootDirectory], r12
0x18008ddd6  mov     [rbp+70h+ObjectAttributes.Attributes], r12d
0x18008ddda  mov     [rbp+70h+ObjectAttributes.ObjectName], r12
0x18008ddde  mov     [rbp+70h+ObjectAttributes.SecurityDescriptor], r12
0x18008dde2  mov     dword ptr [rbp+70h+var_90+4], r9d
0x18008dde6  mov     word ptr [rbp+70h+var_88], 100h
0x18008ddec  mov     dword ptr [rbp+70h+var_90], 0Ch
0x18008ddf3  call    cs:__imp_NtCreateToken
0x18008ddf9  mov     edi, eax
0x18008ddfb  jmp     short loc_18008DE02
0x18008ddfd  mov     rbx, [rsp+170h+Sid1]
0x18008de02  test    rbx, rbx
0x18008de05  jz      short loc_18008DE10
0x18008de07  mov     rcx, rbx; hMem
0x18008de0a  call    cs:__imp_LocalFree
0x18008de10  mov     rcx, cs:WPP_GLOBAL_Control
0x18008de17  test    dword ptr [rcx+44h], 20000h
0x18008de1e  jz      short loc_18008DE3C
0x18008de20  mov     rcx, [rcx+38h]
0x18008de24  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008de2b  mov     edx, 1Ch
0x18008de30  mov     dword ptr [rsp+170h+AuthenticationId], edi
0x18008de34  mov     r9d, edi
0x18008de37  call    WPP_SF_Dd
0x18008de3c  mov     eax, edi
0x18008de3e  mov     rcx, [rbp+70h+var_38]
0x18008de42  xor     rcx, rsp; StackCookie
0x18008de45  call    __security_check_cookie
0x18008de4a  add     rsp, 140h
0x18008de51  pop     r15
0x18008de53  pop     r14
0x18008de55  pop     r12
0x18008de57  pop     rdi
0x18008de58  pop     rsi
0x18008de59  pop     rbx
0x18008de5a  pop     rbp
0x18008de5b  retn
```
