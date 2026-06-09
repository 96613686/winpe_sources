# CUserProfile::UserHasExplicitAccess(void *,_ACL *)

- ea: `0x18006b5ac`
- end: `0x18006b6fe`
- name: `?UserHasExplicitAccess@CUserProfile@@CAJPEAXPEAU_ACL@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(PSID pSid2, PACL pAcl)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006ac5c`

## callees

- `0x18000a210`
- `0x1800321f0`
- `0x18006b5ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b640`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006b6b2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006b6b2`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18006b636`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18006b636`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18006b5f1`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18006b5f1`

## string_xrefs

- `0x18006b6ce`: `CUserProfile::UserHasExplicitAccess`
- `0x18006b614`: `GetAclInformation failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserProfile::UserHasExplicitAccess(PSID pSid2, PACL pAcl)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  DWORD i; // edi
  signed int v7; // eax
  char *v8; // r9
  LPVOID pAce; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+28h] [rbp-30h] BYREF
  int v12; // [rsp+30h] [rbp-28h]

  v3 = 1;
  v11 = 0;
  v12 = 0;
  pAce = 0;
  if ( GetAclInformation(pAcl, &v11, 0xCu, AclSizeInformation) )
    goto LABEL_6;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( (v3 & 0x80000000) == 0 )
  {
LABEL_6:
    for ( i = 0; ; ++i )
    {
      if ( i >= (unsigned int)v11 )
        return v3;
      if ( !GetAce(pAcl, i, &pAce) )
      {
        v7 = GetLastError();
        v3 = v7;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
      }
      if ( (v3 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "GetAce failed: 0x%x in %s", v3, "CUserProfile::UserHasExplicitAccess");
        return v3;
      }
      if ( *(_BYTE *)pAce )
      {
        if ( *(_BYTE *)pAce != 5 )
          continue;
        v8 = (char *)pAce + 16 * (*((_DWORD *)pAce + 2) & 1) + 12;
        if ( (*((_DWORD *)pAce + 2) & 2) != 0 )
          v8 = (char *)pAce + 16 * (*((_DWORD *)pAce + 2) & 1) + 28;
      }
      else
      {
        v8 = (char *)pAce + 8;
      }
      if ( (((*((_DWORD *)pAce + 1) & 0x1F01FF) != 2032127) & !_bittest((const signed __int32 *)pAce + 1, 0x1Cu)) == 0
        && EqualSid(v8, pSid2) )
      {
        return 0;
      }
    }
  }
  _DbgPrintMessage(8, "GetAclInformation failed: 0x%x in %s", v3, "CUserProfile::UserHasExplicitAccess");
  return v3;
}

