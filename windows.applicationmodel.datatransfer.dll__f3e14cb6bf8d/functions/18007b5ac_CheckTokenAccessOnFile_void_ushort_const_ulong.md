# CheckTokenAccessOnFile(void *,ushort const *,ulong)

- ea: `0x18007b5ac`
- end: `0x18007b713`
- name: `?CheckTokenAccessOnFile@@YAJPEAXPEBGK@Z`
- size: `359`
- prototype: `__int64 __fastcall(HANDLE ClientToken, LPCWSTR pObjectName)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800602dc`
- `0x180064d70`

## callees

- `0x180002ad0`
- `0x18007b5ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b6b1`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18007b6a7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18007b6a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007b6ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007b6ea`
- `ntdll!RtlMapGenericMask` at `0x18007b655`
- `ntdll!RtlMapGenericMask` at `0x18007b655`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18007b614`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18007b614`

## pseudocode

```c
__int64 __fastcall CheckTokenAccessOnFile(HANDLE ClientToken, LPCWSTR pObjectName)
{
  signed int NamedSecurityInfoW; // eax
  signed int v4; // ebx
  signed int LastError; // eax
  PSECURITY_DESCRIPTOR v6; // rcx
  DWORD AccessMask; // [rsp+48h] [rbp+7h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp+Fh] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp+17h] BYREF
  DWORD GrantedAccess; // [rsp+60h] [rbp+1Fh] BYREF
  DWORD PrivilegeSetLength; // [rsp+64h] [rbp+23h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp+27h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp+37h] BYREF

  AccessMask = 1179785;
  pSecurityDescriptor = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 7u, 0, 0, 0, 0, &pSecurityDescriptor);
  v4 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    v4 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( v4 >= 0 )
  {
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    RtlMapGenericMask(&AccessMask, &GenericMapping);
    GrantedAccess = 0;
    AccessStatus = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    PrivilegeSetLength = 20;
    if ( AccessCheck(
           pSecurityDescriptor,
           ClientToken,
           AccessMask,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      v4 = 0;
      if ( !AccessStatus )
        v4 = -2147024891;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
    }
  }
  v6 = pSecurityDescriptor;
  pSecurityDescriptor = 0;
  LocalFree(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007b5ac  mov     r11, rsp
0x18007b5af  mov     [r11+18h], rbx
0x18007b5b3  mov     [r11+20h], rdi
0x18007b5b7  push    rbp
0x18007b5b8  lea     rbp, [r11-5Fh]
0x18007b5bc  sub     rsp, 90h
0x18007b5c3  mov     rax, cs:__security_cookie
0x18007b5ca  xor     rax, rsp
0x18007b5cd  mov     [rbp+57h+var_8], rax
0x18007b5d1  mov     rdi, rcx
0x18007b5d4  mov     [rbp+57h+AccessMask], 120089h
0x18007b5db  xor     r9d, r9d; ppsidOwner
0x18007b5de  mov     [rbp+57h+pSecurityDescriptor], 0
0x18007b5e6  mov     rax, rdx
0x18007b5e9  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x18007b5ed  mov     [r11-60h], rcx
0x18007b5f1  mov     rcx, rax; pObjectName
0x18007b5f4  mov     qword ptr [r11-68h], 0
0x18007b5fc  mov     qword ptr [r11-70h], 0
0x18007b604  lea     edx, [r9+1]; ObjectType
0x18007b608  lea     r8d, [r9+7]; SecurityInfo
0x18007b60c  mov     qword ptr [r11-78h], 0
0x18007b614  call    cs:__imp_GetNamedSecurityInfoW
0x18007b61a  mov     ebx, eax
0x18007b61c  test    eax, eax
0x18007b61e  jle     short loc_18007B629
0x18007b620  movzx   ebx, ax
0x18007b623  or      ebx, 80070000h
0x18007b629  test    ebx, ebx
0x18007b62b  js      loc_18007B6DE
0x18007b631  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18007b635  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18007b63c  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18007b640  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18007b647  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18007b64e  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18007b655  call    cs:__imp_RtlMapGenericMask
0x18007b65b  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18007b65f  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18007b663  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18007b667  xor     eax, eax
0x18007b669  mov     [rbp+57h+var_20.Privilege.Attributes], eax
0x18007b66c  xorps   xmm0, xmm0
0x18007b66f  mov     [rbp+57h+var_38], eax
0x18007b672  mov     rdx, rdi; ClientToken
0x18007b675  mov     [rbp+57h+var_48], eax
0x18007b678  lea     rax, [rbp+57h+var_48]
0x18007b67c  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x18007b681  lea     rax, [rbp+57h+var_38]
0x18007b685  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x18007b68a  lea     rax, [rbp+57h+var_34]
0x18007b68e  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18007b693  lea     rax, [rbp+57h+var_20]
0x18007b697  mov     [rsp+90h+PrivilegeSet], rax; PrivilegeSet
0x18007b69c  movups  xmmword ptr [rbp+57h+var_20.PrivilegeCount], xmm0
0x18007b6a0  mov     [rbp+57h+var_34], 14h
0x18007b6a7  call    cs:__imp_AccessCheck
0x18007b6ad  test    eax, eax
0x18007b6af  jnz     short loc_18007B6D2
0x18007b6b1  call    cs:__imp_GetLastError
0x18007b6b7  mov     ebx, eax
0x18007b6b9  test    eax, eax
0x18007b6bb  jle     short loc_18007B6C6
0x18007b6bd  movzx   ebx, ax
0x18007b6c0  or      ebx, 80070000h
0x18007b6c6  test    ebx, ebx
0x18007b6c8  mov     eax, 80004005h
0x18007b6cd  cmovns  ebx, eax
0x18007b6d0  jmp     short loc_18007B6DE
0x18007b6d2  xor     ebx, ebx
0x18007b6d4  cmp     [rbp+57h+var_48], ebx
0x18007b6d7  jnz     short loc_18007B6DE
0x18007b6d9  mov     ebx, 80070005h
0x18007b6de  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x18007b6e2  mov     [rbp+57h+pSecurityDescriptor], 0
0x18007b6ea  call    cs:__imp_LocalFree
0x18007b6f0  mov     eax, ebx
0x18007b6f2  mov     rcx, [rbp+57h+var_8]
0x18007b6f6  xor     rcx, rsp; StackCookie
0x18007b6f9  call    __security_check_cookie
0x18007b6fe  lea     r11, [rsp+90h+var_s0]
0x18007b706  mov     rbx, [r11+20h]
0x18007b70a  mov     rdi, [r11+28h]
0x18007b70e  mov     rsp, r11
0x18007b711  pop     rbp
0x18007b712  retn
```
