# FolderAccessCheck(ushort const *,void *,ulong)

- ea: `0x18002af30`
- end: `0x18002b0c9`
- name: `?FolderAccessCheck@@YAJPEBGPEAXK@Z`
- size: `409`
- prototype: `signed int __fastcall(LPCWSTR lpFileName, HANDLE ClientToken, DWORD DesiredAccess)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180015280`
- `0x18002b0d0`
- `0x18002b1b4`

## callees

- `0x180007488`
- `0x1800074c8`
- `0x18002af30`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002b063`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002b063`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002af89`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002afef`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002af89`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002afef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b080`

## pseudocode

```c
signed int __fastcall FolderAccessCheck(LPCWSTR lpFileName, HANDLE ClientToken, DWORD DesiredAccess)
{
  signed int result; // eax
  unsigned int v7; // ebx
  void *v8; // rsi
  signed int LastError; // eax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-40h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-38h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp-34h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-30h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-20h] BYREF

  if ( !DesiredAccess || !lpFileName )
    return -2147024891;
  nLengthNeeded = 0;
  if ( GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded) || (result = GetLastError(), result == 122) )
  {
    v7 = -2147024891;
    if ( nLengthNeeded )
    {
      v8 = operator new(nLengthNeeded + 1);
      if ( v8 )
      {
        if ( GetFileSecurityW(lpFileName, 7u, v8, nLengthNeeded, &nLengthNeeded) )
        {
          GenericMapping.GenericRead = 1179785;
          AccessStatus = 0;
          GrantedAccess = 0;
          GenericMapping.GenericWrite = 1179926;
          GenericMapping.GenericExecute = 1179808;
          GenericMapping.GenericAll = 2032127;
          memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
          PrivilegeSetLength = 20;
          if ( AccessCheck(
                 v8,
                 ClientToken,
                 DesiredAccess,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus)
            && AccessStatus
            && (GrantedAccess & DesiredAccess) == DesiredAccess )
          {
            v7 = 0;
          }
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
        }
        operator delete(v8);
      }
    }
    return v7;
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002af30  mov     [rsp-28h+arg_18], rbx
0x18002af35  push    rbp
0x18002af36  push    rsi
0x18002af37  push    rdi
0x18002af38  push    r14
0x18002af3a  push    r15
0x18002af3c  mov     rbp, rsp
0x18002af3f  sub     rsp, 80h
0x18002af46  mov     rax, cs:__security_cookie
0x18002af4d  xor     rax, rsp
0x18002af50  mov     [rbp+var_8], rax
0x18002af54  mov     edi, r8d
0x18002af57  mov     r15, rdx
0x18002af5a  mov     r14, rcx
0x18002af5d  test    r8d, r8d
0x18002af60  jz      loc_18002B0A1
0x18002af66  test    rcx, rcx
0x18002af69  jz      loc_18002B0A1
0x18002af6f  xor     r9d, r9d; nLength
0x18002af72  mov     [rbp+nLengthNeeded], 0
0x18002af79  lea     rax, [rbp+nLengthNeeded]
0x18002af7d  xor     r8d, r8d; pSecurityDescriptor
0x18002af80  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002af85  lea     edx, [r9+7]; RequestedInformation
0x18002af89  call    cs:__imp_GetFileSecurityW
0x18002af8f  test    eax, eax
0x18002af91  jnz     short loc_18002AFB3
0x18002af93  call    cs:__imp_GetLastError
0x18002af99  cmp     eax, 7Ah ; 'z'
0x18002af9c  jz      short loc_18002AFB3
0x18002af9e  test    eax, eax
0x18002afa0  jle     loc_18002B0A6
0x18002afa6  movzx   eax, ax
0x18002afa9  or      eax, 80070000h
0x18002afae  jmp     loc_18002B0A6
0x18002afb3  mov     eax, [rbp+nLengthNeeded]
0x18002afb6  mov     ebx, 80070005h
0x18002afbb  test    eax, eax
0x18002afbd  jz      loc_18002B09D
0x18002afc3  lea     ecx, [rax+1]; Size
0x18002afc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002afcb  mov     rsi, rax
0x18002afce  test    rax, rax
0x18002afd1  jz      loc_18002B09D
0x18002afd7  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18002afdb  lea     rax, [rbp+nLengthNeeded]
0x18002afdf  mov     r8, rsi; pSecurityDescriptor
0x18002afe2  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002afe7  mov     edx, 7; RequestedInformation
0x18002afec  mov     rcx, r14; lpFileName
0x18002afef  call    cs:__imp_GetFileSecurityW
0x18002aff5  test    eax, eax
0x18002aff7  jz      loc_18002B080
0x18002affd  xor     eax, eax
0x18002afff  mov     [rbp+GenericMapping.GenericRead], 120089h
0x18002b006  mov     [rbp+PrivilegeSet.Privilege.Attributes], eax
0x18002b009  lea     r9, [rbp+GenericMapping]; GenericMapping
0x18002b00d  mov     [rbp+var_3C], eax
0x18002b010  xorps   xmm0, xmm0
0x18002b013  mov     [rbp+var_38], eax
0x18002b016  mov     r8d, edi; DesiredAccess
0x18002b019  lea     rax, [rbp+var_3C]
0x18002b01d  mov     [rbp+GenericMapping.GenericWrite], 120116h
0x18002b024  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x18002b029  mov     rdx, r15; ClientToken
0x18002b02c  lea     rax, [rbp+var_38]
0x18002b030  mov     [rbp+GenericMapping.GenericExecute], 1200A0h
0x18002b037  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x18002b03c  mov     rcx, rsi; pSecurityDescriptor
0x18002b03f  lea     rax, [rbp+var_34]
0x18002b043  mov     [rbp+GenericMapping.GenericAll], 1F01FFh
0x18002b04a  mov     [rsp+80h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18002b04f  lea     rax, [rbp+PrivilegeSet]
0x18002b053  mov     [rsp+80h+lpnLengthNeeded], rax; PrivilegeSet
0x18002b058  movups  xmmword ptr [rbp+PrivilegeSet.PrivilegeCount], xmm0
0x18002b05c  mov     [rbp+var_34], 14h
0x18002b063  call    cs:__imp_AccessCheck
0x18002b069  test    eax, eax
0x18002b06b  jz      short loc_18002B095
0x18002b06d  cmp     [rbp+var_3C], 0
0x18002b071  jz      short loc_18002B095
0x18002b073  mov     eax, edi
0x18002b075  and     eax, [rbp+var_38]
0x18002b078  cmp     eax, edi
0x18002b07a  jnz     short loc_18002B095
0x18002b07c  xor     ebx, ebx
0x18002b07e  jmp     short loc_18002B095
0x18002b080  call    cs:__imp_GetLastError
0x18002b086  mov     ebx, eax
0x18002b088  test    eax, eax
0x18002b08a  jle     short loc_18002B095
0x18002b08c  movzx   ebx, ax
0x18002b08f  or      ebx, 80070000h
0x18002b095  mov     rcx, rsi; Block
0x18002b098  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b09d  mov     eax, ebx
0x18002b09f  jmp     short loc_18002B0A6
0x18002b0a1  mov     eax, 80070005h
0x18002b0a6  mov     rcx, [rbp+var_8]
0x18002b0aa  xor     rcx, rsp; StackCookie
0x18002b0ad  call    __security_check_cookie
0x18002b0b2  mov     rbx, [rsp+80h+arg_18]
0x18002b0ba  add     rsp, 80h
0x18002b0c1  pop     r15
0x18002b0c3  pop     r14
0x18002b0c5  pop     rdi
0x18002b0c6  pop     rsi
0x18002b0c7  pop     rbp
0x18002b0c8  retn
```
