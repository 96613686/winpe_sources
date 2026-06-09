# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800055a0`
- end: `0x180005b79`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000527c`
- `0x1800055a0`

## callees

- `0x1800033ac`
- `0x180003b44`
- `0x180003bb4`
- `0x180003cc8`
- `0x180003de4`
- `0x18000465c`
- `0x180004968`
- `0x180004b60`
- `0x180004cc0`
- `0x180005168`
- `0x1800055a0`
- `0x180005e5c`
- `0x180005f2c`
- `0x180012800`
- `0x1800128c0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800059a6`
- `msvcrt!wcsncpy_s` at `0x1800059a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800058a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800058a7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800057f5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800057f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000561b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000562e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005702`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005731`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000561b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000562e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005702`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005731`

## string_xrefs

- `0x180005624`: `ForceRemove`
- `0x1800056f8`: `NoRemove`
- `0x180005611`: `Delete`

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
0x1800055a0  push    rbp
0x1800055a2  push    rbx
0x1800055a3  push    rsi
0x1800055a4  push    rdi
0x1800055a5  push    r12
0x1800055a7  push    r13
0x1800055a9  push    r14
0x1800055ab  push    r15
0x1800055ad  lea     rbp, [rsp-21C8h]
0x1800055b5  mov     eax, 22C8h
0x1800055ba  call    _alloca_probe
0x1800055bf  sub     rsp, rax
0x1800055c2  mov     rax, cs:__security_cookie
0x1800055c9  xor     rax, rsp
0x1800055cc  mov     [rbp+2200h+var_50], rax
0x1800055d3  mov     r15d, r9d
0x1800055d6  mov     [rsp+2300h+var_22B0], r9d
0x1800055db  mov     r13, r8
0x1800055de  mov     rdi, rdx
0x1800055e1  mov     rsi, rcx
0x1800055e4  xor     r14d, r14d
0x1800055e7  mov     [rsp+2300h+var_2290], r14
0x1800055ec  mov     [rsp+2300h+var_2288], r14
0x1800055f1  mov     [rbp+2200h+var_2280], r14
0x1800055f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800055fa  test    eax, eax
0x1800055fc  mov     ebx, eax
0x1800055fe  js      loc_180005B2D
0x180005604  xor     r12d, r12d
0x180005607  cmp     word ptr [rdi], 7Dh ; '}'
0x18000560b  jz      loc_180005B2D
0x180005611  lea     rdx, String2; "Delete"
0x180005618  mov     rcx, rdi; lpString1
0x18000561b  call    cs:__imp_lstrcmpiW
0x180005621  mov     r14d, eax
0x180005624  lea     rdx, aForceremove; "ForceRemove"
0x18000562b  mov     rcx, rdi; lpString1
0x18000562e  call    cs:__imp_lstrcmpiW
0x180005634  test    eax, eax
0x180005636  jz      short loc_180005641
0x180005638  test    r14d, r14d
0x18000563b  jnz     loc_1800056F2
0x180005641  mov     rdx, rdi; unsigned __int16 *
0x180005644  mov     rcx, rsi; this
0x180005647  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000564c  mov     ebx, eax
0x18000564e  test    eax, eax
0x180005650  js      loc_180005B2D
0x180005656  test    r15d, r15d
0x180005659  jz      loc_1800056F2
0x18000565f  mov     [rsp+2300h+hKey], r12
0x180005664  mov     [rsp+2300h+var_22A0], r12
0x180005669  mov     [rsp+2300h+var_2298], r12
0x18000566e  mov     edx, 5Ch ; '\'; unsigned __int16
0x180005673  mov     rcx, rdi; lpsz
0x180005676  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000567b  test    rax, rax
0x18000567e  jnz     loc_180005B1E
0x180005684  mov     rdx, rdi; unsigned __int16 *
0x180005687  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000568c  test    eax, eax
0x18000568e  jz      short loc_1800056A7
0x180005690  mov     [rsp+2300h+hKey], r13
0x180005695  mov     rdx, rdi; unsigned __int16 *
0x180005698  lea     rcx, [rsp+2300h+hKey]; this
0x18000569d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800056a2  mov     [rsp+2300h+hKey], r12
0x1800056a7  test    r14d, r14d
0x1800056aa  jnz     short loc_1800056E8
0x1800056ac  mov     rdx, rdi; unsigned __int16 *
0x1800056af  mov     rcx, rsi; this
0x1800056b2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800056b7  mov     ebx, eax
0x1800056b9  xor     r14d, r14d
0x1800056bc  test    eax, eax
0x1800056be  js      loc_180005B65
0x1800056c4  mov     rdx, rdi; unsigned __int16 *
0x1800056c7  mov     rcx, rsi; this
0x1800056ca  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800056cf  mov     ebx, eax
0x1800056d1  test    eax, eax
0x1800056d3  lea     rcx, [rsp+2300h+hKey]; this
0x1800056d8  js      loc_180005B6A
0x1800056de  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800056e3  jmp     loc_18000590C
0x1800056e8  lea     rcx, [rsp+2300h+hKey]; this
0x1800056ed  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800056f2  mov     r12d, 1
0x1800056f8  lea     rdx, aNoremove; "NoRemove"
0x1800056ff  mov     rcx, rdi; lpString1
0x180005702  call    cs:__imp_lstrcmpiW
0x180005708  xor     r14d, r14d
0x18000570b  test    eax, eax
0x18000570d  jnz     short loc_180005727
0x18000570f  mov     r12d, r14d
0x180005712  mov     rdx, rdi; unsigned __int16 *
0x180005715  mov     rcx, rsi; this
0x180005718  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000571d  mov     ebx, eax
0x18000571f  test    eax, eax
0x180005721  js      loc_180005B2D
0x180005727  lea     rdx, aVal; "Val"
0x18000572e  mov     rcx, rdi; lpString1
0x180005731  call    cs:__imp_lstrcmpiW
0x180005737  test    eax, eax
0x180005739  jnz     loc_180005820
0x18000573f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180005746  mov     rcx, rsi; this
0x180005749  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000574e  mov     ebx, eax
0x180005750  test    eax, eax
0x180005752  js      loc_180005B2D
0x180005758  mov     rdx, rdi; unsigned __int16 *
0x18000575b  mov     rcx, rsi; this
0x18000575e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005763  mov     ebx, eax
0x180005765  test    eax, eax
0x180005767  js      loc_180005B2D
0x18000576d  cmp     word ptr [rdi], 3Dh ; '='
0x180005771  jnz     loc_180005B28
0x180005777  test    r15d, r15d
0x18000577a  jz      short loc_1800057AE
0x18000577c  mov     [rsp+2300h+var_22A0], r14
0x180005781  mov     [rsp+2300h+var_2298], r14
0x180005786  mov     [rsp+2300h+hKey], r13
0x18000578b  mov     r9, rdi; unsigned __int16 *
0x18000578e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180005795  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18000579a  mov     rcx, rsi; this
0x18000579d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800057a2  mov     ebx, eax
0x1800057a4  mov     [rsp+2300h+hKey], r14
0x1800057a9  jmp     loc_1800056D1
0x1800057ae  cmp     [rbp+2200h+arg_20], r14d
0x1800057b5  jnz     short loc_180005810
0x1800057b7  test    r12d, r12d
0x1800057ba  jz      short loc_180005810
0x1800057bc  mov     [rsp+2300h+hKey], r14
0x1800057c1  mov     [rsp+2300h+var_22A0], r14
0x1800057c6  mov     [rsp+2300h+var_2298], r14
0x1800057cb  mov     r9d, 20006h; unsigned int
0x1800057d1  xor     r8d, r8d; lpSubKey
0x1800057d4  mov     rdx, r13; hKey
0x1800057d7  lea     rcx, [rsp+2300h+hKey]; this
0x1800057dc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800057e1  test    eax, eax
0x1800057e3  jnz     loc_180005B5C
0x1800057e9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800057f0  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800057f5  call    cs:__imp_RegDeleteValueW
0x1800057fb  test    eax, 0FFFFFFFDh
0x180005800  jnz     loc_180005B5C
0x180005806  lea     rcx, [rsp+2300h+hKey]; this
0x18000580b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005810  mov     rdx, rdi; unsigned __int16 *
0x180005813  mov     rcx, rsi; this
0x180005816  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000581b  jmp     loc_1800055FA
0x180005820  mov     edx, 5Ch ; '\'; unsigned __int16
0x180005825  mov     rcx, rdi; lpsz
0x180005828  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000582d  test    rax, rax
0x180005830  jnz     loc_180005B28
0x180005836  test    r15d, r15d
0x180005839  jz      loc_18000595B
0x18000583f  mov     ebx, 2001Fh
0x180005844  mov     r9d, ebx; unsigned int
0x180005847  mov     r8, rdi; lpSubKey
0x18000584a  mov     rdx, r13; hKey
0x18000584d  lea     rcx, [rsp+2300h+var_2290]; this
0x180005852  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005857  test    eax, eax
0x180005859  jz      short loc_1800058D4
0x18000585b  lea     r9d, [rbx-6]; unsigned int
0x18000585f  mov     r8, rdi; lpSubKey
0x180005862  mov     rdx, r13; hKey
0x180005865  lea     rcx, [rsp+2300h+var_2290]; this
0x18000586a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000586f  test    eax, eax
0x180005871  jz      short loc_1800058D4
0x180005873  mov     [rbp+2200h+dwDisposition], r14d
0x180005877  mov     [rbp+2200h+var_2270], r14
0x18000587b  lea     rax, [rbp+2200h+dwDisposition]
0x18000587f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180005884  lea     rax, [rbp+2200h+var_2270]
0x180005888  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000588d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180005892  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180005896  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18000589b  xor     r9d, r9d; lpClass
0x18000589e  xor     r8d, r8d; Reserved
0x1800058a1  mov     rdx, rdi; lpSubKey
0x1800058a4  mov     rcx, r13; hKey
0x1800058a7  call    cs:__imp_RegCreateKeyExW
0x1800058ad  mov     ecx, eax
0x1800058af  test    eax, eax
0x1800058b1  jnz     loc_180005A5B
0x1800058b7  lea     rcx, [rsp+2300h+var_2290]; this
0x1800058bc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800058c1  mov     ecx, eax
0x1800058c3  mov     rax, [rbp+2200h+var_2270]
0x1800058c7  mov     [rsp+2300h+var_2290], rax
0x1800058cc  test    ecx, ecx
0x1800058ce  jnz     loc_180005A5B
0x1800058d4  mov     rdx, rdi; unsigned __int16 *
0x1800058d7  mov     rcx, rsi; this
0x1800058da  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800058df  mov     ebx, eax
0x1800058e1  test    eax, eax
0x1800058e3  js      loc_180005B2D
0x1800058e9  cmp     word ptr [rdi], 3Dh ; '='
0x1800058ed  jnz     short loc_18000590C
0x1800058ef  mov     r9, rdi; unsigned __int16 *
0x1800058f2  xor     r8d, r8d; unsigned __int16 *
0x1800058f5  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1800058fa  mov     rcx, rsi; this
0x1800058fd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005902  mov     ebx, eax
0x180005904  test    eax, eax
0x180005906  js      loc_180005B2D
0x18000590c  cmp     word ptr [rdi], 7Bh ; '{'
0x180005910  jnz     loc_180005604
0x180005916  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000591a  inc     rax
0x18000591d  cmp     [rdi+rax*2], r14w
0x180005922  jnz     short loc_18000591A
0x180005924  cmp     rax, 1
0x180005928  jnz     loc_180005604
0x18000592e  mov     [rsp+2300h+dwOptions], r14d; int
0x180005933  mov     r9d, r15d; int
0x180005936  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000593b  mov     rdx, rdi; unsigned __int16 *
0x18000593e  mov     rcx, rsi; this
0x180005941  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005946  mov     ebx, eax
0x180005948  test    eax, eax
0x18000594a  js      loc_180005B2D
0x180005950  mov     rdx, rdi
0x180005953  mov     rcx, rsi
0x180005956  jmp     loc_1800055F5
0x18000595b  cmp     [rbp+2200h+arg_20], r14d
0x180005962  jnz     short loc_18000597F
0x180005964  mov     r9d, 20019h; unsigned int
0x18000596a  mov     r8, rdi; lpSubKey
0x18000596d  mov     rdx, r13; hKey
0x180005970  lea     rcx, [rsp+2300h+var_2290]; this
0x180005975  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000597a  mov     r14d, eax
0x18000597d  jmp     short loc_180005985
0x18000597f  mov     r14d, 2
0x180005985  mov     r15d, 1
0x18000598b  test    r14d, r14d
0x18000598e  cmovz   r15d, [rbp+2200h+arg_20]
0x180005996  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000599a  mov     r8, rdi; Source
0x18000599d  mov     edx, 104h; SizeInWords
0x1800059a2  lea     rcx, [rbp+2200h+Destination]; Destination
0x1800059a6  call    cs:__imp_wcsncpy_s
0x1800059ac  mov     ecx, eax; int
0x1800059ae  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800059b3  mov     rdx, rdi; unsigned __int16 *
0x1800059b6  mov     rcx, rsi; this
0x1800059b9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800059be  mov     ebx, eax
0x1800059c0  test    eax, eax
0x1800059c2  js      loc_180005B2D
0x1800059c8  mov     rdx, rdi; unsigned __int16 *
0x1800059cb  mov     rcx, rsi; this
0x1800059ce  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800059d3  mov     ebx, eax
0x1800059d5  xor     ecx, ecx
0x1800059d7  test    eax, eax
0x1800059d9  js      loc_180005B2D
0x1800059df  cmp     word ptr [rdi], 7Bh ; '{'
0x1800059e3  jnz     short loc_180005A34
0x1800059e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800059e9  inc     rax
0x1800059ec  cmp     [rdi+rax*2], cx
0x1800059f0  jnz     short loc_1800059E9
0x1800059f2  cmp     rax, 1
0x1800059f6  jnz     short loc_180005A34
0x1800059f8  mov     [rsp+2300h+dwOptions], r15d; int
0x1800059fd  xor     r9d, r9d; int
0x180005a00  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180005a05  mov     rdx, rdi; unsigned __int16 *
0x180005a08  mov     rcx, rsi; this
0x180005a0b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005a10  mov     ebx, eax
0x180005a12  test    eax, eax
0x180005a14  jns     short loc_180005A1F
0x180005a16  test    r15d, r15d
0x180005a19  jz      loc_180005B2D
0x180005a1f  mov     rdx, rdi; unsigned __int16 *
0x180005a22  mov     rcx, rsi; this
0x180005a25  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005a2a  mov     ebx, eax
0x180005a2c  test    eax, eax
0x180005a2e  js      loc_180005B2D
0x180005a34  cmp     r14d, 2
0x180005a38  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
