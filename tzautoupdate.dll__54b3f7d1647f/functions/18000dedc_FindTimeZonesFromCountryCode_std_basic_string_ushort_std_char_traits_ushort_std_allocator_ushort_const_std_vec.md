# FindTimeZonesFromCountryCode(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18000dedc`
- end: `0x18000e253`
- name: `?FindTimeZonesFromCountryCode@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@Z`
- size: `887`
- prototype: `__int64 __fastcall(wchar_t *Source, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18000dc80`

## callees

- `0x18000885c`
- `0x18000d33c`
- `0x18000d694`
- `0x18000da78`
- `0x18000db14`
- `0x18000dedc`
- `0x18000e298`
- `0x18000e47c`
- `0x18000e508`
- `0x18000e968`
- `0x18000efe8`
- `0x18001b0f6`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000df31`
- `msvcrt!wcsnlen` at `0x18000df31`
- `icu!uenum_count` at `0x18000dfdb`
- `icu!uenum_count` at `0x18000dfdb`
- `icu!uenum_unext` at `0x18000e0a9`
- `icu!uenum_unext` at `0x18000e0a9`
- `icu!ucal_getWindowsTimeZoneID` at `0x18000e0ef`
- `icu!ucal_getWindowsTimeZoneID` at `0x18000e0ef`
- `icu!uenum_close` at `0x18000e17a`
- `icu!uenum_close` at `0x18000e1b6`
- `icu!uenum_close` at `0x18000e200`
- `icu!uenum_close` at `0x18000df82`
- `icu!uenum_close` at `0x18000e17a`
- `icu!uenum_close` at `0x18000e1b6`
- `icu!uenum_close` at `0x18000e200`
- `icu!uenum_reset` at `0x18000e028`
- `icu!uenum_reset` at `0x18000e028`
- `icu!ucal_openCountryTimeZones` at `0x18000df74`
- `icu!ucal_openCountryTimeZones` at `0x18000df74`

## string_xrefs

- `0x18000dfa8`: `onecore\base\win32\winnls\tzautoupdate\countrycodefinder.cpp`
- `0x18000dffa`: `onecore\base\win32\winnls\tzautoupdate\countrycodefinder.cpp`
- `0x18000e045`: `onecore\base\win32\winnls\tzautoupdate\countrycodefinder.cpp`
- `0x18000e154`: `onecore\base\win32\winnls\tzautoupdate\countrycodefinder.cpp`
- `0x18000e190`: `onecore\base\win32\winnls\tzautoupdate\countrycodefinder.cpp`
- `0x18000e21a`: `onecore\base\win32\winnls\tzautoupdate\countrycodefinder.cpp`

## pseudocode

```c
__int64 __fastcall FindTimeZonesFromCountryCode(wchar_t *Source, _QWORD *a2)
{
  const wchar_t *v3; // rbx
  size_t v4; // rdx
  size_t i; // rcx
  __int64 v6; // rsi
  unsigned int v7; // eax
  unsigned int v8; // edi
  int v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // eax
  int j; // ebx
  __int64 v14; // r15
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // edx
  __int64 v18; // rax
  __int64 v19; // r8
  unsigned int v20; // ebx
  __int64 v21; // rdi
  __int64 v22; // rbx
  unsigned int *v23; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v26; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v27[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v28[16]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v29[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v3 = Source;
  v25 = 0;
  if ( *((_QWORD *)Source + 3) >= 8u )
    v3 = *(const wchar_t **)Source;
  if ( v3 )
  {
    v4 = wcsnlen(v3, 4u);
    if ( v4 == 4 )
    {
LABEL_38:
      v20 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\countrycodefinder.cpp",
        (const char *)0x80070057LL,
        (int)v23);
      return v20;
    }
  }
  else
  {
    v4 = 0;
  }
  for ( i = 0; i < v4; ++i )
  {
    if ( v3[i] > 0x7Fu )
      goto LABEL_38;
    *((_BYTE *)&v25 + i) = v3[i];
  }
  v24 = 0;
  v6 = ucal_openCountryTimeZones(&v25, &v24);
  v27[2] = v6;
  v27[3] = uenum_close;
  v7 = IcuStatusToWin32Error(v24);
  if ( v7 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x32,
           (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\countrycodefinder.cpp",
           (const char *)v7,
           (unsigned int)v23);
    if ( v6 )
      uenum_close(v6);
    return v8;
  }
  v10 = uenum_count(v6, &v24);
  v11 = IcuStatusToWin32Error(v24);
  if ( v11 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x35,
           (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\countrycodefinder.cpp",
           (const char *)v11,
           (unsigned int)v23);
    if ( v6 )
      uenum_close(v6);
    return v8;
  }
  uenum_reset(v6, &v24);
  v12 = IcuStatusToWin32Error(v24);
  if ( v12 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x38,
           (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\countrycodefinder.cpp",
           (const char *)v12,
           (unsigned int)v23);
    if ( v6 )
      uenum_close(v6);
    return v8;
  }
  v27[0] = 0;
  v27[1] = 0;
  v27[0] = std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode();
  for ( j = 0; j < v10; ++j )
  {
    v26 = 0;
    v14 = uenum_unext(v6, &v26, &v24);
    v15 = IcuStatusToWin32Error(v24);
    if ( v15 )
    {
      v20 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x3F,
              (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\countrycodefinder.cpp",
              (const char *)v15,
              (unsigned int)v23);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v27);
      if ( v6 )
        uenum_close(v6);
      return v20;
    }
    memset_0(v30, 0, sizeof(v30));
    v23 = &v24;
    ucal_getWindowsTimeZoneID(v14, v26, v30, 128);
    v16 = IcuStatusToWin32Error(v24);
    if ( v16 )
    {
      v20 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x43,
              (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\countrycodefinder.cpp",
              (const char *)v16,
              (unsigned int)&v24);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v27);
      if ( v6 )
        uenum_close(v6);
      return v20;
    }
    if ( v17 )
    {
      v18 = std::wstring::wstring(v29, v30);
      LOBYTE(v23) = byte_1800313A8;
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring,std::_Nil>(
        v27,
        v28,
        v19,
        v18);
      std::wstring::_Tidy(v29, 1, 0);
    }
  }
  v21 = v27[0];
  v22 = *(_QWORD *)v27[0];
  std::vector<std::wstring>::erase(a2, &v26, *a2, a2[1]);
  std::vector<std::wstring>::_Insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>>(
    a2,
    *a2,
    v22,
    v21);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v27);
  if ( v6 )
    uenum_close(v6);
  return 0;
}

