# CUVHDProfileTelemetryLogging::GetRoleStatus(ulong *,ulong *)

- ea: `0x180002bb0`
- end: `0x180002d92`
- name: `?GetRoleStatus@CUVHDProfileTelemetryLogging@@CAJPEAK0@Z`
- size: `482`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004620`
- `0x1800337b0`

## callees

- `0x180002bb0`
- `0x180003f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002bf6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002bf6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002c5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ca0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002c5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ca0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d7d`

## string_xrefs

- `0x180002c19`: `RegOpenKeyEx REG_CONTROL_TSERVER failed failed: 0x%x in %s`
- `0x180002c99`: `TSAppCompat`
- `0x180002c58`: `SessionDirectoryActive`
- `0x180002cc3`: `RegQueryValueEx REG_TERMSRV_APPCOMPAT failed failed: 0x%x in %s`
- `0x180002d4a`: `REG_TERMSRV_APPCOMPAT not REG_DWORD failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUVHDProfileTelemetryLogging::GetRoleStatus(unsigned int *a1, unsigned int *a2)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-28h] BYREF
  BYTE v10[4]; // [rsp+34h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v10 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    _DbgPrintMessage(
      8,
      "RegOpenKeyEx REG_CONTROL_TSERVER failed failed: 0x%x in %s",
      v5,
      "CUVHDProfileTelemetryLogging::GetRoleStatus");
    goto LABEL_23;
  }
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"SessionDirectoryActive", 0, &Type, Data, &cbData);
  v5 = v6;
  if ( v6 == 2 )
  {
    *(_DWORD *)Data = 0;
  }
  else
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RegQueryValueEx REG_TS_SESSDIRACTIVE failed failed: 0x%x in %s",
        v5,
        "CUVHDProfileTelemetryLogging::GetRoleStatus");
      goto LABEL_23;
    }
    if ( Type != 4 )
    {
      v5 = -2147024809;
      _DbgPrintMessage(
        8,
        "REG_TS_SESSDIRACTIVE not REG_DWORD failed: 0x%x in %s",
        -2147024809,
        "CUVHDProfileTelemetryLogging::GetRoleStatus");
      goto LABEL_23;
    }
  }
  cbData = 4;
  v7 = RegQueryValueExW(hKey, L"TSAppCompat", 0, &Type, v10, &cbData);
  v5 = v7;
  if ( v7 > 0 )
    v5 = (unsigned __int16)v7 | 0x80070000;
  if ( v5 >= 0 )
  {
    if ( Type == 4 )
    {
      if ( a1 )
        *a1 = *(_DWORD *)Data;
      if ( a2 )
        *a2 = *(_DWORD *)v10;
    }
    else
    {
      v5 = -2147024809;
      _DbgPrintMessage(
        8,
        "REG_TERMSRV_APPCOMPAT not REG_DWORD failed: 0x%x in %s",
        -2147024809,
        "CUVHDProfileTelemetryLogging::GetRoleStatus");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "RegQueryValueEx REG_TERMSRV_APPCOMPAT failed failed: 0x%x in %s",
      v5,
      "CUVHDProfileTelemetryLogging::GetRoleStatus");
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002bb0  mov     rax, rsp
0x180002bb3  mov     [rax+8], rbx
0x180002bb7  push    rbp
0x180002bb8  push    rsi
0x180002bb9  push    rdi
0x180002bba  sub     rsp, 40h
0x180002bbe  xor     ebp, ebp
0x180002bc0  mov     rdi, rdx
0x180002bc3  mov     [rax-20h], rbp
0x180002bc7  mov     rsi, rcx
0x180002bca  mov     [rax+20h], ebp
0x180002bcd  mov     r9d, 20019h; samDesired
0x180002bd3  mov     [rax+18h], ebp
0x180002bd6  xor     r8d, r8d; ulOptions
0x180002bd9  mov     [rax-28h], ebp
0x180002bdc  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180002be3  mov     [rax-24h], ebp
0x180002be6  lea     rax, [rax-20h]
0x180002bea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002bf1  mov     [rsp+58h+phkResult], rax; phkResult
0x180002bf6  call    cs:__imp_RegOpenKeyExW
0x180002bfc  mov     ebx, eax
0x180002bfe  test    eax, eax
0x180002c00  jle     short loc_180002C0B
0x180002c02  movzx   ebx, ax
0x180002c05  or      ebx, 80070000h
0x180002c0b  test    ebx, ebx
0x180002c0d  jns     short loc_180002C2F
0x180002c0f  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x180002c16  mov     r8d, ebx
0x180002c19  lea     rdx, aRegopenkeyexRe_0; "RegOpenKeyEx REG_CONTROL_TSERVER failed"...
0x180002c20  mov     ecx, 8; int
0x180002c25  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002c2a  jmp     loc_180002D73
0x180002c2f  mov     rcx, [rsp+58h+hKey]; hKey
0x180002c34  lea     rax, [rsp+58h+cbData]
0x180002c39  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180002c3e  lea     r9, [rsp+58h+Type]; lpType
0x180002c43  lea     rax, [rsp+58h+Data]
0x180002c48  mov     [rsp+58h+cbData], 4
0x180002c50  xor     r8d, r8d; lpReserved
0x180002c53  mov     [rsp+58h+phkResult], rax; lpData
0x180002c58  lea     rdx, aSessiondirecto; "SessionDirectoryActive"
0x180002c5f  call    cs:__imp_RegQueryValueExW
0x180002c65  mov     ebx, eax
0x180002c67  cmp     eax, 2
0x180002c6a  jnz     short loc_180002CD9
0x180002c6c  mov     dword ptr [rsp+58h+Data], ebp
0x180002c70  mov     rcx, [rsp+58h+hKey]; hKey
0x180002c75  lea     rax, [rsp+58h+cbData]
0x180002c7a  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180002c7f  lea     r9, [rsp+58h+Type]; lpType
0x180002c84  lea     rax, [rsp+58h+var_24]
0x180002c89  mov     [rsp+58h+cbData], 4
0x180002c91  xor     r8d, r8d; lpReserved
0x180002c94  mov     [rsp+58h+phkResult], rax; lpData
0x180002c99  lea     rdx, aTsappcompat; "TSAppCompat"
0x180002ca0  call    cs:__imp_RegQueryValueExW
0x180002ca6  mov     ebx, eax
0x180002ca8  test    eax, eax
0x180002caa  jle     short loc_180002CB5
0x180002cac  movzx   ebx, ax
0x180002caf  or      ebx, 80070000h
0x180002cb5  test    ebx, ebx
0x180002cb7  jns     short loc_180002D34
0x180002cb9  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x180002cc0  mov     r8d, ebx
0x180002cc3  lea     rdx, aRegqueryvaluee_1; "RegQueryValueEx REG_TERMSRV_APPCOMPAT f"...
0x180002cca  mov     ecx, 8; int
0x180002ccf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002cd4  jmp     loc_180002D73
0x180002cd9  test    eax, eax
0x180002cdb  jle     short loc_180002CE6
0x180002cdd  movzx   ebx, ax
0x180002ce0  or      ebx, 80070000h
0x180002ce6  test    ebx, ebx
0x180002ce8  jns     short loc_180002D07
0x180002cea  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x180002cf1  mov     r8d, ebx
0x180002cf4  lea     rdx, aRegqueryvaluee_10; "RegQueryValueEx REG_TS_SESSDIRACTIVE fa"...
0x180002cfb  mov     ecx, 8; int
0x180002d00  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002d05  jmp     short loc_180002D73
0x180002d07  cmp     [rsp+58h+Type], 4
0x180002d0c  jz      loc_180002C70
0x180002d12  mov     ebx, 80070057h
0x180002d17  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x180002d1e  mov     r8d, ebx
0x180002d21  lea     rdx, aRegTsSessdirac; "REG_TS_SESSDIRACTIVE not REG_DWORD fail"...
0x180002d28  mov     ecx, 8; int
0x180002d2d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002d32  jmp     short loc_180002D73
0x180002d34  cmp     [rsp+58h+Type], 4
0x180002d39  jz      short loc_180002D5D
0x180002d3b  mov     ebx, 80070057h
0x180002d40  lea     r9, aCuvhdprofilete_2; "CUVHDProfileTelemetryLogging::GetRoleSt"...
0x180002d47  mov     r8d, ebx
0x180002d4a  lea     rdx, aRegTermsrvAppc; "REG_TERMSRV_APPCOMPAT not REG_DWORD fai"...
0x180002d51  mov     ecx, 8; int
0x180002d56  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002d5b  jmp     short loc_180002D73
0x180002d5d  test    rsi, rsi
0x180002d60  jz      short loc_180002D68
0x180002d62  mov     eax, dword ptr [rsp+58h+Data]
0x180002d66  mov     [rsi], eax
0x180002d68  test    rdi, rdi
0x180002d6b  jz      short loc_180002D73
0x180002d6d  mov     eax, dword ptr [rsp+58h+var_24]
0x180002d71  mov     [rdi], eax
0x180002d73  mov     rcx, [rsp+58h+hKey]; hKey
0x180002d78  test    rcx, rcx
0x180002d7b  jz      short loc_180002D83
0x180002d7d  call    cs:__imp_RegCloseKey
0x180002d83  mov     eax, ebx
0x180002d85  mov     rbx, [rsp+58h+arg_0]
0x180002d8a  add     rsp, 40h
0x180002d8e  pop     rdi
0x180002d8f  pop     rsi
0x180002d90  pop     rbp
0x180002d91  retn
```
