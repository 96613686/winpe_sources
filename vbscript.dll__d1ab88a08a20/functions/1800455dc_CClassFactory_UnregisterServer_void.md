# CClassFactory::UnregisterServer(void)

- ea: `0x1800455dc`
- end: `0x180045ae1`
- name: `?UnregisterServer@CClassFactory@@QEAAJXZ`
- size: `1285`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180045c4c`
- `0x180058e00`

## callees

- `0x1800455dc`
- `0x180051a00`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18004562b`
- `ADVAPI32!RegOpenKeyExA` at `0x180045656`
- `ADVAPI32!RegOpenKeyExA` at `0x180045698`
- `ADVAPI32!RegOpenKeyExA` at `0x18004585d`
- `ADVAPI32!RegOpenKeyExA` at `0x18004596b`
- `ADVAPI32!RegOpenKeyExA` at `0x18004562b`
- `ADVAPI32!RegOpenKeyExA` at `0x180045656`
- `ADVAPI32!RegOpenKeyExA` at `0x180045698`
- `ADVAPI32!RegOpenKeyExA` at `0x18004585d`
- `ADVAPI32!RegOpenKeyExA` at `0x18004596b`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800456cd`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045776`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045882`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800458a4`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800458da`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045993`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800459b5`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800459f3`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045a15`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045a30`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045a52`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045a81`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045ab4`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800456cd`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045776`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045882`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800458a4`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800458da`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045993`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800459b5`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800459f3`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045a15`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045a30`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045a52`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045a81`
- `ADVAPI32!RegDeleteKeyExA` at `0x180045ab4`
- `ADVAPI32!RegCreateKeyExA` at `0x18004593d`
- `ADVAPI32!RegCreateKeyExA` at `0x18004593d`
- `ADVAPI32!RegCloseKey` at `0x18004566e`
- `ADVAPI32!RegCloseKey` at `0x1800456b0`
- `ADVAPI32!RegCloseKey` at `0x180045786`
- `ADVAPI32!RegCloseKey` at `0x18004579e`
- `ADVAPI32!RegCloseKey` at `0x1800458b9`
- `ADVAPI32!RegCloseKey` at `0x180045a67`
- `ADVAPI32!RegCloseKey` at `0x180045a96`
- `ADVAPI32!RegCloseKey` at `0x18004566e`
- `ADVAPI32!RegCloseKey` at `0x1800456b0`
- `ADVAPI32!RegCloseKey` at `0x180045786`
- `ADVAPI32!RegCloseKey` at `0x18004579e`
- `ADVAPI32!RegCloseKey` at `0x1800458b9`
- `ADVAPI32!RegCloseKey` at `0x180045a67`
- `ADVAPI32!RegCloseKey` at `0x180045a96`

## string_xrefs

- `0x18004561a`: `CLSID`
- `0x180045875`: `CLSID`
- `0x180045910`: `CLSID`

## pseudocode

```c
__int64 __fastcall CClassFactory::UnregisterServer(CClassFactory *this)
{
  unsigned int v2; // r14d
  unsigned int v4; // ebx
  int i; // r15d
  __int64 v6; // rax
  const CHAR *v7; // rdx
  GUID v8; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+40h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x2000000u, &hKey) )
  {
    if ( !RegOpenKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0x2000000u, &phkResult) )
    {
      RegCloseKey(hKey);
      hKey = phkResult;
      if ( !RegOpenKeyExA(phkResult, "InprocServer", 0, 0x2000000u, &phkResult) )
      {
        RegCloseKey(phkResult);
        v2 = RegDeleteKeyExA(hKey, "InprocServer32", 0, 0) != 0 ? 0x80004005 : 0;
        if ( (*((_BYTE *)this + 84) & 1) != 0 )
        {
          v8 = CATID_ActiveScript;
          UnRegisterCLSIDInCategory((char *)this + 68, &v8);
        }
        if ( (*((_BYTE *)this + 84) & 2) != 0 )
        {
          v8 = CATID_ActiveScriptParse;
          UnRegisterCLSIDInCategory((char *)this + 68, &v8);
        }
        if ( (*((_BYTE *)this + 84) & 4) != 0 )
        {
          v8 = CATID_ActiveScriptAuthor;
          UnRegisterCLSIDInCategory((char *)this + 68, &v8);
        }
        if ( (*((_BYTE *)this + 84) & 8) != 0 )
        {
          v8 = CATID_ActiveScriptEncode;
          UnRegisterCLSIDInCategory((char *)this + 68, &v8);
        }
        RegDeleteKeyExA(hKey, "Implemented Categories", 0, 0);
        RegCloseKey(hKey);
        return v2;
      }
    }
    RegCloseKey(hKey);
  }
  v4 = 0;
  if ( (*((_BYTE *)this + 84) & 1) != 0 )
  {
    v8 = CATID_ActiveScript;
    UnRegisterCLSIDInCategory((char *)this + 68, &v8);
  }
  if ( (*((_BYTE *)this + 84) & 2) != 0 )
  {
    v8 = CATID_ActiveScriptParse;
    UnRegisterCLSIDInCategory((char *)this + 68, &v8);
  }
  if ( (*((_BYTE *)this + 84) & 4) != 0 )
  {
    v8 = CATID_ActiveScriptAuthor;
    UnRegisterCLSIDInCategory((char *)this + 68, &v8);
  }
  if ( (*((_BYTE *)this + 84) & 8) != 0 )
  {
    v8 = CATID_ActiveScriptEncode;
    UnRegisterCLSIDInCategory((char *)this + 68, &v8);
  }
  for ( i = 0; i < *((_DWORD *)this + 16); ++i )
  {
    if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, *(LPCSTR *)(*((_QWORD *)this + 7) + 8LL * i), 0, 0x2000000u, &hKey) )
    {
      v4 = -2147467259;
    }
    else
    {
      if ( RegDeleteKeyExA(hKey, "CLSID", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(hKey, "OLEScript", 0, 0) )
        v4 = -2147467259;
      RegCloseKey(hKey);
      if ( RegDeleteKeyExA(HKEY_CLASSES_ROOT, *(LPCSTR *)(*((_QWORD *)this + 7) + 8LL * i), 0, 0) )
        v4 = -2147467259;
    }
  }
  if ( RegCreateKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
  {
    v4 = -2147467259;
  }
  else
  {
    if ( RegOpenKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0x2000000u, &phkResult) )
    {
      v4 = -2147467259;
    }
    else
    {
      if ( RegDeleteKeyExA(phkResult, "ProgID", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(phkResult, "OLEScript", 0, 0) )
        v4 = -2147467259;
      v6 = *(_QWORD *)((char *)this + 68) - *(_QWORD *)&CLSID_VBScriptRegExp.Data1;
      if ( !v6 )
        v6 = *(_QWORD *)((char *)this + 76) - *(_QWORD *)CLSID_VBScriptRegExp.Data4;
      if ( v6 )
      {
        if ( RegDeleteKeyExA(phkResult, "Implemented Categories", 0, 0) )
          v4 = -2147467259;
      }
      else
      {
        if ( RegDeleteKeyExA(phkResult, "TypeLib", 0, 0) )
          v4 = -2147467259;
        if ( RegDeleteKeyExA(phkResult, "Version", 0, 0) )
          v4 = -2147467259;
      }
      if ( RegDeleteKeyExA(phkResult, "InprocServer32", 0, 0) )
        v4 = -2147467259;
      RegCloseKey(phkResult);
    }
    if ( RegDeleteKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0) )
      v4 = -2147467259;
    RegCloseKey(hKey);
  }
  v7 = (const CHAR *)*((_QWORD *)this + 5);
  if ( v7 && RegDeleteKeyExA(HKEY_CLASSES_ROOT, v7, 0, 0) )
    return (unsigned int)-2147467259;
  return v4;
}

