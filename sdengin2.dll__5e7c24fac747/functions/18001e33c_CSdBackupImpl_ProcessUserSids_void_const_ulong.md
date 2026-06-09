# CSdBackupImpl::_ProcessUserSids(void * const,ulong)

- ea: `0x18001e33c`
- end: `0x18001e5fb`
- name: `?_ProcessUserSids@CSdBackupImpl@@AEAAJQEAXK@Z`
- size: `703`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, PSECURITY_DESCRIPTOR pSecurityDescriptor, ULONG SecurityDescriptorLength)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016464`

## callees

- `0x180016924`
- `0x180017b18`
- `0x18001e33c`
- `0x1800212c4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001e3d4`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001e3d4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001e57d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001e57d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001e516`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001e516`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001e486`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001e486`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001e3fd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001e3fd`

## string_xrefs

- `0x18001e36b`: `CSdBackupImpl::_ProcessUserSids`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_ProcessUserSids(
        CSdBackupImpl *this,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        ULONG SecurityDescriptorLength)
{
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  bool v8; // zf
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-29h] BYREF
  __int16 v15; // [rsp+24h] [rbp-25h]
  __int16 v16; // [rsp+26h] [rbp-23h]
  unsigned int v17; // [rsp+58h] [rbp+Fh] BYREF
  unsigned int v18; // [rsp+5Ch] [rbp+13h] BYREF
  WINBOOL bSaclPresent; // [rsp+60h] [rbp+17h] BYREF
  WINBOOL bDaclPresent; // [rsp+64h] [rbp+1Bh] BYREF
  PSID pOwner; // [rsp+68h] [rbp+1Fh] BYREF
  PSID pGroup; // [rsp+70h] [rbp+27h] BYREF
  PACL pSacl; // [rsp+78h] [rbp+2Fh] BYREF
  PACL pDacl; // [rsp+80h] [rbp+37h] BYREF
  int v25; // [rsp+B8h] [rbp+6Fh] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+C8h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSdBackupImpl::_ProcessUserSids", 2856, 1);
  v25 = 0;
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  v17 = 0;
  v18 = 0;
  pOwner = 0;
  pGroup = 0;
  pSacl = 0;
  pDacl = 0;
  v6 = 2870;
  if ( !pSecurityDescriptor )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v14 = LastFailureAsHRESULT;
LABEL_4:
    v16 = v6;
    goto LABEL_31;
  }
  v14 = 0;
  v15 = 2870;
  v8 = RtlValidRelativeSecurityDescriptor(pSecurityDescriptor, SecurityDescriptorLength, 0xFu) == 0;
  v6 = 2871;
  if ( v8 )
  {
    LastFailureAsHRESULT = -2147023558;
    goto LABEL_3;
  }
  v14 = 0;
  v15 = 2871;
  if ( !GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v14 = LastFailureAsHRESULT;
    v6 = 2874;
    goto LABEL_4;
  }
  v14 = 0;
  v15 = 2874;
  LastFailureAsHRESULT = CSdBackupImpl::_CheckIfLocalSid(this, pOwner, &v17, &v25);
  v14 = LastFailureAsHRESULT;
  v6 = 2875;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_4;
  v15 = 2875;
  if ( v25 )
  {
    LastFailureAsHRESULT = CSdBackupImpl::_AddSidToMemList(this, pOwner, v17);
    v14 = LastFailureAsHRESULT;
    v6 = 2879;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_4;
    v15 = 2879;
  }
  if ( !GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bOwnerDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
    v14 = LastFailureAsHRESULT;
    v6 = 2884;
    goto LABEL_4;
  }
  v14 = 0;
  v15 = 2884;
  LastFailureAsHRESULT = CSdBackupImpl::_CheckIfLocalSid(this, pGroup, &v18, &v25);
  v14 = LastFailureAsHRESULT;
  v6 = 2885;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_4;
  v15 = 2885;
  if ( v25 )
  {
    LastFailureAsHRESULT = CSdBackupImpl::_AddSidToMemList(this, pGroup, v18);
    v14 = LastFailureAsHRESULT;
    v6 = 2889;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_4;
    v15 = 2889;
  }
  if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bOwnerDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
    v14 = LastFailureAsHRESULT;
    v6 = 2894;
    goto LABEL_4;
  }
  v14 = 0;
  v15 = 2894;
  if ( bSaclPresent && pSacl )
  {
    LastFailureAsHRESULT = CSdBackupImpl::_WalkAclListForSids(this, pSacl);
    v14 = LastFailureAsHRESULT;
    v6 = 2898;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_4;
    v15 = 2898;
  }
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
    v14 = LastFailureAsHRESULT;
    v6 = 2903;
    goto LABEL_4;
  }
  v14 = 0;
  v15 = 2903;
  LastFailureAsHRESULT = 0;
  if ( bDaclPresent && pDacl )
  {
    LastFailureAsHRESULT = CSdBackupImpl::_WalkAclListForSids(this, pDacl);
    v14 = LastFailureAsHRESULT;
    v6 = 2907;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v15 = 2907;
      goto LABEL_31;
    }
    goto LABEL_4;
  }
