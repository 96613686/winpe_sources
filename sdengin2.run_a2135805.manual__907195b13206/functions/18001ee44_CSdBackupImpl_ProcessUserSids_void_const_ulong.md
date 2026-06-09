# CSdBackupImpl::_ProcessUserSids(void * const,ulong)

- ea: `0x18001ee44`
- end: `0x18001f122`
- name: `?_ProcessUserSids@CSdBackupImpl@@AEAAJQEAXK@Z`
- size: `734`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, PSECURITY_DESCRIPTOR pSecurityDescriptor, ULONG SecurityDescriptorLength)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016de4`

## callees

- `0x1800172ac`
- `0x1800184f0`
- `0x18001ee44`
- `0x180021eb8`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001eedc`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001eedc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001f09d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001f09d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001f030`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001f030`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001ef9a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001ef9a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001ef0b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001ef0b`

## string_xrefs

- `0x18001ee73`: `CSdBackupImpl::_ProcessUserSids`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSdBackupImpl::_ProcessUserSids", 0xB28u, 1u);
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
0x18001ee44  mov     [rsp-8+arg_0], rbx
0x18001ee49  mov     [rsp-8+arg_10], rsi
0x18001ee4e  push    rbp
0x18001ee4f  push    rdi
0x18001ee50  push    r14
0x18001ee52  lea     rbp, [rsp-47h]
0x18001ee57  sub     rsp, 90h
0x18001ee5e  mov     ebx, r8d
0x18001ee61  mov     rsi, rdx
0x18001ee64  mov     rdi, rcx
0x18001ee67  mov     r9d, 1; unsigned __int16
0x18001ee6d  mov     r8d, 0B28h; unsigned __int16
0x18001ee73  lea     rdx, aCsdbackupimplP_7; "CSdBackupImpl::_ProcessUserSids"
0x18001ee7a  lea     rcx, [rbp+57h+var_80]; this
0x18001ee7e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ee83  xor     r14d, r14d
0x18001ee86  mov     [rbp+57h+arg_8], r14d
0x18001ee8a  mov     [rbp+57h+bOwnerDefaulted], r14d
0x18001ee8e  mov     [rbp+57h+bDaclPresent], r14d
0x18001ee92  mov     [rbp+57h+bSaclPresent], r14d
0x18001ee96  mov     [rbp+57h+var_48], r14d
0x18001ee9a  mov     [rbp+57h+var_44], r14d
0x18001ee9e  mov     [rbp+57h+pOwner], r14
0x18001eea2  mov     [rbp+57h+pGroup], r14
0x18001eea6  mov     [rbp+57h+pSacl], r14
0x18001eeaa  mov     [rbp+57h+pDacl], r14
0x18001eeae  mov     eax, 0B36h
0x18001eeb3  test    rsi, rsi
0x18001eeb6  jnz     short loc_18001EEC9
0x18001eeb8  mov     ebx, 80070057h
0x18001eebd  mov     [rbp+57h+var_80], ebx
0x18001eec0  mov     [rbp+57h+var_7A], ax
0x18001eec4  jmp     loc_18001F0FE
0x18001eec9  mov     [rbp+57h+var_80], r14d
0x18001eecd  mov     [rbp+57h+var_7C], ax
0x18001eed1  mov     r8d, 0Fh; RequiredInformation
0x18001eed7  mov     edx, ebx; SecurityDescriptorLength
0x18001eed9  mov     rcx, rsi; SecurityDescriptorInput
0x18001eedc  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18001eee3  nop     dword ptr [rax+rax+00h]
0x18001eee8  test    al, al
0x18001eeea  mov     eax, 0B37h
0x18001eeef  jnz     short loc_18001EEF8
0x18001eef1  mov     ebx, 8007053Ah
0x18001eef6  jmp     short loc_18001EEBD
0x18001eef8  mov     [rbp+57h+var_80], r14d
0x18001eefc  mov     [rbp+57h+var_7C], ax
0x18001ef00  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18001ef04  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18001ef08  mov     rcx, rsi; pSecurityDescriptor
0x18001ef0b  call    cs:__imp_GetSecurityDescriptorOwner
0x18001ef12  nop     dword ptr [rax+rax+00h]
0x18001ef17  test    eax, eax
0x18001ef19  jnz     short loc_18001EF2C
0x18001ef1b  call    GetLastFailureAsHRESULT
0x18001ef20  mov     ebx, eax
0x18001ef22  mov     [rbp+57h+var_80], eax
0x18001ef25  mov     eax, 0B3Ah
0x18001ef2a  jmp     short loc_18001EEC0
0x18001ef2c  mov     [rbp+57h+var_80], r14d
0x18001ef30  mov     eax, 0B3Ah
0x18001ef35  mov     [rbp+57h+var_7C], ax
0x18001ef39  lea     r9, [rbp+57h+arg_8]; int *
0x18001ef3d  lea     r8, [rbp+57h+var_48]; unsigned int *
0x18001ef41  mov     rdx, [rbp+57h+pOwner]; void *
0x18001ef45  mov     rcx, rdi; this
0x18001ef48  call    ?_CheckIfLocalSid@CSdBackupImpl@@AEAAJQEAXPEAKPEAH@Z; CSdBackupImpl::_CheckIfLocalSid(void * const,ulong *,int *)
0x18001ef4d  mov     ebx, eax
0x18001ef4f  mov     [rbp+57h+var_80], eax
0x18001ef52  test    eax, eax
0x18001ef54  mov     eax, 0B3Bh
0x18001ef59  js      loc_18001EEC0
0x18001ef5f  mov     [rbp+57h+var_7C], ax
0x18001ef63  cmp     [rbp+57h+arg_8], r14d
0x18001ef67  jz      short loc_18001EF8F
0x18001ef69  mov     r8d, [rbp+57h+var_48]; unsigned int
0x18001ef6d  mov     rdx, [rbp+57h+pOwner]; void *
0x18001ef71  mov     rcx, rdi; this
0x18001ef74  call    ?_AddSidToMemList@CSdBackupImpl@@AEAAJQEAXK@Z; CSdBackupImpl::_AddSidToMemList(void * const,ulong)
0x18001ef79  mov     ebx, eax
0x18001ef7b  mov     [rbp+57h+var_80], eax
0x18001ef7e  test    eax, eax
0x18001ef80  mov     eax, 0B3Fh
0x18001ef85  js      loc_18001EEC0
0x18001ef8b  mov     [rbp+57h+var_7C], ax
0x18001ef8f  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbGroupDefaulted
0x18001ef93  lea     rdx, [rbp+57h+pGroup]; pGroup
0x18001ef97  mov     rcx, rsi; pSecurityDescriptor
0x18001ef9a  call    cs:__imp_GetSecurityDescriptorGroup
0x18001efa1  nop     dword ptr [rax+rax+00h]
0x18001efa6  test    eax, eax
0x18001efa8  jnz     short loc_18001EFBE
0x18001efaa  call    GetLastFailureAsHRESULT
0x18001efaf  mov     ebx, eax
0x18001efb1  mov     [rbp+57h+var_80], eax
0x18001efb4  mov     eax, 0B44h
0x18001efb9  jmp     loc_18001EEC0
0x18001efbe  mov     [rbp+57h+var_80], r14d
0x18001efc2  mov     eax, 0B44h
0x18001efc7  mov     [rbp+57h+var_7C], ax
0x18001efcb  lea     r9, [rbp+57h+arg_8]; int *
0x18001efcf  lea     r8, [rbp+57h+var_44]; unsigned int *
0x18001efd3  mov     rdx, [rbp+57h+pGroup]; void *
0x18001efd7  mov     rcx, rdi; this
0x18001efda  call    ?_CheckIfLocalSid@CSdBackupImpl@@AEAAJQEAXPEAKPEAH@Z; CSdBackupImpl::_CheckIfLocalSid(void * const,ulong *,int *)
0x18001efdf  mov     ebx, eax
0x18001efe1  mov     [rbp+57h+var_80], eax
0x18001efe4  test    eax, eax
0x18001efe6  mov     eax, 0B45h
0x18001efeb  js      loc_18001EEC0
0x18001eff1  mov     [rbp+57h+var_7C], ax
0x18001eff5  cmp     [rbp+57h+arg_8], r14d
0x18001eff9  jz      short loc_18001F021
0x18001effb  mov     r8d, [rbp+57h+var_44]; unsigned int
0x18001efff  mov     rdx, [rbp+57h+pGroup]; void *
0x18001f003  mov     rcx, rdi; this
0x18001f006  call    ?_AddSidToMemList@CSdBackupImpl@@AEAAJQEAXK@Z; CSdBackupImpl::_AddSidToMemList(void * const,ulong)
0x18001f00b  mov     ebx, eax
0x18001f00d  mov     [rbp+57h+var_80], eax
0x18001f010  test    eax, eax
0x18001f012  mov     eax, 0B49h
0x18001f017  js      loc_18001EEC0
0x18001f01d  mov     [rbp+57h+var_7C], ax
0x18001f021  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbSaclDefaulted
0x18001f025  lea     r8, [rbp+57h+pSacl]; pSacl
0x18001f029  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18001f02d  mov     rcx, rsi; pSecurityDescriptor
0x18001f030  call    cs:__imp_GetSecurityDescriptorSacl
0x18001f037  nop     dword ptr [rax+rax+00h]
0x18001f03c  test    eax, eax
0x18001f03e  jnz     short loc_18001F054
0x18001f040  call    GetLastFailureAsHRESULT
0x18001f045  mov     ebx, eax
0x18001f047  mov     [rbp+57h+var_80], eax
0x18001f04a  mov     eax, 0B4Eh
0x18001f04f  jmp     loc_18001EEC0
0x18001f054  mov     [rbp+57h+var_80], r14d
0x18001f058  mov     eax, 0B4Eh
0x18001f05d  mov     [rbp+57h+var_7C], ax
0x18001f061  cmp     [rbp+57h+bSaclPresent], r14d
0x18001f065  jz      short loc_18001F08E
0x18001f067  mov     rdx, [rbp+57h+pSacl]; pAcl
0x18001f06b  test    rdx, rdx
0x18001f06e  jz      short loc_18001F08E
0x18001f070  mov     rcx, rdi; this
0x18001f073  call    ?_WalkAclListForSids@CSdBackupImpl@@AEAAJPEAU_ACL@@@Z; CSdBackupImpl::_WalkAclListForSids(_ACL *)
0x18001f078  mov     ebx, eax
0x18001f07a  mov     [rbp+57h+var_80], eax
0x18001f07d  test    eax, eax
0x18001f07f  mov     eax, 0B52h
0x18001f084  js      loc_18001EEC0
0x18001f08a  mov     [rbp+57h+var_7C], ax
0x18001f08e  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbDaclDefaulted
0x18001f092  lea     r8, [rbp+57h+pDacl]; pDacl
0x18001f096  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18001f09a  mov     rcx, rsi; pSecurityDescriptor
0x18001f09d  call    cs:__imp_GetSecurityDescriptorDacl
0x18001f0a4  nop     dword ptr [rax+rax+00h]
0x18001f0a9  test    eax, eax
0x18001f0ab  jnz     short loc_18001F0C1
0x18001f0ad  call    GetLastFailureAsHRESULT
0x18001f0b2  mov     ebx, eax
0x18001f0b4  mov     [rbp+57h+var_80], eax
0x18001f0b7  mov     eax, 0B57h
0x18001f0bc  jmp     loc_18001EEC0
0x18001f0c1  mov     [rbp+57h+var_80], r14d
0x18001f0c5  mov     eax, 0B57h
0x18001f0ca  mov     [rbp+57h+var_7C], ax
0x18001f0ce  mov     ebx, r14d
0x18001f0d1  cmp     [rbp+57h+bDaclPresent], r14d
0x18001f0d5  jz      short loc_18001F0FE
0x18001f0d7  mov     rdx, [rbp+57h+pDacl]; pAcl
0x18001f0db  test    rdx, rdx
0x18001f0de  jz      short loc_18001F0FE
0x18001f0e0  mov     rcx, rdi; this
0x18001f0e3  call    ?_WalkAclListForSids@CSdBackupImpl@@AEAAJPEAU_ACL@@@Z; CSdBackupImpl::_WalkAclListForSids(_ACL *)
0x18001f0e8  mov     ebx, eax
0x18001f0ea  mov     [rbp+57h+var_80], eax
0x18001f0ed  test    eax, eax
0x18001f0ef  mov     eax, 0B5Bh
0x18001f0f4  js      loc_18001EEC0
0x18001f0fa  mov     [rbp+57h+var_7C], ax
0x18001f0fe  lea     rcx, [rbp+57h+var_80]; this
0x18001f102  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001f107  mov     eax, ebx
0x18001f109  lea     r11, [rsp+0A0h+var_10]
0x18001f111  mov     rbx, [r11+20h]
0x18001f115  mov     rsi, [r11+30h]
0x18001f119  mov     rsp, r11
0x18001f11c  pop     r14
0x18001f11e  pop     rdi
0x18001f11f  pop     rbp
0x18001f120  retn
```
