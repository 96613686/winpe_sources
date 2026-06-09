# CWPPLoggerGuidConfig::ReadTraceConfig(void)

- ea: `0x18002b82c`
- end: `0x18002bc91`
- name: `?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ`
- size: `1125`
- prototype: `__int64 __fastcall(CWPPLoggerGuidConfig *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d600`
- `0x1800be0e0`
- `0x1800be4c4`

## callees

- `0x180009940`
- `0x180014808`
- `0x18002b82c`
- `0x180033f60`
- `0x180034e64`
- `0x1800a2c54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b93f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b98b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b9dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ba48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ba92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bae8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bbe5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bc29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b93f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b98b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b9dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ba48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ba92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bae8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bbe5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bc29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b8b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b8b5`

## string_xrefs

- `0x18002b8cf`: `error %#x: RegOpenKeyEx(%S) failed`

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
0x18002b82c  mov     [rsp-8+arg_8], rbx
0x18002b831  mov     [rsp-8+arg_10], rdi
0x18002b836  push    rbp
0x18002b837  push    r14
0x18002b839  push    r15
0x18002b83b  lea     rbp, [rsp-170h]
0x18002b843  sub     rsp, 270h
0x18002b84a  mov     rax, cs:__security_cookie
0x18002b851  xor     rax, rsp
0x18002b854  mov     [rbp+180h+var_20], rax
0x18002b85b  mov     rbx, rcx
0x18002b85e  mov     [rsp+280h+Type], 0
0x18002b866  mov     r15d, 208h
0x18002b86c  mov     dword ptr [rsp+280h+Data], 0
0x18002b874  mov     r8d, r15d; Size
0x18002b877  mov     [rsp+280h+cbData], 0
0x18002b87f  xor     edx, edx; Val
0x18002b881  mov     [rsp+280h+hKey], 0
0x18002b88a  lea     rcx, [rsp+280h+ValueName]; void *
0x18002b88f  call    memset_0
0x18002b894  lea     rax, [rsp+280h+hKey]
0x18002b899  mov     r9d, 20019h; samDesired
0x18002b89f  xor     r8d, r8d; ulOptions
0x18002b8a2  mov     [rsp+280h+phkResult], rax; phkResult
0x18002b8a7  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18002b8ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b8b5  call    cs:__imp_RegOpenKeyExW
0x18002b8bc  nop     dword ptr [rax+rax+00h]
0x18002b8c1  mov     edi, eax
0x18002b8c3  test    eax, eax
0x18002b8c5  jz      short loc_18002B8F6
0x18002b8c7  lea     r9, [rsp+280h+ValueName]
0x18002b8cc  mov     r8d, eax
0x18002b8cf  lea     rdx, aErrorXRegopenk; "error %#x: RegOpenKeyEx(%S) failed"
0x18002b8d6  mov     ecx, 1; int
0x18002b8db  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b8e0  test    edi, edi
0x18002b8e2  jle     loc_18002BC50
0x18002b8e8  movzx   edi, di
0x18002b8eb  or      edi, 80070000h
0x18002b8f1  jmp     loc_18002BC50
0x18002b8f6  mov     r9, [rbx+10h]
0x18002b8fa  lea     r8, aDebugS; "Debug%s"
0x18002b901  mov     rdx, r15; unsigned __int64
0x18002b904  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x18002b909  xor     edi, edi
0x18002b90b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b910  mov     rcx, [rsp+280h+hKey]; hKey
0x18002b915  lea     rax, [rsp+280h+cbData]
0x18002b91a  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002b91f  lea     r14d, [rdi+4]
0x18002b923  lea     rax, [rsp+280h+Data]
0x18002b928  mov     [rsp+280h+cbData], r14d
0x18002b92d  lea     r9, [rsp+280h+Type]; lpType
0x18002b932  mov     [rsp+280h+phkResult], rax; lpData
0x18002b937  xor     r8d, r8d; lpReserved
0x18002b93a  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002b93f  call    cs:__imp_RegQueryValueExW
0x18002b946  nop     dword ptr [rax+rax+00h]
0x18002b94b  test    eax, eax
0x18002b94d  jnz     short loc_18002B95E
0x18002b94f  cmp     [rsp+280h+Type], r14d
0x18002b954  jnz     short loc_18002B95E
0x18002b956  xor     ecx, ecx
0x18002b958  cmp     dword ptr [rsp+280h+Data], ecx
0x18002b95c  jmp     short loc_18002B9A9
0x18002b95e  mov     rcx, [rsp+280h+hKey]; hKey
0x18002b963  lea     rax, [rsp+280h+cbData]
0x18002b968  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002b96d  lea     r9, [rsp+280h+Type]; lpType
0x18002b972  lea     rax, [rsp+280h+Data]
0x18002b977  mov     [rsp+280h+cbData], r14d
0x18002b97c  xor     r8d, r8d; lpReserved
0x18002b97f  mov     [rsp+280h+phkResult], rax; lpData
0x18002b984  lea     rdx, aDebug; "Debug"
0x18002b98b  call    cs:__imp_RegQueryValueExW
0x18002b992  nop     dword ptr [rax+rax+00h]
0x18002b997  test    eax, eax
0x18002b999  jnz     short loc_18002B9A2
0x18002b99b  cmp     [rsp+280h+Type], r14d
0x18002b9a0  jz      short loc_18002B956
0x18002b9a2  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x18002b9a7  test    eax, eax
0x18002b9a9  setnz   cl
0x18002b9ac  lea     rax, [rsp+280h+cbData]
0x18002b9b1  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002b9b6  lea     r9, [rsp+280h+Type]; lpType
0x18002b9bb  mov     [rbx+20h], cl
0x18002b9be  lea     rax, [rsp+280h+Data]
0x18002b9c3  mov     rcx, [rsp+280h+hKey]; hKey
0x18002b9c8  lea     rdx, aCapturestacktr; "CaptureStackTrace"
0x18002b9cf  xor     r8d, r8d; lpReserved
0x18002b9d2  mov     [rsp+280h+phkResult], rax; lpData
0x18002b9d7  mov     [rsp+280h+cbData], r14d
0x18002b9dc  call    cs:__imp_RegQueryValueExW
0x18002b9e3  nop     dword ptr [rax+rax+00h]
0x18002b9e8  test    eax, eax
0x18002b9ea  jnz     short loc_18002B9F9
0x18002b9ec  cmp     [rsp+280h+Type], r14d
0x18002b9f1  jnz     short loc_18002B9F9
0x18002b9f3  mov     eax, dword ptr [rsp+280h+Data]
0x18002b9f7  jmp     short loc_18002B9FF
0x18002b9f9  xor     eax, eax
0x18002b9fb  mov     dword ptr [rsp+280h+Data], eax
0x18002b9ff  mov     r9, [rbx+10h]
0x18002ba03  lea     r8, aDebugSflags; "Debug%sFlags"
0x18002ba0a  mov     rdx, r15; unsigned __int64
0x18002ba0d  mov     cs:?g_bCaptureObjectStackTrace@@3HA, eax; int g_bCaptureObjectStackTrace
0x18002ba13  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x18002ba18  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ba1d  mov     rcx, [rsp+280h+hKey]; hKey
0x18002ba22  lea     rax, [rsp+280h+cbData]
0x18002ba27  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002ba2c  lea     r9, [rsp+280h+Type]; lpType
0x18002ba31  lea     rax, [rsp+280h+Data]
0x18002ba36  mov     [rsp+280h+cbData], r14d
0x18002ba3b  xor     r8d, r8d; lpReserved
0x18002ba3e  mov     [rsp+280h+phkResult], rax; lpData
0x18002ba43  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002ba48  call    cs:__imp_RegQueryValueExW
0x18002ba4f  nop     dword ptr [rax+rax+00h]
0x18002ba54  test    eax, eax
0x18002ba56  jnz     short loc_18002BA65
0x18002ba58  cmp     [rsp+280h+Type], r14d
0x18002ba5d  jnz     short loc_18002BA65
0x18002ba5f  mov     eax, dword ptr [rsp+280h+Data]
0x18002ba63  jmp     short loc_18002BAB2
0x18002ba65  mov     rcx, [rsp+280h+hKey]; hKey
0x18002ba6a  lea     rax, [rsp+280h+cbData]
0x18002ba6f  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002ba74  lea     r9, [rsp+280h+Type]; lpType
0x18002ba79  lea     rax, [rsp+280h+Data]
0x18002ba7e  mov     [rsp+280h+cbData], r14d
0x18002ba83  xor     r8d, r8d; lpReserved
0x18002ba86  mov     [rsp+280h+phkResult], rax; lpData
0x18002ba8b  lea     rdx, aDebugflags; "DebugFlags"
0x18002ba92  call    cs:__imp_RegQueryValueExW
0x18002ba99  nop     dword ptr [rax+rax+00h]
0x18002ba9e  test    eax, eax
0x18002baa0  jnz     short loc_18002BAAD
0x18002baa2  mov     eax, dword ptr [rsp+280h+Data]
0x18002baa6  cmp     [rsp+280h+Type], r14d
0x18002baab  jz      short loc_18002BAB2
0x18002baad  mov     eax, 0FFFFFFFEh
0x18002bab2  mov     rcx, [rsp+280h+hKey]; hKey
0x18002bab7  lea     r9, [rsp+280h+Type]; lpType
0x18002babc  mov     [rbx+18h], eax
0x18002babf  lea     rdx, aDebugflagsex; "DebugFlagsEx"
0x18002bac6  mov     cs:?g_DebugTraceComponent@@3KA, eax; ulong g_DebugTraceComponent
0x18002bacc  xor     r8d, r8d; lpReserved
0x18002bacf  lea     rax, [rsp+280h+cbData]
0x18002bad4  mov     [rsp+280h+cbData], r14d
0x18002bad9  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002bade  lea     rax, [rsp+280h+Data]
0x18002bae3  mov     [rsp+280h+phkResult], rax; lpData
0x18002bae8  call    cs:__imp_RegQueryValueExW
0x18002baef  nop     dword ptr [rax+rax+00h]
0x18002baf4  mov     r9, [rbx+10h]
0x18002baf8  lea     r8, aDebugSlevel; "Debug%sLevel"
0x18002baff  mov     rdx, r15; unsigned __int64
0x18002bb02  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x18002bb07  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bb0c  mov     rcx, [rsp+280h+hKey]; hKey
0x18002bb11  lea     rax, [rsp+280h+cbData]
0x18002bb16  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002bb1b  lea     r9, [rsp+280h+Type]; lpType
0x18002bb20  lea     rax, [rsp+280h+Data]
0x18002bb25  mov     [rsp+280h+cbData], r14d
0x18002bb2a  xor     r8d, r8d; lpReserved
0x18002bb2d  mov     [rsp+280h+phkResult], rax; lpData
0x18002bb32  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002bb37  call    cs:__imp_RegQueryValueExW
0x18002bb3e  nop     dword ptr [rax+rax+00h]
0x18002bb43  test    eax, eax
0x18002bb45  jnz     short loc_18002BB4E
0x18002bb47  cmp     [rsp+280h+Type], r14d
0x18002bb4c  jz      short loc_18002BB92
0x18002bb4e  mov     rcx, [rsp+280h+hKey]; hKey
0x18002bb53  lea     rax, [rsp+280h+cbData]
0x18002bb58  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002bb5d  lea     r9, [rsp+280h+Type]; lpType
0x18002bb62  lea     rax, [rsp+280h+Data]
0x18002bb67  mov     [rsp+280h+cbData], r14d
0x18002bb6c  xor     r8d, r8d; lpReserved
0x18002bb6f  mov     [rsp+280h+phkResult], rax; lpData
0x18002bb74  lea     rdx, aDebuglevel; "DebugLevel"
0x18002bb7b  call    cs:__imp_RegQueryValueExW
0x18002bb82  nop     dword ptr [rax+rax+00h]
0x18002bb87  test    eax, eax
0x18002bb89  jnz     short loc_18002BB9B
0x18002bb8b  cmp     [rsp+280h+Type], r14d
0x18002bb90  jnz     short loc_18002BB9B
0x18002bb92  mov     eax, dword ptr [rsp+280h+Data]
0x18002bb96  mov     [rbx+1Ch], eax
0x18002bb99  jmp     short loc_18002BBA2
0x18002bb9b  mov     dword ptr [rbx+1Ch], 40BEh
0x18002bba2  mov     r9, [rbx+10h]
0x18002bba6  lea     r8, aDebugStodebugg; "Debug%sToDebugger"
0x18002bbad  mov     rdx, r15; unsigned __int64
0x18002bbb0  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x18002bbb5  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bbba  mov     rcx, [rsp+280h+hKey]; hKey
0x18002bbbf  lea     rax, [rsp+280h+cbData]
0x18002bbc4  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002bbc9  lea     r9, [rsp+280h+Type]; lpType
0x18002bbce  lea     rax, [rsp+280h+Data]
0x18002bbd3  mov     [rsp+280h+cbData], r14d
0x18002bbd8  xor     r8d, r8d; lpReserved
0x18002bbdb  mov     [rsp+280h+phkResult], rax; lpData
0x18002bbe0  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x18002bbe5  call    cs:__imp_RegQueryValueExW
0x18002bbec  nop     dword ptr [rax+rax+00h]
0x18002bbf1  test    eax, eax
0x18002bbf3  jnz     short loc_18002BBFC
0x18002bbf5  cmp     [rsp+280h+Type], r14d
0x18002bbfa  jz      short loc_18002BC40
0x18002bbfc  mov     rcx, [rsp+280h+hKey]; hKey
0x18002bc01  lea     rax, [rsp+280h+cbData]
0x18002bc06  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002bc0b  lea     r9, [rsp+280h+Type]; lpType
0x18002bc10  lea     rax, [rsp+280h+Data]
0x18002bc15  mov     [rsp+280h+cbData], r14d
0x18002bc1a  xor     r8d, r8d; lpReserved
0x18002bc1d  mov     [rsp+280h+phkResult], rax; lpData
0x18002bc22  lea     rdx, aDebugtodebugge; "DebugToDebugger"
0x18002bc29  call    cs:__imp_RegQueryValueExW
0x18002bc30  nop     dword ptr [rax+rax+00h]
0x18002bc35  test    eax, eax
0x18002bc37  jnz     short loc_18002BC4C
0x18002bc39  cmp     [rsp+280h+Type], r14d
0x18002bc3e  jnz     short loc_18002BC4C
0x18002bc40  cmp     dword ptr [rsp+280h+Data], edi
0x18002bc44  setnz   al
0x18002bc47  mov     [rbx+21h], al
0x18002bc4a  jmp     short loc_18002BC50
0x18002bc4c  mov     [rbx+21h], dil
0x18002bc50  mov     rcx, [rsp+280h+hKey]; hKey
0x18002bc55  test    rcx, rcx
0x18002bc58  jz      short loc_18002BC66
0x18002bc5a  call    cs:__imp_RegCloseKey
0x18002bc61  nop     dword ptr [rax+rax+00h]
0x18002bc66  mov     eax, edi
0x18002bc68  mov     rcx, [rbp+180h+var_20]
0x18002bc6f  xor     rcx, rsp; StackCookie
0x18002bc72  call    __security_check_cookie
0x18002bc77  lea     r11, [rsp+280h+var_10]
0x18002bc7f  mov     rbx, [r11+28h]
0x18002bc83  mov     rdi, [r11+30h]
0x18002bc87  mov     rsp, r11
0x18002bc8a  pop     r15
0x18002bc8c  pop     r14
0x18002bc8e  pop     rbp
0x18002bc8f  retn
```
