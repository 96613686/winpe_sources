# CRegEventProvider::TranslateHiveName(ushort const *)

- ea: `0x180007d70`
- end: `0x180007fd8`
- name: `?TranslateHiveName@CRegEventProvider@@IEAAPEAUHKEY__@@PEBG@Z`
- size: `616`
- prototype: `unsigned __int64 __fastcall(CRegEventProvider *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006740`
- `0x180007100`

## callees

- `0x180006fe0`
- `0x180007d70`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007dfe`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007e53`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007eda`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007f2d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007dfe`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007e53`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007eda`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180007f2d`

## string_xrefs

- `0x180007f88`: `HKEY_CURRENT_CONFIG`

## pseudocode

```c
unsigned __int64 __fastcall CRegEventProvider::TranslateHiveName(CRegEventProvider *this, const unsigned __int16 *a2)
{
  const wchar_t *v2; // rsi
  const unsigned __int16 *i; // r14
  WCHAR v5; // bx
  int v7; // eax
  WCHAR v8; // cx
  int v9; // eax
  const wchar_t *v10; // rsi
  const unsigned __int16 *j; // r14
  WCHAR v12; // bx
  int v13; // eax
  WCHAR v14; // cx
  int v15; // eax
  CRegEventProvider *DestStr; // [rsp+60h] [rbp+30h] BYREF
  WCHAR SrcStr; // [rsp+68h] [rbp+38h] BYREF

  DestStr = this;
  v2 = L"HKEY_CLASSES_ROOT";
  for ( i = a2; ; ++i )
  {
    v5 = *i;
    if ( *i )
    {
      if ( v5 > 0x7Fu )
      {
        SrcStr = *i;
        LOWORD(DestStr) = 0;
        v7 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, (LPWSTR)&DestStr, 1);
        v5 = (unsigned __int16)DestStr;
        if ( !v7 )
          v5 = SrcStr;
      }
      else if ( (unsigned __int16)(v5 - 65) <= 0x19u )
      {
        v5 += 32;
      }
    }
    else if ( !*v2 )
    {
      return 0xFFFFFFFF80000000uLL;
    }
    v8 = *v2;
    if ( *v2 > 0x7Fu )
    {
      SrcStr = *v2;
      LOWORD(DestStr) = 0;
      v9 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, (LPWSTR)&DestStr, 1);
      v8 = (unsigned __int16)DestStr;
      if ( !v9 )
        v8 = SrcStr;
    }
    else if ( (unsigned __int16)(v8 - 65) <= 0x19u )
    {
      v8 += 32;
    }
    if ( v5 != v8 )
      break;
    ++v2;
  }
  v10 = L"HKEY_LOCAL_MACHINE";
  for ( j = a2; ; ++j )
  {
    v12 = *j;
    if ( *j )
    {
      if ( v12 > 0x7Fu )
      {
        SrcStr = *j;
        LOWORD(DestStr) = 0;
        v13 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, (LPWSTR)&DestStr, 1);
        v12 = (unsigned __int16)DestStr;
        if ( !v13 )
          v12 = SrcStr;
      }
      else if ( (unsigned __int16)(v12 - 65) <= 0x19u )
      {
        v12 += 32;
      }
    }
    else if ( !*v10 )
    {
      return -2147483646;
    }
    v14 = *v10;
    if ( *v10 > 0x7Fu )
    {
      SrcStr = *v10;
      LOWORD(DestStr) = 0;
      v15 = LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, (LPWSTR)&DestStr, 1);
      v14 = (unsigned __int16)DestStr;
      if ( !v15 )
        v14 = SrcStr;
    }
    else if ( (unsigned __int16)(v14 - 65) <= 0x19u )
    {
      v14 += 32;
    }
    if ( v12 != v14 )
      break;
    ++v10;
  }
  if ( !(unsigned int)wbem_wcsicmp(a2, L"HKEY_USERS") )
    return -2147483645;
  if ( !(unsigned int)wbem_wcsicmp(a2, L"HKEY_PERFORMANCE_DATA") )
    return -2147483644;
  if ( (unsigned int)wbem_wcsicmp(a2, L"HKEY_CURRENT_CONFIG") )
    return -(__int64)((unsigned int)wbem_wcsicmp(a2, L"HKEY_DYN_DATA") == 0) & 0xFFFFFFFF80000006uLL;
  return -2147483643;
}

