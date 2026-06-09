# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18003f67c`
- end: `0x18003fbfd`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1409`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003f35c`
- `0x18003f67c`

## callees

- `0x1800358c0`
- `0x18003e370`
- `0x18003e8d4`
- `0x18003e944`
- `0x18003e984`
- `0x18003eae0`
- `0x18003eb0c`
- `0x18003eb94`
- `0x18003ed6c`
- `0x18003ee34`
- `0x18003efac`
- `0x18003f248`
- `0x18003f67c`
- `0x18003fcdc`
- `0x18003fdac`
- `0x18006ad80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003fa3d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003fa3d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003f8cd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003f8cd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003f6f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003f703`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003f7d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003f803`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003f6f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003f703`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003f7d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003f803`

## string_xrefs

- `0x18003f6f9`: `ForceRemove`
- `0x18003f7ca`: `NoRemove`
- `0x18003f6e6`: `Delete`

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
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  __int64 v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  HKEY v35[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v35, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_80;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_80;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( !v5 )
          break;
        hKey = 0;
        v33 = 0;
        v34 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
          v10 = -2147352567;
          goto LABEL_80;
        }
        if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
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
          goto LABEL_82;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_82;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_80;
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
          goto LABEL_80;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_79;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v35, a3, v7, v16, v27, v28, v29, v30)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_80;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v35, 0, v7);
            if ( v10 < 0 )
              goto LABEL_80;
          }
          goto LABEL_40;
        }
LABEL_83:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_80;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v36, 260, v7, -1, v27);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_80;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_80;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_80;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_80;
        }
      }
      if ( v19 != 2 )
      {
        if ( v19 )
        {
          if ( !a5 )
          {
            v24 = v19;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v35[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v35, v36);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v35[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v35);
          if ( v17 )
            goto LABEL_83;
          if ( v14 && !HasSubKeys )
          {
            v33 = 0;
            v34 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v36);
            hKey = 0;
            if ( v15 )
              goto LABEL_81;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
      }
      v5 = a4;
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_80;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_80;
    if ( *v7 != 61 )
      goto LABEL_79;
    if ( v5 )
    {
      v33 = 0;
      v34 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v33 = 0;
    v34 = 0;
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
LABEL_81:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_82:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)v35);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003f67c  push    rbp
0x18003f67e  push    rbx
0x18003f67f  push    rsi
0x18003f680  push    rdi
0x18003f681  push    r12
0x18003f683  push    r13
0x18003f685  push    r14
0x18003f687  push    r15
0x18003f689  lea     rbp, [rsp-21A8h]
0x18003f691  mov     eax, 22A8h
0x18003f696  call    _alloca_probe
0x18003f69b  sub     rsp, rax
0x18003f69e  mov     rax, cs:__security_cookie
0x18003f6a5  xor     rax, rsp
0x18003f6a8  mov     [rbp+21E0h+var_50], rax
0x18003f6af  mov     r15d, r9d
0x18003f6b2  mov     [rsp+22E0h+var_22A0], r9d
0x18003f6b7  mov     r13, r8
0x18003f6ba  mov     rdi, rdx
0x18003f6bd  mov     rsi, rcx
0x18003f6c0  xor     r12d, r12d
0x18003f6c3  mov     [rsp+22E0h+var_2280], r12
0x18003f6c8  mov     [rsp+22E0h+var_2278], r12
0x18003f6cd  mov     [rsp+22E0h+var_2270], r12
0x18003f6d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f6d7  mov     ebx, eax
0x18003f6d9  test    eax, eax
0x18003f6db  js      loc_18003FBB1
0x18003f6e1  jmp     loc_18003FB38
0x18003f6e6  lea     rdx, aDelete; "Delete"
0x18003f6ed  mov     rcx, rdi; lpString1
0x18003f6f0  call    cs:__imp_lstrcmpiW
0x18003f6f6  mov     r14d, eax
0x18003f6f9  lea     rdx, aForceremove; "ForceRemove"
0x18003f700  mov     rcx, rdi; lpString1
0x18003f703  call    cs:__imp_lstrcmpiW
0x18003f709  test    eax, eax
0x18003f70b  jz      short loc_18003F716
0x18003f70d  test    r14d, r14d
0x18003f710  jnz     loc_18003F7C4
0x18003f716  mov     rdx, rdi; unsigned __int16 *
0x18003f719  mov     rcx, rsi; this
0x18003f71c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f721  mov     ebx, eax
0x18003f723  test    eax, eax
0x18003f725  js      loc_18003FBB1
0x18003f72b  test    r15d, r15d
0x18003f72e  jz      loc_18003F7C4
0x18003f734  mov     [rsp+22E0h+hKey], r12
0x18003f739  mov     [rsp+22E0h+var_2290], r12
0x18003f73e  mov     [rsp+22E0h+var_2288], r12
0x18003f743  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003f748  mov     rcx, rdi; lpsz
0x18003f74b  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18003f750  test    rax, rax
0x18003f753  jnz     loc_18003FBA2
0x18003f759  mov     rdx, rdi; unsigned __int16 *
0x18003f75c  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18003f761  test    eax, eax
0x18003f763  jz      short loc_18003F77C
0x18003f765  mov     [rsp+22E0h+hKey], r13
0x18003f76a  mov     rdx, rdi; unsigned __int16 *
0x18003f76d  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f772  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18003f777  mov     [rsp+22E0h+hKey], r12
0x18003f77c  test    r14d, r14d
0x18003f77f  jnz     short loc_18003F7BA
0x18003f781  mov     rdx, rdi; unsigned __int16 *
0x18003f784  mov     rcx, rsi; this
0x18003f787  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f78c  mov     ebx, eax
0x18003f78e  test    eax, eax
0x18003f790  js      loc_18003FBE9
0x18003f796  mov     rdx, rdi; unsigned __int16 *
0x18003f799  mov     rcx, rsi; this
0x18003f79c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003f7a1  mov     ebx, eax
0x18003f7a3  test    eax, eax
0x18003f7a5  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f7aa  js      loc_18003FBEE
0x18003f7b0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003f7b5  jmp     loc_18003F9A3
0x18003f7ba  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f7bf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003f7c4  mov     r12d, 1
0x18003f7ca  lea     rdx, aNoremove; "NoRemove"
0x18003f7d1  mov     rcx, rdi; lpString1
0x18003f7d4  call    cs:__imp_lstrcmpiW
0x18003f7da  xor     r14d, r14d
0x18003f7dd  test    eax, eax
0x18003f7df  jnz     short loc_18003F7F9
0x18003f7e1  mov     r12d, r14d
0x18003f7e4  mov     rdx, rdi; unsigned __int16 *
0x18003f7e7  mov     rcx, rsi; this
0x18003f7ea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f7ef  mov     ebx, eax
0x18003f7f1  test    eax, eax
0x18003f7f3  js      loc_18003FBB1
0x18003f7f9  lea     rdx, aVal; "Val"
0x18003f800  mov     rcx, rdi; lpString1
0x18003f803  call    cs:__imp_lstrcmpiW
0x18003f809  test    eax, eax
0x18003f80b  jnz     loc_18003F8FD
0x18003f811  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18003f818  mov     rcx, rsi; this
0x18003f81b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f820  mov     ebx, eax
0x18003f822  test    eax, eax
0x18003f824  js      loc_18003FBB1
0x18003f82a  mov     rdx, rdi; unsigned __int16 *
0x18003f82d  mov     rcx, rsi; this
0x18003f830  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f835  mov     ebx, eax
0x18003f837  test    eax, eax
0x18003f839  js      loc_18003FBB1
0x18003f83f  cmp     word ptr [rdi], 3Dh ; '='
0x18003f843  jnz     loc_18003FBAC
0x18003f849  test    r15d, r15d
0x18003f84c  jz      short loc_18003F883
0x18003f84e  xor     r12d, r12d
0x18003f851  mov     [rsp+22E0h+var_2290], r12
0x18003f856  mov     [rsp+22E0h+var_2288], r12
0x18003f85b  mov     [rsp+22E0h+hKey], r13
0x18003f860  mov     r9, rdi; unsigned __int16 *
0x18003f863  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18003f86a  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18003f86f  mov     rcx, rsi; this
0x18003f872  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18003f877  mov     ebx, eax
0x18003f879  mov     [rsp+22E0h+hKey], r12
0x18003f87e  jmp     loc_18003F7A3
0x18003f883  cmp     [rbp+21E0h+arg_20], r14d
0x18003f88a  jnz     short loc_18003F8EA
0x18003f88c  test    r12d, r12d
0x18003f88f  jz      short loc_18003F8EA
0x18003f891  xor     r12d, r12d
0x18003f894  mov     [rsp+22E0h+hKey], r12
0x18003f899  mov     [rsp+22E0h+var_2290], r12
0x18003f89e  mov     [rsp+22E0h+var_2288], r12
0x18003f8a3  mov     r9d, 20006h; unsigned int
0x18003f8a9  xor     r8d, r8d; lpSubKey
0x18003f8ac  mov     rdx, r13; hKey
0x18003f8af  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f8b4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f8b9  test    eax, eax
0x18003f8bb  jnz     loc_18003FBE0
0x18003f8c1  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18003f8c8  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18003f8cd  call    cs:__imp_RegDeleteValueW
0x18003f8d3  test    eax, 0FFFFFFFDh
0x18003f8d8  jnz     loc_18003FBE0
0x18003f8de  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f8e3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003f8e8  jmp     short loc_18003F8ED
0x18003f8ea  xor     r12d, r12d
0x18003f8ed  mov     rdx, rdi; unsigned __int16 *
0x18003f8f0  mov     rcx, rsi; this
0x18003f8f3  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003f8f8  jmp     loc_18003F6D7
0x18003f8fd  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003f902  mov     rcx, rdi; lpsz
0x18003f905  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18003f90a  test    rax, rax
0x18003f90d  jnz     loc_18003FBAC
0x18003f913  test    r15d, r15d
0x18003f916  jz      loc_18003F9F2
0x18003f91c  mov     r9d, 2001Fh; unsigned int
0x18003f922  mov     r8, rdi; lpSubKey
0x18003f925  mov     rdx, r13; hKey
0x18003f928  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003f92d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f932  xor     r12d, r12d
0x18003f935  test    eax, eax
0x18003f937  jz      short loc_18003F96B
0x18003f939  mov     r9d, 20019h; unsigned int
0x18003f93f  mov     r8, rdi; lpSubKey
0x18003f942  mov     rdx, r13; hKey
0x18003f945  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003f94a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f94f  test    eax, eax
0x18003f951  jz      short loc_18003F96B
0x18003f953  mov     r8, rdi; lpSubKey
0x18003f956  mov     rdx, r13; hKey
0x18003f959  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003f95e  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18003f963  test    eax, eax
0x18003f965  jnz     loc_18003FBF5
0x18003f96b  mov     rdx, rdi; unsigned __int16 *
0x18003f96e  mov     rcx, rsi; this
0x18003f971  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f976  mov     ebx, eax
0x18003f978  test    eax, eax
0x18003f97a  js      loc_18003FBB1
0x18003f980  cmp     word ptr [rdi], 3Dh ; '='
0x18003f984  jnz     short loc_18003F9A3
0x18003f986  mov     r9, rdi; unsigned __int16 *
0x18003f989  xor     r8d, r8d; unsigned __int16 *
0x18003f98c  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18003f991  mov     rcx, rsi; this
0x18003f994  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18003f999  mov     ebx, eax
0x18003f99b  test    eax, eax
0x18003f99d  js      loc_18003FBB1
0x18003f9a3  cmp     word ptr [rdi], 7Bh ; '{'
0x18003f9a7  jnz     loc_18003FB38
0x18003f9ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f9b1  inc     rax
0x18003f9b4  cmp     [rdi+rax*2], r12w
0x18003f9b9  jnz     short loc_18003F9B1
0x18003f9bb  cmp     rax, 1
0x18003f9bf  jnz     loc_18003FB38
0x18003f9c5  mov     dword ptr [rsp+22E0h+var_22C0], r12d; int
0x18003f9ca  mov     r9d, r15d; int
0x18003f9cd  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18003f9d2  mov     rdx, rdi; unsigned __int16 *
0x18003f9d5  mov     rcx, rsi; this
0x18003f9d8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003f9dd  mov     ebx, eax
0x18003f9df  test    eax, eax
0x18003f9e1  js      loc_18003FBB1
0x18003f9e7  mov     rdx, rdi
0x18003f9ea  mov     rcx, rsi
0x18003f9ed  jmp     loc_18003F6D2
0x18003f9f2  cmp     [rbp+21E0h+arg_20], r14d
0x18003f9f9  jnz     short loc_18003FA16
0x18003f9fb  mov     r9d, 20019h; unsigned int
0x18003fa01  mov     r8, rdi; lpSubKey
0x18003fa04  mov     rdx, r13; hKey
0x18003fa07  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003fa0c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003fa11  mov     r14d, eax
0x18003fa14  jmp     short loc_18003FA1C
0x18003fa16  mov     r14d, 2
0x18003fa1c  mov     r15d, 1
0x18003fa22  test    r14d, r14d
0x18003fa25  cmovz   r15d, [rbp+21E0h+arg_20]
0x18003fa2d  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003fa31  mov     r8, rdi
0x18003fa34  mov     edx, 104h
0x18003fa39  lea     rcx, [rbp+21E0h+var_2260]
0x18003fa3d  call    cs:__imp__o_wcsncpy_s
0x18003fa43  mov     ecx, eax; int
0x18003fa45  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003fa4a  mov     rdx, rdi; unsigned __int16 *
0x18003fa4d  mov     rcx, rsi; this
0x18003fa50  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003fa55  mov     ebx, eax
0x18003fa57  test    eax, eax
0x18003fa59  js      loc_18003FBB1
0x18003fa5f  mov     rdx, rdi; unsigned __int16 *
0x18003fa62  mov     rcx, rsi; this
0x18003fa65  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003fa6a  mov     ebx, eax
0x18003fa6c  xor     ecx, ecx; this
0x18003fa6e  test    eax, eax
0x18003fa70  js      loc_18003FBB1
0x18003fa76  cmp     word ptr [rdi], 7Bh ; '{'
0x18003fa7a  jnz     short loc_18003FAD0
0x18003fa7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003fa80  inc     rax
0x18003fa83  cmp     [rdi+rax*2], cx
0x18003fa87  jnz     short loc_18003FA80
0x18003fa89  cmp     rax, 1
0x18003fa8d  jnz     short loc_18003FAD0
0x18003fa8f  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x18003fa94  xor     r9d, r9d; int
0x18003fa97  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18003fa9c  mov     rdx, rdi; unsigned __int16 *
0x18003fa9f  mov     rcx, rsi; this
0x18003faa2  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003faa7  mov     ebx, eax
0x18003faa9  test    eax, eax
0x18003faab  jns     short loc_18003FAB6
0x18003faad  test    r15d, r15d
0x18003fab0  jz      loc_18003FBB1
0x18003fab6  mov     rdx, rdi; unsigned __int16 *
0x18003fab9  mov     rcx, rsi; this
0x18003fabc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003fac1  mov     ebx, eax
0x18003fac3  xor     r15d, r15d
0x18003fac6  test    eax, eax
0x18003fac8  js      loc_18003FBB1
0x18003face  jmp     short loc_18003FAD3
0x18003fad0  xor     r15d, r15d
0x18003fad3  cmp     r14d, 2
0x18003fad7  jz      short loc_18003FB30
0x18003fad9  test    r14d, r14d
0x18003fadc  jz      short loc_18003FAF9
0x18003fade  xor     r12d, r12d
0x18003fae1  cmp     [rbp+21E0h+arg_20], r12d
0x18003fae8  jnz     short loc_18003FB33
0x18003faea  mov     ecx, r14d; unsigned int
0x18003faed  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18003faf2  mov     ebx, eax
0x18003faf4  jmp     loc_18003FBB1
0x18003faf9  cmp     [rbp+21E0h+arg_20], r15d
0x18003fb00  jz      short loc_18003FB44
0x18003fb02  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18003fb07  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x18003fb0c  test    eax, eax
  ... truncated ...
```
