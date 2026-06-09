# EASPoliciesAreBeingEnforced(void)

- ea: `0x180011988`
- end: `0x180011d0b`
- name: `?EASPoliciesAreBeingEnforced@@YA_NXZ`
- size: `899`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018e78`

## callees

- `0x180011988`
- `0x180069a7c`
- `0x180069b08`
- `0x18006a608`
- `0x18006b164`
- `0x18006b2d8`
- `0x18006b660`
- `0x18006b920`
- `0x18006ba70`
- `0x18006bc1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011cd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011cd8`

## string_xrefs

- `0x180011a14`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180011a4e`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180011aa5`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180011b06`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180011c52`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180011cba`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180011b0d`: `_ReadPolicies`

## pseudocode

```c
char __fastcall EASPoliciesAreBeingEnforced(__int64 a1)
{
  char v1; // r15
  int v2; // ebx
  HKEY v3; // r12
  unsigned int v4; // r13d
  int v5; // r14d
  int v6; // esi
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  HKEY v10; // rsi
  unsigned int v11; // eax
  unsigned int *v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+40h] [rbp-38h] BYREF
  HKEY v15; // [rsp+48h] [rbp-30h] BYREF
  struct _tagEASPolicy *v16; // [rsp+50h] [rbp-28h] BYREF
  __int128 v17; // [rsp+58h] [rbp-20h] BYREF
  int v18; // [rsp+68h] [rbp-10h]
  int v19; // [rsp+C0h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int v21; // [rsp+D0h] [rbp+58h] BYREF
  unsigned int v22; // [rsp+D8h] [rbp+60h] BYREF

  v1 = 0;
  if ( (int)EasEngineInitialize(a1, 0) < 0 )
    return v1;
  v21 = 0;
  v2 = 0;
  v18 = 0;
  v3 = 0;
  v22 = 0;
  v14 = 0;
  v4 = 0;
  LODWORD(hKey) = 0;
  v16 = 0;
  v15 = 0;
  v5 = -1073283051;
  v19 = 0;
  v17 = 0;
  if ( !g_bInitialized )
  {
    v6 = -1073283051;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221684245LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      206,
      L"Not initialized",
      &Class);
    goto LABEL_24;
  }
  v7 = _LockStore(1, (void **)&v15);
  v6 = v7;
  if ( v7 )
  {
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v7,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      212,
      L"_LockStore",
      &Class);
    v3 = v15;
  }
  else
  {
    v3 = v15;
    v8 = _CheckForControlledUsers(v15, &v19);
    v6 = v8;
    if ( !v8 )
    {
      v2 = v19;
      if ( !v19 )
      {
        v9 = _ReadPolicies(v3, (unsigned int *)&hKey, &v16);
        v6 = v9;
        if ( v9 )
        {
          DbgPrintfW(
            1u,
            L"(0x%08x) %ws:%u : %ws:%ws\n",
            v9,
            L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
            229,
            L"_ReadPolicies",
            &Class);
          v4 = (unsigned int)hKey;
          goto LABEL_24;
        }
        v4 = (unsigned int)hKey;
        if ( (_DWORD)hKey )
        {
          v6 = _ParsePolicies((unsigned int)hKey, v16, (struct _tagPasswordPolicies *)&v17, &v21, &v22, &v14);
          if ( v6 )
          {
            LODWORD(v13) = 242;
            DbgPrintfW(
              1u,
              L"(0x%08x) %ws:%u : %ws:%ws\n",
              (unsigned int)v6,
              L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
              v13,
              "_ParsePolicies",
              &Class);
            goto LABEL_24;
          }
          if ( v18 == 1 || (_DWORD)v17 || *((_QWORD *)&v17 + 1) || DWORD1(v17) || v21 || v22 || v14 == 1 )
            v2 = 1;
        }
      }
      v6 = 0;
      goto LABEL_24;
    }
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      v8,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      216,
      L"_CheckForControlledUsers",
      &Class);
    v2 = v19;
  }
