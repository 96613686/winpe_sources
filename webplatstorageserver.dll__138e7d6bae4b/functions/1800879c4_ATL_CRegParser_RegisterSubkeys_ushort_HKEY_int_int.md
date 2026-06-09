# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800879c4`
- end: `0x180087f61`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1437`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800875fc`
- `0x1800879c4`

## callees

- `0x180080fb0`
- `0x180085dc0`
- `0x1800864f0`
- `0x180086560`
- `0x1800868d8`
- `0x1800869f4`
- `0x180086a20`
- `0x180086cd8`
- `0x180086ec8`
- `0x180086fa0`
- `0x180087100`
- `0x1800874e8`
- `0x1800879c4`
- `0x180088054`
- `0x180088124`
- `0x1800bced0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180087d92`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180087d92`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180087c2a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180087c2a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087a48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087a5b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087b2f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087b5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087a48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087a5b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087b2f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087b5e`

## string_xrefs

- `0x180087a51`: `ForceRemove`
- `0x180087b25`: `NoRemove`
- `0x180087a3e`: `Delete`

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
  HKEY hKey[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h]
  HKEY v34[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  v34[0] = 0;
  v34[1] = 0;
  v35 = 0;
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_77;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_77;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_77;
        if ( !v5 )
          break;
        hKey[0] = 0;
        hKey[1] = 0;
        v33 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_76:
          v10 = -2147352567;
          goto LABEL_77;
        }
        if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey[0] = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, v7);
          hKey[0] = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_79;
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_77;
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
          goto LABEL_77;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_76;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v34, a3, v7, v16, v27, v28, v29, v30)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_77;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v34, 0, v7);
            if ( v10 < 0 )
              goto LABEL_77;
          }
          goto LABEL_40;
        }
