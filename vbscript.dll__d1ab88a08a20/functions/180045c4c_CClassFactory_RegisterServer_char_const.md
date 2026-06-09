# CClassFactory::RegisterServer(char const *)

- ea: `0x180045c4c`
- end: `0x18004644b`
- name: `?RegisterServer@CClassFactory@@QEAAJPEBD@Z`
- size: `2047`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, BYTE *lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058840`

## callees

- `0x1800455dc`
- `0x180045c4c`
- `0x180051680`
- `0x1800518a0`
- `0x180079490`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x180045cc0`
- `KERNEL32!GetModuleHandleA` at `0x180045cc0`
- `KERNEL32!GetModuleFileNameA` at `0x180045cd9`
- `KERNEL32!GetModuleFileNameA` at `0x180045cd9`
- `ADVAPI32!RegOpenKeyExA` at `0x1800460d6`
- `ADVAPI32!RegOpenKeyExA` at `0x1800460d6`
- `ADVAPI32!RegSetValueExA` at `0x180045dc6`
- `ADVAPI32!RegSetValueExA` at `0x180045e33`
- `ADVAPI32!RegSetValueExA` at `0x180045faf`
- `ADVAPI32!RegSetValueExA` at `0x180046025`
- `ADVAPI32!RegSetValueExA` at `0x180046099`
- `ADVAPI32!RegSetValueExA` at `0x180046134`
- `ADVAPI32!RegSetValueExA` at `0x1800461f1`
- `ADVAPI32!RegSetValueExA` at `0x180046273`
- `ADVAPI32!RegSetValueExA` at `0x180046327`
- `ADVAPI32!RegSetValueExA` at `0x180045dc6`
- `ADVAPI32!RegSetValueExA` at `0x180045e33`
- `ADVAPI32!RegSetValueExA` at `0x180045faf`
- `ADVAPI32!RegSetValueExA` at `0x180046025`
- `ADVAPI32!RegSetValueExA` at `0x180046099`
- `ADVAPI32!RegSetValueExA` at `0x180046134`
- `ADVAPI32!RegSetValueExA` at `0x1800461f1`
- `ADVAPI32!RegSetValueExA` at `0x180046273`
- `ADVAPI32!RegSetValueExA` at `0x180046327`
- `ADVAPI32!RegCreateKeyExA` at `0x180045d3b`
- `ADVAPI32!RegCreateKeyExA` at `0x180045d83`
- `ADVAPI32!RegCreateKeyExA` at `0x180045e06`
- `ADVAPI32!RegCreateKeyExA` at `0x180045edf`
- `ADVAPI32!RegCreateKeyExA` at `0x180045f20`
- `ADVAPI32!RegCreateKeyExA` at `0x180045f63`
- `ADVAPI32!RegCreateKeyExA` at `0x180045fed`
- `ADVAPI32!RegCreateKeyExA` at `0x18004606f`
- `ADVAPI32!RegCreateKeyExA` at `0x1800461bc`
- `ADVAPI32!RegCreateKeyExA` at `0x18004623e`
- `ADVAPI32!RegCreateKeyExA` at `0x1800462ed`
- `ADVAPI32!RegCreateKeyExA` at `0x180045d3b`
- `ADVAPI32!RegCreateKeyExA` at `0x180045d83`
- `ADVAPI32!RegCreateKeyExA` at `0x180045e06`
- `ADVAPI32!RegCreateKeyExA` at `0x180045edf`
- `ADVAPI32!RegCreateKeyExA` at `0x180045f20`
- `ADVAPI32!RegCreateKeyExA` at `0x180045f63`
- `ADVAPI32!RegCreateKeyExA` at `0x180045fed`
- `ADVAPI32!RegCreateKeyExA` at `0x18004606f`
- `ADVAPI32!RegCreateKeyExA` at `0x1800461bc`
- `ADVAPI32!RegCreateKeyExA` at `0x18004623e`
- `ADVAPI32!RegCreateKeyExA` at `0x1800462ed`
- `ADVAPI32!RegCloseKey` at `0x180045d9c`
- `ADVAPI32!RegCloseKey` at `0x180045e44`
- `ADVAPI32!RegCloseKey` at `0x180045e55`
- `ADVAPI32!RegCloseKey` at `0x180045e6e`
- `ADVAPI32!RegCloseKey` at `0x180045f78`
- `ADVAPI32!RegCloseKey` at `0x180046035`
- `ADVAPI32!RegCloseKey` at `0x1800460a9`
- `ADVAPI32!RegCloseKey` at `0x1800460eb`
- `ADVAPI32!RegCloseKey` at `0x1800460fc`
- `ADVAPI32!RegCloseKey` at `0x180046145`
- `ADVAPI32!RegCloseKey` at `0x180046156`
- `ADVAPI32!RegCloseKey` at `0x180046202`
- `ADVAPI32!RegCloseKey` at `0x180046284`
- `ADVAPI32!RegCloseKey` at `0x180046295`
- `ADVAPI32!RegCloseKey` at `0x1800462a6`
- `ADVAPI32!RegCloseKey` at `0x180046340`
- `ADVAPI32!RegCloseKey` at `0x180045d9c`
- `ADVAPI32!RegCloseKey` at `0x180045e44`
- `ADVAPI32!RegCloseKey` at `0x180045e55`
- `ADVAPI32!RegCloseKey` at `0x180045e6e`
- `ADVAPI32!RegCloseKey` at `0x180045f78`
- `ADVAPI32!RegCloseKey` at `0x180046035`
- `ADVAPI32!RegCloseKey` at `0x1800460a9`
- `ADVAPI32!RegCloseKey` at `0x1800460eb`
- `ADVAPI32!RegCloseKey` at `0x1800460fc`
- `ADVAPI32!RegCloseKey` at `0x180046145`
- `ADVAPI32!RegCloseKey` at `0x180046156`
- `ADVAPI32!RegCloseKey` at `0x180046202`
- `ADVAPI32!RegCloseKey` at `0x180046284`
- `ADVAPI32!RegCloseKey` at `0x180046295`
- `ADVAPI32!RegCloseKey` at `0x1800462a6`
- `ADVAPI32!RegCloseKey` at `0x180046340`

