# CClassFactory::UnregisterServer(void)

- ea: `0x180044378`
- end: `0x1800447e0`
- name: `?UnregisterServer@CClassFactory@@QEAAJXZ`
- size: `1128`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004494c`
- `0x180057380`

## callees

- `0x180044378`
- `0x180050244`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x1800443c7`
- `ADVAPI32!RegOpenKeyExA` at `0x1800443ec`
- `ADVAPI32!RegOpenKeyExA` at `0x180044422`
- `ADVAPI32!RegOpenKeyExA` at `0x1800445c3`
- `ADVAPI32!RegOpenKeyExA` at `0x1800446ad`
- `ADVAPI32!RegOpenKeyExA` at `0x1800443c7`
- `ADVAPI32!RegOpenKeyExA` at `0x1800443ec`
- `ADVAPI32!RegOpenKeyExA` at `0x180044422`
- `ADVAPI32!RegOpenKeyExA` at `0x1800445c3`
- `ADVAPI32!RegOpenKeyExA` at `0x1800446ad`
- `ADVAPI32!RegDeleteKeyExA` at `0x18004444b`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800444ee`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800445e2`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800445fe`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044628`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800446cf`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800446eb`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044723`
- `ADVAPI32!RegDeleteKeyExA` at `0x18004473f`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044754`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044770`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044793`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800447ba`
- `ADVAPI32!RegDeleteKeyExA` at `0x18004444b`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800444ee`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800445e2`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800445fe`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044628`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800446cf`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800446eb`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044723`
- `ADVAPI32!RegDeleteKeyExA` at `0x18004473f`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044754`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044770`
- `ADVAPI32!RegDeleteKeyExA` at `0x180044793`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800447ba`
- `ADVAPI32!RegCreateKeyExA` at `0x180044685`
- `ADVAPI32!RegCreateKeyExA` at `0x180044685`
- `ADVAPI32!RegCloseKey` at `0x1800443fe`
- `ADVAPI32!RegCloseKey` at `0x180044434`
- `ADVAPI32!RegCloseKey` at `0x1800444f8`
- `ADVAPI32!RegCloseKey` at `0x18004450a`
- `ADVAPI32!RegCloseKey` at `0x18004460d`
- `ADVAPI32!RegCloseKey` at `0x18004477f`
- `ADVAPI32!RegCloseKey` at `0x1800447a2`
- `ADVAPI32!RegCloseKey` at `0x1800443fe`
- `ADVAPI32!RegCloseKey` at `0x180044434`
- `ADVAPI32!RegCloseKey` at `0x1800444f8`
- `ADVAPI32!RegCloseKey` at `0x18004450a`
- `ADVAPI32!RegCloseKey` at `0x18004460d`
- `ADVAPI32!RegCloseKey` at `0x18004477f`
- `ADVAPI32!RegCloseKey` at `0x1800447a2`

## string_xrefs

- `0x1800443b6`: `CLSID`
- `0x1800445d5`: `CLSID`
- `0x180044658`: `CLSID`

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
0x180044378  mov     [rsp-28h+arg_0], rbx
0x18004437d  mov     [rsp-28h+arg_18], rsi
0x180044382  push    rbp
0x180044383  push    rdi
0x180044384  push    r12
0x180044386  push    r14
0x180044388  push    r15
0x18004438a  mov     rbp, rsp
0x18004438d  sub     rsp, 60h
0x180044391  mov     rdi, rcx
0x180044394  mov     [rbp+hKey], 0
0x18004439c  lea     rax, [rbp+hKey]
0x1800443a0  mov     [rbp+arg_10], 0
0x1800443a8  mov     r12d, 2000000h
0x1800443ae  mov     [rsp+60h+phkResult], rax; phkResult
0x1800443b3  mov     r9d, r12d; samDesired
0x1800443b6  lea     rdx, aClsid; "CLSID"
0x1800443bd  xor     r8d, r8d; ulOptions
0x1800443c0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800443c7  call    cs:__imp_RegOpenKeyExA
0x1800443cd  test    eax, eax
0x1800443cf  jnz     loc_180044510
0x1800443d5  mov     rdx, [rdi+18h]; lpSubKey
0x1800443d9  lea     rax, [rbp+arg_10]
0x1800443dd  mov     rcx, [rbp+hKey]; hKey
0x1800443e1  mov     r9d, r12d; samDesired
0x1800443e4  xor     r8d, r8d; ulOptions
0x1800443e7  mov     [rsp+60h+phkResult], rax; phkResult
0x1800443ec  call    cs:__imp_RegOpenKeyExA
0x1800443f2  test    eax, eax
0x1800443f4  jnz     loc_180044506
0x1800443fa  mov     rcx, [rbp+hKey]; hKey
0x1800443fe  call    cs:__imp_RegCloseKey
0x180044404  mov     rcx, [rbp+arg_10]; hKey
0x180044408  lea     rax, [rbp+arg_10]
0x18004440c  mov     r9d, r12d; samDesired
0x18004440f  mov     [rbp+hKey], rcx
0x180044413  xor     r8d, r8d; ulOptions
0x180044416  mov     [rsp+60h+phkResult], rax; phkResult
0x18004441b  lea     rdx, aInprocserver; "InprocServer"
0x180044422  call    cs:__imp_RegOpenKeyExA
0x180044428  test    eax, eax
0x18004442a  jnz     loc_180044506
0x180044430  mov     rcx, [rbp+arg_10]; hKey
0x180044434  call    cs:__imp_RegCloseKey
0x18004443a  mov     rcx, [rbp+hKey]; hKey
0x18004443e  lea     rdx, aInprocserver32; "InprocServer32"
0x180044445  xor     r9d, r9d; Reserved
0x180044448  xor     r8d, r8d; samDesired
0x18004444b  call    cs:__imp_RegDeleteKeyExA
0x180044451  xor     ecx, ecx
0x180044453  lea     rbx, [rdi+44h]
0x180044457  sub     ecx, eax
0x180044459  neg     ecx
0x18004445b  sbb     r14d, r14d
0x18004445e  and     r14d, 80004005h
0x180044465  test    byte ptr [rdi+54h], 1
0x180044469  jz      short loc_180044483
0x18004446b  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x180044472  lea     rdx, [rbp+var_10]
0x180044476  mov     rcx, rbx
0x180044479  movdqu  [rbp+var_10], xmm0
0x18004447e  call    UnRegisterCLSIDInCategory
0x180044483  test    byte ptr [rdi+54h], 2
0x180044487  jz      short loc_1800444A1
0x180044489  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x180044490  lea     rdx, [rbp+var_10]
0x180044494  mov     rcx, rbx
0x180044497  movdqu  [rbp+var_10], xmm0
0x18004449c  call    UnRegisterCLSIDInCategory
0x1800444a1  test    byte ptr [rdi+54h], 4
0x1800444a5  jz      short loc_1800444BF
0x1800444a7  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptAuthor.Data1
0x1800444ae  lea     rdx, [rbp+var_10]
0x1800444b2  mov     rcx, rbx
0x1800444b5  movdqu  [rbp+var_10], xmm0
0x1800444ba  call    UnRegisterCLSIDInCategory
0x1800444bf  test    byte ptr [rdi+54h], 8
0x1800444c3  jz      short loc_1800444DD
0x1800444c5  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptEncode.Data1
0x1800444cc  lea     rdx, [rbp+var_10]
0x1800444d0  mov     rcx, rbx
0x1800444d3  movdqu  [rbp+var_10], xmm0
0x1800444d8  call    UnRegisterCLSIDInCategory
0x1800444dd  mov     rcx, [rbp+hKey]; hKey
0x1800444e1  lea     rdx, aImplementedCat; "Implemented Categories"
0x1800444e8  xor     r9d, r9d; Reserved
0x1800444eb  xor     r8d, r8d; samDesired
0x1800444ee  call    cs:__imp_RegDeleteKeyExA
0x1800444f4  mov     rcx, [rbp+hKey]; hKey
0x1800444f8  call    cs:__imp_RegCloseKey
0x1800444fe  mov     eax, r14d
0x180044501  jmp     loc_1800447C7
0x180044506  mov     rcx, [rbp+hKey]; hKey
0x18004450a  call    cs:__imp_RegCloseKey
0x180044510  xor     ebx, ebx
0x180044512  lea     r14, [rdi+44h]
0x180044516  test    byte ptr [rdi+54h], 1
0x18004451a  jz      short loc_180044534
0x18004451c  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x180044523  lea     rdx, [rbp+var_10]
0x180044527  mov     rcx, r14
0x18004452a  movdqu  [rbp+var_10], xmm0
0x18004452f  call    UnRegisterCLSIDInCategory
0x180044534  test    byte ptr [rdi+54h], 2
0x180044538  jz      short loc_180044552
0x18004453a  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x180044541  lea     rdx, [rbp+var_10]
0x180044545  mov     rcx, r14
0x180044548  movdqu  [rbp+var_10], xmm0
0x18004454d  call    UnRegisterCLSIDInCategory
0x180044552  test    byte ptr [rdi+54h], 4
0x180044556  jz      short loc_180044570
0x180044558  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptAuthor.Data1
0x18004455f  lea     rdx, [rbp+var_10]
0x180044563  mov     rcx, r14
0x180044566  movdqu  [rbp+var_10], xmm0
0x18004456b  call    UnRegisterCLSIDInCategory
0x180044570  test    byte ptr [rdi+54h], 8
0x180044574  jz      short loc_18004458E
0x180044576  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptEncode.Data1
0x18004457d  lea     rdx, [rbp+var_10]
0x180044581  mov     rcx, r14
0x180044584  movdqu  [rbp+var_10], xmm0
0x180044589  call    UnRegisterCLSIDInCategory
0x18004458e  xor     r15d, r15d
0x180044591  mov     esi, 80004005h
0x180044596  cmp     [rdi+40h], ebx
0x180044599  jle     loc_180044646
0x18004459f  mov     rdx, [rdi+38h]
0x1800445a3  lea     rax, [rbp+hKey]
0x1800445a7  movsxd  r12, r15d
0x1800445aa  mov     r9d, 2000000h; samDesired
0x1800445b0  xor     r8d, r8d; ulOptions
0x1800445b3  mov     [rsp+60h+phkResult], rax; phkResult
0x1800445b8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800445bf  mov     rdx, [rdx+r12*8]; lpSubKey
0x1800445c3  call    cs:__imp_RegOpenKeyExA
0x1800445c9  test    eax, eax
0x1800445cb  jz      short loc_1800445D1
0x1800445cd  mov     ebx, esi
0x1800445cf  jmp     short loc_180044633
0x1800445d1  mov     rcx, [rbp+hKey]; hKey
0x1800445d5  lea     rdx, aClsid; "CLSID"
0x1800445dc  xor     r9d, r9d; Reserved
0x1800445df  xor     r8d, r8d; samDesired
0x1800445e2  call    cs:__imp_RegDeleteKeyExA
0x1800445e8  mov     rcx, [rbp+hKey]; hKey
0x1800445ec  lea     rdx, aOlescript; "OLEScript"
0x1800445f3  test    eax, eax
0x1800445f5  cmovnz  ebx, esi
0x1800445f8  xor     r9d, r9d; Reserved
0x1800445fb  xor     r8d, r8d; samDesired
0x1800445fe  call    cs:__imp_RegDeleteKeyExA
0x180044604  mov     rcx, [rbp+hKey]; hKey
0x180044608  test    eax, eax
0x18004460a  cmovnz  ebx, esi
0x18004460d  call    cs:__imp_RegCloseKey
0x180044613  mov     rdx, [rdi+38h]
0x180044617  xor     r9d, r9d; Reserved
0x18004461a  xor     r8d, r8d; samDesired
0x18004461d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180044624  mov     rdx, [rdx+r12*8]; lpSubKey
0x180044628  call    cs:__imp_RegDeleteKeyExA
0x18004462e  test    eax, eax
0x180044630  cmovnz  ebx, esi
0x180044633  inc     r15d
0x180044636  cmp     r15d, [rdi+40h]
0x18004463a  jl      loc_18004459F
0x180044640  mov     r12d, 2000000h
0x180044646  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18004464f  lea     rax, [rbp+hKey]
0x180044653  mov     [rsp+60h+var_28], rax; phkResult
0x180044658  lea     rdx, aClsid; "CLSID"
0x18004465f  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180044668  mov     r15, 0FFFFFFFF80000000h
0x18004466f  mov     [rsp+60h+samDesired], r12d; samDesired
0x180044674  xor     r9d, r9d; lpClass
0x180044677  xor     r8d, r8d; Reserved
0x18004467a  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180044682  mov     rcx, r15; hKey
0x180044685  call    cs:__imp_RegCreateKeyExA
0x18004468b  test    eax, eax
0x18004468d  jz      short loc_180044696
0x18004468f  mov     ebx, esi
0x180044691  jmp     loc_1800447A8
0x180044696  mov     rdx, [rdi+18h]; lpSubKey
0x18004469a  lea     rax, [rbp+arg_10]
0x18004469e  mov     rcx, [rbp+hKey]; hKey
0x1800446a2  mov     r9d, r12d; samDesired
0x1800446a5  xor     r8d, r8d; ulOptions
0x1800446a8  mov     [rsp+60h+phkResult], rax; phkResult
0x1800446ad  call    cs:__imp_RegOpenKeyExA
0x1800446b3  test    eax, eax
0x1800446b5  jz      short loc_1800446BE
0x1800446b7  mov     ebx, esi
0x1800446b9  jmp     loc_180044785
0x1800446be  mov     rcx, [rbp+arg_10]; hKey
0x1800446c2  lea     rdx, aProgid; "ProgID"
0x1800446c9  xor     r9d, r9d; Reserved
0x1800446cc  xor     r8d, r8d; samDesired
0x1800446cf  call    cs:__imp_RegDeleteKeyExA
0x1800446d5  mov     rcx, [rbp+arg_10]; hKey
0x1800446d9  lea     rdx, aOlescript; "OLEScript"
0x1800446e0  test    eax, eax
0x1800446e2  cmovnz  ebx, esi
0x1800446e5  xor     r9d, r9d; Reserved
0x1800446e8  xor     r8d, r8d; samDesired
0x1800446eb  call    cs:__imp_RegDeleteKeyExA
0x1800446f1  test    eax, eax
0x1800446f3  mov     rax, [r14]
0x1800446f6  cmovnz  ebx, esi
0x1800446f9  sub     rax, qword ptr cs:CLSID_VBScriptRegExp.Data1
0x180044700  jnz     short loc_18004470D
0x180044702  mov     rax, [r14+8]
0x180044706  sub     rax, qword ptr cs:CLSID_VBScriptRegExp.Data4
0x18004470d  mov     rcx, [rbp+arg_10]; hKey
0x180044711  xor     r9d, r9d; Reserved
0x180044714  xor     r8d, r8d; samDesired
0x180044717  test    rax, rax
0x18004471a  jnz     short loc_18004474D
0x18004471c  lea     rdx, aTypelib; "TypeLib"
0x180044723  call    cs:__imp_RegDeleteKeyExA
0x180044729  mov     rcx, [rbp+arg_10]; hKey
0x18004472d  lea     rdx, aVersion; "Version"
0x180044734  test    eax, eax
0x180044736  cmovnz  ebx, esi
0x180044739  xor     r9d, r9d; Reserved
0x18004473c  xor     r8d, r8d; samDesired
0x18004473f  call    cs:__imp_RegDeleteKeyExA
0x180044745  test    eax, eax
0x180044747  jz      short loc_18004475F
0x180044749  mov     ebx, esi
0x18004474b  jmp     short loc_18004475F
0x18004474d  lea     rdx, aImplementedCat; "Implemented Categories"
0x180044754  call    cs:__imp_RegDeleteKeyExA
0x18004475a  test    eax, eax
0x18004475c  cmovnz  ebx, esi
0x18004475f  mov     rcx, [rbp+arg_10]; hKey
0x180044763  lea     rdx, aInprocserver32; "InprocServer32"
0x18004476a  xor     r9d, r9d; Reserved
0x18004476d  xor     r8d, r8d; samDesired
0x180044770  call    cs:__imp_RegDeleteKeyExA
0x180044776  mov     rcx, [rbp+arg_10]; hKey
0x18004477a  test    eax, eax
0x18004477c  cmovnz  ebx, esi
0x18004477f  call    cs:__imp_RegCloseKey
0x180044785  mov     rdx, [rdi+18h]; lpSubKey
0x180044789  xor     r9d, r9d; Reserved
0x18004478c  mov     rcx, [rbp+hKey]; hKey
0x180044790  xor     r8d, r8d; samDesired
0x180044793  call    cs:__imp_RegDeleteKeyExA
0x180044799  mov     rcx, [rbp+hKey]; hKey
0x18004479d  test    eax, eax
0x18004479f  cmovnz  ebx, esi
0x1800447a2  call    cs:__imp_RegCloseKey
0x1800447a8  mov     rdx, [rdi+28h]; lpSubKey
0x1800447ac  test    rdx, rdx
0x1800447af  jz      short loc_1800447C5
0x1800447b1  xor     r9d, r9d; Reserved
0x1800447b4  xor     r8d, r8d; samDesired
0x1800447b7  mov     rcx, r15; hKey
0x1800447ba  call    cs:__imp_RegDeleteKeyExA
0x1800447c0  test    eax, eax
0x1800447c2  cmovnz  ebx, esi
0x1800447c5  mov     eax, ebx
0x1800447c7  lea     r11, [rsp+60h+var_s0]
0x1800447cc  mov     rbx, [r11+30h]
0x1800447d0  mov     rsi, [r11+48h]
0x1800447d4  mov     rsp, r11
0x1800447d7  pop     r15
0x1800447d9  pop     r14
0x1800447db  pop     r12
0x1800447dd  pop     rdi
0x1800447de  pop     rbp
0x1800447df  retn
```
