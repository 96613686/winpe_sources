# CUtils::IsCallerSystem(void)

- ea: `0x18009d908`
- end: `0x18009dbcd`
- name: `?IsCallerSystem@CUtils@@SAJXZ`
- size: `709`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038670`
- `0x18005aab0`
- `0x18005efe0`

## callees

- `0x18000a210`
- `0x1800321f0`
- `0x18009d908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009d9b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009d9b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009da0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009da79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009db14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009db34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009da0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009da79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009db14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009db34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009d96b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009d96b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009d982`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009d982`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009db8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009db8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009dabb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009dabb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009db9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009dbab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009db9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009dbab`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18009da31`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18009da31`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18009da6b`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18009db0a`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18009da6b`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18009db0a`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18009d9bc`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18009d9bc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009da02`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009da02`

## string_xrefs

- `0x18009d9a4`: `IsCallerSystem: Could not open thread token %x`
- `0x18009d9e4`: `IsCallerSystem: IsTokenRestricted failed %x`
- `0x18009da1d`: `IsCallerSystem: Could not convert security descriptor string %x`
- `0x18009db73`: `IsCallerSystem: Token is restricted %x`
- `0x18009daaa`: `IsCallerSystem: AccessCheck probe returned privilege set size of 0 unexpectedly %x`
- `0x18009da92`: `IsCallerSystem: Token access check probe failed %x`
- `0x18009db25`: `IsCallerSystem: Token access check failed %x`
- `0x18009dace`: `IsCallerSystem: Failed to allocate privilege set %x`
- `0x18009db54`: `IsCallerSystem: Token missing required right`
- `0x18009db45`: `IsCallerSystem: Token access denied %x`

## pseudocode

```c
__int64 CUtils::IsCallerSystem(void)
{
  struct _PRIVILEGE_SET *v0; // rsi
  HANDLE CurrentThread; // rax
  signed int v2; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  WINBOOL AccessStatus; // [rsp+40h] [rbp-19h] BYREF
  DWORD PrivilegeSetLength; // [rsp+44h] [rbp-15h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-11h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-Dh] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-1h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+7h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+17h] BYREF

  TokenHandle = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  v0 = 0;
  SecurityDescriptor = 0;
  GenericMapping = (struct _GENERIC_MAPPING)xmmword_1800FFD20;
  GrantedAccess = 0;
  AccessMask = 0x40000000;
  PrivilegeSetLength = 20;
  CurrentThread = GetCurrentThread();
  AccessStatus = OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  if ( AccessStatus )
  {
    SetLastError(0);
    if ( IsTokenRestricted(TokenHandle) )
    {
      v3 = -2147024891;
      _DbgPrintMessage(8, "IsCallerSystem: Token is restricted %x", 2147942405LL);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 )
      {
        _DbgPrintMessage(8, "IsCallerSystem: IsTokenRestricted failed %x", v3);
        goto LABEL_35;
      }
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:SYG:BAD:(A;;0x1;;;SY)", 1u, &SecurityDescriptor, 0) )
      {
        MapGenericMask(&AccessMask, &GenericMapping);
        if ( AccessCheck(
               SecurityDescriptor,
               TokenHandle,
               AccessMask,
               &GenericMapping,
               &PrivilegeSet,
               &PrivilegeSetLength,
               &GrantedAccess,
               &AccessStatus) )
        {
          goto LABEL_27;
        }
        v6 = GetLastError();
        v3 = v6;
        if ( v6 > 0 )
          v3 = (unsigned __int16)v6 | 0x80070000;
        if ( v3 != -2147024774 )
        {
          _DbgPrintMessage(8, "IsCallerSystem: Token access check probe failed %x", v3);
          goto LABEL_35;
        }
        if ( !PrivilegeSetLength )
        {
          v3 = -2147418113;
          _DbgPrintMessage(
            8,
            "IsCallerSystem: AccessCheck probe returned privilege set size of 0 unexpectedly %x",
            2147549183LL);
          goto LABEL_35;
        }
        v0 = (struct _PRIVILEGE_SET *)LocalAlloc(0, PrivilegeSetLength);
        if ( !v0 )
        {
          v3 = -2147024882;
          _DbgPrintMessage(8, "IsCallerSystem: Failed to allocate privilege set %x", 2147942414LL);
          goto LABEL_35;
        }
        if ( AccessCheck(
               SecurityDescriptor,
               TokenHandle,
               AccessMask,
               &GenericMapping,
               v0,
               &PrivilegeSetLength,
               &GrantedAccess,
               &AccessStatus) )
        {
LABEL_27:
          if ( AccessStatus )
          {
            if ( (GrantedAccess & 1) != 0 )
            {
              v3 = 0;
            }
            else
            {
              v3 = 1;
              _DbgPrintMessage(8, "IsCallerSystem: Token missing required right");
            }
          }
          else
          {
            v8 = GetLastError();
            v3 = v8;
            if ( v8 > 0 )
              v3 = (unsigned __int16)v8 | 0x80070000;
            _DbgPrintMessage(8, "IsCallerSystem: Token access denied %x", v3);
          }
        }
        else
        {
          v7 = GetLastError();
          v3 = v7;
          if ( v7 > 0 )
            v3 = (unsigned __int16)v7 | 0x80070000;
          _DbgPrintMessage(8, "IsCallerSystem: Token access check failed %x", v3);
        }
      }
      else
      {
        v5 = GetLastError();
        v3 = v5;
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
        _DbgPrintMessage(8, "IsCallerSystem: Could not convert security descriptor string %x", v3);
      }
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    _DbgPrintMessage(8, "IsCallerSystem: Could not open thread token %x", v3);
  }
LABEL_35:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v0 )
    LocalFree(v0);
  return v3;
}

```

