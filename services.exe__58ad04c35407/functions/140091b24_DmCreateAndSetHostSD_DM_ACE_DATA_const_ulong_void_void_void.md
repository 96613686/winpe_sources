# DmCreateAndSetHostSD(DM_ACE_DATA * const,ulong,void *,void *,void * *)

- ea: `0x140091b24`
- end: `0x140091e6c`
- name: `?DmCreateAndSetHostSD@@YAKQEAUDM_ACE_DATA@@KPEAX1PEAPEAX@Z`
- size: `840`
- prototype: `__int64 __fastcall(PSID **, __int64, void *, void *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14008f640`

## callees

- `0x140004c58`
- `0x14001f99c`
- `0x140029228`
- `0x140044300`
- `0x140091b24`
- `0x140091f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140091c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140091c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140091d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140091df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140091c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140091c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140091d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140091df9`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x140091d41`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x140091d41`
- `api-ms-win-security-base-l1-1-0!AddAuditAccessAceEx` at `0x140091d1b`
- `api-ms-win-security-base-l1-1-0!AddAuditAccessAceEx` at `0x140091d1b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140091da7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140091da7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140091db9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140091db9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140091d94`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140091d94`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140091dd4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140091dd4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140091d67`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140091d67`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140091c0a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140091c84`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140091c0a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140091c84`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x140091def`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x140091def`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140091b68`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140091b7d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140091b68`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140091b7d`

## pseudocode

```c
__int64 __fastcall DmCreateAndSetHostSD(PSID **a1, __int64 a2, void *a3, void *a4, void **a5)
{
  int v5; // edi
  int v6; // ebp
  unsigned int i; // ebx
  const struct std::nothrow_t *v10; // rdx
  __int64 v11; // rbx
  DWORD v12; // r12d
  struct _ACL *v13; // rax
  struct _ACL *v14; // rdi
  DWORD LastError; // ebx
  struct _ACL *v17; // rbp
  PRPC_ASYNC_STATE v18; // rcx
  __int64 v19; // rdx
  struct _ACL *v20; // r15
  struct _ACL *v21; // rbx
  struct _ACL *v22; // r14
  unsigned int j; // ebp
  BOOL v24; // eax

  v5 = 0;
  v6 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( !LOBYTE(a1[2 * i]) || LOBYTE(a1[2 * i]) == 1 )
    {
      v5 += GetLengthSid(*a1[2 * i + 1]) + 8;
    }
    else
    {
      if ( LOBYTE(a1[2 * i]) != 2 )
        return 87;
      v6 += GetLengthSid(*a1[2 * i + 1]) + 8;
    }
  }
  v11 = (unsigned int)(v5 + 8);
  v12 = v6 + 8;
  if ( !v5 )
    v11 = 0;
  if ( !v6 )
    v12 = 0;
  v13 = (struct _ACL *)operator new(v12 + (_DWORD)v11 + 40, v10);
  v14 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 10, WPP_e3511582f2a533ad198c1a3640c6c2ac_Traceguids);
    }
    return 14;
  }
  v17 = v13 + 5;
  if ( (_DWORD)v11 )
  {
    if ( !InitializeAcl(v13 + 5, v11, 2u) )
    {
      LastError = GetLastError();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
      {
        goto LABEL_51;
      }
      v19 = 11;
LABEL_25:
      WPP_SF_d(v18->u.APC.hThread, v19, WPP_e3511582f2a533ad198c1a3640c6c2ac_Traceguids, LastError);
LABEL_51:
      if ( !LastError )
        goto LABEL_58;
LABEL_52:
      operator delete(v14);
      return LastError;
    }
    v20 = v17;
    v21 = (struct _ACL *)((char *)v17 + v11);
  }
  else
  {
    v20 = 0;
    v21 = v13 + 5;
  }
  v22 = 0;
  if ( v12 )
  {
    if ( !InitializeAcl(v21, v12, 2u) )
    {
      LastError = GetLastError();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
      {
        goto LABEL_51;
      }
      v19 = 12;
      goto LABEL_25;
    }
    v22 = v21;
  }
  for ( j = 0; j < 2; ++j )
  {
    if ( LOBYTE(a1[2 * j]) )
    {
      if ( LOBYTE(a1[2 * j]) == 1 )
      {
        v24 = AddAccessDeniedAceEx(v20, 2u, BYTE1(a1[2 * j]), HIDWORD(a1[2 * j]), *a1[2 * j + 1]);
      }
      else
      {
        if ( LOBYTE(a1[2 * j]) != 2 )
          continue;
        v24 = AddAuditAccessAceEx(v22, 2u, BYTE1(a1[2 * j]), HIDWORD(a1[2 * j]), *a1[2 * j + 1], 0, 0);
      }
    }
    else
    {
      v24 = AddAccessAllowedAceEx(v20, 2u, BYTE1(a1[2 * j]), HIDWORD(a1[2 * j]), *a1[2 * j + 1]);
    }
    if ( !v24 )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->u.APC.hThread, 13, WPP_e3511582f2a533ad198c1a3640c6c2ac_Traceguids);
        }
        goto LABEL_52;
      }
    }
  }
  if ( !InitializeSecurityDescriptor(v14, 1u)
    || !SetSecurityDescriptorOwner(v14, a3, 0)
    || !SetSecurityDescriptorGroup(v14, 0, 0)
    || !SetSecurityDescriptorDacl(v14, v20 != 0, v20, 0)
    || !SetSecurityDescriptorSacl(v14, v22 != 0, v22, 0) )
  {
    LastError = GetLastError();
    goto LABEL_51;
  }
  LastError = 0;
LABEL_58:
  *a5 = v14;
  return LastError;
}

```