```

## disassembly

```asm
0x180007d70  mov     [rsp-28h+arg_10], rbx
0x180007d75  mov     [rsp-28h+arg_18], rsi
0x180007d7a  mov     [rsp-28h+DestStr], rcx
0x180007d7f  push    rbp
0x180007d80  push    rdi
0x180007d81  push    r12
0x180007d83  push    r14
0x180007d85  push    r15
0x180007d87  mov     rbp, rsp
0x180007d8a  sub     rsp, 30h
0x180007d8e  xor     r15d, r15d
0x180007d91  lea     rsi, aHkeyClassesRoo; "HKEY_CLASSES_ROOT"
0x180007d98  mov     rdi, rdx
0x180007d9b  mov     r14, rdx
0x180007d9e  lea     r12d, [r15+7Fh]
0x180007da2  movzx   ebx, word ptr [r14]
0x180007da6  test    bx, bx
0x180007da9  jnz     short loc_180007DBD
0x180007dab  cmp     [rsi], r15w
0x180007daf  jnz     short loc_180007E0F
0x180007db1  mov     rax, 0FFFFFFFF80000000h
0x180007db8  jmp     loc_180007FC1
0x180007dbd  cmp     bx, r12w
0x180007dc1  ja      short loc_180007DD2
0x180007dc3  lea     eax, [rbx-41h]
0x180007dc6  cmp     ax, 19h
0x180007dca  ja      short loc_180007E0F
0x180007dcc  add     bx, 20h ; ' '
0x180007dd0  jmp     short loc_180007E0F
0x180007dd2  lea     rax, [rbp+DestStr]
0x180007dd6  mov     [rsp+30h+cchDest], 1; cchDest
0x180007dde  mov     r9d, 1; cchSrc
0x180007de4  mov     [rsp+30h+lpDestStr], rax; lpDestStr
0x180007de9  lea     r8, [rbp+SrcStr]; lpSrcStr
0x180007ded  mov     [rbp+SrcStr], bx
0x180007df1  mov     edx, 100h; dwMapFlags
0x180007df6  mov     word ptr [rbp+DestStr], r15w
0x180007dfb  mov     ecx, r12d; Locale
0x180007dfe  call    cs:__imp_LCMapStringW
0x180007e04  movzx   ebx, word ptr [rbp+DestStr]
0x180007e08  test    eax, eax
0x180007e0a  cmovz   bx, [rbp+SrcStr]
0x180007e0f  movzx   ecx, word ptr [rsi]
0x180007e12  cmp     cx, r12w
0x180007e16  ja      short loc_180007E27
0x180007e18  lea     eax, [rcx-41h]
0x180007e1b  cmp     ax, 19h
0x180007e1f  ja      short loc_180007E64
0x180007e21  add     cx, 20h ; ' '
0x180007e25  jmp     short loc_180007E64
0x180007e27  mov     [rbp+SrcStr], cx
0x180007e2b  lea     rax, [rbp+DestStr]
0x180007e2f  mov     ecx, r12d; Locale
0x180007e32  mov     [rsp+30h+cchDest], 1; cchDest
0x180007e3a  mov     r9d, 1; cchSrc
0x180007e40  mov     [rsp+30h+lpDestStr], rax; lpDestStr
0x180007e45  lea     r8, [rbp+SrcStr]; lpSrcStr
0x180007e49  mov     word ptr [rbp+DestStr], r15w
0x180007e4e  mov     edx, 100h; dwMapFlags
0x180007e53  call    cs:__imp_LCMapStringW
0x180007e59  movzx   ecx, word ptr [rbp+DestStr]
0x180007e5d  test    eax, eax
0x180007e5f  cmovz   cx, [rbp+SrcStr]
0x180007e64  cmp     bx, cx
0x180007e67  jnz     short loc_180007E76
0x180007e69  add     r14, 2
0x180007e6d  add     rsi, 2
0x180007e71  jmp     loc_180007DA2
0x180007e76  lea     rsi, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x180007e7d  mov     r14, rdi
0x180007e80  movzx   ebx, word ptr [r14]
0x180007e84  test    bx, bx
0x180007e87  jnz     short loc_180007E9B
0x180007e89  cmp     [rsi], r15w
0x180007e8d  jnz     short loc_180007EEB
0x180007e8f  mov     rax, 0FFFFFFFF80000002h
0x180007e96  jmp     loc_180007FC1
0x180007e9b  cmp     bx, r12w
0x180007e9f  ja      short loc_180007EB0
0x180007ea1  lea     eax, [rbx-41h]
0x180007ea4  cmp     ax, 19h
0x180007ea8  ja      short loc_180007EEB
0x180007eaa  add     bx, 20h ; ' '
0x180007eae  jmp     short loc_180007EEB
0x180007eb0  mov     ecx, 1
0x180007eb5  mov     [rbp+SrcStr], bx
0x180007eb9  mov     [rsp+30h+cchDest], ecx; cchDest
0x180007ebd  lea     rax, [rbp+DestStr]
0x180007ec1  mov     r9d, ecx; cchSrc
0x180007ec4  mov     word ptr [rbp+DestStr], r15w
0x180007ec9  mov     ecx, r12d; Locale
0x180007ecc  mov     [rsp+30h+lpDestStr], rax; lpDestStr
0x180007ed1  lea     r8, [rbp+SrcStr]; lpSrcStr
0x180007ed5  mov     edx, 100h; dwMapFlags
0x180007eda  call    cs:__imp_LCMapStringW
0x180007ee0  movzx   ebx, word ptr [rbp+DestStr]
0x180007ee4  test    eax, eax
0x180007ee6  cmovz   bx, [rbp+SrcStr]
0x180007eeb  movzx   ecx, word ptr [rsi]
0x180007eee  cmp     cx, r12w
0x180007ef2  ja      short loc_180007F03
0x180007ef4  lea     eax, [rcx-41h]
0x180007ef7  cmp     ax, 19h
0x180007efb  ja      short loc_180007F3E
0x180007efd  add     cx, 20h ; ' '
0x180007f01  jmp     short loc_180007F3E
0x180007f03  mov     [rbp+SrcStr], cx
0x180007f07  lea     rax, [rbp+DestStr]
0x180007f0b  mov     ecx, 1
0x180007f10  mov     word ptr [rbp+DestStr], r15w
0x180007f15  mov     [rsp+30h+cchDest], ecx; cchDest
0x180007f19  lea     r8, [rbp+SrcStr]; lpSrcStr
0x180007f1d  mov     r9d, ecx; cchSrc
0x180007f20  mov     [rsp+30h+lpDestStr], rax; lpDestStr
0x180007f25  mov     ecx, r12d; Locale
0x180007f28  mov     edx, 100h; dwMapFlags
0x180007f2d  call    cs:__imp_LCMapStringW
0x180007f33  movzx   ecx, word ptr [rbp+DestStr]
0x180007f37  test    eax, eax
0x180007f39  cmovz   cx, [rbp+SrcStr]
0x180007f3e  cmp     bx, cx
0x180007f41  jnz     short loc_180007F50
0x180007f43  add     r14, 2
0x180007f47  add     rsi, 2
0x180007f4b  jmp     loc_180007E80
0x180007f50  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x180007f57  mov     rcx, rdi; unsigned __int16 *
0x180007f5a  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180007f5f  test    eax, eax
0x180007f61  jnz     short loc_180007F6C
0x180007f63  mov     rax, 0FFFFFFFF80000003h
0x180007f6a  jmp     short loc_180007FC1
0x180007f6c  lea     rdx, aHkeyPerformanc; "HKEY_PERFORMANCE_DATA"
0x180007f73  mov     rcx, rdi; unsigned __int16 *
0x180007f76  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180007f7b  test    eax, eax
0x180007f7d  jnz     short loc_180007F88
0x180007f7f  mov     rax, 0FFFFFFFF80000004h
0x180007f86  jmp     short loc_180007FC1
0x180007f88  lea     rdx, aHkeyCurrentCon; "HKEY_CURRENT_CONFIG"
0x180007f8f  mov     rcx, rdi; unsigned __int16 *
0x180007f92  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180007f97  test    eax, eax
0x180007f99  jnz     short loc_180007FA4
0x180007f9b  mov     rax, 0FFFFFFFF80000005h
0x180007fa2  jmp     short loc_180007FC1
0x180007fa4  lea     rdx, aHkeyDynData; "HKEY_DYN_DATA"
0x180007fab  mov     rcx, rdi; unsigned __int16 *
0x180007fae  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180007fb3  neg     eax
0x180007fb5  sbb     rax, rax
0x180007fb8  not     rax
0x180007fbb  and     rax, 0FFFFFFFF80000006h
0x180007fc1  mov     rbx, [rsp+30h+arg_10]
0x180007fc6  mov     rsi, [rsp+30h+arg_18]
0x180007fcb  add     rsp, 30h
0x180007fcf  pop     r15
0x180007fd1  pop     r14
0x180007fd3  pop     r12
0x180007fd5  pop     rdi
0x180007fd6  pop     rbp
0x180007fd7  retn
```
