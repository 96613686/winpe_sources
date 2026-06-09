# FolderAccessCheck(ushort const *,void *,ulong)

- ea: `0x18002cad4`
- end: `0x18002cc8c`
- name: `?FolderAccessCheck@@YAJPEBGPEAXK@Z`
- size: `440`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HANDLE ClientToken, DWORD DesiredAccess)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180016040`
- `0x18002cc94`
- `0x18002cdb0`

## callees

- `0x180007948`
- `0x180007988`
- `0x18002cad4`
- `0x180030700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002cc19`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18002cc19`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002cb2d`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002cb9f`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002cb2d`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002cb9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc3c`

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
0x18002cad4  mov     [rsp-28h+arg_18], rbx
0x18002cad9  push    rbp
0x18002cada  push    rsi
0x18002cadb  push    rdi
0x18002cadc  push    r14
0x18002cade  push    r15
0x18002cae0  mov     rbp, rsp
0x18002cae3  sub     rsp, 80h
0x18002caea  mov     rax, cs:__security_cookie
0x18002caf1  xor     rax, rsp
0x18002caf4  mov     [rbp+var_8], rax
0x18002caf8  mov     edi, r8d
0x18002cafb  mov     r15, rdx
0x18002cafe  mov     r14, rcx
0x18002cb01  test    r8d, r8d
0x18002cb04  jz      loc_18002CC63
0x18002cb0a  test    rcx, rcx
0x18002cb0d  jz      loc_18002CC63
0x18002cb13  xor     r9d, r9d; nLength
0x18002cb16  mov     [rbp+nLengthNeeded], 0
0x18002cb1d  lea     rax, [rbp+nLengthNeeded]
0x18002cb21  xor     r8d, r8d; pSecurityDescriptor
0x18002cb24  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002cb29  lea     edx, [r9+7]; RequestedInformation
0x18002cb2d  call    cs:__imp_GetFileSecurityW
0x18002cb34  nop     dword ptr [rax+rax+00h]
0x18002cb39  test    eax, eax
0x18002cb3b  jnz     short loc_18002CB63
0x18002cb3d  call    cs:__imp_GetLastError
0x18002cb44  nop     dword ptr [rax+rax+00h]
0x18002cb49  cmp     eax, 7Ah ; 'z'
0x18002cb4c  jz      short loc_18002CB63
0x18002cb4e  test    eax, eax
0x18002cb50  jle     loc_18002CC68
0x18002cb56  movzx   eax, ax
0x18002cb59  or      eax, 80070000h
0x18002cb5e  jmp     loc_18002CC68
0x18002cb63  mov     eax, [rbp+nLengthNeeded]
0x18002cb66  mov     ebx, 80070005h
0x18002cb6b  test    eax, eax
0x18002cb6d  jz      loc_18002CC5F
0x18002cb73  lea     ecx, [rax+1]; Size
0x18002cb76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cb7b  mov     rsi, rax
0x18002cb7e  test    rax, rax
0x18002cb81  jz      loc_18002CC5F
0x18002cb87  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18002cb8b  lea     rax, [rbp+nLengthNeeded]
0x18002cb8f  mov     r8, rsi; pSecurityDescriptor
0x18002cb92  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002cb97  mov     edx, 7; RequestedInformation
0x18002cb9c  mov     rcx, r14; lpFileName
0x18002cb9f  call    cs:__imp_GetFileSecurityW
0x18002cba6  nop     dword ptr [rax+rax+00h]
0x18002cbab  test    eax, eax
0x18002cbad  jz      loc_18002CC3C
0x18002cbb3  xor     eax, eax
0x18002cbb5  mov     [rbp+GenericMapping.GenericRead], 120089h
0x18002cbbc  mov     [rbp+PrivilegeSet.Privilege.Attributes], eax
0x18002cbbf  lea     r9, [rbp+GenericMapping]; GenericMapping
0x18002cbc3  mov     [rbp+var_3C], eax
0x18002cbc6  xorps   xmm0, xmm0
0x18002cbc9  mov     [rbp+var_38], eax
0x18002cbcc  mov     r8d, edi; DesiredAccess
0x18002cbcf  lea     rax, [rbp+var_3C]
0x18002cbd3  mov     [rbp+GenericMapping.GenericWrite], 120116h
0x18002cbda  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x18002cbdf  mov     rdx, r15; ClientToken
0x18002cbe2  lea     rax, [rbp+var_38]
0x18002cbe6  mov     [rbp+GenericMapping.GenericExecute], 1200A0h
0x18002cbed  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x18002cbf2  mov     rcx, rsi; pSecurityDescriptor
0x18002cbf5  lea     rax, [rbp+var_34]
0x18002cbf9  mov     [rbp+GenericMapping.GenericAll], 1F01FFh
0x18002cc00  mov     [rsp+80h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18002cc05  lea     rax, [rbp+PrivilegeSet]
0x18002cc09  mov     [rsp+80h+lpnLengthNeeded], rax; PrivilegeSet
0x18002cc0e  movups  xmmword ptr [rbp+PrivilegeSet.PrivilegeCount], xmm0
0x18002cc12  mov     [rbp+var_34], 14h
0x18002cc19  call    cs:__imp_AccessCheck
0x18002cc20  nop     dword ptr [rax+rax+00h]
0x18002cc25  test    eax, eax
0x18002cc27  jz      short loc_18002CC57
0x18002cc29  cmp     [rbp+var_3C], 0
0x18002cc2d  jz      short loc_18002CC57
0x18002cc2f  mov     eax, edi
0x18002cc31  and     eax, [rbp+var_38]
0x18002cc34  cmp     eax, edi
0x18002cc36  jnz     short loc_18002CC57
0x18002cc38  xor     ebx, ebx
0x18002cc3a  jmp     short loc_18002CC57
0x18002cc3c  call    cs:__imp_GetLastError
0x18002cc43  nop     dword ptr [rax+rax+00h]
0x18002cc48  mov     ebx, eax
0x18002cc4a  test    eax, eax
0x18002cc4c  jle     short loc_18002CC57
0x18002cc4e  movzx   ebx, ax
0x18002cc51  or      ebx, 80070000h
0x18002cc57  mov     rcx, rsi; Block
0x18002cc5a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cc5f  mov     eax, ebx
0x18002cc61  jmp     short loc_18002CC68
0x18002cc63  mov     eax, 80070005h
0x18002cc68  mov     rcx, [rbp+var_8]
0x18002cc6c  xor     rcx, rsp; StackCookie
0x18002cc6f  call    __security_check_cookie
0x18002cc74  mov     rbx, [rsp+80h+arg_18]
0x18002cc7c  add     rsp, 80h
0x18002cc83  pop     r15
0x18002cc85  pop     r14
0x18002cc87  pop     rdi
0x18002cc88  pop     rsi
0x18002cc89  pop     rbp
0x18002cc8a  retn
```
