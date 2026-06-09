# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18001ef4c`
- end: `0x18001f4f3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1447`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18001ec2c`
- `0x18001ef4c`

## callees

- `0x180011530`
- `0x180011a80`
- `0x180015788`
- `0x18001a0d0`
- `0x18001d43c`
- `0x18001da2c`
- `0x18001da44`
- `0x18001db54`
- `0x18001e32c`
- `0x18001e448`
- `0x18001e500`
- `0x18001eb18`
- `0x18001ef4c`
- `0x18001f908`
- `0x18001f9d8`
- `0x180053560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001f320`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001f320`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f1a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f1a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001efc8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001efdb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001f0af`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001f0de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001efc8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001efdb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001f0af`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001f0de`

## string_xrefs

- `0x18001efd1`: `ForceRemove`
- `0x18001f0a5`: `NoRemove`
- `0x18001efbe`: `Delete`

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
  int v20; // eax
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
        if ( !ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu)
          || !ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u)
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
          if ( ATL::CRegParser::CanForceRemoveKey(v21, v31) && v14 )
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
0x18001ef4c  push    rbp
0x18001ef4e  push    rbx
0x18001ef4f  push    rsi
0x18001ef50  push    rdi
0x18001ef51  push    r12
0x18001ef53  push    r13
0x18001ef55  push    r14
0x18001ef57  push    r15
0x18001ef59  lea     rbp, [rsp-21A8h]
0x18001ef61  mov     eax, 22A8h
0x18001ef66  call    _alloca_probe
0x18001ef6b  sub     rsp, rax
0x18001ef6e  mov     rax, cs:__security_cookie
0x18001ef75  xor     rax, rsp
0x18001ef78  mov     [rbp+21E0h+var_50], rax
0x18001ef7f  mov     r15d, r9d
0x18001ef82  mov     [rsp+22E0h+var_22A0], r9d
0x18001ef87  mov     r13, r8
0x18001ef8a  mov     rdi, rdx
0x18001ef8d  mov     rsi, rcx
0x18001ef90  xor     r14d, r14d
0x18001ef93  mov     [rsp+22E0h+var_2280], r14
0x18001ef98  mov     [rsp+22E0h+var_2278], r14
0x18001ef9d  mov     [rsp+22E0h+var_2270], r14
0x18001efa2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001efa7  test    eax, eax
0x18001efa9  mov     ebx, eax
0x18001efab  js      loc_18001F4A7
0x18001efb1  xor     r12d, r12d
0x18001efb4  cmp     word ptr [rdi], 7Dh ; '}'
0x18001efb8  jz      loc_18001F4A7
0x18001efbe  lea     rdx, String2; "Delete"
0x18001efc5  mov     rcx, rdi; lpString1
0x18001efc8  call    cs:__imp_lstrcmpiW
0x18001efce  mov     r14d, eax
0x18001efd1  lea     rdx, aForceremove; "ForceRemove"
0x18001efd8  mov     rcx, rdi; lpString1
0x18001efdb  call    cs:__imp_lstrcmpiW
0x18001efe1  test    eax, eax
0x18001efe3  jz      short loc_18001EFEE
0x18001efe5  test    r14d, r14d
0x18001efe8  jnz     loc_18001F09F
0x18001efee  mov     rdx, rdi; unsigned __int16 *
0x18001eff1  mov     rcx, rsi; this
0x18001eff4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001eff9  mov     ebx, eax
0x18001effb  test    eax, eax
0x18001effd  js      loc_18001F4A7
0x18001f003  test    r15d, r15d
0x18001f006  jz      loc_18001F09F
0x18001f00c  mov     [rsp+22E0h+hKey], r12
0x18001f011  mov     [rsp+22E0h+var_2290], r12
0x18001f016  mov     [rsp+22E0h+var_2288], r12
0x18001f01b  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001f020  mov     rcx, rdi; lpsz
0x18001f023  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001f028  test    rax, rax
0x18001f02b  jnz     loc_18001F498
0x18001f031  mov     rdx, rdi; unsigned __int16 *
0x18001f034  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18001f039  test    eax, eax
0x18001f03b  jz      short loc_18001F054
0x18001f03d  mov     [rsp+22E0h+hKey], r13
0x18001f042  mov     rdx, rdi; unsigned __int16 *
0x18001f045  lea     rcx, [rsp+22E0h+hKey]; this
0x18001f04a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001f04f  mov     [rsp+22E0h+hKey], r12
0x18001f054  test    r14d, r14d
0x18001f057  jnz     short loc_18001F095
0x18001f059  mov     rdx, rdi; unsigned __int16 *
0x18001f05c  mov     rcx, rsi; this
0x18001f05f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f064  mov     ebx, eax
0x18001f066  xor     r14d, r14d
0x18001f069  test    eax, eax
0x18001f06b  js      loc_18001F4DF
0x18001f071  mov     rdx, rdi; unsigned __int16 *
0x18001f074  mov     rcx, rsi; this
0x18001f077  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001f07c  mov     ebx, eax
0x18001f07e  test    eax, eax
0x18001f080  lea     rcx, [rsp+22E0h+hKey]; this
0x18001f085  js      loc_18001F4E4
0x18001f08b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001f090  jmp     loc_18001F286
0x18001f095  lea     rcx, [rsp+22E0h+hKey]; this
0x18001f09a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001f09f  mov     r12d, 1
0x18001f0a5  lea     rdx, aNoremove; "NoRemove"
0x18001f0ac  mov     rcx, rdi; lpString1
0x18001f0af  call    cs:__imp_lstrcmpiW
0x18001f0b5  xor     r14d, r14d
0x18001f0b8  test    eax, eax
0x18001f0ba  jnz     short loc_18001F0D4
0x18001f0bc  mov     r12d, r14d
0x18001f0bf  mov     rdx, rdi; unsigned __int16 *
0x18001f0c2  mov     rcx, rsi; this
0x18001f0c5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f0ca  mov     ebx, eax
0x18001f0cc  test    eax, eax
0x18001f0ce  js      loc_18001F4A7
0x18001f0d4  lea     rdx, aVal; "Val"
0x18001f0db  mov     rcx, rdi; lpString1
0x18001f0de  call    cs:__imp_lstrcmpiW
0x18001f0e4  test    eax, eax
0x18001f0e6  jnz     loc_18001F1CD
0x18001f0ec  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18001f0f3  mov     rcx, rsi; this
0x18001f0f6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f0fb  mov     ebx, eax
0x18001f0fd  test    eax, eax
0x18001f0ff  js      loc_18001F4A7
0x18001f105  mov     rdx, rdi; unsigned __int16 *
0x18001f108  mov     rcx, rsi; this
0x18001f10b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f110  mov     ebx, eax
0x18001f112  test    eax, eax
0x18001f114  js      loc_18001F4A7
0x18001f11a  cmp     word ptr [rdi], 3Dh ; '='
0x18001f11e  jnz     loc_18001F4A2
0x18001f124  test    r15d, r15d
0x18001f127  jz      short loc_18001F15B
0x18001f129  mov     [rsp+22E0h+var_2290], r14
0x18001f12e  mov     [rsp+22E0h+var_2288], r14
0x18001f133  mov     [rsp+22E0h+hKey], r13
0x18001f138  mov     r9, rdi; unsigned __int16 *
0x18001f13b  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18001f142  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18001f147  mov     rcx, rsi; this
0x18001f14a  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001f14f  mov     ebx, eax
0x18001f151  mov     [rsp+22E0h+hKey], r14
0x18001f156  jmp     loc_18001F07E
0x18001f15b  cmp     [rbp+21E0h+arg_20], r14d
0x18001f162  jnz     short loc_18001F1BD
0x18001f164  test    r12d, r12d
0x18001f167  jz      short loc_18001F1BD
0x18001f169  mov     [rsp+22E0h+hKey], r14
0x18001f16e  mov     [rsp+22E0h+var_2290], r14
0x18001f173  mov     [rsp+22E0h+var_2288], r14
0x18001f178  mov     r9d, 20006h; unsigned int
0x18001f17e  xor     r8d, r8d; unsigned __int16 *
0x18001f181  mov     rdx, r13; HKEY
0x18001f184  lea     rcx, [rsp+22E0h+hKey]; this
0x18001f189  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001f18e  test    eax, eax
0x18001f190  jnz     loc_18001F4D6
0x18001f196  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18001f19d  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18001f1a2  call    cs:__imp_RegDeleteValueW
0x18001f1a8  test    eax, 0FFFFFFFDh
0x18001f1ad  jnz     loc_18001F4D6
0x18001f1b3  lea     rcx, [rsp+22E0h+hKey]; this
0x18001f1b8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001f1bd  mov     rdx, rdi; unsigned __int16 *
0x18001f1c0  mov     rcx, rsi; this
0x18001f1c3  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001f1c8  jmp     loc_18001EFA7
0x18001f1cd  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001f1d2  mov     rcx, rdi; lpsz
0x18001f1d5  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001f1da  test    rax, rax
0x18001f1dd  jnz     loc_18001F4A2
0x18001f1e3  test    r15d, r15d
0x18001f1e6  jz      loc_18001F2D5
0x18001f1ec  mov     ebx, 2001Fh
0x18001f1f1  mov     r9d, ebx; unsigned int
0x18001f1f4  mov     r8, rdi; unsigned __int16 *
0x18001f1f7  mov     rdx, r13; HKEY
0x18001f1fa  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001f1ff  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001f204  test    eax, eax
0x18001f206  jz      short loc_18001F24E
0x18001f208  lea     r9d, [rbx-6]; unsigned int
0x18001f20c  mov     r8, rdi; unsigned __int16 *
0x18001f20f  mov     rdx, r13; HKEY
0x18001f212  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001f217  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001f21c  test    eax, eax
0x18001f21e  jz      short loc_18001F24E
0x18001f220  mov     [rsp+22E0h+var_22A8], r14; unsigned int *
0x18001f225  mov     [rsp+22E0h+var_22B0], r14; LPSECURITY_ATTRIBUTES
0x18001f22a  mov     [rsp+22E0h+var_22B8], ebx; REGSAM
0x18001f22e  mov     [rsp+22E0h+var_22C0], r14d; DWORD
0x18001f233  xor     r9d, r9d; unsigned __int16 *
0x18001f236  mov     r8, rdi; lpSubKey
0x18001f239  mov     rdx, r13; hKey
0x18001f23c  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001f241  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001f246  test    eax, eax
0x18001f248  jnz     loc_18001F4EB
0x18001f24e  mov     rdx, rdi; unsigned __int16 *
0x18001f251  mov     rcx, rsi; this
0x18001f254  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f259  mov     ebx, eax
0x18001f25b  test    eax, eax
0x18001f25d  js      loc_18001F4A7
0x18001f263  cmp     word ptr [rdi], 3Dh ; '='
0x18001f267  jnz     short loc_18001F286
0x18001f269  mov     r9, rdi; unsigned __int16 *
0x18001f26c  xor     r8d, r8d; unsigned __int16 *
0x18001f26f  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18001f274  mov     rcx, rsi; this
0x18001f277  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001f27c  mov     ebx, eax
0x18001f27e  test    eax, eax
0x18001f280  js      loc_18001F4A7
0x18001f286  cmp     word ptr [rdi], 7Bh ; '{'
0x18001f28a  jnz     loc_18001EFB1
0x18001f290  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f294  inc     rax
0x18001f297  cmp     [rdi+rax*2], r14w
0x18001f29c  jnz     short loc_18001F294
0x18001f29e  cmp     rax, 1
0x18001f2a2  jnz     loc_18001EFB1
0x18001f2a8  mov     [rsp+22E0h+var_22C0], r14d; int
0x18001f2ad  mov     r9d, r15d; int
0x18001f2b0  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001f2b5  mov     rdx, rdi; unsigned __int16 *
0x18001f2b8  mov     rcx, rsi; this
0x18001f2bb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001f2c0  mov     ebx, eax
0x18001f2c2  test    eax, eax
0x18001f2c4  js      loc_18001F4A7
0x18001f2ca  mov     rdx, rdi
0x18001f2cd  mov     rcx, rsi
0x18001f2d0  jmp     loc_18001EFA2
0x18001f2d5  cmp     [rbp+21E0h+arg_20], r14d
0x18001f2dc  jnz     short loc_18001F2F9
0x18001f2de  mov     r9d, 20019h; unsigned int
0x18001f2e4  mov     r8, rdi; unsigned __int16 *
0x18001f2e7  mov     rdx, r13; HKEY
0x18001f2ea  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001f2ef  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001f2f4  mov     r14d, eax
0x18001f2f7  jmp     short loc_18001F2FF
0x18001f2f9  mov     r14d, 2
0x18001f2ff  mov     r15d, 1
0x18001f305  test    r14d, r14d
0x18001f308  cmovz   r15d, [rbp+21E0h+arg_20]
0x18001f310  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001f314  mov     r8, rdi
0x18001f317  mov     edx, 104h
0x18001f31c  lea     rcx, [rbp+21E0h+var_2260]
0x18001f320  call    cs:__imp__o_wcsncpy_s
0x18001f326  mov     ecx, eax; int
0x18001f328  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001f32d  mov     rdx, rdi; unsigned __int16 *
0x18001f330  mov     rcx, rsi; this
0x18001f333  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f338  mov     ebx, eax
0x18001f33a  test    eax, eax
0x18001f33c  js      loc_18001F4A7
0x18001f342  mov     rdx, rdi; unsigned __int16 *
0x18001f345  mov     rcx, rsi; this
0x18001f348  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001f34d  mov     ebx, eax
0x18001f34f  xor     ecx, ecx
0x18001f351  test    eax, eax
0x18001f353  js      loc_18001F4A7
0x18001f359  cmp     word ptr [rdi], 7Bh ; '{'
0x18001f35d  jnz     short loc_18001F3AE
0x18001f35f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f363  inc     rax
0x18001f366  cmp     [rdi+rax*2], cx
0x18001f36a  jnz     short loc_18001F363
0x18001f36c  cmp     rax, 1
0x18001f370  jnz     short loc_18001F3AE
0x18001f372  mov     [rsp+22E0h+var_22C0], r15d; int
0x18001f377  xor     r9d, r9d; int
0x18001f37a  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001f37f  mov     rdx, rdi; unsigned __int16 *
0x18001f382  mov     rcx, rsi; this
0x18001f385  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001f38a  mov     ebx, eax
0x18001f38c  test    eax, eax
0x18001f38e  jns     short loc_18001F399
0x18001f390  test    r15d, r15d
0x18001f393  jz      loc_18001F4A7
0x18001f399  mov     rdx, rdi; unsigned __int16 *
0x18001f39c  mov     rcx, rsi; this
0x18001f39f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001f3a4  mov     ebx, eax
0x18001f3a6  test    eax, eax
0x18001f3a8  js      loc_18001F4A7
0x18001f3ae  cmp     r14d, 2
0x18001f3b2  mov     r15d, [rsp+22E0h+var_22A0]
0x18001f3b7  jz      loc_18001EFB1
0x18001f3bd  test    r14d, r14d
0x18001f3c0  jz      short loc_18001F3E1
0x18001f3c2  xor     r12d, r12d
0x18001f3c5  cmp     [rbp+21E0h+arg_20], r12d
0x18001f3cc  jnz     loc_18001EFB4
0x18001f3d2  mov     ecx, r14d; unsigned int
0x18001f3d5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001f3da  mov     ebx, eax
0x18001f3dc  jmp     loc_18001F4A7
0x18001f3e1  xor     r14d, r14d
0x18001f3e4  cmp     [rbp+21E0h+arg_20], r14d
0x18001f3eb  jz      short loc_18001F42B
  ... truncated ...
```
