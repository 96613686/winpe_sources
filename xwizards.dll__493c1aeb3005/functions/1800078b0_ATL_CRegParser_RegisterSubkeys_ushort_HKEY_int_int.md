# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800078b0`
- end: `0x180007e89`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000758c`
- `0x1800078b0`

## callees

- `0x180003b8c`
- `0x180004324`
- `0x180004394`
- `0x1800044a8`
- `0x1800045c4`
- `0x180005c2c`
- `0x1800067f8`
- `0x180006b10`
- `0x180006c70`
- `0x180007478`
- `0x1800078b0`
- `0x180008488`
- `0x180008558`
- `0x180032a30`
- `0x180032af0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180007cb6`
- `msvcrt!wcsncpy_s` at `0x180007cb6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007bb7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007bb7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180007b05`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180007b05`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000792b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000793e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007a12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007a41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000792b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000793e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007a12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007a41`

## string_xrefs

- `0x180007934`: `ForceRemove`
- `0x180007a08`: `NoRemove`
- `0x180007921`: `Delete`

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
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
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
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
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
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
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
            if ( ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, Destination);
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
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
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
0x1800078b0  push    rbp
0x1800078b2  push    rbx
0x1800078b3  push    rsi
0x1800078b4  push    rdi
0x1800078b5  push    r12
0x1800078b7  push    r13
0x1800078b9  push    r14
0x1800078bb  push    r15
0x1800078bd  lea     rbp, [rsp-21C8h]
0x1800078c5  mov     eax, 22C8h
0x1800078ca  call    _alloca_probe
0x1800078cf  sub     rsp, rax
0x1800078d2  mov     rax, cs:__security_cookie
0x1800078d9  xor     rax, rsp
0x1800078dc  mov     [rbp+2200h+var_50], rax
0x1800078e3  mov     r15d, r9d
0x1800078e6  mov     [rsp+2300h+var_22B0], r9d
0x1800078eb  mov     r13, r8
0x1800078ee  mov     rdi, rdx
0x1800078f1  mov     rsi, rcx
0x1800078f4  xor     r14d, r14d
0x1800078f7  mov     [rsp+2300h+var_2290], r14
0x1800078fc  mov     [rsp+2300h+var_2288], r14
0x180007901  mov     [rbp+2200h+var_2280], r14
0x180007905  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000790a  test    eax, eax
0x18000790c  mov     ebx, eax
0x18000790e  js      loc_180007E3D
0x180007914  xor     r12d, r12d
0x180007917  cmp     word ptr [rdi], 7Dh ; '}'
0x18000791b  jz      loc_180007E3D
0x180007921  lea     rdx, String2; "Delete"
0x180007928  mov     rcx, rdi; lpString1
0x18000792b  call    cs:__imp_lstrcmpiW
0x180007931  mov     r14d, eax
0x180007934  lea     rdx, aForceremove; "ForceRemove"
0x18000793b  mov     rcx, rdi; lpString1
0x18000793e  call    cs:__imp_lstrcmpiW
0x180007944  test    eax, eax
0x180007946  jz      short loc_180007951
0x180007948  test    r14d, r14d
0x18000794b  jnz     loc_180007A02
0x180007951  mov     rdx, rdi; unsigned __int16 *
0x180007954  mov     rcx, rsi; this
0x180007957  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000795c  mov     ebx, eax
0x18000795e  test    eax, eax
0x180007960  js      loc_180007E3D
0x180007966  test    r15d, r15d
0x180007969  jz      loc_180007A02
0x18000796f  mov     [rsp+2300h+hKey], r12
0x180007974  mov     [rsp+2300h+var_22A0], r12
0x180007979  mov     [rsp+2300h+var_2298], r12
0x18000797e  mov     edx, 5Ch ; '\'; unsigned __int16
0x180007983  mov     rcx, rdi; lpsz
0x180007986  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000798b  test    rax, rax
0x18000798e  jnz     loc_180007E2E
0x180007994  mov     rdx, rdi; unsigned __int16 *
0x180007997  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000799c  test    eax, eax
0x18000799e  jz      short loc_1800079B7
0x1800079a0  mov     [rsp+2300h+hKey], r13
0x1800079a5  mov     rdx, rdi; unsigned __int16 *
0x1800079a8  lea     rcx, [rsp+2300h+hKey]; this
0x1800079ad  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800079b2  mov     [rsp+2300h+hKey], r12
0x1800079b7  test    r14d, r14d
0x1800079ba  jnz     short loc_1800079F8
0x1800079bc  mov     rdx, rdi; unsigned __int16 *
0x1800079bf  mov     rcx, rsi; this
0x1800079c2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800079c7  mov     ebx, eax
0x1800079c9  xor     r14d, r14d
0x1800079cc  test    eax, eax
0x1800079ce  js      loc_180007E75
0x1800079d4  mov     rdx, rdi; unsigned __int16 *
0x1800079d7  mov     rcx, rsi; this
0x1800079da  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800079df  mov     ebx, eax
0x1800079e1  test    eax, eax
0x1800079e3  lea     rcx, [rsp+2300h+hKey]; this
0x1800079e8  js      loc_180007E7A
0x1800079ee  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800079f3  jmp     loc_180007C1C
0x1800079f8  lea     rcx, [rsp+2300h+hKey]; this
0x1800079fd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007a02  mov     r12d, 1
0x180007a08  lea     rdx, aNoremove; "NoRemove"
0x180007a0f  mov     rcx, rdi; lpString1
0x180007a12  call    cs:__imp_lstrcmpiW
0x180007a18  xor     r14d, r14d
0x180007a1b  test    eax, eax
0x180007a1d  jnz     short loc_180007A37
0x180007a1f  mov     r12d, r14d
0x180007a22  mov     rdx, rdi; unsigned __int16 *
0x180007a25  mov     rcx, rsi; this
0x180007a28  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007a2d  mov     ebx, eax
0x180007a2f  test    eax, eax
0x180007a31  js      loc_180007E3D
0x180007a37  lea     rdx, aVal; "Val"
0x180007a3e  mov     rcx, rdi; lpString1
0x180007a41  call    cs:__imp_lstrcmpiW
0x180007a47  test    eax, eax
0x180007a49  jnz     loc_180007B30
0x180007a4f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180007a56  mov     rcx, rsi; this
0x180007a59  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007a5e  mov     ebx, eax
0x180007a60  test    eax, eax
0x180007a62  js      loc_180007E3D
0x180007a68  mov     rdx, rdi; unsigned __int16 *
0x180007a6b  mov     rcx, rsi; this
0x180007a6e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007a73  mov     ebx, eax
0x180007a75  test    eax, eax
0x180007a77  js      loc_180007E3D
0x180007a7d  cmp     word ptr [rdi], 3Dh ; '='
0x180007a81  jnz     loc_180007E38
0x180007a87  test    r15d, r15d
0x180007a8a  jz      short loc_180007ABE
0x180007a8c  mov     [rsp+2300h+var_22A0], r14
0x180007a91  mov     [rsp+2300h+var_2298], r14
0x180007a96  mov     [rsp+2300h+hKey], r13
0x180007a9b  mov     r9, rdi; unsigned __int16 *
0x180007a9e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180007aa5  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180007aaa  mov     rcx, rsi; this
0x180007aad  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007ab2  mov     ebx, eax
0x180007ab4  mov     [rsp+2300h+hKey], r14
0x180007ab9  jmp     loc_1800079E1
0x180007abe  cmp     [rbp+2200h+arg_20], r14d
0x180007ac5  jnz     short loc_180007B20
0x180007ac7  test    r12d, r12d
0x180007aca  jz      short loc_180007B20
0x180007acc  mov     [rsp+2300h+hKey], r14
0x180007ad1  mov     [rsp+2300h+var_22A0], r14
0x180007ad6  mov     [rsp+2300h+var_2298], r14
0x180007adb  mov     r9d, 20006h; unsigned int
0x180007ae1  xor     r8d, r8d; lpSubKey
0x180007ae4  mov     rdx, r13; hKey
0x180007ae7  lea     rcx, [rsp+2300h+hKey]; this
0x180007aec  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007af1  test    eax, eax
0x180007af3  jnz     loc_180007E6C
0x180007af9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180007b00  mov     rcx, [rsp+2300h+hKey]; hKey
0x180007b05  call    cs:__imp_RegDeleteValueW
0x180007b0b  test    eax, 0FFFFFFFDh
0x180007b10  jnz     loc_180007E6C
0x180007b16  lea     rcx, [rsp+2300h+hKey]; this
0x180007b1b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007b20  mov     rdx, rdi; unsigned __int16 *
0x180007b23  mov     rcx, rsi; this
0x180007b26  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007b2b  jmp     loc_18000790A
0x180007b30  mov     edx, 5Ch ; '\'; unsigned __int16
0x180007b35  mov     rcx, rdi; lpsz
0x180007b38  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180007b3d  test    rax, rax
0x180007b40  jnz     loc_180007E38
0x180007b46  test    r15d, r15d
0x180007b49  jz      loc_180007C6B
0x180007b4f  mov     ebx, 2001Fh
0x180007b54  mov     r9d, ebx; unsigned int
0x180007b57  mov     r8, rdi; lpSubKey
0x180007b5a  mov     rdx, r13; hKey
0x180007b5d  lea     rcx, [rsp+2300h+var_2290]; this
0x180007b62  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007b67  test    eax, eax
0x180007b69  jz      short loc_180007BE4
0x180007b6b  lea     r9d, [rbx-6]; unsigned int
0x180007b6f  mov     r8, rdi; lpSubKey
0x180007b72  mov     rdx, r13; hKey
0x180007b75  lea     rcx, [rsp+2300h+var_2290]; this
0x180007b7a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007b7f  test    eax, eax
0x180007b81  jz      short loc_180007BE4
0x180007b83  mov     [rbp+2200h+dwDisposition], r14d
0x180007b87  mov     [rbp+2200h+var_2270], r14
0x180007b8b  lea     rax, [rbp+2200h+dwDisposition]
0x180007b8f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180007b94  lea     rax, [rbp+2200h+var_2270]
0x180007b98  mov     [rsp+2300h+phkResult], rax; phkResult
0x180007b9d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180007ba2  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180007ba6  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x180007bab  xor     r9d, r9d; lpClass
0x180007bae  xor     r8d, r8d; Reserved
0x180007bb1  mov     rdx, rdi; lpSubKey
0x180007bb4  mov     rcx, r13; hKey
0x180007bb7  call    cs:__imp_RegCreateKeyExW
0x180007bbd  mov     ecx, eax
0x180007bbf  test    eax, eax
0x180007bc1  jnz     loc_180007D6B
0x180007bc7  lea     rcx, [rsp+2300h+var_2290]; this
0x180007bcc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007bd1  mov     ecx, eax
0x180007bd3  mov     rax, [rbp+2200h+var_2270]
0x180007bd7  mov     [rsp+2300h+var_2290], rax
0x180007bdc  test    ecx, ecx
0x180007bde  jnz     loc_180007D6B
0x180007be4  mov     rdx, rdi; unsigned __int16 *
0x180007be7  mov     rcx, rsi; this
0x180007bea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007bef  mov     ebx, eax
0x180007bf1  test    eax, eax
0x180007bf3  js      loc_180007E3D
0x180007bf9  cmp     word ptr [rdi], 3Dh ; '='
0x180007bfd  jnz     short loc_180007C1C
0x180007bff  mov     r9, rdi; unsigned __int16 *
0x180007c02  xor     r8d, r8d; unsigned __int16 *
0x180007c05  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180007c0a  mov     rcx, rsi; this
0x180007c0d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007c12  mov     ebx, eax
0x180007c14  test    eax, eax
0x180007c16  js      loc_180007E3D
0x180007c1c  cmp     word ptr [rdi], 7Bh ; '{'
0x180007c20  jnz     loc_180007914
0x180007c26  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007c2a  inc     rax
0x180007c2d  cmp     [rdi+rax*2], r14w
0x180007c32  jnz     short loc_180007C2A
0x180007c34  cmp     rax, 1
0x180007c38  jnz     loc_180007914
0x180007c3e  mov     [rsp+2300h+dwOptions], r14d; int
0x180007c43  mov     r9d, r15d; int
0x180007c46  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180007c4b  mov     rdx, rdi; unsigned __int16 *
0x180007c4e  mov     rcx, rsi; this
0x180007c51  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007c56  mov     ebx, eax
0x180007c58  test    eax, eax
0x180007c5a  js      loc_180007E3D
0x180007c60  mov     rdx, rdi
0x180007c63  mov     rcx, rsi
0x180007c66  jmp     loc_180007905
0x180007c6b  cmp     [rbp+2200h+arg_20], r14d
0x180007c72  jnz     short loc_180007C8F
0x180007c74  mov     r9d, 20019h; unsigned int
0x180007c7a  mov     r8, rdi; lpSubKey
0x180007c7d  mov     rdx, r13; hKey
0x180007c80  lea     rcx, [rsp+2300h+var_2290]; this
0x180007c85  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007c8a  mov     r14d, eax
0x180007c8d  jmp     short loc_180007C95
0x180007c8f  mov     r14d, 2
0x180007c95  mov     r15d, 1
0x180007c9b  test    r14d, r14d
0x180007c9e  cmovz   r15d, [rbp+2200h+arg_20]
0x180007ca6  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180007caa  mov     r8, rdi; Source
0x180007cad  mov     edx, 104h; SizeInWords
0x180007cb2  lea     rcx, [rbp+2200h+Destination]; Destination
0x180007cb6  call    cs:__imp_wcsncpy_s
0x180007cbc  mov     ecx, eax; int
0x180007cbe  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007cc3  mov     rdx, rdi; unsigned __int16 *
0x180007cc6  mov     rcx, rsi; this
0x180007cc9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007cce  mov     ebx, eax
0x180007cd0  test    eax, eax
0x180007cd2  js      loc_180007E3D
0x180007cd8  mov     rdx, rdi; unsigned __int16 *
0x180007cdb  mov     rcx, rsi; this
0x180007cde  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007ce3  mov     ebx, eax
0x180007ce5  xor     ecx, ecx
0x180007ce7  test    eax, eax
0x180007ce9  js      loc_180007E3D
0x180007cef  cmp     word ptr [rdi], 7Bh ; '{'
0x180007cf3  jnz     short loc_180007D44
0x180007cf5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007cf9  inc     rax
0x180007cfc  cmp     [rdi+rax*2], cx
0x180007d00  jnz     short loc_180007CF9
0x180007d02  cmp     rax, 1
0x180007d06  jnz     short loc_180007D44
0x180007d08  mov     [rsp+2300h+dwOptions], r15d; int
0x180007d0d  xor     r9d, r9d; int
0x180007d10  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180007d15  mov     rdx, rdi; unsigned __int16 *
0x180007d18  mov     rcx, rsi; this
0x180007d1b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007d20  mov     ebx, eax
0x180007d22  test    eax, eax
0x180007d24  jns     short loc_180007D2F
0x180007d26  test    r15d, r15d
0x180007d29  jz      loc_180007E3D
0x180007d2f  mov     rdx, rdi; unsigned __int16 *
0x180007d32  mov     rcx, rsi; this
0x180007d35  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007d3a  mov     ebx, eax
0x180007d3c  test    eax, eax
0x180007d3e  js      loc_180007E3D
0x180007d44  cmp     r14d, 2
0x180007d48  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
