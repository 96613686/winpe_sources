# CVssSecurityDescriptor::AddAccessDeniedACEToACL(_ACL * *,void *,ulong,ulong)

- ea: `0x18003bae4`
- end: `0x18003bc01`
- name: `?AddAccessDeniedACEToACL@CVssSecurityDescriptor@@CAJPEAPEAU_ACL@@PEAXKK@Z`
- size: `285`
- prototype: `int __fastcall(struct _ACL **, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003cb0c`

## callees

- `0x180001580`
- `0x180001674`
- `0x180001af0`
- `0x18003bae4`
- `0x18003c808`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb80`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003bb2d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003bb2d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003bb6e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003bb6e`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x18003bba6`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x18003bba6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003bb36`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003bb36`

## pseudocode

```c
int __fastcall CVssSecurityDescriptor::AddAccessDeniedACEToACL(struct _ACL **a1, void *a2)
{
  struct _ACL *v2; // rdi
  DWORD LengthSid; // eax
  signed int v6; // esi
  struct _ACL *v7; // rax
  struct _ACL *v8; // rbx
  int result; // eax
  BOOL v10; // eax
  struct _ACL *v11; // rcx
  BOOL v12; // eax
  int v13; // esi
  __int64 v14; // [rsp+30h] [rbp-38h] BYREF
  int v15; // [rsp+38h] [rbp-30h]

  v2 = *a1;
  v14 = 0;
  v15 = 0;
  if ( v2 )
    GetAclInformation(v2, &v14, 0xCu, AclSizeInformation);
  LengthSid = GetLengthSid(a2);
  v6 = LengthSid + HIDWORD(v14) + 16;
  v7 = (struct _ACL *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
    return -2147024882;
  v10 = InitializeAcl(v7, v6, 2u);
  v11 = v8;
  if ( v10 && (v12 = AddAccessDeniedAceEx(v8, 2u, 0, 1u, a2), v11 = v8, v12) )
  {
    v13 = CVssSecurityDescriptor::CopyACL(v8, v2);
    if ( v13 >= 0 )
    {
      *a1 = v8;
      if ( v2 )
        operator delete(v2);
      return 0;
    }
    else
    {
      operator delete(v8);
      return v13;
    }
  }
  else
  {
    operator delete(v11);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18003bae4  mov     r11, rsp
0x18003bae7  mov     [r11+18h], rbx
0x18003baeb  mov     [r11+20h], rbp
0x18003baef  push    rsi
0x18003baf0  push    rdi
0x18003baf1  push    r14
0x18003baf3  sub     rsp, 50h
0x18003baf7  mov     rax, cs:__security_cookie
0x18003bafe  xor     rax, rsp
0x18003bb01  mov     [rsp+68h+var_28], rax
0x18003bb06  mov     rdi, [rcx]
0x18003bb09  xor     eax, eax
0x18003bb0b  mov     [r11-38h], rax
0x18003bb0f  mov     rbp, rdx
0x18003bb12  mov     [rsp+68h+var_30], eax
0x18003bb16  mov     r14, rcx
0x18003bb19  test    rdi, rdi
0x18003bb1c  jz      short loc_18003BB33
0x18003bb1e  lea     r9d, [rax+2]; dwAclInformationClass
0x18003bb22  mov     rcx, rdi; pAcl
0x18003bb25  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18003bb29  lea     rdx, [r11-38h]; pAclInformation
0x18003bb2d  call    cs:__imp_GetAclInformation
0x18003bb33  mov     rcx, rbp; pSid
0x18003bb36  call    cs:__imp_GetLengthSid
0x18003bb3c  mov     esi, [rsp+68h+var_34]
0x18003bb40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003bb47  add     esi, 10h
0x18003bb4a  add     esi, eax
0x18003bb4c  movsxd  rcx, esi; unsigned __int64
0x18003bb4f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003bb54  mov     rbx, rax
0x18003bb57  test    rax, rax
0x18003bb5a  jnz     short loc_18003BB63
0x18003bb5c  mov     eax, 8007000Eh
0x18003bb61  jmp     short loc_18003BBDF
0x18003bb63  mov     r8d, 2; dwAclRevision
0x18003bb69  mov     edx, esi; nAclLength
0x18003bb6b  mov     rcx, rbx; pAcl
0x18003bb6e  call    cs:__imp_InitializeAcl
0x18003bb74  mov     rcx, rbx; pAcl
0x18003bb77  test    eax, eax
0x18003bb79  jnz     short loc_18003BB94
0x18003bb7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bb80  call    cs:__imp_GetLastError
0x18003bb86  test    eax, eax
0x18003bb88  jle     short loc_18003BBDF
0x18003bb8a  movzx   eax, ax
0x18003bb8d  or      eax, 80070000h
0x18003bb92  jmp     short loc_18003BBDF
0x18003bb94  mov     r9d, 1; AccessMask
0x18003bb9a  mov     [rsp+68h+pSid], rbp; pSid
0x18003bb9f  xor     r8d, r8d; AceFlags
0x18003bba2  lea     edx, [r9+1]; dwAceRevision
0x18003bba6  call    cs:__imp_AddAccessDeniedAceEx
0x18003bbac  mov     rcx, rbx; pAcl
0x18003bbaf  test    eax, eax
0x18003bbb1  jz      short loc_18003BB7B
0x18003bbb3  mov     rdx, rdi; PACL
0x18003bbb6  call    ?CopyACL@CVssSecurityDescriptor@@CAJPEAU_ACL@@0@Z; CVssSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x18003bbbb  mov     esi, eax
0x18003bbbd  test    eax, eax
0x18003bbbf  jns     short loc_18003BBCD
0x18003bbc1  mov     rcx, rbx; Block
0x18003bbc4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bbc9  mov     eax, esi
0x18003bbcb  jmp     short loc_18003BBDF
0x18003bbcd  mov     [r14], rbx
0x18003bbd0  test    rdi, rdi
0x18003bbd3  jz      short loc_18003BBDD
0x18003bbd5  mov     rcx, rdi; Block
0x18003bbd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bbdd  xor     eax, eax
0x18003bbdf  mov     rcx, [rsp+68h+var_28]
0x18003bbe4  xor     rcx, rsp; StackCookie
0x18003bbe7  call    __security_check_cookie
0x18003bbec  lea     r11, [rsp+68h+var_18]
0x18003bbf1  mov     rbx, [r11+30h]
0x18003bbf5  mov     rbp, [r11+38h]
0x18003bbf9  mov     rsp, r11
0x18003bbfc  pop     r14
0x18003bbfe  pop     rdi
0x18003bbff  pop     rsi
0x18003bc00  retn
```
