# EasEngineGetPolicies(int,void *,ulong,ulong *,_tagEASPolicy * *)

- ea: `0x140015260`
- end: `0x1400155e8`
- name: `?EasEngineGetPolicies@@YAJHPEAXKPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `904`
- prototype: `int(int, void *, unsigned int, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140013c40`
- `0x140014000`
- `0x1400146a0`
- `0x14002c6b0`
- `0x140036db0`

## callees

- `0x140013620`
- `0x140015260`
- `0x140038250`
- `0x14009718c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400152e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400152e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015495`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400155b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015495`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400155b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400153fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400153fd`

## string_xrefs

- `0x1400153b8`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x1400154ed`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x140015528`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x140015423`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x140015408`: `RegOpenKeyEx`
- `0x14001550d`: `_ReadPolicies`
- `0x1400154b7`: `pSID is NULL`

## pseudocode

```c
__int64 __fastcall EasEngineGetPolicies(int a1, void *a2, unsigned int a3, unsigned int *a4, struct _tagEASPolicy **a5)
{
  unsigned int v8; // edi
  char *v9; // rbp
  struct _tagEASPolicy **v10; // r14
  unsigned int BuiltInProvidersPolicies; // ebx
  bool v12; // zf
  HKEY v13; // rsi
  unsigned int i; // eax
  char *v16; // r8
  struct _tagEASPolicy *v17; // rax
  __int16 v18; // cx
  PHKEY phkResult; // [rsp+20h] [rbp-68h]
  PHKEY phkResulta; // [rsp+20h] [rbp-68h]
  PHKEY phkResultb; // [rsp+20h] [rbp-68h]
  HLOCAL hMem; // [rsp+40h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+20h] BYREF

  v25 = 0;
  v8 = 0;
  hMem = 0;
  v9 = 0;
  if ( !a4 || (v10 = a5) == 0 )
  {
    BuiltInProvidersPolicies = -1073741811;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225485LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      323,
      L"Null Arg(s)",
      &pPassword);
    goto LABEL_15;
  }
  v12 = g_bInitialized == 0;
  *a4 = 0;
  *v10 = 0;
  if ( v12 )
  {
    BuiltInProvidersPolicies = -1073283051;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221684245LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      331,
      L"Not initialized",
      &pPassword);
    goto LABEL_15;
  }
  hKey = 0;
  BuiltInProvidersPolicies = RegOpenKeyExW(
                               HKEY_LOCAL_MACHINE,
                               L"SYSTEM\\CurrentControlSet\\Control\\EAS\\Policies",
                               0,
                               0x20019u,
                               &hKey);
  if ( BuiltInProvidersPolicies - 2 <= 1 )
  {
    BuiltInProvidersPolicies = 0;
LABEL_6:
    v12 = BuiltInProvidersPolicies == 0;
    goto LABEL_7;
  }
  v12 = BuiltInProvidersPolicies == 0;
  if ( (int)BuiltInProvidersPolicies > 0 )
  {
    BuiltInProvidersPolicies = (unsigned __int16)BuiltInProvidersPolicies | 0xC0070000;
    goto LABEL_6;
  }
LABEL_7:
  if ( v12 )
  {
    v13 = hKey;
    hKey = 0;
    if ( !a1 && !a2 )
    {
      BuiltInProvidersPolicies = -1073741584;
      LODWORD(phkResult) = 344;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        3221225712LL,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
        phkResult,
        L"pSID is NULL",
        &pPassword);
      goto LABEL_13;
    }
    BuiltInProvidersPolicies = _ReadPolicies(v13, &v25, (struct _tagEASPolicy **)&hMem);
    if ( BuiltInProvidersPolicies )
    {
      LODWORD(phkResult) = 368;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        BuiltInProvidersPolicies,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
        phkResult,
        L"_ReadPolicies",
        &pPassword);
      v8 = v25;
      v9 = (char *)hMem;
    }
    else
    {
      v8 = v25;
      if ( !v25 )
      {
        v9 = (char *)hMem;
LABEL_12:
        BuiltInProvidersPolicies = 0;
        goto LABEL_13;
      }
      if ( !a3 )
      {
        v17 = (struct _tagEASPolicy *)hMem;
        *a4 = v25;
        v8 = 0;
        *v10 = v17;
        goto LABEL_12;
      }
      v9 = (char *)hMem;
      if ( ((a3 - 1) & 0xFFFFFFFC) != 0 )
        goto LABEL_12;
      if ( a3 == 2 )
        goto LABEL_12;
      BuiltInProvidersPolicies = _GetBuiltInProvidersPolicies(a3, v25, (struct _tagEASPolicy *)hMem, a4, v10);
      if ( !BuiltInProvidersPolicies )
        goto LABEL_12;
      LODWORD(phkResultb) = 398;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        BuiltInProvidersPolicies,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
        phkResultb,
        L"_GetBuiltInProvidersPolicies",
        &pPassword);
    }
