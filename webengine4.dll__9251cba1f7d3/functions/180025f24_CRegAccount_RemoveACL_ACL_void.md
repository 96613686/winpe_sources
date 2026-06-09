# CRegAccount::RemoveACL(_ACL *,void *)

- ea: `0x180025f24`
- end: `0x180025ff1`
- name: `?RemoveACL@CRegAccount@@SAJPEAU_ACL@@PEAX@Z`
- size: `205`
- prototype: `__int64 __fastcall(PACL pAcl, PSID pSid1)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800263bc`
- `0x180044ea0`

## callees

- `0x180025f24`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x180025fb4`
- `ADVAPI32!EqualSid` at `0x180025fb4`
- `ADVAPI32!DeleteAce` at `0x180025fc3`
- `ADVAPI32!DeleteAce` at `0x180025fc3`
- `ADVAPI32!GetAce` at `0x180025f95`
- `ADVAPI32!GetAce` at `0x180025f95`
- `ADVAPI32!GetAclInformation` at `0x180025f6d`
- `ADVAPI32!GetAclInformation` at `0x180025f6d`

## pseudocode

```c
__int64 __fastcall CRegAccount::RemoveACL(PACL pAcl, PSID pSid1)
{
  unsigned int v2; // ebx
  DWORD v5; // edi
  LPVOID pAce; // [rsp+20h] [rbp-38h] BYREF
  __int64 pAclInformation; // [rsp+28h] [rbp-30h] BYREF
  int v9; // [rsp+30h] [rbp-28h]

  v2 = 0;
  if ( pAcl && pSid1 )
  {
    pAclInformation = 0;
    v9 = 0;
    if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      v5 = pAclInformation;
      while ( (--v5 & 0x80000000) == 0 )
      {
        pAce = 0;
        if ( GetAce(pAcl, v5, &pAce) && pAce && !*(_BYTE *)pAce && EqualSid(pSid1, (char *)pAce + 8) )
          DeleteAce(pAcl, v5);
      }
    }
    else
    {
      return (unsigned int)GetLastWin32Error();
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x180025f24  mov     [rsp+arg_10], rbx
0x180025f29  push    rbp
0x180025f2a  push    rsi
0x180025f2b  push    rdi
0x180025f2c  sub     rsp, 40h
0x180025f30  mov     rax, cs:__security_cookie
0x180025f37  xor     rax, rsp
0x180025f3a  mov     [rsp+58h+var_20], rax
0x180025f3f  xor     ebx, ebx
0x180025f41  mov     rbp, rdx
0x180025f44  mov     rsi, rcx
0x180025f47  test    rcx, rcx
0x180025f4a  jz      loc_180025FD0
0x180025f50  test    rdx, rdx
0x180025f53  jz      short loc_180025FD0
0x180025f55  xor     eax, eax
0x180025f57  lea     r9d, [rbx+2]; dwAclInformationClass
0x180025f5b  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x180025f5f  mov     [rsp+58h+pAclInformation], rax
0x180025f64  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x180025f69  mov     [rsp+58h+var_28], eax
0x180025f6d  call    cs:__imp_GetAclInformation
0x180025f73  test    eax, eax
0x180025f75  jnz     short loc_180025F80
0x180025f77  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180025f7c  mov     ebx, eax
0x180025f7e  jmp     short loc_180025FD5
0x180025f80  mov     edi, dword ptr [rsp+58h+pAclInformation]
0x180025f84  jmp     short loc_180025FC9
0x180025f86  lea     r8, [rsp+58h+pAce]; pAce
0x180025f8b  mov     [rsp+58h+pAce], rbx
0x180025f90  mov     edx, edi; dwAceIndex
0x180025f92  mov     rcx, rsi; pAcl
0x180025f95  call    cs:__imp_GetAce
0x180025f9b  test    eax, eax
0x180025f9d  jz      short loc_180025FC9
0x180025f9f  mov     rdx, [rsp+58h+pAce]
0x180025fa4  test    rdx, rdx
0x180025fa7  jz      short loc_180025FC9
0x180025fa9  cmp     [rdx], bl
0x180025fab  jnz     short loc_180025FC9
0x180025fad  add     rdx, 8; pSid2
0x180025fb1  mov     rcx, rbp; pSid1
0x180025fb4  call    cs:__imp_EqualSid
0x180025fba  test    eax, eax
0x180025fbc  jz      short loc_180025FC9
0x180025fbe  mov     edx, edi; dwAceIndex
0x180025fc0  mov     rcx, rsi; pAcl
0x180025fc3  call    cs:__imp_DeleteAce
0x180025fc9  sub     edi, 1
0x180025fcc  jns     short loc_180025F86
0x180025fce  jmp     short loc_180025FD5
0x180025fd0  mov     ebx, 80070057h
0x180025fd5  mov     eax, ebx
0x180025fd7  mov     rcx, [rsp+58h+var_20]
0x180025fdc  xor     rcx, rsp; StackCookie
0x180025fdf  call    __security_check_cookie
0x180025fe4  mov     rbx, [rsp+58h+arg_10]
0x180025fe9  add     rsp, 40h
0x180025fed  pop     rdi
0x180025fee  pop     rsi
0x180025fef  pop     rbp
0x180025ff0  retn
```
