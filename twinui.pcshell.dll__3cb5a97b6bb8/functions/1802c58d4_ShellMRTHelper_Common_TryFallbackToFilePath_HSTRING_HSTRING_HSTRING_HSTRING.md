# ShellMRTHelper::Common::TryFallbackToFilePath(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x1802c58d4`
- end: `0x1802c5bf2`
- name: `?TryFallbackToFilePath@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@00PEAPEAU3@@Z`
- size: `798`
- prototype: `int(ShellMRTHelper::Common *__hidden this, HSTRING, HSTRING, HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c9644`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x18007b3e0`
- `0x1800e14e4`
- `0x180288dec`
- `0x1802b6978`
- `0x1802c58d4`
- `0x1802d6838`
- `0x180356360`
- `0x180667754`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1802c5b44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1802c5b44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1802c5b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1802c5b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c5a1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c5aa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c5acc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c5a1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c5aa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c5acc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802c5923`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802c5a50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802c5923`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802c5a50`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1802c592f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1802c592f`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1802c5952`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1802c5952`

## string_xrefs

- `0x1802c59a7`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1802c59f4`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1802c5a94`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1802c5ba8`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1802c5980`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall ShellMRTHelper::Common::TryFallbackToFilePath(
        ShellMRTHelper::Common *this,
        HSTRING a2,
        ShellMRTHelper::Common *a3,
        HSTRING *a4)
{
  const WCHAR *StringRawBuffer; // rbx
  HSTRING v8; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, ShellMRTHelper::Common *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  PCWSTR v18; // rbx
  unsigned __int64 v19; // rax
  unsigned __int64 i; // rcx
  HRESULT v21; // eax
  __int64 v22; // rdx
  HSTRING string; // [rsp+20h] [rbp-39h] BYREF
  __int64 v25; // [rsp+28h] [rbp-31h] BYREF
  PCNZWCH sourceString; // [rsp+30h] [rbp-29h] BYREF
  UINT32 v27[2]; // [rsp+38h] [rbp-21h]
  __int64 v28; // [rsp+40h] [rbp-19h]
  UINT32 length; // [rsp+48h] [rbp-11h] BYREF
  __int64 v30; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v31[2]; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v33; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a4 = 0;
  if ( a3 )
  {
    sourceString = 0;
    *(_QWORD *)v27 = 0;
    v28 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a3, 0);
    if ( PathIsRelativeW(StringRawBuffer) && *StringRawBuffer != 64 )
    {
      v31[0] = 0;
      v31[1] = a2;
      if ( PathIsURLW(StringRawBuffer) )
      {
        if ( ShellMRTHelper::Common::HasMsAppXUriScheme(a3, v8) )
        {
          v30 = 0;
          v33 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Foundation.Uri",
            0x17u,
            0x16u);
          v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                 v33,
                 &v30);
          v10 = v9;
          if ( v9 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x132,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v9,
              (int)string);
LABEL_17:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
LABEL_32:
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
            return v10;
          }
          v11 = v30;
          v25 = 0;
          v12 = *(__int64 (__fastcall **)(__int64, ShellMRTHelper::Common *, __int64 *))(*(_QWORD *)v30 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          v13 = v12(v11, a3, &v25);
          v10 = v13;
          if ( v13 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x135,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v13,
              (int)string);
LABEL_16:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
            goto LABEL_17;
          }
          v14 = v25;
          string = 0;
          v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 104LL);
          WindowsDeleteString(0);
          string = 0;
          v16 = v15(v14, &string);
          v10 = v16;
          if ( v16 < 0 )
          {
            v17 = 313;
LABEL_15:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v16,
              (int)string);
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_16;
          }
          length = 0;
          v18 = WindowsGetStringRawBuffer(string, &length);
          if ( length > 1 )
          {
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
            *(_QWORD *)v27 = -1;
            v28 = -1;
            v16 = _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(v31, v18 + 1, &sourceString);
            v10 = v16;
            if ( v16 < 0 )
            {
              v17 = 320;
              goto LABEL_15;
            }
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
        }
      }
      else
      {
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
        *(_QWORD *)v27 = -1;
        v28 = -1;
        v21 = _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(v31, StringRawBuffer, &sourceString);
        v10 = v21;
        if ( v21 < 0 )
        {
          v22 = 327;
          goto LABEL_31;
        }
      }
    }
    if ( sourceString && *sourceString )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
      v19 = *(_QWORD *)v27;
      for ( i = 0; i < v19; ++i )
      {
        if ( sourceString[i] == 47 )
        {
          sourceString[i] = 92;
          v19 = *(_QWORD *)v27;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
      v21 = WindowsCreateString(sourceString, v27[0], a4);
      v10 = v21;
      if ( v21 < 0 )
      {
        v22 = 338;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v21,
          (int)string);
        goto LABEL_32;
      }
    }
    else
    {
      v21 = WindowsDuplicateString((HSTRING)a3, a4);
      v10 = v21;
      if ( v21 < 0 )
      {
        v22 = 343;
        goto LABEL_31;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
  }
  return 0;
}

```

