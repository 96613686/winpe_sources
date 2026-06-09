# _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)

- ea: `0x18007ed70`
- end: `0x18007f019`
- name: `?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z`
- size: `681`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarIn, PROPVARIANT *, enum tagCONDITION_OPERATION, LCID Locale, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007b898`

## callees

- `0x180024418`
- `0x180077d24`
- `0x180077fd4`
- `0x180078c80`
- `0x18007a948`
- `0x18007c1f0`
- `0x18007ca0c`
- `0x18007ed70`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007eee5`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007efa4`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007eff1`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007eee5`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007efa4`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007eff1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecExW` at `0x18007eeaf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecExW` at `0x18007eeaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007efb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007efc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007efb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007efc6`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18007eda7`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18007edba`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18007eda7`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18007edba`

## pseudocode

```c
__int64 __fastcall _LikeOpCompareValuesWorker(
        PROPVARIANT *propvarIn,
        PROPVARIANT *a2,
        enum tagCONDITION_OPERATION a3,
        LCID Locale,
        unsigned int a5)
{
  unsigned int v8; // edi
  const WCHAR *v9; // r14
  const WCHAR *lpStringValue; // rax
  const struct std::nothrow_t *v11; // rdx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // rbp
  unsigned __int64 v14; // rcx
  CWordMatch *v15; // rax
  CWordMatch *v16; // rax
  const unsigned __int16 *v17; // r8
  CWordMatch *v18; // rbx
  unsigned int NLSString; // edi
  DWORD v20; // edx
  unsigned int v21; // ebx
  int v22; // r13d
  unsigned int v23; // edx
  WCHAR *v24; // rbx
  LPCWSTR lpStringSource; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR v27; // [rsp+48h] [rbp-30h] BYREF
  int v28; // [rsp+90h] [rbp+18h] BYREF

  v28 = 0;
  v8 = 0;
  v9 = PropVariantToStringWithDefault(a2, &pszDefault);
  lpStringValue = PropVariantToStringWithDefault(propvarIn, &pszDefault);
  v13 = lpStringValue;
  if ( a3 != COP_VALUE_STARTSWITH )
  {
    if ( a3 == COP_VALUE_ENDSWITH )
    {
      v20 = a5 | 0x200000;
    }
    else
    {
      if ( a3 != COP_VALUE_CONTAINS )
      {
        if ( a3 != COP_VALUE_NOTCONTAINS )
        {
          if ( a3 == COP_DOSWILDCARDS )
          {
            LOBYTE(v8) = PathMatchSpecExW(v9, lpStringValue, 0) == 0;
          }
          else
          {
            v14 = (unsigned int)(a3 - 12);
            if ( (unsigned int)v14 <= 1 )
            {
              v15 = (CWordMatch *)CZeroInitNew::operator new(v14, v11);
              if ( v15 )
              {
                v16 = CWordMatch::CWordMatch(v15, a3);
                v18 = v16;
                if ( v16 )
                {
                  *((_DWORD *)v16 + 138) = Locale;
                  *((_DWORD *)v16 + 139) = a5;
                  if ( Locale == 1042
                    && !CScriptAutoDetection::HasScript((CScriptAutoDetection *)g_scriptAutoDetection, v13, v17) )
                  {
                    CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                      (CKoreanDecomposition *)g_koreanDecomposition,
                      v13,
                      (unsigned __int16 **)v18 + 67);
                  }
                  if ( (int)StringCchCopyW((unsigned __int16 *)v18 + 6, 0x104u, v13) >= 0 )
                  {
                    CWordMatch::WordMatch(v18, v9, &v28);
                    v8 = v28;
                  }
                  CWordMatch::Release(v18);
                }
              }
            }
          }
          return v8;
        }
        NLSString = FindNLSString(Locale, a5 | 0x400000, v9, -1, lpStringValue, -1, 0);
        return NLSString >> 31;
      }
      v20 = a5 | 0x400000;
    }
LABEL_27:
    NLSString = ~FindNLSString(Locale, v20, v9, -1, v13, -1, 0);
    return NLSString >> 31;
  }
  v21 = a5;
  if ( Locale != 1042 || CScriptAutoDetection::HasScript((CScriptAutoDetection *)g_scriptAutoDetection, v9, v12) )
    goto LABEL_26;
  lpStringSource = 0;
  v22 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
          (CKoreanDecomposition *)g_koreanDecomposition,
          v9,
          (unsigned __int16 **)&lpStringSource);
  if ( v22 >= 0 )
  {
    v27 = 0;
    v22 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
            (CKoreanDecomposition *)g_koreanDecomposition,
            v13,
            (unsigned __int16 **)&v27);
    if ( v22 >= 0 )
    {
      v23 = v21;
      v24 = (WCHAR *)v27;
      v8 = FindNLSString(0x412u, v23 | 0x100000, lpStringSource, -1, v27, -1, 0) >= 0;
      CoTaskMemFree(v24);
      v21 = a5;
    }
    CoTaskMemFree((LPVOID)lpStringSource);
  }
  if ( v22 )
  {
LABEL_26:
    v20 = v21 | 0x100000;
    goto LABEL_27;
  }
  return v8;
}

