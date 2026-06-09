# EasEngineGetPolicies(int,void *,ulong,ulong *,_tagEASPolicy * *)

- ea: `0x180019e3c`
- end: `0x18001a014`
- name: `?EasEngineGetPolicies@@YAJHPEAXKPEAKPEAPEAU_tagEASPolicy@@@Z`
- size: `472`
- prototype: `__int64 __fastcall(__int64, void *, __int64, unsigned int *, struct _tagEASPolicy **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016740`

## callees

- `0x180019e3c`
- `0x18001a01c`
- `0x18001a154`
- `0x18001a22c`
- `0x18001a270`
- `0x18001a344`
- `0x18001a788`

## string_xrefs

- `0x180019ed6`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180019f34`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180019fd3`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180019f3b`: `_ReadPolicies`

## pseudocode

```c
__int64 __fastcall EasEngineGetPolicies(__int64 a1, void *a2, __int64 a3, unsigned int *a4, struct _tagEASPolicy **a5)
{
  unsigned int v5; // edi
  HKEY v6; // r14
  struct _tagEASPolicy **v8; // rsi
  bool v9; // zf
  unsigned int BuiltInProvidersPolicies; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rcx
  struct _tagEASPolicy **v15; // [rsp+20h] [rbp-20h]
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+40h] BYREF
  struct _tagEASPolicy *v18; // [rsp+88h] [rbp+48h] BYREF

  v5 = 0;
  v6 = 0;
  v17 = 0;
  v18 = 0;
  hKey = 0;
  if ( a4 && (v8 = a5) != 0 )
  {
    v9 = g_bInitialized == 0;
    *a4 = 0;
    *v8 = 0;
    if ( v9 )
    {
      BuiltInProvidersPolicies = -1073283051;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        3221684245LL,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
        331,
        L"Not initialized",
        &pszPassword);
    }
    else
    {
      v11 = _LockStore(a1, (void **)&hKey);
      BuiltInProvidersPolicies = v11;
      if ( v11 )
      {
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          v11,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
          337,
          L"_LockStore",
          &pszPassword);
        v6 = hKey;
      }
      else
      {
        v6 = hKey;
        v12 = _ReadPolicies(hKey, &v17, &v18);
        BuiltInProvidersPolicies = v12;
        if ( v12 )
        {
          DbgPrintfW(
            1u,
            L"(0x%08x) %ws:%u : %ws:%ws\n",
            v12,
            L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
            368,
            L"_ReadPolicies",
            &pszPassword);
          v5 = v17;
        }
        else
        {
          v5 = v17;
          if ( v17 && (BuiltInProvidersPolicies = _GetBuiltInProvidersPolicies(v13, v17, v18, a4, v8)) != 0 )
          {
            LODWORD(v15) = 398;
            DbgPrintfW(
              1u,
              L"(0x%08x) %ws:%u : %ws:%ws\n",
              BuiltInProvidersPolicies,
              L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
              v15,
              L"_GetBuiltInProvidersPolicies",
              &pszPassword);
          }
          else
          {
            BuiltInProvidersPolicies = 0;
          }
        }
      }
    }
  }
  else
  {
    BuiltInProvidersPolicies = -1073741811;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221225485LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      323,
      L"Null Arg(s)",
      &pszPassword);
  }
  _UnlockStore(v6);
  _FreePolicies(v5, v18);
  return BuiltInProvidersPolicies;
}

