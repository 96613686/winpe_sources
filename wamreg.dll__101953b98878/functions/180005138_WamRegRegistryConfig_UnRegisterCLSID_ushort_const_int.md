# WamRegRegistryConfig::UnRegisterCLSID(ushort const *,int)

- ea: `0x180005138`
- end: `0x1800053cf`
- name: `?UnRegisterCLSID@WamRegRegistryConfig@@QEAAJPEBGH@Z`
- size: `663`
- prototype: `__int64 __fastcall(WamRegRegistryConfig *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180004acc`

## callees

- `0x180005138`
- `0x1800053d8`
- `0x180006822`
- `0x180006850`

## import_xrefs

- `msvcrt!strncat_s` at `0x1800051de`
- `msvcrt!strncat_s` at `0x1800051de`
- `ADVAPI32!RegCloseKey` at `0x1800052f4`
- `ADVAPI32!RegCloseKey` at `0x1800052f4`
- `ADVAPI32!RegDeleteKeyA` at `0x1800052af`
- `ADVAPI32!RegDeleteKeyA` at `0x180005349`
- `ADVAPI32!RegDeleteKeyA` at `0x1800052af`
- `ADVAPI32!RegDeleteKeyA` at `0x180005349`
- `ADVAPI32!RegOpenKeyExA` at `0x180005296`
- `ADVAPI32!RegOpenKeyExA` at `0x180005296`
- `ADVAPI32!RegEnumKeyExA` at `0x1800052e5`
- `ADVAPI32!RegEnumKeyExA` at `0x1800052e5`
- `ole32!ProgIDFromCLSID` at `0x180005209`
- `ole32!ProgIDFromCLSID` at `0x180005209`
- `ole32!CLSIDFromString` at `0x1800051ec`
- `ole32!CLSIDFromString` at `0x1800051ec`
- `ole32!CoTaskMemFree` at `0x180005226`
- `ole32!CoTaskMemFree` at `0x180005226`
- `KERNEL32!WideCharToMultiByte` at `0x1800051c9`
- `KERNEL32!WideCharToMultiByte` at `0x1800051c9`
- `iisutil!PuDbgPrint` at `0x180005271`
- `iisutil!PuDbgPrint` at `0x180005337`
- `iisutil!PuDbgPrint` at `0x180005395`
- `iisutil!PuDbgPrint` at `0x180005271`
- `iisutil!PuDbgPrint` at `0x180005337`
- `iisutil!PuDbgPrint` at `0x180005395`

## string_xrefs

- `0x18000515d`: `CLSID\`
- `0x18000525a`: `WamRegRegistryConfig::UnRegisterCLSID`
- `0x18000531a`: `WamRegRegistryConfig::UnRegisterCLSID`
- `0x180005371`: `WamRegRegistryConfig::UnRegisterCLSID`

## pseudocode

```c
__int64 __fastcall WamRegRegistryConfig::UnRegisterCLSID(WamRegRegistryConfig *this, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int v4; // ebx
  WamRegRegistryConfig *v5; // rcx
  __int64 v6; // r8
  int v7; // eax
  int v8; // eax
  int v9; // edi
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  LPOLESTR lpszProgID; // [rsp+50h] [rbp-B0h] BYREF
  CLSID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  char Destination[7]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[105]; // [rsp+77h] [rbp-89h] BYREF
  CHAR MultiByteStr[48]; // [rsp+E0h] [rbp-20h] BYREF
  CHAR SubKey[272]; // [rsp+110h] [rbp+10h] BYREF

  strcpy(Destination, "CLSID\\");
  phkResult = 0;
  memset_0(v16, 0, 0x5Du);
  lpszProgID = 0;
  pclsid = 0;
  WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, 39, 0, 0);
  strncat_s(Destination, 0x64u, MultiByteStr, 0x27u);
  v3 = CLSIDFromString(a2, &pclsid);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_9;
    v6 = 547;
    goto LABEL_8;
  }
  v3 = ProgIDFromCLSID(&pclsid, &lpszProgID);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_9;
    v6 = 542;
LABEL_8:
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
      v6,
      "WamRegRegistryConfig::UnRegisterCLSID",
      "error = %08x\n",
      v3);
    goto LABEL_9;
  }
  v4 = WamRegRegistryConfig::UnRegisterProgID(v5, lpszProgID);
  CoTaskMemFree(lpszProgID);
  lpszProgID = 0;
