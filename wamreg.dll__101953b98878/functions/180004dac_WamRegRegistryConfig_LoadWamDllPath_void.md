# WamRegRegistryConfig::LoadWamDllPath(void)

- ea: `0x180004dac`
- end: `0x180004fcd`
- name: `?LoadWamDllPath@WamRegRegistryConfig@@QEAAJXZ`
- size: `545`
- prototype: `__int64 __fastcall(WamRegRegistryConfig *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004540`

## callees

- `0x180004dac`
- `0x180006850`

## import_xrefs

- `msvcrt!strncpy_s` at `0x180004e8a`
- `msvcrt!strncpy_s` at `0x180004e8a`
- `msvcrt!strncat_s` at `0x180004ed7`
- `msvcrt!strncat_s` at `0x180004ed7`
- `ADVAPI32!RegCloseKey` at `0x180004f9b`
- `ADVAPI32!RegCloseKey` at `0x180004f9b`
- `ADVAPI32!RegQueryValueExA` at `0x180004e59`
- `ADVAPI32!RegQueryValueExA` at `0x180004e59`
- `ADVAPI32!RegOpenKeyExA` at `0x180004dfd`
- `ADVAPI32!RegOpenKeyExA` at `0x180004dfd`
- `KERNEL32!GetLastError` at `0x180004eeb`
- `KERNEL32!GetLastError` at `0x180004eeb`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180004eaf`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180004eaf`
- `iisutil!PuDbgPrint` at `0x180004f42`
- `iisutil!PuDbgPrint` at `0x180004f83`
- `iisutil!PuDbgPrint` at `0x180004f42`
- `iisutil!PuDbgPrint` at `0x180004f83`

## string_xrefs

- `0x180004e0d`: `\wam.dll`
- `0x180004e1f`: `InstallPath`
- `0x180004f1d`: `WamRegRegistryConfig::LoadWamDllPath`
- `0x180004f5f`: `WamRegRegistryConfig::LoadWamDllPath`
- `0x180004f71`: `Wrong Type for InstallPath registry key.dwType = %d\n`

## pseudocode

```c
__int64 __fastcall WamRegRegistryConfig::LoadWamDllPath(WamRegRegistryConfig *this)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  DWORD v4; // eax
  signed int LastError; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  char Source[16]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[272]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  WamRegRegistryConfig::m_szWamDllPath = 0;
  v1 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\InetStp", 0, 0x20019u, &hKey);
  v2 = v1;
  if ( !v1 )
  {
    Type = 0;
    strcpy(Source, "\\wam.dll");
    cbData = 251;
    v3 = RegQueryValueExA(hKey, "InstallPath", 0, &Type, Data, &cbData);
    v2 = v3;
    if ( v3 )
    {
      if ( v3 > 0 )
        v2 = (unsigned __int16)v3 | 0x80070000;
      goto LABEL_18;
    }
    if ( Type == 1 )
    {
      strncpy_s(&WamRegRegistryConfig::m_szWamDllPath, 0x104u, (const char *)Data, cbData);
LABEL_8:
      strncat_s(&WamRegRegistryConfig::m_szWamDllPath, 0x104u, Source, 9u);
      v2 = 0;
LABEL_18:
      RegCloseKey(hKey);
      return v2;
    }
    if ( Type != 2 )
    {
      v2 = -2147418113;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
          790,
          "WamRegRegistryConfig::LoadWamDllPath",
          "Wrong Type for InstallPath registry key.dwType = %d\n",
          Type);
      goto LABEL_18;
    }
    v4 = ExpandEnvironmentStringsA((LPCSTR)Data, &WamRegRegistryConfig::m_szWamDllPath, 0xFBu);
    if ( v4 )
    {
      if ( v4 <= 0xFB )
        goto LABEL_8;
      v2 = -2147418113;
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
        778,
        "WamRegRegistryConfig::LoadWamDllPath",
        "Failed to expand %s, hr = %08x\n",
        (const char *)Data,
        v2);
    goto LABEL_18;
  }
  if ( v1 > 0 )
    return (unsigned __int16)v1 | 0x80070000;
  return v2;
}

```

## disassembly

