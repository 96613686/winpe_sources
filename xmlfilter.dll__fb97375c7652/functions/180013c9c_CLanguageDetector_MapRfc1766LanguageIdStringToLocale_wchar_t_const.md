# CLanguageDetector::MapRfc1766LanguageIdStringToLocale(wchar_t const *)

- ea: `0x180013c9c`
- end: `0x180013d98`
- name: `?MapRfc1766LanguageIdStringToLocale@CLanguageDetector@@QEAAKPEB_W@Z`
- size: `252`
- prototype: `__int64 __fastcall(CLanguageDetector *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f7e0`

## callees

- `0x180005f70`
- `0x180013c9c`
- `0x180014234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180013cd5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180013cd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d15`

## string_xrefs

- `0x180013d72`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\languagedetector.cpp"`
- `0x180013d66`: `[XmlFilter Language Detector] CLCIDToLocaleNameConverter::LocaleNameToLCID(): Could not map language string %s`

## pseudocode

```c
__int64 __fastcall CLanguageDetector::MapRfc1766LanguageIdStringToLocale(CLanguageDetector *this, const wchar_t *a2)
{
  int v4; // esi
  __int64 v5; // rcx
  unsigned int v6; // r14d
  wchar_t *v7; // rdi
  unsigned int v8; // eax
  __int64 v9; // rcx
  wchar_t v10; // dx
  unsigned int v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = 0;
  if ( !a2 || !*a2 || !(unsigned int)_o__wcsnicmp(L"Neutral", a2, 8) )
    return 0;
  v4 = CLCIDToLocaleNameConverter::LocaleNameToLCIDHelper(this, a2, &v12);
  if ( v4 >= 0 )
    return v12;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  v7 = (wchar_t *)CoTaskMemAlloc(2LL * (unsigned int)(v5 + 1));
  v8 = 0;
  if ( v6 )
  {
    while ( 1 )
    {
      v9 = v8;
      v10 = a2[v8];
      if ( v10 == 45 )
        break;
      ++v8;
      v7[v9] = v10;
      if ( v8 >= v6 )
        goto LABEL_12;
    }
    v7[v8] = 0;
    v4 = CLCIDToLocaleNameConverter::LocaleNameToLCIDHelper(this, v7, &v12);
  }
LABEL_12:
  CoTaskMemFree(v7);
  if ( v4 >= 0 )
    return v12;
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\languagedetector.cpp\"",
    (const wchar_t *)0x6A,
    (__int64)L"[XmlFilter Language Detector] CLCIDToLocaleNameConverter::LocaleNameToLCID(): Could not map language string %s",
    a2);
  return 0;
}

```

## disassembly

```asm
0x180013c9c  push    rbx
0x180013c9e  push    rbp
0x180013c9f  push    rsi
0x180013ca0  push    rdi
0x180013ca1  push    r14
0x180013ca3  push    r15
0x180013ca5  sub     rsp, 28h
0x180013ca9  xor     r15d, r15d
0x180013cac  mov     rbx, rdx
0x180013caf  mov     [rsp+58h+arg_8], r15d
0x180013cb4  mov     rbp, rcx
0x180013cb7  test    rdx, rdx
0x180013cba  jz      loc_180013D89
0x180013cc0  cmp     r15w, [rdx]
0x180013cc4  jz      loc_180013D89
0x180013cca  lea     r8d, [r15+8]
0x180013cce  lea     rcx, aNeutral; "Neutral"
0x180013cd5  call    cs:__imp__o__wcsnicmp
0x180013cdb  test    eax, eax
0x180013cdd  jz      loc_180013D89
0x180013ce3  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x180013ce8  mov     rdx, rbx; wchar_t *
0x180013ceb  mov     rcx, rbp; this
0x180013cee  call    ?LocaleNameToLCIDHelper@CLCIDToLocaleNameConverter@@AEAAJPEB_WPEAK@Z; CLCIDToLocaleNameConverter::LocaleNameToLCIDHelper(wchar_t const *,ulong *)
0x180013cf3  mov     esi, eax
0x180013cf5  test    eax, eax
0x180013cf7  jns     loc_180013D83
0x180013cfd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013d01  inc     rcx
0x180013d04  cmp     [rbx+rcx*2], r15w
0x180013d09  jnz     short loc_180013D01
0x180013d0b  lea     r14d, [rcx+1]
0x180013d0f  mov     ecx, r14d
0x180013d12  add     rcx, rcx; cb
0x180013d15  call    cs:__imp_CoTaskMemAlloc
0x180013d1b  mov     rdi, rax
0x180013d1e  mov     eax, r15d
0x180013d21  test    r14d, r14d
0x180013d24  jz      short loc_180013D56
0x180013d26  mov     ecx, eax
0x180013d28  movzx   edx, word ptr [rbx+rcx*2]
0x180013d2c  cmp     dx, 2Dh ; '-'
0x180013d30  jz      short loc_180013D3F
0x180013d32  inc     eax
0x180013d34  mov     [rdi+rcx*2], dx
0x180013d38  cmp     eax, r14d
0x180013d3b  jb      short loc_180013D26
0x180013d3d  jmp     short loc_180013D56
0x180013d3f  mov     [rdi+rcx*2], r15w
0x180013d44  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x180013d49  mov     rcx, rbp; this
0x180013d4c  mov     rdx, rdi; wchar_t *
0x180013d4f  call    ?LocaleNameToLCIDHelper@CLCIDToLocaleNameConverter@@AEAAJPEB_WPEAK@Z; CLCIDToLocaleNameConverter::LocaleNameToLCIDHelper(wchar_t const *,ulong *)
0x180013d54  mov     esi, eax
0x180013d56  mov     rcx, rdi; pv
0x180013d59  call    cs:__imp_CoTaskMemFree
0x180013d5f  test    esi, esi
0x180013d61  jns     short loc_180013D83
0x180013d63  mov     r9, rbx; wchar_t *
0x180013d66  lea     r8, aXmlfilterLangu_0; "[XmlFilter Language Detector] CLCIDToLo"...
0x180013d6d  mov     edx, 6Ah ; 'j'; wchar_t *
0x180013d72  lea     rcx, aOnecoreuapBase_7; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180013d79  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180013d7e  mov     eax, r15d
0x180013d81  jmp     short loc_180013D8B
0x180013d83  mov     eax, [rsp+58h+arg_8]
0x180013d87  jmp     short loc_180013D8B
0x180013d89  xor     eax, eax
0x180013d8b  add     rsp, 28h
0x180013d8f  pop     r15
0x180013d91  pop     r14
0x180013d93  pop     rdi
0x180013d94  pop     rsi
0x180013d95  pop     rbp
0x180013d96  pop     rbx
0x180013d97  retn
```