## string_xrefs

- `0x180045dde`: `CLSID`
- `0x180045eb7`: `CLSID`
- `0x18004611e`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall CClassFactory::RegisterServer(CClassFactory *this, BYTE *lpData)
{
  __int64 v2; // rax
  int v3; // r15d
  __int64 v4; // rdi
  __int64 v5; // r14
  __int64 v8; // rsi
  HMODULE ModuleHandleA; // rax
  DWORD ModuleFileNameA; // r12d
  HKEY v11; // rcx
  const BYTE *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  const CHAR *v17; // rdx
  const BYTE *v18; // rcx
  LSTATUS v19; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v23[2]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v24[2]; // [rsp+80h] [rbp-80h] BYREF
  CHAR Filename[512]; // [rsp+90h] [rbp-70h] BYREF

  v2 = *((_QWORD *)this + 4);
  v3 = 0;
  v4 = -1;
  hKey = 0;
  v5 = -1;
  phkResult = 0;
  v22[0] = 0;
  v24[0] = 0;
  do
    ++v5;
  while ( *(_BYTE *)(v2 + v5) );
  v8 = -1;
  do
    ++v8;
  while ( *(_BYTE *)(*((_QWORD *)this + 3) + v8) );
  ModuleHandleA = GetModuleHandleA(*((LPCSTR *)this + 6));
  ModuleFileNameA = GetModuleFileNameA(ModuleHandleA, Filename, 0x200u);
  if ( !ModuleFileNameA )
    return 2147500037LL;
  CClassFactory::UnregisterServer(this);
  while ( v3 < *((_DWORD *)this + 16) )
  {
    if ( RegCreateKeyExA(
           HKEY_CLASSES_ROOT,
           *(LPCSTR *)(*((_QWORD *)this + 7) + 8LL * v3),
           0,
           0,
           0,
           0x2000000u,
           0,
           &hKey,
           0) )
    {
      return 2147500037LL;
    }
    if ( RegCreateKeyExA(hKey, "OLEScript", 0, 0, 0, 0x2000000u, 0, &phkResult, 0) )
      goto LABEL_12;
    RegCloseKey(phkResult);
    RegSetValueExA(hKey, 0, 0, 1u, *((const BYTE **)this + 4), v5);
    if ( RegCreateKeyExA(hKey, "CLSID", 0, 0, 0, 2u, 0, &phkResult, 0) )
      goto LABEL_12;
    RegSetValueExA(phkResult, 0, 0, 1u, *((const BYTE **)this + 3), v8);
    RegCloseKey(phkResult);
    RegCloseKey(hKey);
    ++v3;
  }
  if ( RegCreateKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
    return 2147500037LL;
  if ( RegCreateKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0, 0, 0x2000000u, 0, &phkResult, 0) )
  {
LABEL_12:
    v11 = hKey;
LABEL_13:
    RegCloseKey(v11);
    return 2147500037LL;
  }
  if ( RegCreateKeyExA(phkResult, "OLEScript", 0, 0, 0, 0x2000000u, 0, v22, 0) )
  {
LABEL_18:
    RegCloseKey(hKey);
    v11 = phkResult;
    goto LABEL_13;
  }
  RegSetValueExA(phkResult, 0, 0, 1u, *((const BYTE **)this + 4), v5);
  if ( !RegCreateKeyExA(phkResult, "ProgID", 0, 0, 0, 2u, 0, v24, 0) )
  {
    v13 = (const BYTE *)**((_QWORD **)this + 7);
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    RegSetValueExA(v24[0], 0, 0, 1u, v13, v14);
    RegCloseKey(v24[0]);
  }
  if ( !RegCreateKeyExA(phkResult, "InprocServer32", 0, 0, 0, 2u, 0, v24, 0) )
  {
    RegSetValueExA(v24[0], 0, 0, 1u, (const BYTE *)Filename, ModuleFileNameA);
    RegCloseKey(v24[0]);
  }
  v23[0] = 0;
  if ( RegOpenKeyExA(phkResult, "InprocServer32", 0, 2u, v23) )
  {
    RegCloseKey(v22[0]);
    RegCloseKey(phkResult);
    goto LABEL_12;
  }
  v15 = -1;
  do
    ++v15;
  while ( lpData[v15] );
  RegSetValueExA(v23[0], "ThreadingModel", 0, 1u, lpData, v15);
  RegCloseKey(v23[0]);
  RegCloseKey(v22[0]);
  v16 = *(_QWORD *)((char *)this + 68) - *(_QWORD *)&CLSID_VBScriptRegExp.Data1;
  if ( !v16 )
    v16 = *(_QWORD *)((char *)this + 76) - *(_QWORD *)CLSID_VBScriptRegExp.Data4;
  if ( !v16 )
  {
    if ( RegCreateKeyExA(phkResult, "TypeLib", 0, 0, 0, 0x2000000u, 0, v22, 0) )
      goto LABEL_18;
    RegSetValueExA(v22[0], 0, 0, 1u, "{3F4DACA7-160D-11D2-A8E9-00104B365C9F}", 0x26u);
    RegCloseKey(v22[0]);
    if ( RegCreateKeyExA(phkResult, "Version", 0, 0, 0, 0x2000000u, 0, v22, 0) )
      goto LABEL_18;
    RegSetValueExA(v22[0], 0, 0, 1u, "5.5", 3u);
    RegCloseKey(v22[0]);
  }
  RegCloseKey(phkResult);
  RegCloseKey(hKey);
  v17 = (const CHAR *)*((_QWORD *)this + 5);
  if ( !v17 )
    goto LABEL_41;
  if ( RegCreateKeyExA(HKEY_CLASSES_ROOT, v17, 0, 0, 0, 2u, 0, &hKey, 0) )
    return 2147500037LL;
  v18 = (const BYTE *)**((_QWORD **)this + 7);
  do
    ++v4;
  while ( v18[v4] );
  v19 = RegSetValueExA(hKey, 0, 0, 1u, v18, v4);
  v11 = hKey;
  if ( v19 )
    goto LABEL_13;
  RegCloseKey(hKey);
LABEL_41:
  if ( (*((_BYTE *)this + 84) & 1) != 0 )
  {
    *(GUID *)v23 = CATID_ActiveScript;
    CreateComponentCategory(v23, L"Active Scripting Engine");
    *(GUID *)v23 = CATID_ActiveScript;
    RegisterCLSIDInCategory((char *)this + 68, v23);
  }
  if ( (*((_BYTE *)this + 84) & 2) != 0 )
  {
    *(GUID *)v23 = CATID_ActiveScriptParse;
    CreateComponentCategory(v23, L"Active Scripting Engine with Parsing");
    *(GUID *)v23 = CATID_ActiveScriptParse;
    RegisterCLSIDInCategory((char *)this + 68, v23);
  }
  if ( (*((_BYTE *)this + 84) & 4) != 0 )
  {
    *(GUID *)v23 = CATID_ActiveScriptAuthor;
    CreateComponentCategory(v23, L"Active Scripting Engine with Authoring");
    *(GUID *)v23 = CATID_ActiveScriptAuthor;
    RegisterCLSIDInCategory((char *)this + 68, v23);
  }
  if ( (*((_BYTE *)this + 84) & 8) != 0 )
  {
    *(GUID *)v23 = CATID_ActiveScriptEncode;
    CreateComponentCategory(v23, L"Active Scripting Engine with Encoding");
    *(GUID *)v23 = CATID_ActiveScriptEncode;
    RegisterCLSIDInCategory((char *)this + 68, v23);
  }
  return 0;
}