```

## disassembly

```asm
0x18000dedc  mov     [rsp-8+arg_10], rbx
0x18000dee1  push    rbp
0x18000dee2  push    rsi
0x18000dee3  push    rdi
0x18000dee4  push    r14
0x18000dee6  push    r15
0x18000dee8  lea     rbp, [rsp-0A0h]
0x18000def0  sub     rsp, 1A0h
0x18000def7  mov     rax, cs:__security_cookie
0x18000defe  xor     rax, rsp
0x18000df01  mov     [rbp+0C0h+var_30], rax
0x18000df08  mov     r14, rdx
0x18000df0b  mov     rbx, rcx
0x18000df0e  mov     [rsp+1C0h+var_18C], 0
0x18000df16  cmp     qword ptr [rcx+18h], 8
0x18000df1b  jb      short loc_18000DF20
0x18000df1d  mov     rbx, [rcx]
0x18000df20  test    rbx, rbx
0x18000df23  jnz     short loc_18000DF29
0x18000df25  xor     edx, edx
0x18000df27  jmp     short loc_18000DF44
0x18000df29  mov     edx, 4; MaxCount
0x18000df2e  mov     rcx, rbx; Source
0x18000df31  call    cs:__imp_wcsnlen
0x18000df37  mov     rdx, rax
0x18000df3a  cmp     rax, 4
0x18000df3e  jz      loc_18000E20B
0x18000df44  xor     ecx, ecx
0x18000df46  cmp     rcx, rdx
0x18000df49  jnb     short loc_18000DF62
0x18000df4b  cmp     word ptr [rbx+rcx*2], 7Fh
0x18000df50  ja      loc_18000E20B
0x18000df56  mov     al, [rbx+rcx*2]
0x18000df59  mov     byte ptr [rsp+rcx+1C0h+var_18C], al
0x18000df5d  inc     rcx
0x18000df60  jmp     short loc_18000DF46
0x18000df62  mov     [rsp+1C0h+var_190], 0
0x18000df6a  lea     rdx, [rsp+1C0h+var_190]
0x18000df6f  lea     rcx, [rsp+1C0h+var_18C]
0x18000df74  call    cs:__imp_ucal_openCountryTimeZones
0x18000df7a  mov     rsi, rax
0x18000df7d  mov     [rsp+1C0h+var_170], rax
0x18000df82  mov     rcx, cs:__imp_uenum_close
0x18000df89  mov     [rsp+1C0h+var_168], rcx
0x18000df8e  mov     rbx, rcx
0x18000df91  mov     ecx, [rsp+1C0h+var_190]
0x18000df95  call    ?IcuStatusToWin32Error@@YAKW4UErrorCode@@K@Z; IcuStatusToWin32Error(UErrorCode,ulong)
0x18000df9a  test    eax, eax
0x18000df9c  jz      short loc_18000DFD3
0x18000df9e  mov     rcx, [rbp+0C8h]; this
0x18000dfa5  mov     r9d, eax; char *
0x18000dfa8  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000dfaf  mov     edx, 32h ; '2'; void *
0x18000dfb4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000dfb9  mov     edi, eax
0x18000dfbb  test    rsi, rsi
0x18000dfbe  jz      short loc_18000DFCC
0x18000dfc0  mov     rcx, rsi
0x18000dfc3  mov     rax, rbx
0x18000dfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfcb  nop
0x18000dfcc  mov     eax, edi
0x18000dfce  jmp     loc_18000E22D
0x18000dfd3  lea     rdx, [rsp+1C0h+var_190]
0x18000dfd8  mov     rcx, rsi
0x18000dfdb  call    cs:__imp_uenum_count
0x18000dfe1  mov     edi, eax
0x18000dfe3  mov     ecx, [rsp+1C0h+var_190]
0x18000dfe7  call    ?IcuStatusToWin32Error@@YAKW4UErrorCode@@K@Z; IcuStatusToWin32Error(UErrorCode,ulong)
0x18000dfec  test    eax, eax
0x18000dfee  jz      short loc_18000E020
0x18000dff0  mov     rcx, [rbp+0C8h]; this
0x18000dff7  mov     r9d, eax; char *
0x18000dffa  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000e001  mov     edx, 35h ; '5'; void *
0x18000e006  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000e00b  mov     edi, eax
0x18000e00d  test    rsi, rsi
0x18000e010  jz      short loc_18000E01E
0x18000e012  mov     rcx, rsi
0x18000e015  mov     rax, rbx
0x18000e018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e01d  nop
0x18000e01e  jmp     short loc_18000DFCC
0x18000e020  lea     rdx, [rsp+1C0h+var_190]
0x18000e025  mov     rcx, rsi
0x18000e028  call    cs:__imp_uenum_reset
0x18000e02e  mov     ecx, [rsp+1C0h+var_190]
0x18000e032  call    ?IcuStatusToWin32Error@@YAKW4UErrorCode@@K@Z; IcuStatusToWin32Error(UErrorCode,ulong)
0x18000e037  test    eax, eax
0x18000e039  jz      short loc_18000E06E
0x18000e03b  mov     rcx, [rbp+0C8h]; this
0x18000e042  mov     r9d, eax; char *
0x18000e045  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000e04c  mov     edx, 38h ; '8'; void *
0x18000e051  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000e056  mov     edi, eax
0x18000e058  test    rsi, rsi
0x18000e05b  jz      short loc_18000E069
0x18000e05d  mov     rcx, rsi
0x18000e060  mov     rax, rbx
0x18000e063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e068  nop
0x18000e069  jmp     loc_18000DFCC
0x18000e06e  mov     [rsp+1C0h+var_180], 0
0x18000e077  mov     [rsp+1C0h+var_178], 0
0x18000e080  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::wstring>>::_Buyheadnode(void)
0x18000e085  mov     [rsp+1C0h+var_180], rax
0x18000e08a  xor     ebx, ebx
0x18000e08c  cmp     ebx, edi
0x18000e08e  jge     loc_18000E1BF
0x18000e094  mov     [rsp+1C0h+var_188], 0
0x18000e09c  lea     r8, [rsp+1C0h+var_190]
0x18000e0a1  lea     rdx, [rsp+1C0h+var_188]
0x18000e0a6  mov     rcx, rsi
0x18000e0a9  call    cs:__imp_uenum_unext
0x18000e0af  mov     r15, rax
0x18000e0b2  mov     ecx, [rsp+1C0h+var_190]
0x18000e0b6  call    ?IcuStatusToWin32Error@@YAKW4UErrorCode@@K@Z; IcuStatusToWin32Error(UErrorCode,ulong)
0x18000e0bb  test    eax, eax
0x18000e0bd  jnz     loc_18000E186
0x18000e0c3  xor     edx, edx; Val
0x18000e0c5  mov     r8d, 100h; Size
0x18000e0cb  lea     rcx, [rbp+0C0h+var_130]; void *
0x18000e0cf  call    memset_0
0x18000e0d4  lea     rax, [rsp+1C0h+var_190]
0x18000e0d9  mov     qword ptr [rsp+1C0h+var_1A0], rax; unsigned int
0x18000e0de  mov     r9d, 80h
0x18000e0e4  lea     r8, [rbp+0C0h+var_130]
0x18000e0e8  mov     edx, [rsp+1C0h+var_188]
0x18000e0ec  mov     rcx, r15
0x18000e0ef  call    cs:__imp_ucal_getWindowsTimeZoneID
0x18000e0f5  mov     edx, eax
0x18000e0f7  mov     ecx, [rsp+1C0h+var_190]
0x18000e0fb  call    ?IcuStatusToWin32Error@@YAKW4UErrorCode@@K@Z; IcuStatusToWin32Error(UErrorCode,ulong)
0x18000e100  test    eax, eax
0x18000e102  jnz     short loc_18000E14A
0x18000e104  test    edx, edx
0x18000e106  jz      short loc_18000E143
0x18000e108  lea     rdx, [rbp+0C0h+var_130]
0x18000e10c  lea     rcx, [rsp+1C0h+var_150]
0x18000e111  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000e116  nop
0x18000e117  mov     cl, cs:byte_1800313A8
0x18000e11d  mov     byte ptr [rsp+1C0h+var_1A0], cl
0x18000e121  mov     r9, rax
0x18000e124  lea     rdx, [rsp+1C0h+var_160]
0x18000e129  lea     rcx, [rsp+1C0h+var_180]
0x18000e12e  call    ??$_Insert_nohint@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Nil@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_N$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring,std::_Nil>(bool,std::wstring &&,std::_Nil)
0x18000e133  nop
0x18000e134  xor     r8d, r8d
0x18000e137  mov     dl, 1
0x18000e139  lea     rcx, [rsp+1C0h+var_150]
0x18000e13e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e143  inc     ebx
0x18000e145  jmp     loc_18000E08C
0x18000e14a  mov     rcx, [rbp+0C8h]; this
0x18000e151  mov     r9d, eax; char *
0x18000e154  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000e15b  mov     edx, 43h ; 'C'; void *
0x18000e160  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000e165  mov     ebx, eax
0x18000e167  lea     rcx, [rsp+1C0h+var_180]
0x18000e16c  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000e171  nop
0x18000e172  test    rsi, rsi
0x18000e175  jz      short loc_18000E181
0x18000e177  mov     rcx, rsi
0x18000e17a  call    cs:__imp_uenum_close
0x18000e180  nop
0x18000e181  jmp     loc_18000E22B
0x18000e186  mov     rcx, [rbp+0C8h]; this
0x18000e18d  mov     r9d, eax; char *
0x18000e190  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000e197  mov     edx, 3Fh ; '?'; void *
0x18000e19c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000e1a1  mov     ebx, eax
0x18000e1a3  lea     rcx, [rsp+1C0h+var_180]
0x18000e1a8  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000e1ad  nop
0x18000e1ae  test    rsi, rsi
0x18000e1b1  jz      short loc_18000E1BD
0x18000e1b3  mov     rcx, rsi
0x18000e1b6  call    cs:__imp_uenum_close
0x18000e1bc  nop
0x18000e1bd  jmp     short loc_18000E22B
0x18000e1bf  mov     rdi, [rsp+1C0h+var_180]
0x18000e1c4  mov     rbx, [rdi]
0x18000e1c7  mov     r9, [r14+8]
0x18000e1cb  mov     r8, [r14]
0x18000e1ce  lea     rdx, [rsp+1C0h+var_188]
0x18000e1d3  mov     rcx, r14
0x18000e1d6  call    ?erase@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@0@Z; std::vector<std::wstring>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>)
0x18000e1db  mov     r9, rdi
0x18000e1de  mov     r8, rbx
0x18000e1e1  mov     rdx, [r14]
0x18000e1e4  mov     rcx, r14
0x18000e1e7  call    ??$_Insert@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@1Uforward_iterator_tag@1@@Z; std::vector<std::wstring>::_Insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>,std::forward_iterator_tag)
0x18000e1ec  nop
0x18000e1ed  lea     rcx, [rsp+1C0h+var_180]
0x18000e1f2  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000e1f7  nop
0x18000e1f8  test    rsi, rsi
0x18000e1fb  jz      short loc_18000E207
0x18000e1fd  mov     rcx, rsi
0x18000e200  call    cs:__imp_uenum_close
0x18000e206  nop
0x18000e207  xor     eax, eax
0x18000e209  jmp     short loc_18000E22D
0x18000e20b  mov     rcx, [rbp+0C8h]; this
0x18000e212  mov     ebx, 80070057h
0x18000e217  mov     r9d, ebx; char *
0x18000e21a  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000e221  mov     edx, 2Ch ; ','; void *
0x18000e226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e22b  mov     eax, ebx
0x18000e22d  mov     rcx, [rbp+0C0h+var_30]
0x18000e234  xor     rcx, rsp; StackCookie
0x18000e237  call    __security_check_cookie
0x18000e23c  mov     rbx, [rsp+1C0h+arg_10]
0x18000e244  add     rsp, 1A0h
0x18000e24b  pop     r15
0x18000e24d  pop     r14
0x18000e24f  pop     rdi
0x18000e250  pop     rsi
0x18000e251  pop     rbp
0x18000e252  retn
```