LABEL_31:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001e33c  mov     [rsp-8+arg_0], rbx
0x18001e341  mov     [rsp-8+arg_10], rsi
0x18001e346  push    rbp
0x18001e347  push    rdi
0x18001e348  push    r14
0x18001e34a  lea     rbp, [rsp-47h]
0x18001e34f  sub     rsp, 90h
0x18001e356  mov     ebx, r8d
0x18001e359  mov     rsi, rdx
0x18001e35c  mov     rdi, rcx
0x18001e35f  mov     r9d, 1; unsigned __int16
0x18001e365  mov     r8d, 0B28h; unsigned __int16
0x18001e36b  lea     rdx, aCsdbackupimplP_7; "CSdBackupImpl::_ProcessUserSids"
0x18001e372  lea     rcx, [rbp+57h+var_80]; this
0x18001e376  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e37b  xor     r14d, r14d
0x18001e37e  mov     [rbp+57h+arg_8], r14d
0x18001e382  mov     [rbp+57h+bOwnerDefaulted], r14d
0x18001e386  mov     [rbp+57h+bDaclPresent], r14d
0x18001e38a  mov     [rbp+57h+bSaclPresent], r14d
0x18001e38e  mov     [rbp+57h+var_48], r14d
0x18001e392  mov     [rbp+57h+var_44], r14d
0x18001e396  mov     [rbp+57h+pOwner], r14
0x18001e39a  mov     [rbp+57h+pGroup], r14
0x18001e39e  mov     [rbp+57h+pSacl], r14
0x18001e3a2  mov     [rbp+57h+pDacl], r14
0x18001e3a6  mov     eax, 0B36h
0x18001e3ab  test    rsi, rsi
0x18001e3ae  jnz     short loc_18001E3C1
0x18001e3b0  mov     ebx, 80070057h
0x18001e3b5  mov     [rbp+57h+var_80], ebx
0x18001e3b8  mov     [rbp+57h+var_7A], ax
0x18001e3bc  jmp     loc_18001E5D8
0x18001e3c1  mov     [rbp+57h+var_80], r14d
0x18001e3c5  mov     [rbp+57h+var_7C], ax
0x18001e3c9  mov     r8d, 0Fh; RequiredInformation
0x18001e3cf  mov     edx, ebx; SecurityDescriptorLength
0x18001e3d1  mov     rcx, rsi; SecurityDescriptorInput
0x18001e3d4  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18001e3da  test    al, al
0x18001e3dc  mov     eax, 0B37h
0x18001e3e1  jnz     short loc_18001E3EA
0x18001e3e3  mov     ebx, 8007053Ah
0x18001e3e8  jmp     short loc_18001E3B5
0x18001e3ea  mov     [rbp+57h+var_80], r14d
0x18001e3ee  mov     [rbp+57h+var_7C], ax
0x18001e3f2  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18001e3f6  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18001e3fa  mov     rcx, rsi; pSecurityDescriptor
0x18001e3fd  call    cs:__imp_GetSecurityDescriptorOwner
0x18001e403  test    eax, eax
0x18001e405  jnz     short loc_18001E418
0x18001e407  call    GetLastFailureAsHRESULT
0x18001e40c  mov     ebx, eax
0x18001e40e  mov     [rbp+57h+var_80], eax
0x18001e411  mov     eax, 0B3Ah
0x18001e416  jmp     short loc_18001E3B8
0x18001e418  mov     [rbp+57h+var_80], r14d
0x18001e41c  mov     eax, 0B3Ah
0x18001e421  mov     [rbp+57h+var_7C], ax
0x18001e425  lea     r9, [rbp+57h+arg_8]; int *
0x18001e429  lea     r8, [rbp+57h+var_48]; unsigned int *
0x18001e42d  mov     rdx, [rbp+57h+pOwner]; void *
0x18001e431  mov     rcx, rdi; this
0x18001e434  call    ?_CheckIfLocalSid@CSdBackupImpl@@AEAAJQEAXPEAKPEAH@Z; CSdBackupImpl::_CheckIfLocalSid(void * const,ulong *,int *)
0x18001e439  mov     ebx, eax
0x18001e43b  mov     [rbp+57h+var_80], eax
0x18001e43e  test    eax, eax
0x18001e440  mov     eax, 0B3Bh
0x18001e445  js      loc_18001E3B8
0x18001e44b  mov     [rbp+57h+var_7C], ax
0x18001e44f  cmp     [rbp+57h+arg_8], r14d
0x18001e453  jz      short loc_18001E47B
0x18001e455  mov     r8d, [rbp+57h+var_48]; unsigned int
0x18001e459  mov     rdx, [rbp+57h+pOwner]; void *
0x18001e45d  mov     rcx, rdi; this
0x18001e460  call    ?_AddSidToMemList@CSdBackupImpl@@AEAAJQEAXK@Z; CSdBackupImpl::_AddSidToMemList(void * const,ulong)
0x18001e465  mov     ebx, eax
0x18001e467  mov     [rbp+57h+var_80], eax
0x18001e46a  test    eax, eax
0x18001e46c  mov     eax, 0B3Fh
0x18001e471  js      loc_18001E3B8
0x18001e477  mov     [rbp+57h+var_7C], ax
0x18001e47b  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbGroupDefaulted
0x18001e47f  lea     rdx, [rbp+57h+pGroup]; pGroup
0x18001e483  mov     rcx, rsi; pSecurityDescriptor
0x18001e486  call    cs:__imp_GetSecurityDescriptorGroup
0x18001e48c  test    eax, eax
0x18001e48e  jnz     short loc_18001E4A4
0x18001e490  call    GetLastFailureAsHRESULT
0x18001e495  mov     ebx, eax
0x18001e497  mov     [rbp+57h+var_80], eax
0x18001e49a  mov     eax, 0B44h
0x18001e49f  jmp     loc_18001E3B8
0x18001e4a4  mov     [rbp+57h+var_80], r14d
0x18001e4a8  mov     eax, 0B44h
0x18001e4ad  mov     [rbp+57h+var_7C], ax
0x18001e4b1  lea     r9, [rbp+57h+arg_8]; int *
0x18001e4b5  lea     r8, [rbp+57h+var_44]; unsigned int *
0x18001e4b9  mov     rdx, [rbp+57h+pGroup]; void *
0x18001e4bd  mov     rcx, rdi; this
0x18001e4c0  call    ?_CheckIfLocalSid@CSdBackupImpl@@AEAAJQEAXPEAKPEAH@Z; CSdBackupImpl::_CheckIfLocalSid(void * const,ulong *,int *)
0x18001e4c5  mov     ebx, eax
0x18001e4c7  mov     [rbp+57h+var_80], eax
0x18001e4ca  test    eax, eax
0x18001e4cc  mov     eax, 0B45h
0x18001e4d1  js      loc_18001E3B8
0x18001e4d7  mov     [rbp+57h+var_7C], ax
0x18001e4db  cmp     [rbp+57h+arg_8], r14d
0x18001e4df  jz      short loc_18001E507
0x18001e4e1  mov     r8d, [rbp+57h+var_44]; unsigned int
0x18001e4e5  mov     rdx, [rbp+57h+pGroup]; void *
0x18001e4e9  mov     rcx, rdi; this
0x18001e4ec  call    ?_AddSidToMemList@CSdBackupImpl@@AEAAJQEAXK@Z; CSdBackupImpl::_AddSidToMemList(void * const,ulong)
0x18001e4f1  mov     ebx, eax
0x18001e4f3  mov     [rbp+57h+var_80], eax
0x18001e4f6  test    eax, eax
0x18001e4f8  mov     eax, 0B49h
0x18001e4fd  js      loc_18001E3B8
0x18001e503  mov     [rbp+57h+var_7C], ax
0x18001e507  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbSaclDefaulted
0x18001e50b  lea     r8, [rbp+57h+pSacl]; pSacl
0x18001e50f  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18001e513  mov     rcx, rsi; pSecurityDescriptor
0x18001e516  call    cs:__imp_GetSecurityDescriptorSacl
0x18001e51c  test    eax, eax
0x18001e51e  jnz     short loc_18001E534
0x18001e520  call    GetLastFailureAsHRESULT
0x18001e525  mov     ebx, eax
0x18001e527  mov     [rbp+57h+var_80], eax
0x18001e52a  mov     eax, 0B4Eh
0x18001e52f  jmp     loc_18001E3B8
0x18001e534  mov     [rbp+57h+var_80], r14d
0x18001e538  mov     eax, 0B4Eh
0x18001e53d  mov     [rbp+57h+var_7C], ax
0x18001e541  cmp     [rbp+57h+bSaclPresent], r14d
0x18001e545  jz      short loc_18001E56E
0x18001e547  mov     rdx, [rbp+57h+pSacl]; pAcl
0x18001e54b  test    rdx, rdx
0x18001e54e  jz      short loc_18001E56E
0x18001e550  mov     rcx, rdi; this
0x18001e553  call    ?_WalkAclListForSids@CSdBackupImpl@@AEAAJPEAU_ACL@@@Z; CSdBackupImpl::_WalkAclListForSids(_ACL *)
0x18001e558  mov     ebx, eax
0x18001e55a  mov     [rbp+57h+var_80], eax
0x18001e55d  test    eax, eax
0x18001e55f  mov     eax, 0B52h
0x18001e564  js      loc_18001E3B8
0x18001e56a  mov     [rbp+57h+var_7C], ax
0x18001e56e  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbDaclDefaulted
0x18001e572  lea     r8, [rbp+57h+pDacl]; pDacl
0x18001e576  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18001e57a  mov     rcx, rsi; pSecurityDescriptor
0x18001e57d  call    cs:__imp_GetSecurityDescriptorDacl
0x18001e583  test    eax, eax
0x18001e585  jnz     short loc_18001E59B
0x18001e587  call    GetLastFailureAsHRESULT
0x18001e58c  mov     ebx, eax
0x18001e58e  mov     [rbp+57h+var_80], eax
0x18001e591  mov     eax, 0B57h
0x18001e596  jmp     loc_18001E3B8
0x18001e59b  mov     [rbp+57h+var_80], r14d
0x18001e59f  mov     eax, 0B57h
0x18001e5a4  mov     [rbp+57h+var_7C], ax
0x18001e5a8  mov     ebx, r14d
0x18001e5ab  cmp     [rbp+57h+bDaclPresent], r14d
0x18001e5af  jz      short loc_18001E5D8
0x18001e5b1  mov     rdx, [rbp+57h+pDacl]; pAcl
0x18001e5b5  test    rdx, rdx
0x18001e5b8  jz      short loc_18001E5D8
0x18001e5ba  mov     rcx, rdi; this
0x18001e5bd  call    ?_WalkAclListForSids@CSdBackupImpl@@AEAAJPEAU_ACL@@@Z; CSdBackupImpl::_WalkAclListForSids(_ACL *)
0x18001e5c2  mov     ebx, eax
0x18001e5c4  mov     [rbp+57h+var_80], eax
0x18001e5c7  test    eax, eax
0x18001e5c9  mov     eax, 0B5Bh
0x18001e5ce  js      loc_18001E3B8
0x18001e5d4  mov     [rbp+57h+var_7C], ax
0x18001e5d8  lea     rcx, [rbp+57h+var_80]; this
0x18001e5dc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e5e1  mov     eax, ebx
0x18001e5e3  lea     r11, [rsp+0A0h+var_10]
0x18001e5eb  mov     rbx, [r11+20h]
0x18001e5ef  mov     rsi, [r11+30h]
0x18001e5f3  mov     rsp, r11
0x18001e5f6  pop     r14
0x18001e5f8  pop     rdi
0x18001e5f9  pop     rbp
0x18001e5fa  retn
```
