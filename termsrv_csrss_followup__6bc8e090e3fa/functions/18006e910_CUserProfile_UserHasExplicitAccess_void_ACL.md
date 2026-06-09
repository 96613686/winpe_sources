# CUserProfile::UserHasExplicitAccess(void *,_ACL *)

- ea: `0x18006e910`
- end: `0x18006ea81`
- name: `?UserHasExplicitAccess@CUserProfile@@CAJPEAXPEAU_ACL@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(PSID pSid2, PACL pAcl)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006df3c`

## callees

- `0x180009940`
- `0x180033f60`
- `0x18006e910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e9b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e9b6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006ea2e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006ea2e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18006e9a6`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18006e9a6`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18006e955`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18006e955`

## string_xrefs

- `0x18006ea50`: `CUserProfile::UserHasExplicitAccess`
- `0x18006e984`: `GetAclInformation failed: 0x%x in %s`

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
0x18006e910  mov     r11, rsp
0x18006e913  mov     [r11+18h], rbx
0x18006e917  push    rbp
0x18006e918  push    rsi
0x18006e919  push    rdi
0x18006e91a  sub     rsp, 40h
0x18006e91e  mov     rax, cs:__security_cookie
0x18006e925  xor     rax, rsp
0x18006e928  mov     [rsp+58h+var_20], rax
0x18006e92d  xor     eax, eax
0x18006e92f  mov     rsi, rdx
0x18006e932  mov     ebx, 1
0x18006e937  mov     [r11-30h], rax
0x18006e93b  mov     rbp, rcx
0x18006e93e  mov     [rsp+58h+var_28], eax
0x18006e942  lea     rdx, [r11-30h]; pAclInformation
0x18006e946  mov     [r11-38h], rax
0x18006e94a  mov     rcx, rsi; pAcl
0x18006e94d  lea     r9d, [rbx+1]; dwAclInformationClass
0x18006e951  lea     r8d, [rbx+0Bh]; nAclInformationLength
0x18006e955  call    cs:__imp_GetAclInformation
0x18006e95c  nop     dword ptr [rax+rax+00h]
0x18006e961  test    eax, eax
0x18006e963  jnz     short loc_18006E990
0x18006e965  call    cs:__imp_GetLastError
0x18006e96c  nop     dword ptr [rax+rax+00h]
0x18006e971  mov     ebx, eax
0x18006e973  test    eax, eax
0x18006e975  jle     short loc_18006E980
0x18006e977  movzx   ebx, ax
0x18006e97a  or      ebx, 80070000h
0x18006e980  test    ebx, ebx
0x18006e982  jns     short loc_18006E990
0x18006e984  lea     rdx, aGetaclinformat_0; "GetAclInformation failed: 0x%x in %s"
0x18006e98b  jmp     loc_18006EA50
0x18006e990  xor     edi, edi
0x18006e992  cmp     edi, dword ptr [rsp+58h+var_30]
0x18006e996  jnb     loc_18006EA64
0x18006e99c  lea     r8, [rsp+58h+pAce]; pAce
0x18006e9a1  mov     edx, edi; dwAceIndex
0x18006e9a3  mov     rcx, rsi; pAcl
0x18006e9a6  call    cs:__imp_GetAce
0x18006e9ad  nop     dword ptr [rax+rax+00h]
0x18006e9b2  test    eax, eax
0x18006e9b4  jnz     short loc_18006E9D1
0x18006e9b6  call    cs:__imp_GetLastError
0x18006e9bd  nop     dword ptr [rax+rax+00h]
0x18006e9c2  mov     ebx, eax
0x18006e9c4  test    eax, eax
0x18006e9c6  jle     short loc_18006E9D1
0x18006e9c8  movzx   ebx, ax
0x18006e9cb  or      ebx, 80070000h
0x18006e9d1  test    ebx, ebx
0x18006e9d3  js      short loc_18006EA49
0x18006e9d5  mov     r8, [rsp+58h+pAce]
0x18006e9da  mov     al, [r8]
0x18006e9dd  test    al, al
0x18006e9df  jnz     short loc_18006E9E7
0x18006e9e1  lea     r9, [r8+8]
0x18006e9e5  jmp     short loc_18006EA0A
0x18006e9e7  cmp     al, 5
0x18006e9e9  jnz     short loc_18006EA3E
0x18006e9eb  mov     edx, [r8+8]
0x18006e9ef  mov     ecx, edx
0x18006e9f1  and     ecx, 1
0x18006e9f4  shl     rcx, 4
0x18006e9f8  add     rcx, 1Ch
0x18006e9fc  add     rcx, r8
0x18006e9ff  test    dl, 2
0x18006ea02  lea     r9, [rcx-10h]
0x18006ea06  cmovnz  r9, rcx
0x18006ea0a  mov     eax, [r8+4]
0x18006ea0e  and     eax, 1F01FFh
0x18006ea13  cmp     eax, 1F01FFh
0x18006ea18  setnz   dl
0x18006ea1b  bt      dword ptr [r8+4], 1Ch
0x18006ea21  setnb   al
0x18006ea24  test    al, dl
0x18006ea26  jnz     short loc_18006EA3E
0x18006ea28  mov     rdx, rbp; pSid2
0x18006ea2b  mov     rcx, r9; pSid1
0x18006ea2e  call    cs:__imp_EqualSid
0x18006ea35  nop     dword ptr [rax+rax+00h]
0x18006ea3a  test    eax, eax
0x18006ea3c  jnz     short loc_18006EA45
0x18006ea3e  inc     edi
0x18006ea40  jmp     loc_18006E992
0x18006ea45  xor     ebx, ebx
0x18006ea47  jmp     short loc_18006EA64
0x18006ea49  lea     rdx, aGetaceFailed0x; "GetAce failed: 0x%x in %s"
0x18006ea50  lea     r9, aCuserprofileUs; "CUserProfile::UserHasExplicitAccess"
0x18006ea57  mov     r8d, ebx
0x18006ea5a  mov     ecx, 8; int
0x18006ea5f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ea64  mov     eax, ebx
0x18006ea66  mov     rcx, [rsp+58h+var_20]
0x18006ea6b  xor     rcx, rsp; StackCookie
0x18006ea6e  call    __security_check_cookie
0x18006ea73  mov     rbx, [rsp+58h+arg_10]
0x18006ea78  add     rsp, 40h
0x18006ea7c  pop     rdi
0x18006ea7d  pop     rsi
0x18006ea7e  pop     rbp
0x18006ea7f  retn
```