## disassembly

```asm
0x140091b24  push    rbx
0x140091b26  push    rbp
0x140091b27  push    rsi
0x140091b28  push    rdi
0x140091b29  push    r12
0x140091b2b  push    r13
0x140091b2d  push    r14
0x140091b2f  push    r15
0x140091b31  sub     rsp, 48h
0x140091b35  xor     edi, edi
0x140091b37  xor     ebp, ebp
0x140091b39  mov     r13, r8
0x140091b3c  mov     rsi, rcx
0x140091b3f  xor     ebx, ebx
0x140091b41  lea     r14d, [rdi+2]
0x140091b45  mov     edx, ebx
0x140091b47  add     rdx, rdx
0x140091b4a  movzx   ecx, byte ptr [rsi+rdx*8]
0x140091b4e  test    ecx, ecx
0x140091b50  jz      short loc_140091B75
0x140091b52  sub     ecx, 1
0x140091b55  jz      short loc_140091B75
0x140091b57  cmp     ecx, 1
0x140091b5a  jnz     loc_140091BF0
0x140091b60  mov     rcx, [rsi+rdx*8+8]
0x140091b65  mov     rcx, [rcx]; pSid
0x140091b68  call    cs:__imp_GetLengthSid
0x140091b6e  add     ebp, 8
0x140091b71  add     ebp, eax
0x140091b73  jmp     short loc_140091B88
0x140091b75  mov     rcx, [rsi+rdx*8+8]
0x140091b7a  mov     rcx, [rcx]; pSid
0x140091b7d  call    cs:__imp_GetLengthSid
0x140091b83  add     edi, 8
0x140091b86  add     edi, eax
0x140091b88  inc     ebx
0x140091b8a  cmp     ebx, r14d
0x140091b8d  jb      short loc_140091B45
0x140091b8f  test    edi, edi
0x140091b91  lea     ebx, [rdi+8]
0x140091b94  lea     r12d, [rbp+8]
0x140091b98  cmovz   ebx, edi
0x140091b9b  test    ebp, ebp
0x140091b9d  cmovz   r12d, ebp
0x140091ba1  lea     ecx, [rbx+28h]
0x140091ba4  add     ecx, r12d; Size
0x140091ba7  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x140091bac  mov     rdi, rax
0x140091baf  test    rax, rax
0x140091bb2  jnz     short loc_140091BFA
0x140091bb4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140091bbb  lea     rax, WPP_GLOBAL_Control
0x140091bc2  cmp     rcx, rax
0x140091bc5  jz      short loc_140091BE6
0x140091bc7  test    byte ptr [rcx+44h], 8
0x140091bcb  jz      short loc_140091BE6
0x140091bcd  cmp     [rcx+41h], r14b
0x140091bd1  jb      short loc_140091BE6
0x140091bd3  mov     rcx, [rcx+38h]
0x140091bd7  lea     edx, [rdi+0Ah]
0x140091bda  lea     r8, WPP_e3511582f2a533ad198c1a3640c6c2ac_Traceguids
0x140091be1  call    WPP_SF_
0x140091be6  mov     ebx, 0Eh
0x140091beb  jmp     loc_140091E59
0x140091bf0  mov     eax, 57h ; 'W'
0x140091bf5  jmp     loc_140091E5B
0x140091bfa  lea     rbp, [rax+28h]
0x140091bfe  test    ebx, ebx
0x140091c00  jz      short loc_140091C6C
0x140091c02  mov     r8d, r14d; dwAclRevision
0x140091c05  mov     edx, ebx; nAclLength
0x140091c07  mov     rcx, rbp; pAcl
0x140091c0a  call    cs:__imp_InitializeAcl
0x140091c10  test    eax, eax
0x140091c12  jnz     short loc_140091C64
0x140091c14  call    cs:__imp_GetLastError
0x140091c1a  mov     ebx, eax
0x140091c1c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140091c23  lea     rax, WPP_GLOBAL_Control
0x140091c2a  cmp     rcx, rax
0x140091c2d  jz      loc_140091E01
0x140091c33  test    byte ptr [rcx+44h], 8
0x140091c37  jz      loc_140091E01
0x140091c3d  cmp     [rcx+41h], r14b
0x140091c41  jb      loc_140091E01
0x140091c47  mov     edx, 0Bh
0x140091c4c  mov     rcx, [rcx+38h]
0x140091c50  lea     r8, WPP_e3511582f2a533ad198c1a3640c6c2ac_Traceguids
0x140091c57  mov     r9d, ebx
0x140091c5a  call    WPP_SF_d
0x140091c5f  jmp     loc_140091E01
0x140091c64  mov     r15, rbp
0x140091c67  add     rbx, rbp
0x140091c6a  jmp     short loc_140091C72
0x140091c6c  xor     r15d, r15d
0x140091c6f  mov     rbx, rbp
0x140091c72  xor     r14d, r14d
0x140091c75  test    r12d, r12d
0x140091c78  jz      short loc_140091CCA
0x140091c7a  lea     r8d, [r14+2]; dwAclRevision
0x140091c7e  mov     edx, r12d; nAclLength
0x140091c81  mov     rcx, rbx; pAcl
0x140091c84  call    cs:__imp_InitializeAcl
0x140091c8a  test    eax, eax
0x140091c8c  jnz     short loc_140091CC7
0x140091c8e  call    cs:__imp_GetLastError
0x140091c94  mov     ebx, eax
0x140091c96  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140091c9d  lea     rax, WPP_GLOBAL_Control
0x140091ca4  cmp     rcx, rax
0x140091ca7  jz      loc_140091E01
0x140091cad  test    byte ptr [rcx+44h], 8
0x140091cb1  jz      loc_140091E01
0x140091cb7  cmp     byte ptr [rcx+41h], 2
0x140091cbb  jb      loc_140091E01
0x140091cc1  lea     edx, [r14+0Ch]
0x140091cc5  jmp     short loc_140091C4C
0x140091cc7  mov     r14, rbx
0x140091cca  xor     ebp, ebp
0x140091ccc  lea     r12d, [rbp+2]
0x140091cd0  mov     r9d, ebp
0x140091cd3  add     r9, r9
0x140091cd6  movzx   ecx, byte ptr [rsi+r9*8]
0x140091cdb  test    ecx, ecx
0x140091cdd  jz      short loc_140091D49
0x140091cdf  sub     ecx, 1
0x140091ce2  jz      short loc_140091D23
0x140091ce4  cmp     ecx, 1
0x140091ce7  jnz     loc_140091D81
0x140091ced  mov     rax, [rsi+r9*8+8]
0x140091cf2  mov     edx, r12d; dwAceRevision
0x140091cf5  movzx   r8d, byte ptr [rsi+r9*8+1]; AceFlags
0x140091cfb  mov     rcx, r14; pAcl
0x140091cfe  mov     r9d, [rsi+r9*8+4]; dwAccessMask
0x140091d03  mov     [rsp+88h+bAuditFailure], 0; bAuditFailure
0x140091d0b  mov     rax, [rax]
0x140091d0e  mov     [rsp+88h+bAuditSuccess], 0; bAuditSuccess
0x140091d16  mov     [rsp+88h+pSid], rax; pSid
0x140091d1b  call    cs:__imp_AddAuditAccessAceEx
0x140091d21  jmp     short loc_140091D6D
0x140091d23  mov     rax, [rsi+r9*8+8]
0x140091d28  mov     edx, r12d; dwAceRevision
0x140091d2b  movzx   r8d, byte ptr [rsi+r9*8+1]; AceFlags
0x140091d31  mov     rcx, r15; pAcl
0x140091d34  mov     r9d, [rsi+r9*8+4]; AccessMask
0x140091d39  mov     rax, [rax]
0x140091d3c  mov     [rsp+88h+pSid], rax; pSid
0x140091d41  call    cs:__imp_AddAccessDeniedAceEx
0x140091d47  jmp     short loc_140091D6D
0x140091d49  mov     rax, [rsi+r9*8+8]
0x140091d4e  mov     edx, r12d; dwAceRevision
0x140091d51  movzx   r8d, byte ptr [rsi+r9*8+1]; AceFlags
0x140091d57  mov     rcx, r15; pAcl
0x140091d5a  mov     r9d, [rsi+r9*8+4]; AccessMask
0x140091d5f  mov     rax, [rax]
0x140091d62  mov     [rsp+88h+pSid], rax; pSid
0x140091d67  call    cs:__imp_AddAccessAllowedAceEx
0x140091d6d  test    eax, eax
0x140091d6f  jnz     short loc_140091D81
0x140091d71  call    cs:__imp_GetLastError
0x140091d77  mov     ebx, eax
0x140091d79  test    eax, eax
0x140091d7b  jnz     loc_140091E0F
0x140091d81  inc     ebp
0x140091d83  cmp     ebp, r12d
0x140091d86  jb      loc_140091CD0
0x140091d8c  mov     edx, 1; dwRevision
0x140091d91  mov     rcx, rdi; pSecurityDescriptor
0x140091d94  call    cs:__imp_InitializeSecurityDescriptor
0x140091d9a  test    eax, eax
0x140091d9c  jz      short loc_140091DF9
0x140091d9e  xor     r8d, r8d; bOwnerDefaulted
0x140091da1  mov     rdx, r13; pOwner
0x140091da4  mov     rcx, rdi; pSecurityDescriptor
0x140091da7  call    cs:__imp_SetSecurityDescriptorOwner
0x140091dad  test    eax, eax
0x140091daf  jz      short loc_140091DF9
0x140091db1  xor     r8d, r8d; bGroupDefaulted
0x140091db4  xor     edx, edx; pGroup
0x140091db6  mov     rcx, rdi; pSecurityDescriptor
0x140091db9  call    cs:__imp_SetSecurityDescriptorGroup
0x140091dbf  test    eax, eax
0x140091dc1  jz      short loc_140091DF9
0x140091dc3  xor     edx, edx
0x140091dc5  mov     r8, r15; pDacl
0x140091dc8  test    r15, r15
0x140091dcb  mov     rcx, rdi; pSecurityDescriptor
0x140091dce  setnz   dl; bDaclPresent
0x140091dd1  xor     r9d, r9d; bDaclDefaulted
0x140091dd4  call    cs:__imp_SetSecurityDescriptorDacl
0x140091dda  test    eax, eax
0x140091ddc  jz      short loc_140091DF9
0x140091dde  xor     edx, edx
0x140091de0  mov     r8, r14; pSacl
0x140091de3  test    r14, r14
0x140091de6  mov     rcx, rdi; pSecurityDescriptor
0x140091de9  setnz   dl; bSaclPresent
0x140091dec  xor     r9d, r9d; bSaclDefaulted
0x140091def  call    cs:__imp_SetSecurityDescriptorSacl
0x140091df5  test    eax, eax
0x140091df7  jnz     short loc_140091E4C
0x140091df9  call    cs:__imp_GetLastError
0x140091dff  mov     ebx, eax
0x140091e01  test    ebx, ebx
0x140091e03  jz      short loc_140091E4E
0x140091e05  mov     rcx, rdi; void *
0x140091e08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140091e0d  jmp     short loc_140091E59
0x140091e0f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140091e16  lea     rax, WPP_GLOBAL_Control
0x140091e1d  cmp     rcx, rax
0x140091e20  jz      short loc_140091E05
0x140091e22  test    byte ptr [rcx+44h], 8
0x140091e26  jz      short loc_140091E05
0x140091e28  cmp     [rcx+41h], r12b
0x140091e2c  jb      short loc_140091E05
0x140091e2e  mov     rcx, [rcx+38h]
0x140091e32  lea     r8, WPP_e3511582f2a533ad198c1a3640c6c2ac_Traceguids
0x140091e39  mov     edx, 0Dh
0x140091e3e  mov     dword ptr [rsp+88h+pSid], ebx
0x140091e42  mov     r9d, ebp
0x140091e45  call    WPP_SF_Dd
0x140091e4a  jmp     short loc_140091E05
0x140091e4c  xor     ebx, ebx
0x140091e4e  mov     rax, [rsp+88h+arg_20]
0x140091e56  mov     [rax], rdi
0x140091e59  mov     eax, ebx
0x140091e5b  add     rsp, 48h
0x140091e5f  pop     r15
0x140091e61  pop     r14
0x140091e63  pop     r13
0x140091e65  pop     r12
0x140091e67  pop     rdi
0x140091e68  pop     rsi
0x140091e69  pop     rbp
0x140091e6a  pop     rbx
0x140091e6b  retn
```
