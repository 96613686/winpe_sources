# ShellMRTHelper::MRTHelperBase::Resolve(ShellMRTHelper::MRTHelperBase::MRTResolutionType,wchar_t const *,wchar_t * *)

- ea: `0x180047c60`
- end: `0x1800483ec`
- name: `?Resolve@MRTHelperBase@ShellMRTHelper@@AEAAJW4MRTResolutionType@12@PEB_WPEAPEA_W@Z`
- size: `1932`
- prototype: `int __high(enum ShellMRTHelper::MRTHelperBase::MRTResolutionType, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046fac`

## callees

- `0x180037df8`
- `0x180044668`
- `0x180047c60`
- `0x1800483f4`
- `0x180048424`
- `0x18004b894`
- `0x18005b244`
- `0x1800636c4`
- `0x18006c944`
- `0x18007a73c`
- `0x1800e34bc`
- `0x18011d690`
- `0x18015cb00`
- `0x1802db264`
- `0x18044e1fc`
- `0x180468598`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180047d49`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180047d49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047ce7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048173`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047ce7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048173`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004832a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004832a`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800480cf`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800480cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004806a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004806a`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180048035`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180048035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18004828e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18004828e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004808d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004808d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047f29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047cf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047cf9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180047e8a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180047e8a`

## string_xrefs