## disassembly

```asm
0x18009d908  push    rbp
0x18009d90a  push    rbx
0x18009d90b  push    rsi
0x18009d90c  push    rdi
0x18009d90d  push    r15
0x18009d90f  lea     rbp, [rsp-37h]
0x18009d914  sub     rsp, 90h
0x18009d91b  mov     rax, cs:__security_cookie
0x18009d922  xor     rax, rsp
0x18009d925  mov     [rbp+57h+var_28], rax
0x18009d929  xorps   xmm0, xmm0
0x18009d92c  mov     [rbp+57h+TokenHandle], 0
0x18009d934  movups  xmmword ptr [rbp+57h+var_40.PrivilegeCount], xmm0
0x18009d938  xor     eax, eax
0x18009d93a  xor     esi, esi
0x18009d93c  movups  xmm0, cs:xmmword_1800FFD20
0x18009d943  mov     [rbp+57h+var_70], 0
0x18009d94a  mov     [rbp+57h+SecurityDescriptor], 0
0x18009d952  movdqu  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18009d957  mov     [rbp+57h+var_64], esi
0x18009d95a  mov     [rbp+57h+AccessMask], 40000000h
0x18009d961  mov     [rbp+57h+var_40.Privilege.Attributes], eax
0x18009d964  mov     [rbp+57h+var_6C], 14h
0x18009d96b  call    cs:__imp_GetCurrentThread
0x18009d971  lea     r15d, [rsi+8]
0x18009d975  xor     r8d, r8d; OpenAsSelf
0x18009d978  mov     rcx, rax; ThreadHandle
0x18009d97b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18009d97f  mov     edx, r15d; DesiredAccess
0x18009d982  call    cs:__imp_OpenThreadToken
0x18009d988  mov     [rbp+57h+var_70], eax
0x18009d98b  test    eax, eax
0x18009d98d  jnz     short loc_18009D9B0
0x18009d98f  call    cs:__imp_GetLastError
0x18009d995  mov     ebx, eax
0x18009d997  test    eax, eax
0x18009d999  jle     short loc_18009D9A4
0x18009d99b  movzx   ebx, ax
0x18009d99e  or      ebx, 80070000h
0x18009d9a4  lea     rdx, aIscallersystem_1; "IsCallerSystem: Could not open thread t"...
0x18009d9ab  jmp     loc_18009DB7A
0x18009d9b0  xor     ecx, ecx; dwErrCode
0x18009d9b2  call    cs:__imp_SetLastError
0x18009d9b8  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18009d9bc  call    cs:__imp_IsTokenRestricted
0x18009d9c2  test    eax, eax
0x18009d9c4  jnz     loc_18009DB6E
0x18009d9ca  call    cs:__imp_GetLastError
0x18009d9d0  mov     ebx, eax
0x18009d9d2  mov     edi, 80070000h
0x18009d9d7  test    eax, eax
0x18009d9d9  jle     short loc_18009D9E0
0x18009d9db  movzx   ebx, ax
0x18009d9de  or      ebx, edi
0x18009d9e0  test    ebx, ebx
0x18009d9e2  jz      short loc_18009D9F0
0x18009d9e4  lea     rdx, aIscallersystem_6; "IsCallerSystem: IsTokenRestricted faile"...
0x18009d9eb  jmp     loc_18009DB7A
0x18009d9f0  xor     r9d, r9d; SecurityDescriptorSize
0x18009d9f3  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18009d9f7  lea     rcx, StringSecurityDescriptor; "O:SYG:BAD:(A;;0x1;;;SY)"
0x18009d9fe  lea     edx, [r9+1]; StringSDRevision
0x18009da02  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18009da08  test    eax, eax
0x18009da0a  jnz     short loc_18009DA29
0x18009da0c  call    cs:__imp_GetLastError
0x18009da12  mov     ebx, eax
0x18009da14  test    eax, eax
0x18009da16  jle     short loc_18009DA1D
0x18009da18  movzx   ebx, ax
0x18009da1b  or      ebx, edi
0x18009da1d  lea     rdx, aIscallersystem_3; "IsCallerSystem: Could not convert secur"...
0x18009da24  jmp     loc_18009DB7A
0x18009da29  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18009da2d  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18009da31  call    cs:__imp_MapGenericMask
0x18009da37  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18009da3b  lea     rax, [rbp+57h+var_70]
0x18009da3f  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18009da43  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18009da47  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18009da4b  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18009da50  lea     rax, [rbp+57h+var_64]
0x18009da54  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x18009da59  lea     rax, [rbp+57h+var_6C]
0x18009da5d  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18009da62  lea     rax, [rbp+57h+var_40]
0x18009da66  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x18009da6b  call    cs:__imp_AccessCheck
0x18009da71  test    eax, eax
0x18009da73  jnz     loc_18009DB2E
0x18009da79  call    cs:__imp_GetLastError
0x18009da7f  mov     ebx, eax
0x18009da81  test    eax, eax
0x18009da83  jle     short loc_18009DA8A
0x18009da85  movzx   ebx, ax
0x18009da88  or      ebx, edi
0x18009da8a  cmp     ebx, 8007007Ah
0x18009da90  jz      short loc_18009DA9E
0x18009da92  lea     rdx, aIscallersystem_2; "IsCallerSystem: Token access check prob"...
0x18009da99  jmp     loc_18009DB7A
0x18009da9e  mov     eax, [rbp+57h+var_6C]
0x18009daa1  test    eax, eax
0x18009daa3  jnz     short loc_18009DAB6
0x18009daa5  mov     ebx, 8000FFFFh
0x18009daaa  lea     rdx, aIscallersystem_8; "IsCallerSystem: AccessCheck probe retur"...
0x18009dab1  jmp     loc_18009DB7A
0x18009dab6  mov     rdx, rax; uBytes
0x18009dab9  xor     ecx, ecx; uFlags
0x18009dabb  call    cs:__imp_LocalAlloc
0x18009dac1  mov     rsi, rax
0x18009dac4  test    rax, rax
0x18009dac7  jnz     short loc_18009DADA
0x18009dac9  mov     ebx, 8007000Eh
0x18009dace  lea     rdx, aIscallersystem_7; "IsCallerSystem: Failed to allocate priv"...
0x18009dad5  jmp     loc_18009DB7A
0x18009dada  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18009dade  lea     rax, [rbp+57h+var_70]
0x18009dae2  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18009dae6  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18009daea  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18009daee  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18009daf3  lea     rax, [rbp+57h+var_64]
0x18009daf7  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x18009dafc  lea     rax, [rbp+57h+var_6C]
0x18009db00  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18009db05  mov     [rsp+0B0h+PrivilegeSet], rsi; PrivilegeSet
0x18009db0a  call    cs:__imp_AccessCheck
0x18009db10  test    eax, eax
0x18009db12  jnz     short loc_18009DB2E
0x18009db14  call    cs:__imp_GetLastError
0x18009db1a  mov     ebx, eax
0x18009db1c  test    eax, eax
0x18009db1e  jle     short loc_18009DB25
0x18009db20  movzx   ebx, ax
0x18009db23  or      ebx, edi
0x18009db25  lea     rdx, aIscallersystem_5; "IsCallerSystem: Token access check fail"...
0x18009db2c  jmp     short loc_18009DB7A
0x18009db2e  cmp     [rbp+57h+var_70], 0
0x18009db32  jnz     short loc_18009DB4E
0x18009db34  call    cs:__imp_GetLastError
0x18009db3a  mov     ebx, eax
0x18009db3c  test    eax, eax
0x18009db3e  jle     short loc_18009DB45
0x18009db40  movzx   ebx, ax
0x18009db43  or      ebx, edi
0x18009db45  lea     rdx, aIscallersystem_0; "IsCallerSystem: Token access denied %x"
0x18009db4c  jmp     short loc_18009DB7A
0x18009db4e  test    byte ptr [rbp+57h+var_64], 1
0x18009db52  jnz     short loc_18009DB6A
0x18009db54  lea     rdx, aIscallersystem_4; "IsCallerSystem: Token missing required "...
0x18009db5b  mov     ecx, r15d; int
0x18009db5e  mov     ebx, 1
0x18009db63  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009db68  jmp     short loc_18009DB85
0x18009db6a  xor     ebx, ebx
0x18009db6c  jmp     short loc_18009DB85
0x18009db6e  mov     ebx, 80070005h
0x18009db73  lea     rdx, aIscallersystem; "IsCallerSystem: Token is restricted %x"
0x18009db7a  mov     r8d, ebx
0x18009db7d  mov     ecx, r15d; int
0x18009db80  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009db85  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18009db89  test    rcx, rcx
0x18009db8c  jz      short loc_18009DB94
0x18009db8e  call    cs:__imp_CloseHandle
0x18009db94  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18009db98  test    rcx, rcx
0x18009db9b  jz      short loc_18009DBA3
0x18009db9d  call    cs:__imp_LocalFree
0x18009dba3  test    rsi, rsi
0x18009dba6  jz      short loc_18009DBB1
0x18009dba8  mov     rcx, rsi; hMem
0x18009dbab  call    cs:__imp_LocalFree
0x18009dbb1  mov     eax, ebx
0x18009dbb3  mov     rcx, [rbp+57h+var_28]
0x18009dbb7  xor     rcx, rsp; StackCookie
0x18009dbba  call    __security_check_cookie
0x18009dbbf  add     rsp, 90h
0x18009dbc6  pop     r15
0x18009dbc8  pop     rdi
0x18009dbc9  pop     rsi
0x18009dbca  pop     rbx
0x18009dbcb  pop     rbp
0x18009dbcc  retn
```
