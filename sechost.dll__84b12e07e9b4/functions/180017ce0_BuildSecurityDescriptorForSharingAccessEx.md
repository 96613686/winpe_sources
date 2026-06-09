# BuildSecurityDescriptorForSharingAccessEx

- ea: `0x180017ce0`
- end: `0x180018007`
- name: `BuildSecurityDescriptorForSharingAccessEx`
- size: `807`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017cc0`

## callees

- `0x180012290`
- `0x1800125c8`
- `0x180017ce0`
- `0x180018a7c`
- `0x180023374`
- `0x180023698`
- `0x18002370c`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180017fd7`
- `ntdll!RtlNtStatusToDosError` at `0x180017fd7`
- `ntdll!RtlEqualSid` at `0x180017dcc`
- `ntdll!RtlEqualSid` at `0x180017dfb`
- `ntdll!RtlEqualSid` at `0x180017dcc`
- `ntdll!RtlEqualSid` at `0x180017dfb`
- `ntdll!RtlInitializeSid` at `0x180017ea9`
- `ntdll!RtlInitializeSid` at `0x180017ea9`
- `ntdll!RtlSubAuthoritySid` at `0x180017eb4`
- `ntdll!RtlSubAuthoritySid` at `0x180017eb4`
- `ntdll!NtOpenProcessTokenEx` at `0x180017e2a`
- `ntdll!NtOpenProcessTokenEx` at `0x180017e2a`
- `ntdll!RtlLengthRequiredSid` at `0x180017e79`
- `ntdll!RtlLengthRequiredSid` at `0x180017e79`
- `ntdll!RtlAddMandatoryAce` at `0x180017f1b`
- `ntdll!RtlAddMandatoryAce` at `0x180017f1b`
- `ntdll!RtlLengthSid` at `0x180017ec2`
- `ntdll!RtlLengthSid` at `0x180017ec2`
- `ntdll!RtlCreateAcl` at `0x180017ef5`
- `ntdll!RtlCreateAcl` at `0x180017ef5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017fdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017fdf`

## pseudocode