```

## disassembly

```asm
0x18006b5ac  mov     r11, rsp
0x18006b5af  mov     [r11+18h], rbx
0x18006b5b3  push    rbp
0x18006b5b4  push    rsi
0x18006b5b5  push    rdi
0x18006b5b6  sub     rsp, 40h
0x18006b5ba  mov     rax, cs:__security_cookie
0x18006b5c1  xor     rax, rsp
0x18006b5c4  mov     [rsp+58h+var_20], rax
0x18006b5c9  xor     eax, eax
0x18006b5cb  mov     rsi, rdx
0x18006b5ce  mov     ebx, 1
0x18006b5d3  mov     [r11-30h], rax
0x18006b5d7  mov     rbp, rcx
0x18006b5da  mov     [rsp+58h+var_28], eax
0x18006b5de  lea     rdx, [r11-30h]; pAclInformation
0x18006b5e2  mov     [r11-38h], rax
0x18006b5e6  mov     rcx, rsi; pAcl
0x18006b5e9  lea     r9d, [rbx+1]; dwAclInformationClass
0x18006b5ed  lea     r8d, [rbx+0Bh]; nAclInformationLength
0x18006b5f1  call    cs:__imp_GetAclInformation
0x18006b5f7  test    eax, eax
0x18006b5f9  jnz     short loc_18006B620
0x18006b5fb  call    cs:__imp_GetLastError
0x18006b601  mov     ebx, eax
0x18006b603  test    eax, eax
0x18006b605  jle     short loc_18006B610
0x18006b607  movzx   ebx, ax
0x18006b60a  or      ebx, 80070000h
0x18006b610  test    ebx, ebx
0x18006b612  jns     short loc_18006B620
0x18006b614  lea     rdx, aGetaclinformat_0; "GetAclInformation failed: 0x%x in %s"
0x18006b61b  jmp     loc_18006B6CE
0x18006b620  xor     edi, edi
0x18006b622  cmp     edi, dword ptr [rsp+58h+var_30]
0x18006b626  jnb     loc_18006B6E2
0x18006b62c  lea     r8, [rsp+58h+pAce]; pAce
0x18006b631  mov     edx, edi; dwAceIndex
0x18006b633  mov     rcx, rsi; pAcl
0x18006b636  call    cs:__imp_GetAce
0x18006b63c  test    eax, eax
0x18006b63e  jnz     short loc_18006B655
0x18006b640  call    cs:__imp_GetLastError
0x18006b646  mov     ebx, eax
0x18006b648  test    eax, eax
0x18006b64a  jle     short loc_18006B655
0x18006b64c  movzx   ebx, ax
0x18006b64f  or      ebx, 80070000h
0x18006b655  test    ebx, ebx
0x18006b657  js      short loc_18006B6C7
0x18006b659  mov     r8, [rsp+58h+pAce]
0x18006b65e  mov     al, [r8]
0x18006b661  test    al, al
0x18006b663  jnz     short loc_18006B66B
0x18006b665  lea     r9, [r8+8]
0x18006b669  jmp     short loc_18006B68E
0x18006b66b  cmp     al, 5
0x18006b66d  jnz     short loc_18006B6BC
0x18006b66f  mov     edx, [r8+8]
0x18006b673  mov     ecx, edx
0x18006b675  and     ecx, 1
0x18006b678  shl     rcx, 4
0x18006b67c  add     rcx, 1Ch
0x18006b680  add     rcx, r8
0x18006b683  test    dl, 2
0x18006b686  lea     r9, [rcx-10h]
0x18006b68a  cmovnz  r9, rcx
0x18006b68e  mov     eax, [r8+4]
0x18006b692  and     eax, 1F01FFh
0x18006b697  cmp     eax, 1F01FFh
0x18006b69c  setnz   dl
0x18006b69f  bt      dword ptr [r8+4], 1Ch
0x18006b6a5  setnb   al
0x18006b6a8  test    al, dl
0x18006b6aa  jnz     short loc_18006B6BC
0x18006b6ac  mov     rdx, rbp; pSid2
0x18006b6af  mov     rcx, r9; pSid1
0x18006b6b2  call    cs:__imp_EqualSid
0x18006b6b8  test    eax, eax
0x18006b6ba  jnz     short loc_18006B6C3
0x18006b6bc  inc     edi
0x18006b6be  jmp     loc_18006B622
0x18006b6c3  xor     ebx, ebx
0x18006b6c5  jmp     short loc_18006B6E2
0x18006b6c7  lea     rdx, aGetaceFailed0x; "GetAce failed: 0x%x in %s"
0x18006b6ce  lea     r9, aCuserprofileUs; "CUserProfile::UserHasExplicitAccess"
0x18006b6d5  mov     r8d, ebx
0x18006b6d8  mov     ecx, 8; int
0x18006b6dd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b6e2  mov     eax, ebx
0x18006b6e4  mov     rcx, [rsp+58h+var_20]
0x18006b6e9  xor     rcx, rsp; StackCookie
0x18006b6ec  call    __security_check_cookie
0x18006b6f1  mov     rbx, [rsp+58h+arg_10]
0x18006b6f6  add     rsp, 40h
0x18006b6fa  pop     rdi
0x18006b6fb  pop     rsi
0x18006b6fc  pop     rbp
0x18006b6fd  retn
```