## disassembly

```asm
0x1802c58d4  mov     [rsp-8+arg_0], rbx
0x1802c58d9  push    rbp
0x1802c58da  push    rsi
0x1802c58db  push    rdi
0x1802c58dc  push    r14
0x1802c58de  push    r15
0x1802c58e0  lea     rbp, [rsp-37h]
0x1802c58e5  sub     rsp, 90h
0x1802c58ec  mov     rax, cs:__security_cookie
0x1802c58f3  xor     rax, rsp
0x1802c58f6  mov     [rbp+57h+var_28], rax
0x1802c58fa  xor     r15d, r15d
0x1802c58fd  mov     r14, r9
0x1802c5900  mov     [r9], r15
0x1802c5903  mov     rsi, r8
0x1802c5906  mov     rdi, rdx
0x1802c5909  test    r8, r8
0x1802c590c  jz      loc_1802C5BCD
0x1802c5912  xor     edx, edx; length
0x1802c5914  mov     [rbp+57h+sourceString], r15
0x1802c5918  mov     rcx, r8; string
0x1802c591b  mov     qword ptr [rbp+57h+var_78], r15
0x1802c591f  mov     [rbp+57h+var_70], r15
0x1802c5923  call    cs:__imp_WindowsGetStringRawBuffer
0x1802c5929  mov     rcx, rax; pszPath
0x1802c592c  mov     rbx, rax
0x1802c592f  call    cs:__imp_PathIsRelativeW
0x1802c5935  test    eax, eax
0x1802c5937  jz      loc_1802C5AE8
0x1802c593d  cmp     word ptr [rbx], 40h ; '@'
0x1802c5941  jz      loc_1802C5AE8
0x1802c5947  mov     rcx, rbx; pszPath
0x1802c594a  mov     [rbp+57h+var_58], r15
0x1802c594e  mov     [rbp+57h+var_50], rdi
0x1802c5952  call    cs:__imp_PathIsURLW
0x1802c5958  test    eax, eax
0x1802c595a  jz      loc_1802C5B57
0x1802c5960  mov     rcx, rsi; this
0x1802c5963  call    ?HasMsAppXUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppXUriScheme(HSTRING__ *)
0x1802c5968  test    al, al
0x1802c596a  jz      loc_1802C5AE8
0x1802c5970  lea     r9d, [r15+16h]; unsigned int
0x1802c5974  mov     [rbp+57h+var_60], r15
0x1802c5978  lea     r8d, [r15+17h]; unsigned int
0x1802c597c  mov     [rbp+57h+var_30], r15
0x1802c5980  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1802c5987  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1802c598b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1802c5990  mov     rcx, [rbp+57h+var_30]
0x1802c5994  lea     rdx, [rbp+57h+var_60]
0x1802c5998  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1802c599d  mov     ebx, eax
0x1802c599f  test    eax, eax
0x1802c59a1  jns     short loc_1802C59C0
0x1802c59a3  mov     rcx, [rbp+5Fh]; this
0x1802c59a7  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1802c59ae  mov     r9d, eax; char *
0x1802c59b1  mov     edx, 132h; void *
0x1802c59b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c59bb  jmp     loc_1802C5ABA
0x1802c59c0  mov     rdi, [rbp+57h+var_60]
0x1802c59c4  lea     rcx, [rbp+57h+var_88]
0x1802c59c8  mov     [rbp+57h+var_88], r15
0x1802c59cc  mov     rax, [rdi]
0x1802c59cf  mov     rbx, [rax+30h]
0x1802c59d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802c59d8  lea     r8, [rbp+57h+var_88]
0x1802c59dc  mov     rdx, rsi
0x1802c59df  mov     rcx, rdi
0x1802c59e2  mov     rax, rbx
0x1802c59e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c59ea  mov     ebx, eax
0x1802c59ec  test    eax, eax
0x1802c59ee  jns     short loc_1802C5A0D
0x1802c59f0  mov     rcx, [rbp+5Fh]; this
0x1802c59f4  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1802c59fb  mov     r9d, eax; char *
0x1802c59fe  mov     edx, 135h; void *
0x1802c5a03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c5a08  jmp     loc_1802C5AB1
0x1802c5a0d  mov     rdi, [rbp+57h+var_88]
0x1802c5a11  xor     ecx, ecx; string
0x1802c5a13  mov     [rbp+57h+string], r15
0x1802c5a17  mov     rax, [rdi]
0x1802c5a1a  mov     rbx, [rax+68h]
0x1802c5a1e  call    cs:__imp_WindowsDeleteString
0x1802c5a24  lea     rdx, [rbp+57h+string]
0x1802c5a28  mov     [rbp+57h+string], r15
0x1802c5a2c  mov     rcx, rdi
0x1802c5a2f  mov     rax, rbx
0x1802c5a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c5a37  mov     ebx, eax
0x1802c5a39  test    eax, eax
0x1802c5a3b  jns     short loc_1802C5A44
0x1802c5a3d  mov     edx, 139h
0x1802c5a42  jmp     short loc_1802C5A90
0x1802c5a44  mov     rcx, [rbp+57h+string]; string
0x1802c5a48  lea     rdx, [rbp+57h+length]; length
0x1802c5a4c  mov     [rbp+57h+length], r15d
0x1802c5a50  call    cs:__imp_WindowsGetStringRawBuffer
0x1802c5a56  cmp     [rbp+57h+length], 1
0x1802c5a5a  mov     rbx, rax
0x1802c5a5d  jbe     short loc_1802C5AC8
0x1802c5a5f  lea     rcx, [rbp+57h+sourceString]
0x1802c5a63  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802c5a68  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1802c5a6c  lea     rdx, [rbx+2]
0x1802c5a70  mov     qword ptr [rbp+57h+var_78], rcx
0x1802c5a74  lea     r8, [rbp+57h+sourceString]
0x1802c5a78  mov     [rbp+57h+var_70], rcx
0x1802c5a7c  lea     rcx, [rbp+57h+var_58]
0x1802c5a80  call    ??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z; _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)
0x1802c5a85  mov     ebx, eax
0x1802c5a87  test    eax, eax
0x1802c5a89  jns     short loc_1802C5AC8
0x1802c5a8b  mov     edx, 140h; void *
0x1802c5a90  mov     rcx, [rbp+5Fh]; this
0x1802c5a94  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1802c5a9b  mov     r9d, eax; char *
0x1802c5a9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c5aa3  mov     rcx, [rbp+57h+string]; string
0x1802c5aa7  call    cs:__imp_WindowsDeleteString
0x1802c5aad  mov     [rbp+57h+string], r15
0x1802c5ab1  lea     rcx, [rbp+57h+var_88]
0x1802c5ab5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802c5aba  lea     rcx, [rbp+57h+var_60]
0x1802c5abe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802c5ac3  jmp     loc_1802C5BB7
0x1802c5ac8  mov     rcx, [rbp+57h+string]; string
0x1802c5acc  call    cs:__imp_WindowsDeleteString
0x1802c5ad2  lea     rcx, [rbp+57h+var_88]
0x1802c5ad6  mov     [rbp+57h+string], r15
0x1802c5ada  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802c5adf  lea     rcx, [rbp+57h+var_60]
0x1802c5ae3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802c5ae8  mov     rax, [rbp+57h+sourceString]
0x1802c5aec  test    rax, rax
0x1802c5aef  jz      loc_1802C5B8D
0x1802c5af5  cmp     [rax], r15w
0x1802c5af9  jz      loc_1802C5B8D
0x1802c5aff  lea     rcx, [rbp+57h+sourceString]
0x1802c5b03  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x1802c5b08  mov     rax, qword ptr [rbp+57h+var_78]
0x1802c5b0c  mov     rcx, r15
0x1802c5b0f  test    rax, rax
0x1802c5b12  jz      short loc_1802C5B31
0x1802c5b14  mov     rdx, [rbp+57h+sourceString]
0x1802c5b18  cmp     word ptr [rdx+rcx*2], 2Fh ; '/'
0x1802c5b1d  jnz     short loc_1802C5B29
0x1802c5b1f  mov     word ptr [rdx+rcx*2], 5Ch ; '\'
0x1802c5b25  mov     rax, qword ptr [rbp+57h+var_78]
0x1802c5b29  inc     rcx
0x1802c5b2c  cmp     rcx, rax
0x1802c5b2f  jb      short loc_1802C5B14
0x1802c5b31  lea     rcx, [rbp+57h+sourceString]
0x1802c5b35  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x1802c5b3a  mov     edx, [rbp+57h+var_78]; length
0x1802c5b3d  mov     r8, r14; string
0x1802c5b40  mov     rcx, [rbp+57h+sourceString]; sourceString
0x1802c5b44  call    cs:__imp_WindowsCreateString
0x1802c5b4a  mov     ebx, eax
0x1802c5b4c  test    eax, eax
0x1802c5b4e  jns     short loc_1802C5BC4
0x1802c5b50  mov     edx, 152h
0x1802c5b55  jmp     short loc_1802C5BA4
0x1802c5b57  lea     rcx, [rbp+57h+sourceString]
0x1802c5b5b  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802c5b60  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1802c5b64  lea     r8, [rbp+57h+sourceString]
0x1802c5b68  mov     qword ptr [rbp+57h+var_78], rcx
0x1802c5b6c  mov     rdx, rbx
0x1802c5b6f  mov     [rbp+57h+var_70], rcx
0x1802c5b73  lea     rcx, [rbp+57h+var_58]
0x1802c5b77  call    ??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z; _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)
0x1802c5b7c  mov     ebx, eax
0x1802c5b7e  test    eax, eax
0x1802c5b80  jns     loc_1802C5AE8
0x1802c5b86  mov     edx, 147h
0x1802c5b8b  jmp     short loc_1802C5BA4
0x1802c5b8d  mov     rdx, r14; newString
0x1802c5b90  mov     rcx, rsi; string
0x1802c5b93  call    cs:__imp_WindowsDuplicateString
0x1802c5b99  mov     ebx, eax
0x1802c5b9b  test    eax, eax
0x1802c5b9d  jns     short loc_1802C5BC4
0x1802c5b9f  mov     edx, 157h; void *
0x1802c5ba4  mov     rcx, [rbp+5Fh]; this
0x1802c5ba8  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1802c5baf  mov     r9d, eax; char *
0x1802c5bb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c5bb7  lea     rcx, [rbp+57h+sourceString]
0x1802c5bbb  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802c5bc0  mov     eax, ebx
0x1802c5bc2  jmp     short loc_1802C5BCF
0x1802c5bc4  lea     rcx, [rbp+57h+sourceString]
0x1802c5bc8  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802c5bcd  xor     eax, eax
0x1802c5bcf  mov     rcx, [rbp+57h+var_28]
0x1802c5bd3  xor     rcx, rsp; StackCookie
0x1802c5bd6  call    __security_check_cookie
0x1802c5bdb  mov     rbx, [rsp+0B0h+arg_0]
0x1802c5be3  add     rsp, 90h
0x1802c5bea  pop     r15
0x1802c5bec  pop     r14
0x1802c5bee  pop     rdi
0x1802c5bef  pop     rsi
0x1802c5bf0  pop     rbp
0x1802c5bf1  retn
```
