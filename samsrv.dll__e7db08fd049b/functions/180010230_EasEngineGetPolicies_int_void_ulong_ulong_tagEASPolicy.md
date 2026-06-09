# EasEngineGetPolicies(int,void *,ulong,ulong *,_tagEASPolicy * *)

- ea: `0x180010230`
- end: `0x18001083a`
- name: `?EasEngineGetPolicies@@YAJHPEAXKPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `1546`
- prototype: `__int64 __fastcall(int, void *, int, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ed50`
- `0x18000f830`
- `0x18000fa80`
- `0x180010120`

## callees

- `0x180010230`
- `0x180010840`
- `0x180027c58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800102b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800102b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010694`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010694`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800103f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800103f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010393`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800105e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010393`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800105e1`

## string_xrefs

- `0x180010468`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180010513`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180010577`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180010600`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180010701`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x18001044d`: `_ReadPolicies`
- `0x18001063b`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x1800107b8`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x180010620`: `RegOpenKeyEx`
- `0x1800107dd`: `_myVariantCopy`
- `0x1800106bb`: `pSID is NULL`

## pseudocode

```c
__int64 __fastcall EasEngineGetPolicies(int a1, void *a2, int a3, unsigned int *a4, struct _tagEASPolicy **a5)
{
  __int64 v5; // rbx
  char *v6; // rbp
  struct _tagEASPolicy **v10; // r14
  unsigned int Policies; // edi
  bool v12; // zf
  HKEY v13; // rsi
  unsigned int k; // eax
  char *v15; // r8
  __int16 v16; // dx
  struct _tagEASPolicy *v18; // r10
  unsigned int v19; // r12d
  unsigned int i; // edx
  char *v21; // r8
  _DWORD *v22; // rcx
  _WORD *v23; // rcx
  _WORD *v24; // r8
  int v25; // r9d
  __int64 v26; // rcx
  char *v27; // r8
  unsigned int j; // ecx
  char *v29; // rdx
  __int16 v30; // ax
  struct _tagEASPolicy *v31; // rax
  __int64 v32; // r8
  const wchar_t *v33; // r10
  int v34; // eax
  const wchar_t *v35; // r8
  int v36; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-68h]
  PHKEY phkResulta; // [rsp+20h] [rbp-68h]
  PHKEY phkResultb; // [rsp+20h] [rbp-68h]
  HLOCAL hMem; // [rsp+40h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-40h] BYREF
  HLOCAL v43; // [rsp+A8h] [rbp+20h] BYREF

  LODWORD(v5) = 0;
  v6 = 0;
  LODWORD(v43) = 0;
  hMem = 0;
  if ( !a4 || (v10 = a5) == 0 )
  {
    Policies = -1073741811;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225485LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      323,
      L"Null Arg(s)",
      &Annotation);
    goto LABEL_14;
  }
  v12 = g_bInitialized == 0;
  *a4 = 0;
  *v10 = 0;
  if ( v12 )
  {
    Policies = -1073283051;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221684245LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      331,
      L"Not initialized",
      &Annotation);
    goto LABEL_14;
  }
  hKey = 0;
  Policies = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\EAS\\Policies", 0, 0x20019u, &hKey);
  if ( Policies - 2 <= 1 )
  {
    Policies = 0;
LABEL_24:
    v12 = Policies == 0;
    goto LABEL_6;
  }
  v12 = Policies == 0;
  if ( (int)Policies > 0 )
  {
    Policies = (unsigned __int16)Policies | 0xC0070000;
    goto LABEL_24;
  }
LABEL_6:
  if ( !v12 )
  {
    LODWORD(phkResult) = 42;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      Policies,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      phkResult,
      L"RegOpenKeyEx",
      &Annotation);
    if ( hKey )
      RegCloseKey(hKey);
    LODWORD(phkResultb) = 337;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      Policies,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      phkResultb,
      L"_LockStore",
      &Annotation);
    goto LABEL_14;
  }
  v13 = hKey;
  hKey = 0;
  if ( !a1 && !a2 )
  {
    Policies = -1073741584;
    LODWORD(phkResult) = 344;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225712LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      phkResult,
      L"pSID is NULL",
      &Annotation);
    goto LABEL_12;
  }
  Policies = _ReadPolicies(v13, (unsigned int *)&v43, (struct _tagEASPolicy **)&hMem);
  if ( Policies )
  {
    LODWORD(phkResult) = 368;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      Policies,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      phkResult,
      L"_ReadPolicies",
      &Annotation);
    LODWORD(v5) = (_DWORD)v43;
    v6 = (char *)hMem;
    goto LABEL_12;
  }
  v5 = (unsigned int)v43;
  if ( !(_DWORD)v43 )
  {
    v6 = (char *)hMem;
LABEL_11:
    Policies = 0;
    goto LABEL_12;
  }
  if ( !a3 )
  {
    v31 = (struct _tagEASPolicy *)hMem;
    *a4 = (unsigned int)v43;
    LODWORD(v5) = 0;
    *v10 = v31;
    goto LABEL_11;
  }
  v6 = (char *)hMem;
  if ( ((a3 - 1) & 0xFFFFFFFC) != 0 )
    goto LABEL_11;
  if ( a3 == 2 )
    goto LABEL_11;
  *a4 = 0;
  *v10 = 0;
  if ( !(_DWORD)v5 )
    goto LABEL_11;
  v43 = LocalAlloc(0x40u, 32 * v5);
  v18 = (struct _tagEASPolicy *)v43;
  if ( !v43 )
  {
    Policies = -1073741801;
    LODWORD(phkResult) = 31;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225495LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      phkResult,
      L"LocalAlloc",
      &Annotation);
    goto LABEL_59;
  }
  v19 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned int)v5 )
    {
      *a4 = v19;
      *v10 = v18;
      goto LABEL_11;
    }
    switch ( a3 )
    {
      case 3:
        v21 = &v6[32 * i];
        if ( *(_DWORD *)v21 != 7 )
          continue;
        break;
      case 1:
        v25 = 0;
        v26 = 0;
        v21 = &v6[32 * i];
        while ( (unsigned int)v26 < 5 )
        {
          if ( *(_DWORD *)v21 == *((_DWORD *)&g_dwPasswordProvPolicies + v26) )
          {
            v25 = 1;
            break;
          }
          v26 = (unsigned int)(v26 + 1);
        }
        if ( !v25 )
          continue;
        break;
      case 4:
        v21 = &v6[32 * i];
        if ( *(_DWORD *)v21 != 6 )
          continue;
        break;
      default:
        v32 = 3221225485LL;
        v33 = L"Invalid Provider";
        Policies = -1073741811;
        v34 = 65;
        goto LABEL_52;
    }
    v22 = (_DWORD *)((char *)v18 + 32 * v19);
    *v22 = *(_DWORD *)v21;
    v23 = v22 + 2;
    if ( !v23 )
      break;
    *v23 = 0;
    v24 = v21 + 8;
    if ( v24 )
    {
      if ( *v24 == 11 )
      {
        v23[4] = v24[4];
      }
      else
      {
        if ( *v24 != 19 )
        {
          Policies = -1073741637;
          v35 = L"unsupported type";
          v36 = 382;
          goto LABEL_76;
        }
        *((_DWORD *)v23 + 2) = *((_DWORD *)v24 + 2);
      }
      *v23 = *v24;
    }
    ++v19;
  }
  Policies = -1073741811;
  v35 = L"Null Arg";
  v36 = 362;
LABEL_76:
  LODWORD(phkResult) = v36;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    Policies,
    L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
    phkResult,
    v35,
    &Annotation);
  v32 = Policies;
  v33 = L"_myVariantCopy";
  v34 = 71;
LABEL_52:
  LODWORD(phkResult) = v34;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v32,
    L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
    phkResult,
    v33,
    &Annotation);
  v27 = (char *)v43;
  for ( j = 0; j < v19; ++j )
  {
    v29 = &v27[32 * j + 8];
    if ( v29 )
    {
      v30 = *(_WORD *)v29;
      if ( *(_WORD *)v29 >= 2u && (v30 == 11 || v30 == 19) )
        *(_WORD *)v29 = 0;
    }
  }
  LocalFree(v27);
LABEL_59:
  LODWORD(phkResulta) = 398;
  DbgPrintfW(
    1u,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    Policies,
    L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
    phkResulta,
    L"_GetBuiltInProvidersPolicies",
    &Annotation);
LABEL_12:
  if ( v13 )
    RegCloseKey(v13);
LABEL_14:
  if ( v6 )
  {
    for ( k = 0; k < (unsigned int)v5; ++k )
    {
      v15 = &v6[32 * k + 8];
      if ( v15 )
      {
        v16 = *(_WORD *)v15;
        if ( *(_WORD *)v15 >= 2u && (v16 == 11 || v16 == 19) )
          *(_WORD *)v15 = 0;
      }
    }
    LocalFree(v6);
  }
  return Policies;
}

```

## disassembly

```asm
0x180010230  mov     rax, rsp
0x180010233  mov     [rax+10h], rdx
0x180010237  push    rbx
0x180010238  push    rbp
0x180010239  push    rdi
0x18001023a  sub     rsp, 70h
0x18001023e  mov     [rax+8], rsi
0x180010242  xor     ebx, ebx
0x180010244  mov     [rax-20h], r12
0x180010248  xor     ebp, ebp
0x18001024a  mov     [rax-28h], r13
0x18001024e  mov     r13d, r8d
0x180010251  mov     [rax-30h], r14
0x180010255  mov     r12d, ecx
0x180010258  mov     [rax-38h], r15
0x18001025c  mov     r15, r9
0x18001025f  mov     [rax+20h], ebx
0x180010262  mov     [rax-48h], rbp
0x180010266  test    r9, r9
0x180010269  jz      loc_1800107FD
0x18001026f  mov     r14, [rsp+88h+arg_20]
0x180010277  test    r14, r14
0x18001027a  jz      loc_1800107FD
0x180010280  cmp     cs:?g_bInitialized@@3HA, ebx; int g_bInitialized
0x180010286  mov     [r9], ebx
0x180010289  mov     [r14], rbx
0x18001028c  jz      loc_1800104EB
0x180010292  mov     [rax-40h], rbx
0x180010296  lea     rax, [rax-40h]
0x18001029a  mov     r9d, 20019h; samDesired
0x1800102a0  mov     [rsp+88h+phkResult], rax; phkResult
0x1800102a5  xor     r8d, r8d; ulOptions
0x1800102a8  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Control\\EAS"...
0x1800102af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800102b6  call    cs:__imp_RegOpenKeyExW
0x1800102bc  mov     edi, eax
0x1800102be  add     eax, 0FFFFFFFEh
0x1800102c1  cmp     eax, 1
0x1800102c4  jbe     loc_1800103A3
0x1800102ca  test    edi, edi
0x1800102cc  jg      loc_180010686
0x1800102d2  jnz     loc_180010620
0x1800102d8  mov     rsi, [rsp+88h+hKey]
0x1800102dd  mov     [rsp+88h+hKey], rbx
0x1800102e2  test    r12d, r12d
0x1800102e5  jz      loc_18001069C
0x1800102eb  lea     r8, [rsp+88h+hMem]; struct _tagEASPolicy **
0x1800102f0  mov     rcx, rsi; hKey
0x1800102f3  lea     rdx, [rsp+88h+arg_18]; unsigned int *
0x1800102fb  call    ?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z; _ReadPolicies(void *,ulong *,_tagEASPolicy * *)
0x180010300  mov     edi, eax
0x180010302  test    eax, eax
0x180010304  jnz     loc_18001044D
0x18001030a  mov     ebx, dword ptr [rsp+88h+arg_18]
0x180010311  test    ebx, ebx
0x180010313  jnz     loc_1800103AC
0x180010319  mov     rbp, [rsp+88h+hMem]
0x18001031e  xor     edi, edi
0x180010320  test    rsi, rsi
0x180010323  jz      short loc_18001032E
0x180010325  mov     rcx, rsi; hKey
0x180010328  call    cs:__imp_RegCloseKey
0x18001032e  mov     r15, [rsp+88h+var_38]
0x180010333  mov     r14, [rsp+88h+var_30]
0x180010338  mov     r13, [rsp+88h+var_28]
0x18001033d  mov     r12, [rsp+88h+var_20]
0x180010342  mov     rsi, [rsp+88h+arg_0]
0x18001034a  test    rbp, rbp
0x18001034d  jz      short loc_180010399
0x18001034f  xor     eax, eax
0x180010351  test    ebx, ebx
0x180010353  jz      short loc_180010390
0x180010355  nop     word ptr [rax+rax+00000000h]
0x180010360  mov     r8d, eax
0x180010363  shl     r8, 5
0x180010367  add     r8, 8
0x18001036b  add     r8, rbp
0x18001036e  jz      short loc_18001038A
0x180010370  movzx   edx, word ptr [r8]
0x180010374  cmp     dx, 2
0x180010378  jb      short loc_18001038A
0x18001037a  cmp     dx, 0Bh
0x18001037e  jnz     loc_18001082B
0x180010384  xor     edx, edx
0x180010386  mov     [r8], dx
0x18001038a  inc     eax
0x18001038c  cmp     eax, ebx
0x18001038e  jb      short loc_180010360
0x180010390  mov     rcx, rbp; hMem
0x180010393  call    cs:__imp_LocalFree
0x180010399  mov     eax, edi
0x18001039b  add     rsp, 70h
0x18001039f  pop     rdi
0x1800103a0  pop     rbp
0x1800103a1  pop     rbx
0x1800103a2  retn
0x1800103a3  xor     edi, edi
0x1800103a5  test    edi, edi
0x1800103a7  jmp     loc_1800102D2
0x1800103ac  test    r13d, r13d
0x1800103af  jz      loc_1800106D4
0x1800103b5  mov     rbp, [rsp+88h+hMem]
0x1800103ba  lea     eax, [r13-1]
0x1800103be  test    eax, 0FFFFFFFCh
0x1800103c3  jnz     loc_18001031E
0x1800103c9  cmp     r13d, 2
0x1800103cd  jz      loc_18001031E
0x1800103d3  mov     dword ptr [r15], 0
0x1800103da  mov     qword ptr [r14], 0
0x1800103e1  test    ebx, ebx
0x1800103e3  jz      loc_18001031E
0x1800103e9  mov     rdx, rbx
0x1800103ec  mov     ecx, 40h ; '@'; uFlags
0x1800103f1  shl     rdx, 5; uBytes
0x1800103f5  call    cs:__imp_LocalAlloc
0x1800103fb  mov     [rsp+88h+arg_18], rax
0x180010403  mov     r10, rax
0x180010406  test    rax, rax
0x180010409  jz      loc_1800106E6
0x18001040f  xor     r12d, r12d
0x180010412  lea     r11, ?g_dwPasswordProvPolicies@@3PAKA; ulong near * g_dwPasswordProvPolicies
0x180010419  xor     edx, edx
0x18001041b  nop     dword ptr [rax+rax+00h]
0x180010420  cmp     edx, ebx
0x180010422  jnb     short loc_180010442
0x180010424  cmp     r13d, 3
0x180010428  jnz     loc_180010530
0x18001042e  mov     r8d, edx
0x180010431  shl     r8, 5
0x180010435  add     r8, rbp
0x180010438  cmp     dword ptr [r8], 7
0x18001043c  jz      short loc_180010499
0x18001043e  inc     edx
0x180010440  jmp     short loc_180010420
0x180010442  mov     [r15], r12d
0x180010445  mov     [r14], r10
0x180010448  jmp     loc_18001031E
0x18001044d  lea     rax, aReadpolicies; "_ReadPolicies"
0x180010454  mov     r8d, edi
0x180010457  lea     r14, Annotation
0x18001045e  mov     ecx, 1; unsigned int
0x180010463  mov     [rsp+88h+var_58], r14
0x180010468  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18001046f  mov     [rsp+88h+var_60], rax
0x180010474  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001047b  mov     dword ptr [rsp+88h+phkResult], 170h
0x180010483  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180010488  mov     ebx, dword ptr [rsp+88h+arg_18]
0x18001048f  mov     rbp, [rsp+88h+hMem]
0x180010494  jmp     loc_180010320
0x180010499  mov     eax, [r8]
0x18001049c  mov     ecx, r12d
0x18001049f  shl     rcx, 5
0x1800104a3  add     rcx, r10
0x1800104a6  mov     [rcx], eax
0x1800104a8  add     rcx, 8
0x1800104ac  jz      loc_180010796
0x1800104b2  xor     eax, eax
0x1800104b4  mov     [rcx], ax
0x1800104b7  add     r8, 8
0x1800104bb  jz      short loc_1800104E3
0x1800104bd  movzx   eax, word ptr [r8]
0x1800104c1  cmp     ax, 0Bh
0x1800104c5  jz      loc_180010754
0x1800104cb  cmp     ax, 13h
0x1800104cf  jnz     loc_180010783
0x1800104d5  mov     eax, [r8+8]
0x1800104d9  mov     [rcx+8], eax
0x1800104dc  movzx   eax, word ptr [r8]
0x1800104e0  mov     [rcx], ax
0x1800104e3  inc     r12d
0x1800104e6  jmp     loc_18001043E
0x1800104eb  lea     r14, Annotation
0x1800104f2  mov     edi, 0C0070015h
0x1800104f7  mov     [rsp+88h+var_58], r14
0x1800104fc  lea     rax, aNotInitialized; "Not initialized"
0x180010503  mov     [rsp+88h+var_60], rax
0x180010508  mov     r8d, edi
0x18001050b  mov     dword ptr [rsp+88h+phkResult], 14Bh
0x180010513  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18001051a  mov     ecx, 1; unsigned int
0x18001051f  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010526  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001052b  jmp     loc_18001032E
0x180010530  mov     eax, r13d
0x180010533  sub     eax, 1
0x180010536  jnz     loc_18001072B
0x18001053c  mov     r8d, edx
0x18001053f  xor     r9d, r9d
0x180010542  shl     r8, 5
0x180010546  xor     ecx, ecx
0x180010548  add     r8, rbp
0x18001054b  nop     dword ptr [rax+rax+00h]
0x180010550  cmp     ecx, 5
0x180010553  jnb     short loc_180010566
0x180010555  mov     eax, [r11+rcx*4]
0x180010559  cmp     [r8], eax
0x18001055c  jz      loc_180010749
0x180010562  inc     ecx
0x180010564  jmp     short loc_180010550
0x180010566  test    r9d, r9d
0x180010569  jz      loc_18001043E
0x18001056f  jmp     loc_180010499
0x180010574  mov     r11, r14
0x180010577  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18001057e  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010585  mov     ecx, 1; unsigned int
0x18001058a  mov     [rsp+88h+var_58], r14
0x18001058f  mov     [rsp+88h+var_60], r10
0x180010594  mov     dword ptr [rsp+88h+phkResult], eax
0x180010598  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001059d  mov     r8, [rsp+88h+arg_18]
0x1800105a5  xor     ecx, ecx
0x1800105a7  test    r12d, r12d
0x1800105aa  jz      short loc_1800105DE
0x1800105ac  nop     dword ptr [rax+00h]
0x1800105b0  mov     edx, ecx
0x1800105b2  shl     rdx, 5
0x1800105b6  add     rdx, 8
0x1800105ba  add     rdx, r8
0x1800105bd  jz      short loc_1800105D7
0x1800105bf  movzx   eax, word ptr [rdx]
0x1800105c2  cmp     ax, 2
0x1800105c6  jb      short loc_1800105D7
0x1800105c8  cmp     ax, 0Bh
0x1800105cc  jnz     loc_1800107EE
0x1800105d2  xor     eax, eax
0x1800105d4  mov     [rdx], ax
0x1800105d7  inc     ecx
0x1800105d9  cmp     ecx, r12d
0x1800105dc  jb      short loc_1800105B0
0x1800105de  mov     rcx, r8; hMem
0x1800105e1  call    cs:__imp_LocalFree
0x1800105e7  mov     [rsp+88h+var_58], r14
0x1800105ec  lea     rax, aGetbuiltinprov; "_GetBuiltInProvidersPolicies"
0x1800105f3  mov     [rsp+88h+var_60], rax
0x1800105f8  mov     dword ptr [rsp+88h+phkResult], 18Eh
0x180010600  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x180010607  mov     r8d, edi
0x18001060a  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010611  mov     ecx, 1; unsigned int
0x180010616  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001061b  jmp     loc_180010320
0x180010620  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x180010627  mov     r8d, edi
0x18001062a  lea     r14, Annotation
0x180010631  mov     ecx, 1; unsigned int
0x180010636  mov     [rsp+88h+var_58], r14
0x18001063b  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x180010642  mov     [rsp+88h+var_60], rax
0x180010647  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001064e  mov     dword ptr [rsp+88h+phkResult], 2Ah ; '*'
0x180010656  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001065b  mov     rcx, [rsp+88h+hKey]; hKey
0x180010660  test    rcx, rcx
0x180010663  jnz     short loc_180010694
0x180010665  mov     [rsp+88h+var_58], r14
0x18001066a  lea     rax, aLockstore; "_LockStore"
0x180010671  mov     [rsp+88h+var_60], rax
0x180010676  mov     r8d, edi
0x180010679  mov     dword ptr [rsp+88h+phkResult], 151h
0x180010681  jmp     loc_180010513
0x180010686  movzx   edi, di
0x180010689  or      edi, 0C0070000h
0x18001068f  jmp     loc_1800103A5
0x180010694  call    cs:__imp_RegCloseKey
0x18001069a  jmp     short loc_180010665
0x18001069c  cmp     [rsp+88h+arg_8], rbx
0x1800106a4  jnz     loc_1800102EB
0x1800106aa  lea     r14, Annotation
0x1800106b1  mov     edi, 0C00000F0h
0x1800106b6  mov     [rsp+88h+var_58], r14
0x1800106bb  lea     rax, aPsidIsNull; "pSID is NULL"
0x1800106c2  mov     [rsp+88h+var_60], rax
0x1800106c7  mov     dword ptr [rsp+88h+phkResult], 158h
0x1800106cf  jmp     loc_180010600
0x1800106d4  mov     rax, [rsp+88h+hMem]
0x1800106d9  mov     [r15], ebx
0x1800106dc  xor     ebx, ebx
0x1800106de  mov     [r14], rax
0x1800106e1  jmp     loc_18001031E
0x1800106e6  lea     rax, aLocalalloc; "LocalAlloc"
0x1800106ed  mov     edi, 0C0000017h
0x1800106f2  lea     r14, Annotation
0x1800106f9  mov     r8d, edi
0x1800106fc  mov     [rsp+88h+var_58], r14
0x180010701  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x180010708  mov     [rsp+88h+var_60], rax
0x18001070d  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180010714  mov     ecx, 1; unsigned int
0x180010719  mov     dword ptr [rsp+88h+phkResult], 1Fh
0x180010721  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180010726  jmp     loc_1800105E7
0x18001072b  cmp     eax, 3
0x18001072e  jnz     short loc_180010762
0x180010730  mov     r8d, edx
0x180010733  shl     r8, 5
0x180010737  add     r8, rbp
0x18001073a  cmp     dword ptr [r8], 6
0x18001073e  jnz     loc_18001043E
  ... truncated ...
```
