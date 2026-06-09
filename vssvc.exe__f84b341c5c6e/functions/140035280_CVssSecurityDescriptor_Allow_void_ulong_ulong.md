# CVssSecurityDescriptor::Allow(void *,ulong,ulong)

- ea: `0x140035280`
- end: `0x140035495`
- name: `?Allow@CVssSecurityDescriptor@@QEAAJPEAXKK@Z`
- size: `533`
- prototype: `int(CVssSecurityDescriptor *__hidden this, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400b3648`

## callees

- `0x140035280`
- `0x140091560`
- `0x140091584`
- `0x1400919a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035476`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14003530d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14003530d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140035385`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140035385`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14003541b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14003541b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400353b5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400353b5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400352d8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400352d8`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1400353f1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1400353f1`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1400352cf`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140035344`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1400352cf`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140035344`

## pseudocode

```c
__int64 __fastcall CVssSecurityDescriptor::Allow(CVssSecurityDescriptor *this, void *a2)
{
  struct _ACL *v2; // rdi
  DWORD LengthSid; // eax
  signed int v6; // ebx
  struct _ACL *v7; // rax
  struct _ACL *v8; // rsi
  signed int LastError; // eax
  signed int v10; // ebx
  DWORD i; // ebx
  signed int v13; // eax
  LPVOID pAce; // [rsp+30h] [rbp-48h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-40h] BYREF
  int v16; // [rsp+40h] [rbp-38h]
  __int64 v17; // [rsp+48h] [rbp-30h] BYREF
  int v18; // [rsp+50h] [rbp-28h]

  v2 = (struct _ACL *)*((_QWORD *)this + 3);
  pAclInformation = 0;
  v16 = 0;
  if ( v2 )
    GetAclInformation(v2, &pAclInformation, 0xCu, AclSizeInformation);
  LengthSid = GetLengthSid(a2);
  v6 = LengthSid + HIDWORD(pAclInformation) + 16;
  v7 = (struct _ACL *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    if ( InitializeAcl(v7, v6, 2u) )
    {
      v17 = 0;
      v18 = 0;
      pAce = 0;
      if ( v2 )
      {
        if ( GetAclInformation(v2, &v17, 0xCu, AclSizeInformation) )
        {
          for ( i = 0; i < (unsigned int)v17; ++i )
          {
            if ( !GetAce(v2, i, &pAce) )
              goto LABEL_7;
            if ( !AddAce(v8, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
            {
              LastError = GetLastError();
              v10 = LastError;
              if ( LastError <= 0 )
                goto LABEL_9;
              goto LABEL_8;
            }
          }
        }
        else
        {
LABEL_7:
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
LABEL_8:
            v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_9:
          if ( v10 < 0 )
          {
            operator delete(v8);
            return (unsigned int)v10;
          }
        }
      }
      if ( AddAccessAllowedAceEx(v8, 2u, 0, 1u, a2) )
      {
        *((_QWORD *)this + 3) = v8;
        if ( v2 )
          operator delete(v2);
        v10 = 0;
LABEL_14:
        SetSecurityDescriptorDacl(*(PSECURITY_DESCRIPTOR *)this, 1, *((PACL *)this + 3), 0);
        return (unsigned int)v10;
      }
      operator delete(v8);
      v13 = GetLastError();
      v10 = v13;
      if ( v13 > 0 )
        goto LABEL_22;
    }
    else
    {
      operator delete(v8);
      v13 = GetLastError();
      v10 = v13;
      if ( v13 > 0 )
LABEL_22:
        v10 = (unsigned __int16)v13 | 0x80070000;
    }
    if ( v10 < 0 )
      return (unsigned int)v10;
    goto LABEL_14;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x140035280  mov     [rsp+arg_10], rbx
0x140035285  mov     [rsp+arg_18], rbp
0x14003528a  push    rsi
0x14003528b  push    rdi
0x14003528c  push    r14
0x14003528e  sub     rsp, 60h
0x140035292  mov     rax, cs:__security_cookie
0x140035299  xor     rax, rsp
0x14003529c  mov     [rsp+78h+var_20], rax
0x1400352a1  mov     rdi, [rcx+18h]
0x1400352a5  xor     eax, eax
0x1400352a7  mov     [rsp+78h+pAclInformation], rax
0x1400352ac  mov     rbp, rdx
0x1400352af  mov     [rsp+78h+var_38], eax
0x1400352b3  mov     r14, rcx
0x1400352b6  test    rdi, rdi
0x1400352b9  jz      short loc_1400352D5
0x1400352bb  mov     r9d, 2; dwAclInformationClass
0x1400352c1  lea     rdx, [rsp+78h+pAclInformation]; pAclInformation
0x1400352c6  mov     r8d, 0Ch; nAclInformationLength
0x1400352cc  mov     rcx, rdi; pAcl
0x1400352cf  call    cs:__imp_GetAclInformation
0x1400352d5  mov     rcx, rbp; pSid
0x1400352d8  call    cs:__imp_GetLengthSid
0x1400352de  mov     ebx, dword ptr [rsp+78h+pAclInformation+4]
0x1400352e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400352e9  add     ebx, 10h
0x1400352ec  add     ebx, eax
0x1400352ee  movsxd  rcx, ebx; unsigned __int64
0x1400352f1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400352f6  mov     rsi, rax
0x1400352f9  test    rax, rax
0x1400352fc  jz      loc_14003548B
0x140035302  mov     r8d, 2; dwAclRevision
0x140035308  mov     edx, ebx; nAclLength
0x14003530a  mov     rcx, rax; pAcl
0x14003530d  call    cs:__imp_InitializeAcl
0x140035313  test    eax, eax
0x140035315  jz      loc_140035460
0x14003531b  xor     eax, eax
0x14003531d  mov     [rsp+78h+var_30], rax
0x140035322  mov     [rsp+78h+var_28], eax
0x140035326  mov     [rsp+78h+pAce], rax
0x14003532b  test    rdi, rdi
0x14003532e  jz      short loc_14003536F
0x140035330  mov     r9d, 2; dwAclInformationClass
0x140035336  lea     rdx, [rsp+78h+var_30]; pAclInformation
0x14003533b  mov     r8d, 0Ch; nAclInformationLength
0x140035341  mov     rcx, rdi; pAcl
0x140035344  call    cs:__imp_GetAclInformation
0x14003534a  test    eax, eax
0x14003534c  jnz     loc_1400353DF
0x140035352  call    cs:__imp_GetLastError
0x140035358  mov     ebx, eax
0x14003535a  test    eax, eax
0x14003535c  jle     short loc_140035367
0x14003535e  movzx   ebx, ax
0x140035361  or      ebx, 80070000h
0x140035367  test    ebx, ebx
0x140035369  js      loc_140035453
0x14003536f  mov     r9d, 1; AccessMask
0x140035375  mov     [rsp+78h+pSid], rbp; pSid
0x14003537a  xor     r8d, r8d; AceFlags
0x14003537d  mov     edx, 2; dwAceRevision
0x140035382  mov     rcx, rsi; pAcl
0x140035385  call    cs:__imp_AddAccessAllowedAceEx
0x14003538b  test    eax, eax
0x14003538d  jz      loc_140035429
0x140035393  mov     [r14+18h], rsi
0x140035397  test    rdi, rdi
0x14003539a  jz      short loc_1400353A4
0x14003539c  mov     rcx, rdi; Block
0x14003539f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400353a4  xor     ebx, ebx
0x1400353a6  mov     r8, [r14+18h]; pDacl
0x1400353aa  xor     r9d, r9d; bDaclDefaulted
0x1400353ad  mov     rcx, [r14]; pSecurityDescriptor
0x1400353b0  mov     edx, 1; bDaclPresent
0x1400353b5  call    cs:__imp_SetSecurityDescriptorDacl
0x1400353bb  mov     eax, ebx
0x1400353bd  mov     rcx, [rsp+78h+var_20]
0x1400353c2  xor     rcx, rsp; StackCookie
0x1400353c5  call    __security_check_cookie
0x1400353ca  lea     r11, [rsp+78h+var_18]
0x1400353cf  mov     rbx, [r11+30h]
0x1400353d3  mov     rbp, [r11+38h]
0x1400353d7  mov     rsp, r11
0x1400353da  pop     r14
0x1400353dc  pop     rdi
0x1400353dd  pop     rsi
0x1400353de  retn
0x1400353df  xor     ebx, ebx
0x1400353e1  cmp     ebx, dword ptr [rsp+78h+var_30]
0x1400353e5  jnb     short loc_14003536F
0x1400353e7  lea     r8, [rsp+78h+pAce]; pAce
0x1400353ec  mov     edx, ebx; dwAceIndex
0x1400353ee  mov     rcx, rdi; pAcl
0x1400353f1  call    cs:__imp_GetAce
0x1400353f7  test    eax, eax
0x1400353f9  jz      loc_140035352
0x1400353ff  mov     r9, [rsp+78h+pAce]; pAceList
0x140035404  mov     edx, 2; dwAceRevision
0x140035409  mov     r8d, 0FFFFFFFFh; dwStartingAceIndex
0x14003540f  mov     rcx, rsi; pAcl
0x140035412  movzx   eax, word ptr [r9+2]
0x140035417  mov     dword ptr [rsp+78h+pSid], eax; nAceListLength
0x14003541b  call    cs:__imp_AddAce
0x140035421  test    eax, eax
0x140035423  jz      short loc_140035476
0x140035425  inc     ebx
0x140035427  jmp     short loc_1400353E1
0x140035429  mov     rcx, rsi; Block
0x14003542c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140035431  call    cs:__imp_GetLastError
0x140035437  mov     ebx, eax
0x140035439  test    eax, eax
0x14003543b  jle     short loc_140035446
0x14003543d  movzx   ebx, ax
0x140035440  or      ebx, 80070000h
0x140035446  test    ebx, ebx
0x140035448  jns     loc_1400353A6
0x14003544e  jmp     loc_1400353BB
0x140035453  mov     rcx, rsi; Block
0x140035456  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003545b  jmp     loc_1400353BB
0x140035460  mov     rcx, rsi; Block
0x140035463  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140035468  call    cs:__imp_GetLastError
0x14003546e  mov     ebx, eax
0x140035470  test    eax, eax
0x140035472  jle     short loc_140035446
0x140035474  jmp     short loc_14003543D
0x140035476  call    cs:__imp_GetLastError
0x14003547c  mov     ebx, eax
0x14003547e  test    eax, eax
0x140035480  jle     loc_140035367
0x140035486  jmp     loc_14003535E
0x14003548b  mov     eax, 8007000Eh
0x140035490  jmp     loc_1400353BD
```