```

## disassembly

```asm
0x180045c4c  mov     [rsp-8+arg_10], rbx
0x180045c51  push    rbp
0x180045c52  push    rsi
0x180045c53  push    rdi
0x180045c54  push    r12
0x180045c56  push    r13
0x180045c58  push    r14
0x180045c5a  push    r15
0x180045c5c  lea     rbp, [rsp-1A0h]
0x180045c64  sub     rsp, 2A0h
0x180045c6b  mov     rax, cs:__security_cookie
0x180045c72  xor     rax, rsp
0x180045c75  mov     [rbp+1D0h+var_40], rax
0x180045c7c  mov     rax, [rcx+20h]
0x180045c80  xor     r15d, r15d
0x180045c83  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180045c87  mov     [rsp+2D0h+hKey], r15
0x180045c8c  mov     r14, rdi
0x180045c8f  mov     [rsp+2D0h+var_278], r15
0x180045c94  mov     r13, rdx
0x180045c97  mov     [rsp+2D0h+var_270], r15
0x180045c9c  mov     rbx, rcx
0x180045c9f  mov     [rbp+1D0h+var_250], r15
0x180045ca3  inc     r14
0x180045ca6  cmp     [rax+r14], r15b
0x180045caa  jnz     short loc_180045CA3
0x180045cac  mov     rax, [rcx+18h]
0x180045cb0  mov     rsi, rdi
0x180045cb3  inc     rsi
0x180045cb6  cmp     [rax+rsi], r15b
0x180045cba  jnz     short loc_180045CB3
0x180045cbc  mov     rcx, [rcx+30h]; lpModuleName
0x180045cc0  call    cs:__imp_GetModuleHandleA
0x180045cc7  nop     dword ptr [rax+rax+00h]
0x180045ccc  mov     r8d, 200h; nSize
0x180045cd2  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x180045cd6  mov     rcx, rax; hModule
0x180045cd9  call    cs:__imp_GetModuleFileNameA
0x180045ce0  nop     dword ptr [rax+rax+00h]
0x180045ce5  mov     r12d, eax
0x180045ce8  test    eax, eax
0x180045cea  jz      loc_180045E7A
0x180045cf0  mov     rcx, rbx; this
0x180045cf3  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x180045cf8  xor     r9d, r9d; lpClass
0x180045cfb  cmp     r15d, [rbx+40h]
0x180045cff  jge     loc_180045EAA
0x180045d05  mov     rdx, [rbx+38h]
0x180045d09  lea     rcx, [rsp+2D0h+hKey]
0x180045d0e  xor     r8d, r8d; Reserved
0x180045d11  movsxd  rax, r15d
0x180045d14  mov     [rsp+2D0h+lpdwDisposition], r8; lpdwDisposition
0x180045d19  mov     [rsp+2D0h+phkResult], rcx; phkResult
0x180045d1e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180045d25  mov     [rsp+2D0h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180045d2a  mov     rdx, [rdx+rax*8]; lpSubKey
0x180045d2e  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x180045d36  mov     [rsp+2D0h+dwOptions], r8d; dwOptions
0x180045d3b  call    cs:__imp_RegCreateKeyExA
0x180045d42  nop     dword ptr [rax+rax+00h]
0x180045d47  xor     ecx, ecx
0x180045d49  test    eax, eax
0x180045d4b  jnz     loc_180045E7A
0x180045d51  mov     [rsp+2D0h+lpdwDisposition], rcx; lpdwDisposition
0x180045d56  lea     rax, [rsp+2D0h+var_278]
0x180045d5b  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180045d60  lea     rdx, aOlescript; "OLEScript"
0x180045d67  mov     [rsp+2D0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180045d6c  xor     r9d, r9d; lpClass
0x180045d6f  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x180045d77  xor     r8d, r8d; Reserved
0x180045d7a  mov     [rsp+2D0h+dwOptions], ecx; dwOptions
0x180045d7e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180045d83  call    cs:__imp_RegCreateKeyExA
0x180045d8a  nop     dword ptr [rax+rax+00h]
0x180045d8f  test    eax, eax
0x180045d91  jnz     loc_180045E69
0x180045d97  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180045d9c  call    cs:__imp_RegCloseKey
0x180045da3  nop     dword ptr [rax+rax+00h]
0x180045da8  mov     rax, [rbx+20h]
0x180045dac  mov     r9d, 1; dwType
0x180045db2  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180045db7  xor     r8d, r8d; Reserved
0x180045dba  mov     [rsp+2D0h+samDesired], r14d; cbData
0x180045dbf  xor     edx, edx; lpValueName
0x180045dc1  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180045dc6  call    cs:__imp_RegSetValueExA
0x180045dcd  nop     dword ptr [rax+rax+00h]
0x180045dd2  xor     ecx, ecx
0x180045dd4  lea     rax, [rsp+2D0h+var_278]
0x180045dd9  mov     [rsp+2D0h+lpdwDisposition], rcx; lpdwDisposition
0x180045dde  lea     rdx, aClsid; "CLSID"
0x180045de5  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180045dea  xor     r9d, r9d; lpClass
0x180045ded  mov     [rsp+2D0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180045df2  xor     r8d, r8d; Reserved
0x180045df5  mov     [rsp+2D0h+samDesired], 2; samDesired
0x180045dfd  mov     [rsp+2D0h+dwOptions], ecx; dwOptions
0x180045e01  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180045e06  call    cs:__imp_RegCreateKeyExA
0x180045e0d  nop     dword ptr [rax+rax+00h]
0x180045e12  test    eax, eax
0x180045e14  jnz     short loc_180045E69
0x180045e16  mov     rax, [rbx+18h]
0x180045e1a  mov     r9d, 1; dwType
0x180045e20  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180045e25  xor     r8d, r8d; Reserved
0x180045e28  mov     [rsp+2D0h+samDesired], esi; cbData
0x180045e2c  xor     edx, edx; lpValueName
0x180045e2e  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180045e33  call    cs:__imp_RegSetValueExA
0x180045e3a  nop     dword ptr [rax+rax+00h]
0x180045e3f  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180045e44  call    cs:__imp_RegCloseKey
0x180045e4b  nop     dword ptr [rax+rax+00h]
0x180045e50  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180045e55  call    cs:__imp_RegCloseKey
0x180045e5c  nop     dword ptr [rax+rax+00h]
0x180045e61  inc     r15d
0x180045e64  jmp     loc_180045CF8
0x180045e69  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180045e6e  call    cs:__imp_RegCloseKey
0x180045e75  nop     dword ptr [rax+rax+00h]
0x180045e7a  mov     eax, 80004005h
0x180045e7f  mov     rcx, [rbp+1D0h+var_40]
0x180045e86  xor     rcx, rsp; StackCookie
0x180045e89  call    __security_check_cookie
0x180045e8e  mov     rbx, [rsp+2D0h+arg_10]
0x180045e96  add     rsp, 2A0h
0x180045e9d  pop     r15
0x180045e9f  pop     r14
0x180045ea1  pop     r13
0x180045ea3  pop     r12
0x180045ea5  pop     rdi
0x180045ea6  pop     rsi
0x180045ea7  pop     rbp
0x180045ea8  retn
0x180045eaa  xor     r15d, r15d
0x180045ead  lea     rax, [rsp+2D0h+hKey]
0x180045eb2  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180045eb7  lea     rdx, aClsid; "CLSID"
0x180045ebe  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180045ec3  xor     r8d, r8d; Reserved
0x180045ec6  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180045ecb  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180045ed2  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x180045eda  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180045edf  call    cs:__imp_RegCreateKeyExA
0x180045ee6  nop     dword ptr [rax+rax+00h]
0x180045eeb  test    eax, eax
0x180045eed  jnz     short loc_180045E7A
0x180045eef  mov     rdx, [rbx+18h]; lpSubKey
0x180045ef3  lea     rax, [rsp+2D0h+var_278]
0x180045ef8  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180045efd  mov     esi, 2000000h
0x180045f02  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180045f07  xor     r9d, r9d; lpClass
0x180045f0a  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180045f0f  xor     r8d, r8d; Reserved
0x180045f12  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180045f17  mov     [rsp+2D0h+samDesired], esi; samDesired
0x180045f1b  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180045f20  call    cs:__imp_RegCreateKeyExA
0x180045f27  nop     dword ptr [rax+rax+00h]
0x180045f2c  test    eax, eax
0x180045f2e  jnz     loc_180045E69
0x180045f34  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180045f39  lea     rax, [rsp+2D0h+var_270]
0x180045f3e  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180045f43  lea     rdx, aOlescript; "OLEScript"
0x180045f4a  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180045f4f  xor     r9d, r9d; lpClass
0x180045f52  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180045f57  xor     r8d, r8d; Reserved
0x180045f5a  mov     [rsp+2D0h+samDesired], esi; samDesired
0x180045f5e  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180045f63  call    cs:__imp_RegCreateKeyExA
0x180045f6a  nop     dword ptr [rax+rax+00h]
0x180045f6f  test    eax, eax
0x180045f71  jz      short loc_180045F8E
0x180045f73  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180045f78  call    cs:__imp_RegCloseKey
0x180045f7f  nop     dword ptr [rax+rax+00h]
0x180045f84  mov     rcx, [rsp+2D0h+var_278]
0x180045f89  jmp     loc_180045E6E
0x180045f8e  mov     rax, [rbx+20h]
0x180045f92  xor     r8d, r8d; Reserved
0x180045f95  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180045f9a  xor     edx, edx; lpValueName
0x180045f9c  mov     [rsp+2D0h+samDesired], r14d; cbData
0x180045fa1  mov     r14d, 1
0x180045fa7  mov     r9d, r14d; dwType
0x180045faa  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180045faf  call    cs:__imp_RegSetValueExA
0x180045fb6  nop     dword ptr [rax+rax+00h]
0x180045fbb  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180045fc0  lea     rax, [rbp+1D0h+var_250]
0x180045fc4  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180045fc9  lea     esi, [r14+1]
0x180045fcd  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180045fd2  lea     rdx, aProgid; "ProgID"
0x180045fd9  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180045fde  xor     r9d, r9d; lpClass
0x180045fe1  mov     [rsp+2D0h+samDesired], esi; samDesired
0x180045fe5  xor     r8d, r8d; Reserved
0x180045fe8  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180045fed  call    cs:__imp_RegCreateKeyExA
0x180045ff4  nop     dword ptr [rax+rax+00h]
0x180045ff9  test    eax, eax
0x180045ffb  jnz     short loc_180046041
0x180045ffd  mov     rax, [rbx+38h]
0x180046001  mov     rcx, [rax]
0x180046004  mov     rax, rdi
0x180046007  inc     rax
0x18004600a  cmp     [rcx+rax], r15b
0x18004600e  jnz     short loc_180046007
0x180046010  mov     [rsp+2D0h+samDesired], eax; cbData
0x180046014  mov     r9d, r14d; dwType
0x180046017  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x18004601c  xor     r8d, r8d; Reserved
0x18004601f  mov     rcx, [rbp+1D0h+var_250]; hKey
0x180046023  xor     edx, edx; lpValueName
0x180046025  call    cs:__imp_RegSetValueExA
0x18004602c  nop     dword ptr [rax+rax+00h]
0x180046031  mov     rcx, [rbp+1D0h+var_250]; hKey
0x180046035  call    cs:__imp_RegCloseKey
0x18004603c  nop     dword ptr [rax+rax+00h]
0x180046041  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180046046  lea     rax, [rbp+1D0h+var_250]
0x18004604a  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x18004604f  lea     rdx, aInprocserver32; "InprocServer32"
0x180046056  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18004605b  xor     r9d, r9d; lpClass
0x18004605e  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180046063  xor     r8d, r8d; Reserved
0x180046066  mov     [rsp+2D0h+samDesired], esi; samDesired
0x18004606a  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x18004606f  call    cs:__imp_RegCreateKeyExA
0x180046076  nop     dword ptr [rax+rax+00h]
0x18004607b  test    eax, eax
0x18004607d  jnz     short loc_1800460B5
0x18004607f  mov     rcx, [rbp+1D0h+var_250]; hKey
0x180046083  lea     rax, [rbp+1D0h+Filename]
0x180046087  mov     [rsp+2D0h+samDesired], r12d; cbData
0x18004608c  mov     r9d, r14d; dwType
0x18004608f  xor     r8d, r8d; Reserved
0x180046092  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180046097  xor     edx, edx; lpValueName
0x180046099  call    cs:__imp_RegSetValueExA
0x1800460a0  nop     dword ptr [rax+rax+00h]
0x1800460a5  mov     rcx, [rbp+1D0h+var_250]; hKey
0x1800460a9  call    cs:__imp_RegCloseKey
0x1800460b0  nop     dword ptr [rax+rax+00h]
0x1800460b5  mov     rcx, [rsp+2D0h+var_278]; hKey
0x1800460ba  lea     rax, [rsp+2D0h+var_260]
0x1800460bf  mov     r9d, esi; samDesired
0x1800460c2  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x1800460c7  xor     r8d, r8d; ulOptions
0x1800460ca  mov     [rsp+2D0h+var_260], r15
0x1800460cf  lea     rdx, aInprocserver32; "InprocServer32"
0x1800460d6  call    cs:__imp_RegOpenKeyExA
0x1800460dd  nop     dword ptr [rax+rax+00h]
0x1800460e2  test    eax, eax
0x1800460e4  jz      short loc_18004610D
0x1800460e6  mov     rcx, [rsp+2D0h+var_270]; hKey
0x1800460eb  call    cs:__imp_RegCloseKey
0x1800460f2  nop     dword ptr [rax+rax+00h]
0x1800460f7  mov     rcx, [rsp+2D0h+var_278]; hKey
0x1800460fc  call    cs:__imp_RegCloseKey
0x180046103  nop     dword ptr [rax+rax+00h]
0x180046108  jmp     loc_180045E69
0x18004610d  mov     rax, rdi
0x180046110  inc     rax
0x180046113  cmp     [rax+r13], r15b
0x180046117  jnz     short loc_180046110
0x180046119  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18004611e  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180046125  mov     [rsp+2D0h+samDesired], eax; cbData
0x180046129  mov     r9d, r14d; dwType
0x18004612c  xor     r8d, r8d; Reserved
0x18004612f  mov     qword ptr [rsp+2D0h+dwOptions], r13; lpData
0x180046134  call    cs:__imp_RegSetValueExA
0x18004613b  nop     dword ptr [rax+rax+00h]
0x180046140  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180046145  call    cs:__imp_RegCloseKey
0x18004614c  nop     dword ptr [rax+rax+00h]
0x180046151  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180046156  call    cs:__imp_RegCloseKey
0x18004615d  nop     dword ptr [rax+rax+00h]
0x180046162  lea     rsi, [rbx+44h]
0x180046166  mov     rax, [rsi]
0x180046169  sub     rax, qword ptr cs:CLSID_VBScriptRegExp.Data1
0x180046170  jnz     short loc_18004617D
0x180046172  mov     rax, [rsi+8]
0x180046176  sub     rax, qword ptr cs:CLSID_VBScriptRegExp.Data4
0x18004617d  test    rax, rax
0x180046180  jnz     loc_180046290
0x180046186  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18004618b  lea     rax, [rsp+2D0h+var_270]
  ... truncated ...
```
