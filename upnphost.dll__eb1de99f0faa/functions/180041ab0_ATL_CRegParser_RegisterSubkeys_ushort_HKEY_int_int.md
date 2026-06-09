# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180041ab0`
- end: `0x18004204e`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1438`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180041690`
- `0x180041ab0`

## callees

- `0x18003a560`
- `0x18003da48`
- `0x18003df34`
- `0x18003dfa4`
- `0x18003dfbc`
- `0x18003e154`
- `0x18003e1e0`
- `0x18003eb90`
- `0x18003fc38`
- `0x180040630`
- `0x1800409ac`
- `0x18004157c`
- `0x180041ab0`
- `0x180042d28`
- `0x180042fdc`
- `0x1800542a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180041e71`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180041e71`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180041cff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180041cff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041b24`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041b37`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041c08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041c37`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041b24`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041b37`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041c08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041c37`

## string_xrefs

- `0x180041b2a`: `ForceRemove`
- `0x180041bf8`: `NoRemove`
- `0x180041b1a`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // r15d
  int v21; // eax
  int v22; // eax
  ATL::CRegParser *v23; // rcx
  __int64 v24; // rax
  int HasSubKeys; // r15d
  unsigned int v26; // r14d
  unsigned int v28; // ecx
  __int64 v29; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  HKEY v34[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v35[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  memset(v34, 0, 24);
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_3:
    v10 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
        {
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
          if ( v5 )
          {
            hKey = 0;
            v32 = 0;
            v33 = 0;
            if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
              v10 = -2147352567;
              goto LABEL_79;
            }
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
            {
              hKey = a3;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
              hKey = 0;
            }
            if ( !v11 )
            {
              v10 = ATL::CRegParser::NextToken(i, v7);
              if ( v10 < 0 )
                goto LABEL_81;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_15:
              v10 = v13;
              if ( v13 < 0 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              goto LABEL_40;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v10 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v10 < 0 )
            goto LABEL_79;
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
          if ( *v7 != 61 )
            goto LABEL_78;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_31;
            hKey = 0;
            v32 = 0;
            v33 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_3;
              }
            }
LABEL_80:
            v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_79;
          }
          hKey = a3;
          v32 = 0;
          v33 = 0;
          v13 = ATL::CRegParser::AddValue(i, &hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_15;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_78;
        if ( v5 )
          break;
        if ( a5 )
          v19 = 2;
        else
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        v21 = _o_wcsncpy_s(v35, 260, v7, -1, v29);
        ATL::AtlCrtErrorCheck(v21);
        v10 = ATL::CRegParser::NextToken(i, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v22 = ATL::CRegParser::SkipAssignment(i, v7);
        v23 = 0;
        v10 = v22;
        if ( v22 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v7[v24] );
          if ( v24 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(i, v7, v34[0], 0, v20);
            if ( v10 < 0 && !v20 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(i, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        if ( v19 != 2 )
        {
          if ( v19 )
          {
            if ( !a5 )
            {
              v10 = ATL::AtlHresultFromWin32(v19);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v23, v34[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v23, v35) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, v35);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v23, v34[0]);
            v26 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
            if ( v26 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v34);
              v28 = v26;
              return ATL::AtlHresultFromWin32(v28);
            }
            if ( v14 && !HasSubKeys )
            {
              v32 = 0;
              v33 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v35);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
        v5 = a4;
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u) )
        {
          v17 = ATL::CRegKey::Create((ATL::CRegKey *)v34, a3, v7, v16, v29);
          if ( v17 )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v34);
            v28 = v17;
            return ATL::AtlHresultFromWin32(v28);
          }
        }
      }
      v10 = ATL::CRegParser::NextToken(i, v7);
      if ( v10 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v10 = ATL::CRegParser::AddValue(i, v34, 0, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
LABEL_40:
      if ( *v7 == 123 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v7[v18] );
        if ( v18 == 1 )
          break;
      }
    }
    v10 = ATL::CRegParser::RegisterSubkeys(i, v7, v34[0], v5, 0);
    if ( v10 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180041ab0  push    rbp
0x180041ab2  push    rbx
0x180041ab3  push    rsi
0x180041ab4  push    rdi
0x180041ab5  push    r12
0x180041ab7  push    r13
0x180041ab9  push    r14
0x180041abb  push    r15
0x180041abd  lea     rbp, [rsp-21A8h]
0x180041ac5  mov     eax, 22A8h
0x180041aca  call    _alloca_probe
0x180041acf  sub     rsp, rax
0x180041ad2  mov     rax, cs:__security_cookie
0x180041ad9  xor     rax, rsp
0x180041adc  mov     [rbp+21E0h+var_50], rax
0x180041ae3  xor     r12d, r12d
0x180041ae6  mov     [rsp+22E0h+var_22A0], r9d
0x180041aeb  mov     [rsp+22E0h+var_2280], r12
0x180041af0  mov     r15d, r9d
0x180041af3  mov     [rsp+22E0h+var_2278], r12
0x180041af8  mov     r13, r8
0x180041afb  mov     [rsp+22E0h+var_2270], r12
0x180041b00  mov     rdi, rdx
0x180041b03  mov     rsi, rcx
0x180041b06  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041b0b  mov     ebx, eax
0x180041b0d  test    eax, eax
0x180041b0f  js      loc_180041FE8
0x180041b15  jmp     loc_180041F6C
0x180041b1a  lea     rdx, aDelete; "Delete"
0x180041b21  mov     rcx, rdi; lpString1
0x180041b24  call    cs:__imp_lstrcmpiW
0x180041b2a  lea     rdx, aForceremove; "ForceRemove"
0x180041b31  mov     rcx, rdi; lpString1
0x180041b34  mov     r14d, eax
0x180041b37  call    cs:__imp_lstrcmpiW
0x180041b3d  test    eax, eax
0x180041b3f  jz      short loc_180041B4A
0x180041b41  test    r14d, r14d
0x180041b44  jnz     loc_180041BF8
0x180041b4a  mov     rdx, rdi; unsigned __int16 *
0x180041b4d  mov     rcx, rsi; this
0x180041b50  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041b55  mov     ebx, eax
0x180041b57  test    eax, eax
0x180041b59  js      loc_180041FE8
0x180041b5f  test    r15d, r15d
0x180041b62  jz      loc_180041BF8
0x180041b68  mov     edx, 5Ch ; '\'; unsigned __int16
0x180041b6d  mov     [rsp+22E0h+hKey], r12
0x180041b72  mov     rcx, rdi; lpsz
0x180041b75  mov     [rsp+22E0h+var_2290], r12
0x180041b7a  mov     [rsp+22E0h+var_2288], r12
0x180041b7f  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180041b84  test    rax, rax
0x180041b87  jnz     loc_180041FD9
0x180041b8d  mov     rdx, rdi; unsigned __int16 *
0x180041b90  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180041b95  test    eax, eax
0x180041b97  jz      short loc_180041BB0
0x180041b99  mov     rdx, rdi; unsigned __int16 *
0x180041b9c  mov     [rsp+22E0h+hKey], r13
0x180041ba1  lea     rcx, [rsp+22E0h+hKey]; this
0x180041ba6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180041bab  mov     [rsp+22E0h+hKey], r12
0x180041bb0  test    r14d, r14d
0x180041bb3  jnz     short loc_180041BEE
0x180041bb5  mov     rdx, rdi; unsigned __int16 *
0x180041bb8  mov     rcx, rsi; this
0x180041bbb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041bc0  mov     ebx, eax
0x180041bc2  test    eax, eax
0x180041bc4  js      loc_180042020
0x180041bca  mov     rdx, rdi; unsigned __int16 *
0x180041bcd  mov     rcx, rsi; this
0x180041bd0  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180041bd5  lea     rcx, [rsp+22E0h+hKey]; this
0x180041bda  mov     ebx, eax
0x180041bdc  test    eax, eax
0x180041bde  js      loc_180042025
0x180041be4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180041be9  jmp     loc_180041DD7
0x180041bee  lea     rcx, [rsp+22E0h+hKey]; this
0x180041bf3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180041bf8  lea     rdx, aNoremove; "NoRemove"
0x180041bff  mov     rcx, rdi; lpString1
0x180041c02  mov     r12d, 1
0x180041c08  call    cs:__imp_lstrcmpiW
0x180041c0e  xor     r14d, r14d
0x180041c11  test    eax, eax
0x180041c13  jnz     short loc_180041C2D
0x180041c15  mov     rdx, rdi; unsigned __int16 *
0x180041c18  mov     rcx, rsi; this
0x180041c1b  mov     r12d, r14d
0x180041c1e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041c23  mov     ebx, eax
0x180041c25  test    eax, eax
0x180041c27  js      loc_180041FE8
0x180041c2d  lea     rdx, aVal; "Val"
0x180041c34  mov     rcx, rdi; lpString1
0x180041c37  call    cs:__imp_lstrcmpiW
0x180041c3d  test    eax, eax
0x180041c3f  jnz     loc_180041D2F
0x180041c45  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180041c4c  mov     rcx, rsi; this
0x180041c4f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041c54  mov     ebx, eax
0x180041c56  test    eax, eax
0x180041c58  js      loc_180041FE8
0x180041c5e  mov     rdx, rdi; unsigned __int16 *
0x180041c61  mov     rcx, rsi; this
0x180041c64  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041c69  mov     ebx, eax
0x180041c6b  test    eax, eax
0x180041c6d  js      loc_180041FE8
0x180041c73  cmp     word ptr [rdi], 3Dh ; '='
0x180041c77  jnz     loc_180041FE3
0x180041c7d  test    r15d, r15d
0x180041c80  jz      short loc_180041CB5
0x180041c82  xor     r12d, r12d
0x180041c85  mov     [rsp+22E0h+hKey], r13
0x180041c8a  mov     r9, rdi; unsigned __int16 *
0x180041c8d  mov     [rsp+22E0h+var_2290], r12
0x180041c92  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180041c99  mov     [rsp+22E0h+var_2288], r12
0x180041c9e  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180041ca3  mov     rcx, rsi; this
0x180041ca6  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180041cab  mov     [rsp+22E0h+hKey], r12
0x180041cb0  jmp     loc_180041BD5
0x180041cb5  cmp     [rbp+21E0h+arg_20], r14d
0x180041cbc  jnz     short loc_180041D1C
0x180041cbe  test    r12d, r12d
0x180041cc1  jz      short loc_180041D1C
0x180041cc3  xor     r12d, r12d
0x180041cc6  lea     rcx, [rsp+22E0h+hKey]; this
0x180041ccb  mov     r9d, 20006h; unsigned int
0x180041cd1  mov     [rsp+22E0h+hKey], r12
0x180041cd6  xor     r8d, r8d; lpSubKey
0x180041cd9  mov     [rsp+22E0h+var_2290], r12
0x180041cde  mov     rdx, r13; hKey
0x180041ce1  mov     [rsp+22E0h+var_2288], r12
0x180041ce6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180041ceb  test    eax, eax
0x180041ced  jnz     loc_180042017
0x180041cf3  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180041cf8  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180041cff  call    cs:__imp_RegDeleteValueW
0x180041d05  test    eax, 0FFFFFFFDh
0x180041d0a  jnz     loc_180042017
0x180041d10  lea     rcx, [rsp+22E0h+hKey]; this
0x180041d15  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180041d1a  jmp     short loc_180041D1F
0x180041d1c  xor     r12d, r12d
0x180041d1f  mov     rdx, rdi; unsigned __int16 *
0x180041d22  mov     rcx, rsi; this
0x180041d25  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180041d2a  jmp     loc_180041B0B
0x180041d2f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180041d34  mov     rcx, rdi; lpsz
0x180041d37  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180041d3c  test    rax, rax
0x180041d3f  jnz     loc_180041FE3
0x180041d45  test    r15d, r15d
0x180041d48  jz      loc_180041E26
0x180041d4e  mov     r9d, 2001Fh; unsigned int
0x180041d54  lea     rcx, [rsp+22E0h+var_2280]; this
0x180041d59  mov     r8, rdi; lpSubKey
0x180041d5c  mov     rdx, r13; hKey
0x180041d5f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180041d64  xor     r12d, r12d
0x180041d67  test    eax, eax
0x180041d69  jz      short loc_180041D9F
0x180041d6b  mov     r9d, 20019h; unsigned int
0x180041d71  lea     rcx, [rsp+22E0h+var_2280]; this
0x180041d76  mov     r8, rdi; lpSubKey
0x180041d79  mov     rdx, r13; hKey
0x180041d7c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180041d81  test    eax, eax
0x180041d83  jz      short loc_180041D9F
0x180041d85  mov     r8, rdi; lpSubKey
0x180041d88  lea     rcx, [rsp+22E0h+var_2280]; this
0x180041d8d  mov     rdx, r13; hKey
0x180041d90  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180041d95  mov     ebx, eax
0x180041d97  test    eax, eax
0x180041d99  jnz     loc_18004202C
0x180041d9f  mov     rdx, rdi; unsigned __int16 *
0x180041da2  mov     rcx, rsi; this
0x180041da5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041daa  mov     ebx, eax
0x180041dac  test    eax, eax
0x180041dae  js      loc_180041FE8
0x180041db4  cmp     word ptr [rdi], 3Dh ; '='
0x180041db8  jnz     short loc_180041DD7
0x180041dba  mov     r9, rdi; unsigned __int16 *
0x180041dbd  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180041dc2  xor     r8d, r8d; unsigned __int16 *
0x180041dc5  mov     rcx, rsi; this
0x180041dc8  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180041dcd  mov     ebx, eax
0x180041dcf  test    eax, eax
0x180041dd1  js      loc_180041FE8
0x180041dd7  cmp     word ptr [rdi], 7Bh ; '{'
0x180041ddb  jnz     loc_180041F6C
0x180041de1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041de5  inc     rax
0x180041de8  cmp     [rdi+rax*2], r12w
0x180041ded  jnz     short loc_180041DE5
0x180041def  cmp     rax, 1
0x180041df3  jnz     loc_180041F6C
0x180041df9  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180041dfe  mov     r9d, r15d; int
0x180041e01  mov     rdx, rdi; unsigned __int16 *
0x180041e04  mov     dword ptr [rsp+22E0h+var_22C0], r12d; int
0x180041e09  mov     rcx, rsi; this
0x180041e0c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180041e11  mov     ebx, eax
0x180041e13  test    eax, eax
0x180041e15  js      loc_180041FE8
0x180041e1b  mov     rdx, rdi
0x180041e1e  mov     rcx, rsi
0x180041e21  jmp     loc_180041B06
0x180041e26  cmp     [rbp+21E0h+arg_20], r14d
0x180041e2d  jnz     short loc_180041E4A
0x180041e2f  mov     r9d, 20019h; unsigned int
0x180041e35  lea     rcx, [rsp+22E0h+var_2280]; this
0x180041e3a  mov     r8, rdi; lpSubKey
0x180041e3d  mov     rdx, r13; hKey
0x180041e40  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180041e45  mov     r14d, eax
0x180041e48  jmp     short loc_180041E50
0x180041e4a  mov     r14d, 2
0x180041e50  test    r14d, r14d
0x180041e53  lea     rcx, [rbp+21E0h+var_2260]
0x180041e57  mov     r15d, 1
0x180041e5d  mov     r8, rdi
0x180041e60  cmovz   r15d, [rbp+21E0h+arg_20]
0x180041e68  mov     edx, 104h
0x180041e6d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180041e71  call    cs:__imp__o_wcsncpy_s
0x180041e77  mov     ecx, eax; int
0x180041e79  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180041e7e  mov     rdx, rdi; unsigned __int16 *
0x180041e81  mov     rcx, rsi; this
0x180041e84  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041e89  mov     ebx, eax
0x180041e8b  test    eax, eax
0x180041e8d  js      loc_180041FE8
0x180041e93  mov     rdx, rdi; unsigned __int16 *
0x180041e96  mov     rcx, rsi; this
0x180041e99  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180041e9e  xor     ecx, ecx; this
0x180041ea0  mov     ebx, eax
0x180041ea2  test    eax, eax
0x180041ea4  js      loc_180041FE8
0x180041eaa  cmp     word ptr [rdi], 7Bh ; '{'
0x180041eae  jnz     short loc_180041F04
0x180041eb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041eb4  inc     rax
0x180041eb7  cmp     [rdi+rax*2], cx
0x180041ebb  jnz     short loc_180041EB4
0x180041ebd  cmp     rax, 1
0x180041ec1  jnz     short loc_180041F04
0x180041ec3  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180041ec8  xor     r9d, r9d; int
0x180041ecb  mov     rdx, rdi; unsigned __int16 *
0x180041ece  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x180041ed3  mov     rcx, rsi; this
0x180041ed6  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180041edb  mov     ebx, eax
0x180041edd  test    eax, eax
0x180041edf  jns     short loc_180041EEA
0x180041ee1  test    r15d, r15d
0x180041ee4  jz      loc_180041FE8
0x180041eea  mov     rdx, rdi; unsigned __int16 *
0x180041eed  mov     rcx, rsi; this
0x180041ef0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041ef5  xor     r15d, r15d
0x180041ef8  mov     ebx, eax
0x180041efa  test    eax, eax
0x180041efc  js      loc_180041FE8
0x180041f02  jmp     short loc_180041F07
0x180041f04  xor     r15d, r15d
0x180041f07  cmp     r14d, 2
0x180041f0b  jz      short loc_180041F64
0x180041f0d  test    r14d, r14d
0x180041f10  jz      short loc_180041F2D
0x180041f12  xor     r12d, r12d
0x180041f15  cmp     [rbp+21E0h+arg_20], r12d
0x180041f1c  jnz     short loc_180041F67
0x180041f1e  mov     ecx, r14d; unsigned int
0x180041f21  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180041f26  mov     ebx, eax
0x180041f28  jmp     loc_180041FE8
0x180041f2d  cmp     [rbp+21E0h+arg_20], r15d
0x180041f34  jz      short loc_180041F78
0x180041f36  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x180041f3b  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180041f40  test    eax, eax
  ... truncated ...
```
