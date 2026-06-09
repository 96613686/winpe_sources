# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18003a3fc`
- end: `0x18003a9a3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1447`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18003a0dc`
- `0x18003a3fc`

## callees

- `0x180002da0`
- `0x18000ac9c`
- `0x18000d554`
- `0x180038990`
- `0x180038f5c`
- `0x180038f74`
- `0x1800393f4`
- `0x180039620`
- `0x180039728`
- `0x1800397ac`
- `0x180039bfc`
- `0x180039fc8`
- `0x18003a3fc`
- `0x18003ab50`
- `0x18003ac20`
- `0x18005b890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003a7d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003a7d0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a652`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a652`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a478`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a48b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a55f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a58e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a478`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a48b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a55f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003a58e`

## string_xrefs

- `0x18003a481`: `ForceRemove`
- `0x18003a555`: `NoRemove`
- `0x18003a46e`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  unsigned int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // ecx
  int HasSubKeys; // r14d
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  HKEY v30[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v31[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_78;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_78;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
        if ( !v5 )
          break;
        hKey = 0;
        v28 = 0;
        v29 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_77:
          v10 = -2147352567;
          goto LABEL_78;
        }
        if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
          hKey = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_80;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_78;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_77;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u)
          || (v16 = ATL::CRegKey::Create((ATL::CRegKey *)v30, a3, v7, 0, 0, 0x2001Fu, 0, 0)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, (struct ATL::CRegKey *)v30, 0, v7);
            if ( v10 < 0 )
              goto LABEL_78;
          }
          goto LABEL_40;
        }
LABEL_81:
        v23 = v16;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v23);
        goto LABEL_78;
      }
      if ( a5 )
        v18 = 2;
      else
        v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
      v19 = 1;
      if ( !v18 )
        v19 = a5;
      v20 = _o_wcsncpy_s(v31, 260, v7, -1);
      ATL::AtlCrtErrorCheck(v20);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_78;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v21 = 0;
      if ( v10 < 0 )
        goto LABEL_78;
      if ( *v7 == 123 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v7[v22] );
        if ( v22 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
          if ( v10 < 0 && !v19 )
            goto LABEL_78;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
        }
      }
      v5 = a4;
      if ( v18 != 2 )
      {
        if ( v18 )
        {
          if ( !a5 )
          {
            v23 = v18;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
        {
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, v31) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v31);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
          v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
          if ( v16 )
            goto LABEL_81;
          if ( v14 && !HasSubKeys )
          {
            v28 = 0;
            v29 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v31);
            hKey = 0;
            if ( v15 )
              goto LABEL_79;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_78;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_78;
    if ( *v7 != 61 )
      goto LABEL_77;
    if ( v5 )
    {
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, (struct ATL::CRegKey *)&hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v28 = 0;
    v29 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_79:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003a3fc  push    rbp
0x18003a3fe  push    rbx
0x18003a3ff  push    rsi
0x18003a400  push    rdi
0x18003a401  push    r12
0x18003a403  push    r13
0x18003a405  push    r14
0x18003a407  push    r15
0x18003a409  lea     rbp, [rsp-21A8h]
0x18003a411  mov     eax, 22A8h
0x18003a416  call    _alloca_probe
0x18003a41b  sub     rsp, rax
0x18003a41e  mov     rax, cs:__security_cookie
0x18003a425  xor     rax, rsp
0x18003a428  mov     [rbp+21E0h+var_50], rax
0x18003a42f  mov     r15d, r9d
0x18003a432  mov     [rsp+22E0h+var_22A0], r9d
0x18003a437  mov     r13, r8
0x18003a43a  mov     rdi, rdx
0x18003a43d  mov     rsi, rcx
0x18003a440  xor     r14d, r14d
0x18003a443  mov     [rsp+22E0h+var_2280], r14
0x18003a448  mov     [rsp+22E0h+var_2278], r14
0x18003a44d  mov     [rsp+22E0h+var_2270], r14
0x18003a452  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a457  test    eax, eax
0x18003a459  mov     ebx, eax
0x18003a45b  js      loc_18003A957
0x18003a461  xor     r12d, r12d
0x18003a464  cmp     word ptr [rdi], 7Dh ; '}'
0x18003a468  jz      loc_18003A957
0x18003a46e  lea     rdx, aDelete; "Delete"
0x18003a475  mov     rcx, rdi; lpString1
0x18003a478  call    cs:__imp_lstrcmpiW
0x18003a47e  mov     r14d, eax
0x18003a481  lea     rdx, aForceremove; "ForceRemove"
0x18003a488  mov     rcx, rdi; lpString1
0x18003a48b  call    cs:__imp_lstrcmpiW
0x18003a491  test    eax, eax
0x18003a493  jz      short loc_18003A49E
0x18003a495  test    r14d, r14d
0x18003a498  jnz     loc_18003A54F
0x18003a49e  mov     rdx, rdi; unsigned __int16 *
0x18003a4a1  mov     rcx, rsi; this
0x18003a4a4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a4a9  mov     ebx, eax
0x18003a4ab  test    eax, eax
0x18003a4ad  js      loc_18003A957
0x18003a4b3  test    r15d, r15d
0x18003a4b6  jz      loc_18003A54F
0x18003a4bc  mov     [rsp+22E0h+hKey], r12
0x18003a4c1  mov     [rsp+22E0h+var_2290], r12
0x18003a4c6  mov     [rsp+22E0h+var_2288], r12
0x18003a4cb  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003a4d0  mov     rcx, rdi; lpsz
0x18003a4d3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18003a4d8  test    rax, rax
0x18003a4db  jnz     loc_18003A948
0x18003a4e1  mov     rdx, rdi; unsigned __int16 *
0x18003a4e4  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18003a4e9  test    eax, eax
0x18003a4eb  jz      short loc_18003A504
0x18003a4ed  mov     [rsp+22E0h+hKey], r13
0x18003a4f2  mov     rdx, rdi; unsigned __int16 *
0x18003a4f5  lea     rcx, [rsp+22E0h+hKey]; this
0x18003a4fa  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18003a4ff  mov     [rsp+22E0h+hKey], r12
0x18003a504  test    r14d, r14d
0x18003a507  jnz     short loc_18003A545
0x18003a509  mov     rdx, rdi; unsigned __int16 *
0x18003a50c  mov     rcx, rsi; this
0x18003a50f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a514  mov     ebx, eax
0x18003a516  xor     r14d, r14d
0x18003a519  test    eax, eax
0x18003a51b  js      loc_18003A98F
0x18003a521  mov     rdx, rdi; unsigned __int16 *
0x18003a524  mov     rcx, rsi; this
0x18003a527  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003a52c  mov     ebx, eax
0x18003a52e  test    eax, eax
0x18003a530  lea     rcx, [rsp+22E0h+hKey]; this
0x18003a535  js      loc_18003A994
0x18003a53b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003a540  jmp     loc_18003A736
0x18003a545  lea     rcx, [rsp+22E0h+hKey]; this
0x18003a54a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003a54f  mov     r12d, 1
0x18003a555  lea     rdx, aNoremove; "NoRemove"
0x18003a55c  mov     rcx, rdi; lpString1
0x18003a55f  call    cs:__imp_lstrcmpiW
0x18003a565  xor     r14d, r14d
0x18003a568  test    eax, eax
0x18003a56a  jnz     short loc_18003A584
0x18003a56c  mov     r12d, r14d
0x18003a56f  mov     rdx, rdi; unsigned __int16 *
0x18003a572  mov     rcx, rsi; this
0x18003a575  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a57a  mov     ebx, eax
0x18003a57c  test    eax, eax
0x18003a57e  js      loc_18003A957
0x18003a584  lea     rdx, aVal; "Val"
0x18003a58b  mov     rcx, rdi; lpString1
0x18003a58e  call    cs:__imp_lstrcmpiW
0x18003a594  test    eax, eax
0x18003a596  jnz     loc_18003A67D
0x18003a59c  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18003a5a3  mov     rcx, rsi; this
0x18003a5a6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a5ab  mov     ebx, eax
0x18003a5ad  test    eax, eax
0x18003a5af  js      loc_18003A957
0x18003a5b5  mov     rdx, rdi; unsigned __int16 *
0x18003a5b8  mov     rcx, rsi; this
0x18003a5bb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a5c0  mov     ebx, eax
0x18003a5c2  test    eax, eax
0x18003a5c4  js      loc_18003A957
0x18003a5ca  cmp     word ptr [rdi], 3Dh ; '='
0x18003a5ce  jnz     loc_18003A952
0x18003a5d4  test    r15d, r15d
0x18003a5d7  jz      short loc_18003A60B
0x18003a5d9  mov     [rsp+22E0h+var_2290], r14
0x18003a5de  mov     [rsp+22E0h+var_2288], r14
0x18003a5e3  mov     [rsp+22E0h+hKey], r13
0x18003a5e8  mov     r9, rdi; unsigned __int16 *
0x18003a5eb  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18003a5f2  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18003a5f7  mov     rcx, rsi; this
0x18003a5fa  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18003a5ff  mov     ebx, eax
0x18003a601  mov     [rsp+22E0h+hKey], r14
0x18003a606  jmp     loc_18003A52E
0x18003a60b  cmp     [rbp+21E0h+arg_20], r14d
0x18003a612  jnz     short loc_18003A66D
0x18003a614  test    r12d, r12d
0x18003a617  jz      short loc_18003A66D
0x18003a619  mov     [rsp+22E0h+hKey], r14
0x18003a61e  mov     [rsp+22E0h+var_2290], r14
0x18003a623  mov     [rsp+22E0h+var_2288], r14
0x18003a628  mov     r9d, 20006h; unsigned int
0x18003a62e  xor     r8d, r8d; lpSubKey
0x18003a631  mov     rdx, r13; hKey
0x18003a634  lea     rcx, [rsp+22E0h+hKey]; this
0x18003a639  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003a63e  test    eax, eax
0x18003a640  jnz     loc_18003A986
0x18003a646  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18003a64d  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18003a652  call    cs:__imp_RegDeleteValueW
0x18003a658  test    eax, 0FFFFFFFDh
0x18003a65d  jnz     loc_18003A986
0x18003a663  lea     rcx, [rsp+22E0h+hKey]; this
0x18003a668  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003a66d  mov     rdx, rdi; unsigned __int16 *
0x18003a670  mov     rcx, rsi; this
0x18003a673  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003a678  jmp     loc_18003A457
0x18003a67d  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003a682  mov     rcx, rdi; lpsz
0x18003a685  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18003a68a  test    rax, rax
0x18003a68d  jnz     loc_18003A952
0x18003a693  test    r15d, r15d
0x18003a696  jz      loc_18003A785
0x18003a69c  mov     ebx, 2001Fh
0x18003a6a1  mov     r9d, ebx; unsigned int
0x18003a6a4  mov     r8, rdi; lpSubKey
0x18003a6a7  mov     rdx, r13; hKey
0x18003a6aa  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003a6af  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003a6b4  test    eax, eax
0x18003a6b6  jz      short loc_18003A6FE
0x18003a6b8  lea     r9d, [rbx-6]; unsigned int
0x18003a6bc  mov     r8, rdi; lpSubKey
0x18003a6bf  mov     rdx, r13; hKey
0x18003a6c2  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003a6c7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003a6cc  test    eax, eax
0x18003a6ce  jz      short loc_18003A6FE
0x18003a6d0  mov     [rsp+22E0h+var_22A8], r14; unsigned int *
0x18003a6d5  mov     [rsp+22E0h+var_22B0], r14; LPSECURITY_ATTRIBUTES
0x18003a6da  mov     [rsp+22E0h+var_22B8], ebx; REGSAM
0x18003a6de  mov     [rsp+22E0h+var_22C0], r14d; DWORD
0x18003a6e3  xor     r9d, r9d; unsigned __int16 *
0x18003a6e6  mov     r8, rdi; lpSubKey
0x18003a6e9  mov     rdx, r13; hKey
0x18003a6ec  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003a6f1  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18003a6f6  test    eax, eax
0x18003a6f8  jnz     loc_18003A99B
0x18003a6fe  mov     rdx, rdi; unsigned __int16 *
0x18003a701  mov     rcx, rsi; this
0x18003a704  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a709  mov     ebx, eax
0x18003a70b  test    eax, eax
0x18003a70d  js      loc_18003A957
0x18003a713  cmp     word ptr [rdi], 3Dh ; '='
0x18003a717  jnz     short loc_18003A736
0x18003a719  mov     r9, rdi; unsigned __int16 *
0x18003a71c  xor     r8d, r8d; unsigned __int16 *
0x18003a71f  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18003a724  mov     rcx, rsi; this
0x18003a727  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18003a72c  mov     ebx, eax
0x18003a72e  test    eax, eax
0x18003a730  js      loc_18003A957
0x18003a736  cmp     word ptr [rdi], 7Bh ; '{'
0x18003a73a  jnz     loc_18003A461
0x18003a740  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a744  inc     rax
0x18003a747  cmp     [rdi+rax*2], r14w
0x18003a74c  jnz     short loc_18003A744
0x18003a74e  cmp     rax, 1
0x18003a752  jnz     loc_18003A461
0x18003a758  mov     [rsp+22E0h+var_22C0], r14d; int
0x18003a75d  mov     r9d, r15d; int
0x18003a760  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18003a765  mov     rdx, rdi; unsigned __int16 *
0x18003a768  mov     rcx, rsi; this
0x18003a76b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003a770  mov     ebx, eax
0x18003a772  test    eax, eax
0x18003a774  js      loc_18003A957
0x18003a77a  mov     rdx, rdi
0x18003a77d  mov     rcx, rsi
0x18003a780  jmp     loc_18003A452
0x18003a785  cmp     [rbp+21E0h+arg_20], r14d
0x18003a78c  jnz     short loc_18003A7A9
0x18003a78e  mov     r9d, 20019h; unsigned int
0x18003a794  mov     r8, rdi; lpSubKey
0x18003a797  mov     rdx, r13; hKey
0x18003a79a  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003a79f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003a7a4  mov     r14d, eax
0x18003a7a7  jmp     short loc_18003A7AF
0x18003a7a9  mov     r14d, 2
0x18003a7af  mov     r15d, 1
0x18003a7b5  test    r14d, r14d
0x18003a7b8  cmovz   r15d, [rbp+21E0h+arg_20]
0x18003a7c0  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003a7c4  mov     r8, rdi
0x18003a7c7  mov     edx, 104h
0x18003a7cc  lea     rcx, [rbp+21E0h+var_2260]
0x18003a7d0  call    cs:__imp__o_wcsncpy_s
0x18003a7d6  mov     ecx, eax; int
0x18003a7d8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003a7dd  mov     rdx, rdi; unsigned __int16 *
0x18003a7e0  mov     rcx, rsi; this
0x18003a7e3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a7e8  mov     ebx, eax
0x18003a7ea  test    eax, eax
0x18003a7ec  js      loc_18003A957
0x18003a7f2  mov     rdx, rdi; unsigned __int16 *
0x18003a7f5  mov     rcx, rsi; this
0x18003a7f8  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003a7fd  mov     ebx, eax
0x18003a7ff  xor     ecx, ecx
0x18003a801  test    eax, eax
0x18003a803  js      loc_18003A957
0x18003a809  cmp     word ptr [rdi], 7Bh ; '{'
0x18003a80d  jnz     short loc_18003A85E
0x18003a80f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a813  inc     rax
0x18003a816  cmp     [rdi+rax*2], cx
0x18003a81a  jnz     short loc_18003A813
0x18003a81c  cmp     rax, 1
0x18003a820  jnz     short loc_18003A85E
0x18003a822  mov     [rsp+22E0h+var_22C0], r15d; int
0x18003a827  xor     r9d, r9d; int
0x18003a82a  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18003a82f  mov     rdx, rdi; unsigned __int16 *
0x18003a832  mov     rcx, rsi; this
0x18003a835  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003a83a  mov     ebx, eax
0x18003a83c  test    eax, eax
0x18003a83e  jns     short loc_18003A849
0x18003a840  test    r15d, r15d
0x18003a843  jz      loc_18003A957
0x18003a849  mov     rdx, rdi; unsigned __int16 *
0x18003a84c  mov     rcx, rsi; this
0x18003a84f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003a854  mov     ebx, eax
0x18003a856  test    eax, eax
0x18003a858  js      loc_18003A957
0x18003a85e  cmp     r14d, 2
0x18003a862  mov     r15d, [rsp+22E0h+var_22A0]
0x18003a867  jz      loc_18003A461
0x18003a86d  test    r14d, r14d
0x18003a870  jz      short loc_18003A891
0x18003a872  xor     r12d, r12d
0x18003a875  cmp     [rbp+21E0h+arg_20], r12d
0x18003a87c  jnz     loc_18003A464
0x18003a882  mov     ecx, r14d; unsigned int
0x18003a885  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18003a88a  mov     ebx, eax
0x18003a88c  jmp     loc_18003A957
0x18003a891  xor     r14d, r14d
0x18003a894  cmp     [rbp+21E0h+arg_20], r14d
0x18003a89b  jz      short loc_18003A8DB
  ... truncated ...
```