- `0x180047d72`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x180047e1d`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x180047ea2`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18004804f`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x180048146`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18004819c`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x1800482dc`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x180048385`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ShellMRTHelper::MRTHelperBase::Resolve(__int64 a1, __int64 a2, __int64 a3, LPWSTR *a4)
{
  LPWSTR *v4; // rsi
  __int64 v6; // r15
  unsigned __int64 v7; // rdx
  HRESULT v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  wchar_t *v11; // rax
  signed int v12; // edi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LPWSTR, GUID *, HSTRING__ *); // rbx
  int v15; // eax
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, UINT32 *); // rbx
  __int64 v20; // rcx
  __int64 v21; // rcx
  HRESULT v22; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  const wchar_t *v25; // r13
  size_t v26; // rbx
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rsi
  WCHAR *v29; // rax
  size_t v30; // r8
  size_t v31; // rdx
  wchar_t *v32; // rcx
  size_t *v33; // r8
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int64, LPWSTR *); // rdi
  HRESULT v36; // eax
  HRESULT v38; // eax
  wchar_t **v39; // r8
  int v40; // eax
  __int64 v41; // rbx
  int v42; // eax
  LPWSTR v43; // rax
  const WCHAR *StringRawBuffer; // rax
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, _QWORD, __int64, LPWSTR *); // rbx
  __int64 v47; // rsi
  __int64 (__fastcall *v48)(__int64, _QWORD, __int64, LPWSTR *); // rdi
  int cchToCopy; // [rsp+20h] [rbp-E0h]
  LPWSTR ppwsz; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v52; // [rsp+40h] [rbp-C0h]
  HSTRING__ v53[2]; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 length[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR *v55; // [rsp+58h] [rbp-A8h]
  PWSTR ppszPathOut; // [rsp+68h] [rbp-98h] BYREF
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  __int64 v59; // [rsp+80h] [rbp-80h]
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-78h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v4 = a4;
  v55 = a4;
  v6 = a1;
  v59 = a1;
  *a4 = 0;
  ppwsz = 0;
  v51 = 0;
  v52 = 0;
  string = 0;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a3 + 2 * v7) );
  if ( v7 > 0xFFFFFFFF || (int)v7 + 1 < (unsigned int)v7 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v8 = WindowsCreateStringReference((PCWSTR)a3, v7, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
LABEL_68:
    v42 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Initialize(
            &ppwsz,
            ppszPathOut,
            -1);
    v10 = v42;
    if ( v42 >= 0 )
    {
      v43 = ppwsz;
      ppwsz = 0;
      v52 = 0;
      v51 = 0;
      *v4 = v43;
      v10 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
        (const char *)(unsigned int)v42,
        cchToCopy);
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(&ppszPathOut);
    goto LABEL_27;
  }
  v9 = ShellMRTHelper::MRTHelperBase::InitializeMRTObjects((LPVOID *)v6);
  v10 = v9;
  if ( *(_BYTE *)(v6 + 46) && ((unsigned int)(v9 + 2147024894) <= 1 || v9 == -2147023728) )
  {
    ppszPathOut = 0;
    v57 = -1;
    v58 = -1;
    v36 = PathAllocCombine(*(PCWSTR *)(v6 + 72), (PCWSTR)a3, 0, &ppszPathOut);
    v10 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
        (const char *)(unsigned int)v36,
        cchToCopy);
      if ( ppszPathOut )
      {
        LocalFree(ppszPathOut);
        ppszPathOut = 0;
      }
      v57 = 0;
      v58 = 0;
      string = 0;
      return v10;
    }
    goto LABEL_68;
  }
  if ( v9 < 0 )
  {
    if ( v9 == -2147024891 || (unsigned int)(v9 + 2147024894) <= 1 || v9 == -2147023728 )
      goto LABEL_27;
    v23 = (unsigned int)v9;
    v24 = 320;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
      (const char *)v23,
      cchToCopy);
LABEL_27:
    string = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(&ppwsz);
    return v10;
  }
  if ( *(_WORD *)a3 == 64 )
  {
    if ( *(_WORD *)(a3 + 2) == 123 )
    {
      v11 = wcschr((const wchar_t *)a3, 0x3Fu);
      v12 = v11 == 0 ? 0x8000FFFF : 0;
      if ( !v11 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14A,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v12,
          cchToCopy);
        goto LABEL_13;
      }
      v25 = v11 + 1;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      if ( v11 == (wchar_t *)-2LL )
      {
        v12 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(&ppwsz);
        goto LABEL_44;
      }
      v27 = v26 - 1;
      if ( v26 )
      {
        if ( v27 < v26 )
          --v26;
      }
      else
      {
        v27 = 0;
      }
      v28 = v27 + 1;
      if ( v27 + 1 >= v27 && is_mul_ok(v28, 2u) )
      {
        v29 = (WCHAR *)CoTaskMemAlloc(2 * v28);
        if ( v29 )
        {
          v52 = v28;
          ppwsz = v29;
          *v29 = 0;
          v12 = 0;
          if ( StringValidateDestW(ppwsz, v28, v30) < 0 )
          {
            if ( !v28 )
              goto LABEL_42;
          }
          else if ( v26 <= 0x7FFFFFFE )
          {
            StringCopyWorkerW_0(v32, v31, v33, v25, v26);
LABEL_42:
            v51 = v26;
            goto LABEL_43;
          }
          *v32 = 0;
          goto LABEL_42;
        }
        v12 = -2147024882;
      }
      else
      {
        v12 = -2147024362;
      }
LABEL_43:
      v4 = v55;
LABEL_44:
      v6 = v59;
LABEL_13:
      *(_QWORD *)&v53[0].unused = 0;
      *(_QWORD *)length = 0;
      if ( v12 >= 0 )
      {
        v13 = *(_QWORD *)(v6 + 8);
        v14 = *(__int64 (__fastcall **)(__int64, LPWSTR, GUID *, HSTRING__ *))(*(_QWORD *)v13 + 88LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v53);
        v15 = v14(v13, ppwsz, &GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2, v53);
        v12 = v15;
        v16 = retaddr;
        if ( v15 >= 0 )
        {
          v18 = *(_QWORD *)&v53[0].unused;
          v19 = *(__int64 (__fastcall **)(__int64, _QWORD, UINT32 *))(**(_QWORD **)&v53[0].unused + 56LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(length);
          v15 = v19(v18, *(_QWORD *)(v6 + 16), length);
          v12 = v15;
          v16 = retaddr;
          if ( v15 >= 0 )
          {
            v34 = *(_QWORD *)length;
            v35 = *(__int64 (__fastcall **)(__int64, LPWSTR *))(**(_QWORD **)length + 24LL);
            if ( ppwsz )
            {
              CoTaskMemFree(ppwsz);
              ppwsz = 0;
            }
            v51 = -1;
            v52 = -1;
            v15 = v35(v34, &ppwsz);
            v12 = v15;
            v16 = retaddr;
            if ( v15 >= 0 )
              goto LABEL_19;
            v17 = 353;
          }
          else
          {
            v17 = 346;
          }
        }
        else
        {
          v17 = 341;
        }
        wil::details::in1diag3::_Log_Hr(
          v16,
          (void *)v17,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v15,
          cchToCopy);
      }
LABEL_19:
      v20 = *(_QWORD *)length;
      if ( *(_QWORD *)length )
      {
        *(_QWORD *)length = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v21 = *(_QWORD *)&v53[0].unused;
      if ( *(_QWORD *)&v53[0].unused )
      {
        *(_QWORD *)&v53[0].unused = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      goto LABEL_23;
    }
    v38 = SHLoadIndirectString((PCWSTR)a3, pszOutBuf, 0x104u, 0);
    if ( v38 >= 0 )
    {
      v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Initialize(
              &ppwsz,
              pszOutBuf,
              -1);
      goto LABEL_23;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x172,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
      (const char *)(unsigned int)v38,
      cchToCopy);
  }
  else
  {
    length[0] = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, length);
    if ( length[0] >= 0xC && CompareStringOrdinal(StringRawBuffer, 12, L"ms-resource:", 12, 1) == 2 )
    {
      v45 = *(_QWORD *)(v6 + 8);
      v46 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPWSTR *))(*(_QWORD *)v45 + 48LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(&ppwsz);
      v51 = -1;
      v52 = -1;
      v12 = v46(v45, *(_QWORD *)(v6 + 16), a3, &ppwsz);
      if ( v12 >= 0 )
        goto LABEL_59;
      *(_QWORD *)&v53[0].unused = 0;
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
        v53,
        0);
      v40 = ShellMRTHelper::Common::TryRemoveImplicitResourcesPrefixFromShortenedMsResourceUri(
              (ShellMRTHelper::Common *)string,
              v53,
              v39);
      if ( v40 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x184,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v40,
          cchToCopy);
      }
      else
      {
        v41 = *(_QWORD *)&v53[0].unused;
        if ( *(_QWORD *)&v53[0].unused && **(_WORD **)&v53[0].unused )
        {
          v47 = *(_QWORD *)(v6 + 8);
          v48 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPWSTR *))(*(_QWORD *)v47 + 48LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(&ppwsz);
          v51 = -1;
          v52 = -1;
          v12 = v48(v47, *(_QWORD *)(v6 + 16), v41, &ppwsz);
          v4 = v55;
        }
      }
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18B,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v12,
          cchToCopy);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v53);
LABEL_23:
      if ( v12 >= 0 )
        goto LABEL_59;
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(&ppwsz);
  v51 = -1;
  v52 = -1;
  v22 = SHStrDupW((LPCWSTR)a3, &ppwsz);
  v10 = v22;
  if ( v22 < 0 )
  {
    v23 = (unsigned int)v22;
    v24 = 443;
    goto LABEL_26;
  }
LABEL_59:
  *v4 = ppwsz;
  return 0;
}

```