LABEL_24:
  if ( v3 )
    RegCloseKey(v3);
  _FreePolicies(v4, v16);
  if ( v6 >= 0 && v2 )
  {
    v10 = 0;
    hKey = 0;
    v19 = 0;
    if ( g_bInitialized )
    {
      v11 = _LockStore(1, (void **)&hKey);
      v5 = v11;
      if ( v11 )
      {
        LODWORD(v13) = 292;
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          v11,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
          v13,
          L"_LockStore",
          &Class);
        v10 = hKey;
      }
      else
      {
        v10 = hKey;
        v5 = _CheckForMDMEnforcement(hKey, &v19);
        if ( v5 )
        {
          LODWORD(v13) = 295;
          DbgPrintfW(
            1u,
            L"(0x%08x) %ws:%u : %ws:%ws\n",
            (unsigned int)v5,
            L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
            v13,
            "_CheckForMDMEnforcement",
            &Class);
        }
      }
    }
    else
    {
      LODWORD(v13) = 286;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        3221684245LL,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
        v13,
        L"Not initialized",
        &Class);
    }
    if ( v10 )
      RegCloseKey(v10);
    if ( v5 >= 0 && v19 )
      v2 = 0;
    if ( v2 )
      v1 = 1;
  }
  EasEngineUninitialize();
  return v1;
}