LABEL_9:
  if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, Destination, 0, 0x2001Fu, &phkResult) )
  {
    do
      cchName = 260;
    while ( !RegEnumKeyExA(phkResult, 0, SubKey, &cchName, 0, 0, 0, 0) && !RegDeleteKeyA(phkResult, SubKey) );
    v7 = RegCloseKey(phkResult);
    if ( v7 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
          591,
          "WamRegRegistryConfig::UnRegisterCLSID",
          "error = %08x\n",
          v7);
      }
    }
  }
  v8 = RegDeleteKeyA(HKEY_CLASSES_ROOT, Destination);
  v9 = v8;
  if ( v8 && (g_dwDebugFlags & 3) != 0 )
  {
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
      598,
      "WamRegRegistryConfig::UnRegisterCLSID",
      "error = %08x\n",
      v8);
  }
  if ( v4 >= 0 && v9 )
  {
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
    else
      return (unsigned int)v9;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005138  push    rbp
0x18000513a  push    rbx
0x18000513b  push    rsi
0x18000513c  push    rdi
0x18000513d  lea     rbp, [rsp-138h]
0x180005145  sub     rsp, 238h
0x18000514c  mov     rax, cs:__security_cookie
0x180005153  xor     rax, rsp
0x180005156  mov     [rbp+150h+var_30], rax
0x18000515d  mov     eax, dword ptr cs:aClsid; "CLSID\\"
0x180005163  lea     rcx, [rsp+250h+var_1D9]; void *
0x180005168  mov     dword ptr [rsp+250h+Destination], eax
0x18000516c  xor     esi, esi
0x18000516e  movzx   eax, word ptr cs:aClsid+4; "D\\"
0x180005175  mov     rbx, rdx
0x180005178  mov     [rsp+250h+var_1DC], ax
0x18000517d  xor     edx, edx; Val
0x18000517f  mov     al, byte ptr cs:aClsid+6; ""
0x180005185  lea     r8d, [rsi+5Dh]; Size
0x180005189  mov     [rsp+250h+var_1DA], al
0x18000518d  mov     [rsp+250h+phkResult], rsi
0x180005192  call    memset_0
0x180005197  mov     [rsp+250h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x18000519c  lea     rax, [rbp+150h+MultiByteStr]
0x1800051a0  xorps   xmm0, xmm0
0x1800051a3  mov     [rsp+250h+lpDefaultChar], rsi; lpDefaultChar
0x1800051a8  lea     edi, [rsi+27h]
0x1800051ab  mov     [rsp+250h+lpszProgID], rsi
0x1800051b0  mov     [rsp+250h+cbMultiByte], edi; cbMultiByte
0x1800051b4  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800051b8  mov     r8, rbx; lpWideCharStr
0x1800051bb  mov     [rsp+250h+lpMultiByteStr], rax; lpMultiByteStr
0x1800051c0  xor     edx, edx; dwFlags
0x1800051c2  xor     ecx, ecx; CodePage
0x1800051c4  movups  xmmword ptr [rsp+250h+pclsid.Data1], xmm0
0x1800051c9  call    cs:__imp_WideCharToMultiByte
0x1800051cf  mov     r9d, edi; MaxCount
0x1800051d2  lea     r8, [rbp+150h+MultiByteStr]; Source
0x1800051d6  lea     edx, [rsi+64h]; SizeInBytes
0x1800051d9  lea     rcx, [rsp+250h+Destination]; Destination
0x1800051de  call    cs:__imp_strncat_s
0x1800051e4  lea     rdx, [rsp+250h+pclsid]; pclsid
0x1800051e9  mov     rcx, rbx; lpsz
0x1800051ec  call    cs:__imp_CLSIDFromString
0x1800051f2  lea     rdi, aError08x; "error = %08x\n"
0x1800051f9  mov     ebx, eax
0x1800051fb  test    eax, eax
0x1800051fd  js      short loc_180005244
0x1800051ff  lea     rdx, [rsp+250h+lpszProgID]; lplpszProgID
0x180005204  lea     rcx, [rsp+250h+pclsid]; clsid
0x180005209  call    cs:__imp_ProgIDFromCLSID
0x18000520f  mov     ebx, eax
0x180005211  test    eax, eax
0x180005213  js      short loc_180005233
0x180005215  mov     rdx, [rsp+250h+lpszProgID]; unsigned __int16 *
0x18000521a  call    ?UnRegisterProgID@WamRegRegistryConfig@@AEAAJPEBG@Z; WamRegRegistryConfig::UnRegisterProgID(ushort const *)
0x18000521f  mov     rcx, [rsp+250h+lpszProgID]; pv
0x180005224  mov     ebx, eax
0x180005226  call    cs:__imp_CoTaskMemFree
0x18000522c  mov     [rsp+250h+lpszProgID], rsi
0x180005231  jmp     short loc_180005277
0x180005233  test    byte ptr cs:g_dwDebugFlags, 3
0x18000523a  jz      short loc_180005277
0x18000523c  mov     r8d, 21Eh
0x180005242  jmp     short loc_180005253
0x180005244  test    byte ptr cs:g_dwDebugFlags, 3
0x18000524b  jz      short loc_180005277
0x18000524d  mov     r8d, 223h
0x180005253  mov     rcx, cs:g_pDebug
0x18000525a  lea     r9, aWamregregistry_0; "WamRegRegistryConfig::UnRegisterCLSID"
0x180005261  mov     [rsp+250h+cbMultiByte], eax
0x180005265  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x18000526c  mov     [rsp+250h+lpMultiByteStr], rdi
0x180005271  call    cs:__imp_PuDbgPrint
0x180005277  lea     rax, [rsp+250h+phkResult]
0x18000527c  mov     r9d, 2001Fh; samDesired
0x180005282  xor     r8d, r8d; ulOptions
0x180005285  mov     [rsp+250h+lpMultiByteStr], rax; phkResult
0x18000528a  lea     rdx, [rsp+250h+Destination]; lpSubKey
0x18000528f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005296  call    cs:__imp_RegOpenKeyExA
0x18000529c  test    eax, eax
0x18000529e  jnz     loc_18000533D
0x1800052a4  jmp     short loc_1800052B9
0x1800052a6  mov     rcx, [rsp+250h+phkResult]; hKey
0x1800052ab  lea     rdx, [rbp+150h+SubKey]; lpSubKey
0x1800052af  call    cs:__imp_RegDeleteKeyA
0x1800052b5  test    eax, eax
0x1800052b7  jnz     short loc_1800052EF
0x1800052b9  mov     rcx, [rsp+250h+phkResult]; hKey
0x1800052be  lea     r9, [rsp+250h+cchName]; lpcchName
0x1800052c3  mov     [rsp+250h+lpUsedDefaultChar], rsi; lpftLastWriteTime
0x1800052c8  lea     r8, [rbp+150h+SubKey]; lpName
0x1800052cc  mov     [rsp+250h+lpDefaultChar], rsi; lpcchClass
0x1800052d1  xor     edx, edx; dwIndex
0x1800052d3  mov     qword ptr [rsp+250h+cbMultiByte], rsi; lpClass
0x1800052d8  mov     [rsp+250h+lpMultiByteStr], rsi; lpReserved
0x1800052dd  mov     [rsp+250h+cchName], 104h
0x1800052e5  call    cs:__imp_RegEnumKeyExA
0x1800052eb  test    eax, eax
0x1800052ed  jz      short loc_1800052A6
0x1800052ef  mov     rcx, [rsp+250h+phkResult]; hKey
0x1800052f4  call    cs:__imp_RegCloseKey
0x1800052fa  test    eax, eax
0x1800052fc  jz      short loc_18000533D
0x1800052fe  test    byte ptr cs:g_dwDebugFlags, 3
0x180005305  jz      short loc_18000533D
0x180005307  test    eax, eax
0x180005309  jle     short loc_180005313
0x18000530b  movzx   eax, ax
0x18000530e  or      eax, 80070000h
0x180005313  mov     rcx, cs:g_pDebug
0x18000531a  lea     r9, aWamregregistry_0; "WamRegRegistryConfig::UnRegisterCLSID"
0x180005321  mov     [rsp+250h+cbMultiByte], eax
0x180005325  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x18000532c  mov     r8d, 24Fh
0x180005332  mov     [rsp+250h+lpMultiByteStr], rdi
0x180005337  call    cs:__imp_PuDbgPrint
0x18000533d  lea     rdx, [rsp+250h+Destination]; lpSubKey
0x180005342  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005349  call    cs:__imp_RegDeleteKeyA
0x18000534f  mov     edi, eax
0x180005351  test    eax, eax
0x180005353  jz      short loc_18000539B
0x180005355  test    byte ptr cs:g_dwDebugFlags, 3
0x18000535c  jz      short loc_18000539B
0x18000535e  test    eax, eax
0x180005360  jle     short loc_18000536A
0x180005362  movzx   eax, di
0x180005365  or      eax, 80070000h
0x18000536a  mov     rcx, cs:g_pDebug
0x180005371  lea     r9, aWamregregistry_0; "WamRegRegistryConfig::UnRegisterCLSID"
0x180005378  mov     [rsp+250h+cbMultiByte], eax
0x18000537c  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180005383  lea     rax, aError08x; "error = %08x\n"
0x18000538a  mov     r8d, 256h
0x180005390  mov     [rsp+250h+lpMultiByteStr], rax
0x180005395  call    cs:__imp_PuDbgPrint
0x18000539b  test    ebx, ebx
0x18000539d  js      short loc_1800053B2
0x18000539f  test    edi, edi
0x1800053a1  jz      short loc_1800053B2
0x1800053a3  jg      short loc_1800053A9
0x1800053a5  mov     ebx, edi
0x1800053a7  jmp     short loc_1800053B2
0x1800053a9  movzx   ebx, di
0x1800053ac  or      ebx, 80070000h
0x1800053b2  mov     eax, ebx
0x1800053b4  mov     rcx, [rbp+150h+var_30]
0x1800053bb  xor     rcx, rsp; StackCookie
0x1800053be  call    __security_check_cookie
0x1800053c3  add     rsp, 238h
0x1800053ca  pop     rdi
0x1800053cb  pop     rsi
0x1800053cc  pop     rbx
0x1800053cd  pop     rbp
0x1800053ce  retn
```