```c
__int64 __fastcall BuildSecurityDescriptorForSharingAccessEx(
        HANDLE TokenHandle,
        void *a2,
        ACCESS_MASK a3,
        int a4,
        _QWORD *a5)
{
  PSID v5; // r14
  PSID v6; // rdi
  PSID v7; // r15
  PSID v8; // rsi
  struct _ACL *v9; // r13
  __int64 v10; // r12
  NTSTATUS AppUserSID; // ebx
  int CurrentProcessAppUserSID; // eax
  BOOLEAN v13; // al
  BOOLEAN v14; // r12
  void *v15; // rcx
  ULONG v16; // eax
  void *v17; // rax
  void *v18; // rbx
  PULONG v19; // rax
  ULONG v20; // ebx
  struct _ACL *v21; // rax
  DWORD v22; // eax
  PSID LabelSid; // [rsp+28h] [rbp-79h]
  ULONG MandatoryFlags[2]; // [rsp+40h] [rbp-61h]
  PSID Sid2; // [rsp+50h] [rbp-51h] BYREF
  PSID v27; // [rsp+58h] [rbp-49h]
  void *TokenHandlea; // [rsp+60h] [rbp-41h] BYREF
  PSID v29; // [rsp+68h] [rbp-39h] BYREF
  PSID Sid1; // [rsp+70h] [rbp-31h] BYREF
  PSID v31; // [rsp+78h] [rbp-29h] BYREF
  ACCESS_MASK AccessMask; // [rsp+80h] [rbp-21h]
  HANDLE v33; // [rsp+88h] [rbp-19h]
  __int64 v34; // [rsp+90h] [rbp-11h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp-9h] BYREF

  v33 = TokenHandle;
  LODWORD(v27) = a4;
  v5 = 0;
  v34 = (__int64)a5;
  v6 = 0;
  AccessMask = a3;
  v7 = 0;
  TokenHandlea = a2;
  v8 = 0;
  Sid1 = 0;
  v9 = 0;
  v31 = 0;
  v10 = 0;
  Sid2 = 0;
  v29 = 0;
  *(_QWORD *)MandatoryFlags = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  if ( !TokenHandle || !a3 || !a5 )
  {
    AppUserSID = -1073741811;
    goto LABEL_34;
  }
  *a5 = 0;
  AppUserSID = GetAppUserSID(TokenHandle, &Sid1, &v31);
  if ( AppUserSID < 0 )
  {
    v5 = Sid1;
    v6 = v31;
    goto LABEL_34;
  }
  if ( TokenHandlea )
    CurrentProcessAppUserSID = GetAppUserSID(TokenHandlea, &Sid2, &v29);
  else
    CurrentProcessAppUserSID = GetCurrentProcessAppUserSID(&Sid2, &v29);
  v7 = Sid2;
  AppUserSID = CurrentProcessAppUserSID;
  v5 = Sid1;
  if ( CurrentProcessAppUserSID < 0 )
  {
    v6 = v31;
    v8 = v29;
    goto LABEL_34;
  }
  v13 = RtlEqualSid(Sid1, Sid2);
  v6 = v31;
  v14 = v13;
  v8 = v29;
  if ( v13 )
  {
    if ( v31 && v29 )
      v14 = RtlEqualSid(v31, v29);
    else
      v14 = 0;
  }
  if ( !(_DWORD)v27 )
    goto LABEL_27;
  v15 = TokenHandlea;
  if ( TokenHandlea )
    goto LABEL_18;
  AppUserSID = NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0, &TokenHandlea);
  if ( !AppUserSID )
  {
    v15 = TokenHandlea;
LABEL_18:
    AppUserSID = GetIntegrityLevel(v15);
    if ( !AppUserSID )
    {
      AppUserSID = GetIntegrityLevel(v33);
      if ( !AppUserSID )
      {
        LODWORD(Sid2) = 0;
        v16 = RtlLengthRequiredSid(1u);
        v17 = (void *)AccessHlprAlloc(v16);
        *(_QWORD *)MandatoryFlags = v17;
        v18 = v17;
        if ( !v17 )
        {
          AppUserSID = -1073741801;
          v10 = 0;
          goto LABEL_34;
        }
        RtlInitializeSid(v17, &IdentifierAuthority, 1u);
        v19 = RtlSubAuthoritySid(v18, 0);
        *v19 = (unsigned int)Sid2;
        v20 = RtlLengthSid(v18);
        v21 = (struct _ACL *)AccessHlprAlloc(v20 + 16LL);
        v9 = v21;
        if ( !v21 )
        {
          AppUserSID = -1073741801;
LABEL_24:
          v10 = *(_QWORD *)MandatoryFlags;
          goto LABEL_34;
        }
        AppUserSID = RtlCreateAcl(v21, v20 + 16, 2u);
        if ( AppUserSID < 0 )
          goto LABEL_24;
        LODWORD(LabelSid) = (_DWORD)v27;
        AppUserSID = RtlAddMandatoryAce(v9, 2u, 0, MandatoryFlags[0], 0x11u, LabelSid);
        if ( AppUserSID < 0 )
          goto LABEL_24;
LABEL_27:
        if ( v14 )
          AppUserSID = 0;
        else
          AppUserSID = BuildSecurityDescriptorForSharingAccessInternal(v5, v6, v7, v8, AccessMask, v9, (_QWORD *)v34);
        goto LABEL_24;
      }
    }
  }
  v10 = 0;
LABEL_34:
  if ( v5 )
    FreeTransientObjectSecurityDescriptor(v5);
  if ( v6 )
    FreeTransientObjectSecurityDescriptor(v6);
  if ( v7 )
    FreeTransientObjectSecurityDescriptor(v7);
  if ( v8 )
    FreeTransientObjectSecurityDescriptor(v8);
  if ( v9 )
    FreeTransientObjectSecurityDescriptor(v9);
  if ( v10 )
    FreeTransientObjectSecurityDescriptor(v10);
  if ( AppUserSID < 0 )
  {
    v22 = RtlNtStatusToDosError(AppUserSID);
    SetLastError(v22);
  }
  return (unsigned int)AppUserSID;
}

```

## disassembly

