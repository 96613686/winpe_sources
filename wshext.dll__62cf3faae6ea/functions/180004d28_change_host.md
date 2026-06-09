# change_host

- ea: `0x180004d28`
- end: `0x180004f45`
- name: `change_host`
- size: `541`
- prototype: `__int64 __fastcall(char *String2, char *, char *, char *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000494c`

## callees

- `0x1800038f8`
- `0x180004c50`
- `0x180004d28`
- `0x18000d1c0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180004ec0`
- `msvcrt!_stricmp` at `0x180004ec0`
- `ADVAPI32!RegOpenKeyExA` at `0x180004da6`
- `ADVAPI32!RegOpenKeyExA` at `0x180004e72`
- `ADVAPI32!RegOpenKeyExA` at `0x180004e9f`
- `ADVAPI32!RegOpenKeyExA` at `0x180004da6`
- `ADVAPI32!RegOpenKeyExA` at `0x180004e72`
- `ADVAPI32!RegOpenKeyExA` at `0x180004e9f`
- `ADVAPI32!RegQueryValueExA` at `0x180004e09`
- `ADVAPI32!RegQueryValueExA` at `0x180004e09`
- `ADVAPI32!RegCloseKey` at `0x180004e16`
- `ADVAPI32!RegCloseKey` at `0x180004eac`
- `ADVAPI32!RegCloseKey` at `0x180004f32`
- `ADVAPI32!RegCloseKey` at `0x180004e16`
- `ADVAPI32!RegCloseKey` at `0x180004eac`
- `ADVAPI32!RegCloseKey` at `0x180004f32`

## string_xrefs

- `0x180004eed`: `Shell\Open\Command`
- `0x180004ed9`: `Shell\Open`
- `0x180004f04`: `Shell\Open2`
- `0x180004f1b`: `Shell\Open2\Command`

## pseudocode

```c
LSTATUS __fastcall change_host(char *String2, char *a2, char *a3, char *a4, char *a5)
{
  LSTATUS result; // eax
  bool v10; // cc
  LSTATUS v11; // ebx
  __int64 v12; // rax
  LSTATUS v13; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v17; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v17 = 0;
  hKey = 0;
  phkResult = 0;
  cbData = 0;
  result = RegOpenKeyExA(HKEY_CLASSES_ROOT, String2, 0, 0x20019u, &hKey);
  v10 = result <= 0;
  if ( result )
  {
LABEL_2:
    if ( !v10 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  cbData = 1024;
  v11 = RegQueryValueExA(hKey, ValueName, 0, 0, Data, &cbData);
  RegCloseKey(hKey);
  if ( v11 )
  {
    if ( v11 > 0 )
      return (unsigned __int16)v11 | 0x80070000;
    return v11;
  }
  else
  {
    if ( !cbData )
      return -2147467259;
    v12 = cbData - 1;
    if ( (unsigned int)v12 >= 0x400 )
      _report_rangecheckfailure();
    Data[v12] = 0;
    result = RegOpenKeyExA(HKEY_CLASSES_ROOT, (LPCSTR)Data, 0, 0x2001Fu, &phkResult);
    v10 = result <= 0;
    if ( result )
      goto LABEL_2;
    v13 = RegOpenKeyExA(phkResult, "ScriptEngine", 0, 0x20006u, &v17);
    RegCloseKey(v17);
    if ( !v13 || !_stricmp(".wsf", String2) )
    {
      TaRegSetEXPAND_SZ(phkResult, "Shell\\Open", ValueName, a2);
      TaRegSetEXPAND_SZ(phkResult, "Shell\\Open\\Command", ValueName, a3);
      TaRegSetEXPAND_SZ(phkResult, "Shell\\Open2", ValueName, a4);
      TaRegSetEXPAND_SZ(phkResult, "Shell\\Open2\\Command", ValueName, a5);
    }
    RegCloseKey(phkResult);
    return 0;
  }
}

```