## disassembly

```asm
0x180047c60  push    rbp
0x180047c62  push    rbx
0x180047c63  push    rsi
0x180047c64  push    rdi
0x180047c65  push    r12
0x180047c67  push    r13
0x180047c69  push    r15
0x180047c6b  lea     rbp, [rsp-1D0h]
0x180047c73  sub     rsp, 2D0h
0x180047c7a  mov     rax, cs:__security_cookie
0x180047c81  xor     rax, rsp
0x180047c84  mov     [rbp+200h+var_40], rax
0x180047c8b  mov     rsi, r9
0x180047c8e  mov     [rsp+300h+var_2A8], r9
0x180047c93  mov     r12, r8
0x180047c96  mov     r15, rcx
0x180047c99  mov     [rbp+200h+var_280], rcx
0x180047c9d  xor     r13d, r13d
0x180047ca0  mov     [r9], r13
0x180047ca3  mov     [rsp+300h+ppwsz], r13
0x180047ca8  mov     [rsp+300h+var_2C8], r13
0x180047cad  mov     [rsp+300h+var_2C0], r13
0x180047cb2  mov     [rbp+200h+string], r13
0x180047cb6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180047cba  mov     rdx, rdi
0x180047cbd  inc     rdx; length
0x180047cc0  cmp     [r8+rdx*2], r13w
0x180047cc5  jnz     short loc_180047CBD
0x180047cc7  mov     eax, 0FFFFFFFFh
0x180047ccc  cmp     rdx, rax
0x180047ccf  ja      short loc_180047CD8
0x180047cd1  lea     eax, [rdx+1]
0x180047cd4  cmp     eax, edx
0x180047cd6  jnb     short loc_180047CEE
0x180047cd8  xor     r9d, r9d; lpArguments
0x180047cdb  xor     r8d, r8d; nNumberOfArguments
0x180047cde  lea     edx, [r9+1]; dwExceptionFlags
0x180047ce2  mov     ecx, 80070216h; dwExceptionCode
0x180047ce7  call    cs:__imp_RaiseException
0x180047ced  int     3; Trap to Debugger
0x180047cee  lea     r9, [rbp+200h+string]; string
0x180047cf2  lea     r8, [rbp+200h+hstringHeader]; hstringHeader
0x180047cf6  mov     rcx, r12; sourceString
0x180047cf9  call    cs:__imp_WindowsCreateStringReference
0x180047cff  test    eax, eax
0x180047d01  js      loc_180048167
0x180047d07  mov     rcx, r15; ppv
0x180047d0a  call    ?InitializeMRTObjects@MRTHelperBase@ShellMRTHelper@@AEAAJXZ; ShellMRTHelper::MRTHelperBase::InitializeMRTObjects(void)
0x180047d0f  mov     ebx, eax
0x180047d11  mov     ecx, 80070490h
0x180047d16  cmp     [r15+2Eh], r13b
0x180047d1a  jnz     loc_180048002
0x180047d20  test    ebx, ebx
0x180047d22  js      loc_1800481D8
0x180047d28  cmp     word ptr [r12], 40h ; '@'
0x180047d2e  jnz     loc_1800482F2
0x180047d34  mov     rcx, r12; pszSource
0x180047d37  cmp     word ptr [r12+2], 7Bh ; '{'
0x180047d3e  jnz     loc_1800480C2
0x180047d44  mov     edx, 3Fh ; '?'; Ch
0x180047d49  call    cs:__imp_wcschr
0x180047d4f  mov     rcx, rax
0x180047d52  neg     rcx
0x180047d55  sbb     edi, edi
0x180047d57  not     edi
0x180047d59  and     edi, 8000FFFFh
0x180047d5f  mov     rcx, [rbp+208h]; this
0x180047d66  test    rax, rax
0x180047d69  jnz     loc_180047EC9
0x180047d6f  mov     r9d, edi; char *
0x180047d72  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180047d79  mov     edx, 14Ah; void *
0x180047d7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047d83  mov     qword ptr [rsp+300h+var_2B8.unused], r13
0x180047d88  mov     qword ptr [rsp+300h+length], r13
0x180047d8d  test    edi, edi
0x180047d8f  js      loc_180047E2A
0x180047d95  mov     rdi, [r15+8]
0x180047d99  mov     rax, [rdi]
0x180047d9c  mov     rbx, [rax+58h]
0x180047da0  lea     rcx, [rsp+300h+var_2B8]
0x180047da5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047daa  lea     r9, [rsp+300h+var_2B8]
0x180047daf  lea     r8, _GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2
0x180047db6  mov     rdx, [rsp+300h+ppwsz]
0x180047dbb  mov     rcx, rdi
0x180047dbe  mov     rax, rbx
0x180047dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dc6  mov     edi, eax
0x180047dc8  mov     rcx, [rbp+208h]
0x180047dcf  test    eax, eax
0x180047dd1  jns     short loc_180047DDA
0x180047dd3  mov     edx, 155h
0x180047dd8  jmp     short loc_180047E1A
0x180047dda  mov     rdi, qword ptr [rsp+300h+var_2B8.unused]
0x180047ddf  mov     rax, [rdi]
0x180047de2  mov     rbx, [rax+38h]
0x180047de6  lea     rcx, [rsp+300h+length]
0x180047deb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047df0  lea     r8, [rsp+300h+length]
0x180047df5  mov     rdx, [r15+10h]
0x180047df9  mov     rcx, rdi
0x180047dfc  mov     rax, rbx
0x180047dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e04  mov     edi, eax
0x180047e06  mov     rcx, [rbp+208h]; this
0x180047e0d  test    eax, eax
0x180047e0f  jns     loc_180047F9C
0x180047e15  mov     edx, 15Ah; void *
0x180047e1a  mov     r9d, eax; char *
0x180047e1d  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180047e24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047e29  nop
0x180047e2a  mov     rcx, qword ptr [rsp+300h+length]
0x180047e2f  test    rcx, rcx
0x180047e32  jz      short loc_180047E46
0x180047e34  mov     qword ptr [rsp+300h+length], r13
0x180047e39  mov     rax, [rcx]
0x180047e3c  mov     rax, [rax+10h]
0x180047e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e45  nop
0x180047e46  mov     rcx, qword ptr [rsp+300h+var_2B8.unused]
0x180047e4b  test    rcx, rcx
0x180047e4e  jz      short loc_180047E62
0x180047e50  mov     qword ptr [rsp+300h+var_2B8.unused], r13
0x180047e55  mov     rax, [rcx]
0x180047e58  mov     rax, [rax+10h]
0x180047e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e61  nop
0x180047e62  test    edi, edi
0x180047e64  jns     loc_180048097
0x180047e6a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180047e6e  lea     rcx, [rsp+300h+ppwsz]
0x180047e73  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(void)
0x180047e78  mov     [rsp+300h+var_2C8], rdi
0x180047e7d  mov     [rsp+300h+var_2C0], rdi
0x180047e82  lea     rdx, [rsp+300h+ppwsz]; ppwsz
0x180047e87  mov     rcx, r12; psz
0x180047e8a  call    cs:__imp_SHStrDupW
0x180047e90  mov     ebx, eax
0x180047e92  test    eax, eax
0x180047e94  jns     loc_180048097
0x180047e9a  mov     r9d, eax; char *
0x180047e9d  mov     edx, 1BBh; void *
0x180047ea2  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180047ea9  mov     rcx, [rbp+208h]; this
0x180047eb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047eb5  nop
0x180047eb6  mov     [rbp+200h+string], r13
0x180047eba  lea     rcx, [rsp+300h+ppwsz]
0x180047ebf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(void)
0x180047ec4  jmp     loc_180048093
0x180047ec9  lea     r13, [rax+2]
0x180047ecd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180047ed1  xor     r15d, r15d
0x180047ed4  inc     rbx
0x180047ed7  cmp     [r13+rbx*2+0], r15w
0x180047edd  jnz     short loc_180047ED4
0x180047edf  test    r13, r13
0x180047ee2  jz      loc_1800482C7
0x180047ee8  lea     rax, [rbx-1]
0x180047eec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180047ef0  jnz     loc_180047FF6
0x180047ef6  mov     rax, rbx
0x180047ef9  lea     rsi, [rax+1]
0x180047efd  cmp     rsi, rax
0x180047f00  jb      short loc_180047F47
0x180047f02  mov     r9, [rsp+300h+var_2C0]
0x180047f07  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180047f0b  jz      loc_180048207
0x180047f11  test    r9, r9
0x180047f14  jnz     loc_180048237
0x180047f1a  lea     eax, [r9+2]
0x180047f1e  mul     rsi
0x180047f21  test    rdx, rdx
0x180047f24  jnz     short loc_180047F47
0x180047f26  mov     rcx, rax; cb
0x180047f29  call    cs:__imp_CoTaskMemAlloc
0x180047f2f  test    rax, rax
0x180047f32  jz      short loc_180047F4E
0x180047f34  mov     [rsp+300h+var_2C0], rsi
0x180047f39  mov     [rsp+300h+ppwsz], rax
0x180047f3e  mov     [rax], r15w
0x180047f42  mov     edi, r15d
0x180047f45  jmp     short loc_180047F57
0x180047f47  mov     edi, 80070216h
0x180047f4c  jmp     short loc_180047F8B
0x180047f4e  mov     edi, 8007000Eh
0x180047f53  test    edi, edi
0x180047f55  js      short loc_180047F8B
0x180047f57  mov     rcx, [rsp+300h+ppwsz]; pszDest
0x180047f5c  mov     rdx, rsi; cchDest
0x180047f5f  call    StringValidateDestW
0x180047f64  test    eax, eax
0x180047f66  js      loc_1800482B5
0x180047f6c  cmp     rbx, 7FFFFFFEh
0x180047f73  ja      loc_1800482BE
0x180047f79  mov     qword ptr [rsp+300h+cchToCopy], rbx; cchToCopy
0x180047f7e  mov     r9, r13; pszSrc
0x180047f81  call    StringCopyWorkerW_0
0x180047f86  mov     [rsp+300h+var_2C8], rbx
0x180047f8b  mov     rsi, [rsp+300h+var_2A8]
0x180047f90  xor     r13d, r13d
0x180047f93  mov     r15, [rbp+200h+var_280]
0x180047f97  jmp     loc_180047D83
0x180047f9c  mov     rbx, qword ptr [rsp+300h+length]
0x180047fa1  mov     rax, [rbx]
0x180047fa4  mov     rdi, [rax+18h]
0x180047fa8  mov     rcx, [rsp+300h+ppwsz]; pv
0x180047fad  test    rcx, rcx
0x180047fb0  jz      short loc_180047FBD
0x180047fb2  call    cs:__imp_CoTaskMemFree
0x180047fb8  mov     [rsp+300h+ppwsz], r13
0x180047fbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047fc1  mov     [rsp+300h+var_2C8], rax
0x180047fc6  mov     [rsp+300h+var_2C0], rax
0x180047fcb  lea     rdx, [rsp+300h+ppwsz]
0x180047fd0  mov     rcx, rbx
0x180047fd3  mov     rax, rdi
0x180047fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fdb  mov     edi, eax
0x180047fdd  mov     rcx, [rbp+208h]
0x180047fe4  test    eax, eax
0x180047fe6  jns     loc_180047E2A
0x180047fec  mov     edx, 161h
0x180047ff1  jmp     loc_180047E1A
0x180047ff6  cmp     rax, rbx
0x180047ff9  cmovb   rbx, rax
0x180047ffd  jmp     loc_180047EF9
0x180048002  lea     r8d, [rax+7FF8FFFEh]
0x180048009  cmp     r8d, 1
0x18004800d  jbe     short loc_180048017
0x18004800f  cmp     ebx, ecx
0x180048011  jnz     loc_180047D20
0x180048017  mov     [rsp+300h+ppszPathOut], r13
0x18004801c  mov     [rsp+300h+var_290], rdi
0x180048021  mov     [rsp+300h+var_288], rdi
0x180048026  lea     r9, [rsp+300h+ppszPathOut]; ppszPathOut
0x18004802b  xor     r8d, r8d; dwFlags
0x18004802e  mov     rdx, r12; pszMore
0x180048031  mov     rcx, [r15+48h]; pszPathIn
0x180048035  call    cs:__imp_PathAllocCombine
0x18004803b  mov     ebx, eax
0x18004803d  test    eax, eax
0x18004803f  jns     loc_18004817A
0x180048045  mov     rcx, [rbp+208h]; this
0x18004804c  mov     r9d, eax; char *
0x18004804f  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180048056  mov     edx, 139h; void *
0x18004805b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048060  mov     rcx, [rsp+300h+ppszPathOut]; hMem
0x180048065  test    rcx, rcx
0x180048068  jz      short loc_180048075
0x18004806a  call    cs:__imp_LocalFree
0x180048070  mov     [rsp+300h+ppszPathOut], r13
0x180048075  mov     [rsp+300h+var_290], r13
0x18004807a  mov     [rsp+300h+var_288], r13
0x18004807f  mov     [rbp+200h+string], r13
0x180048083  mov     rcx, [rsp+300h+ppwsz]; pv
0x180048088  test    rcx, rcx
0x18004808b  jz      short loc_180048093
0x18004808d  call    cs:__imp_CoTaskMemFree
0x180048093  mov     eax, ebx
0x180048095  jmp     short loc_1800480A1
0x180048097  mov     rax, [rsp+300h+ppwsz]
0x18004809c  mov     [rsi], rax
0x18004809f  xor     eax, eax
0x1800480a1  mov     rcx, [rbp+200h+var_40]
0x1800480a8  xor     rcx, rsp; StackCookie
0x1800480ab  call    __security_check_cookie
0x1800480b0  add     rsp, 2D0h
0x1800480b7  pop     r15
0x1800480b9  pop     r13
0x1800480bb  pop     r12
0x1800480bd  pop     rdi
0x1800480be  pop     rsi
0x1800480bf  pop     rbx
0x1800480c0  pop     rbp
0x1800480c1  retn
0x1800480c2  xor     r9d, r9d; ppvReserved
0x1800480c5  mov     r8d, 104h; cchOutBuf
0x1800480cb  lea     rdx, [rbp+200h+pszOutBuf]; pszOutBuf
0x1800480cf  call    cs:__imp_SHLoadIndirectString
0x1800480d5  mov     rcx, [rbp+208h]; this
0x1800480dc  test    eax, eax
0x1800480de  js      loc_1800482D9
0x1800480e4  mov     r8, rdi
0x1800480e7  lea     rdx, [rbp+200h+pszOutBuf]
0x1800480eb  lea     rcx, [rsp+300h+ppwsz]
0x1800480f0  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAJPEB_W_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Initialize(wchar_t const *,unsigned __int64)
0x1800480f5  mov     edi, eax
0x1800480f7  jmp     loc_180047E62
0x1800480fc  mov     qword ptr [rsp+300h+var_2B8.unused], r13
0x180048101  xor     edx, edx
0x180048103  lea     rcx, [rsp+300h+var_2B8]
0x180048108  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18004810d  lea     rdx, [rsp+300h+var_2B8]; HSTRING
0x180048112  mov     rcx, [rbp+200h+string]; this
0x180048116  call    ?TryRemoveImplicitResourcesPrefixFromShortenedMsResourceUri@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@PEAPEA_W@Z; ShellMRTHelper::Common::TryRemoveImplicitResourcesPrefixFromShortenedMsResourceUri(HSTRING__ *,wchar_t * *)
0x18004811b  mov     rcx, [rbp+208h]; this
  ... truncated ...
```
