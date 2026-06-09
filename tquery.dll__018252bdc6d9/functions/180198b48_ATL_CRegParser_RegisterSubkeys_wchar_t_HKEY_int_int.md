# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x180198b48`
- end: `0x180199121`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18019878c`
- `0x180198b48`

## callees

- `0x180176e60`
- `0x180188d90`
- `0x1801937fc`
- `0x180193f0c`
- `0x180194268`
- `0x180194384`
- `0x180195180`
- `0x180197a48`
- `0x180197c10`
- `0x180197da4`
- `0x180198678`
- `0x180198b48`
- `0x18019a2a0`
- `0x18019a370`
- `0x180294310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180198f4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180198f4e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180198d9d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180198d9d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180198e4f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180198e4f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180198bc3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180198bd6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180198caa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180198cd9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180198bc3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180198bd6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180198caa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180198cd9`

## string_xrefs

- `0x180198bcc`: `ForceRemove`
- `0x180198ca0`: `NoRemove`
- `0x180198bb9`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, wchar_t *a2, HKEY a3, int a4, int a5)
{
  int v5; // r15d
  wchar_t *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v33[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
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
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v33, 260, v7, -1);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
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
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v33) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v33);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
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
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180198b48  push    rbp
0x180198b4a  push    rbx
0x180198b4b  push    rsi
0x180198b4c  push    rdi
0x180198b4d  push    r12
0x180198b4f  push    r13
0x180198b51  push    r14
0x180198b53  push    r15
0x180198b55  lea     rbp, [rsp-21C8h]
0x180198b5d  mov     eax, 22C8h
0x180198b62  call    _alloca_probe
0x180198b67  sub     rsp, rax
0x180198b6a  mov     rax, cs:__security_cookie
0x180198b71  xor     rax, rsp
0x180198b74  mov     [rbp+2200h+var_50], rax
0x180198b7b  mov     r15d, r9d
0x180198b7e  mov     [rsp+2300h+var_22B0], r9d
0x180198b83  mov     r13, r8
0x180198b86  mov     rdi, rdx
0x180198b89  mov     rsi, rcx
0x180198b8c  xor     r14d, r14d
0x180198b8f  mov     [rsp+2300h+var_2290], r14
0x180198b94  mov     [rsp+2300h+var_2288], r14
0x180198b99  mov     [rbp+2200h+var_2280], r14
0x180198b9d  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198ba2  test    eax, eax
0x180198ba4  mov     ebx, eax
0x180198ba6  js      loc_1801990D5
0x180198bac  xor     r12d, r12d
0x180198baf  cmp     word ptr [rdi], 7Dh ; '}'
0x180198bb3  jz      loc_1801990D5
0x180198bb9  lea     rdx, aDelete; "Delete"
0x180198bc0  mov     rcx, rdi; lpString1
0x180198bc3  call    cs:__imp_lstrcmpiW
0x180198bc9  mov     r14d, eax
0x180198bcc  lea     rdx, aForceremove; "ForceRemove"
0x180198bd3  mov     rcx, rdi; lpString1
0x180198bd6  call    cs:__imp_lstrcmpiW
0x180198bdc  test    eax, eax
0x180198bde  jz      short loc_180198BE9
0x180198be0  test    r14d, r14d
0x180198be3  jnz     loc_180198C9A
0x180198be9  mov     rdx, rdi; wchar_t *
0x180198bec  mov     rcx, rsi; this
0x180198bef  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198bf4  mov     ebx, eax
0x180198bf6  test    eax, eax
0x180198bf8  js      loc_1801990D5
0x180198bfe  test    r15d, r15d
0x180198c01  jz      loc_180198C9A
0x180198c07  mov     [rsp+2300h+hKey], r12
0x180198c0c  mov     [rsp+2300h+var_22A0], r12
0x180198c11  mov     [rsp+2300h+var_2298], r12
0x180198c16  mov     edx, 5Ch ; '\'; wchar_t
0x180198c1b  mov     rcx, rdi; lpsz
0x180198c1e  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x180198c23  test    rax, rax
0x180198c26  jnz     loc_1801990C6
0x180198c2c  mov     rdx, rdi; wchar_t *
0x180198c2f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x180198c34  test    eax, eax
0x180198c36  jz      short loc_180198C4F
0x180198c38  mov     [rsp+2300h+hKey], r13
0x180198c3d  mov     rdx, rdi; wchar_t *
0x180198c40  lea     rcx, [rsp+2300h+hKey]; this
0x180198c45  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x180198c4a  mov     [rsp+2300h+hKey], r12
0x180198c4f  test    r14d, r14d
0x180198c52  jnz     short loc_180198C90
0x180198c54  mov     rdx, rdi; wchar_t *
0x180198c57  mov     rcx, rsi; this
0x180198c5a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198c5f  mov     ebx, eax
0x180198c61  xor     r14d, r14d
0x180198c64  test    eax, eax
0x180198c66  js      loc_18019910D
0x180198c6c  mov     rdx, rdi; wchar_t *
0x180198c6f  mov     rcx, rsi; this
0x180198c72  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180198c77  mov     ebx, eax
0x180198c79  test    eax, eax
0x180198c7b  lea     rcx, [rsp+2300h+hKey]; this
0x180198c80  js      loc_180199112
0x180198c86  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180198c8b  jmp     loc_180198EB4
0x180198c90  lea     rcx, [rsp+2300h+hKey]; this
0x180198c95  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180198c9a  mov     r12d, 1
0x180198ca0  lea     rdx, aNoremove; "NoRemove"
0x180198ca7  mov     rcx, rdi; lpString1
0x180198caa  call    cs:__imp_lstrcmpiW
0x180198cb0  xor     r14d, r14d
0x180198cb3  test    eax, eax
0x180198cb5  jnz     short loc_180198CCF
0x180198cb7  mov     r12d, r14d
0x180198cba  mov     rdx, rdi; wchar_t *
0x180198cbd  mov     rcx, rsi; this
0x180198cc0  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198cc5  mov     ebx, eax
0x180198cc7  test    eax, eax
0x180198cc9  js      loc_1801990D5
0x180198ccf  lea     rdx, aVal; "Val"
0x180198cd6  mov     rcx, rdi; lpString1
0x180198cd9  call    cs:__imp_lstrcmpiW
0x180198cdf  test    eax, eax
0x180198ce1  jnz     loc_180198DC8
0x180198ce7  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x180198cee  mov     rcx, rsi; this
0x180198cf1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198cf6  mov     ebx, eax
0x180198cf8  test    eax, eax
0x180198cfa  js      loc_1801990D5
0x180198d00  mov     rdx, rdi; wchar_t *
0x180198d03  mov     rcx, rsi; this
0x180198d06  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198d0b  mov     ebx, eax
0x180198d0d  test    eax, eax
0x180198d0f  js      loc_1801990D5
0x180198d15  cmp     word ptr [rdi], 3Dh ; '='
0x180198d19  jnz     loc_1801990D0
0x180198d1f  test    r15d, r15d
0x180198d22  jz      short loc_180198D56
0x180198d24  mov     [rsp+2300h+var_22A0], r14
0x180198d29  mov     [rsp+2300h+var_2298], r14
0x180198d2e  mov     [rsp+2300h+hKey], r13
0x180198d33  mov     r9, rdi; wchar_t *
0x180198d36  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x180198d3d  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180198d42  mov     rcx, rsi; this
0x180198d45  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180198d4a  mov     ebx, eax
0x180198d4c  mov     [rsp+2300h+hKey], r14
0x180198d51  jmp     loc_180198C79
0x180198d56  cmp     [rbp+2200h+arg_20], r14d
0x180198d5d  jnz     short loc_180198DB8
0x180198d5f  test    r12d, r12d
0x180198d62  jz      short loc_180198DB8
0x180198d64  mov     [rsp+2300h+hKey], r14
0x180198d69  mov     [rsp+2300h+var_22A0], r14
0x180198d6e  mov     [rsp+2300h+var_2298], r14
0x180198d73  mov     r9d, 20006h; unsigned int
0x180198d79  xor     r8d, r8d; lpSubKey
0x180198d7c  mov     rdx, r13; hKey
0x180198d7f  lea     rcx, [rsp+2300h+hKey]; this
0x180198d84  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180198d89  test    eax, eax
0x180198d8b  jnz     loc_180199104
0x180198d91  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180198d98  mov     rcx, [rsp+2300h+hKey]; hKey
0x180198d9d  call    cs:__imp_RegDeleteValueW
0x180198da3  test    eax, 0FFFFFFFDh
0x180198da8  jnz     loc_180199104
0x180198dae  lea     rcx, [rsp+2300h+hKey]; this
0x180198db3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180198db8  mov     rdx, rdi; wchar_t *
0x180198dbb  mov     rcx, rsi; this
0x180198dbe  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180198dc3  jmp     loc_180198BA2
0x180198dc8  mov     edx, 5Ch ; '\'; wchar_t
0x180198dcd  mov     rcx, rdi; lpsz
0x180198dd0  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x180198dd5  test    rax, rax
0x180198dd8  jnz     loc_1801990D0
0x180198dde  test    r15d, r15d
0x180198de1  jz      loc_180198F03
0x180198de7  mov     ebx, 2001Fh
0x180198dec  mov     r9d, ebx; unsigned int
0x180198def  mov     r8, rdi; lpSubKey
0x180198df2  mov     rdx, r13; hKey
0x180198df5  lea     rcx, [rsp+2300h+var_2290]; this
0x180198dfa  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180198dff  test    eax, eax
0x180198e01  jz      short loc_180198E7C
0x180198e03  lea     r9d, [rbx-6]; unsigned int
0x180198e07  mov     r8, rdi; lpSubKey
0x180198e0a  mov     rdx, r13; hKey
0x180198e0d  lea     rcx, [rsp+2300h+var_2290]; this
0x180198e12  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180198e17  test    eax, eax
0x180198e19  jz      short loc_180198E7C
0x180198e1b  mov     [rbp+2200h+dwDisposition], r14d
0x180198e1f  mov     [rbp+2200h+var_2270], r14
0x180198e23  lea     rax, [rbp+2200h+dwDisposition]
0x180198e27  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180198e2c  lea     rax, [rbp+2200h+var_2270]
0x180198e30  mov     [rsp+2300h+phkResult], rax; phkResult
0x180198e35  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180198e3a  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180198e3e  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x180198e43  xor     r9d, r9d; lpClass
0x180198e46  xor     r8d, r8d; Reserved
0x180198e49  mov     rdx, rdi; lpSubKey
0x180198e4c  mov     rcx, r13; hKey
0x180198e4f  call    cs:__imp_RegCreateKeyExW
0x180198e55  mov     ecx, eax
0x180198e57  test    eax, eax
0x180198e59  jnz     loc_180199003
0x180198e5f  lea     rcx, [rsp+2300h+var_2290]; this
0x180198e64  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180198e69  mov     ecx, eax
0x180198e6b  mov     rax, [rbp+2200h+var_2270]
0x180198e6f  mov     [rsp+2300h+var_2290], rax
0x180198e74  test    ecx, ecx
0x180198e76  jnz     loc_180199003
0x180198e7c  mov     rdx, rdi; wchar_t *
0x180198e7f  mov     rcx, rsi; this
0x180198e82  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198e87  mov     ebx, eax
0x180198e89  test    eax, eax
0x180198e8b  js      loc_1801990D5
0x180198e91  cmp     word ptr [rdi], 3Dh ; '='
0x180198e95  jnz     short loc_180198EB4
0x180198e97  mov     r9, rdi; wchar_t *
0x180198e9a  xor     r8d, r8d; wchar_t *
0x180198e9d  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180198ea2  mov     rcx, rsi; this
0x180198ea5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180198eaa  mov     ebx, eax
0x180198eac  test    eax, eax
0x180198eae  js      loc_1801990D5
0x180198eb4  cmp     word ptr [rdi], 7Bh ; '{'
0x180198eb8  jnz     loc_180198BAC
0x180198ebe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180198ec2  inc     rax
0x180198ec5  cmp     [rdi+rax*2], r14w
0x180198eca  jnz     short loc_180198EC2
0x180198ecc  cmp     rax, 1
0x180198ed0  jnz     loc_180198BAC
0x180198ed6  mov     [rsp+2300h+dwOptions], r14d; int
0x180198edb  mov     r9d, r15d; int
0x180198ede  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180198ee3  mov     rdx, rdi; wchar_t *
0x180198ee6  mov     rcx, rsi; this
0x180198ee9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180198eee  mov     ebx, eax
0x180198ef0  test    eax, eax
0x180198ef2  js      loc_1801990D5
0x180198ef8  mov     rdx, rdi
0x180198efb  mov     rcx, rsi
0x180198efe  jmp     loc_180198B9D
0x180198f03  cmp     [rbp+2200h+arg_20], r14d
0x180198f0a  jnz     short loc_180198F27
0x180198f0c  mov     r9d, 20019h; unsigned int
0x180198f12  mov     r8, rdi; lpSubKey
0x180198f15  mov     rdx, r13; hKey
0x180198f18  lea     rcx, [rsp+2300h+var_2290]; this
0x180198f1d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180198f22  mov     r14d, eax
0x180198f25  jmp     short loc_180198F2D
0x180198f27  mov     r14d, 2
0x180198f2d  mov     r15d, 1
0x180198f33  test    r14d, r14d
0x180198f36  cmovz   r15d, [rbp+2200h+arg_20]
0x180198f3e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180198f42  mov     r8, rdi
0x180198f45  mov     edx, 104h
0x180198f4a  lea     rcx, [rbp+2200h+var_2260]
0x180198f4e  call    cs:__imp__o_wcsncpy_s
0x180198f54  mov     ecx, eax; int
0x180198f56  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180198f5b  mov     rdx, rdi; wchar_t *
0x180198f5e  mov     rcx, rsi; this
0x180198f61  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198f66  mov     ebx, eax
0x180198f68  test    eax, eax
0x180198f6a  js      loc_1801990D5
0x180198f70  mov     rdx, rdi; wchar_t *
0x180198f73  mov     rcx, rsi; this
0x180198f76  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180198f7b  mov     ebx, eax
0x180198f7d  xor     ecx, ecx
0x180198f7f  test    eax, eax
0x180198f81  js      loc_1801990D5
0x180198f87  cmp     word ptr [rdi], 7Bh ; '{'
0x180198f8b  jnz     short loc_180198FDC
0x180198f8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180198f91  inc     rax
0x180198f94  cmp     [rdi+rax*2], cx
0x180198f98  jnz     short loc_180198F91
0x180198f9a  cmp     rax, 1
0x180198f9e  jnz     short loc_180198FDC
0x180198fa0  mov     [rsp+2300h+dwOptions], r15d; int
0x180198fa5  xor     r9d, r9d; int
0x180198fa8  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180198fad  mov     rdx, rdi; wchar_t *
0x180198fb0  mov     rcx, rsi; this
0x180198fb3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180198fb8  mov     ebx, eax
0x180198fba  test    eax, eax
0x180198fbc  jns     short loc_180198FC7
0x180198fbe  test    r15d, r15d
0x180198fc1  jz      loc_1801990D5
0x180198fc7  mov     rdx, rdi; wchar_t *
0x180198fca  mov     rcx, rsi; this
0x180198fcd  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180198fd2  mov     ebx, eax
0x180198fd4  test    eax, eax
0x180198fd6  js      loc_1801990D5
0x180198fdc  cmp     r14d, 2
0x180198fe0  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
