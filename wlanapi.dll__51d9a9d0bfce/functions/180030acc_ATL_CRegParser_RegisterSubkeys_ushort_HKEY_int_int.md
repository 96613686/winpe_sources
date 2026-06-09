# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180030acc`
- end: `0x18003104d`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1409`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800307ac`
- `0x180030acc`

## callees

- `0x180019a20`
- `0x18002f5ac`
- `0x18002fb10`
- `0x18002fb80`
- `0x18002fcb4`
- `0x18002fe54`
- `0x18002fe80`
- `0x18002ff08`
- `0x1800300ec`
- `0x180030264`
- `0x1800303dc`
- `0x180030698`
- `0x180030acc`
- `0x1800311f4`
- `0x1800312c4`
- `0x1800600d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030e8d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030e8d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030d1d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030d1d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030b40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030b53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030c24`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030c53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030b40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030b53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030c24`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180030c53`

## string_xrefs

- `0x180030b36`: `Delete`
- `0x180030b49`: `ForceRemove`
- `0x180030c1a`: `NoRemove`

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
  unsigned int v27; // [rsp+20h] [rbp-E0h]
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
      v21 = _o_wcsncpy_s(v36, 260, v7, -1);
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
0x180030acc  push    rbp
0x180030ace  push    rbx
0x180030acf  push    rsi
0x180030ad0  push    rdi
0x180030ad1  push    r12
0x180030ad3  push    r13
0x180030ad5  push    r14
0x180030ad7  push    r15
0x180030ad9  lea     rbp, [rsp-21A8h]
0x180030ae1  mov     eax, 22A8h
0x180030ae6  call    _alloca_probe
0x180030aeb  sub     rsp, rax
0x180030aee  mov     rax, cs:__security_cookie
0x180030af5  xor     rax, rsp
0x180030af8  mov     [rbp+21E0h+var_50], rax
0x180030aff  mov     r15d, r9d
0x180030b02  mov     [rsp+22E0h+var_22A0], r9d
0x180030b07  mov     r13, r8
0x180030b0a  mov     rdi, rdx
0x180030b0d  mov     rsi, rcx
0x180030b10  xor     r12d, r12d
0x180030b13  mov     [rsp+22E0h+var_2280], r12
0x180030b18  mov     [rsp+22E0h+var_2278], r12
0x180030b1d  mov     [rsp+22E0h+var_2270], r12
0x180030b22  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030b27  mov     ebx, eax
0x180030b29  test    eax, eax
0x180030b2b  js      loc_180031001
0x180030b31  jmp     loc_180030F88
0x180030b36  lea     rdx, String2; "Delete"
0x180030b3d  mov     rcx, rdi; lpString1
0x180030b40  call    cs:__imp_lstrcmpiW
0x180030b46  mov     r14d, eax
0x180030b49  lea     rdx, aForceremove; "ForceRemove"
0x180030b50  mov     rcx, rdi; lpString1
0x180030b53  call    cs:__imp_lstrcmpiW
0x180030b59  test    eax, eax
0x180030b5b  jz      short loc_180030B66
0x180030b5d  test    r14d, r14d
0x180030b60  jnz     loc_180030C14
0x180030b66  mov     rdx, rdi; unsigned __int16 *
0x180030b69  mov     rcx, rsi; this
0x180030b6c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030b71  mov     ebx, eax
0x180030b73  test    eax, eax
0x180030b75  js      loc_180031001
0x180030b7b  test    r15d, r15d
0x180030b7e  jz      loc_180030C14
0x180030b84  mov     [rsp+22E0h+hKey], r12
0x180030b89  mov     [rsp+22E0h+var_2290], r12
0x180030b8e  mov     [rsp+22E0h+var_2288], r12
0x180030b93  mov     edx, 5Ch ; '\'; unsigned __int16
0x180030b98  mov     rcx, rdi; lpsz
0x180030b9b  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180030ba0  test    rax, rax
0x180030ba3  jnz     loc_180030FF2
0x180030ba9  mov     rdx, rdi; unsigned __int16 *
0x180030bac  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180030bb1  test    eax, eax
0x180030bb3  jz      short loc_180030BCC
0x180030bb5  mov     [rsp+22E0h+hKey], r13
0x180030bba  mov     rdx, rdi; unsigned __int16 *
0x180030bbd  lea     rcx, [rsp+22E0h+hKey]; this
0x180030bc2  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180030bc7  mov     [rsp+22E0h+hKey], r12
0x180030bcc  test    r14d, r14d
0x180030bcf  jnz     short loc_180030C0A
0x180030bd1  mov     rdx, rdi; unsigned __int16 *
0x180030bd4  mov     rcx, rsi; this
0x180030bd7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030bdc  mov     ebx, eax
0x180030bde  test    eax, eax
0x180030be0  js      loc_180031039
0x180030be6  mov     rdx, rdi; unsigned __int16 *
0x180030be9  mov     rcx, rsi; this
0x180030bec  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180030bf1  mov     ebx, eax
0x180030bf3  test    eax, eax
0x180030bf5  lea     rcx, [rsp+22E0h+hKey]; this
0x180030bfa  js      loc_18003103E
0x180030c00  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180030c05  jmp     loc_180030DF3
0x180030c0a  lea     rcx, [rsp+22E0h+hKey]; this
0x180030c0f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180030c14  mov     r12d, 1
0x180030c1a  lea     rdx, aNoremove; "NoRemove"
0x180030c21  mov     rcx, rdi; lpString1
0x180030c24  call    cs:__imp_lstrcmpiW
0x180030c2a  xor     r14d, r14d
0x180030c2d  test    eax, eax
0x180030c2f  jnz     short loc_180030C49
0x180030c31  mov     r12d, r14d
0x180030c34  mov     rdx, rdi; unsigned __int16 *
0x180030c37  mov     rcx, rsi; this
0x180030c3a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030c3f  mov     ebx, eax
0x180030c41  test    eax, eax
0x180030c43  js      loc_180031001
0x180030c49  lea     rdx, aVal; "Val"
0x180030c50  mov     rcx, rdi; lpString1
0x180030c53  call    cs:__imp_lstrcmpiW
0x180030c59  test    eax, eax
0x180030c5b  jnz     loc_180030D4D
0x180030c61  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180030c68  mov     rcx, rsi; this
0x180030c6b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030c70  mov     ebx, eax
0x180030c72  test    eax, eax
0x180030c74  js      loc_180031001
0x180030c7a  mov     rdx, rdi; unsigned __int16 *
0x180030c7d  mov     rcx, rsi; this
0x180030c80  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030c85  mov     ebx, eax
0x180030c87  test    eax, eax
0x180030c89  js      loc_180031001
0x180030c8f  cmp     word ptr [rdi], 3Dh ; '='
0x180030c93  jnz     loc_180030FFC
0x180030c99  test    r15d, r15d
0x180030c9c  jz      short loc_180030CD3
0x180030c9e  xor     r12d, r12d
0x180030ca1  mov     [rsp+22E0h+var_2290], r12
0x180030ca6  mov     [rsp+22E0h+var_2288], r12
0x180030cab  mov     [rsp+22E0h+hKey], r13
0x180030cb0  mov     r9, rdi; unsigned __int16 *
0x180030cb3  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180030cba  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180030cbf  mov     rcx, rsi; this
0x180030cc2  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180030cc7  mov     ebx, eax
0x180030cc9  mov     [rsp+22E0h+hKey], r12
0x180030cce  jmp     loc_180030BF3
0x180030cd3  cmp     [rbp+21E0h+arg_20], r14d
0x180030cda  jnz     short loc_180030D3A
0x180030cdc  test    r12d, r12d
0x180030cdf  jz      short loc_180030D3A
0x180030ce1  xor     r12d, r12d
0x180030ce4  mov     [rsp+22E0h+hKey], r12
0x180030ce9  mov     [rsp+22E0h+var_2290], r12
0x180030cee  mov     [rsp+22E0h+var_2288], r12
0x180030cf3  mov     r9d, 20006h; unsigned int
0x180030cf9  xor     r8d, r8d; lpSubKey
0x180030cfc  mov     rdx, r13; hKey
0x180030cff  lea     rcx, [rsp+22E0h+hKey]; this
0x180030d04  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180030d09  test    eax, eax
0x180030d0b  jnz     loc_180031030
0x180030d11  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180030d18  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180030d1d  call    cs:__imp_RegDeleteValueW
0x180030d23  test    eax, 0FFFFFFFDh
0x180030d28  jnz     loc_180031030
0x180030d2e  lea     rcx, [rsp+22E0h+hKey]; this
0x180030d33  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180030d38  jmp     short loc_180030D3D
0x180030d3a  xor     r12d, r12d
0x180030d3d  mov     rdx, rdi; unsigned __int16 *
0x180030d40  mov     rcx, rsi; this
0x180030d43  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180030d48  jmp     loc_180030B27
0x180030d4d  mov     edx, 5Ch ; '\'; unsigned __int16
0x180030d52  mov     rcx, rdi; lpsz
0x180030d55  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180030d5a  test    rax, rax
0x180030d5d  jnz     loc_180030FFC
0x180030d63  test    r15d, r15d
0x180030d66  jz      loc_180030E42
0x180030d6c  mov     r9d, 2001Fh; unsigned int
0x180030d72  mov     r8, rdi; lpSubKey
0x180030d75  mov     rdx, r13; hKey
0x180030d78  lea     rcx, [rsp+22E0h+var_2280]; this
0x180030d7d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180030d82  xor     r12d, r12d
0x180030d85  test    eax, eax
0x180030d87  jz      short loc_180030DBB
0x180030d89  mov     r9d, 20019h; unsigned int
0x180030d8f  mov     r8, rdi; lpSubKey
0x180030d92  mov     rdx, r13; hKey
0x180030d95  lea     rcx, [rsp+22E0h+var_2280]; this
0x180030d9a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180030d9f  test    eax, eax
0x180030da1  jz      short loc_180030DBB
0x180030da3  mov     r8, rdi; lpSubKey
0x180030da6  mov     rdx, r13; hKey
0x180030da9  lea     rcx, [rsp+22E0h+var_2280]; this
0x180030dae  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180030db3  test    eax, eax
0x180030db5  jnz     loc_180031045
0x180030dbb  mov     rdx, rdi; unsigned __int16 *
0x180030dbe  mov     rcx, rsi; this
0x180030dc1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030dc6  mov     ebx, eax
0x180030dc8  test    eax, eax
0x180030dca  js      loc_180031001
0x180030dd0  cmp     word ptr [rdi], 3Dh ; '='
0x180030dd4  jnz     short loc_180030DF3
0x180030dd6  mov     r9, rdi; unsigned __int16 *
0x180030dd9  xor     r8d, r8d; unsigned __int16 *
0x180030ddc  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180030de1  mov     rcx, rsi; this
0x180030de4  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180030de9  mov     ebx, eax
0x180030deb  test    eax, eax
0x180030ded  js      loc_180031001
0x180030df3  cmp     word ptr [rdi], 7Bh ; '{'
0x180030df7  jnz     loc_180030F88
0x180030dfd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030e01  inc     rax
0x180030e04  cmp     [rdi+rax*2], r12w
0x180030e09  jnz     short loc_180030E01
0x180030e0b  cmp     rax, 1
0x180030e0f  jnz     loc_180030F88
0x180030e15  mov     [rsp+22E0h+var_22C0], r12d; int
0x180030e1a  mov     r9d, r15d; int
0x180030e1d  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180030e22  mov     rdx, rdi; unsigned __int16 *
0x180030e25  mov     rcx, rsi; this
0x180030e28  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180030e2d  mov     ebx, eax
0x180030e2f  test    eax, eax
0x180030e31  js      loc_180031001
0x180030e37  mov     rdx, rdi
0x180030e3a  mov     rcx, rsi
0x180030e3d  jmp     loc_180030B22
0x180030e42  cmp     [rbp+21E0h+arg_20], r14d
0x180030e49  jnz     short loc_180030E66
0x180030e4b  mov     r9d, 20019h; unsigned int
0x180030e51  mov     r8, rdi; lpSubKey
0x180030e54  mov     rdx, r13; hKey
0x180030e57  lea     rcx, [rsp+22E0h+var_2280]; this
0x180030e5c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180030e61  mov     r14d, eax
0x180030e64  jmp     short loc_180030E6C
0x180030e66  mov     r14d, 2
0x180030e6c  mov     r15d, 1
0x180030e72  test    r14d, r14d
0x180030e75  cmovz   r15d, [rbp+21E0h+arg_20]
0x180030e7d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180030e81  mov     r8, rdi
0x180030e84  mov     edx, 104h
0x180030e89  lea     rcx, [rbp+21E0h+var_2260]
0x180030e8d  call    cs:__imp__o_wcsncpy_s
0x180030e93  mov     ecx, eax; int
0x180030e95  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180030e9a  mov     rdx, rdi; unsigned __int16 *
0x180030e9d  mov     rcx, rsi; this
0x180030ea0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030ea5  mov     ebx, eax
0x180030ea7  test    eax, eax
0x180030ea9  js      loc_180031001
0x180030eaf  mov     rdx, rdi; unsigned __int16 *
0x180030eb2  mov     rcx, rsi; this
0x180030eb5  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180030eba  mov     ebx, eax
0x180030ebc  xor     ecx, ecx; this
0x180030ebe  test    eax, eax
0x180030ec0  js      loc_180031001
0x180030ec6  cmp     word ptr [rdi], 7Bh ; '{'
0x180030eca  jnz     short loc_180030F20
0x180030ecc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030ed0  inc     rax
0x180030ed3  cmp     [rdi+rax*2], cx
0x180030ed7  jnz     short loc_180030ED0
0x180030ed9  cmp     rax, 1
0x180030edd  jnz     short loc_180030F20
0x180030edf  mov     [rsp+22E0h+var_22C0], r15d; int
0x180030ee4  xor     r9d, r9d; int
0x180030ee7  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180030eec  mov     rdx, rdi; unsigned __int16 *
0x180030eef  mov     rcx, rsi; this
0x180030ef2  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180030ef7  mov     ebx, eax
0x180030ef9  test    eax, eax
0x180030efb  jns     short loc_180030F06
0x180030efd  test    r15d, r15d
0x180030f00  jz      loc_180031001
0x180030f06  mov     rdx, rdi; unsigned __int16 *
0x180030f09  mov     rcx, rsi; this
0x180030f0c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180030f11  mov     ebx, eax
0x180030f13  xor     r15d, r15d
0x180030f16  test    eax, eax
0x180030f18  js      loc_180031001
0x180030f1e  jmp     short loc_180030F23
0x180030f20  xor     r15d, r15d
0x180030f23  cmp     r14d, 2
0x180030f27  jz      short loc_180030F80
0x180030f29  test    r14d, r14d
0x180030f2c  jz      short loc_180030F49
0x180030f2e  xor     r12d, r12d
0x180030f31  cmp     [rbp+21E0h+arg_20], r12d
0x180030f38  jnz     short loc_180030F83
0x180030f3a  mov     ecx, r14d; unsigned int
0x180030f3d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180030f42  mov     ebx, eax
0x180030f44  jmp     loc_180031001
0x180030f49  cmp     [rbp+21E0h+arg_20], r15d
0x180030f50  jz      short loc_180030F94
0x180030f52  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x180030f57  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180030f5c  test    eax, eax
  ... truncated ...
```