```

## disassembly

```asm
0x18007ed70  mov     r11, rsp
0x18007ed73  mov     [r11+8], rbx
0x18007ed77  mov     [r11+10h], rbp
0x18007ed7b  push    rsi
0x18007ed7c  push    rdi
0x18007ed7d  push    r13
0x18007ed7f  push    r14
0x18007ed81  push    r15
0x18007ed83  sub     rsp, 50h
0x18007ed87  mov     rax, rdx
0x18007ed8a  mov     rbx, rcx
0x18007ed8d  xor     r13d, r13d
0x18007ed90  lea     rdx, pszDefault; pszDefault
0x18007ed97  mov     rcx, rax; propvarIn
0x18007ed9a  mov     [r11+18h], r13d
0x18007ed9e  mov     r15d, r9d
0x18007eda1  mov     esi, r8d
0x18007eda4  mov     edi, r13d
0x18007eda7  call    cs:__imp_PropVariantToStringWithDefault
0x18007edad  lea     rdx, pszDefault; pszDefault
0x18007edb4  mov     rcx, rbx; propvarIn
0x18007edb7  mov     r14, rax
0x18007edba  call    cs:__imp_PropVariantToStringWithDefault
0x18007edc0  mov     ecx, esi
0x18007edc2  mov     rbp, rax
0x18007edc5  sub     ecx, 7
0x18007edc8  jz      loc_18007EF12
0x18007edce  sub     ecx, 1
0x18007edd1  jz      loc_18007EF05
0x18007edd7  sub     ecx, 1
0x18007edda  jz      loc_18007EEF2
0x18007ede0  sub     ecx, 1
0x18007ede3  jz      loc_18007EEC0
0x18007ede9  sub     ecx, 1
0x18007edec  jz      loc_18007EEA6
0x18007edf2  sub     ecx, 1; unsigned __int64
0x18007edf5  jz      short loc_18007EE00
0x18007edf7  cmp     ecx, 1
0x18007edfa  jnz     loc_18007EFFE
0x18007ee00  call    ??2CZeroInitNew@@SAPEAX_KAEBUnothrow_t@std@@@Z; CZeroInitNew::operator new(unsigned __int64,std::nothrow_t const &)
0x18007ee05  test    rax, rax
0x18007ee08  jz      loc_18007EFFE
0x18007ee0e  mov     edx, esi; enum tagCONDITION_OPERATION
0x18007ee10  mov     rcx, rax; this
0x18007ee13  call    ??0CWordMatch@@QEAA@W4tagCONDITION_OPERATION@@@Z; CWordMatch::CWordMatch(tagCONDITION_OPERATION)
0x18007ee18  mov     rbx, rax
0x18007ee1b  test    rax, rax
0x18007ee1e  jz      loc_18007EFFE
0x18007ee24  mov     [rax+228h], r15d
0x18007ee2b  mov     eax, [rsp+78h+arg_20]
0x18007ee32  mov     [rbx+22Ch], eax
0x18007ee38  cmp     r15d, 412h
0x18007ee3f  jnz     short loc_18007EE6A
0x18007ee41  mov     rdx, rbp; unsigned __int16 *
0x18007ee44  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18007ee4b  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x18007ee50  test    eax, eax
0x18007ee52  jnz     short loc_18007EE6A
0x18007ee54  lea     r8, [rbx+218h]; unsigned __int16 **
0x18007ee5b  mov     rdx, rbp; unsigned __int16 *
0x18007ee5e  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18007ee65  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18007ee6a  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x18007ee6e  mov     r8, rbp; unsigned __int16 *
0x18007ee71  mov     edx, 104h; unsigned __int64
0x18007ee76  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007ee7b  test    eax, eax
0x18007ee7d  js      short loc_18007EE99
0x18007ee7f  lea     r8, [rsp+78h+arg_10]; int *
0x18007ee87  mov     rdx, r14; unsigned __int16 *
0x18007ee8a  mov     rcx, rbx; this
0x18007ee8d  call    ?WordMatch@CWordMatch@@QEAAJPEBGPEAH@Z; CWordMatch::WordMatch(ushort const *,int *)
0x18007ee92  mov     edi, [rsp+78h+arg_10]
0x18007ee99  mov     rcx, rbx; this
0x18007ee9c  call    ?Release@CWordMatch@@UEAAKXZ; CWordMatch::Release(void)
0x18007eea1  jmp     loc_18007EFFE
0x18007eea6  xor     r8d, r8d; dwFlags
0x18007eea9  mov     rdx, rbp; pszSpec
0x18007eeac  mov     rcx, r14; pszFile
0x18007eeaf  call    cs:__imp_PathMatchSpecExW
0x18007eeb5  test    eax, eax
0x18007eeb7  setz    dil
0x18007eebb  jmp     loc_18007EFFE
0x18007eec0  mov     edx, [rsp+78h+arg_20]
0x18007eec7  or      esi, 0FFFFFFFFh
0x18007eeca  mov     [rsp+78h+pcchFound], r13; pcchFound
0x18007eecf  bts     edx, 16h; dwFindNLSStringFlags
0x18007eed3  mov     [rsp+78h+cchValue], esi; cchValue
0x18007eed7  mov     r9d, esi; cchSource
0x18007eeda  mov     r8, r14; lpStringSource
0x18007eedd  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x18007eee2  mov     ecx, r15d; Locale
0x18007eee5  call    cs:__imp_FindNLSString
0x18007eeeb  mov     edi, eax
0x18007eeed  jmp     loc_18007EFFB
0x18007eef2  mov     edx, [rsp+78h+arg_20]
0x18007eef9  bts     edx, 16h
0x18007eefd  or      esi, 0FFFFFFFFh
0x18007ef00  jmp     loc_18007EFDA
0x18007ef05  mov     edx, [rsp+78h+arg_20]
0x18007ef0c  bts     edx, 15h
0x18007ef10  jmp     short loc_18007EEFD
0x18007ef12  mov     ebx, [rsp+78h+arg_20]
0x18007ef19  or      esi, 0FFFFFFFFh
0x18007ef1c  cmp     r15d, 412h
0x18007ef23  jnz     loc_18007EFD4
0x18007ef29  mov     rdx, r14; unsigned __int16 *
0x18007ef2c  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18007ef33  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x18007ef38  test    eax, eax
0x18007ef3a  jnz     loc_18007EFD4
0x18007ef40  lea     r8, [rsp+78h+lpStringSource]; unsigned __int16 **
0x18007ef45  mov     [rsp+78h+lpStringSource], r13
0x18007ef4a  mov     rdx, r14; unsigned __int16 *
0x18007ef4d  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18007ef54  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18007ef59  mov     r13d, eax
0x18007ef5c  test    eax, eax
0x18007ef5e  js      short loc_18007EFCC
0x18007ef60  lea     r8, [rsp+78h+var_30]; unsigned __int16 **
0x18007ef65  mov     [rsp+78h+var_30], rdi
0x18007ef6a  mov     rdx, rbp; unsigned __int16 *
0x18007ef6d  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18007ef74  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18007ef79  mov     r13d, eax
0x18007ef7c  test    eax, eax
0x18007ef7e  js      short loc_18007EFC1
0x18007ef80  mov     r8, [rsp+78h+lpStringSource]; lpStringSource
0x18007ef85  mov     edx, ebx
0x18007ef87  mov     rbx, [rsp+78h+var_30]
0x18007ef8c  bts     edx, 14h; dwFindNLSStringFlags
0x18007ef90  mov     [rsp+78h+pcchFound], rdi; pcchFound
0x18007ef95  mov     r9d, esi; cchSource
0x18007ef98  mov     [rsp+78h+cchValue], esi; cchValue
0x18007ef9c  mov     ecx, r15d; Locale
0x18007ef9f  mov     [rsp+78h+lpStringValue], rbx; lpStringValue
0x18007efa4  call    cs:__imp_FindNLSString
0x18007efaa  mov     edi, eax
0x18007efac  mov     rcx, rbx; pv
0x18007efaf  not     edi
0x18007efb1  shr     edi, 1Fh
0x18007efb4  call    cs:__imp_CoTaskMemFree
0x18007efba  mov     ebx, [rsp+78h+arg_20]
0x18007efc1  mov     rcx, [rsp+78h+lpStringSource]; pv
0x18007efc6  call    cs:__imp_CoTaskMemFree
0x18007efcc  test    r13d, r13d
0x18007efcf  jz      short loc_18007EFFE
0x18007efd1  xor     r13d, r13d
0x18007efd4  bts     ebx, 14h
0x18007efd8  mov     edx, ebx; dwFindNLSStringFlags
0x18007efda  mov     [rsp+78h+pcchFound], r13; pcchFound
0x18007efdf  mov     r9d, esi; cchSource
0x18007efe2  mov     [rsp+78h+cchValue], esi; cchValue
0x18007efe6  mov     r8, r14; lpStringSource
0x18007efe9  mov     ecx, r15d; Locale
0x18007efec  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x18007eff1  call    cs:__imp_FindNLSString
0x18007eff7  mov     edi, eax
0x18007eff9  not     edi
0x18007effb  shr     edi, 1Fh
0x18007effe  lea     r11, [rsp+78h+var_28]
0x18007f003  mov     eax, edi
0x18007f005  mov     rbx, [r11+30h]
0x18007f009  mov     rbp, [r11+38h]
0x18007f00d  mov     rsp, r11
0x18007f010  pop     r15
0x18007f012  pop     r14
0x18007f014  pop     r13
0x18007f016  pop     rdi
0x18007f017  pop     rsi
0x18007f018  retn
```
