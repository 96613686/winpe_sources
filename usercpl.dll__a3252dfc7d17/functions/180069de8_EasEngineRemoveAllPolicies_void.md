# EasEngineRemoveAllPolicies(void)

- ea: `0x180069de8`
- end: `0x18006a0a2`
- name: `?EasEngineRemoveAllPolicies@@YAJXZ`
- size: `698`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011d20`

## callees

- `0x180069de8`
- `0x18006a454`
- `0x18006a608`
- `0x18006b46c`
- `0x18006b660`
- `0x18006b920`
- `0x18006bc1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a084`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a084`
- `ADVAPI32!RegDeleteTreeW` at `0x180069f2f`
- `ADVAPI32!RegDeleteTreeW` at `0x180069fb3`
- `ADVAPI32!RegDeleteTreeW` at `0x180069f2f`
- `ADVAPI32!RegDeleteTreeW` at `0x180069fb3`

## string_xrefs

- `0x180069e7d`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x18006a061`: `onecore\ds\security\eas\policyengine\extnlib\readpolicies.cpp`
- `0x180069ed0`: `_ReadPolicies`
- `0x180069e37`: `_CheckWriteAccess`
- `0x180069f03`: `_RemoveBuiltInPolicies`
- `0x180069f90`: `_DeleteControlledUsersState`
- `0x180069f6b`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x18006a001`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x180069f50`: `RegDeleteKey`
- `0x180069fe6`: `RegDeleteKey`

## pseudocode

```c
__int64 __fastcall EasEngineRemoveAllPolicies(void *a1)
{
  HKEY v1; // rdi
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  __int64 v5; // [rsp+20h] [rbp-38h]
  __int64 v6; // [rsp+20h] [rbp-38h]
  unsigned int v7; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  struct _tagEASPolicy *v9; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  v7 = 0;
  v9 = 0;
  hKey = 0;
  if ( g_bInitialized && g_bProvInitialized )
  {
    v2 = _CheckWriteAccess(a1);
    if ( v2 )
    {
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v2,
        L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
        461,
        L"_CheckWriteAccess",
        &Class);
    }
    else
    {
      v2 = _LockStore(0, (void **)&hKey);
      if ( v2 )
      {
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          v2,
          L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
          466,
          L"_LockStore",
          &Class);
        v1 = hKey;
      }
      else
      {
        v1 = hKey;
        v2 = _ReadPolicies(hKey, &v7, &v9);
        if ( v2 )
        {
          DbgPrintfW(
            1u,
            L"(0x%08x) %ws:%u : %ws:%ws\n",
            v2,
            L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
            469,
            L"_ReadPolicies",
            &Class);
        }
        else
        {
          v2 = _RemoveBuiltInPolicies(v1);
          if ( v2 )
          {
            DbgPrintfW(
              1u,
              L"(0x%08x) %ws:%u : %ws:%ws\n",
              v2,
              L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
              472,
              L"_RemoveBuiltInPolicies",
              &Class);
          }
          else if ( v1 && ((v3 = RegDeleteTreeW(v1, L"ControlledUsers"), v2 = v3, (v3 & 0xFFFFFFFC) != 0) || v3 == 1) )
          {
            if ( v3 > 0 )
              v2 = (unsigned __int16)v3 | 0xC0070000;
            DbgPrintfW(
              1u,
              L"(0x%08x) %ws:%u : %ws:%ws\n",
              v2,
              L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
              812,
              L"RegDeleteKey",
              &Class);
            LODWORD(v5) = 488;
            DbgPrintfW(
              1u,
              L"(0x%08x) %ws:%u : %ws:%ws\n",
              v2,
              L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
              v5,
              L"_DeleteControlledUsersState",
              &Class);
          }
          else
          {
            v2 = RegDeleteTreeW(v1, L"MDM");
            if ( v2 - 4 <= 0x48B || v2 == 1 || v2 >= 0x491 )
            {
              if ( (int)v2 > 0 )
                v2 = (unsigned __int16)v2 | 0xC0070000;
              DbgPrintfW(
                1u,
                L"(0x%08x) %ws:%u : %ws:%ws\n",
                v2,
                L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
                1161,
                L"RegDeleteKey",
                &Class);
              LODWORD(v6) = 493;
              DbgPrintfW(
                1u,
                L"(0x%08x) %ws:%u : %ws:%ws\n",
                v2,
                L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
                v6,
                "_SetMDMEnforced",
                &Class);
            }
            else
            {
              v2 = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v2 = -1073283051;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      3221684245LL,
      L"onecore\\ds\\security\\eas\\policyengine\\extnlib\\readpolicies.cpp",
      457,
      L"Not initialized",
      &Class);
  }
  if ( v1 )
    RegCloseKey(v1);
  _FreePolicies(v7, v9);
  return v2;
}

```

## disassembly

```asm
0x180069de8  push    rbx
0x180069dea  push    rsi
0x180069deb  push    rdi
0x180069dec  sub     rsp, 40h
0x180069df0  xor     edi, edi
0x180069df2  mov     [rsp+58h+arg_0], 0
0x180069dfa  cmp     cs:?g_bInitialized@@3HA, edi; int g_bInitialized
0x180069e00  mov     [rsp+58h+arg_10], 0
0x180069e09  mov     [rsp+58h+hKey], rdi
0x180069e0e  jz      loc_18006A03C
0x180069e14  cmp     cs:?g_bProvInitialized@@3HA, edi; int g_bProvInitialized
0x180069e1a  jz      loc_18006A03C
0x180069e20  call    ?_CheckWriteAccess@@YAJPEAX@Z; _CheckWriteAccess(void *)
0x180069e25  mov     ebx, eax
0x180069e27  test    eax, eax
0x180069e29  jz      short loc_180069E50
0x180069e2b  lea     rsi, Class
0x180069e32  mov     [rsp+58h+var_28], rsi
0x180069e37  lea     rax, aCheckwriteacce; "_CheckWriteAccess"
0x180069e3e  mov     [rsp+58h+var_30], rax
0x180069e43  mov     dword ptr [rsp+58h+var_38], 1CDh
0x180069e4b  jmp     loc_18006A061
0x180069e50  lea     rdx, [rsp+58h+hKey]; void **
0x180069e55  xor     ecx, ecx; int
0x180069e57  call    ?_LockStore@@YAJHPEAPEAX@Z; _LockStore(int,void * *)
0x180069e5c  mov     ebx, eax
0x180069e5e  test    eax, eax
0x180069e60  jz      short loc_180069EA7
0x180069e62  lea     rax, aLockstore; "_LockStore"
0x180069e69  mov     r8d, ebx
0x180069e6c  lea     rsi, Class
0x180069e73  mov     ecx, 1; unsigned int
0x180069e78  mov     [rsp+58h+var_28], rsi
0x180069e7d  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x180069e84  mov     [rsp+58h+var_30], rax
0x180069e89  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180069e90  mov     dword ptr [rsp+58h+var_38], 1D2h
0x180069e98  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180069e9d  mov     rdi, [rsp+58h+hKey]
0x180069ea2  jmp     loc_18006A07C
0x180069ea7  mov     rdi, [rsp+58h+hKey]
0x180069eac  lea     r8, [rsp+58h+arg_10]; struct _tagEASPolicy **
0x180069eb1  mov     rcx, rdi; hKey
0x180069eb4  lea     rdx, [rsp+58h+arg_0]; unsigned int *
0x180069eb9  call    ?_ReadPolicies@@YAJPEAXPEAKPEAPEAU_tagEASPolicy@@@Z; _ReadPolicies(void *,ulong *,_tagEASPolicy * *)
0x180069ebe  mov     ebx, eax
0x180069ec0  test    eax, eax
0x180069ec2  jz      short loc_180069EE9
0x180069ec4  lea     rsi, Class
0x180069ecb  mov     [rsp+58h+var_28], rsi
0x180069ed0  lea     rax, aReadpolicies; "_ReadPolicies"
0x180069ed7  mov     [rsp+58h+var_30], rax
0x180069edc  mov     dword ptr [rsp+58h+var_38], 1D5h
0x180069ee4  jmp     loc_18006A061
0x180069ee9  mov     rcx, rdi; hKey
0x180069eec  call    ?_RemoveBuiltInPolicies@@YAJPEAX@Z; _RemoveBuiltInPolicies(void *)
0x180069ef1  mov     ebx, eax
0x180069ef3  test    eax, eax
0x180069ef5  jz      short loc_180069F1C
0x180069ef7  lea     rsi, Class
0x180069efe  mov     [rsp+58h+var_28], rsi
0x180069f03  lea     rax, aRemovebuiltinp; "_RemoveBuiltInPolicies"
0x180069f0a  mov     [rsp+58h+var_30], rax
0x180069f0f  mov     dword ptr [rsp+58h+var_38], 1D8h
0x180069f17  jmp     loc_18006A061
0x180069f1c  test    rdi, rdi
0x180069f1f  jz      loc_180069FA9
0x180069f25  lea     rdx, aControlleduser; "ControlledUsers"
0x180069f2c  mov     rcx, rdi; hKey
0x180069f2f  call    cs:__imp_RegDeleteTreeW
0x180069f35  mov     ebx, eax
0x180069f37  test    eax, 0FFFFFFFCh
0x180069f3c  jnz     short loc_180069F43
0x180069f3e  cmp     eax, 1
0x180069f41  jnz     short loc_180069FA9
0x180069f43  test    eax, eax
0x180069f45  jle     short loc_180069F50
0x180069f47  movzx   ebx, ax
0x180069f4a  or      ebx, 0C0070000h
0x180069f50  lea     rax, aRegdeletekey; "RegDeleteKey"
0x180069f57  mov     r8d, ebx
0x180069f5a  lea     rsi, Class
0x180069f61  mov     ecx, 1; unsigned int
0x180069f66  mov     [rsp+58h+var_28], rsi
0x180069f6b  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x180069f72  mov     [rsp+58h+var_30], rax
0x180069f77  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x180069f7e  mov     dword ptr [rsp+58h+var_38], 32Ch
0x180069f86  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x180069f8b  mov     [rsp+58h+var_28], rsi
0x180069f90  lea     rax, aDeletecontroll; "_DeleteControlledUsersState"
0x180069f97  mov     [rsp+58h+var_30], rax
0x180069f9c  mov     dword ptr [rsp+58h+var_38], 1E8h
0x180069fa4  jmp     loc_18006A061
0x180069fa9  lea     rdx, aMdm; "MDM"
0x180069fb0  mov     rcx, rdi; hKey
0x180069fb3  call    cs:__imp_RegDeleteTreeW
0x180069fb9  mov     ebx, eax
0x180069fbb  add     eax, 0FFFFFFFCh
0x180069fbe  cmp     eax, 48Bh
0x180069fc3  jbe     short loc_180069FD9
0x180069fc5  cmp     ebx, 1
0x180069fc8  jz      short loc_180069FD9
0x180069fca  cmp     ebx, 491h
0x180069fd0  jnb     short loc_180069FD9
0x180069fd2  xor     ebx, ebx
0x180069fd4  jmp     loc_18006A07C
0x180069fd9  test    ebx, ebx
0x180069fdb  jle     short loc_180069FE6
0x180069fdd  movzx   ebx, bx
0x180069fe0  or      ebx, 0C0070000h
0x180069fe6  lea     rax, aRegdeletekey; "RegDeleteKey"
0x180069fed  mov     r8d, ebx
0x180069ff0  lea     rsi, Class
0x180069ff7  mov     ecx, 1; unsigned int
0x180069ffc  mov     [rsp+58h+var_28], rsi
0x18006a001  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x18006a008  mov     [rsp+58h+var_30], rax
0x18006a00d  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006a014  mov     dword ptr [rsp+58h+var_38], 489h
0x18006a01c  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006a021  mov     [rsp+58h+var_28], rsi
0x18006a026  lea     rax, aSetmdmenforced; "_SetMDMEnforced"
0x18006a02d  mov     [rsp+58h+var_30], rax
0x18006a032  mov     dword ptr [rsp+58h+var_38], 1EDh
0x18006a03a  jmp     short loc_18006A061
0x18006a03c  lea     rsi, Class
0x18006a043  mov     ebx, 0C0070015h
0x18006a048  mov     [rsp+58h+var_28], rsi
0x18006a04d  lea     rax, aNotInitialized_0; "Not initialized"
0x18006a054  mov     [rsp+58h+var_30], rax
0x18006a059  mov     dword ptr [rsp+58h+var_38], 1C9h
0x18006a061  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\eas\\policyengin"...
0x18006a068  mov     r8d, ebx
0x18006a06b  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006a072  mov     ecx, 1; unsigned int
0x18006a077  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006a07c  test    rdi, rdi
0x18006a07f  jz      short loc_18006A08A
0x18006a081  mov     rcx, rdi; hKey
0x18006a084  call    cs:__imp_RegCloseKey
0x18006a08a  mov     rdx, [rsp+58h+arg_10]; struct _tagEASPolicy *
0x18006a08f  mov     ecx, [rsp+58h+arg_0]; unsigned int
0x18006a093  call    ?_FreePolicies@@YAXKPEAU_tagEASPolicy@@@Z; _FreePolicies(ulong,_tagEASPolicy *)
0x18006a098  mov     eax, ebx
0x18006a09a  add     rsp, 40h
0x18006a09e  pop     rdi
0x18006a09f  pop     rsi
0x18006a0a0  pop     rbx
0x18006a0a1  retn
```
