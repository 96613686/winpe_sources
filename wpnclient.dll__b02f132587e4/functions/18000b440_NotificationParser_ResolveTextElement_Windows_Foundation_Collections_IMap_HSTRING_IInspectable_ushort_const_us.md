# NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000b440`
- end: `0x18000bbdf`
- name: `?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z`
- size: `1951`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180016334`
- `0x180018d90`
- `0x180019b4c`
- `0x18001acfc`
- `0x18001afb0`
- `0x18001dc28`
- `0x18002d280`

## callees

- `0x180005670`
- `0x18000735c`
- `0x18000b440`
- `0x18000c718`
- `0x1800180cc`
- `0x18001b848`
- `0x18001ff00`
- `0x180020d34`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b526`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b601`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b68b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b8ba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b938`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b526`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b601`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b68b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b8ba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b938`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b76e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b69e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b8cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b94c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b69e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b8cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b94c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b727`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ba28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b727`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ba28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b6f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b9ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b9f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b6f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b9ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b9f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b7b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b7b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
HRESULT __fastcall NotificationParser::ResolveTextElement(_QWORD *a1, __int64 a2, const WCHAR *a3, __int64 a4)
{
  _QWORD *v7; // rbx
  __int64 v8; // r12
  unsigned __int64 v9; // r14
  __int64 v10; // r12
  PCWSTR StringRawBuffer; // r15
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 *); // rdi
  unsigned __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 (__fastcall *v19)(__int64, HSTRING, char *); // r15
  WCHAR *v20; // rdi
  unsigned __int64 v21; // rbx
  __int64 v22; // rbx
  int v23; // eax
  __int64 (__fastcall *v24)(__int64, HSTRING, __int64, char *); // r15
  WCHAR *v25; // rdi
  unsigned __int64 v26; // rbx
  __int64 v27; // r8
  int v28; // eax
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // eax
  const WCHAR *v31; // rax
  const OLECHAR *v32; // rdi
  unsigned __int64 v33; // rbx
  __int64 v34; // rcx
  int v35; // r9d
  unsigned __int64 v36; // rbx
  unsigned __int64 v37; // r15
  int v38; // r12d
  __int64 v39; // r11
  const OLECHAR *v40; // rcx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // r8
  OLECHAR *v43; // r9
  __int64 v44; // r10
  OLECHAR v45; // dx
  __int64 v46; // rdx
  OLECHAR *v47; // rcx
  __int64 v48; // r15
  bool v49; // cf
  __int64 v50; // r15
  __int64 (__fastcall *v51)(__int64, HSTRING, __int64 *); // r12
  const WCHAR *v52; // rdi
  unsigned __int64 v53; // rbx
  int v54; // eax
  __int64 v55; // r15
  __int64 (__fastcall *v56)(__int64, HSTRING, __int64, char *); // rdi
  __int64 v57; // rbx
  int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, HSTRING *); // rbx
  int v62; // eax
  int v63; // eax
  int v64; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-91h]
  WCHAR *bIgnoreCasea; // [rsp+20h] [rbp-91h]
  char v67; // [rsp+30h] [rbp-81h] BYREF
  char v68[7]; // [rsp+31h] [rbp-80h] BYREF
  __int64 v69; // [rsp+38h] [rbp-79h]
  __int64 v70; // [rsp+40h] [rbp-71h] BYREF
  HSTRING v71; // [rsp+48h] [rbp-69h] BYREF
  struct IWpnMrtHelper *v72; // [rsp+50h] [rbp-61h] BYREF
  _QWORD *v73; // [rsp+58h] [rbp-59h]
  __int64 v74; // [rsp+60h] [rbp-51h] BYREF
  HSTRING v75; // [rsp+68h] [rbp-49h] BYREF
  __int64 v76; // [rsp+70h] [rbp-41h] BYREF
  WCHAR sourceString[8]; // [rsp+78h] [rbp-39h] BYREF
  __int128 v78; // [rsp+88h] [rbp-29h]
  HSTRING string; // [rsp+98h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v69 = a2;
  v7 = a1;
  v73 = a1;
  v8 = a1[1];
  *(_OWORD *)sourceString = 0;
  v78 = 0;
  std::wstring::_Construct<1,unsigned short const *>(sourceString, L"lang", 4);
  v68[0] = 0;
  v9 = -1;
  if ( !v8 )
    goto LABEL_2;
  v19 = *(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)a2 + 64LL);
  if ( *((_QWORD *)&v78 + 1) > 7u )
    v20 = *(WCHAR **)sourceString;
  else
    v20 = sourceString;
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  if ( v21 > 0xFFFFFFFF )
  {
    LODWORD(v21) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v20, v21, &hstringHeader, &string);
  v22 = v69;
  v23 = v19(v69, string, v68);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3AA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v23,
      bIgnoreCase);
  if ( v68[0] )
  {
    v7 = v73;
LABEL_2:
    v10 = v69;
    goto LABEL_3;
  }
  v67 = 0;
  v24 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v22 + 80LL);
  if ( *((_QWORD *)&v78 + 1) > 7u )
    v25 = *(WCHAR **)sourceString;
  else
    v25 = sourceString;
  v26 = -1;
  do
    ++v26;
  while ( v25[v26] );
  if ( v26 > 0xFFFFFFFF )
  {
    LODWORD(v26) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v25, v26, &hstringHeader, &string);
  v27 = v8;
  v10 = v69;
  v28 = v24(v69, string, v27, &v67);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v28,
      bIgnoreCase);
  v7 = v73;
LABEL_3:
  StringRawBuffer = 0;
  if ( *((_QWORD *)&v78 + 1) > 7u )
    std::_Deallocate<16>(*(_QWORD *)sourceString, 2LL * *((_QWORD *)&v78 + 1) + 2);
  v71 = 0;
  v76 = 0;
  v12 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))v7[1];
  if ( v12 && (**v12)(v12, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v76) >= 0 )
  {
    v60 = v76;
    v61 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v76 + 152LL);
    WindowsDeleteString(v71);
    v71 = 0;
    v62 = v61(v60, &v71);
    if ( v62 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x700,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v62,
        bIgnoreCase);
    StringRawBuffer = WindowsGetStringRawBuffer(v71, 0);
  }
  v70 = 0;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v10 + 48LL);
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  if ( v14 > 0xFFFFFFFF )
  {
    LODWORD(v14) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a3, v14, &hstringHeader, &string);
  v15 = v13(v10, string, &v70);
  v16 = v70;
  if ( v15 >= 0 && v70 )
  {
    v75 = 0;
    v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v70 + 152LL);
    WindowsDeleteString(0);
    v75 = 0;
    v30 = v29(v16, &v75);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v30,
        bIgnoreCase);
    *(_QWORD *)sourceString = 0;
    *(_QWORD *)&sourceString[4] = -1;
    *(_QWORD *)&v78 = -1;
    v31 = WindowsGetStringRawBuffer(v75, 0);
    v32 = v31;
    v33 = v73[4];
    *(_QWORD *)sourceString = 0;
    v34 = -1;
    do
      ++v34;
    while ( v31[v34] );
    v35 = 12;
    if ( (int)v34 < 12 )
      v35 = v34;
    if ( CompareStringOrdinal(L"ms-resource:", 12, v31, v35, 1) == 2 )
    {
      v72 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      v63 = CreateMrtHelper(v33, &v72);
      if ( v63 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
          (const char *)(unsigned int)v63,
          (int)bIgnoreCasea);
      bIgnoreCasea = sourceString;
      v64 = (*(__int64 (__fastcall **)(struct IWpnMrtHelper *, const OLECHAR *, __int64, PCWSTR))(*(_QWORD *)v72 + 24LL))(
              v72,
              v32,
              a4,
              StringRawBuffer);
      if ( v64 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
          (const char *)(unsigned int)v64,
          (int)sourceString);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
    }
    else
    {
      v36 = -1;
      do
        ++v36;
      while ( v32[v36] );
      *(_QWORD *)sourceString = 0;
      v37 = v36 + 1;
      if ( v36 + 1 < v36 )
      {
        v38 = -2147024362;
      }
      else
      {
        *(_QWORD *)sourceString = 0;
        if ( is_mul_ok(v37, 2u) )
        {
          *(_QWORD *)sourceString = CoTaskMemAlloc(2 * v37);
          v38 = -2147024882;
          if ( *(_QWORD *)sourceString )
            v38 = 0;
        }
        else
        {
          v38 = -2147024362;
        }
        if ( v38 >= 0 )
        {
          v39 = *(_QWORD *)sourceString;
          if ( (*(_QWORD *)sourceString || v36 == -1) && v37 <= 0x7FFFFFFF )
          {
            if ( v36 >= 0x7FFFFFFF )
            {
              if ( v36 != -1 )
                **(_WORD **)sourceString = 0;
            }
            else
            {
              v40 = &pwzBaseUrl;
              if ( v32 )
                v40 = v32;
              v41 = 0;
              if ( v32 )
                v41 = v36;
              v42 = v36 + 1;
              v43 = *(OLECHAR **)sourceString;
              v44 = 0;
              do
              {
                if ( !v41 )
                  break;
                v45 = *v40;
                if ( !*v40 )
                  break;
                ++v40;
                *v43++ = v45;
                --v41;
                ++v44;
                --v42;
              }
              while ( v42 );
              v46 = v44 - 1;
              if ( v42 )
                v46 = v44;
              v47 = v43 - 1;
              if ( v42 )
                v47 = v43;
              *v47 = 0;
              if ( v42 )
              {
                v49 = v37 == v46;
                v48 = v37 - v46;
                if ( !v49 && v48 != 1 && (unsigned __int64)(2 * v48) > 2 )
                  memset_0((void *)(v39 + 2 + 2 * v46), 0, 2 * v48 - 2);
              }
            }
          }
          else
          {
            **(_WORD **)sourceString = 0;
          }
        }
      }
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
          (const char *)(unsigned int)v38,
          (int)bIgnoreCasea);
    }
    v74 = 0;
    v50 = *v73;
    v51 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*v73 + 144LL);
    v52 = *(const WCHAR **)sourceString;
    v53 = -1;
    do
      ++v53;
    while ( *(_WORD *)(*(_QWORD *)sourceString + 2 * v53) );
    if ( v53 > 0xFFFFFFFF )
    {
      LODWORD(v53) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v52, v53, &hstringHeader, &string);
    v54 = v51(v50, string, &v74);
    if ( v54 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x712,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v54,
        (int)bIgnoreCasea);
    v67 = 0;
    v55 = v69;
    v56 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v69 + 80LL);
    v57 = v74;
    do
      ++v9;
    while ( a3[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      LODWORD(v9) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(a3, v9, &hstringHeader, &string);
    v58 = v56(v55, string, v57, &v67);
    if ( v58 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x715,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v58,
        (int)bIgnoreCasea);
    v59 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    if ( *(_QWORD *)sourceString )
    {
      CoTaskMemFree(*(LPVOID *)sourceString);
      *(_QWORD *)sourceString = 0;
    }
    *(_QWORD *)&sourceString[4] = 0;
    *(_QWORD *)&v78 = 0;
    WindowsDeleteString(v75);
    v16 = v70;
  }
  if ( v16 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return WindowsDeleteString(v71);
}

```

