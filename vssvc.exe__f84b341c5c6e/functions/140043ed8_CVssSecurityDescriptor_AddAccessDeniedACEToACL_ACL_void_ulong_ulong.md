# CVssSecurityDescriptor::AddAccessDeniedACEToACL(_ACL * *,void *,ulong,ulong)

- ea: `0x140043ed8`
- end: `0x140043ff5`
- name: `?AddAccessDeniedACEToACL@CVssSecurityDescriptor@@CAJPEAPEAU_ACL@@PEAXKK@Z`
- size: `285`
- prototype: `int __fastcall(struct _ACL **, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14005a9a8`

## callees

- `0x1400355e0`
- `0x140043ed8`
- `0x140091560`
- `0x140091584`
- `0x1400919a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043f74`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140043f62`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140043f62`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x140043f9a`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x140043f9a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140043f2a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140043f2a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140043f21`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140043f21`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x140043ed8  mov     r11, rsp
0x140043edb  mov     [r11+18h], rbx
0x140043edf  mov     [r11+20h], rbp
0x140043ee3  push    rsi
0x140043ee4  push    rdi
0x140043ee5  push    r14
0x140043ee7  sub     rsp, 50h
0x140043eeb  mov     rax, cs:__security_cookie
0x140043ef2  xor     rax, rsp
0x140043ef5  mov     [rsp+68h+var_28], rax
0x140043efa  mov     rdi, [rcx]
0x140043efd  xor     eax, eax
0x140043eff  mov     [r11-38h], rax
0x140043f03  mov     rbp, rdx
0x140043f06  mov     [rsp+68h+var_30], eax
0x140043f0a  mov     r14, rcx
0x140043f0d  test    rdi, rdi
0x140043f10  jz      short loc_140043F27
0x140043f12  lea     r9d, [rax+2]; dwAclInformationClass
0x140043f16  mov     rcx, rdi; pAcl
0x140043f19  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140043f1d  lea     rdx, [r11-38h]; pAclInformation
0x140043f21  call    cs:__imp_GetAclInformation
0x140043f27  mov     rcx, rbp; pSid
0x140043f2a  call    cs:__imp_GetLengthSid
0x140043f30  mov     esi, [rsp+68h+var_34]
0x140043f34  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140043f3b  add     esi, 10h
0x140043f3e  add     esi, eax
0x140043f40  movsxd  rcx, esi; unsigned __int64
0x140043f43  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140043f48  mov     rbx, rax
0x140043f4b  test    rax, rax
0x140043f4e  jnz     short loc_140043F57
0x140043f50  mov     eax, 8007000Eh
0x140043f55  jmp     short loc_140043FD3
0x140043f57  mov     r8d, 2; dwAclRevision
0x140043f5d  mov     edx, esi; nAclLength
0x140043f5f  mov     rcx, rbx; pAcl
0x140043f62  call    cs:__imp_InitializeAcl
0x140043f68  mov     rcx, rbx; Block
0x140043f6b  test    eax, eax
0x140043f6d  jnz     short loc_140043F88
0x140043f6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043f74  call    cs:__imp_GetLastError
0x140043f7a  test    eax, eax
0x140043f7c  jle     short loc_140043FD3
0x140043f7e  movzx   eax, ax
0x140043f81  or      eax, 80070000h
0x140043f86  jmp     short loc_140043FD3
0x140043f88  mov     r9d, 1; AccessMask
0x140043f8e  mov     [rsp+68h+pSid], rbp; pSid
0x140043f93  xor     r8d, r8d; AceFlags
0x140043f96  lea     edx, [r9+1]; dwAceRevision
0x140043f9a  call    cs:__imp_AddAccessDeniedAceEx
0x140043fa0  mov     rcx, rbx; pAcl
0x140043fa3  test    eax, eax
0x140043fa5  jz      short loc_140043F6F
0x140043fa7  mov     rdx, rdi; PACL
0x140043faa  call    ?CopyACL@CVssSecurityDescriptor@@CAJPEAU_ACL@@0@Z; CVssSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x140043faf  mov     esi, eax
0x140043fb1  test    eax, eax
0x140043fb3  jns     short loc_140043FC1
0x140043fb5  mov     rcx, rbx; Block
0x140043fb8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043fbd  mov     eax, esi
0x140043fbf  jmp     short loc_140043FD3
0x140043fc1  mov     [r14], rbx
0x140043fc4  test    rdi, rdi
0x140043fc7  jz      short loc_140043FD1
0x140043fc9  mov     rcx, rdi; Block
0x140043fcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140043fd1  xor     eax, eax
0x140043fd3  mov     rcx, [rsp+68h+var_28]
0x140043fd8  xor     rcx, rsp; StackCookie
0x140043fdb  call    __security_check_cookie
0x140043fe0  lea     r11, [rsp+68h+var_18]
0x140043fe5  mov     rbx, [r11+30h]
0x140043fe9  mov     rbp, [r11+38h]
0x140043fed  mov     rsp, r11
0x140043ff0  pop     r14
0x140043ff2  pop     rdi
0x140043ff3  pop     rsi
0x140043ff4  retn
```
