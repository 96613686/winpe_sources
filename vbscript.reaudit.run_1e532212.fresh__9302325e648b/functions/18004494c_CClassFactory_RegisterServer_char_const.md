# CClassFactory::RegisterServer(char const *)

- ea: `0x18004494c`
- end: `0x18004505c`
- name: `?RegisterServer@CClassFactory@@QEAAJPEBD@Z`
- size: `1808`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, BYTE *lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180056e40`

## callees

- `0x180044378`
- `0x18004494c`
- `0x18004feec`
- `0x1800500f0`
- `0x1800767a0`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x1800449c0`
- `KERNEL32!GetModuleHandleA` at `0x1800449c0`
- `KERNEL32!GetModuleFileNameA` at `0x1800449d3`
- `KERNEL32!GetModuleFileNameA` at `0x1800449d3`
- `ADVAPI32!RegOpenKeyExA` at `0x180044d51`
- `ADVAPI32!RegOpenKeyExA` at `0x180044d51`
- `ADVAPI32!RegSetValueExA` at `0x180044aa8`
- `ADVAPI32!RegSetValueExA` at `0x180044b09`
- `ADVAPI32!RegSetValueExA` at `0x180044c54`
- `ADVAPI32!RegSetValueExA` at `0x180044cbe`
- `ADVAPI32!RegSetValueExA` at `0x180044d20`
- `ADVAPI32!RegSetValueExA` at `0x180044d9d`
- `ADVAPI32!RegSetValueExA` at `0x180044e42`
- `ADVAPI32!RegSetValueExA` at `0x180044eb2`
- `ADVAPI32!RegSetValueExA` at `0x180044f44`
- `ADVAPI32!RegSetValueExA` at `0x180044aa8`
- `ADVAPI32!RegSetValueExA` at `0x180044b09`
- `ADVAPI32!RegSetValueExA` at `0x180044c54`
- `ADVAPI32!RegSetValueExA` at `0x180044cbe`
- `ADVAPI32!RegSetValueExA` at `0x180044d20`
- `ADVAPI32!RegSetValueExA` at `0x180044d9d`
- `ADVAPI32!RegSetValueExA` at `0x180044e42`
- `ADVAPI32!RegSetValueExA` at `0x180044eb2`
- `ADVAPI32!RegSetValueExA` at `0x180044f44`
- `ADVAPI32!RegCreateKeyExA` at `0x180044a2f`
- `ADVAPI32!RegCreateKeyExA` at `0x180044a71`
- `ADVAPI32!RegCreateKeyExA` at `0x180044ae2`
- `ADVAPI32!RegCreateKeyExA` at `0x180044b9c`
- `ADVAPI32!RegCreateKeyExA` at `0x180044bd7`
- `ADVAPI32!RegCreateKeyExA` at `0x180044c14`
- `ADVAPI32!RegCreateKeyExA` at `0x180044c8c`
- `ADVAPI32!RegCreateKeyExA` at `0x180044cfc`
- `ADVAPI32!RegCreateKeyExA` at `0x180044e13`
- `ADVAPI32!RegCreateKeyExA` at `0x180044e83`
- `ADVAPI32!RegCreateKeyExA` at `0x180044f10`
- `ADVAPI32!RegCreateKeyExA` at `0x180044a2f`
- `ADVAPI32!RegCreateKeyExA` at `0x180044a71`
- `ADVAPI32!RegCreateKeyExA` at `0x180044ae2`
- `ADVAPI32!RegCreateKeyExA` at `0x180044b9c`
- `ADVAPI32!RegCreateKeyExA` at `0x180044bd7`
- `ADVAPI32!RegCreateKeyExA` at `0x180044c14`
- `ADVAPI32!RegCreateKeyExA` at `0x180044c8c`
- `ADVAPI32!RegCreateKeyExA` at `0x180044cfc`
- `ADVAPI32!RegCreateKeyExA` at `0x180044e13`
- `ADVAPI32!RegCreateKeyExA` at `0x180044e83`
- `ADVAPI32!RegCreateKeyExA` at `0x180044f10`
- `ADVAPI32!RegCloseKey` at `0x180044a84`
- `ADVAPI32!RegCloseKey` at `0x180044b14`
- `ADVAPI32!RegCloseKey` at `0x180044b1f`
- `ADVAPI32!RegCloseKey` at `0x180044b32`
- `ADVAPI32!RegCloseKey` at `0x180044c23`
- `ADVAPI32!RegCloseKey` at `0x180044cc8`
- `ADVAPI32!RegCloseKey` at `0x180044d2a`
- `ADVAPI32!RegCloseKey` at `0x180044d60`
- `ADVAPI32!RegCloseKey` at `0x180044d6b`
- `ADVAPI32!RegCloseKey` at `0x180044da8`
- `ADVAPI32!RegCloseKey` at `0x180044db3`
- `ADVAPI32!RegCloseKey` at `0x180044e4d`
- `ADVAPI32!RegCloseKey` at `0x180044ebd`
- `ADVAPI32!RegCloseKey` at `0x180044ec8`
- `ADVAPI32!RegCloseKey` at `0x180044ed3`
- `ADVAPI32!RegCloseKey` at `0x180044f57`
- `ADVAPI32!RegCloseKey` at `0x180044a84`
- `ADVAPI32!RegCloseKey` at `0x180044b14`
- `ADVAPI32!RegCloseKey` at `0x180044b1f`
- `ADVAPI32!RegCloseKey` at `0x180044b32`
- `ADVAPI32!RegCloseKey` at `0x180044c23`
- `ADVAPI32!RegCloseKey` at `0x180044cc8`
- `ADVAPI32!RegCloseKey` at `0x180044d2a`
- `ADVAPI32!RegCloseKey` at `0x180044d60`
- `ADVAPI32!RegCloseKey` at `0x180044d6b`
- `ADVAPI32!RegCloseKey` at `0x180044da8`
- `ADVAPI32!RegCloseKey` at `0x180044db3`
- `ADVAPI32!RegCloseKey` at `0x180044e4d`
- `ADVAPI32!RegCloseKey` at `0x180044ebd`
- `ADVAPI32!RegCloseKey` at `0x180044ec8`
- `ADVAPI32!RegCloseKey` at `0x180044ed3`
- `ADVAPI32!RegCloseKey` at `0x180044f57`

