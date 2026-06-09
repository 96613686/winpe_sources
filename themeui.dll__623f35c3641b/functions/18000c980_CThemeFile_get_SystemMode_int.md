# CThemeFile::get_SystemMode(int *)

- ea: `0x18000c980`
- end: `0x18000cc24`
- name: `?get_SystemMode@CThemeFile@@UEAAJPEAH@Z`
- size: `676`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x18000c980`
- `0x18000cc2c`
- `0x18000dd60`
- `0x1800358c0`
- `0x18003633c`
- `0x18006d010`

## import_xrefs

- `SHCORE!IsOS` at `0x18000cb04`
- `SHCORE!IsOS` at `0x18000cb04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000caba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cb23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000caba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cb23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cacc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cacc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ca06`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ca06`

## pseudocode

```c
__int64 __fastcall CThemeFile::get_SystemMode(CThemeFile *this, int *a2)
{
  WCHAR *v4; // r15
  __int64 *v5; // rbx
  HRESULT v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v16; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v17[264]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[528]; // [rsp+270h] [rbp+170h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl);
  v4 = 0;
  v16 = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    v6 = -2147467259;
    goto LABEL_13;
  }
  v5 = (__int64 *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    v8 = *((_QWORD *)this + 5);
    v9 = *v5;
    if ( !*((_BYTE *)this + 48) )
    {
      (*(void (__fastcall **)(__int64))(v9 + 8))(v8);
LABEL_22:
      pv = 0;
      if ( (int)StringCchPrintfW(v17, 0x104u, L"%s.MUI", L"SystemMode") >= 0
        && (*(int (__fastcall **)(__int64 *, const WCHAR *, unsigned __int16 *, _QWORD, int, LPVOID *))(*v5 + 48))(
             v5,
             L"VisualStyles",
             v17,
             0,
             1,
             &pv) >= 0
        || (v6 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, const wchar_t *, _QWORD, int, LPVOID *))(*v5 + 48))(
                   v5,
                   L"VisualStyles",
                   L"SystemMode",
                   0,
                   1,
                   &pv),
            v6 >= 0) )
      {
        memset_0(v18, 0, 0x208u);
        v6 = _AllocString<CTCoAllocPolicy>(v13, v12, pv, &v16);
        CoTaskMemFree(pv);
        v4 = v16;
      }
      v10 = *v5;
      goto LABEL_12;
    }
    (*(void (__fastcall **)(__int64))(v9 + 96))(v8);
  }
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
  if ( v6 < 0 )
    goto LABEL_13;
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
         ppv,
         *((_QWORD *)this + 4),
         0x400000);
  if ( v6 >= 0 )
  {
    v7 = *((_QWORD *)this + 5);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v5 = (__int64 *)ppv;
    *((_QWORD *)this + 5) = ppv;
    (*(void (__fastcall **)(__int64 *))(*v5 + 8))(v5);
    *((_BYTE *)this + 48) = 0;
    goto LABEL_22;
  }
  v10 = *(_QWORD *)ppv;
LABEL_12:
  (*(void (**)(void))(v10 + 16))();
LABEL_13:
  if ( v6 < 0 )
  {
    *a2 = IsOS(0x13u);
  }
  else
  {
    if ( CompareStringOrdinal(v4, -1, L"Light", -1, 1) == 2 )
    {
      *a2 = 1;
    }
    else if ( CompareStringOrdinal(v4, -1, L"Dark", -1, 1) == 2 )
    {
      *a2 = 0;
    }
    CoTaskMemFree(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c980  mov     [rsp-8+arg_10], rbx
0x18000c985  mov     [rsp-8+arg_18], rsi
0x18000c98a  push    rbp
0x18000c98b  push    rdi
0x18000c98c  push    r12
0x18000c98e  push    r14
0x18000c990  push    r15
0x18000c992  lea     rbp, [rsp-390h]
0x18000c99a  sub     rsp, 490h
0x18000c9a1  mov     rax, cs:__security_cookie
0x18000c9a8  xor     rax, rsp
0x18000c9ab  mov     [rbp+3B0h+var_30], rax
0x18000c9b2  mov     r12, rdx
0x18000c9b5  mov     rsi, rcx
0x18000c9b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SystemLightTheme@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SystemLightTheme@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme> `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl(void)'::`2'::impl
0x18000c9bf  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SystemLightTheme@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000c9c4  xor     r15d, r15d
0x18000c9c7  mov     [rsp+4B0h+var_460], r15
0x18000c9cc  cmp     [rsi+20h], r15
0x18000c9d0  jz      loc_18000CA83
0x18000c9d6  mov     rbx, [rsi+28h]
0x18000c9da  test    rbx, rbx
0x18000c9dd  jnz     loc_18000CA65
0x18000c9e3  xor     edx, edx; pUnkOuter
0x18000c9e5  mov     [rsp+4B0h+var_468], r15
0x18000c9ea  lea     rax, [rsp+4B0h+var_468]
0x18000c9ef  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x18000c9f6  mov     [rsp+4B0h+ppv], rax; ppv
0x18000c9fb  lea     rcx, CLSID_PrivateProfile; rclsid
0x18000ca02  lea     r8d, [rdx+1]; dwClsContext
0x18000ca06  call    cs:__imp_CoCreateInstance
0x18000ca0c  mov     edi, eax
0x18000ca0e  test    eax, eax
0x18000ca10  js      loc_18000CA9B
0x18000ca16  mov     rcx, [rsp+4B0h+var_468]
0x18000ca1b  mov     r8d, 400000h
0x18000ca21  mov     rdx, [rsi+20h]
0x18000ca25  mov     rax, [rcx]
0x18000ca28  mov     rax, [rax+18h]
0x18000ca2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca31  mov     edi, eax
0x18000ca33  test    eax, eax
0x18000ca35  js      short loc_18000CA8A
0x18000ca37  mov     rcx, [rsi+28h]
0x18000ca3b  test    rcx, rcx
0x18000ca3e  jnz     loc_18000CB38
0x18000ca44  mov     rbx, [rsp+4B0h+var_468]
0x18000ca49  mov     [rsi+28h], rbx
0x18000ca4d  mov     rcx, rbx
0x18000ca50  mov     rax, [rbx]
0x18000ca53  mov     rax, [rax+8]
0x18000ca57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca5c  mov     [rsi+30h], r15b
0x18000ca60  jmp     loc_18000CB52
0x18000ca65  mov     rcx, rbx
0x18000ca68  mov     rax, [rbx]
0x18000ca6b  cmp     [rsi+30h], r15b
0x18000ca6f  jz      loc_18000CB49
0x18000ca75  mov     rax, [rax+60h]
0x18000ca79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca7e  jmp     loc_18000C9E3
0x18000ca83  mov     edi, 80004005h
0x18000ca88  jmp     short loc_18000CA9B
0x18000ca8a  mov     rcx, [rsp+4B0h+var_468]
0x18000ca8f  mov     rax, [rcx]
0x18000ca92  mov     rax, [rax+10h]
0x18000ca96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca9b  test    edi, edi
0x18000ca9d  js      short loc_18000CAFF
0x18000ca9f  or      ebx, 0FFFFFFFFh
0x18000caa2  lea     r8, aLight; "Light"
0x18000caa9  mov     edi, 1
0x18000caae  mov     r9d, ebx; cchCount2
0x18000cab1  mov     edx, ebx; cchCount1
0x18000cab3  mov     dword ptr [rsp+4B0h+ppv], edi; bIgnoreCase
0x18000cab7  mov     rcx, r15; lpString1
0x18000caba  call    cs:__imp_CompareStringOrdinal
0x18000cac0  cmp     eax, 2
0x18000cac3  jnz     short loc_18000CB10
0x18000cac5  mov     [r12], edi
0x18000cac9  mov     rcx, r15; pv
0x18000cacc  call    cs:__imp_CoTaskMemFree
0x18000cad2  xor     eax, eax
0x18000cad4  mov     rcx, [rbp+3B0h+var_30]
0x18000cadb  xor     rcx, rsp; StackCookie
0x18000cade  call    __security_check_cookie
0x18000cae3  lea     r11, [rsp+4B0h+var_20]
0x18000caeb  mov     rbx, [r11+40h]
0x18000caef  mov     rsi, [r11+48h]
0x18000caf3  mov     rsp, r11
0x18000caf6  pop     r15
0x18000caf8  pop     r14
0x18000cafa  pop     r12
0x18000cafc  pop     rdi
0x18000cafd  pop     rbp
0x18000cafe  retn
0x18000caff  mov     ecx, 13h; dwOS
0x18000cb04  call    cs:__imp_IsOS
0x18000cb0a  mov     [r12], eax
0x18000cb0e  jmp     short loc_18000CAD2
0x18000cb10  mov     r9d, ebx; cchCount2
0x18000cb13  mov     dword ptr [rsp+4B0h+ppv], edi; bIgnoreCase
0x18000cb17  lea     r8, aDark_0; "Dark"
0x18000cb1e  mov     edx, ebx; cchCount1
0x18000cb20  mov     rcx, r15; lpString1
0x18000cb23  call    cs:__imp_CompareStringOrdinal
0x18000cb29  cmp     eax, 2
0x18000cb2c  jnz     short loc_18000CAC9
0x18000cb2e  mov     dword ptr [r12], 0
0x18000cb36  jmp     short loc_18000CAC9
0x18000cb38  mov     rax, [rcx]
0x18000cb3b  mov     rax, [rax+10h]
0x18000cb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb44  jmp     loc_18000CA44
0x18000cb49  mov     rax, [rax+8]
0x18000cb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb52  lea     r9, aSystemmode; "SystemMode"
0x18000cb59  mov     [rsp+4B0h+pv], r15
0x18000cb5e  lea     r8, aSMui; "%s.MUI"
0x18000cb65  mov     edx, 104h; unsigned __int64
0x18000cb6a  lea     rcx, [rsp+4B0h+var_450]; unsigned __int16 *
0x18000cb6f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cb74  test    eax, eax
0x18000cb76  js      short loc_18000CBAC
0x18000cb78  mov     rax, [rbx]
0x18000cb7b  lea     rcx, [rsp+4B0h+pv]
0x18000cb80  mov     [rsp+4B0h+var_488], rcx
0x18000cb85  lea     r8, [rsp+4B0h+var_450]
0x18000cb8a  xor     r9d, r9d
0x18000cb8d  mov     dword ptr [rsp+4B0h+ppv], 1
0x18000cb95  lea     rdx, aVisualstyles; "VisualStyles"
0x18000cb9c  mov     rcx, rbx
0x18000cb9f  mov     rax, [rax+30h]
0x18000cba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cba8  test    eax, eax
0x18000cbaa  jns     short loc_18000CBE4
0x18000cbac  mov     rax, [rbx]
0x18000cbaf  lea     rcx, [rsp+4B0h+pv]
0x18000cbb4  mov     [rsp+4B0h+var_488], rcx
0x18000cbb9  lea     r8, aSystemmode; "SystemMode"
0x18000cbc0  xor     r9d, r9d
0x18000cbc3  mov     dword ptr [rsp+4B0h+ppv], 1
0x18000cbcb  lea     rdx, aVisualstyles; "VisualStyles"
0x18000cbd2  mov     rcx, rbx
0x18000cbd5  mov     rax, [rax+30h]
0x18000cbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbde  mov     edi, eax
0x18000cbe0  test    eax, eax
0x18000cbe2  js      short loc_18000CC19
0x18000cbe4  xor     edx, edx; Val
0x18000cbe6  lea     rcx, [rbp+3B0h+var_240]; void *
0x18000cbed  mov     r8d, 208h; Size
0x18000cbf3  call    memset_0
0x18000cbf8  mov     r8, [rsp+4B0h+pv]
0x18000cbfd  lea     r9, [rsp+4B0h+var_460]
0x18000cc02  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000cc07  mov     rcx, [rsp+4B0h+pv]; pv
0x18000cc0c  mov     edi, eax
0x18000cc0e  call    cs:__imp_CoTaskMemFree
0x18000cc14  mov     r15, [rsp+4B0h+var_460]
0x18000cc19  mov     rax, [rbx]
0x18000cc1c  mov     rcx, rbx
0x18000cc1f  jmp     loc_18000CA92
```