## disassembly

```asm
0x180004d28  push    rbp
0x180004d2a  push    rbx
0x180004d2b  push    rsi
0x180004d2c  push    rdi
0x180004d2d  push    r12
0x180004d2f  push    r14
0x180004d31  push    r15
0x180004d33  lea     rbp, [rsp-360h]
0x180004d3b  sub     rsp, 460h
0x180004d42  mov     rax, cs:__security_cookie
0x180004d49  xor     rax, rsp
0x180004d4c  mov     [rbp+390h+var_40], rax
0x180004d53  mov     r12, [rbp+390h+arg_20]
0x180004d5a  lea     rax, [rsp+490h+hKey]
0x180004d5f  mov     rsi, rdx
0x180004d62  mov     [rsp+490h+var_448], 0
0x180004d6b  mov     rdx, rcx; lpSubKey
0x180004d6e  mov     [rsp+490h+hKey], 0
0x180004d77  mov     r15, r9
0x180004d7a  mov     [rsp+490h+var_458], 0
0x180004d83  mov     r14, r8
0x180004d86  mov     [rsp+490h+cbData], 0
0x180004d8e  mov     rdi, rcx
0x180004d91  mov     [rsp+490h+phkResult], rax; phkResult
0x180004d96  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004d9d  mov     r9d, 20019h; samDesired
0x180004da3  xor     r8d, r8d; ulOptions
0x180004da6  call    cs:__imp_RegOpenKeyExA
0x180004dac  test    eax, eax
0x180004dae  jz      short loc_180004DDB
0x180004db0  jle     short loc_180004DBA
0x180004db2  movzx   eax, ax
0x180004db5  or      eax, 80070000h
0x180004dba  mov     rcx, [rbp+390h+var_40]
0x180004dc1  xor     rcx, rsp; StackCookie
0x180004dc4  call    __security_check_cookie
0x180004dc9  add     rsp, 460h
0x180004dd0  pop     r15
0x180004dd2  pop     r14
0x180004dd4  pop     r12
0x180004dd6  pop     rdi
0x180004dd7  pop     rsi
0x180004dd8  pop     rbx
0x180004dd9  pop     rbp
0x180004dda  retn
0x180004ddb  mov     rcx, [rsp+490h+hKey]; hKey
0x180004de0  lea     rax, [rsp+490h+cbData]
0x180004de5  mov     [rsp+490h+lpcbData], rax; lpcbData
0x180004dea  lea     rdx, ValueName; lpValueName
0x180004df1  lea     rax, [rsp+490h+Data]
0x180004df6  mov     [rsp+490h+cbData], 400h
0x180004dfe  xor     r9d, r9d; lpType
0x180004e01  mov     [rsp+490h+phkResult], rax; lpData
0x180004e06  xor     r8d, r8d; lpReserved
0x180004e09  call    cs:__imp_RegQueryValueExA
0x180004e0f  mov     rcx, [rsp+490h+hKey]; hKey
0x180004e14  mov     ebx, eax
0x180004e16  call    cs:__imp_RegCloseKey
0x180004e1c  test    ebx, ebx
0x180004e1e  jz      short loc_180004E2F
0x180004e20  jle     short loc_180004E2B
0x180004e22  movzx   ebx, bx
0x180004e25  or      ebx, 80070000h
0x180004e2b  mov     eax, ebx
0x180004e2d  jmp     short loc_180004DBA
0x180004e2f  mov     eax, [rsp+490h+cbData]
0x180004e33  test    eax, eax
0x180004e35  jnz     short loc_180004E41
0x180004e37  mov     eax, 80004005h
0x180004e3c  jmp     loc_180004DBA
0x180004e41  dec     eax
0x180004e43  cmp     eax, 400h
0x180004e48  jnb     loc_180004F3F
0x180004e4e  mov     [rsp+rax+490h+Data], 0
0x180004e53  lea     rdx, [rsp+490h+Data]; lpSubKey
0x180004e58  lea     rax, [rsp+490h+var_458]
0x180004e5d  mov     r9d, 2001Fh; samDesired
0x180004e63  xor     r8d, r8d; ulOptions
0x180004e66  mov     [rsp+490h+phkResult], rax; phkResult
0x180004e6b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004e72  call    cs:__imp_RegOpenKeyExA
0x180004e78  test    eax, eax
0x180004e7a  jnz     loc_180004DB0
0x180004e80  mov     rcx, [rsp+490h+var_458]; hKey
0x180004e85  lea     rax, [rsp+490h+var_448]
0x180004e8a  mov     r9d, 20006h; samDesired
0x180004e90  mov     [rsp+490h+phkResult], rax; phkResult
0x180004e95  xor     r8d, r8d; ulOptions
0x180004e98  lea     rdx, SubKey; "ScriptEngine"
0x180004e9f  call    cs:__imp_RegOpenKeyExA
0x180004ea5  mov     rcx, [rsp+490h+var_448]; hKey
0x180004eaa  mov     ebx, eax
0x180004eac  call    cs:__imp_RegCloseKey
0x180004eb2  test    ebx, ebx
0x180004eb4  jz      short loc_180004ECA
0x180004eb6  mov     rdx, rdi; String2
0x180004eb9  lea     rcx, aWsf_1; ".wsf"
0x180004ec0  call    cs:__imp__stricmp
0x180004ec6  test    eax, eax
0x180004ec8  jnz     short loc_180004F2D
0x180004eca  mov     rcx, [rsp+490h+var_458]; HKEY
0x180004ecf  lea     rbx, ValueName
0x180004ed6  mov     r8, rbx; char *
0x180004ed9  lea     rdx, aShellOpen; "Shell\\Open"
0x180004ee0  mov     r9, rsi; char *
0x180004ee3  call    ?TaRegSetEXPAND_SZ@@YAJPEAUHKEY__@@PEBD11@Z; TaRegSetEXPAND_SZ(HKEY__ *,char const *,char const *,char const *)
0x180004ee8  mov     rcx, [rsp+490h+var_458]; HKEY
0x180004eed  lea     rdx, aShellOpenComma; "Shell\\Open\\Command"
0x180004ef4  mov     r9, r14; char *
0x180004ef7  mov     r8, rbx; char *
0x180004efa  call    ?TaRegSetEXPAND_SZ@@YAJPEAUHKEY__@@PEBD11@Z; TaRegSetEXPAND_SZ(HKEY__ *,char const *,char const *,char const *)
0x180004eff  mov     rcx, [rsp+490h+var_458]; HKEY
0x180004f04  lea     rdx, aShellOpen2; "Shell\\Open2"
0x180004f0b  mov     r9, r15; char *
0x180004f0e  mov     r8, rbx; char *
0x180004f11  call    ?TaRegSetEXPAND_SZ@@YAJPEAUHKEY__@@PEBD11@Z; TaRegSetEXPAND_SZ(HKEY__ *,char const *,char const *,char const *)
0x180004f16  mov     rcx, [rsp+490h+var_458]; HKEY
0x180004f1b  lea     rdx, aShellOpen2Comm; "Shell\\Open2\\Command"
0x180004f22  mov     r9, r12; char *
0x180004f25  mov     r8, rbx; char *
0x180004f28  call    ?TaRegSetEXPAND_SZ@@YAJPEAUHKEY__@@PEBD11@Z; TaRegSetEXPAND_SZ(HKEY__ *,char const *,char const *,char const *)
0x180004f2d  mov     rcx, [rsp+490h+var_458]; hKey
0x180004f32  call    cs:__imp_RegCloseKey
0x180004f38  xor     eax, eax
0x180004f3a  jmp     loc_180004DBA
0x180004f3f  call    __report_rangecheckfailure
```