```

## disassembly

```asm
0x180011988  push    rbp
0x18001198a  push    rbx
0x18001198b  push    rsi
0x18001198c  push    rdi
0x18001198d  push    r12
0x18001198f  push    r13
0x180011991  push    r14
0x180011993  push    r15
0x180011995  mov     rbp, rsp
0x180011998  sub     rsp, 78h
0x18001199c  xor     edi, edi
0x18001199e  xor     edx, edx
0x1800119a0  mov     r15b, dil
0x1800119a3  call    EasEngineInitialize
0x1800119a8  test    eax, eax
0x1800119aa  js      loc_180011CF7
0x1800119b0  xor     eax, eax
0x1800119b2  mov     [rbp+arg_10], edi
0x1800119b5  cmp     cs:?g_bInitialized@@3HA, edi; int g_bInitialized
0x1800119bb  lea     rcx, aNotInitialized_0; "Not initialized"
0x1800119c2  mov     ebx, edi
0x1800119c4  mov     [rbp+var_10], eax
0x1800119c7  mov     r12d, edi
0x1800119ca  mov     [rbp+arg_18], edi
0x1800119cd  xorps   xmm0, xmm0
0x1800119d0  mov     [rbp+var_38], edi
0x1800119d3  mov     r13d, edi
0x1800119d6  mov     dword ptr [rbp+hKey], edi
0x1800119d9  mov     [rbp+var_28], rdi
0x1800119dd  lea     rax, Class
0x1800119e4  mov     [rbp+var_30], rdi
0x1800119e8  mov     r14d, 0C0070015h
0x1800119ee  lea     edi, [r12+1]
0x1800119f3  mov     [rbp+arg_0], ebx
0x1800119f6  movups  [rbp+var_20], xmm0
0x1800119fa  jnz     short loc_180011A2E
0x1800119fc  mov     [rsp+78h+var_48], rax
0x180011a01  mov     esi, r14d
0x180011a04  mov     [rsp+78h+var_50], rcx
0x180011a09  mov     r8d, r14d
0x180011a0c  mov     dword ptr [rsp+78h+var_58], 0CEh
0x180011a14  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x180011a1b  mov     ecx, edi; unsigned int
0x180011a1d  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180011a24  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180011a29  jmp     loc_180011BCB
0x180011a2e  lea     rdx, [rbp+var_30]; void **
0x180011a32  mov     ecx, edi; int
0x180011a34  call    ?_LockStore@@YAJHPEAPEAX@Z; _LockStore(int,void * *)
0x180011a39  mov     esi, eax
0x180011a3b  test    eax, eax
0x180011a3d  jz      short loc_180011A80
0x180011a3f  lea     rax, Class
0x180011a46  mov     r8d, esi
0x180011a49  mov     [rsp+78h+var_48], rax
0x180011a4e  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x180011a55  lea     rax, aLockstore; "_LockStore"
0x180011a5c  mov     ecx, edi; unsigned int
0x180011a5e  mov     [rsp+78h+var_50], rax
0x180011a63  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180011a6a  mov     dword ptr [rsp+78h+var_58], 0D4h
0x180011a72  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180011a77  mov     r12, [rbp+var_30]
0x180011a7b  jmp     loc_180011BCB
0x180011a80  mov     r12, [rbp+var_30]
0x180011a84  lea     rdx, [rbp+arg_0]; int *
0x180011a88  mov     rcx, r12; void *
0x180011a8b  call    ?_CheckForControlledUsers@@YAJPEAXPEAH@Z; _CheckForControlledUsers(void *,int *)
0x180011a90  mov     esi, eax
0x180011a92  test    eax, eax
0x180011a94  jz      short loc_180011AD6
0x180011a96  lea     rax, Class
0x180011a9d  mov     r8d, esi
0x180011aa0  mov     [rsp+78h+var_48], rax
0x180011aa5  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x180011aac  lea     rax, aCheckforcontro; "_CheckForControlledUsers"
0x180011ab3  mov     ecx, edi; unsigned int
0x180011ab5  mov     [rsp+78h+var_50], rax
0x180011aba  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180011ac1  mov     dword ptr [rsp+78h+var_58], 0D8h
0x180011ac9  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180011ace  mov     ebx, [rbp+arg_0]
0x180011ad1  jmp     loc_180011BCB
0x180011ad6  mov     ebx, [rbp+arg_0]
0x180011ad9  test    ebx, ebx
0x180011adb  jnz     loc_180011BC9
0x180011ae1  lea     r8, [rbp+var_28]; struct _tagEASPolicy **
0x180011ae5  mov     rcx, r12; hKey
0x180011ae8  lea     rdx, [rbp+hKey]; unsigned int *
0x180011aec  call    ?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z; _ReadPolicies(void *,ulong *,_tagEASPolicy * *)
0x180011af1  mov     esi, eax
0x180011af3  test    eax, eax
0x180011af5  jz      short loc_180011B38
0x180011af7  lea     rax, Class
0x180011afe  mov     r8d, esi
0x180011b01  mov     [rsp+78h+var_48], rax
0x180011b06  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x180011b0d  lea     rax, aReadpolicies; "_ReadPolicies"
0x180011b14  mov     ecx, edi; unsigned int
0x180011b16  mov     [rsp+78h+var_50], rax
0x180011b1b  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180011b22  mov     dword ptr [rsp+78h+var_58], 0E5h
0x180011b2a  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180011b2f  mov     r13d, dword ptr [rbp+hKey]
0x180011b33  jmp     loc_180011BCB
0x180011b38  mov     r13d, dword ptr [rbp+hKey]
0x180011b3c  test    r13d, r13d
0x180011b3f  jz      loc_180011BC9
0x180011b45  mov     rdx, [rbp+var_28]; struct _tagEASPolicy *
0x180011b49  lea     rax, [rbp+var_38]
0x180011b4d  mov     [rsp+78h+var_50], rax; int *
0x180011b52  lea     r9, [rbp+arg_10]; unsigned int *
0x180011b56  lea     rax, [rbp+arg_18]
0x180011b5a  mov     ecx, r13d; unsigned int
0x180011b5d  lea     r8, [rbp+var_20]; struct _tagPasswordPolicies *
0x180011b61  mov     [rsp+78h+var_58], rax; unsigned int *
0x180011b66  call    ?_ParsePolicies@@YAJKPEAU_tagEASPolicy@@PEAU_tagPasswordPolicies@@PEAK2PEAH@Z; _ParsePolicies(ulong,_tagEASPolicy *,_tagPasswordPolicies *,ulong *,ulong *,int *)
0x180011b6b  mov     esi, eax
0x180011b6d  test    eax, eax
0x180011b6f  jz      short loc_180011B99
0x180011b71  lea     rax, Class
0x180011b78  mov     r8d, esi
0x180011b7b  mov     [rsp+78h+var_48], rax
0x180011b80  lea     rax, aParsepolicies; "_ParsePolicies"
0x180011b87  mov     [rsp+78h+var_50], rax
0x180011b8c  mov     dword ptr [rsp+78h+var_58], 0F2h
0x180011b94  jmp     loc_180011A14
0x180011b99  cmp     [rbp+var_10], edi
0x180011b9c  jz      short loc_180011BC7
0x180011b9e  cmp     dword ptr [rbp+var_20], 0
0x180011ba2  jnz     short loc_180011BC7
0x180011ba4  cmp     dword ptr [rbp+var_20+8], 0
0x180011ba8  jnz     short loc_180011BC7
0x180011baa  cmp     dword ptr [rbp+var_20+0Ch], 0
0x180011bae  jnz     short loc_180011BC7
0x180011bb0  cmp     dword ptr [rbp+var_20+4], 0
0x180011bb4  jnz     short loc_180011BC7
0x180011bb6  cmp     [rbp+arg_10], 0
0x180011bba  jnz     short loc_180011BC7
0x180011bbc  cmp     [rbp+arg_18], 0
0x180011bc0  jnz     short loc_180011BC7
0x180011bc2  cmp     [rbp+var_38], edi
0x180011bc5  jnz     short loc_180011BC9
0x180011bc7  mov     ebx, edi
0x180011bc9  xor     esi, esi
0x180011bcb  test    r12, r12
0x180011bce  jz      short loc_180011BD9
0x180011bd0  mov     rcx, r12; hKey
0x180011bd3  call    cs:__imp_RegCloseKey
0x180011bd9  mov     rdx, [rbp+var_28]; struct _tagEASPolicy *
0x180011bdd  mov     ecx, r13d; unsigned int
0x180011be0  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x180011be5  xor     r12d, r12d
0x180011be8  test    esi, esi
0x180011bea  js      loc_180011CF2
0x180011bf0  test    ebx, ebx
0x180011bf2  jz      loc_180011CF2
0x180011bf8  cmp     cs:?g_bInitialized@@3HA, r12d; int g_bInitialized
0x180011bff  mov     esi, r12d
0x180011c02  mov     [rbp+hKey], r12
0x180011c06  mov     ecx, edi; int
0x180011c08  mov     [rbp+arg_0], r12d
0x180011c0c  jnz     short loc_180011C33
0x180011c0e  lea     rax, Class
0x180011c15  mov     [rsp+78h+var_48], rax
0x180011c1a  lea     rax, aNotInitialized_0; "Not initialized"
0x180011c21  mov     [rsp+78h+var_50], rax
0x180011c26  mov     dword ptr [rsp+78h+var_58], 11Eh
0x180011c2e  jmp     loc_180011CBA
0x180011c33  lea     rdx, [rbp+hKey]; void **
0x180011c37  call    ?_LockStore@@YAJHPEAPEAX@Z; _LockStore(int,void * *)
0x180011c3c  mov     r14d, eax
0x180011c3f  test    eax, eax
0x180011c41  jz      short loc_180011C81
0x180011c43  lea     rax, Class
0x180011c4a  mov     r8d, r14d
0x180011c4d  mov     [rsp+78h+var_48], rax
0x180011c52  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x180011c59  lea     rax, aLockstore; "_LockStore"
0x180011c60  mov     ecx, edi; unsigned int
0x180011c62  mov     [rsp+78h+var_50], rax
0x180011c67  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180011c6e  mov     dword ptr [rsp+78h+var_58], 124h
0x180011c76  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180011c7b  mov     rsi, [rbp+hKey]
0x180011c7f  jmp     short loc_180011CD0
0x180011c81  mov     rsi, [rbp+hKey]
0x180011c85  lea     rdx, [rbp+arg_0]; int *
0x180011c89  mov     rcx, rsi; void *
0x180011c8c  call    ?_CheckForMDMEnforcement@@YAJPEAXPEAH@Z; _CheckForMDMEnforcement(void *,int *)
0x180011c91  mov     r14d, eax
0x180011c94  test    eax, eax
0x180011c96  jz      short loc_180011CD0
0x180011c98  lea     rax, Class
0x180011c9f  mov     ecx, edi; unsigned int
0x180011ca1  mov     [rsp+78h+var_48], rax
0x180011ca6  lea     rax, aCheckformdmenf; "_CheckForMDMEnforcement"
0x180011cad  mov     [rsp+78h+var_50], rax
0x180011cb2  mov     dword ptr [rsp+78h+var_58], 127h
0x180011cba  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x180011cc1  mov     r8d, r14d
0x180011cc4  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180011ccb  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180011cd0  test    rsi, rsi
0x180011cd3  jz      short loc_180011CDE
0x180011cd5  mov     rcx, rsi; hKey
0x180011cd8  call    cs:__imp_RegCloseKey
0x180011cde  test    r14d, r14d
0x180011ce1  js      short loc_180011CEB
0x180011ce3  cmp     [rbp+arg_0], r12d
0x180011ce7  cmovnz  ebx, r12d
0x180011ceb  test    ebx, ebx
0x180011ced  jz      short loc_180011CF2
0x180011cef  mov     r15b, dil
0x180011cf2  call    EasEngineUninitialize
0x180011cf7  mov     al, r15b
0x180011cfa  add     rsp, 78h
0x180011cfe  pop     r15
0x180011d00  pop     r14
0x180011d02  pop     r13
0x180011d04  pop     r12
0x180011d06  pop     rdi
0x180011d07  pop     rsi
0x180011d08  pop     rbx
0x180011d09  pop     rbp
0x180011d0a  retn
```