LABEL_80:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_77;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v36, 260, v7, -1, v27);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_77;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_77;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_77;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_77;
        }
      }
      v5 = a4;
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
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v34[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, v36);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v34[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
          if ( v17 )
            goto LABEL_80;
          if ( v14 && !HasSubKeys )
          {
            hKey[1] = 0;
            v33 = 0;
            hKey[0] = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)hKey, v36);
            hKey[0] = 0;
            if ( v15 )
              goto LABEL_78;
            ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_77;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_77;
    if ( *v7 != 61 )
      goto LABEL_76;
    if ( v5 )
    {
      hKey[1] = 0;
      v33 = 0;
      hKey[0] = a3;
      v13 = ATL::CRegParser::AddValue(v8, hKey, ValueName, v7);
      v10 = v13;
      hKey[0] = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey[0] = 0;
    hKey[1] = 0;
    v33 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey[0], ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_78:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_77:
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800879c4  push    rbp
0x1800879c6  push    rbx
0x1800879c7  push    rsi
0x1800879c8  push    rdi
0x1800879c9  push    r12
0x1800879cb  push    r13
0x1800879cd  push    r14
0x1800879cf  push    r15
0x1800879d1  lea     rbp, [rsp-21A8h]
0x1800879d9  mov     eax, 22A8h
0x1800879de  call    _alloca_probe
0x1800879e3  sub     rsp, rax
0x1800879e6  mov     rax, cs:__security_cookie
0x1800879ed  xor     rax, rsp
0x1800879f0  mov     [rbp+21E0h+var_50], rax
0x1800879f7  mov     r15d, r9d
0x1800879fa  mov     [rsp+22E0h+var_22A0], r9d
0x1800879ff  mov     r13, r8
0x180087a02  mov     rdi, rdx
0x180087a05  mov     rsi, rcx
0x180087a08  xorps   xmm0, xmm0
0x180087a0b  movups  xmmword ptr [rsp+22E0h+var_2280], xmm0
0x180087a10  xor     r14d, r14d
0x180087a13  mov     [rsp+22E0h+var_2280], r14
0x180087a18  mov     [rsp+22E0h+var_2280+8], r14
0x180087a1d  mov     [rsp+22E0h+var_2270], r14
0x180087a22  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087a27  test    eax, eax
0x180087a29  mov     ebx, eax
0x180087a2b  js      loc_180087F15
0x180087a31  xor     r12d, r12d
0x180087a34  cmp     word ptr [rdi], 7Dh ; '}'
0x180087a38  jz      loc_180087F15
0x180087a3e  lea     rdx, String2; "Delete"
0x180087a45  mov     rcx, rdi; lpString1
0x180087a48  call    cs:__imp_lstrcmpiW
0x180087a4e  mov     r14d, eax
0x180087a51  lea     rdx, aForceremove; "ForceRemove"
0x180087a58  mov     rcx, rdi; lpString1
0x180087a5b  call    cs:__imp_lstrcmpiW
0x180087a61  test    eax, eax
0x180087a63  jz      short loc_180087A6E
0x180087a65  test    r14d, r14d
0x180087a68  jnz     loc_180087B1F
0x180087a6e  mov     rdx, rdi; unsigned __int16 *
0x180087a71  mov     rcx, rsi; this
0x180087a74  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087a79  mov     ebx, eax
0x180087a7b  test    eax, eax
0x180087a7d  js      loc_180087F15
0x180087a83  test    r15d, r15d
0x180087a86  jz      loc_180087B1F
0x180087a8c  mov     [rsp+22E0h+hKey], r12
0x180087a91  mov     [rsp+22E0h+hKey+8], r12
0x180087a96  mov     [rsp+22E0h+var_2288], r12
0x180087a9b  mov     edx, 5Ch ; '\'; unsigned __int16
0x180087aa0  mov     rcx, rdi; lpsz
0x180087aa3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180087aa8  test    rax, rax
0x180087aab  jnz     loc_180087F06
0x180087ab1  mov     rdx, rdi; unsigned __int16 *
0x180087ab4  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180087ab9  test    eax, eax
0x180087abb  jz      short loc_180087AD4
0x180087abd  mov     [rsp+22E0h+hKey], r13
0x180087ac2  mov     rdx, rdi; unsigned __int16 *
0x180087ac5  lea     rcx, [rsp+22E0h+hKey]; this
0x180087aca  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180087acf  mov     [rsp+22E0h+hKey], r12
0x180087ad4  test    r14d, r14d
0x180087ad7  jnz     short loc_180087B15
0x180087ad9  mov     rdx, rdi; unsigned __int16 *
0x180087adc  mov     rcx, rsi; this
0x180087adf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087ae4  mov     ebx, eax
0x180087ae6  xor     r14d, r14d
0x180087ae9  test    eax, eax
0x180087aeb  js      loc_180087F4D
0x180087af1  mov     rdx, rdi; unsigned __int16 *
0x180087af4  mov     rcx, rsi; this
0x180087af7  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180087afc  mov     ebx, eax
0x180087afe  test    eax, eax
0x180087b00  lea     rcx, [rsp+22E0h+hKey]; this
0x180087b05  js      loc_180087F52
0x180087b0b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180087b10  jmp     loc_180087CF8
0x180087b15  lea     rcx, [rsp+22E0h+hKey]; this
0x180087b1a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180087b1f  mov     r12d, 1
0x180087b25  lea     rdx, aNoremove; "NoRemove"
0x180087b2c  mov     rcx, rdi; lpString1
0x180087b2f  call    cs:__imp_lstrcmpiW
0x180087b35  xor     r14d, r14d
0x180087b38  test    eax, eax
0x180087b3a  jnz     short loc_180087B54
0x180087b3c  mov     r12d, r14d
0x180087b3f  mov     rdx, rdi; unsigned __int16 *
0x180087b42  mov     rcx, rsi; this
0x180087b45  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087b4a  mov     ebx, eax
0x180087b4c  test    eax, eax
0x180087b4e  js      loc_180087F15
0x180087b54  lea     rdx, aVal; "Val"
0x180087b5b  mov     rcx, rdi; lpString1
0x180087b5e  call    cs:__imp_lstrcmpiW
0x180087b64  test    eax, eax
0x180087b66  jnz     loc_180087C55
0x180087b6c  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180087b73  mov     rcx, rsi; this
0x180087b76  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087b7b  mov     ebx, eax
0x180087b7d  test    eax, eax
0x180087b7f  js      loc_180087F15
0x180087b85  mov     rdx, rdi; unsigned __int16 *
0x180087b88  mov     rcx, rsi; this
0x180087b8b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087b90  mov     ebx, eax
0x180087b92  test    eax, eax
0x180087b94  js      loc_180087F15
0x180087b9a  cmp     word ptr [rdi], 3Dh ; '='
0x180087b9e  jnz     loc_180087F10
0x180087ba4  test    r15d, r15d
0x180087ba7  jz      short loc_180087BE3
0x180087ba9  xorps   xmm0, xmm0
0x180087bac  movups  xmmword ptr [rsp+22E0h+hKey], xmm0
0x180087bb1  mov     [rsp+22E0h+hKey+8], r14
0x180087bb6  mov     [rsp+22E0h+var_2288], r14
0x180087bbb  mov     [rsp+22E0h+hKey], r13
0x180087bc0  mov     r9, rdi; unsigned __int16 *
0x180087bc3  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180087bca  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180087bcf  mov     rcx, rsi; this
0x180087bd2  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180087bd7  mov     ebx, eax
0x180087bd9  mov     [rsp+22E0h+hKey], r14
0x180087bde  jmp     loc_180087AFE
0x180087be3  cmp     [rbp+21E0h+arg_20], r14d
0x180087bea  jnz     short loc_180087C45
0x180087bec  test    r12d, r12d
0x180087bef  jz      short loc_180087C45
0x180087bf1  mov     [rsp+22E0h+hKey], r14
0x180087bf6  mov     [rsp+22E0h+hKey+8], r14
0x180087bfb  mov     [rsp+22E0h+var_2288], r14
0x180087c00  mov     r9d, 20006h; unsigned int
0x180087c06  xor     r8d, r8d; lpSubKey
0x180087c09  mov     rdx, r13; hKey
0x180087c0c  lea     rcx, [rsp+22E0h+hKey]; this
0x180087c11  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180087c16  test    eax, eax
0x180087c18  jnz     loc_180087F44
0x180087c1e  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180087c25  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180087c2a  call    cs:__imp_RegDeleteValueW
0x180087c30  test    eax, 0FFFFFFFDh
0x180087c35  jnz     loc_180087F44
0x180087c3b  lea     rcx, [rsp+22E0h+hKey]; this
0x180087c40  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180087c45  mov     rdx, rdi; unsigned __int16 *
0x180087c48  mov     rcx, rsi; this
0x180087c4b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180087c50  jmp     loc_180087A27
0x180087c55  mov     edx, 5Ch ; '\'; unsigned __int16
0x180087c5a  mov     rcx, rdi; lpsz
0x180087c5d  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180087c62  test    rax, rax
0x180087c65  jnz     loc_180087F10
0x180087c6b  test    r15d, r15d
0x180087c6e  jz      loc_180087D47
0x180087c74  mov     r9d, 2001Fh; unsigned int
0x180087c7a  mov     r8, rdi; lpSubKey
0x180087c7d  mov     rdx, r13; hKey
0x180087c80  lea     rcx, [rsp+22E0h+var_2280]; this
0x180087c85  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180087c8a  test    eax, eax
0x180087c8c  jz      short loc_180087CC0
0x180087c8e  mov     r9d, 20019h; unsigned int
0x180087c94  mov     r8, rdi; lpSubKey
0x180087c97  mov     rdx, r13; hKey
0x180087c9a  lea     rcx, [rsp+22E0h+var_2280]; this
0x180087c9f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180087ca4  test    eax, eax
0x180087ca6  jz      short loc_180087CC0
0x180087ca8  mov     r8, rdi; lpSubKey
0x180087cab  mov     rdx, r13; hKey
0x180087cae  lea     rcx, [rsp+22E0h+var_2280]; this
0x180087cb3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180087cb8  test    eax, eax
0x180087cba  jnz     loc_180087F59
0x180087cc0  mov     rdx, rdi; unsigned __int16 *
0x180087cc3  mov     rcx, rsi; this
0x180087cc6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087ccb  mov     ebx, eax
0x180087ccd  test    eax, eax
0x180087ccf  js      loc_180087F15
0x180087cd5  cmp     word ptr [rdi], 3Dh ; '='
0x180087cd9  jnz     short loc_180087CF8
0x180087cdb  mov     r9, rdi; unsigned __int16 *
0x180087cde  xor     r8d, r8d; unsigned __int16 *
0x180087ce1  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180087ce6  mov     rcx, rsi; this
0x180087ce9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180087cee  mov     ebx, eax
0x180087cf0  test    eax, eax
0x180087cf2  js      loc_180087F15
0x180087cf8  cmp     word ptr [rdi], 7Bh ; '{'
0x180087cfc  jnz     loc_180087A31
0x180087d02  or      rax, 0FFFFFFFFFFFFFFFFh
0x180087d06  inc     rax
0x180087d09  cmp     [rdi+rax*2], r14w
0x180087d0e  jnz     short loc_180087D06
0x180087d10  cmp     rax, 1
0x180087d14  jnz     loc_180087A31
0x180087d1a  mov     dword ptr [rsp+22E0h+var_22C0], r14d; int
0x180087d1f  mov     r9d, r15d; int
0x180087d22  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180087d27  mov     rdx, rdi; unsigned __int16 *
0x180087d2a  mov     rcx, rsi; this
0x180087d2d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180087d32  mov     ebx, eax
0x180087d34  test    eax, eax
0x180087d36  js      loc_180087F15
0x180087d3c  mov     rdx, rdi
0x180087d3f  mov     rcx, rsi
0x180087d42  jmp     loc_180087A22
0x180087d47  cmp     [rbp+21E0h+arg_20], r14d
0x180087d4e  jnz     short loc_180087D6B
0x180087d50  mov     r9d, 20019h; unsigned int
0x180087d56  mov     r8, rdi; lpSubKey
0x180087d59  mov     rdx, r13; hKey
0x180087d5c  lea     rcx, [rsp+22E0h+var_2280]; this
0x180087d61  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180087d66  mov     r14d, eax
0x180087d69  jmp     short loc_180087D71
0x180087d6b  mov     r14d, 2
0x180087d71  mov     r15d, 1
0x180087d77  test    r14d, r14d
0x180087d7a  cmovz   r15d, [rbp+21E0h+arg_20]
0x180087d82  or      r9, 0FFFFFFFFFFFFFFFFh
0x180087d86  mov     r8, rdi
0x180087d89  mov     edx, 104h
0x180087d8e  lea     rcx, [rbp+21E0h+var_2260]
0x180087d92  call    cs:__imp__o_wcsncpy_s
0x180087d98  mov     ecx, eax; int
0x180087d9a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180087d9f  mov     rdx, rdi; unsigned __int16 *
0x180087da2  mov     rcx, rsi; this
0x180087da5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087daa  mov     ebx, eax
0x180087dac  test    eax, eax
0x180087dae  js      loc_180087F15
0x180087db4  mov     rdx, rdi; unsigned __int16 *
0x180087db7  mov     rcx, rsi; this
0x180087dba  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180087dbf  mov     ebx, eax
0x180087dc1  xor     ecx, ecx
0x180087dc3  test    eax, eax
0x180087dc5  js      loc_180087F15
0x180087dcb  cmp     word ptr [rdi], 7Bh ; '{'
0x180087dcf  jnz     short loc_180087E20
0x180087dd1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180087dd5  inc     rax
0x180087dd8  cmp     [rdi+rax*2], cx
0x180087ddc  jnz     short loc_180087DD5
0x180087dde  cmp     rax, 1
0x180087de2  jnz     short loc_180087E20
0x180087de4  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x180087de9  xor     r9d, r9d; int
0x180087dec  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180087df1  mov     rdx, rdi; unsigned __int16 *
0x180087df4  mov     rcx, rsi; this
0x180087df7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180087dfc  mov     ebx, eax
0x180087dfe  test    eax, eax
0x180087e00  jns     short loc_180087E0B
0x180087e02  test    r15d, r15d
0x180087e05  jz      loc_180087F15
0x180087e0b  mov     rdx, rdi; unsigned __int16 *
0x180087e0e  mov     rcx, rsi; this
0x180087e11  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180087e16  mov     ebx, eax
0x180087e18  test    eax, eax
0x180087e1a  js      loc_180087F15
0x180087e20  cmp     r14d, 2
0x180087e24  mov     r15d, [rsp+22E0h+var_22A0]
0x180087e29  jz      loc_180087A31
0x180087e2f  test    r14d, r14d
0x180087e32  jz      short loc_180087E53
0x180087e34  xor     r12d, r12d
0x180087e37  cmp     [rbp+21E0h+arg_20], r12d
0x180087e3e  jnz     loc_180087A34
0x180087e44  mov     ecx, r14d; unsigned int
0x180087e47  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180087e4c  mov     ebx, eax
0x180087e4e  jmp     loc_180087F15
0x180087e53  xor     r14d, r14d
0x180087e56  cmp     [rbp+21E0h+arg_20], r14d
0x180087e5d  jz      short loc_180087E9D
0x180087e5f  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x180087e64  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
  ... truncated ...
```
