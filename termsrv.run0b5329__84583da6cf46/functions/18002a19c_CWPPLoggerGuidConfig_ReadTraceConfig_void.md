# CWPPLoggerGuidConfig::ReadTraceConfig(void)

- ea: `0x18002a19c`
- end: `0x18002a5b8`
- name: `?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ`
- size: `1052`
- prototype: `__int64 __fastcall(CWPPLoggerGuidConfig *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c7e0`
- `0x1800b78dc`
- `0x1800b7cb4`

## callees

- `0x18000a210`
- `0x180013e38`
- `0x18002a19c`
- `0x1800321f0`
- `0x1800330c4`
- `0x18009dcb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a2a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a2ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a33a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a3a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a3e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a434`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a47d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a4bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a51f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a55d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a2a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a2ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a33a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a3a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a3e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a434`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a47d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a4bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a51f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a55d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a588`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a225`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a225`

## string_xrefs

- `0x18002a239`: `error %#x: RegOpenKeyEx(%S) failed`

## pseudocode

```c
__int64 __fastcall CWPPLoggerGuidConfig::ReadTraceConfig(CWPPLoggerGuidConfig *this)
{
  LSTATUS v2; // eax
  signed int v3; // edi
  bool v4; // zf
  int v5; // eax
  __int64 v6; // r9
  unsigned int v7; // eax
  HKEY v8; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  memset_0(ValueName, 0, 0x208u);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    _DbgPrintMessage(1, "error %#x: RegOpenKeyEx(%S) failed", v2, ValueName);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v3 = 0;
    StringCbPrintfW(ValueName, 0x208u, L"Debug%s", *((_QWORD *)this + 2));
    cbData = 4;
    if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 4
      || (cbData = 4, !RegQueryValueExW(hKey, L"Debug", 0, &Type, Data, &cbData)) && Type == 4 )
    {
      v4 = *(_DWORD *)Data == 0;
    }
    else
    {
      v4 = (unsigned int)CUtils::IsKernelDebuggerAttached() == 0;
    }
    *((_BYTE *)this + 32) = !v4;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"CaptureStackTrace", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v5 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v5 = *(_DWORD *)Data;
    }
    v6 = *((_QWORD *)this + 2);
    g_bCaptureObjectStackTrace = v5;
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sFlags", v6);
    cbData = 4;
    if ( RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) || Type != 4 )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"DebugFlags", 0, &Type, Data, &cbData) || (v7 = *(_DWORD *)Data, Type != 4) )
        v7 = -2;
    }
    else
    {
      v7 = *(_DWORD *)Data;
    }
    v8 = hKey;
    *((_DWORD *)this + 6) = v7;
    g_DebugTraceComponent = v7;
    cbData = 4;
    RegQueryValueExW(v8, L"DebugFlagsEx", 0, &Type, Data, &cbData);
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sLevel", *((_QWORD *)this + 2));
    cbData = 4;
    if ( (RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) || Type != 4)
      && ((cbData = 4, RegQueryValueExW(hKey, L"DebugLevel", 0, &Type, Data, &cbData)) || Type != 4) )
    {
      *((_DWORD *)this + 7) = 16574;
    }
    else
    {
      *((_DWORD *)this + 7) = *(_DWORD *)Data;
    }
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sToDebugger", *((_QWORD *)this + 2));
    cbData = 4;
    *((_BYTE *)this + 33) = (!RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 4
                          || (cbData = 4, !RegQueryValueExW(hKey, L"DebugToDebugger", 0, &Type, Data, &cbData))
                          && Type == 4)
                         && *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002a19c  mov     [rsp-8+arg_8], rbx
0x18002a1a1  mov     [rsp-8+arg_10], rdi
0x18002a1a6  push    rbp
0x18002a1a7  push    r14
0x18002a1a9  push    r15
0x18002a1ab  lea     rbp, [rsp-170h]
0x18002a1b3  sub     rsp, 270h
0x18002a1ba  mov     rax, cs:__security_cookie
0x18002a1c1  xor     rax, rsp
0x18002a1c4  mov     [rbp+180h+var_20], rax
0x18002a1cb  mov     rbx, rcx
0x18002a1ce  mov     [rsp+280h+Type], 0
0x18002a1d6  mov     r15d, 208h
0x18002a1dc  mov     dword ptr [rsp+280h+Data], 0
0x18002a1e4  mov     r8d, r15d; Size
0x18002a1e7  mov     [rsp+280h+cbData], 0
0x18002a1ef  xor     edx, edx; Val
0x18002a1f1  mov     [rsp+280h+hKey], 0
0x18002a1fa  lea     rcx, [rsp+280h+ValueName]; void *
0x18002a1ff  call    memset_0
0x18002a204  lea     rax, [rsp+280h+hKey]
0x18002a209  mov     r9d, 20019h; samDesired
0x18002a20f  xor     r8d, r8d; ulOptions
0x18002a212  mov     [rsp+280h+phkResult], rax; phkResult
0x18002a217  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18002a21e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a225  call    cs:__imp_RegOpenKeyExW
0x18002a22b  mov     edi, eax
0x18002a22d  test    eax, eax
0x18002a22f  jz      short loc_18002A260
0x18002a231  lea     r9, [rsp+280h+ValueName]
0x18002a236  mov     r8d, eax
0x18002a239  lea     rdx, aErrorXRegopenk; "error %#x: RegOpenKeyEx(%S) failed"
0x18002a240  mov     ecx, 1; int
0x18002a245  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a24a  test    edi, edi
0x18002a24c  jle     loc_18002A57E
0x18002a252  movzx   edi, di
0x18002a255  or      edi, 80070000h
0x18002a25b  jmp     loc_18002A57E
0x18002a260  mov     r9, [rbx+10h]
0x18002a264  lea     r8, aDebugS; "Debug%s"
0x18002a26b  mov     rdx, r15; unsigned __int64
0x18002a26e  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x18002a273  xor     edi, edi
0x18002a275  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a27a  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a27f  lea     rax, [rsp+280h+cbData]
0x18002a284  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a289  lea     r14d, [rdi+4]
0x18002a28d  lea     rax, [rsp+280h+Data]
0x18002a292  mov     [rsp+280h+cbData], r14d
0x18002a297  lea     r9, [rsp+280h+Type]; lpType
0x18002a29c  mov     [rsp+280h+phkResult], rax; lpData
0x18002a2a1  xor     r8d, r8d; lpReserved
0x18002a2a4  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002a2a9  call    cs:__imp_RegQueryValueExW
0x18002a2af  test    eax, eax
0x18002a2b1  jnz     short loc_18002A2C2
0x18002a2b3  cmp     [rsp+280h+Type], r14d
0x18002a2b8  jnz     short loc_18002A2C2
0x18002a2ba  xor     ecx, ecx
0x18002a2bc  cmp     dword ptr [rsp+280h+Data], ecx
0x18002a2c0  jmp     short loc_18002A307
0x18002a2c2  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a2c7  lea     rax, [rsp+280h+cbData]
0x18002a2cc  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a2d1  lea     r9, [rsp+280h+Type]; lpType
0x18002a2d6  lea     rax, [rsp+280h+Data]
0x18002a2db  mov     [rsp+280h+cbData], r14d
0x18002a2e0  xor     r8d, r8d; lpReserved
0x18002a2e3  mov     [rsp+280h+phkResult], rax; lpData
0x18002a2e8  lea     rdx, aDebug; "Debug"
0x18002a2ef  call    cs:__imp_RegQueryValueExW
0x18002a2f5  test    eax, eax
0x18002a2f7  jnz     short loc_18002A300
0x18002a2f9  cmp     [rsp+280h+Type], r14d
0x18002a2fe  jz      short loc_18002A2BA
0x18002a300  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x18002a305  test    eax, eax
0x18002a307  setnz   cl
0x18002a30a  lea     rax, [rsp+280h+cbData]
0x18002a30f  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a314  lea     r9, [rsp+280h+Type]; lpType
0x18002a319  mov     [rbx+20h], cl
0x18002a31c  lea     rax, [rsp+280h+Data]
0x18002a321  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a326  lea     rdx, aCapturestacktr; "CaptureStackTrace"
0x18002a32d  xor     r8d, r8d; lpReserved
0x18002a330  mov     [rsp+280h+phkResult], rax; lpData
0x18002a335  mov     [rsp+280h+cbData], r14d
0x18002a33a  call    cs:__imp_RegQueryValueExW
0x18002a340  test    eax, eax
0x18002a342  jnz     short loc_18002A351
0x18002a344  cmp     [rsp+280h+Type], r14d
0x18002a349  jnz     short loc_18002A351
0x18002a34b  mov     eax, dword ptr [rsp+280h+Data]
0x18002a34f  jmp     short loc_18002A357
0x18002a351  xor     eax, eax
0x18002a353  mov     dword ptr [rsp+280h+Data], eax
0x18002a357  mov     r9, [rbx+10h]
0x18002a35b  lea     r8, aDebugSflags; "Debug%sFlags"
0x18002a362  mov     rdx, r15; unsigned __int64
0x18002a365  mov     cs:?g_bCaptureObjectStackTrace@@3HA, eax; int g_bCaptureObjectStackTrace
0x18002a36b  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x18002a370  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a375  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a37a  lea     rax, [rsp+280h+cbData]
0x18002a37f  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a384  lea     r9, [rsp+280h+Type]; lpType
0x18002a389  lea     rax, [rsp+280h+Data]
0x18002a38e  mov     [rsp+280h+cbData], r14d
0x18002a393  xor     r8d, r8d; lpReserved
0x18002a396  mov     [rsp+280h+phkResult], rax; lpData
0x18002a39b  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002a3a0  call    cs:__imp_RegQueryValueExW
0x18002a3a6  test    eax, eax
0x18002a3a8  jnz     short loc_18002A3B7
0x18002a3aa  cmp     [rsp+280h+Type], r14d
0x18002a3af  jnz     short loc_18002A3B7
0x18002a3b1  mov     eax, dword ptr [rsp+280h+Data]
0x18002a3b5  jmp     short loc_18002A3FE
0x18002a3b7  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a3bc  lea     rax, [rsp+280h+cbData]
0x18002a3c1  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a3c6  lea     r9, [rsp+280h+Type]; lpType
0x18002a3cb  lea     rax, [rsp+280h+Data]
0x18002a3d0  mov     [rsp+280h+cbData], r14d
0x18002a3d5  xor     r8d, r8d; lpReserved
0x18002a3d8  mov     [rsp+280h+phkResult], rax; lpData
0x18002a3dd  lea     rdx, aDebugflags; "DebugFlags"
0x18002a3e4  call    cs:__imp_RegQueryValueExW
0x18002a3ea  test    eax, eax
0x18002a3ec  jnz     short loc_18002A3F9
0x18002a3ee  mov     eax, dword ptr [rsp+280h+Data]
0x18002a3f2  cmp     [rsp+280h+Type], r14d
0x18002a3f7  jz      short loc_18002A3FE
0x18002a3f9  mov     eax, 0FFFFFFFEh
0x18002a3fe  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a403  lea     r9, [rsp+280h+Type]; lpType
0x18002a408  mov     [rbx+18h], eax
0x18002a40b  lea     rdx, aDebugflagsex; "DebugFlagsEx"
0x18002a412  mov     cs:?g_DebugTraceComponent@@3KA, eax; ulong g_DebugTraceComponent
0x18002a418  xor     r8d, r8d; lpReserved
0x18002a41b  lea     rax, [rsp+280h+cbData]
0x18002a420  mov     [rsp+280h+cbData], r14d
0x18002a425  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a42a  lea     rax, [rsp+280h+Data]
0x18002a42f  mov     [rsp+280h+phkResult], rax; lpData
0x18002a434  call    cs:__imp_RegQueryValueExW
0x18002a43a  mov     r9, [rbx+10h]
0x18002a43e  lea     r8, aDebugSlevel; "Debug%sLevel"
0x18002a445  mov     rdx, r15; unsigned __int64
0x18002a448  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x18002a44d  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a452  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a457  lea     rax, [rsp+280h+cbData]
0x18002a45c  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a461  lea     r9, [rsp+280h+Type]; lpType
0x18002a466  lea     rax, [rsp+280h+Data]
0x18002a46b  mov     [rsp+280h+cbData], r14d
0x18002a470  xor     r8d, r8d; lpReserved
0x18002a473  mov     [rsp+280h+phkResult], rax; lpData
0x18002a478  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002a47d  call    cs:__imp_RegQueryValueExW
0x18002a483  test    eax, eax
0x18002a485  jnz     short loc_18002A48E
0x18002a487  cmp     [rsp+280h+Type], r14d
0x18002a48c  jz      short loc_18002A4CC
0x18002a48e  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a493  lea     rax, [rsp+280h+cbData]
0x18002a498  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a49d  lea     r9, [rsp+280h+Type]; lpType
0x18002a4a2  lea     rax, [rsp+280h+Data]
0x18002a4a7  mov     [rsp+280h+cbData], r14d
0x18002a4ac  xor     r8d, r8d; lpReserved
0x18002a4af  mov     [rsp+280h+phkResult], rax; lpData
0x18002a4b4  lea     rdx, aDebuglevel; "DebugLevel"
0x18002a4bb  call    cs:__imp_RegQueryValueExW
0x18002a4c1  test    eax, eax
0x18002a4c3  jnz     short loc_18002A4D5
0x18002a4c5  cmp     [rsp+280h+Type], r14d
0x18002a4ca  jnz     short loc_18002A4D5
0x18002a4cc  mov     eax, dword ptr [rsp+280h+Data]
0x18002a4d0  mov     [rbx+1Ch], eax
0x18002a4d3  jmp     short loc_18002A4DC
0x18002a4d5  mov     dword ptr [rbx+1Ch], 40BEh
0x18002a4dc  mov     r9, [rbx+10h]
0x18002a4e0  lea     r8, aDebugStodebugg; "Debug%sToDebugger"
0x18002a4e7  mov     rdx, r15; unsigned __int64
0x18002a4ea  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x18002a4ef  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a4f4  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a4f9  lea     rax, [rsp+280h+cbData]
0x18002a4fe  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a503  lea     r9, [rsp+280h+Type]; lpType
0x18002a508  lea     rax, [rsp+280h+Data]
0x18002a50d  mov     [rsp+280h+cbData], r14d
0x18002a512  xor     r8d, r8d; lpReserved
0x18002a515  mov     [rsp+280h+phkResult], rax; lpData
0x18002a51a  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002a51f  call    cs:__imp_RegQueryValueExW
0x18002a525  test    eax, eax
0x18002a527  jnz     short loc_18002A530
0x18002a529  cmp     [rsp+280h+Type], r14d
0x18002a52e  jz      short loc_18002A56E
0x18002a530  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a535  lea     rax, [rsp+280h+cbData]
0x18002a53a  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002a53f  lea     r9, [rsp+280h+Type]; lpType
0x18002a544  lea     rax, [rsp+280h+Data]
0x18002a549  mov     [rsp+280h+cbData], r14d
0x18002a54e  xor     r8d, r8d; lpReserved
0x18002a551  mov     [rsp+280h+phkResult], rax; lpData
0x18002a556  lea     rdx, aDebugtodebugge; "DebugToDebugger"
0x18002a55d  call    cs:__imp_RegQueryValueExW
0x18002a563  test    eax, eax
0x18002a565  jnz     short loc_18002A57A
0x18002a567  cmp     [rsp+280h+Type], r14d
0x18002a56c  jnz     short loc_18002A57A
0x18002a56e  cmp     dword ptr [rsp+280h+Data], edi
0x18002a572  setnz   al
0x18002a575  mov     [rbx+21h], al
0x18002a578  jmp     short loc_18002A57E
0x18002a57a  mov     [rbx+21h], dil
0x18002a57e  mov     rcx, [rsp+280h+hKey]; hKey
0x18002a583  test    rcx, rcx
0x18002a586  jz      short loc_18002A58E
0x18002a588  call    cs:__imp_RegCloseKey
0x18002a58e  mov     eax, edi
0x18002a590  mov     rcx, [rbp+180h+var_20]
0x18002a597  xor     rcx, rsp; StackCookie
0x18002a59a  call    __security_check_cookie
0x18002a59f  lea     r11, [rsp+280h+var_10]
0x18002a5a7  mov     rbx, [r11+28h]
0x18002a5ab  mov     rdi, [r11+30h]
0x18002a5af  mov     rsp, r11
0x18002a5b2  pop     r15
0x18002a5b4  pop     r14
0x18002a5b6  pop     rbp
0x18002a5b7  retn
```
