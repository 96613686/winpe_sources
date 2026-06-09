# AccessCheckForRailEncVC(ulong)

- ea: `0x18005bebc`
- end: `0x18005c13b`
- name: `?AccessCheckForRailEncVC@@YAJK@Z`
- size: `639`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005d970`

## callees

- `0x18000a210`
- `0x18005bebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bf93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bfdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bf93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bfdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005bf73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005bf73`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005bf89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005bf89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c127`
- `RPCRT4!RpcRevertToSelf` at `0x18005c118`
- `RPCRT4!RpcRevertToSelf` at `0x18005c118`
- `RPCRT4!RpcImpersonateClient` at `0x18005bf43`
- `RPCRT4!RpcImpersonateClient` at `0x18005bf43`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005bf22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005bf22`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005bfd5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c086`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005bfd5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c086`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18005c042`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18005c042`

## string_xrefs

- `0x18005bf52`: `Cannot impersonate client: %d`
- `0x18005bf32`: `AccessCheckForRailEncVC bypassed since we are running inside container`
- `0x18005c02b`: `AccessCheckForRailEncVC`
- `0x18005c0d0`: `AccessCheckForRailEncVC`
- `0x18005bfaf`: `OpenThreadToken failed failed: 0x%x in %s`
- `0x18005bffb`: `GetTokenInformation with TokenSessionId failed failed: 0x%x in %s`
- `0x18005c024`: `%s failed 0x%x: AccessCheckForRailEncVC failed! CallerSessionId(%u) != SessionIdOfVC(%u)`
- `0x18005c0ab`: `GetTokenInformation with TokenUIAccess failed failed: 0x%x in %s`
- `0x18005c0c6`: `AccessCheckForRailEncVC failed! dwUIAccess == 0 failed: 0x%x in %s`
- `0x18005c0f1`: `UAC disabled, bypassing the UIAccess check in AccessCheckForRailEncVC`
- `0x18005c102`: `AccessCheckForRailEncVC passed`
- `0x18005c0e1`: `AccessCheckForRailEncVC failed (0x%x)`

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
0x18005bebc  push    rbp
0x18005bebe  push    rbx
0x18005bebf  push    rdi
0x18005bec0  push    r14
0x18005bec2  push    r15
0x18005bec4  mov     rbp, rsp
0x18005bec7  sub     rsp, 60h
0x18005becb  xor     r15d, r15d
0x18005bece  lea     r8, Value; "ContainerMode"
0x18005bed5  mov     r14d, ecx
0x18005bed8  mov     [rbp+TokenHandle], r15
0x18005bedc  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18005bee3  mov     [rbp+var_18], r15d
0x18005bee7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005beee  mov     [rbp+TokenInformation], r15d
0x18005bef2  lea     eax, [r15+4]
0x18005bef6  mov     [rbp+arg_8], r15d
0x18005befa  mov     [rbp+TokenInformationLength], eax
0x18005befd  lea     r9d, [r15+10h]; dwFlags
0x18005bf01  mov     [rbp+ReturnLength], eax
0x18005bf04  mov     [rbp+var_14], eax
0x18005bf07  lea     rax, [rbp+var_14]
0x18005bf0b  mov     [rsp+60h+pcbData], rax; pcbData
0x18005bf10  lea     rax, [rbp+arg_10]
0x18005bf14  mov     [rsp+60h+pvData], rax; pvData
0x18005bf19  mov     [rsp+60h+pdwType], r15; pdwType
0x18005bf1e  mov     [rbp+arg_10], r15d
0x18005bf22  call    cs:__imp_RegGetValueW
0x18005bf28  test    eax, eax
0x18005bf2a  jnz     short loc_18005BF41
0x18005bf2c  cmp     [rbp+arg_10], r15d
0x18005bf30  jz      short loc_18005BF41
0x18005bf32  lea     rdx, aAccesscheckfor_2; "AccessCheckForRailEncVC bypassed since "...
0x18005bf39  lea     ecx, [rax+1]
0x18005bf3c  jmp     loc_18005C0FB
0x18005bf41  xor     ecx, ecx; BindingHandle
0x18005bf43  call    cs:__imp_RpcImpersonateClient
0x18005bf49  test    eax, eax
0x18005bf4b  jz      short loc_18005BF6D
0x18005bf4d  mov     edi, 8
0x18005bf52  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x18005bf59  mov     ecx, edi; int
0x18005bf5b  mov     r8d, eax
0x18005bf5e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005bf63  mov     ebx, 80070005h
0x18005bf68  jmp     loc_18005C0DE
0x18005bf6d  mov     r15d, 1
0x18005bf73  call    cs:__imp_GetCurrentThread
0x18005bf79  lea     edi, [r15+7]
0x18005bf7d  mov     r8d, r15d; OpenAsSelf
0x18005bf80  mov     rcx, rax; ThreadHandle
0x18005bf83  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005bf87  mov     edx, edi; DesiredAccess
0x18005bf89  call    cs:__imp_OpenThreadToken
0x18005bf8f  test    eax, eax
0x18005bf91  jnz     short loc_18005BFBB
0x18005bf93  call    cs:__imp_GetLastError
0x18005bf99  mov     ebx, eax
0x18005bf9b  test    eax, eax
0x18005bf9d  jle     short loc_18005BFA8
0x18005bf9f  movzx   ebx, ax
0x18005bfa2  or      ebx, 80070000h
0x18005bfa8  test    ebx, ebx
0x18005bfaa  jns     short loc_18005BFBB
0x18005bfac  mov     r8d, ebx
0x18005bfaf  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed failed: 0x%x in "...
0x18005bfb6  jmp     loc_18005C0D0
0x18005bfbb  mov     r9d, [rbp+ReturnLength]; TokenInformationLength
0x18005bfbf  lea     rax, [rbp+ReturnLength]
0x18005bfc3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005bfc7  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18005bfcb  mov     edx, 0Ch; TokenInformationClass
0x18005bfd0  mov     [rsp+60h+pdwType], rax; ReturnLength
0x18005bfd5  call    cs:__imp_GetTokenInformation
0x18005bfdb  test    eax, eax
0x18005bfdd  jnz     short loc_18005C007
0x18005bfdf  call    cs:__imp_GetLastError
0x18005bfe5  mov     ebx, eax
0x18005bfe7  test    eax, eax
0x18005bfe9  jle     short loc_18005BFF4
0x18005bfeb  movzx   ebx, ax
0x18005bfee  or      ebx, 80070000h
0x18005bff4  test    ebx, ebx
0x18005bff6  jns     short loc_18005C03E
0x18005bff8  mov     r8d, ebx
0x18005bffb  lea     rdx, aGettokeninform_2; "GetTokenInformation with TokenSessionId"...
0x18005c002  jmp     loc_18005C0D0
0x18005c007  mov     eax, [rbp+TokenInformation]
0x18005c00a  cmp     eax, r14d
0x18005c00d  jz      short loc_18005C03E
0x18005c00f  mov     r8d, 80070005h
0x18005c015  mov     dword ptr [rsp+60h+pvData], r14d
0x18005c01a  mov     ebx, r8d
0x18005c01d  mov     dword ptr [rsp+60h+pdwType], eax
0x18005c021  mov     r9d, r8d
0x18005c024  lea     rdx, aSFailed0xXAcce; "%s failed 0x%x: AccessCheckForRailEncVC"...
0x18005c02b  lea     r8, aAccesscheckfor_3; "AccessCheckForRailEncVC"
0x18005c032  mov     ecx, edi; int
0x18005c034  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005c039  jmp     loc_18005C0DE
0x18005c03e  lea     rcx, [rbp+arg_8]
0x18005c042  call    cs:__imp_CheckElevationEnabled
0x18005c048  test    eax, eax
0x18005c04a  jz      short loc_18005C061
0x18005c04c  lea     rdx, aCheckelevation; "CheckElevationEnabled failed, set fLuaE"...
0x18005c053  mov     ecx, edi; int
0x18005c055  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005c05a  xor     eax, eax
0x18005c05c  mov     [rbp+arg_8], eax
0x18005c05f  jmp     short loc_18005C064
0x18005c061  mov     eax, [rbp+arg_8]
0x18005c064  test    eax, eax
0x18005c066  jz      loc_18005C0F1
0x18005c06c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18005c070  lea     rax, [rbp+TokenInformationLength]
0x18005c074  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005c078  lea     r8, [rbp+var_18]; TokenInformation
0x18005c07c  mov     edx, 1Ah; TokenInformationClass
0x18005c081  mov     [rsp+60h+pdwType], rax; ReturnLength
0x18005c086  call    cs:__imp_GetTokenInformation
0x18005c08c  test    eax, eax
0x18005c08e  jnz     short loc_18005C0BA
0x18005c090  call    cs:__imp_GetLastError
0x18005c096  test    eax, eax
0x18005c098  jle     short loc_18005C0A4
0x18005c09a  movzx   eax, ax
0x18005c09d  or      eax, 80070000h
0x18005c0a2  test    eax, eax
0x18005c0a4  mov     ebx, eax
0x18005c0a6  jns     short loc_18005C0B4
0x18005c0a8  mov     r8d, eax
0x18005c0ab  lea     rdx, aGettokeninform_1; "GetTokenInformation with TokenUIAccess "...
0x18005c0b2  jmp     short loc_18005C0D0
0x18005c0b4  test    eax, eax
0x18005c0b6  jnz     short loc_18005C0DE
0x18005c0b8  jmp     short loc_18005C102
0x18005c0ba  cmp     [rbp+var_18], 0
0x18005c0be  jnz     short loc_18005C100
0x18005c0c0  mov     r8d, 80070005h
0x18005c0c6  lea     rdx, aAccesscheckfor_4; "AccessCheckForRailEncVC failed! dwUIAcc"...
0x18005c0cd  mov     ebx, r8d
0x18005c0d0  lea     r9, aAccesscheckfor_3; "AccessCheckForRailEncVC"
0x18005c0d7  mov     ecx, edi; int
0x18005c0d9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005c0de  mov     r8d, ebx
0x18005c0e1  lea     rdx, aAccesscheckfor_1; "AccessCheckForRailEncVC failed (0x%x)"
0x18005c0e8  mov     ecx, edi; int
0x18005c0ea  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005c0ef  jmp     short loc_18005C113
0x18005c0f1  lea     rdx, aUacDisabledByp; "UAC disabled, bypassing the UIAccess ch"...
0x18005c0f8  mov     ecx, r15d; int
0x18005c0fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005c100  xor     ebx, ebx
0x18005c102  lea     rdx, aAccesscheckfor_0; "AccessCheckForRailEncVC passed"
0x18005c109  mov     ecx, 1; int
0x18005c10e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005c113  test    r15d, r15d
0x18005c116  jz      short loc_18005C11E
0x18005c118  call    cs:__imp_RpcRevertToSelf
0x18005c11e  mov     rcx, [rbp+TokenHandle]; hObject
0x18005c122  test    rcx, rcx
0x18005c125  jz      short loc_18005C12D
0x18005c127  call    cs:__imp_CloseHandle
0x18005c12d  mov     eax, ebx
0x18005c12f  add     rsp, 60h
0x18005c133  pop     r15
0x18005c135  pop     r14
0x18005c137  pop     rdi
0x18005c138  pop     rbx
0x18005c139  pop     rbp
0x18005c13a  retn
```