```

## disassembly

```asm
0x1800455dc  mov     [rsp-28h+arg_0], rbx
0x1800455e1  mov     [rsp-28h+arg_18], rsi
0x1800455e6  push    rbp
0x1800455e7  push    rdi
0x1800455e8  push    r12
0x1800455ea  push    r14
0x1800455ec  push    r15
0x1800455ee  mov     rbp, rsp
0x1800455f1  sub     rsp, 60h
0x1800455f5  mov     rdi, rcx
0x1800455f8  mov     [rbp+hKey], 0
0x180045600  lea     rax, [rbp+hKey]
0x180045604  mov     [rbp+arg_10], 0
0x18004560c  mov     r12d, 2000000h
0x180045612  mov     [rsp+60h+phkResult], rax; phkResult
0x180045617  mov     r9d, r12d; samDesired
0x18004561a  lea     rdx, aClsid; "CLSID"
0x180045621  xor     r8d, r8d; ulOptions
0x180045624  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18004562b  call    cs:__imp_RegOpenKeyExA
0x180045632  nop     dword ptr [rax+rax+00h]
0x180045637  test    eax, eax
0x180045639  jnz     loc_1800457AA
0x18004563f  mov     rdx, [rdi+18h]; lpSubKey
0x180045643  lea     rax, [rbp+arg_10]
0x180045647  mov     rcx, [rbp+hKey]; hKey
0x18004564b  mov     r9d, r12d; samDesired
0x18004564e  xor     r8d, r8d; ulOptions
0x180045651  mov     [rsp+60h+phkResult], rax; phkResult
0x180045656  call    cs:__imp_RegOpenKeyExA
0x18004565d  nop     dword ptr [rax+rax+00h]
0x180045662  test    eax, eax
0x180045664  jnz     loc_18004579A
0x18004566a  mov     rcx, [rbp+hKey]; hKey
0x18004566e  call    cs:__imp_RegCloseKey
0x180045675  nop     dword ptr [rax+rax+00h]
0x18004567a  mov     rcx, [rbp+arg_10]; hKey
0x18004567e  lea     rax, [rbp+arg_10]
0x180045682  mov     r9d, r12d; samDesired
0x180045685  mov     [rbp+hKey], rcx
0x180045689  xor     r8d, r8d; ulOptions
0x18004568c  mov     [rsp+60h+phkResult], rax; phkResult
0x180045691  lea     rdx, aInprocserver; "InprocServer"
0x180045698  call    cs:__imp_RegOpenKeyExA
0x18004569f  nop     dword ptr [rax+rax+00h]
0x1800456a4  test    eax, eax
0x1800456a6  jnz     loc_18004579A
0x1800456ac  mov     rcx, [rbp+arg_10]; hKey
0x1800456b0  call    cs:__imp_RegCloseKey
0x1800456b7  nop     dword ptr [rax+rax+00h]
0x1800456bc  mov     rcx, [rbp+hKey]; hKey
0x1800456c0  lea     rdx, aInprocserver32; "InprocServer32"
0x1800456c7  xor     r9d, r9d; Reserved
0x1800456ca  xor     r8d, r8d; samDesired
0x1800456cd  call    cs:__imp_RegDeleteKeyExA
0x1800456d4  nop     dword ptr [rax+rax+00h]
0x1800456d9  xor     ecx, ecx
0x1800456db  lea     rbx, [rdi+44h]
0x1800456df  sub     ecx, eax
0x1800456e1  neg     ecx
0x1800456e3  sbb     r14d, r14d
0x1800456e6  and     r14d, 80004005h
0x1800456ed  test    byte ptr [rdi+54h], 1
0x1800456f1  jz      short loc_18004570B
0x1800456f3  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x1800456fa  lea     rdx, [rbp+var_10]
0x1800456fe  mov     rcx, rbx
0x180045701  movdqu  [rbp+var_10], xmm0
0x180045706  call    UnRegisterCLSIDInCategory
0x18004570b  test    byte ptr [rdi+54h], 2
0x18004570f  jz      short loc_180045729
0x180045711  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x180045718  lea     rdx, [rbp+var_10]
0x18004571c  mov     rcx, rbx
0x18004571f  movdqu  [rbp+var_10], xmm0
0x180045724  call    UnRegisterCLSIDInCategory
0x180045729  test    byte ptr [rdi+54h], 4
0x18004572d  jz      short loc_180045747
0x18004572f  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptAuthor.Data1
0x180045736  lea     rdx, [rbp+var_10]
0x18004573a  mov     rcx, rbx
0x18004573d  movdqu  [rbp+var_10], xmm0
0x180045742  call    UnRegisterCLSIDInCategory
0x180045747  test    byte ptr [rdi+54h], 8
0x18004574b  jz      short loc_180045765
0x18004574d  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptEncode.Data1
0x180045754  lea     rdx, [rbp+var_10]
0x180045758  mov     rcx, rbx
0x18004575b  movdqu  [rbp+var_10], xmm0
0x180045760  call    UnRegisterCLSIDInCategory
0x180045765  mov     rcx, [rbp+hKey]; hKey
0x180045769  lea     rdx, aImplementedCat; "Implemented Categories"
0x180045770  xor     r9d, r9d; Reserved
0x180045773  xor     r8d, r8d; samDesired
0x180045776  call    cs:__imp_RegDeleteKeyExA
0x18004577d  nop     dword ptr [rax+rax+00h]
0x180045782  mov     rcx, [rbp+hKey]; hKey
0x180045786  call    cs:__imp_RegCloseKey
0x18004578d  nop     dword ptr [rax+rax+00h]
0x180045792  mov     eax, r14d
0x180045795  jmp     loc_180045AC7
0x18004579a  mov     rcx, [rbp+hKey]; hKey
0x18004579e  call    cs:__imp_RegCloseKey
0x1800457a5  nop     dword ptr [rax+rax+00h]
0x1800457aa  xor     ebx, ebx
0x1800457ac  lea     r14, [rdi+44h]
0x1800457b0  test    byte ptr [rdi+54h], 1
0x1800457b4  jz      short loc_1800457CE
0x1800457b6  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x1800457bd  lea     rdx, [rbp+var_10]
0x1800457c1  mov     rcx, r14
0x1800457c4  movdqu  [rbp+var_10], xmm0
0x1800457c9  call    UnRegisterCLSIDInCategory
0x1800457ce  test    byte ptr [rdi+54h], 2
0x1800457d2  jz      short loc_1800457EC
0x1800457d4  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x1800457db  lea     rdx, [rbp+var_10]
0x1800457df  mov     rcx, r14
0x1800457e2  movdqu  [rbp+var_10], xmm0
0x1800457e7  call    UnRegisterCLSIDInCategory
0x1800457ec  test    byte ptr [rdi+54h], 4
0x1800457f0  jz      short loc_18004580A
0x1800457f2  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptAuthor.Data1
0x1800457f9  lea     rdx, [rbp+var_10]
0x1800457fd  mov     rcx, r14
0x180045800  movdqu  [rbp+var_10], xmm0
0x180045805  call    UnRegisterCLSIDInCategory
0x18004580a  test    byte ptr [rdi+54h], 8
0x18004580e  jz      short loc_180045828
0x180045810  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptEncode.Data1
0x180045817  lea     rdx, [rbp+var_10]
0x18004581b  mov     rcx, r14
0x18004581e  movdqu  [rbp+var_10], xmm0
0x180045823  call    UnRegisterCLSIDInCategory
0x180045828  xor     r15d, r15d
0x18004582b  mov     esi, 80004005h
0x180045830  cmp     [rdi+40h], ebx
0x180045833  jle     loc_1800458FE
0x180045839  mov     rdx, [rdi+38h]
0x18004583d  lea     rax, [rbp+hKey]
0x180045841  movsxd  r12, r15d
0x180045844  mov     r9d, 2000000h; samDesired
0x18004584a  xor     r8d, r8d; ulOptions
0x18004584d  mov     [rsp+60h+phkResult], rax; phkResult
0x180045852  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180045859  mov     rdx, [rdx+r12*8]; lpSubKey
0x18004585d  call    cs:__imp_RegOpenKeyExA
0x180045864  nop     dword ptr [rax+rax+00h]
0x180045869  test    eax, eax
0x18004586b  jz      short loc_180045871
0x18004586d  mov     ebx, esi
0x18004586f  jmp     short loc_1800458EB
0x180045871  mov     rcx, [rbp+hKey]; hKey
0x180045875  lea     rdx, aClsid; "CLSID"
0x18004587c  xor     r9d, r9d; Reserved
0x18004587f  xor     r8d, r8d; samDesired
0x180045882  call    cs:__imp_RegDeleteKeyExA
0x180045889  nop     dword ptr [rax+rax+00h]
0x18004588e  mov     rcx, [rbp+hKey]; hKey
0x180045892  lea     rdx, aOlescript; "OLEScript"
0x180045899  test    eax, eax
0x18004589b  cmovnz  ebx, esi
0x18004589e  xor     r9d, r9d; Reserved
0x1800458a1  xor     r8d, r8d; samDesired
0x1800458a4  call    cs:__imp_RegDeleteKeyExA
0x1800458ab  nop     dword ptr [rax+rax+00h]
0x1800458b0  mov     rcx, [rbp+hKey]; hKey
0x1800458b4  test    eax, eax
0x1800458b6  cmovnz  ebx, esi
0x1800458b9  call    cs:__imp_RegCloseKey
0x1800458c0  nop     dword ptr [rax+rax+00h]
0x1800458c5  mov     rdx, [rdi+38h]
0x1800458c9  xor     r9d, r9d; Reserved
0x1800458cc  xor     r8d, r8d; samDesired
0x1800458cf  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800458d6  mov     rdx, [rdx+r12*8]; lpSubKey
0x1800458da  call    cs:__imp_RegDeleteKeyExA
0x1800458e1  nop     dword ptr [rax+rax+00h]
0x1800458e6  test    eax, eax
0x1800458e8  cmovnz  ebx, esi
0x1800458eb  inc     r15d
0x1800458ee  cmp     r15d, [rdi+40h]
0x1800458f2  jl      loc_180045839
0x1800458f8  mov     r12d, 2000000h
0x1800458fe  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180045907  lea     rax, [rbp+hKey]
0x18004590b  mov     [rsp+60h+var_28], rax; phkResult
0x180045910  lea     rdx, aClsid; "CLSID"
0x180045917  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180045920  mov     r15, 0FFFFFFFF80000000h
0x180045927  mov     [rsp+60h+samDesired], r12d; samDesired
0x18004592c  xor     r9d, r9d; lpClass
0x18004592f  xor     r8d, r8d; Reserved
0x180045932  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x18004593a  mov     rcx, r15; hKey
0x18004593d  call    cs:__imp_RegCreateKeyExA
0x180045944  nop     dword ptr [rax+rax+00h]
0x180045949  test    eax, eax
0x18004594b  jz      short loc_180045954
0x18004594d  mov     ebx, esi
0x18004594f  jmp     loc_180045AA2
0x180045954  mov     rdx, [rdi+18h]; lpSubKey
0x180045958  lea     rax, [rbp+arg_10]
0x18004595c  mov     rcx, [rbp+hKey]; hKey
0x180045960  mov     r9d, r12d; samDesired
0x180045963  xor     r8d, r8d; ulOptions
0x180045966  mov     [rsp+60h+phkResult], rax; phkResult
0x18004596b  call    cs:__imp_RegOpenKeyExA
0x180045972  nop     dword ptr [rax+rax+00h]
0x180045977  test    eax, eax
0x180045979  jz      short loc_180045982
0x18004597b  mov     ebx, esi
0x18004597d  jmp     loc_180045A73
0x180045982  mov     rcx, [rbp+arg_10]; hKey
0x180045986  lea     rdx, aProgid; "ProgID"
0x18004598d  xor     r9d, r9d; Reserved
0x180045990  xor     r8d, r8d; samDesired
0x180045993  call    cs:__imp_RegDeleteKeyExA
0x18004599a  nop     dword ptr [rax+rax+00h]
0x18004599f  mov     rcx, [rbp+arg_10]; hKey
0x1800459a3  lea     rdx, aOlescript; "OLEScript"
0x1800459aa  test    eax, eax
0x1800459ac  cmovnz  ebx, esi
0x1800459af  xor     r9d, r9d; Reserved
0x1800459b2  xor     r8d, r8d; samDesired
0x1800459b5  call    cs:__imp_RegDeleteKeyExA
0x1800459bc  nop     dword ptr [rax+rax+00h]
0x1800459c1  test    eax, eax
0x1800459c3  mov     rax, [r14]
0x1800459c6  cmovnz  ebx, esi
0x1800459c9  sub     rax, qword ptr cs:CLSID_VBScriptRegExp.Data1
0x1800459d0  jnz     short loc_1800459DD
0x1800459d2  mov     rax, [r14+8]
0x1800459d6  sub     rax, qword ptr cs:CLSID_VBScriptRegExp.Data4
0x1800459dd  mov     rcx, [rbp+arg_10]; hKey
0x1800459e1  xor     r9d, r9d; Reserved
0x1800459e4  xor     r8d, r8d; samDesired
0x1800459e7  test    rax, rax
0x1800459ea  jnz     short loc_180045A29
0x1800459ec  lea     rdx, aTypelib; "TypeLib"
0x1800459f3  call    cs:__imp_RegDeleteKeyExA
0x1800459fa  nop     dword ptr [rax+rax+00h]
0x1800459ff  mov     rcx, [rbp+arg_10]; hKey
0x180045a03  lea     rdx, aVersion; "Version"
0x180045a0a  test    eax, eax
0x180045a0c  cmovnz  ebx, esi
0x180045a0f  xor     r9d, r9d; Reserved
0x180045a12  xor     r8d, r8d; samDesired
0x180045a15  call    cs:__imp_RegDeleteKeyExA
0x180045a1c  nop     dword ptr [rax+rax+00h]
0x180045a21  test    eax, eax
0x180045a23  jz      short loc_180045A41
0x180045a25  mov     ebx, esi
0x180045a27  jmp     short loc_180045A41
0x180045a29  lea     rdx, aImplementedCat; "Implemented Categories"
0x180045a30  call    cs:__imp_RegDeleteKeyExA
0x180045a37  nop     dword ptr [rax+rax+00h]
0x180045a3c  test    eax, eax
0x180045a3e  cmovnz  ebx, esi
0x180045a41  mov     rcx, [rbp+arg_10]; hKey
0x180045a45  lea     rdx, aInprocserver32; "InprocServer32"
0x180045a4c  xor     r9d, r9d; Reserved
0x180045a4f  xor     r8d, r8d; samDesired
0x180045a52  call    cs:__imp_RegDeleteKeyExA
0x180045a59  nop     dword ptr [rax+rax+00h]
0x180045a5e  mov     rcx, [rbp+arg_10]; hKey
0x180045a62  test    eax, eax
0x180045a64  cmovnz  ebx, esi
0x180045a67  call    cs:__imp_RegCloseKey
0x180045a6e  nop     dword ptr [rax+rax+00h]
0x180045a73  mov     rdx, [rdi+18h]; lpSubKey
0x180045a77  xor     r9d, r9d; Reserved
0x180045a7a  mov     rcx, [rbp+hKey]; hKey
0x180045a7e  xor     r8d, r8d; samDesired
0x180045a81  call    cs:__imp_RegDeleteKeyExA
0x180045a88  nop     dword ptr [rax+rax+00h]
0x180045a8d  mov     rcx, [rbp+hKey]; hKey
0x180045a91  test    eax, eax
0x180045a93  cmovnz  ebx, esi
0x180045a96  call    cs:__imp_RegCloseKey
0x180045a9d  nop     dword ptr [rax+rax+00h]
0x180045aa2  mov     rdx, [rdi+28h]; lpSubKey
0x180045aa6  test    rdx, rdx
0x180045aa9  jz      short loc_180045AC5
0x180045aab  xor     r9d, r9d; Reserved
0x180045aae  xor     r8d, r8d; samDesired
0x180045ab1  mov     rcx, r15; hKey
0x180045ab4  call    cs:__imp_RegDeleteKeyExA
0x180045abb  nop     dword ptr [rax+rax+00h]
0x180045ac0  test    eax, eax
0x180045ac2  cmovnz  ebx, esi
0x180045ac5  mov     eax, ebx
0x180045ac7  lea     r11, [rsp+60h+var_s0]
0x180045acc  mov     rbx, [r11+30h]
0x180045ad0  mov     rsi, [r11+48h]
0x180045ad4  mov     rsp, r11
0x180045ad7  pop     r15
0x180045ad9  pop     r14
0x180045adb  pop     r12
0x180045add  pop     rdi
  ... truncated ...
```
