# AccessCheckForRailEncVC(ulong)

- ea: `0x18005ec90`
- end: `0x18005ef58`
- name: `?AccessCheckForRailEncVC@@YAJK@Z`
- size: `712`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180060880`

## callees

- `0x180009940`
- `0x18005ec90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ed53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ed53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ed6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ed6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ef3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ef3d`
- `RPCRT4!RpcRevertToSelf` at `0x18005ef28`
- `RPCRT4!RpcRevertToSelf` at `0x18005ef28`
- `RPCRT4!RpcImpersonateClient` at `0x18005ed1d`
- `RPCRT4!RpcImpersonateClient` at `0x18005ed1d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ecf6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ecf6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005edc7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005ee8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005edc7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005ee8a`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18005ee40`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18005ee40`

## string_xrefs

- `0x18005ed32`: `Cannot impersonate client: %d`
- `0x18005ed0c`: `AccessCheckForRailEncVC bypassed since we are running inside container`
- `0x18005ee29`: `AccessCheckForRailEncVC`
- `0x18005eee0`: `AccessCheckForRailEncVC`
- `0x18005eda1`: `OpenThreadToken failed failed: 0x%x in %s`
- `0x18005edf9`: `GetTokenInformation with TokenSessionId failed failed: 0x%x in %s`
- `0x18005ee22`: `%s failed 0x%x: AccessCheckForRailEncVC failed! CallerSessionId(%u) != SessionIdOfVC(%u)`
- `0x18005eebb`: `GetTokenInformation with TokenUIAccess failed failed: 0x%x in %s`
- `0x18005eed6`: `AccessCheckForRailEncVC failed! dwUIAccess == 0 failed: 0x%x in %s`
- `0x18005ef01`: `UAC disabled, bypassing the UIAccess check in AccessCheckForRailEncVC`
- `0x18005ef12`: `AccessCheckForRailEncVC passed`
- `0x18005eef1`: `AccessCheckForRailEncVC failed (0x%x)`

## pseudocode

```c
__int64 __fastcall AccessCheckForRailEncVC(int a1)
{
  int v1; // r15d
  RPC_STATUS v3; // eax
  signed int v4; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v7; // eax
  int v8; // eax
  signed int v9; // eax
  bool v10; // sf
  int TokenInformation; // [rsp+40h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+44h] [rbp-1Ch] BYREF
  int v14; // [rsp+48h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-14h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-10h] BYREF
  int v17; // [rsp+98h] [rbp+38h] BYREF
  int pvData; // [rsp+A0h] [rbp+40h] BYREF
  DWORD ReturnLength; // [rsp+A8h] [rbp+48h] BYREF

  v1 = 0;
  TokenHandle = 0;
  v14 = 0;
  TokenInformation = 0;
  v17 = 0;
  TokenInformationLength = 4;
  ReturnLength = 4;
  pcbData = 4;
  pvData = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server",
         L"ContainerMode",
         0x10u,
         0,
         &pvData,
         &pcbData)
    || !pvData )
  {
    v3 = RpcImpersonateClient(0);
    if ( v3 )
    {
      _DbgPrintMessage(8, "Cannot impersonate client: %d", v3);
      v4 = -2147024891;
    }
    else
    {
      v1 = 1;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
        goto LABEL_42;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_42:
        if ( GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, ReturnLength, &ReturnLength) )
        {
          if ( TokenInformation != a1 )
          {
            v4 = -2147024891;
            _DbgPrintMessage(
              8,
              "%s failed 0x%x: AccessCheckForRailEncVC failed! CallerSessionId(%u) != SessionIdOfVC(%u)",
              "AccessCheckForRailEncVC",
              -2147024891,
              TokenInformation,
              a1);
            goto LABEL_31;
          }
        }
        else
        {
          v7 = GetLastError();
          v4 = v7;
          if ( v7 > 0 )
            v4 = (unsigned __int16)v7 | 0x80070000;
          if ( v4 < 0 )
          {
            _DbgPrintMessage(
              8,
              "GetTokenInformation with TokenSessionId failed failed: 0x%x in %s",
              (unsigned int)v4,
              "AccessCheckForRailEncVC");
            goto LABEL_31;
          }
        }
        if ( (unsigned int)CheckElevationEnabled(&v17) )
        {
          _DbgPrintMessage(8, "CheckElevationEnabled failed, set fLuaEnabled = FALSE");
          v8 = 0;
          v17 = 0;
        }
        else
        {
          v8 = v17;
        }
        if ( !v8 )
        {
          _DbgPrintMessage(1, "UAC disabled, bypassing the UIAccess check in AccessCheckForRailEncVC");
          goto LABEL_33;
        }
        if ( GetTokenInformation(TokenHandle, TokenUIAccess, &v14, TokenInformationLength, &TokenInformationLength) )
        {
          if ( v14 )
            goto LABEL_33;
          v4 = -2147024891;
          _DbgPrintMessage(
            8,
            "AccessCheckForRailEncVC failed! dwUIAccess == 0 failed: 0x%x in %s",
            2147942405LL,
            "AccessCheckForRailEncVC");
        }
        else
        {
          v9 = GetLastError();
          v10 = v9 < 0;
          if ( v9 > 0 )
          {
            v9 = (unsigned __int16)v9 | 0x80070000;
            v10 = v9 < 0;
          }
          v4 = v9;
          if ( v10 )
          {
            _DbgPrintMessage(
              8,
              "GetTokenInformation with TokenUIAccess failed failed: 0x%x in %s",
              (unsigned int)v9,
              "AccessCheckForRailEncVC");
          }
          else if ( !v9 )
          {
            goto LABEL_34;
          }
        }
      }
      else
      {
        _DbgPrintMessage(8, "OpenThreadToken failed failed: 0x%x in %s", (unsigned int)v4, "AccessCheckForRailEncVC");
      }
    }
