# TRACELogRegister

- ea: `0x18003de44`
- end: `0x18003e050`
- name: `TRACELogRegister`
- size: `524`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d6d0`

## callees

- `0x180001600`
- `0x18003dbd8`
- `0x18003de44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003df62`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003df90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003dfbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003dfec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003df62`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003df90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003dfbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003dfec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003df21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003df21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dff7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dff7`
- `rtutils!TraceRegisterExW` at `0x18003e025`
- `rtutils!TraceRegisterExW` at `0x18003e025`

## pseudocode

```c
_BOOL8 TRACELogRegister()
{
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  char v4[24]; // [rsp+40h] [rbp-C0h] BYREF
  char v5[24]; // [rsp+58h] [rbp-A8h] BYREF
  char v6[24]; // [rsp+70h] [rbp-90h] BYREF
  CHAR ValueName[24]; // [rsp+88h] [rbp-78h] BYREF
  char pszDest[112]; // [rsp+A0h] [rbp-60h] BYREF

  strcpy(ValueName, "EnableDebuggerTracing");
  strcpy(v6, "EnableConsoleTracing");
  hKey = 0;
  *(_DWORD *)&sg_dwTracingToDebugger = 0;
  strcpy(v4, "EnableFileTracing");
  *(_DWORD *)&sg_dwTracingToConsole = 0;
  *(_DWORD *)&sg_dwTracingToFile = 0;
  strcpy(v5, "ConsoleTracingMask");
  StringCbPrintfA(pszDest, 0x64u, "Software\\Microsoft\\Tracing\\%ls", L"tapisrv");
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &hKey) )
  {
    Type = 0;
    cbData = 4;
    RegQueryValueExA(hKey, ValueName, 0, &Type, &sg_dwTracingToDebugger, &cbData);
    RegQueryValueExA(hKey, v6, 0, &Type, &sg_dwTracingToConsole, &cbData);
    RegQueryValueExA(hKey, v4, 0, &Type, &sg_dwTracingToFile, &cbData);
    RegQueryValueExA(hKey, v5, 0, &Type, &sg_dwDebuggerMask, &cbData);
    RegCloseKey(hKey);
  }
  StringCbPrintfA(sg_szTraceName, 0x64u, "%ls", L"tapisrv");
  sg_dwTraceID = TraceRegisterExW(L"tapisrv", 0);
  return sg_dwTraceID != -1;
}