## string_xrefs

- `0x180044aba`: `CLSID`
- `0x180044b74`: `CLSID`
- `0x180044d87`: `ThreadingModel`

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
0x18004494c  mov     [rsp-8+arg_10], rbx
0x180044951  push    rbp
0x180044952  push    rsi
0x180044953  push    rdi
0x180044954  push    r12
0x180044956  push    r13
0x180044958  push    r14
0x18004495a  push    r15
0x18004495c  lea     rbp, [rsp-1A0h]
0x180044964  sub     rsp, 2A0h
0x18004496b  mov     rax, cs:__security_cookie
0x180044972  xor     rax, rsp
0x180044975  mov     [rbp+1D0h+var_40], rax
0x18004497c  mov     rax, [rcx+20h]
0x180044980  xor     r15d, r15d
0x180044983  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180044987  mov     [rsp+2D0h+hKey], r15
0x18004498c  mov     r14, rdi
0x18004498f  mov     [rsp+2D0h+var_278], r15
0x180044994  mov     r13, rdx
0x180044997  mov     [rsp+2D0h+var_270], r15
0x18004499c  mov     rbx, rcx
0x18004499f  mov     [rbp+1D0h+var_250], r15
0x1800449a3  inc     r14
0x1800449a6  cmp     [rax+r14], r15b
0x1800449aa  jnz     short loc_1800449A3
0x1800449ac  mov     rax, [rcx+18h]
0x1800449b0  mov     rsi, rdi
0x1800449b3  inc     rsi
0x1800449b6  cmp     [rax+rsi], r15b
0x1800449ba  jnz     short loc_1800449B3
0x1800449bc  mov     rcx, [rcx+30h]; lpModuleName
0x1800449c0  call    cs:__imp_GetModuleHandleA
0x1800449c6  mov     r8d, 200h; nSize
0x1800449cc  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x1800449d0  mov     rcx, rax; hModule
0x1800449d3  call    cs:__imp_GetModuleFileNameA
0x1800449d9  mov     r12d, eax
0x1800449dc  test    eax, eax
0x1800449de  jz      loc_180044B38
0x1800449e4  mov     rcx, rbx; this
0x1800449e7  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x1800449ec  xor     r9d, r9d; lpClass
0x1800449ef  cmp     r15d, [rbx+40h]
0x1800449f3  jge     loc_180044B67
0x1800449f9  mov     rdx, [rbx+38h]
0x1800449fd  lea     rcx, [rsp+2D0h+hKey]
0x180044a02  xor     r8d, r8d; Reserved
0x180044a05  movsxd  rax, r15d
0x180044a08  mov     [rsp+2D0h+lpdwDisposition], r8; lpdwDisposition
0x180044a0d  mov     [rsp+2D0h+phkResult], rcx; phkResult
0x180044a12  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180044a19  mov     [rsp+2D0h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180044a1e  mov     rdx, [rdx+rax*8]; lpSubKey
0x180044a22  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x180044a2a  mov     [rsp+2D0h+dwOptions], r8d; dwOptions
0x180044a2f  call    cs:__imp_RegCreateKeyExA
0x180044a35  xor     ecx, ecx
0x180044a37  test    eax, eax
0x180044a39  jnz     loc_180044B38
0x180044a3f  mov     [rsp+2D0h+lpdwDisposition], rcx; lpdwDisposition
0x180044a44  lea     rax, [rsp+2D0h+var_278]
0x180044a49  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044a4e  lea     rdx, aOlescript; "OLEScript"
0x180044a55  mov     [rsp+2D0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180044a5a  xor     r9d, r9d; lpClass
0x180044a5d  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x180044a65  xor     r8d, r8d; Reserved
0x180044a68  mov     [rsp+2D0h+dwOptions], ecx; dwOptions
0x180044a6c  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180044a71  call    cs:__imp_RegCreateKeyExA
0x180044a77  test    eax, eax
0x180044a79  jnz     loc_180044B2D
0x180044a7f  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044a84  call    cs:__imp_RegCloseKey
0x180044a8a  mov     rax, [rbx+20h]
0x180044a8e  mov     r9d, 1; dwType
0x180044a94  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180044a99  xor     r8d, r8d; Reserved
0x180044a9c  mov     [rsp+2D0h+samDesired], r14d; cbData
0x180044aa1  xor     edx, edx; lpValueName
0x180044aa3  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180044aa8  call    cs:__imp_RegSetValueExA
0x180044aae  xor     ecx, ecx
0x180044ab0  lea     rax, [rsp+2D0h+var_278]
0x180044ab5  mov     [rsp+2D0h+lpdwDisposition], rcx; lpdwDisposition
0x180044aba  lea     rdx, aClsid; "CLSID"
0x180044ac1  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044ac6  xor     r9d, r9d; lpClass
0x180044ac9  mov     [rsp+2D0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180044ace  xor     r8d, r8d; Reserved
0x180044ad1  mov     [rsp+2D0h+samDesired], 2; samDesired
0x180044ad9  mov     [rsp+2D0h+dwOptions], ecx; dwOptions
0x180044add  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180044ae2  call    cs:__imp_RegCreateKeyExA
0x180044ae8  test    eax, eax
0x180044aea  jnz     short loc_180044B2D
0x180044aec  mov     rax, [rbx+18h]
0x180044af0  mov     r9d, 1; dwType
0x180044af6  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044afb  xor     r8d, r8d; Reserved
0x180044afe  mov     [rsp+2D0h+samDesired], esi; cbData
0x180044b02  xor     edx, edx; lpValueName
0x180044b04  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180044b09  call    cs:__imp_RegSetValueExA
0x180044b0f  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044b14  call    cs:__imp_RegCloseKey
0x180044b1a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180044b1f  call    cs:__imp_RegCloseKey
0x180044b25  inc     r15d
0x180044b28  jmp     loc_1800449EC
0x180044b2d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180044b32  call    cs:__imp_RegCloseKey
0x180044b38  mov     eax, 80004005h
0x180044b3d  mov     rcx, [rbp+1D0h+var_40]
0x180044b44  xor     rcx, rsp; StackCookie
0x180044b47  call    __security_check_cookie
0x180044b4c  mov     rbx, [rsp+2D0h+arg_10]
0x180044b54  add     rsp, 2A0h
0x180044b5b  pop     r15
0x180044b5d  pop     r14
0x180044b5f  pop     r13
0x180044b61  pop     r12
0x180044b63  pop     rdi
0x180044b64  pop     rsi
0x180044b65  pop     rbp
0x180044b66  retn
0x180044b67  xor     r15d, r15d
0x180044b6a  lea     rax, [rsp+2D0h+hKey]
0x180044b6f  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180044b74  lea     rdx, aClsid; "CLSID"
0x180044b7b  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044b80  xor     r8d, r8d; Reserved
0x180044b83  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180044b88  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180044b8f  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x180044b97  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180044b9c  call    cs:__imp_RegCreateKeyExA
0x180044ba2  test    eax, eax
0x180044ba4  jnz     short loc_180044B38
0x180044ba6  mov     rdx, [rbx+18h]; lpSubKey
0x180044baa  lea     rax, [rsp+2D0h+var_278]
0x180044baf  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180044bb4  mov     esi, 2000000h
0x180044bb9  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180044bbe  xor     r9d, r9d; lpClass
0x180044bc1  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044bc6  xor     r8d, r8d; Reserved
0x180044bc9  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180044bce  mov     [rsp+2D0h+samDesired], esi; samDesired
0x180044bd2  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180044bd7  call    cs:__imp_RegCreateKeyExA
0x180044bdd  test    eax, eax
0x180044bdf  jnz     loc_180044B2D
0x180044be5  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044bea  lea     rax, [rsp+2D0h+var_270]
0x180044bef  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180044bf4  lea     rdx, aOlescript; "OLEScript"
0x180044bfb  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044c00  xor     r9d, r9d; lpClass
0x180044c03  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180044c08  xor     r8d, r8d; Reserved
0x180044c0b  mov     [rsp+2D0h+samDesired], esi; samDesired
0x180044c0f  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180044c14  call    cs:__imp_RegCreateKeyExA
0x180044c1a  test    eax, eax
0x180044c1c  jz      short loc_180044C33
0x180044c1e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180044c23  call    cs:__imp_RegCloseKey
0x180044c29  mov     rcx, [rsp+2D0h+var_278]
0x180044c2e  jmp     loc_180044B32
0x180044c33  mov     rax, [rbx+20h]
0x180044c37  xor     r8d, r8d; Reserved
0x180044c3a  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044c3f  xor     edx, edx; lpValueName
0x180044c41  mov     [rsp+2D0h+samDesired], r14d; cbData
0x180044c46  mov     r14d, 1
0x180044c4c  mov     r9d, r14d; dwType
0x180044c4f  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180044c54  call    cs:__imp_RegSetValueExA
0x180044c5a  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044c5f  lea     rax, [rbp+1D0h+var_250]
0x180044c63  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180044c68  lea     esi, [r14+1]
0x180044c6c  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044c71  lea     rdx, aProgid; "ProgID"
0x180044c78  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180044c7d  xor     r9d, r9d; lpClass
0x180044c80  mov     [rsp+2D0h+samDesired], esi; samDesired
0x180044c84  xor     r8d, r8d; Reserved
0x180044c87  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180044c8c  call    cs:__imp_RegCreateKeyExA
0x180044c92  test    eax, eax
0x180044c94  jnz     short loc_180044CCE
0x180044c96  mov     rax, [rbx+38h]
0x180044c9a  mov     rcx, [rax]
0x180044c9d  mov     rax, rdi
0x180044ca0  inc     rax
0x180044ca3  cmp     [rcx+rax], r15b
0x180044ca7  jnz     short loc_180044CA0
0x180044ca9  mov     [rsp+2D0h+samDesired], eax; cbData
0x180044cad  mov     r9d, r14d; dwType
0x180044cb0  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x180044cb5  xor     r8d, r8d; Reserved
0x180044cb8  mov     rcx, [rbp+1D0h+var_250]; hKey
0x180044cbc  xor     edx, edx; lpValueName
0x180044cbe  call    cs:__imp_RegSetValueExA
0x180044cc4  mov     rcx, [rbp+1D0h+var_250]; hKey
0x180044cc8  call    cs:__imp_RegCloseKey
0x180044cce  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044cd3  lea     rax, [rbp+1D0h+var_250]
0x180044cd7  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180044cdc  lea     rdx, aInprocserver32; "InprocServer32"
0x180044ce3  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044ce8  xor     r9d, r9d; lpClass
0x180044ceb  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180044cf0  xor     r8d, r8d; Reserved
0x180044cf3  mov     [rsp+2D0h+samDesired], esi; samDesired
0x180044cf7  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180044cfc  call    cs:__imp_RegCreateKeyExA
0x180044d02  test    eax, eax
0x180044d04  jnz     short loc_180044D30
0x180044d06  mov     rcx, [rbp+1D0h+var_250]; hKey
0x180044d0a  lea     rax, [rbp+1D0h+Filename]
0x180044d0e  mov     [rsp+2D0h+samDesired], r12d; cbData
0x180044d13  mov     r9d, r14d; dwType
0x180044d16  xor     r8d, r8d; Reserved
0x180044d19  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180044d1e  xor     edx, edx; lpValueName
0x180044d20  call    cs:__imp_RegSetValueExA
0x180044d26  mov     rcx, [rbp+1D0h+var_250]; hKey
0x180044d2a  call    cs:__imp_RegCloseKey
0x180044d30  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044d35  lea     rax, [rsp+2D0h+var_260]
0x180044d3a  mov     r9d, esi; samDesired
0x180044d3d  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x180044d42  xor     r8d, r8d; ulOptions
0x180044d45  mov     [rsp+2D0h+var_260], r15
0x180044d4a  lea     rdx, aInprocserver32; "InprocServer32"
0x180044d51  call    cs:__imp_RegOpenKeyExA
0x180044d57  test    eax, eax
0x180044d59  jz      short loc_180044D76
0x180044d5b  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180044d60  call    cs:__imp_RegCloseKey
0x180044d66  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044d6b  call    cs:__imp_RegCloseKey
0x180044d71  jmp     loc_180044B2D
0x180044d76  mov     rax, rdi
0x180044d79  inc     rax
0x180044d7c  cmp     [rax+r13], r15b
0x180044d80  jnz     short loc_180044D79
0x180044d82  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180044d87  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180044d8e  mov     [rsp+2D0h+samDesired], eax; cbData
0x180044d92  mov     r9d, r14d; dwType
0x180044d95  xor     r8d, r8d; Reserved
0x180044d98  mov     qword ptr [rsp+2D0h+dwOptions], r13; lpData
0x180044d9d  call    cs:__imp_RegSetValueExA
0x180044da3  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180044da8  call    cs:__imp_RegCloseKey
0x180044dae  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180044db3  call    cs:__imp_RegCloseKey
0x180044db9  lea     rsi, [rbx+44h]
0x180044dbd  mov     rax, [rsi]
0x180044dc0  sub     rax, qword ptr cs:CLSID_VBScriptRegExp.Data1
0x180044dc7  jnz     short loc_180044DD4
0x180044dc9  mov     rax, [rsi+8]
0x180044dcd  sub     rax, qword ptr cs:CLSID_VBScriptRegExp.Data4
0x180044dd4  test    rax, rax
0x180044dd7  jnz     loc_180044EC3
0x180044ddd  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044de2  lea     rax, [rsp+2D0h+var_270]
0x180044de7  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180044dec  lea     rdx, aTypelib; "TypeLib"
0x180044df3  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044df8  mov     r12d, 2000000h
0x180044dfe  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180044e03  xor     r9d, r9d; lpClass
0x180044e06  mov     [rsp+2D0h+samDesired], r12d; samDesired
0x180044e0b  xor     r8d, r8d; Reserved
0x180044e0e  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180044e13  call    cs:__imp_RegCreateKeyExA
0x180044e19  test    eax, eax
0x180044e1b  jnz     loc_180044C1E
0x180044e21  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180044e26  lea     rax, Data; "{3F4DACA7-160D-11D2-A8E9-00104B365C9F}"
0x180044e2d  mov     [rsp+2D0h+samDesired], 26h ; '&'; cbData
0x180044e35  mov     r9d, r14d; dwType
0x180044e38  xor     r8d, r8d; Reserved
0x180044e3b  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180044e40  xor     edx, edx; lpValueName
0x180044e42  call    cs:__imp_RegSetValueExA
0x180044e48  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180044e4d  call    cs:__imp_RegCloseKey
0x180044e53  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180044e58  lea     rax, [rsp+2D0h+var_270]
0x180044e5d  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180044e62  lea     rdx, aVersion; "Version"
0x180044e69  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180044e6e  xor     r9d, r9d; lpClass
  ... truncated ...
```
