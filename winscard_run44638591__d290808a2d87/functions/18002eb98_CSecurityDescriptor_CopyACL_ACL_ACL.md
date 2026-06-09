# CSecurityDescriptor::CopyACL(_ACL *,_ACL *)

- ea: `0x18002eb98`
- end: `0x18002ec60`
- name: `?CopyACL@CSecurityDescriptor@@SAJPEAU_ACL@@0@Z`
- size: `200`
- prototype: `__int64 __fastcall(PACL pAcl, PACL)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e998`

## callees

- `0x18001be10`
- `0x18002eb98`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002ec33`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002ec33`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002ec0f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002ec0f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002ebdf`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002ebdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebe9`

## pseudocode

```c
signed int __fastcall CSecurityDescriptor::CopyACL(PACL pAcl, PACL a2)
{
  signed int result; // eax
  DWORD i; // ebx
  LPVOID pAce; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+38h] [rbp-20h] BYREF
  int v8; // [rsp+40h] [rbp-18h]

  v7 = 0;
  v8 = 0;
  pAce = 0;
  if ( !a2 )
    return 0;
  if ( GetAclInformation(a2, &v7, 0xCu, AclSizeInformation) )
  {
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      if ( !GetAce(a2, i, &pAce) || !AddAce(pAcl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
        goto LABEL_3;
    }
    return 0;
  }
LABEL_3:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002eb98  mov     r11, rsp
0x18002eb9b  mov     [r11+18h], rbx
0x18002eb9f  mov     [r11+20h], rsi
0x18002eba3  push    rdi
0x18002eba4  sub     rsp, 50h
0x18002eba8  mov     rax, cs:__security_cookie
0x18002ebaf  xor     rax, rsp
0x18002ebb2  mov     [rsp+58h+var_10], rax
0x18002ebb7  xor     eax, eax
0x18002ebb9  mov     rdi, rdx
0x18002ebbc  mov     [r11-20h], rax
0x18002ebc0  mov     rsi, rcx
0x18002ebc3  mov     [rsp+58h+var_18], eax
0x18002ebc7  mov     [r11-28h], rax
0x18002ebcb  test    rdx, rdx
0x18002ebce  jz      short loc_18002EC41
0x18002ebd0  lea     r9d, [rax+2]; dwAclInformationClass
0x18002ebd4  mov     rcx, rdi; pAcl
0x18002ebd7  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18002ebdb  lea     rdx, [r11-20h]; pAclInformation
0x18002ebdf  call    cs:__imp_GetAclInformation
0x18002ebe5  test    eax, eax
0x18002ebe7  jnz     short loc_18002EBFD
0x18002ebe9  call    cs:__imp_GetLastError
0x18002ebef  test    eax, eax
0x18002ebf1  jle     short loc_18002EC43
0x18002ebf3  movzx   eax, ax
0x18002ebf6  or      eax, 80070000h
0x18002ebfb  jmp     short loc_18002EC43
0x18002ebfd  xor     ebx, ebx
0x18002ebff  cmp     ebx, dword ptr [rsp+58h+var_20]
0x18002ec03  jnb     short loc_18002EC41
0x18002ec05  lea     r8, [rsp+58h+pAce]; pAce
0x18002ec0a  mov     edx, ebx; dwAceIndex
0x18002ec0c  mov     rcx, rdi; pAcl
0x18002ec0f  call    cs:__imp_GetAce
0x18002ec15  test    eax, eax
0x18002ec17  jz      short loc_18002EBE9
0x18002ec19  mov     r9, [rsp+58h+pAce]; pAceList
0x18002ec1e  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18002ec22  mov     edx, 2; dwAceRevision
0x18002ec27  mov     rcx, rsi; pAcl
0x18002ec2a  movzx   eax, word ptr [r9+2]
0x18002ec2f  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x18002ec33  call    cs:__imp_AddAce
0x18002ec39  test    eax, eax
0x18002ec3b  jz      short loc_18002EBE9
0x18002ec3d  inc     ebx
0x18002ec3f  jmp     short loc_18002EBFF
0x18002ec41  xor     eax, eax
0x18002ec43  mov     rcx, [rsp+58h+var_10]
0x18002ec48  xor     rcx, rsp; StackCookie
0x18002ec4b  call    __security_check_cookie
0x18002ec50  mov     rbx, [rsp+58h+arg_10]
0x18002ec55  mov     rsi, [rsp+58h+arg_18]
0x18002ec5a  add     rsp, 50h
0x18002ec5e  pop     rdi
0x18002ec5f  retn
```