```asm
0x180004dac  mov     [rsp-8+arg_0], rbx
0x180004db1  push    rbp
0x180004db2  lea     rbp, [rsp-80h]
0x180004db7  sub     rsp, 180h
0x180004dbe  mov     rax, cs:__security_cookie
0x180004dc5  xor     rax, rsp
0x180004dc8  mov     [rbp+80h+var_10], rax
0x180004dcc  lea     rax, [rsp+180h+hKey]
0x180004dd1  mov     [rsp+180h+hKey], 0
0x180004dda  mov     r9d, 20019h; samDesired
0x180004de0  mov     [rsp+180h+phkResult], rax; phkResult
0x180004de5  xor     r8d, r8d; ulOptions
0x180004de8  mov     cs:?m_szWamDllPath@WamRegRegistryConfig@@0PADA, 0; char near * WamRegRegistryConfig::m_szWamDllPath
0x180004def  lea     rdx, SubKey; "Software\\Microsoft\\InetStp"
0x180004df6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004dfd  call    cs:__imp_RegOpenKeyExA
0x180004e03  mov     ebx, eax
0x180004e05  test    eax, eax
0x180004e07  jnz     loc_180004FA3
0x180004e0d  movsd   xmm0, qword ptr cs:aWamDll; "\\wam.dll"
0x180004e15  lea     r9, [rsp+180h+Type]; lpType
0x180004e1a  mov     rcx, [rsp+180h+hKey]; hKey
0x180004e1f  lea     rdx, ValueName; "InstallPath"
0x180004e26  mov     [rsp+180h+Type], eax
0x180004e2a  xor     r8d, r8d; lpReserved
0x180004e2d  mov     al, byte ptr cs:aWamDll+8; ""
0x180004e33  mov     [rsp+180h+var_128], al
0x180004e37  lea     rax, [rsp+180h+cbData]
0x180004e3c  mov     [rsp+180h+lpcbData], rax; lpcbData
0x180004e41  lea     rax, [rsp+180h+Data]
0x180004e46  mov     [rsp+180h+phkResult], rax; lpData
0x180004e4b  movsd   qword ptr [rsp+180h+Source], xmm0
0x180004e51  mov     [rsp+180h+cbData], 0FBh
0x180004e59  call    cs:__imp_RegQueryValueExA
0x180004e5f  mov     ebx, eax
0x180004e61  test    eax, eax
0x180004e63  jnz     loc_180004F8B
0x180004e69  mov     eax, [rsp+180h+Type]
0x180004e6d  cmp     eax, 1
0x180004e70  jnz     short loc_180004E94
0x180004e72  mov     r9d, [rsp+180h+cbData]; MaxCount
0x180004e77  lea     r8, [rsp+180h+Data]; Source
0x180004e7c  mov     ebx, 104h
0x180004e81  lea     rcx, ?m_szWamDllPath@WamRegRegistryConfig@@0PADA; Destination
0x180004e88  mov     edx, ebx; SizeInBytes
0x180004e8a  call    cs:__imp_strncpy_s
0x180004e90  mov     edx, ebx
0x180004e92  jmp     short loc_180004EC5
0x180004e94  cmp     eax, 2
0x180004e97  jnz     loc_180004F4A
0x180004e9d  mov     r8d, 0FBh; nSize
0x180004ea3  lea     rdx, ?m_szWamDllPath@WamRegRegistryConfig@@0PADA; lpDst
0x180004eaa  lea     rcx, [rsp+180h+Data]; lpSrc
0x180004eaf  call    cs:__imp_ExpandEnvironmentStringsA
0x180004eb5  test    eax, eax
0x180004eb7  jz      short loc_180004EEB
0x180004eb9  cmp     eax, 0FBh
0x180004ebe  ja      short loc_180004EE4
0x180004ec0  mov     edx, 104h; SizeInBytes
0x180004ec5  lea     r8, [rsp+180h+Source]; Source
0x180004eca  mov     r9d, 9; MaxCount
0x180004ed0  lea     rcx, ?m_szWamDllPath@WamRegRegistryConfig@@0PADA; Destination
0x180004ed7  call    cs:__imp_strncat_s
0x180004edd  xor     ebx, ebx
0x180004edf  jmp     loc_180004F96
0x180004ee4  mov     ebx, 8000FFFFh
0x180004ee9  jmp     short loc_180004F00
0x180004eeb  call    cs:__imp_GetLastError
0x180004ef1  mov     ebx, eax
0x180004ef3  test    eax, eax
0x180004ef5  jle     short loc_180004F00
0x180004ef7  movzx   ebx, ax
0x180004efa  or      ebx, 80070000h
0x180004f00  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f07  jz      loc_180004F96
0x180004f0d  mov     rcx, cs:g_pDebug
0x180004f14  lea     rax, [rsp+180h+Data]
0x180004f19  mov     [rsp+180h+var_150], ebx
0x180004f1d  lea     r9, aWamregregistry; "WamRegRegistryConfig::LoadWamDllPath"
0x180004f24  mov     [rsp+180h+lpcbData], rax
0x180004f29  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180004f30  lea     rax, aFailedToExpand; "Failed to expand %s, hr = %08x\n"
0x180004f37  mov     r8d, 30Ah
0x180004f3d  mov     [rsp+180h+phkResult], rax
0x180004f42  call    cs:__imp_PuDbgPrint
0x180004f48  jmp     short loc_180004F96
0x180004f4a  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f51  mov     ebx, 8000FFFFh
0x180004f56  jz      short loc_180004F96
0x180004f58  mov     rcx, cs:g_pDebug
0x180004f5f  lea     r9, aWamregregistry; "WamRegRegistryConfig::LoadWamDllPath"
0x180004f66  mov     dword ptr [rsp+180h+lpcbData], eax
0x180004f6a  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180004f71  lea     rax, aWrongTypeForIn; "Wrong Type for InstallPath registry key"...
0x180004f78  mov     r8d, 316h
0x180004f7e  mov     [rsp+180h+phkResult], rax
0x180004f83  call    cs:__imp_PuDbgPrint
0x180004f89  jmp     short loc_180004F96
0x180004f8b  jle     short loc_180004F96
0x180004f8d  movzx   ebx, ax
0x180004f90  or      ebx, 80070000h
0x180004f96  mov     rcx, [rsp+180h+hKey]; hKey
0x180004f9b  call    cs:__imp_RegCloseKey
0x180004fa1  jmp     short loc_180004FAE
0x180004fa3  jle     short loc_180004FAE
0x180004fa5  movzx   ebx, ax
0x180004fa8  or      ebx, 80070000h
0x180004fae  mov     eax, ebx
0x180004fb0  mov     rcx, [rbp+80h+var_10]
0x180004fb4  xor     rcx, rsp; StackCookie
0x180004fb7  call    __security_check_cookie
0x180004fbc  mov     rbx, [rsp+180h+arg_0]
0x180004fc4  add     rsp, 180h
0x180004fcb  pop     rbp
0x180004fcc  retn
```