## disassembly

```asm
0x18000b440  push    rbp
0x18000b442  push    rbx
0x18000b443  push    rsi
0x18000b444  push    rdi
0x18000b445  push    r12
0x18000b447  push    r13
0x18000b449  push    r14
0x18000b44b  push    r15
0x18000b44d  lea     rbp, [rsp-17h]
0x18000b452  sub     rsp, 0C8h
0x18000b459  mov     rax, cs:__security_cookie
0x18000b460  xor     rax, rsp
0x18000b463  mov     [rbp+4Fh+var_48], rax
0x18000b467  mov     r13, r9
0x18000b46a  mov     rsi, r8
0x18000b46d  mov     rdi, rdx
0x18000b470  mov     [rbp+4Fh+var_C8], rdx
0x18000b474  mov     rbx, rcx
0x18000b477  mov     [rbp+4Fh+var_A8], rcx
0x18000b47b  mov     r12, [rcx+8]
0x18000b47f  xorps   xmm0, xmm0
0x18000b482  movups  xmmword ptr [rbp+4Fh+sourceString], xmm0
0x18000b486  xorps   xmm1, xmm1
0x18000b489  movdqu  [rbp+4Fh+var_78], xmm1
0x18000b48e  mov     r8d, 4
0x18000b494  lea     rdx, aLang; "lang"
0x18000b49b  lea     rcx, [rbp+4Fh+sourceString]
0x18000b49f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000b4a4  nop
0x18000b4a5  mov     [rbp+4Fh+var_CF], 0
0x18000b4a9  mov     ecx, 0FFFFFFFFh
0x18000b4ae  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000b4b5  test    r12, r12
0x18000b4b8  jnz     loc_18000B5BE
0x18000b4be  mov     r12, [rbp+4Fh+var_C8]
0x18000b4c2  xor     edi, edi
0x18000b4c4  mov     r15d, edi
0x18000b4c7  mov     rdx, qword ptr [rbp+4Fh+var_78+8]
0x18000b4cb  cmp     rdx, 7
0x18000b4cf  ja      loc_18000BAFE
0x18000b4d5  mov     [rbp+4Fh+var_B8], rdi
0x18000b4d9  mov     [rbp+4Fh+var_90], rdi
0x18000b4dd  mov     rcx, [rbx+8]
0x18000b4e1  test    rcx, rcx
0x18000b4e4  jnz     loc_18000B9C8
0x18000b4ea  mov     [rbp+4Fh+var_C0], rdi
0x18000b4ee  mov     rcx, [r12]
0x18000b4f2  mov     rdi, [rcx+30h]
0x18000b4f6  mov     rbx, r14
0x18000b4f9  nop     dword ptr [rax+00000000h]
0x18000b500  inc     rbx
0x18000b503  cmp     word ptr [rsi+rbx*2], 0
0x18000b508  jnz     short loc_18000B500
0x18000b50a  mov     eax, 0FFFFFFFFh
0x18000b50f  cmp     rbx, rax
0x18000b512  jbe     short loc_18000B52C
0x18000b514  mov     ebx, eax
0x18000b516  xor     r9d, r9d; lpArguments
0x18000b519  xor     r8d, r8d; nNumberOfArguments
0x18000b51c  mov     edx, 1; dwExceptionFlags
0x18000b521  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000b526  call    cs:__imp_RaiseException
0x18000b52c  lea     r9, [rbp+4Fh+string]; string
0x18000b530  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x18000b534  mov     edx, ebx; length
0x18000b536  mov     rcx, rsi; sourceString
0x18000b539  call    cs:__imp_WindowsCreateStringReference
0x18000b53f  lea     r8, [rbp+4Fh+var_C0]
0x18000b543  mov     rdx, [rbp+4Fh+string]
0x18000b547  mov     rcx, r12
0x18000b54a  mov     rax, rdi
0x18000b54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b552  mov     rdi, [rbp+4Fh+var_C0]
0x18000b556  test    eax, eax
0x18000b558  jns     loc_18000B6D4
0x18000b55e  xor     r13d, r13d
0x18000b561  test    rdi, rdi
0x18000b564  jz      short loc_18000B57A
0x18000b566  mov     [rbp+4Fh+var_C0], r13
0x18000b56a  mov     rax, [rdi]
0x18000b56d  mov     rcx, rdi
0x18000b570  mov     rax, [rax+10h]
0x18000b574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b579  nop
0x18000b57a  mov     rcx, [rbp+4Fh+var_90]
0x18000b57e  test    rcx, rcx
0x18000b581  jz      short loc_18000B594
0x18000b583  mov     [rbp+4Fh+var_90], r13
0x18000b587  mov     rax, [rcx]
0x18000b58a  mov     rax, [rax+10h]
0x18000b58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b593  nop
0x18000b594  mov     rcx, [rbp+4Fh+var_B8]; string
0x18000b598  call    cs:__imp_WindowsDeleteString
0x18000b59e  mov     rcx, [rbp+4Fh+var_48]
0x18000b5a2  xor     rcx, rsp; StackCookie
0x18000b5a5  call    __security_check_cookie
0x18000b5aa  add     rsp, 0C8h
0x18000b5b1  pop     r15
0x18000b5b3  pop     r14
0x18000b5b5  pop     r13
0x18000b5b7  pop     r12
0x18000b5b9  pop     rdi
0x18000b5ba  pop     rsi
0x18000b5bb  pop     rbx
0x18000b5bc  pop     rbp
0x18000b5bd  retn
0x18000b5be  mov     rax, [rdi]
0x18000b5c1  mov     r15, [rax+40h]
0x18000b5c5  cmp     qword ptr [rbp+4Fh+var_78+8], 7
0x18000b5ca  ja      loc_18000BAC2
0x18000b5d0  lea     rdi, [rbp+4Fh+sourceString]
0x18000b5d4  mov     rbx, r14
0x18000b5d7  nop     word ptr [rax+rax+00000000h]
0x18000b5e0  inc     rbx
0x18000b5e3  cmp     word ptr [rdi+rbx*2], 0
0x18000b5e8  jnz     short loc_18000B5E0
0x18000b5ea  cmp     rbx, rcx
0x18000b5ed  jbe     short loc_18000B607
0x18000b5ef  mov     ebx, ecx
0x18000b5f1  xor     r9d, r9d; lpArguments
0x18000b5f4  xor     r8d, r8d; nNumberOfArguments
0x18000b5f7  mov     edx, 1; dwExceptionFlags
0x18000b5fc  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000b601  call    cs:__imp_RaiseException
0x18000b607  lea     r9, [rbp+4Fh+string]; string
0x18000b60b  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x18000b60f  mov     edx, ebx; length
0x18000b611  mov     rcx, rdi; sourceString
0x18000b614  call    cs:__imp_WindowsCreateStringReference
0x18000b61a  lea     r8, [rbp+4Fh+var_CF]
0x18000b61e  mov     rdx, [rbp+4Fh+string]
0x18000b622  mov     rbx, [rbp+4Fh+var_C8]
0x18000b626  mov     rcx, rbx
0x18000b629  mov     rax, r15
0x18000b62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b631  mov     rcx, [rbp+57h]; this
0x18000b635  test    eax, eax
0x18000b637  js      loc_18000BACB
0x18000b63d  cmp     [rbp+4Fh+var_CF], 0
0x18000b641  jnz     loc_18000BA55
0x18000b647  mov     [rsp+100h+var_D0], 0
0x18000b64c  mov     rax, [rbx]
0x18000b64f  mov     r15, [rax+50h]
0x18000b653  cmp     qword ptr [rbp+4Fh+var_78+8], 7
0x18000b658  ja      loc_18000BAE0
0x18000b65e  lea     rdi, [rbp+4Fh+sourceString]
0x18000b662  mov     rbx, r14
0x18000b665  inc     rbx
0x18000b668  cmp     word ptr [rdi+rbx*2], 0
0x18000b66d  jnz     short loc_18000B665
0x18000b66f  mov     eax, 0FFFFFFFFh
0x18000b674  cmp     rbx, rax
0x18000b677  jbe     short loc_18000B691
0x18000b679  mov     ebx, eax
0x18000b67b  xor     r9d, r9d; lpArguments
0x18000b67e  xor     r8d, r8d; nNumberOfArguments
0x18000b681  mov     edx, 1; dwExceptionFlags
0x18000b686  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000b68b  call    cs:__imp_RaiseException
0x18000b691  lea     r9, [rbp+4Fh+string]; string
0x18000b695  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x18000b699  mov     edx, ebx; length
0x18000b69b  mov     rcx, rdi; sourceString
0x18000b69e  call    cs:__imp_WindowsCreateStringReference
0x18000b6a4  lea     r9, [rsp+100h+var_D0]
0x18000b6a9  mov     r8, r12
0x18000b6ac  mov     rdx, [rbp+4Fh+string]
0x18000b6b0  mov     r12, [rbp+4Fh+var_C8]
0x18000b6b4  mov     rcx, r12
0x18000b6b7  mov     rax, r15
0x18000b6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6bf  mov     rcx, [rbp+57h]; this
0x18000b6c3  test    eax, eax
0x18000b6c5  js      loc_18000BAE9
0x18000b6cb  mov     rbx, [rbp+4Fh+var_A8]
0x18000b6cf  jmp     loc_18000B4C2
0x18000b6d4  test    rdi, rdi
0x18000b6d7  jz      loc_18000B55E
0x18000b6dd  xor     r12d, r12d
0x18000b6e0  mov     [rbp+4Fh+var_98], r12
0x18000b6e4  mov     rax, [rdi]
0x18000b6e7  mov     rbx, [rax+98h]
0x18000b6ee  xor     ecx, ecx; string
0x18000b6f0  call    cs:__imp_WindowsDeleteString
0x18000b6f6  mov     [rbp+4Fh+var_98], r12
0x18000b6fa  lea     rdx, [rbp+4Fh+var_98]
0x18000b6fe  mov     rcx, rdi
0x18000b701  mov     rax, rbx
0x18000b704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b709  mov     rcx, [rbp+57h]; this
0x18000b70d  test    eax, eax
0x18000b70f  js      loc_18000BB29
0x18000b715  mov     qword ptr [rbp+4Fh+sourceString], r12
0x18000b719  mov     qword ptr [rbp+4Fh+sourceString+8], r14
0x18000b71d  mov     qword ptr [rbp+4Fh+var_78], r14
0x18000b721  xor     edx, edx; length
0x18000b723  mov     rcx, [rbp+4Fh+var_98]; string
0x18000b727  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b72d  mov     rdi, rax
0x18000b730  mov     rbx, [rbp+4Fh+var_A8]
0x18000b734  mov     rbx, [rbx+20h]
0x18000b738  mov     qword ptr [rbp+4Fh+sourceString], r12
0x18000b73c  mov     rcx, r14
0x18000b73f  nop
0x18000b740  inc     rcx
0x18000b743  cmp     word ptr [rax+rcx*2], 0
0x18000b748  jnz     short loc_18000B740
0x18000b74a  mov     r9d, 0Ch
0x18000b750  cmp     ecx, r9d
0x18000b753  cmovl   r9d, ecx; cchCount2
0x18000b757  mov     [rsp+100h+bIgnoreCase], 1; int
0x18000b75f  mov     r8, rdi; lpString2
0x18000b762  mov     edx, 0Ch; cchCount1
0x18000b767  lea     rcx, String1; "ms-resource:"
0x18000b76e  call    cs:__imp_CompareStringOrdinal
0x18000b774  cmp     eax, 2
0x18000b777  jz      loc_18000BA5E
0x18000b77d  mov     rbx, r14
0x18000b780  inc     rbx
0x18000b783  cmp     word ptr [rdi+rbx*2], 0
0x18000b788  jnz     short loc_18000B780
0x18000b78a  xor     r13d, r13d
0x18000b78d  mov     qword ptr [rbp+4Fh+sourceString], r13
0x18000b791  lea     r15, [rbx+1]
0x18000b795  cmp     r15, rbx
0x18000b798  jb      loc_18000B9BD
0x18000b79e  mov     qword ptr [rbp+4Fh+sourceString], r13
0x18000b7a2  mov     eax, 2
0x18000b7a7  mul     r15
0x18000b7aa  test    rdx, rdx
0x18000b7ad  jnz     loc_18000BA38
0x18000b7b3  mov     rcx, rax; cb
0x18000b7b6  call    cs:__imp_CoTaskMemAlloc
0x18000b7bc  mov     qword ptr [rbp+4Fh+sourceString], rax
0x18000b7c0  mov     r12d, 8007000Eh
0x18000b7c6  test    rax, rax
0x18000b7c9  cmovnz  r12d, r13d
0x18000b7cd  test    r12d, r12d
0x18000b7d0  js      loc_18000B86B
0x18000b7d6  mov     r11, qword ptr [rbp+4Fh+sourceString]
0x18000b7da  test    r11, r11
0x18000b7dd  jz      loc_18000BB68
0x18000b7e3  cmp     r15, 7FFFFFFFh
0x18000b7ea  ja      loc_18000BB71
0x18000b7f0  cmp     rbx, 7FFFFFFFh
0x18000b7f7  jnb     loc_18000BA43
0x18000b7fd  lea     rcx, pwzBaseUrl
0x18000b804  test    rdi, rdi
0x18000b807  cmovnz  rcx, rdi
0x18000b80b  mov     rax, r13
0x18000b80e  cmovnz  rax, rbx
0x18000b812  test    r15, r15
0x18000b815  jz      short loc_18000B86B
0x18000b817  mov     r8, r15
0x18000b81a  mov     r9, r11
0x18000b81d  mov     r10, r13
0x18000b820  test    rax, rax
0x18000b823  jz      short loc_18000B845
0x18000b825  movzx   edx, word ptr [rcx]
0x18000b828  test    dx, dx
0x18000b82b  jz      short loc_18000B845
0x18000b82d  add     rcx, 2
0x18000b831  mov     [r9], dx
0x18000b835  add     r9, 2
0x18000b839  dec     rax
0x18000b83c  inc     r10
0x18000b83f  sub     r8, 1
0x18000b843  jnz     short loc_18000B820
0x18000b845  lea     rdx, [r10-1]
0x18000b849  test    r8, r8
0x18000b84c  cmovnz  rdx, r10
0x18000b850  lea     rcx, [r9-2]
0x18000b854  cmovnz  rcx, r9
0x18000b858  mov     [rcx], r13w
0x18000b85c  jz      short loc_18000B86B
0x18000b85e  sub     r15, rdx
0x18000b861  cmp     r15, 1
0x18000b865  ja      loc_18000BB7A
0x18000b86b  mov     rcx, [rbp+57h]; this
0x18000b86f  test    r12d, r12d
0x18000b872  js      loc_18000BBA0
0x18000b878  mov     [rbp+4Fh+var_A0], r13
0x18000b87c  mov     rax, [rbp+4Fh+var_A8]
0x18000b880  mov     r15, [rax]
0x18000b883  mov     rax, [r15]
0x18000b886  mov     r12, [rax+90h]
0x18000b88d  mov     rdi, qword ptr [rbp+4Fh+sourceString]
0x18000b891  mov     rbx, r14
0x18000b894  inc     rbx
0x18000b897  cmp     word ptr [rdi+rbx*2], 0
0x18000b89c  jnz     short loc_18000B894
0x18000b89e  mov     eax, 0FFFFFFFFh
0x18000b8a3  cmp     rbx, rax
0x18000b8a6  jbe     short loc_18000B8C0
0x18000b8a8  mov     ebx, eax
0x18000b8aa  xor     r9d, r9d; lpArguments
0x18000b8ad  xor     r8d, r8d; nNumberOfArguments
0x18000b8b0  mov     edx, 1; dwExceptionFlags
0x18000b8b5  mov     ecx, 0C000000Dh; dwExceptionCode
  ... truncated ...
```