```

## disassembly

```asm
0x180019e3c  mov     r11, rsp
0x180019e3f  mov     [r11+8], rbx
0x180019e43  mov     [r11+18h], r8d
0x180019e47  mov     [r11+10h], rdx
0x180019e4b  push    rbp
0x180019e4c  push    rsi
0x180019e4d  push    rdi
0x180019e4e  push    r14
0x180019e50  push    r15
0x180019e52  mov     rbp, rsp
0x180019e55  sub     rsp, 40h
0x180019e59  xor     edi, edi
0x180019e5b  xor     r14d, r14d
0x180019e5e  mov     [rbp+arg_10], edi
0x180019e61  mov     r15, r9
0x180019e64  mov     [rbp+arg_18], rdi
0x180019e68  mov     [rbp+hKey], r14
0x180019e6c  test    r9, r9
0x180019e6f  jz      loc_180019FAE
0x180019e75  mov     rsi, [rbp+arg_20]
0x180019e79  test    rsi, rsi
0x180019e7c  jz      loc_180019FAE
0x180019e82  cmp     cs:?g_bInitialized@@3HA, edi; int g_bInitialized
0x180019e88  mov     [r9], edi
0x180019e8b  mov     [rsi], rdi
0x180019e8e  jnz     short loc_180019EB8
0x180019e90  lea     rax, pszPassword
0x180019e97  mov     ebx, 0C0070015h
0x180019e9c  mov     [r11-38h], rax
0x180019ea0  lea     rax, aNotInitialized; "Not initialized"
0x180019ea7  mov     [r11-40h], rax
0x180019eab  mov     dword ptr [rsp+40h+var_20], 14Bh
0x180019eb3  jmp     loc_180019FD3
0x180019eb8  lea     rdx, [rbp+hKey]; void **
0x180019ebc  call    ?_LockStore@@YAJHPEAPEAX@Z; _LockStore(int,void * *)
0x180019ec1  mov     ebx, eax
0x180019ec3  test    eax, eax
0x180019ec5  jz      short loc_180019F0B
0x180019ec7  lea     rax, pszPassword
0x180019ece  mov     r8d, ebx
0x180019ed1  mov     [rsp+40h+var_10], rax
0x180019ed6  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x180019edd  lea     rax, aLockstore; "_LockStore"
0x180019ee4  mov     ecx, 1; unsigned int
0x180019ee9  mov     [rsp+40h+var_18], rax
0x180019eee  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180019ef5  mov     dword ptr [rsp+40h+var_20], 151h
0x180019efd  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180019f02  mov     r14, [rbp+hKey]
0x180019f06  jmp     loc_180019FEE
0x180019f0b  mov     r14, [rbp+hKey]
0x180019f0f  lea     r8, [rbp+arg_18]; struct _tagEASPolicy **
0x180019f13  mov     rcx, r14; hKey
0x180019f16  lea     rdx, [rbp+arg_10]; unsigned int *
0x180019f1a  call    ?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z; _ReadPolicies(void *,ulong *,_tagEASPolicy * *)
0x180019f1f  mov     ebx, eax
0x180019f21  test    eax, eax
0x180019f23  jz      short loc_180019F68
0x180019f25  lea     rax, pszPassword
0x180019f2c  mov     r8d, ebx
0x180019f2f  mov     [rsp+40h+var_10], rax
0x180019f34  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x180019f3b  lea     rax, aReadpolicies; "_ReadPolicies"
0x180019f42  mov     ecx, 1; unsigned int
0x180019f47  mov     [rsp+40h+var_18], rax
0x180019f4c  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180019f53  mov     dword ptr [rsp+40h+var_20], 170h
0x180019f5b  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180019f60  mov     edi, [rbp+arg_10]
0x180019f63  jmp     loc_180019FEE
0x180019f68  mov     edi, [rbp+arg_10]
0x180019f6b  test    edi, edi
0x180019f6d  jz      short loc_180019FAA
0x180019f6f  mov     r8, [rbp+arg_18]; struct _tagEASPolicy *
0x180019f73  mov     r9, r15; unsigned int *
0x180019f76  mov     edx, edi; unsigned int
0x180019f78  mov     [rsp+40h+var_20], rsi; struct _tagEASPolicy **
0x180019f7d  call    ?_GetBuiltInProvidersPolicies@@YAJKKPEAU_tagEASPolicy@@PEAKPEAPEAU1@@Z; _GetBuiltInProvidersPolicies(ulong,ulong,_tagEASPolicy *,ulong *,_tagEASPolicy * *)
0x180019f82  mov     ebx, eax
0x180019f84  test    eax, eax
0x180019f86  jz      short loc_180019FAA
0x180019f88  lea     rax, pszPassword
0x180019f8f  mov     [rsp+40h+var_10], rax
0x180019f94  lea     rax, aGetbuiltinprov; "_GetBuiltInProvidersPolicies"
0x180019f9b  mov     [rsp+40h+var_18], rax
0x180019fa0  mov     dword ptr [rsp+40h+var_20], 18Eh
0x180019fa8  jmp     short loc_180019FD3
0x180019faa  xor     ebx, ebx
0x180019fac  jmp     short loc_180019FEE
0x180019fae  lea     rax, pszPassword
0x180019fb5  mov     ebx, 0C000000Dh
0x180019fba  mov     [rsp+40h+var_10], rax
0x180019fbf  lea     rax, aNullArgS; "Null Arg(s)"
0x180019fc6  mov     [rsp+40h+var_18], rax
0x180019fcb  mov     dword ptr [rsp+40h+var_20], 143h
0x180019fd3  lea     r9, aOnecoreDsSecur_1; "onecore\\ds\\security\\eas\\policyengin"...
0x180019fda  mov     r8d, ebx
0x180019fdd  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180019fe4  mov     ecx, 1; unsigned int
0x180019fe9  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180019fee  mov     rcx, r14; void *
0x180019ff1  call    ?_UnlockStore@@YAXPEAX@Z; _UnlockStore(void *)
0x180019ff6  mov     rdx, [rbp+arg_18]; struct _tagEASPolicy *
0x180019ffa  mov     ecx, edi; unsigned int
0x180019ffc  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x18001a001  mov     eax, ebx
0x18001a003  mov     rbx, [rsp+40h+arg_0]
0x18001a008  add     rsp, 40h
0x18001a00c  pop     r15
0x18001a00e  pop     r14
0x18001a010  pop     rdi
0x18001a011  pop     rsi
0x18001a012  pop     rbp
0x18001a013  retn
```