LABEL_31:
    _DbgPrintMessage(8, "AccessCheckForRailEncVC failed (0x%x)", v4);
    goto LABEL_35;
  }
  _DbgPrintMessage(1, "AccessCheckForRailEncVC bypassed since we are running inside container");
LABEL_33:
  v4 = 0;
LABEL_34:
  _DbgPrintMessage(1, "AccessCheckForRailEncVC passed");
LABEL_35:
  if ( v1 )
    RpcRevertToSelf();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005ec90  push    rbp
0x18005ec92  push    rbx
0x18005ec93  push    rdi
0x18005ec94  push    r14
0x18005ec96  push    r15
0x18005ec98  mov     rbp, rsp
0x18005ec9b  sub     rsp, 60h
0x18005ec9f  xor     r15d, r15d
0x18005eca2  lea     r8, Value; "ContainerMode"
0x18005eca9  mov     r14d, ecx
0x18005ecac  mov     [rbp+TokenHandle], r15
0x18005ecb0  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18005ecb7  mov     [rbp+var_18], r15d
0x18005ecbb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005ecc2  mov     [rbp+TokenInformation], r15d
0x18005ecc6  lea     eax, [r15+4]
0x18005ecca  mov     [rbp+arg_8], r15d
0x18005ecce  mov     [rbp+TokenInformationLength], eax
0x18005ecd1  lea     r9d, [r15+10h]; dwFlags
0x18005ecd5  mov     [rbp+ReturnLength], eax
0x18005ecd8  mov     [rbp+var_14], eax
0x18005ecdb  lea     rax, [rbp+var_14]
0x18005ecdf  mov     [rsp+60h+pcbData], rax; pcbData
0x18005ece4  lea     rax, [rbp+arg_10]
0x18005ece8  mov     [rsp+60h+pvData], rax; pvData
0x18005eced  mov     [rsp+60h+pdwType], r15; pdwType
0x18005ecf2  mov     [rbp+arg_10], r15d
0x18005ecf6  call    cs:__imp_RegGetValueW
0x18005ecfd  nop     dword ptr [rax+rax+00h]
0x18005ed02  test    eax, eax
0x18005ed04  jnz     short loc_18005ED1B
0x18005ed06  cmp     [rbp+arg_10], r15d
0x18005ed0a  jz      short loc_18005ED1B
0x18005ed0c  lea     rdx, aAccesscheckfor_2; "AccessCheckForRailEncVC bypassed since "...
0x18005ed13  lea     ecx, [rax+1]
0x18005ed16  jmp     loc_18005EF0B
0x18005ed1b  xor     ecx, ecx; BindingHandle
0x18005ed1d  call    cs:__imp_RpcImpersonateClient
0x18005ed24  nop     dword ptr [rax+rax+00h]
0x18005ed29  test    eax, eax
0x18005ed2b  jz      short loc_18005ED4D
0x18005ed2d  mov     edi, 8
0x18005ed32  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x18005ed39  mov     ecx, edi; int
0x18005ed3b  mov     r8d, eax
0x18005ed3e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ed43  mov     ebx, 80070005h
0x18005ed48  jmp     loc_18005EEEE
0x18005ed4d  mov     r15d, 1
0x18005ed53  call    cs:__imp_GetCurrentThread
0x18005ed5a  nop     dword ptr [rax+rax+00h]
0x18005ed5f  lea     edi, [r15+7]
0x18005ed63  mov     r8d, r15d; OpenAsSelf
0x18005ed66  mov     rcx, rax; ThreadHandle
0x18005ed69  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005ed6d  mov     edx, edi; DesiredAccess
0x18005ed6f  call    cs:__imp_OpenThreadToken
0x18005ed76  nop     dword ptr [rax+rax+00h]
0x18005ed7b  test    eax, eax
0x18005ed7d  jnz     short loc_18005EDAD
0x18005ed7f  call    cs:__imp_GetLastError
0x18005ed86  nop     dword ptr [rax+rax+00h]
0x18005ed8b  mov     ebx, eax
0x18005ed8d  test    eax, eax
0x18005ed8f  jle     short loc_18005ED9A
0x18005ed91  movzx   ebx, ax
0x18005ed94  or      ebx, 80070000h
0x18005ed9a  test    ebx, ebx
0x18005ed9c  jns     short loc_18005EDAD
0x18005ed9e  mov     r8d, ebx
0x18005eda1  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed failed: 0x%x in "...
0x18005eda8  jmp     loc_18005EEE0
0x18005edad  mov     r9d, [rbp+ReturnLength]; TokenInformationLength
0x18005edb1  lea     rax, [rbp+ReturnLength]
0x18005edb5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005edb9  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18005edbd  mov     edx, 0Ch; TokenInformationClass
0x18005edc2  mov     [rsp+60h+pdwType], rax; ReturnLength
0x18005edc7  call    cs:__imp_GetTokenInformation
0x18005edce  nop     dword ptr [rax+rax+00h]
0x18005edd3  test    eax, eax
0x18005edd5  jnz     short loc_18005EE05
0x18005edd7  call    cs:__imp_GetLastError
0x18005edde  nop     dword ptr [rax+rax+00h]
0x18005ede3  mov     ebx, eax
0x18005ede5  test    eax, eax
0x18005ede7  jle     short loc_18005EDF2
0x18005ede9  movzx   ebx, ax
0x18005edec  or      ebx, 80070000h
0x18005edf2  test    ebx, ebx
0x18005edf4  jns     short loc_18005EE3C
0x18005edf6  mov     r8d, ebx
0x18005edf9  lea     rdx, aGettokeninform_2; "GetTokenInformation with TokenSessionId"...
0x18005ee00  jmp     loc_18005EEE0
0x18005ee05  mov     eax, [rbp+TokenInformation]
0x18005ee08  cmp     eax, r14d
0x18005ee0b  jz      short loc_18005EE3C
0x18005ee0d  mov     r8d, 80070005h
0x18005ee13  mov     dword ptr [rsp+60h+pvData], r14d
0x18005ee18  mov     ebx, r8d
0x18005ee1b  mov     dword ptr [rsp+60h+pdwType], eax
0x18005ee1f  mov     r9d, r8d
0x18005ee22  lea     rdx, aSFailed0xXAcce; "%s failed 0x%x: AccessCheckForRailEncVC"...
0x18005ee29  lea     r8, aAccesscheckfor_3; "AccessCheckForRailEncVC"
0x18005ee30  mov     ecx, edi; int
0x18005ee32  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ee37  jmp     loc_18005EEEE
0x18005ee3c  lea     rcx, [rbp+arg_8]
0x18005ee40  call    cs:__imp_CheckElevationEnabled
0x18005ee47  nop     dword ptr [rax+rax+00h]
0x18005ee4c  test    eax, eax
0x18005ee4e  jz      short loc_18005EE65
0x18005ee50  lea     rdx, aCheckelevation; "CheckElevationEnabled failed, set fLuaE"...
0x18005ee57  mov     ecx, edi; int
0x18005ee59  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ee5e  xor     eax, eax
0x18005ee60  mov     [rbp+arg_8], eax
0x18005ee63  jmp     short loc_18005EE68
0x18005ee65  mov     eax, [rbp+arg_8]
0x18005ee68  test    eax, eax
0x18005ee6a  jz      loc_18005EF01
0x18005ee70  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18005ee74  lea     rax, [rbp+TokenInformationLength]
0x18005ee78  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005ee7c  lea     r8, [rbp+var_18]; TokenInformation
0x18005ee80  mov     edx, 1Ah; TokenInformationClass
0x18005ee85  mov     [rsp+60h+pdwType], rax; ReturnLength
0x18005ee8a  call    cs:__imp_GetTokenInformation
0x18005ee91  nop     dword ptr [rax+rax+00h]
0x18005ee96  test    eax, eax
0x18005ee98  jnz     short loc_18005EECA
0x18005ee9a  call    cs:__imp_GetLastError
0x18005eea1  nop     dword ptr [rax+rax+00h]
0x18005eea6  test    eax, eax
0x18005eea8  jle     short loc_18005EEB4
0x18005eeaa  movzx   eax, ax
0x18005eead  or      eax, 80070000h
0x18005eeb2  test    eax, eax
0x18005eeb4  mov     ebx, eax
0x18005eeb6  jns     short loc_18005EEC4
0x18005eeb8  mov     r8d, eax
0x18005eebb  lea     rdx, aGettokeninform_1; "GetTokenInformation with TokenUIAccess "...
0x18005eec2  jmp     short loc_18005EEE0
0x18005eec4  test    eax, eax
0x18005eec6  jnz     short loc_18005EEEE
0x18005eec8  jmp     short loc_18005EF12
0x18005eeca  cmp     [rbp+var_18], 0
0x18005eece  jnz     short loc_18005EF10
0x18005eed0  mov     r8d, 80070005h
0x18005eed6  lea     rdx, aAccesscheckfor_4; "AccessCheckForRailEncVC failed! dwUIAcc"...
0x18005eedd  mov     ebx, r8d
0x18005eee0  lea     r9, aAccesscheckfor_3; "AccessCheckForRailEncVC"
0x18005eee7  mov     ecx, edi; int
0x18005eee9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005eeee  mov     r8d, ebx
0x18005eef1  lea     rdx, aAccesscheckfor_1; "AccessCheckForRailEncVC failed (0x%x)"
0x18005eef8  mov     ecx, edi; int
0x18005eefa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005eeff  jmp     short loc_18005EF23
0x18005ef01  lea     rdx, aUacDisabledByp; "UAC disabled, bypassing the UIAccess ch"...
0x18005ef08  mov     ecx, r15d; int
0x18005ef0b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ef10  xor     ebx, ebx
0x18005ef12  lea     rdx, aAccesscheckfor_0; "AccessCheckForRailEncVC passed"
0x18005ef19  mov     ecx, 1; int
0x18005ef1e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ef23  test    r15d, r15d
0x18005ef26  jz      short loc_18005EF34
0x18005ef28  call    cs:__imp_RpcRevertToSelf
0x18005ef2f  nop     dword ptr [rax+rax+00h]
0x18005ef34  mov     rcx, [rbp+TokenHandle]; hObject
0x18005ef38  test    rcx, rcx
0x18005ef3b  jz      short loc_18005EF49
0x18005ef3d  call    cs:__imp_CloseHandle
0x18005ef44  nop     dword ptr [rax+rax+00h]
0x18005ef49  mov     eax, ebx
0x18005ef4b  add     rsp, 60h
0x18005ef4f  pop     r15
0x18005ef51  pop     r14
0x18005ef53  pop     rdi
0x18005ef54  pop     rbx
0x18005ef55  pop     rbp
0x18005ef56  retn
```