```

## disassembly

```asm
0x18003de44  push    rbp
0x18003de46  lea     rbp, [rsp-20h]
0x18003de4b  sub     rsp, 120h
0x18003de52  mov     rax, cs:__security_cookie
0x18003de59  xor     rax, rsp
0x18003de5c  mov     [rbp+20h+var_10], rax
0x18003de60  movups  xmm0, xmmword ptr cs:aEnabledebugger; "EnableDebuggerTracing"
0x18003de67  lea     r9, aTapisrv_0; "tapisrv"
0x18003de6e  movzx   eax, word ptr cs:aEnablefiletrac+10h; "g"
0x18003de75  movsd   xmm1, qword ptr cs:aEnabledebugger+0Eh; "Tracing"
0x18003de7d  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Tracing\\%ls"
0x18003de84  movups  xmmword ptr [rbp+20h+ValueName], xmm0
0x18003de88  mov     word ptr [rsp+120h+var_E0+10h], ax
0x18003de8d  mov     edx, 64h ; 'd'; cbDest
0x18003de92  movups  xmm0, xmmword ptr cs:aEnableconsolet; "EnableConsoleTracing"
0x18003de99  mov     eax, dword ptr cs:aConsoletracing+0Fh; "ask"
0x18003de9f  lea     rcx, [rbp+20h+pszDest]; pszDest
0x18003dea3  movsd   qword ptr [rbp+20h+ValueName+0Eh], xmm1
0x18003dea8  movsd   xmm1, qword ptr cs:aEnableconsolet+0Dh; "Tracing"
0x18003deb0  movups  xmmword ptr [rsp+120h+var_B0], xmm0
0x18003deb5  mov     [rsp+120h+hKey], 0
0x18003debe  movups  xmm0, xmmword ptr cs:aEnablefiletrac; "EnableFileTracing"
0x18003dec5  mov     cs:sg_dwTracingToDebugger, 0
0x18003decf  movsd   qword ptr [rsp+120h+var_B0+0Dh], xmm1
0x18003ded5  movups  xmmword ptr [rsp+120h+var_E0], xmm0
0x18003deda  mov     cs:sg_dwTracingToConsole, 0
0x18003dee4  movups  xmm0, xmmword ptr cs:aConsoletracing; "ConsoleTracingMask"
0x18003deeb  mov     cs:sg_dwTracingToFile, 0
0x18003def5  movups  xmmword ptr [rsp+120h+var_C8], xmm0
0x18003defa  mov     dword ptr [rsp+120h+var_C8+0Fh], eax
0x18003defe  call    StringCbPrintfA
0x18003df03  lea     rax, [rsp+120h+hKey]
0x18003df08  mov     r9d, 20019h; samDesired
0x18003df0e  xor     r8d, r8d; ulOptions
0x18003df11  mov     [rsp+120h+phkResult], rax; phkResult
0x18003df16  lea     rdx, [rbp+20h+pszDest]; lpSubKey
0x18003df1a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003df21  call    cs:__imp_RegOpenKeyExA
0x18003df27  test    eax, eax
0x18003df29  jnz     loc_18003DFFD
0x18003df2f  mov     rcx, [rsp+120h+hKey]; hKey
0x18003df34  lea     r9, [rsp+120h+Type]; lpType
0x18003df39  mov     [rsp+120h+Type], eax
0x18003df3d  lea     rdx, [rbp+20h+ValueName]; lpValueName
0x18003df41  lea     rax, [rsp+120h+cbData]
0x18003df46  mov     [rsp+120h+cbData], 4
0x18003df4e  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18003df53  xor     r8d, r8d; lpReserved
0x18003df56  lea     rax, sg_dwTracingToDebugger
0x18003df5d  mov     [rsp+120h+phkResult], rax; lpData
0x18003df62  call    cs:__imp_RegQueryValueExA
0x18003df68  mov     rcx, [rsp+120h+hKey]; hKey
0x18003df6d  lea     rax, [rsp+120h+cbData]
0x18003df72  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18003df77  lea     r9, [rsp+120h+Type]; lpType
0x18003df7c  lea     rax, sg_dwTracingToConsole
0x18003df83  xor     r8d, r8d; lpReserved
0x18003df86  lea     rdx, [rsp+120h+var_B0]; lpValueName
0x18003df8b  mov     [rsp+120h+phkResult], rax; lpData
0x18003df90  call    cs:__imp_RegQueryValueExA
0x18003df96  mov     rcx, [rsp+120h+hKey]; hKey
0x18003df9b  lea     rax, [rsp+120h+cbData]
0x18003dfa0  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18003dfa5  lea     r9, [rsp+120h+Type]; lpType
0x18003dfaa  lea     rax, sg_dwTracingToFile
0x18003dfb1  xor     r8d, r8d; lpReserved
0x18003dfb4  lea     rdx, [rsp+120h+var_E0]; lpValueName
0x18003dfb9  mov     [rsp+120h+phkResult], rax; lpData
0x18003dfbe  call    cs:__imp_RegQueryValueExA
0x18003dfc4  mov     rcx, [rsp+120h+hKey]; hKey
0x18003dfc9  lea     rax, [rsp+120h+cbData]
0x18003dfce  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18003dfd3  lea     r9, [rsp+120h+Type]; lpType
0x18003dfd8  lea     rax, sg_dwDebuggerMask
0x18003dfdf  xor     r8d, r8d; lpReserved
0x18003dfe2  lea     rdx, [rsp+120h+var_C8]; lpValueName
0x18003dfe7  mov     [rsp+120h+phkResult], rax; lpData
0x18003dfec  call    cs:__imp_RegQueryValueExA
0x18003dff2  mov     rcx, [rsp+120h+hKey]; hKey
0x18003dff7  call    cs:__imp_RegCloseKey
0x18003dffd  lea     r9, aTapisrv_0; "tapisrv"
0x18003e004  mov     edx, 64h ; 'd'; cbDest
0x18003e009  lea     r8, aLs; "%ls"
0x18003e010  lea     rcx, sg_szTraceName; pszDest
0x18003e017  call    StringCbPrintfA
0x18003e01c  xor     edx, edx; dwFlags
0x18003e01e  lea     rcx, aTapisrv_0; "tapisrv"
0x18003e025  call    cs:__imp_TraceRegisterExW
0x18003e02b  xor     ecx, ecx
0x18003e02d  mov     cs:sg_dwTraceID, eax
0x18003e033  cmp     eax, 0FFFFFFFFh
0x18003e036  setnz   cl
0x18003e039  mov     eax, ecx
0x18003e03b  mov     rcx, [rbp+20h+var_10]
0x18003e03f  xor     rcx, rsp; StackCookie
0x18003e042  call    __security_check_cookie
0x18003e047  add     rsp, 120h
0x18003e04e  pop     rbp
0x18003e04f  retn
```