```asm
0x180017ce0  push    rbp
0x180017ce2  push    rbx
0x180017ce3  push    rsi
0x180017ce4  push    rdi
0x180017ce5  push    r12
0x180017ce7  push    r13
0x180017ce9  push    r14
0x180017ceb  push    r15
0x180017ced  lea     rbp, [rsp-17h]
0x180017cf2  sub     rsp, 0B8h
0x180017cf9  mov     rax, cs:__security_cookie
0x180017d00  xor     rax, rsp
0x180017d03  mov     [rbp+4Fh+var_50], rax
0x180017d07  xor     ebx, ebx
0x180017d09  mov     [rbp+4Fh+var_68], rcx
0x180017d0d  mov     rax, rcx
0x180017d10  mov     dword ptr [rbp+4Fh+var_98], r9d
0x180017d14  mov     rcx, [rbp+4Fh+arg_20]
0x180017d18  mov     r14d, ebx
0x180017d1b  mov     [rbp+4Fh+var_60], rcx
0x180017d1f  mov     edi, ebx
0x180017d21  mov     [rbp+4Fh+AccessMask], r8d
0x180017d25  mov     r15d, ebx
0x180017d28  mov     [rbp+4Fh+TokenHandle], rdx
0x180017d2c  mov     esi, ebx
0x180017d2e  mov     [rbp+4Fh+Sid1], rbx
0x180017d32  mov     r13d, ebx
0x180017d35  mov     [rbp+4Fh+var_78], rbx
0x180017d39  mov     r12d, ebx
0x180017d3c  mov     [rbp+4Fh+Sid2], rbx
0x180017d40  mov     [rbp+4Fh+var_88], rbx
0x180017d44  mov     [rbp+4Fh+var_A8], ebx
0x180017d47  mov     [rbp+4Fh+var_A4], ebx
0x180017d4a  mov     qword ptr [rbp+4Fh+MandatoryFlags], rbx
0x180017d4e  mov     dword ptr [rbp+4Fh+IdentifierAuthority.Value], ebx
0x180017d51  mov     word ptr [rbp+4Fh+IdentifierAuthority.Value+4], 1000h
0x180017d57  test    rax, rax
0x180017d5a  jz      loc_180017F79
0x180017d60  test    r8d, r8d
0x180017d63  jz      loc_180017F79
0x180017d69  test    rcx, rcx
0x180017d6c  jz      loc_180017F79
0x180017d72  mov     [rcx], rbx
0x180017d75  lea     r8, [rbp+4Fh+var_78]
0x180017d79  mov     rcx, rax; TokenHandle
0x180017d7c  lea     rdx, [rbp+4Fh+Sid1]
0x180017d80  call    GetAppUserSID
0x180017d85  mov     ebx, eax
0x180017d87  test    eax, eax
0x180017d89  js      loc_180017F6F
0x180017d8f  mov     rcx, [rbp+4Fh+TokenHandle]; TokenHandle
0x180017d93  test    rcx, rcx
0x180017d96  jz      short loc_180017DA7
0x180017d98  lea     r8, [rbp+4Fh+var_88]
0x180017d9c  lea     rdx, [rbp+4Fh+Sid2]
0x180017da0  call    GetAppUserSID
0x180017da5  jmp     short loc_180017DB4
0x180017da7  lea     rdx, [rbp+4Fh+var_88]
0x180017dab  lea     rcx, [rbp+4Fh+Sid2]
0x180017daf  call    GetCurrentProcessAppUserSID
0x180017db4  mov     r15, [rbp+4Fh+Sid2]
0x180017db8  mov     ebx, eax
0x180017dba  mov     r14, [rbp+4Fh+Sid1]
0x180017dbe  test    eax, eax
0x180017dc0  js      loc_180017F65
0x180017dc6  mov     rdx, r15; Sid2
0x180017dc9  mov     rcx, r14; Sid1
0x180017dcc  call    cs:__imp_RtlEqualSid
0x180017dd2  mov     rdi, [rbp+4Fh+var_78]
0x180017dd6  mov     r12b, al
0x180017dd9  mov     rsi, [rbp+4Fh+var_88]
0x180017ddd  test    al, al
0x180017ddf  jz      short loc_180017E09
0x180017de1  test    rdi, rdi
0x180017de4  jnz     short loc_180017DF0
0x180017de6  test    rsi, rsi
0x180017de9  jz      short loc_180017E06
0x180017deb  test    rdi, rdi
0x180017dee  jz      short loc_180017E06
0x180017df0  test    rsi, rsi
0x180017df3  jz      short loc_180017E06
0x180017df5  mov     rdx, rsi; Sid2
0x180017df8  mov     rcx, rdi; Sid1
0x180017dfb  call    cs:__imp_RtlEqualSid
0x180017e01  mov     r12b, al
0x180017e04  jmp     short loc_180017E09
0x180017e06  xor     r12b, r12b
0x180017e09  cmp     dword ptr [rbp+4Fh+var_98], r13d
0x180017e0d  jz      loc_180017F2F
0x180017e13  mov     rcx, [rbp+4Fh+TokenHandle]
0x180017e17  test    rcx, rcx
0x180017e1a  jnz     short loc_180017E3E
0x180017e1c  lea     edx, [rcx+8]; DesiredAccess
0x180017e1f  xor     r8d, r8d; HandleAttributes
0x180017e22  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180017e26  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x180017e2a  call    cs:__imp_NtOpenProcessTokenEx
0x180017e30  mov     ebx, eax
0x180017e32  test    eax, eax
0x180017e34  jnz     loc_180017F80
0x180017e3a  mov     rcx, [rbp+4Fh+TokenHandle]; TokenHandle
0x180017e3e  lea     rdx, [rbp+4Fh+var_A8]
0x180017e42  call    GetIntegrityLevel
0x180017e47  mov     ebx, eax
0x180017e49  test    eax, eax
0x180017e4b  jnz     loc_180017F80
0x180017e51  mov     rcx, [rbp+4Fh+var_68]; TokenHandle
0x180017e55  lea     rdx, [rbp+4Fh+var_A4]
0x180017e59  call    GetIntegrityLevel
0x180017e5e  mov     ebx, eax
0x180017e60  test    eax, eax
0x180017e62  jnz     loc_180017F80
0x180017e68  mov     ecx, [rbp+4Fh+var_A8]
0x180017e6b  mov     eax, [rbp+4Fh+var_A4]
0x180017e6e  cmp     eax, ecx
0x180017e70  cmovb   ecx, eax
0x180017e73  mov     dword ptr [rbp+4Fh+Sid2], ecx
0x180017e76  lea     ecx, [rbx+1]; SubAuthorityCount
0x180017e79  call    cs:__imp_RtlLengthRequiredSid
0x180017e7f  mov     ecx, eax
0x180017e81  call    AccessHlprAlloc
0x180017e86  mov     qword ptr [rbp+4Fh+MandatoryFlags], rax
0x180017e8a  mov     rbx, rax
0x180017e8d  test    rax, rax
0x180017e90  jnz     short loc_180017E9F
0x180017e92  mov     ebx, 0C0000017h
0x180017e97  mov     r12, rax
0x180017e9a  jmp     loc_180017F83
0x180017e9f  mov     r8b, 1; SubAuthorityCount
0x180017ea2  lea     rdx, [rbp+4Fh+IdentifierAuthority]; IdentifierAuthority
0x180017ea6  mov     rcx, rbx; Sid
0x180017ea9  call    cs:__imp_RtlInitializeSid
0x180017eaf  xor     edx, edx; SubAuthority
0x180017eb1  mov     rcx, rbx; Sid
0x180017eb4  call    cs:__imp_RtlSubAuthoritySid
0x180017eba  mov     ecx, dword ptr [rbp+4Fh+Sid2]
0x180017ebd  mov     [rax], ecx
0x180017ebf  mov     rcx, rbx; Sid
0x180017ec2  call    cs:__imp_RtlLengthSid
0x180017ec8  mov     ebx, eax
0x180017eca  lea     rcx, [rbx+10h]
0x180017ece  call    AccessHlprAlloc
0x180017ed3  mov     r13, rax
0x180017ed6  test    rax, rax
0x180017ed9  jnz     short loc_180017EE9
0x180017edb  mov     ebx, 0C0000017h
0x180017ee0  mov     r12, qword ptr [rbp+4Fh+MandatoryFlags]
0x180017ee4  jmp     loc_180017F83
0x180017ee9  lea     edx, [rbx+10h]; AclSize
0x180017eec  mov     r8d, 2; AclRevision
0x180017ef2  mov     rcx, r13; Acl
0x180017ef5  call    cs:__imp_RtlCreateAcl
0x180017efb  mov     ebx, eax
0x180017efd  test    eax, eax
0x180017eff  js      short loc_180017EE0
0x180017f01  mov     eax, dword ptr [rbp+4Fh+var_98]
0x180017f04  xor     r8d, r8d; Flags
0x180017f07  mov     r9, qword ptr [rbp+4Fh+MandatoryFlags]; MandatoryFlags
0x180017f0b  mov     rcx, r13; Acl
0x180017f0e  mov     dword ptr [rsp+0F0h+LabelSid], eax; LabelSid
0x180017f12  mov     [rsp+0F0h+AceType], 11h; AceType
0x180017f17  lea     edx, [r8+2]; Revision
0x180017f1b  call    cs:__imp_RtlAddMandatoryAce
0x180017f21  mov     ebx, eax
0x180017f23  test    eax, eax
0x180017f25  js      short loc_180017EE0
0x180017f27  mov     eax, [rbp+4Fh+var_A4]
0x180017f2a  cmp     eax, [rbp+4Fh+var_A8]
0x180017f2d  jnz     short loc_180017F38
0x180017f2f  test    r12b, r12b
0x180017f32  jz      short loc_180017F38
0x180017f34  xor     ebx, ebx
0x180017f36  jmp     short loc_180017EE0
0x180017f38  mov     rax, [rbp+4Fh+var_60]
0x180017f3c  mov     r9, rsi; PSID
0x180017f3f  mov     [rsp+0F0h+var_C0], rax; __int64
0x180017f44  mov     r8, r15; Owner
0x180017f47  mov     eax, [rbp+4Fh+AccessMask]
0x180017f4a  mov     rdx, rdi; PSID
0x180017f4d  mov     [rsp+0F0h+LabelSid], r13; __int64
0x180017f52  mov     rcx, r14; Sid
0x180017f55  mov     dword ptr [rsp+0F0h+AceType], eax; AccessMask
0x180017f59  call    BuildSecurityDescriptorForSharingAccessInternal
0x180017f5e  mov     ebx, eax
0x180017f60  jmp     loc_180017EE0
0x180017f65  mov     rdi, [rbp+4Fh+var_78]
0x180017f69  mov     rsi, [rbp+4Fh+var_88]
0x180017f6d  jmp     short loc_180017F83
0x180017f6f  mov     r14, [rbp+4Fh+Sid1]
0x180017f73  mov     rdi, [rbp+4Fh+var_78]
0x180017f77  jmp     short loc_180017F83
0x180017f79  mov     ebx, 0C000000Dh
0x180017f7e  jmp     short loc_180017F83
0x180017f80  mov     r12, r13
0x180017f83  test    r14, r14
0x180017f86  jz      short loc_180017F90
0x180017f88  mov     rcx, r14
0x180017f8b  call    FreeTransientObjectSecurityDescriptor
0x180017f90  test    rdi, rdi
0x180017f93  jz      short loc_180017F9D
0x180017f95  mov     rcx, rdi
0x180017f98  call    FreeTransientObjectSecurityDescriptor
0x180017f9d  test    r15, r15
0x180017fa0  jz      short loc_180017FAA
0x180017fa2  mov     rcx, r15
0x180017fa5  call    FreeTransientObjectSecurityDescriptor
0x180017faa  test    rsi, rsi
0x180017fad  jz      short loc_180017FB7
0x180017faf  mov     rcx, rsi
0x180017fb2  call    FreeTransientObjectSecurityDescriptor
0x180017fb7  test    r13, r13
0x180017fba  jz      short loc_180017FC4
0x180017fbc  mov     rcx, r13
0x180017fbf  call    FreeTransientObjectSecurityDescriptor
0x180017fc4  test    r12, r12
0x180017fc7  jz      short loc_180017FD1
0x180017fc9  mov     rcx, r12
0x180017fcc  call    FreeTransientObjectSecurityDescriptor
0x180017fd1  test    ebx, ebx
0x180017fd3  jns     short loc_180017FE5
0x180017fd5  mov     ecx, ebx; Status
0x180017fd7  call    cs:__imp_RtlNtStatusToDosError
0x180017fdd  mov     ecx, eax; dwErrCode
0x180017fdf  call    cs:__imp_SetLastError
0x180017fe5  mov     eax, ebx
0x180017fe7  mov     rcx, [rbp+4Fh+var_50]
0x180017feb  xor     rcx, rsp; StackCookie
0x180017fee  call    __security_check_cookie
0x180017ff3  add     rsp, 0B8h
0x180017ffa  pop     r15
0x180017ffc  pop     r14
0x180017ffe  pop     r13
0x180018000  pop     r12
0x180018002  pop     rdi
0x180018003  pop     rsi
0x180018004  pop     rbx
0x180018005  pop     rbp
0x180018006  retn
```
