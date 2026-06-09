# WdsCheckFileAccess

- ea: `0x18001b890`
- end: `0x18001ba89`
- name: `WdsCheckFileAccess`
- size: `505`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HANDLE ClientToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000214c`
- `0x18001b0cc`
- `0x18001b890`
- `0x180030390`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ba26`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ba26`
- `KERNEL32!GetLastError` at `0x18001b932`
- `KERNEL32!GetLastError` at `0x18001b990`
- `KERNEL32!GetLastError` at `0x18001ba05`
- `KERNEL32!GetLastError` at `0x18001ba34`
- `KERNEL32!GetLastError` at `0x18001b932`
- `KERNEL32!GetLastError` at `0x18001b990`
- `KERNEL32!GetLastError` at `0x18001ba05`
- `KERNEL32!GetLastError` at `0x18001ba34`
- `ADVAPI32!GetFileSecurityW` at `0x18001b91e`
- `ADVAPI32!GetFileSecurityW` at `0x18001b980`
- `ADVAPI32!GetFileSecurityW` at `0x18001b91e`
- `ADVAPI32!GetFileSecurityW` at `0x18001b980`
- `ADVAPI32!MapGenericMask` at `0x18001b8fd`
- `ADVAPI32!MapGenericMask` at `0x18001b8fd`
- `ADVAPI32!AccessCheck` at `0x18001b9f5`
- `ADVAPI32!AccessCheck` at `0x18001b9f5`

## pseudocode

```c
__int64 __fastcall WdsCheckFileAccess(LPCWSTR lpFileName, HANDLE ClientToken, DWORD a3)
{
  signed int v3; // ebx
  void *v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // eax
  DWORD v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // eax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-19h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-11h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp-9h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-5h] BYREF
  DWORD PrivilegeSetLength; // [rsp+58h] [rbp-1h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+7h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+17h] BYREF

  v3 = 0;
  AccessMask = a3;
  AccessStatus = 0;
  nLengthNeeded = 0;
  GrantedAccess = 0;
  PrivilegeSetLength = 20;
  GenericMapping.GenericRead = 1179785;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  MapGenericMask(&AccessMask, &GenericMapping);
  if ( GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded) )
    return (unsigned int)-2147024809;
  if ( GetLastError() == 122 )
  {
    v6 = operator new[](nLengthNeeded, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v6 )
      return (unsigned int)-2147024882;
    if ( GetFileSecurityW(lpFileName, 7u, v6, nLengthNeeded, &nLengthNeeded) )
    {
      if ( AccessCheck(
             v6,
             ClientToken,
             AccessMask,
             &GenericMapping,
             &PrivilegeSet,
             &PrivilegeSetLength,
             &GrantedAccess,
             &AccessStatus) )
      {
        if ( !AccessStatus )
          v3 = -2147024891;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v10 = 3730;
    }
    else
    {
      LastError = GetLastError();
      v10 = 3717;
    }
    v11 = ElValidateWin32_8(LastError, v8, v9, v10);
    v3 = v11;
    if ( v11 > 0 )
      v3 = (unsigned __int16)v11 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
LABEL_15:
    operator delete(v6);
    return (unsigned int)v3;
  }
  v12 = GetLastError();
  v15 = ElValidateWin32_8(v12, v13, v14, 3700);
  v3 = v15;
  if ( v15 > 0 )
    v3 = (unsigned __int16)v15 | 0x80070000;
  if ( v3 >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001b890  push    rbp
0x18001b892  push    rbx
0x18001b893  push    rsi
0x18001b894  push    rdi
0x18001b895  push    r14
0x18001b897  lea     rbp, [rsp-37h]
0x18001b89c  sub     rsp, 90h
0x18001b8a3  mov     rax, cs:__security_cookie
0x18001b8aa  xor     rax, rsp
0x18001b8ad  mov     [rbp+57h+var_28], rax
0x18001b8b1  xor     ebx, ebx
0x18001b8b3  mov     [rbp+57h+AccessMask], r8d
0x18001b8b7  and     [rbp+57h+var_60], ebx
0x18001b8ba  mov     r14, rdx
0x18001b8bd  and     [rbp+57h+nLengthNeeded], ebx
0x18001b8c0  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18001b8c4  and     [rbp+57h+var_5C], ebx
0x18001b8c7  mov     rsi, rcx
0x18001b8ca  xorps   xmm0, xmm0
0x18001b8cd  mov     [rbp+57h+var_58], 14h
0x18001b8d4  xor     eax, eax
0x18001b8d6  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18001b8dd  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18001b8e1  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18001b8e4  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x18001b8e8  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18001b8ef  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18001b8f6  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18001b8fd  call    cs:__imp_MapGenericMask
0x18001b904  nop     dword ptr [rax+rax+00h]
0x18001b909  lea     rax, [rbp+57h+nLengthNeeded]
0x18001b90d  xor     r9d, r9d; nLength
0x18001b910  xor     r8d, r8d; pSecurityDescriptor
0x18001b913  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001b918  lea     edx, [rbx+7]; RequestedInformation
0x18001b91b  mov     rcx, rsi; lpFileName
0x18001b91e  call    cs:__imp_GetFileSecurityW
0x18001b925  nop     dword ptr [rax+rax+00h]
0x18001b92a  test    eax, eax
0x18001b92c  jnz     loc_18001BA67
0x18001b932  call    cs:__imp_GetLastError
0x18001b939  nop     dword ptr [rax+rax+00h]
0x18001b93e  cmp     eax, 7Ah ; 'z'
0x18001b941  jnz     loc_18001BA34
0x18001b947  mov     ecx, [rbp+57h+nLengthNeeded]; unsigned __int64
0x18001b94a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b951  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b956  mov     rdi, rax
0x18001b959  test    rax, rax
0x18001b95c  jnz     short loc_18001B968
0x18001b95e  mov     ebx, 8007000Eh
0x18001b963  jmp     loc_18001BA6C
0x18001b968  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x18001b96c  lea     rax, [rbp+57h+nLengthNeeded]
0x18001b970  mov     r8, rdi; pSecurityDescriptor
0x18001b973  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001b978  mov     edx, 7; RequestedInformation
0x18001b97d  mov     rcx, rsi; lpFileName
0x18001b980  call    cs:__imp_GetFileSecurityW
0x18001b987  nop     dword ptr [rax+rax+00h]
0x18001b98c  test    eax, eax
0x18001b98e  jnz     short loc_18001B9C3
0x18001b990  call    cs:__imp_GetLastError
0x18001b997  nop     dword ptr [rax+rax+00h]
0x18001b99c  mov     r9d, 0E85h
0x18001b9a2  mov     ecx, eax
0x18001b9a4  call    ElValidateWin32_8
0x18001b9a9  mov     ebx, eax
0x18001b9ab  test    eax, eax
0x18001b9ad  jle     short loc_18001B9B8
0x18001b9af  movzx   ebx, ax
0x18001b9b2  or      ebx, 80070000h
0x18001b9b8  test    ebx, ebx
0x18001b9ba  js      short loc_18001BA23
0x18001b9bc  mov     ebx, 80004005h
0x18001b9c1  jmp     short loc_18001BA23
0x18001b9c3  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18001b9c7  lea     rax, [rbp+57h+var_60]
0x18001b9cb  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18001b9d0  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18001b9d4  lea     rax, [rbp+57h+var_5C]
0x18001b9d8  mov     rdx, r14; ClientToken
0x18001b9db  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x18001b9e0  mov     rcx, rdi; pSecurityDescriptor
0x18001b9e3  lea     rax, [rbp+57h+var_58]
0x18001b9e7  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001b9ec  lea     rax, [rbp+57h+PrivilegeSet]
0x18001b9f0  mov     [rsp+0B0h+lpnLengthNeeded], rax; PrivilegeSet
0x18001b9f5  call    cs:__imp_AccessCheck
0x18001b9fc  nop     dword ptr [rax+rax+00h]
0x18001ba01  test    eax, eax
0x18001ba03  jnz     short loc_18001BA19
0x18001ba05  call    cs:__imp_GetLastError
0x18001ba0c  nop     dword ptr [rax+rax+00h]
0x18001ba11  mov     r9d, 0E92h
0x18001ba17  jmp     short loc_18001B9A2
0x18001ba19  cmp     [rbp+57h+var_60], ebx
0x18001ba1c  jnz     short loc_18001BA23
0x18001ba1e  mov     ebx, 80070005h
0x18001ba23  mov     rcx, rdi
0x18001ba26  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ba2d  nop     dword ptr [rax+rax+00h]
0x18001ba32  jmp     short loc_18001BA6C
0x18001ba34  call    cs:__imp_GetLastError
0x18001ba3b  nop     dword ptr [rax+rax+00h]
0x18001ba40  mov     ecx, eax
0x18001ba42  mov     r9d, 0E74h
0x18001ba48  call    ElValidateWin32_8
0x18001ba4d  mov     ebx, eax
0x18001ba4f  test    eax, eax
0x18001ba51  jle     short loc_18001BA5C
0x18001ba53  movzx   ebx, ax
0x18001ba56  or      ebx, 80070000h
0x18001ba5c  test    ebx, ebx
0x18001ba5e  js      short loc_18001BA6C
0x18001ba60  mov     ebx, 80004005h
0x18001ba65  jmp     short loc_18001BA6C
0x18001ba67  mov     ebx, 80070057h
0x18001ba6c  mov     eax, ebx
0x18001ba6e  mov     rcx, [rbp+57h+var_28]
0x18001ba72  xor     rcx, rsp; StackCookie
0x18001ba75  call    __security_check_cookie
0x18001ba7a  add     rsp, 90h
0x18001ba81  pop     r14
0x18001ba83  pop     rdi
0x18001ba84  pop     rsi
0x18001ba85  pop     rbx
0x18001ba86  pop     rbp
0x18001ba87  retn
```