LABEL_13:
    if ( v13 )
      RegCloseKey(v13);
    goto LABEL_15;
  }
  LODWORD(phkResult) = 42;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    BuiltInProvidersPolicies,
    L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
    phkResult,
    L"RegOpenKeyEx",
    &pPassword);
  if ( hKey )
    RegCloseKey(hKey);
  LODWORD(phkResulta) = 337;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    BuiltInProvidersPolicies,
    L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
    phkResulta,
    L"_LockStore",
    &pPassword);
LABEL_15:
  if ( v9 )
  {
    for ( i = 0; i < v8; ++i )
    {
      v16 = &v9[32 * i + 8];
      if ( v16 )
      {
        v18 = *(_WORD *)v16;
        if ( *(_WORD *)v16 >= 2u && (v18 == 11 || v18 == 19) )
          *(_WORD *)v16 = 0;
      }
    }
    LocalFree(v9);
  }
  return BuiltInProvidersPolicies;
}

```

## disassembly

```asm
0x140015260  mov     rax, rsp
0x140015263  mov     [rax+18h], r8d
0x140015267  push    rbx
0x140015268  push    rbp
0x140015269  push    rsi
0x14001526a  push    rdi
0x14001526b  sub     rsp, 68h
0x14001526f  xor     esi, esi
0x140015271  mov     [rax+8], r12
0x140015275  mov     [rax-28h], r13
0x140015279  mov     r13, rdx
0x14001527c  mov     [rax-30h], r14
0x140015280  mov     r12d, ecx
0x140015283  mov     [rax-38h], r15
0x140015287  mov     r15, r9
0x14001528a  mov     [rax+20h], esi
0x14001528d  mov     edi, esi
0x14001528f  mov     [rax-48h], rsi
0x140015293  mov     ebp, esi
0x140015295  test    r9, r9
0x140015298  jz      loc_140015393
0x14001529e  mov     r14, [rsp+88h+arg_20]
0x1400152a6  test    r14, r14
0x1400152a9  jz      loc_140015393
0x1400152af  cmp     cs:?g_bInitialized@@3HA, esi; int g_bInitialized
0x1400152b5  mov     [r9], esi
0x1400152b8  mov     [r14], rsi
0x1400152bb  jz      loc_14001546B
0x1400152c1  mov     [rax-40h], rsi
0x1400152c5  lea     rax, [rax-40h]
0x1400152c9  mov     r9d, 20019h; samDesired
0x1400152cf  mov     [rsp+88h+phkResult], rax; phkResult
0x1400152d4  xor     r8d, r8d; ulOptions
0x1400152d7  lea     rdx, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Control\\EAS"...
0x1400152de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400152e5  call    cs:__imp_RegOpenKeyExW
0x1400152eb  mov     ebx, eax
0x1400152ed  add     eax, 0FFFFFFFEh
0x1400152f0  cmp     eax, 1
0x1400152f3  ja      loc_14001537D
0x1400152f9  mov     ebx, esi
0x1400152fb  test    ebx, ebx
0x1400152fd  jnz     loc_140015408
0x140015303  mov     rsi, [rsp+88h+hKey]
0x140015308  mov     [rsp+88h+hKey], rdi
0x14001530d  test    r12d, r12d
0x140015310  jz      loc_14001549D
0x140015316  lea     r8, [rsp+88h+hMem]; struct _tagEASPolicy **
0x14001531b  mov     rcx, rsi; hKey
0x14001531e  lea     rdx, [rsp+88h+arg_18]; unsigned int *
0x140015326  call    ?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z; _ReadPolicies(void *,ulong *,_tagEASPolicy * *)
0x14001532b  mov     ebx, eax
0x14001532d  test    eax, eax
0x14001532f  jnz     loc_14001550D
0x140015335  mov     edi, [rsp+88h+arg_18]
0x14001533c  test    edi, edi
0x14001533e  jnz     loc_140015559
0x140015344  mov     rbp, [rsp+88h+hMem]
0x140015349  xor     ebx, ebx
0x14001534b  test    rsi, rsi
0x14001534e  jnz     loc_1400155B3
0x140015354  xor     esi, esi
0x140015356  mov     r15, [rsp+88h+var_38]
0x14001535b  mov     r14, [rsp+88h+var_30]
0x140015360  mov     r13, [rsp+88h+var_28]
0x140015365  mov     r12, [rsp+88h+arg_0]
0x14001536d  test    rbp, rbp
0x140015370  jnz     short loc_1400153D5
0x140015372  mov     eax, ebx
0x140015374  add     rsp, 68h
0x140015378  pop     rdi
0x140015379  pop     rsi
0x14001537a  pop     rbp
0x14001537b  pop     rbx
0x14001537c  retn
0x14001537d  test    ebx, ebx
0x14001537f  jle     loc_1400152FD
0x140015385  movzx   ebx, bx
0x140015388  or      ebx, 0C0070000h
0x14001538e  jmp     loc_1400152FB
0x140015393  lea     r14, pPassword
0x14001539a  mov     ebx, 0C000000Dh
0x14001539f  mov     [rsp+88h+var_58], r14
0x1400153a4  lea     rax, aNullArgS; "Null Arg(s)"
0x1400153ab  mov     [rsp+88h+var_60], rax
0x1400153b0  mov     dword ptr [rsp+88h+phkResult], 143h
0x1400153b8  lea     r9, aOnecoreDsSecur_4; "onecore\\ds\\security\\eas\\policyengin"...
0x1400153bf  mov     r8d, ebx
0x1400153c2  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x1400153c9  mov     ecx, 1; unsigned int
0x1400153ce  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x1400153d3  jmp     short loc_140015356
0x1400153d5  mov     eax, esi
0x1400153d7  test    edi, edi
0x1400153d9  jz      short loc_1400153FA
0x1400153db  nop     dword ptr [rax+rax+00h]
0x1400153e0  mov     r8d, eax
0x1400153e3  shl     r8, 5
0x1400153e7  add     r8, 8
0x1400153eb  add     r8, rbp
0x1400153ee  jnz     loc_1400155C1
0x1400153f4  inc     eax
0x1400153f6  cmp     eax, edi
0x1400153f8  jb      short loc_1400153E0
0x1400153fa  mov     rcx, rbp; hMem
0x1400153fd  call    cs:__imp_LocalFree
0x140015403  jmp     loc_140015372
0x140015408  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x14001540f  mov     r8d, ebx
0x140015412  lea     r14, pPassword
0x140015419  mov     ecx, 1; unsigned int
0x14001541e  mov     [rsp+88h+var_58], r14
0x140015423  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x14001542a  mov     [rsp+88h+var_60], rax
0x14001542f  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140015436  mov     dword ptr [rsp+88h+phkResult], 2Ah ; '*'
0x14001543e  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140015443  mov     rcx, [rsp+88h+hKey]; hKey
0x140015448  test    rcx, rcx
0x14001544b  jnz     short loc_140015495
0x14001544d  mov     [rsp+88h+var_58], r14
0x140015452  lea     rax, aLockstore; "_LockStore"
0x140015459  mov     [rsp+88h+var_60], rax
0x14001545e  mov     dword ptr [rsp+88h+phkResult], 151h
0x140015466  jmp     loc_1400153B8
0x14001546b  lea     r14, pPassword
0x140015472  mov     ebx, 0C0070015h
0x140015477  mov     [rsp+88h+var_58], r14
0x14001547c  lea     rax, aNotInitialized_0; "Not initialized"
0x140015483  mov     [rsp+88h+var_60], rax
0x140015488  mov     dword ptr [rsp+88h+phkResult], 14Bh
0x140015490  jmp     loc_1400153B8
0x140015495  call    cs:__imp_RegCloseKey
0x14001549b  jmp     short loc_14001544D
0x14001549d  test    r13, r13
0x1400154a0  jnz     loc_140015316
0x1400154a6  lea     r14, pPassword
0x1400154ad  mov     ebx, 0C00000F0h
0x1400154b2  mov     [rsp+88h+var_58], r14
0x1400154b7  lea     rax, aPsidIsNull; "pSID is NULL"
0x1400154be  mov     [rsp+88h+var_60], rax
0x1400154c3  mov     dword ptr [rsp+88h+phkResult], 158h
0x1400154cb  jmp     short loc_1400154ED
0x1400154cd  lea     r14, pPassword
0x1400154d4  mov     [rsp+88h+var_58], r14
0x1400154d9  lea     rax, aGetbuiltinprov; "_GetBuiltInProvidersPolicies"
0x1400154e0  mov     [rsp+88h+var_60], rax
0x1400154e5  mov     dword ptr [rsp+88h+phkResult], 18Eh
0x1400154ed  lea     r9, aOnecoreDsSecur_4; "onecore\\ds\\security\\eas\\policyengin"...
0x1400154f4  mov     r8d, ebx
0x1400154f7  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x1400154fe  mov     ecx, 1; unsigned int
0x140015503  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140015508  jmp     loc_14001534B
0x14001550d  lea     rax, aReadpolicies; "_ReadPolicies"
0x140015514  mov     r8d, ebx
0x140015517  lea     r14, pPassword
0x14001551e  mov     ecx, 1; unsigned int
0x140015523  mov     [rsp+88h+var_58], r14
0x140015528  lea     r9, aOnecoreDsSecur_4; "onecore\\ds\\security\\eas\\policyengin"...
0x14001552f  mov     [rsp+88h+var_60], rax
0x140015534  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x14001553b  mov     dword ptr [rsp+88h+phkResult], 170h
0x140015543  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140015548  mov     edi, [rsp+88h+arg_18]
0x14001554f  mov     rbp, [rsp+88h+hMem]
0x140015554  jmp     loc_14001534B
0x140015559  mov     ecx, [rsp+88h+arg_10]; unsigned int
0x140015560  test    ecx, ecx
0x140015562  jnz     short loc_140015576
0x140015564  mov     rax, [rsp+88h+hMem]
0x140015569  mov     [r15], edi
0x14001556c  xor     edi, edi
0x14001556e  mov     [r14], rax
0x140015571  jmp     loc_140015349
0x140015576  mov     rbp, [rsp+88h+hMem]
0x14001557b  lea     eax, [rcx-1]
0x14001557e  test    eax, 0FFFFFFFCh
0x140015583  jnz     loc_140015349
0x140015589  cmp     ecx, 2
0x14001558c  jz      loc_140015349
0x140015592  mov     r9, r15; unsigned int *
0x140015595  mov     [rsp+88h+phkResult], r14; struct _tagEASPolicy **
0x14001559a  mov     r8, rbp; struct _tagEASPolicy *
0x14001559d  mov     edx, edi; unsigned int
0x14001559f  call    ?_GetBuiltInProvidersPolicies@@YAJKKPEAU_tagEASPolicy@@PEAKPEAPEAU1@@Z; _GetBuiltInProvidersPolicies(ulong,ulong,_tagEASPolicy *,ulong *,_tagEASPolicy * *)
0x1400155a4  mov     ebx, eax
0x1400155a6  test    eax, eax
0x1400155a8  jz      loc_140015349
0x1400155ae  jmp     loc_1400154CD
0x1400155b3  mov     rcx, rsi; hKey
0x1400155b6  call    cs:__imp_RegCloseKey
0x1400155bc  jmp     loc_140015354
0x1400155c1  movzx   ecx, word ptr [r8]
0x1400155c5  cmp     cx, 2
0x1400155c9  jb      loc_1400153F4
0x1400155cf  cmp     cx, 0Bh
0x1400155d3  jz      short loc_1400155DF
0x1400155d5  cmp     cx, 13h
0x1400155d9  jnz     loc_1400153F4
0x1400155df  mov     [r8], si
0x1400155e3  jmp     loc_1400153F4
```
