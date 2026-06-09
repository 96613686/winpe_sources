# CVssSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,void *,ulong,ulong)

- ea: `0x18003b9bc`
- end: `0x18003badb`
- name: `?AddAccessAllowedACEToACL@CVssSecurityDescriptor@@CAJPEAPEAU_ACL@@PEAXKK@Z`
- size: `287`
- prototype: `int __fastcall(struct _ACL **, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003c7b8`

## callees

- `0x180001580`
- `0x180001674`
- `0x180001af0`
- `0x18003b9bc`
- `0x18003c808`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba58`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003ba05`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003ba05`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003ba46`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003ba46`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18003ba98`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18003ba98`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003ba0e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003ba0e`

## pseudocode

```c
int __fastcall CVssSecurityDescriptor::AddAccessAllowedACEToACL(struct _ACL **a1, void *a2)
{
  struct _ACL *v2; // rdi
  DWORD LengthSid; // eax
  signed int v6; // esi
  struct _ACL *v7; // rax
  struct _ACL *v8; // rbx
  int result; // eax
  BOOL v10; // eax
  struct _ACL *v11; // rcx
  int v12; // esi
  __int64 v13; // [rsp+30h] [rbp-38h] BYREF
  int v14; // [rsp+38h] [rbp-30h]

  v2 = *a1;
  v13 = 0;
  v14 = 0;
  if ( v2 )
    GetAclInformation(v2, &v13, 0xCu, AclSizeInformation);
  LengthSid = GetLengthSid(a2);
  v6 = LengthSid + HIDWORD(v13) + 16;
  v7 = (struct _ACL *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
    return -2147024882;
  v10 = InitializeAcl(v7, v6, 2u);
  v11 = v8;
  if ( !v10 )
    goto LABEL_6;
  v12 = CVssSecurityDescriptor::CopyACL(v8, v2);
  if ( v12 < 0 )
  {
    operator delete(v8);
    return v12;
  }
  if ( !AddAccessAllowedAceEx(v8, 2u, 0, 1u, a2) )
  {
    v11 = v8;
LABEL_6:
    operator delete(v11);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  *a1 = v8;
  if ( v2 )
    operator delete(v2);
  return 0;
}

```

## disassembly

```asm
0x18003b9bc  mov     r11, rsp
0x18003b9bf  mov     [r11+18h], rbx
0x18003b9c3  mov     [r11+20h], rbp
0x18003b9c7  push    rsi
0x18003b9c8  push    rdi
0x18003b9c9  push    r14
0x18003b9cb  sub     rsp, 50h
0x18003b9cf  mov     rax, cs:__security_cookie
0x18003b9d6  xor     rax, rsp
0x18003b9d9  mov     [rsp+68h+var_28], rax
0x18003b9de  mov     rdi, [rcx]
0x18003b9e1  xor     eax, eax
0x18003b9e3  mov     [r11-38h], rax
0x18003b9e7  mov     rbp, rdx
0x18003b9ea  mov     [rsp+68h+var_30], eax
0x18003b9ee  mov     r14, rcx
0x18003b9f1  test    rdi, rdi
0x18003b9f4  jz      short loc_18003BA0B
0x18003b9f6  lea     r9d, [rax+2]; dwAclInformationClass
0x18003b9fa  mov     rcx, rdi; pAcl
0x18003b9fd  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18003ba01  lea     rdx, [r11-38h]; pAclInformation
0x18003ba05  call    cs:__imp_GetAclInformation
0x18003ba0b  mov     rcx, rbp; pSid
0x18003ba0e  call    cs:__imp_GetLengthSid
0x18003ba14  mov     esi, [rsp+68h+var_34]
0x18003ba18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ba1f  add     esi, 10h
0x18003ba22  add     esi, eax
0x18003ba24  movsxd  rcx, esi; unsigned __int64
0x18003ba27  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003ba2c  mov     rbx, rax
0x18003ba2f  test    rax, rax
0x18003ba32  jnz     short loc_18003BA3B
0x18003ba34  mov     eax, 8007000Eh
0x18003ba39  jmp     short loc_18003BAB9
0x18003ba3b  mov     r8d, 2; dwAclRevision
0x18003ba41  mov     edx, esi; nAclLength
0x18003ba43  mov     rcx, rbx; pAcl
0x18003ba46  call    cs:__imp_InitializeAcl
0x18003ba4c  mov     rcx, rbx; pAcl
0x18003ba4f  test    eax, eax
0x18003ba51  jnz     short loc_18003BA6C
0x18003ba53  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ba58  call    cs:__imp_GetLastError
0x18003ba5e  test    eax, eax
0x18003ba60  jle     short loc_18003BAB9
0x18003ba62  movzx   eax, ax
0x18003ba65  or      eax, 80070000h
0x18003ba6a  jmp     short loc_18003BAB9
0x18003ba6c  mov     rdx, rdi; PACL
0x18003ba6f  call    ?CopyACL@CVssSecurityDescriptor@@CAJPEAU_ACL@@0@Z; CVssSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x18003ba74  mov     esi, eax
0x18003ba76  mov     rcx, rbx; pAcl
0x18003ba79  test    eax, eax
0x18003ba7b  jns     short loc_18003BA86
0x18003ba7d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ba82  mov     eax, esi
0x18003ba84  jmp     short loc_18003BAB9
0x18003ba86  mov     r9d, 1; AccessMask
0x18003ba8c  mov     [rsp+68h+pSid], rbp; pSid
0x18003ba91  xor     r8d, r8d; AceFlags
0x18003ba94  lea     edx, [r9+1]; dwAceRevision
0x18003ba98  call    cs:__imp_AddAccessAllowedAceEx
0x18003ba9e  test    eax, eax
0x18003baa0  jnz     short loc_18003BAA7
0x18003baa2  mov     rcx, rbx
0x18003baa5  jmp     short loc_18003BA53
0x18003baa7  mov     [r14], rbx
0x18003baaa  test    rdi, rdi
0x18003baad  jz      short loc_18003BAB7
0x18003baaf  mov     rcx, rdi; Block
0x18003bab2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bab7  xor     eax, eax
0x18003bab9  mov     rcx, [rsp+68h+var_28]
0x18003babe  xor     rcx, rsp; StackCookie
0x18003bac1  call    __security_check_cookie
0x18003bac6  lea     r11, [rsp+68h+var_18]
0x18003bacb  mov     rbx, [r11+30h]
0x18003bacf  mov     rbp, [r11+38h]
0x18003bad3  mov     rsp, r11
0x18003bad6  pop     r14
0x18003bad8  pop     rdi
0x18003bad9  pop     rsi
0x18003bada  retn
```
