# CVssSecurityDescriptor::CopyACL(_ACL *,_ACL *)

- ea: `0x18003c808`
- end: `0x18003c8d0`
- name: `?CopyACL@CVssSecurityDescriptor@@CAJPEAU_ACL@@0@Z`
- size: `200`
- prototype: `signed int __fastcall(PACL pAcl, PACL)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b9bc`
- `0x18003bae4`

## callees

- `0x180001580`
- `0x18003c808`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c859`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003c84f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003c84f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003c87f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003c87f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18003c8a3`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18003c8a3`

## pseudocode

```c
signed int __fastcall CVssSecurityDescriptor::CopyACL(PACL pAcl, PACL a2)
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
0x18003c808  mov     r11, rsp
0x18003c80b  mov     [r11+18h], rbx
0x18003c80f  mov     [r11+20h], rsi
0x18003c813  push    rdi
0x18003c814  sub     rsp, 50h
0x18003c818  mov     rax, cs:__security_cookie
0x18003c81f  xor     rax, rsp
0x18003c822  mov     [rsp+58h+var_10], rax
0x18003c827  xor     eax, eax
0x18003c829  mov     rdi, rdx
0x18003c82c  mov     [r11-20h], rax
0x18003c830  mov     rsi, rcx
0x18003c833  mov     [rsp+58h+var_18], eax
0x18003c837  mov     [r11-28h], rax
0x18003c83b  test    rdx, rdx
0x18003c83e  jz      short loc_18003C8B1
0x18003c840  lea     r9d, [rax+2]; dwAclInformationClass
0x18003c844  mov     rcx, rdi; pAcl
0x18003c847  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18003c84b  lea     rdx, [r11-20h]; pAclInformation
0x18003c84f  call    cs:__imp_GetAclInformation
0x18003c855  test    eax, eax
0x18003c857  jnz     short loc_18003C86D
0x18003c859  call    cs:__imp_GetLastError
0x18003c85f  test    eax, eax
0x18003c861  jle     short loc_18003C8B3
0x18003c863  movzx   eax, ax
0x18003c866  or      eax, 80070000h
0x18003c86b  jmp     short loc_18003C8B3
0x18003c86d  xor     ebx, ebx
0x18003c86f  cmp     ebx, dword ptr [rsp+58h+var_20]
0x18003c873  jnb     short loc_18003C8B1
0x18003c875  lea     r8, [rsp+58h+pAce]; pAce
0x18003c87a  mov     edx, ebx; dwAceIndex
0x18003c87c  mov     rcx, rdi; pAcl
0x18003c87f  call    cs:__imp_GetAce
0x18003c885  test    eax, eax
0x18003c887  jz      short loc_18003C859
0x18003c889  mov     r9, [rsp+58h+pAce]; pAceList
0x18003c88e  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18003c892  mov     edx, 2; dwAceRevision
0x18003c897  mov     rcx, rsi; pAcl
0x18003c89a  movzx   eax, word ptr [r9+2]
0x18003c89f  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x18003c8a3  call    cs:__imp_AddAce
0x18003c8a9  test    eax, eax
0x18003c8ab  jz      short loc_18003C859
0x18003c8ad  inc     ebx
0x18003c8af  jmp     short loc_18003C86F
0x18003c8b1  xor     eax, eax
0x18003c8b3  mov     rcx, [rsp+58h+var_10]
0x18003c8b8  xor     rcx, rsp; StackCookie
0x18003c8bb  call    __security_check_cookie
0x18003c8c0  mov     rbx, [rsp+58h+arg_10]
0x18003c8c5  mov     rsi, [rsp+58h+arg_18]
0x18003c8ca  add     rsp, 50h
0x18003c8ce  pop     rdi
0x18003c8cf  retn
```
