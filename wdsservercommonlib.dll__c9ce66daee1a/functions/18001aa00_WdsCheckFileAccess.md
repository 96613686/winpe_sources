# WdsCheckFileAccess

- ea: `0x18001aa00`
- end: `0x18001abf2`
- name: `WdsCheckFileAccess`
- size: `498`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HANDLE ClientToken)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000179c`
- `0x18001a28c`
- `0x18001aa00`
- `0x18002e468`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001aaa2`
- `KERNEL32!GetLastError` at `0x18001ab00`
- `KERNEL32!GetLastError` at `0x18001ab75`
- `KERNEL32!GetLastError` at `0x18001ab9d`
- `KERNEL32!GetLastError` at `0x18001aaa2`
- `KERNEL32!GetLastError` at `0x18001ab00`
- `KERNEL32!GetLastError` at `0x18001ab75`
- `KERNEL32!GetLastError` at `0x18001ab9d`
- `ADVAPI32!AccessCheck` at `0x18001ab65`
- `ADVAPI32!AccessCheck` at `0x18001ab65`
- `ADVAPI32!MapGenericMask` at `0x18001aa6d`
- `ADVAPI32!MapGenericMask` at `0x18001aa6d`
- `ADVAPI32!GetFileSecurityW` at `0x18001aa8e`
- `ADVAPI32!GetFileSecurityW` at `0x18001aaf0`
- `ADVAPI32!GetFileSecurityW` at `0x18001aa8e`
- `ADVAPI32!GetFileSecurityW` at `0x18001aaf0`

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
0x18001aa00  push    rbp
0x18001aa02  push    rbx
0x18001aa03  push    rsi
0x18001aa04  push    rdi
0x18001aa05  push    r14
0x18001aa07  lea     rbp, [rsp-37h]
0x18001aa0c  sub     rsp, 90h
0x18001aa13  mov     rax, cs:__security_cookie
0x18001aa1a  xor     rax, rsp
0x18001aa1d  mov     [rbp+57h+var_28], rax
0x18001aa21  xor     ebx, ebx
0x18001aa23  mov     [rbp+57h+AccessMask], r8d
0x18001aa27  and     [rbp+57h+var_60], ebx
0x18001aa2a  mov     r14, rdx
0x18001aa2d  and     [rbp+57h+nLengthNeeded], ebx
0x18001aa30  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18001aa34  and     [rbp+57h+var_5C], ebx
0x18001aa37  mov     rsi, rcx
0x18001aa3a  xorps   xmm0, xmm0
0x18001aa3d  mov     [rbp+57h+var_58], 14h
0x18001aa44  xor     eax, eax
0x18001aa46  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18001aa4d  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18001aa51  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18001aa54  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x18001aa58  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18001aa5f  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18001aa66  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18001aa6d  call    cs:__imp_MapGenericMask
0x18001aa74  nop     dword ptr [rax+rax+00h]
0x18001aa79  lea     rax, [rbp+57h+nLengthNeeded]
0x18001aa7d  xor     r9d, r9d; nLength
0x18001aa80  xor     r8d, r8d; pSecurityDescriptor
0x18001aa83  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001aa88  lea     edx, [rbx+7]; RequestedInformation
0x18001aa8b  mov     rcx, rsi; lpFileName
0x18001aa8e  call    cs:__imp_GetFileSecurityW
0x18001aa95  nop     dword ptr [rax+rax+00h]
0x18001aa9a  test    eax, eax
0x18001aa9c  jnz     loc_18001ABD0
0x18001aaa2  call    cs:__imp_GetLastError
0x18001aaa9  nop     dword ptr [rax+rax+00h]
0x18001aaae  cmp     eax, 7Ah ; 'z'
0x18001aab1  jnz     loc_18001AB9D
0x18001aab7  mov     ecx, [rbp+57h+nLengthNeeded]; unsigned __int64
0x18001aaba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aac1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001aac6  mov     rdi, rax
0x18001aac9  test    rax, rax
0x18001aacc  jnz     short loc_18001AAD8
0x18001aace  mov     ebx, 8007000Eh
0x18001aad3  jmp     loc_18001ABD5
0x18001aad8  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x18001aadc  lea     rax, [rbp+57h+nLengthNeeded]
0x18001aae0  mov     r8, rdi; pSecurityDescriptor
0x18001aae3  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001aae8  mov     edx, 7; RequestedInformation
0x18001aaed  mov     rcx, rsi; lpFileName
0x18001aaf0  call    cs:__imp_GetFileSecurityW
0x18001aaf7  nop     dword ptr [rax+rax+00h]
0x18001aafc  test    eax, eax
0x18001aafe  jnz     short loc_18001AB33
0x18001ab00  call    cs:__imp_GetLastError
0x18001ab07  nop     dword ptr [rax+rax+00h]
0x18001ab0c  mov     r9d, 0E85h
0x18001ab12  mov     ecx, eax
0x18001ab14  call    ElValidateWin32_8
0x18001ab19  mov     ebx, eax
0x18001ab1b  test    eax, eax
0x18001ab1d  jle     short loc_18001AB28
0x18001ab1f  movzx   ebx, ax
0x18001ab22  or      ebx, 80070000h
0x18001ab28  test    ebx, ebx
0x18001ab2a  js      short loc_18001AB93
0x18001ab2c  mov     ebx, 80004005h
0x18001ab31  jmp     short loc_18001AB93
0x18001ab33  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18001ab37  lea     rax, [rbp+57h+var_60]
0x18001ab3b  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18001ab40  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18001ab44  lea     rax, [rbp+57h+var_5C]
0x18001ab48  mov     rdx, r14; ClientToken
0x18001ab4b  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x18001ab50  mov     rcx, rdi; pSecurityDescriptor
0x18001ab53  lea     rax, [rbp+57h+var_58]
0x18001ab57  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001ab5c  lea     rax, [rbp+57h+PrivilegeSet]
0x18001ab60  mov     [rsp+0B0h+lpnLengthNeeded], rax; PrivilegeSet
0x18001ab65  call    cs:__imp_AccessCheck
0x18001ab6c  nop     dword ptr [rax+rax+00h]
0x18001ab71  test    eax, eax
0x18001ab73  jnz     short loc_18001AB89
0x18001ab75  call    cs:__imp_GetLastError
0x18001ab7c  nop     dword ptr [rax+rax+00h]
0x18001ab81  mov     r9d, 0E92h
0x18001ab87  jmp     short loc_18001AB12
0x18001ab89  cmp     [rbp+57h+var_60], ebx
0x18001ab8c  jnz     short loc_18001AB93
0x18001ab8e  mov     ebx, 80070005h
0x18001ab93  mov     rcx, rdi; lpMem
0x18001ab96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ab9b  jmp     short loc_18001ABD5
0x18001ab9d  call    cs:__imp_GetLastError
0x18001aba4  nop     dword ptr [rax+rax+00h]
0x18001aba9  mov     ecx, eax
0x18001abab  mov     r9d, 0E74h
0x18001abb1  call    ElValidateWin32_8
0x18001abb6  mov     ebx, eax
0x18001abb8  test    eax, eax
0x18001abba  jle     short loc_18001ABC5
0x18001abbc  movzx   ebx, ax
0x18001abbf  or      ebx, 80070000h
0x18001abc5  test    ebx, ebx
0x18001abc7  js      short loc_18001ABD5
0x18001abc9  mov     ebx, 80004005h
0x18001abce  jmp     short loc_18001ABD5
0x18001abd0  mov     ebx, 80070057h
0x18001abd5  mov     eax, ebx
0x18001abd7  mov     rcx, [rbp+57h+var_28]
0x18001abdb  xor     rcx, rsp; StackCookie
0x18001abde  call    __security_check_cookie
0x18001abe3  add     rsp, 90h
0x18001abea  pop     r14
0x18001abec  pop     rdi
0x18001abed  pop     rsi
0x18001abee  pop     rbx
0x18001abef  pop     rbp
0x18001abf0  retn
```
