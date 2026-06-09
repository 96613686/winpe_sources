# CShellProtectedRegLock::Lock(void)

- ea: `0x1802bf890`
- end: `0x1802bfacc`
- name: `?Lock@CShellProtectedRegLock@@QEAAXXZ`
- size: `572`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802bf7cc`
- `0x1805fec40`

## callees

- `0x1802bf890`
- `0x1803b1f60`
- `0x1803b69c5`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802bf97e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802bf97e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802bfa9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802bfa9a`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!SetSecurityInfo` at `0x1802bfa8b`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!SetSecurityInfo` at `0x1802bfa8b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1802bf99e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1802bf99e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1802bf9e3`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1802bfa39`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1802bf9e3`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1802bfa39`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1802bf901`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1802bf92f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1802bf901`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1802bf92f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1802bfa13`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1802bfa13`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1802bf8d2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1802bf8d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1802bf94b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1802bf94b`

## pseudocode

```c
void __fastcall CShellProtectedRegLock::Lock(CShellProtectedRegLock *this)
{
  struct _ACL *v2; // rcx
  struct _ACL *v3; // rcx
  int v4; // ebx
  DWORD v5; // r15d
  DWORD LengthSid; // r13d
  DWORD nAceListLength; // r14d
  __int64 v8; // rbx
  struct _ACL *v9; // rax
  struct _ACL *pDacl; // rsi
  _WORD *v11; // rbx
  int v12; // r14d
  DWORD v13; // ebx
  struct _ACL *v14; // rcx
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  DWORD dwAclRevision; // [rsp+48h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+58h] [rbp-18h]

  if ( *((_QWORD *)this + 2) )
  {
    if ( !EqualSid(qword_180736BD0, **(PSID **)this) )
    {
      v2 = (struct _ACL *)*((_QWORD *)this + 2);
      pAclInformation = 0;
      v18 = 0;
      if ( GetAclInformation(v2, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v3 = (struct _ACL *)*((_QWORD *)this + 2);
        v4 = HIDWORD(pAclInformation);
        dwAclRevision = 0;
        v5 = 2;
        if ( GetAclInformation(v3, &dwAclRevision, 4u, AclRevisionInformation) )
          v5 = dwAclRevision;
        LengthSid = GetLengthSid(**(PSID **)this);
        nAceListLength = LengthSid + 8;
        if ( LengthSid + 8 <= 0xFFFF )
        {
          v8 = nAceListLength + v4;
          if ( (unsigned int)v8 <= 0xFFFF )
          {
            v9 = (struct _ACL *)LocalAlloc(0x40u, (unsigned int)v8 + nAceListLength);
            pDacl = v9;
            if ( v9 )
            {
              InitializeAcl(v9, v8, v5);
              v11 = (_WORD *)((char *)pDacl + v8);
              *(_BYTE *)v11 = 1;
              v11[1] = LengthSid + 8;
              *((_DWORD *)v11 + 1) = 2;
              memcpy_0(v11 + 4, **(const void ***)this, LengthSid);
              if ( AddAce(pDacl, v5, 0xFFFFFFFF, v11, nAceListLength) )
              {
                v12 = 0;
                v13 = 0;
                if ( !(_DWORD)pAclInformation )
                  goto LABEL_16;
                do
                {
                  v14 = (struct _ACL *)*((_QWORD *)this + 2);
                  pAce = 0;
                  if ( GetAce(v14, v13, &pAce) )
                  {
                    if ( !AddAce(pDacl, v5, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
                      v12 = 1;
                  }
                  ++v13;
                }
                while ( v13 < (unsigned int)pAclInformation );
                if ( !v12 )
LABEL_16:
                  SetSecurityInfo(*((HANDLE *)this + 1), SE_REGISTRY_KEY, 0x20000004u, 0, 0, pDacl, 0);
              }
              LocalFree(pDacl);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1802bf890  mov     [rsp-28h+arg_8], rbx
0x1802bf895  mov     [rsp-28h+arg_10], rsi
0x1802bf89a  push    rbp
0x1802bf89b  push    rdi
0x1802bf89c  push    r13
0x1802bf89e  push    r14
0x1802bf8a0  push    r15
0x1802bf8a2  mov     rbp, rsp
0x1802bf8a5  sub     rsp, 70h
0x1802bf8a9  mov     rax, cs:__security_cookie
0x1802bf8b0  xor     rax, rsp
0x1802bf8b3  mov     [rbp+var_10], rax
0x1802bf8b7  cmp     qword ptr [rcx+10h], 0
0x1802bf8bc  mov     rdi, rcx
0x1802bf8bf  jz      loc_1802BFAA6
0x1802bf8c5  mov     rdx, [rcx]
0x1802bf8c8  lea     rcx, qword_180736BD0; pSid1
0x1802bf8cf  mov     rdx, [rdx]; pSid2
0x1802bf8d2  call    cs:__imp_EqualSid
0x1802bf8d9  nop     dword ptr [rax+rax+00h]
0x1802bf8de  test    eax, eax
0x1802bf8e0  jnz     loc_1802BFAA6
0x1802bf8e6  mov     rcx, [rdi+10h]; pAcl
0x1802bf8ea  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x1802bf8ee  xor     eax, eax
0x1802bf8f0  mov     [rbp+pAclInformation], rax
0x1802bf8f4  mov     [rbp+var_18], eax
0x1802bf8f7  lea     esi, [rax+2]
0x1802bf8fa  mov     r9d, esi; dwAclInformationClass
0x1802bf8fd  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1802bf901  call    cs:__imp_GetAclInformation
0x1802bf908  nop     dword ptr [rax+rax+00h]
0x1802bf90d  test    eax, eax
0x1802bf90f  jz      loc_1802BFAA6
0x1802bf915  mov     rcx, [rdi+10h]; pAcl
0x1802bf919  lea     r9d, [rsi-1]; dwAclInformationClass
0x1802bf91d  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x1802bf920  lea     r8d, [rsi+2]; nAclInformationLength
0x1802bf924  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x1802bf928  mov     [rbp+dwAclRevision], 0
0x1802bf92f  call    cs:__imp_GetAclInformation
0x1802bf936  nop     dword ptr [rax+rax+00h]
0x1802bf93b  mov     rcx, [rdi]
0x1802bf93e  mov     r15d, esi
0x1802bf941  test    eax, eax
0x1802bf943  cmovnz  r15d, [rbp+dwAclRevision]
0x1802bf948  mov     rcx, [rcx]; pSid
0x1802bf94b  call    cs:__imp_GetLengthSid
0x1802bf952  nop     dword ptr [rax+rax+00h]
0x1802bf957  mov     r13d, eax
0x1802bf95a  mov     eax, 0FFFFh
0x1802bf95f  lea     r14d, [r13+8]
0x1802bf963  cmp     r14d, eax
0x1802bf966  ja      loc_1802BFAA6
0x1802bf96c  add     ebx, r14d
0x1802bf96f  cmp     ebx, eax
0x1802bf971  ja      loc_1802BFAA6
0x1802bf977  lea     edx, [rbx+r14]; uBytes
0x1802bf97b  lea     ecx, [rsi+3Eh]; uFlags
0x1802bf97e  call    cs:__imp_LocalAlloc
0x1802bf985  nop     dword ptr [rax+rax+00h]
0x1802bf98a  mov     rsi, rax
0x1802bf98d  test    rax, rax
0x1802bf990  jz      loc_1802BFAA6
0x1802bf996  mov     r8d, r15d; dwAclRevision
0x1802bf999  mov     edx, ebx; nAclLength
0x1802bf99b  mov     rcx, rax; pAcl
0x1802bf99e  call    cs:__imp_InitializeAcl
0x1802bf9a5  nop     dword ptr [rax+rax+00h]
0x1802bf9aa  add     rbx, rsi
0x1802bf9ad  mov     r8d, r13d; Size
0x1802bf9b0  mov     byte ptr [rbx], 1
0x1802bf9b3  lea     rcx, [rbx+8]; void *
0x1802bf9b7  mov     [rbx+2], r14w
0x1802bf9bc  mov     dword ptr [rbx+4], 2
0x1802bf9c3  mov     rdx, [rdi]
0x1802bf9c6  mov     rdx, [rdx]; Src
0x1802bf9c9  call    memcpy_0
0x1802bf9ce  or      r13d, 0FFFFFFFFh
0x1802bf9d2  mov     [rsp+70h+nAceListLength], r14d; nAceListLength
0x1802bf9d7  mov     r8d, r13d; dwStartingAceIndex
0x1802bf9da  mov     r9, rbx; pAceList
0x1802bf9dd  mov     edx, r15d; dwAceRevision
0x1802bf9e0  mov     rcx, rsi; pAcl
0x1802bf9e3  call    cs:__imp_AddAce
0x1802bf9ea  nop     dword ptr [rax+rax+00h]
0x1802bf9ef  test    eax, eax
0x1802bf9f1  jz      loc_1802BFA97
0x1802bf9f7  xor     r14d, r14d
0x1802bf9fa  xor     ebx, ebx
0x1802bf9fc  cmp     dword ptr [rbp+pAclInformation], ebx
0x1802bf9ff  jbe     short loc_1802BFA63
0x1802bfa01  mov     rcx, [rdi+10h]; pAcl
0x1802bfa05  lea     r8, [rbp+pAce]; pAce
0x1802bfa09  mov     edx, ebx; dwAceIndex
0x1802bfa0b  mov     [rbp+pAce], 0
0x1802bfa13  call    cs:__imp_GetAce
0x1802bfa1a  nop     dword ptr [rax+rax+00h]
0x1802bfa1f  test    eax, eax
0x1802bfa21  jz      short loc_1802BFA52
0x1802bfa23  mov     r9, [rbp+pAce]; pAceList
0x1802bfa27  mov     r8d, r13d; dwStartingAceIndex
0x1802bfa2a  mov     edx, r15d; dwAceRevision
0x1802bfa2d  mov     rcx, rsi; pAcl
0x1802bfa30  movzx   eax, word ptr [r9+2]
0x1802bfa35  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x1802bfa39  call    cs:__imp_AddAce
0x1802bfa40  nop     dword ptr [rax+rax+00h]
0x1802bfa45  test    eax, eax
0x1802bfa47  mov     eax, 1
0x1802bfa4c  cmovz   r14d, eax
0x1802bfa50  jmp     short loc_1802BFA57
0x1802bfa52  mov     eax, 1
0x1802bfa57  add     ebx, eax
0x1802bfa59  cmp     ebx, dword ptr [rbp+pAclInformation]
0x1802bfa5c  jb      short loc_1802BFA01
0x1802bfa5e  test    r14d, r14d
0x1802bfa61  jnz     short loc_1802BFA97
0x1802bfa63  mov     rcx, [rdi+8]; handle
0x1802bfa67  xor     r9d, r9d; psidOwner
0x1802bfa6a  mov     [rsp+70h+pSacl], 0; pSacl
0x1802bfa73  mov     r8d, 20000004h; SecurityInfo
0x1802bfa79  mov     [rsp+70h+pDacl], rsi; pDacl
0x1802bfa7e  mov     qword ptr [rsp+70h+nAceListLength], 0; psidGroup
0x1802bfa87  lea     edx, [r9+4]; ObjectType
0x1802bfa8b  call    cs:__imp_SetSecurityInfo
0x1802bfa92  nop     dword ptr [rax+rax+00h]
0x1802bfa97  mov     rcx, rsi; hMem
0x1802bfa9a  call    cs:__imp_LocalFree
0x1802bfaa1  nop     dword ptr [rax+rax+00h]
0x1802bfaa6  mov     rcx, [rbp+var_10]
0x1802bfaaa  xor     rcx, rsp; StackCookie
0x1802bfaad  call    __security_check_cookie
0x1802bfab2  lea     r11, [rsp+70h+var_s0]
0x1802bfab7  mov     rbx, [r11+38h]
0x1802bfabb  mov     rsi, [r11+40h]
0x1802bfabf  mov     rsp, r11
0x1802bfac2  pop     r15
0x1802bfac4  pop     r14
0x1802bfac6  pop     r13
0x1802bfac8  pop     rdi
0x1802bfac9  pop     rbp
0x1802bfaca  retn
```
