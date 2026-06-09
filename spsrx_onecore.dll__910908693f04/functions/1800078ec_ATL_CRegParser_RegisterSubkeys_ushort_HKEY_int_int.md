# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800078ec`
- end: `0x180007e9f`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1459`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800074dc`
- `0x1800078ec`

## callees

- `0x180002570`
- `0x180003150`
- `0x1800058ec`
- `0x180005e28`
- `0x180006510`
- `0x180006580`
- `0x18000690c`
- `0x180006ad4`
- `0x180006b00`
- `0x180006cac`
- `0x180006e88`
- `0x180006f50`
- `0x1800070c8`
- `0x1800073c8`
- `0x1800078ec`
- `0x180007ff0`
- `0x1800080c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180007ce5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180007ce5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180007b75`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180007b75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000798a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000799d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007a6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007a99`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000798a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000799d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007a6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007a99`

## string_xrefs

- `0x180007993`: `ForceRemove`
- `0x180007a60`: `NoRemove`
- `0x180007980`: `Delete`

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
  int v12; // r14d
  ATL::CRegParser *v13; // rcx
  int v14; // r12d
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r14d
  unsigned int v25; // [rsp+20h] [rbp-E0h]
  unsigned int v26; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v27; // [rsp+30h] [rbp-D0h]
  unsigned int *v28; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  HKEY v33[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v34[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v33, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_4;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_4;
      v12 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v12 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_4;
        if ( v5 )
        {
          hKey = 0;
          v31 = 0;
          v32 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            ATL::CRegKey::~CRegKey((ATL::CRegKey *)v33);
            return 2147614729LL;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v13, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v12 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_80;
            v10 = ATL::CRegParser::SkipAssignment(v8, v7);
            if ( v10 < 0 )
              goto LABEL_80;
LABEL_16:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_41;
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
          goto LABEL_4;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_82;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x20019u) )
          {
            v17 = ATL::CRegKey::Create((ATL::CRegKey *)v33, a3, v7, v16, v25, v26, v27, v28);
            if ( v17 )
            {
LABEL_81:
              v10 = ATL::AtlHresultFromWin32(v17);
              goto LABEL_83;
            }
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_4;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v33, 0, v7);
          if ( v10 < 0 )
            goto LABEL_4;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v33[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_4;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v19 = 2;
        else
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        v21 = _o_wcsncpy_s(v34, 260, v7, -1);
        ATL::AtlCrtErrorCheck(v21);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_4;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v22 = 0;
        if ( v10 < 0 )
          goto LABEL_4;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v33[0], 0, v20);
            if ( v10 < 0 && !v20 )
              goto LABEL_4;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_4;
          }
        }
        if ( v19 != 2 )
        {
          if ( v19 )
          {
            if ( !a5 )
            {
              v10 = ATL::AtlHresultFromWin32(v19);
LABEL_4:
              ATL::CRegKey::Close((ATL::CRegKey *)v33);
              return (unsigned int)v10;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v33[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v33, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v33[0]);
            v17 = ATL::CRegKey::Close((ATL::CRegKey *)v33);
            if ( v17 )
              goto LABEL_81;
            if ( v14 && !HasSubKeys )
            {
              v31 = 0;
              v32 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
              hKey = 0;
              if ( v15 )
                goto LABEL_79;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
        v5 = a4;
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_4;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_4;
    if ( *v7 == 61 )
    {
      if ( v5 )
      {
        v31 = 0;
        v32 = 0;
        hKey = a3;
        v10 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
        hKey = 0;
        if ( v10 < 0 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          goto LABEL_83;
        }
        goto LABEL_16;
      }
      if ( !a5 && v14 )
      {
        hKey = 0;
        v31 = 0;
        v32 = 0;
        v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
        if ( v15 || (v15 = RegDeleteValueW(hKey, ValueName), (v15 & 0xFFFFFFFD) != 0) )
        {
LABEL_79:
          v10 = ATL::AtlHresultFromWin32(v15);
LABEL_80:
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          goto LABEL_4;
        }
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      }
      Token = ATL::CRegParser::SkipAssignment(v8, v7);
      continue;
    }
    break;
  }
LABEL_82:
  v10 = -2147352567;
LABEL_83:
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)v33);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800078ec  push    rbp
0x1800078ee  push    rbx
0x1800078ef  push    rsi
0x1800078f0  push    rdi
0x1800078f1  push    r12
0x1800078f3  push    r13
0x1800078f5  push    r14
0x1800078f7  push    r15
0x1800078f9  lea     rbp, [rsp-21A8h]
0x180007901  mov     eax, 22A8h
0x180007906  call    _alloca_probe
0x18000790b  sub     rsp, rax
0x18000790e  mov     rax, cs:__security_cookie
0x180007915  xor     rax, rsp
0x180007918  mov     [rbp+21E0h+var_50], rax
0x18000791f  mov     r15d, r9d
0x180007922  mov     [rsp+22E0h+var_22A0], r9d
0x180007927  mov     r13, r8
0x18000792a  mov     rdi, rdx
0x18000792d  mov     rsi, rcx
0x180007930  xor     r12d, r12d
0x180007933  mov     [rsp+22E0h+var_2280], r12
0x180007938  mov     [rsp+22E0h+var_2278], r12
0x18000793d  mov     [rsp+22E0h+var_2270], r12
0x180007942  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007947  mov     ebx, eax
0x180007949  test    eax, eax
0x18000794b  jns     loc_180007DE0
0x180007951  lea     rcx, [rsp+22E0h+var_2280]; this
0x180007956  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000795b  mov     eax, ebx
0x18000795d  mov     rcx, [rbp+21E0h+var_50]
0x180007964  xor     rcx, rsp; StackCookie
0x180007967  call    __security_check_cookie
0x18000796c  add     rsp, 22A8h
0x180007973  pop     r15
0x180007975  pop     r14
0x180007977  pop     r13
0x180007979  pop     r12
0x18000797b  pop     rdi
0x18000797c  pop     rsi
0x18000797d  pop     rbx
0x18000797e  pop     rbp
0x18000797f  retn
0x180007980  lea     rdx, String2; "Delete"
0x180007987  mov     rcx, rdi; lpString1
0x18000798a  call    cs:__imp_lstrcmpiW
0x180007990  mov     r14d, eax
0x180007993  lea     rdx, aForceremove; "ForceRemove"
0x18000799a  mov     rcx, rdi; lpString1
0x18000799d  call    cs:__imp_lstrcmpiW
0x1800079a3  test    eax, eax
0x1800079a5  jz      short loc_1800079B0
0x1800079a7  test    r14d, r14d
0x1800079aa  jnz     loc_180007A5A
0x1800079b0  mov     rdx, rdi; unsigned __int16 *
0x1800079b3  mov     rcx, rsi; this
0x1800079b6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800079bb  mov     ebx, eax
0x1800079bd  test    eax, eax
0x1800079bf  js      short loc_180007951
0x1800079c1  test    r15d, r15d
0x1800079c4  jz      loc_180007A5A
0x1800079ca  mov     [rsp+22E0h+hKey], r12
0x1800079cf  mov     [rsp+22E0h+var_2290], r12
0x1800079d4  mov     [rsp+22E0h+var_2288], r12
0x1800079d9  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800079de  mov     rcx, rdi; lpsz
0x1800079e1  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800079e6  test    rax, rax
0x1800079e9  jnz     loc_180007E49
0x1800079ef  mov     rdx, rdi; unsigned __int16 *
0x1800079f2  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800079f7  test    eax, eax
0x1800079f9  jz      short loc_180007A12
0x1800079fb  mov     [rsp+22E0h+hKey], r13
0x180007a00  mov     rdx, rdi; unsigned __int16 *
0x180007a03  lea     rcx, [rsp+22E0h+hKey]; this
0x180007a08  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007a0d  mov     [rsp+22E0h+hKey], r12
0x180007a12  test    r14d, r14d
0x180007a15  jnz     short loc_180007A50
0x180007a17  mov     rdx, rdi; unsigned __int16 *
0x180007a1a  mov     rcx, rsi; this
0x180007a1d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007a22  mov     ebx, eax
0x180007a24  test    eax, eax
0x180007a26  js      loc_180007E71
0x180007a2c  mov     rdx, rdi; unsigned __int16 *
0x180007a2f  mov     rcx, rsi; this
0x180007a32  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007a37  mov     ebx, eax
0x180007a39  lea     rcx, [rsp+22E0h+hKey]; this
0x180007a3e  test    eax, eax
0x180007a40  js      loc_180007E76
0x180007a46  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007a4b  jmp     loc_180007C4B
0x180007a50  lea     rcx, [rsp+22E0h+hKey]; this
0x180007a55  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007a5a  mov     r12d, 1
0x180007a60  lea     rdx, aNoremove; "NoRemove"
0x180007a67  mov     rcx, rdi; lpString1
0x180007a6a  call    cs:__imp_lstrcmpiW
0x180007a70  xor     r14d, r14d
0x180007a73  test    eax, eax
0x180007a75  jnz     short loc_180007A8F
0x180007a77  mov     r12d, r14d
0x180007a7a  mov     rdx, rdi; unsigned __int16 *
0x180007a7d  mov     rcx, rsi; this
0x180007a80  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007a85  mov     ebx, eax
0x180007a87  test    eax, eax
0x180007a89  js      loc_180007951
0x180007a8f  lea     rdx, aVal; "Val"
0x180007a96  mov     rcx, rdi; lpString1
0x180007a99  call    cs:__imp_lstrcmpiW
0x180007a9f  test    eax, eax
0x180007aa1  jnz     loc_180007BA5
0x180007aa7  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180007aae  mov     rcx, rsi; this
0x180007ab1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007ab6  mov     ebx, eax
0x180007ab8  test    eax, eax
0x180007aba  js      loc_180007951
0x180007ac0  mov     rdx, rdi; unsigned __int16 *
0x180007ac3  mov     rcx, rsi; this
0x180007ac6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007acb  mov     ebx, eax
0x180007acd  test    eax, eax
0x180007acf  js      loc_180007951
0x180007ad5  cmp     word ptr [rdi], 3Dh ; '='
0x180007ad9  jnz     loc_180007E8B
0x180007adf  test    r15d, r15d
0x180007ae2  jz      short loc_180007B2B
0x180007ae4  xor     r12d, r12d
0x180007ae7  mov     [rsp+22E0h+var_2290], r12
0x180007aec  mov     [rsp+22E0h+var_2288], r12
0x180007af1  mov     [rsp+22E0h+hKey], r13
0x180007af6  mov     r9, rdi; unsigned __int16 *
0x180007af9  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180007b00  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180007b05  mov     rcx, rsi; this
0x180007b08  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007b0d  mov     ebx, eax
0x180007b0f  mov     [rsp+22E0h+hKey], r12
0x180007b14  lea     rcx, [rsp+22E0h+hKey]; this
0x180007b19  test    eax, eax
0x180007b1b  jns     loc_180007A46
0x180007b21  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007b26  jmp     loc_180007E90
0x180007b2b  cmp     [rbp+21E0h+arg_20], r14d
0x180007b32  jnz     short loc_180007B92
0x180007b34  test    r12d, r12d
0x180007b37  jz      short loc_180007B92
0x180007b39  xor     r12d, r12d
0x180007b3c  mov     [rsp+22E0h+hKey], r12
0x180007b41  mov     [rsp+22E0h+var_2290], r12
0x180007b46  mov     [rsp+22E0h+var_2288], r12
0x180007b4b  mov     r9d, 20006h; unsigned int
0x180007b51  xor     r8d, r8d; lpSubKey
0x180007b54  mov     rdx, r13; hKey
0x180007b57  lea     rcx, [rsp+22E0h+hKey]; this
0x180007b5c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007b61  test    eax, eax
0x180007b63  jnz     loc_180007E68
0x180007b69  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180007b70  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180007b75  call    cs:__imp_RegDeleteValueW
0x180007b7b  test    eax, 0FFFFFFFDh
0x180007b80  jnz     loc_180007E68
0x180007b86  lea     rcx, [rsp+22E0h+hKey]; this
0x180007b8b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007b90  jmp     short loc_180007B95
0x180007b92  xor     r12d, r12d
0x180007b95  mov     rdx, rdi; unsigned __int16 *
0x180007b98  mov     rcx, rsi; this
0x180007b9b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007ba0  jmp     loc_180007947
0x180007ba5  mov     edx, 5Ch ; '\'; unsigned __int16
0x180007baa  mov     rcx, rdi; lpsz
0x180007bad  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180007bb2  test    rax, rax
0x180007bb5  jnz     loc_180007E8B
0x180007bbb  test    r15d, r15d
0x180007bbe  jz      loc_180007C9A
0x180007bc4  mov     r9d, 2001Fh; unsigned int
0x180007bca  mov     r8, rdi; lpSubKey
0x180007bcd  mov     rdx, r13; hKey
0x180007bd0  lea     rcx, [rsp+22E0h+var_2280]; this
0x180007bd5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007bda  xor     r12d, r12d
0x180007bdd  test    eax, eax
0x180007bdf  jz      short loc_180007C13
0x180007be1  mov     r9d, 20019h; unsigned int
0x180007be7  mov     r8, rdi; lpSubKey
0x180007bea  mov     rdx, r13; hKey
0x180007bed  lea     rcx, [rsp+22E0h+var_2280]; this
0x180007bf2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007bf7  test    eax, eax
0x180007bf9  jz      short loc_180007C13
0x180007bfb  mov     r8, rdi; lpSubKey
0x180007bfe  mov     rdx, r13; hKey
0x180007c01  lea     rcx, [rsp+22E0h+var_2280]; this
0x180007c06  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180007c0b  test    eax, eax
0x180007c0d  jnz     loc_180007E80
0x180007c13  mov     rdx, rdi; unsigned __int16 *
0x180007c16  mov     rcx, rsi; this
0x180007c19  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007c1e  mov     ebx, eax
0x180007c20  test    eax, eax
0x180007c22  js      loc_180007951
0x180007c28  cmp     word ptr [rdi], 3Dh ; '='
0x180007c2c  jnz     short loc_180007C4B
0x180007c2e  mov     r9, rdi; unsigned __int16 *
0x180007c31  xor     r8d, r8d; unsigned __int16 *
0x180007c34  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180007c39  mov     rcx, rsi; this
0x180007c3c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007c41  mov     ebx, eax
0x180007c43  test    eax, eax
0x180007c45  js      loc_180007951
0x180007c4b  cmp     word ptr [rdi], 7Bh ; '{'
0x180007c4f  jnz     loc_180007DE0
0x180007c55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007c59  inc     rax
0x180007c5c  cmp     [rdi+rax*2], r12w
0x180007c61  jnz     short loc_180007C59
0x180007c63  cmp     rax, 1
0x180007c67  jnz     loc_180007DE0
0x180007c6d  mov     [rsp+22E0h+var_22C0], r12d; int
0x180007c72  mov     r9d, r15d; int
0x180007c75  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180007c7a  mov     rdx, rdi; unsigned __int16 *
0x180007c7d  mov     rcx, rsi; this
0x180007c80  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007c85  mov     ebx, eax
0x180007c87  test    eax, eax
0x180007c89  js      loc_180007951
0x180007c8f  mov     rdx, rdi
0x180007c92  mov     rcx, rsi
0x180007c95  jmp     loc_180007942
0x180007c9a  cmp     [rbp+21E0h+arg_20], r14d
0x180007ca1  jnz     short loc_180007CBE
0x180007ca3  mov     r9d, 20019h; unsigned int
0x180007ca9  mov     r8, rdi; lpSubKey
0x180007cac  mov     rdx, r13; hKey
0x180007caf  lea     rcx, [rsp+22E0h+var_2280]; this
0x180007cb4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007cb9  mov     r14d, eax
0x180007cbc  jmp     short loc_180007CC4
0x180007cbe  mov     r14d, 2
0x180007cc4  mov     r15d, 1
0x180007cca  test    r14d, r14d
0x180007ccd  cmovz   r15d, [rbp+21E0h+arg_20]
0x180007cd5  or      r9, 0FFFFFFFFFFFFFFFFh
0x180007cd9  mov     r8, rdi
0x180007cdc  mov     edx, 104h
0x180007ce1  lea     rcx, [rbp+21E0h+var_2260]
0x180007ce5  call    cs:__imp__o_wcsncpy_s
0x180007ceb  mov     ecx, eax; int
0x180007ced  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007cf2  mov     rdx, rdi; unsigned __int16 *
0x180007cf5  mov     rcx, rsi; this
0x180007cf8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007cfd  mov     ebx, eax
0x180007cff  test    eax, eax
0x180007d01  js      loc_180007951
0x180007d07  mov     rdx, rdi; unsigned __int16 *
0x180007d0a  mov     rcx, rsi; this
0x180007d0d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007d12  mov     ebx, eax
0x180007d14  xor     ecx, ecx; this
0x180007d16  test    eax, eax
0x180007d18  js      loc_180007951
0x180007d1e  cmp     word ptr [rdi], 7Bh ; '{'
0x180007d22  jnz     short loc_180007D78
0x180007d24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007d28  inc     rax
0x180007d2b  cmp     [rdi+rax*2], cx
0x180007d2f  jnz     short loc_180007D28
0x180007d31  cmp     rax, 1
0x180007d35  jnz     short loc_180007D78
0x180007d37  mov     [rsp+22E0h+var_22C0], r15d; int
0x180007d3c  xor     r9d, r9d; int
0x180007d3f  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180007d44  mov     rdx, rdi; unsigned __int16 *
0x180007d47  mov     rcx, rsi; this
0x180007d4a  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007d4f  mov     ebx, eax
0x180007d51  test    eax, eax
0x180007d53  jns     short loc_180007D5E
0x180007d55  test    r15d, r15d
0x180007d58  jz      loc_180007951
0x180007d5e  mov     rdx, rdi; unsigned __int16 *
0x180007d61  mov     rcx, rsi; this
0x180007d64  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007d69  mov     ebx, eax
0x180007d6b  xor     r15d, r15d
0x180007d6e  test    eax, eax
  ... truncated ...
```
