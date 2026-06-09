# ShellMRTHelper::Common::TryFallbackToFilePath(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x180324838`
- end: `0x180324b66`
- name: `?TryFallbackToFilePath@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@00PEAPEAU3@@Z`
- size: `814`
- prototype: `int(ShellMRTHelper::Common *__hidden this, HSTRING, HSTRING, HSTRING, HSTRING *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800790b0`
- `0x1801383c0`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x18002769c`
- `0x180037e18`
- `0x18003c5e4`
- `0x1800b5e48`
- `0x180105850`
- `0x18010dd8c`
- `0x18013d330`
- `0x180324838`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1803248bf`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1803248bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18032498d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180324a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180324a3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18032498d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180324a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180324a3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180324b02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180324b02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180324ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180324ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180324890`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803249bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180324890`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803249bf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18032489c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18032489c`

## string_xrefs

- `0x180324919`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180324966`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180324a02`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180324b16`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1803248ef`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall ShellMRTHelper::Common::TryFallbackToFilePath(
        ShellMRTHelper::Common *this,
        HSTRING a2,
        ShellMRTHelper::Common *a3,
        HSTRING *a4)
{
  const WCHAR *StringRawBuffer; // rbx
  HSTRING v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, ShellMRTHelper::Common *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  PCWSTR v20; // rbx
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  unsigned __int64 i; // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  HSTRING string; // [rsp+20h] [rbp-39h] BYREF
  __int64 v29; // [rsp+28h] [rbp-31h] BYREF
  PCNZWCH sourceString; // [rsp+30h] [rbp-29h] BYREF
  UINT32 v31[2]; // [rsp+38h] [rbp-21h]
  __int64 v32; // [rsp+40h] [rbp-19h]
  UINT32 length; // [rsp+48h] [rbp-11h] BYREF
  __int64 v34; // [rsp+50h] [rbp-9h] BYREF
  HSTRING v35[2]; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v37; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a4 = 0;
  if ( a3 )
  {
    sourceString = 0;
    *(_QWORD *)v31 = 0;
    v32 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a3, 0);
    if ( PathIsRelativeW(StringRawBuffer) && *StringRawBuffer != 64 )
    {
      v35[0] = (HSTRING)this;
      v35[1] = a2;
      if ( PathIsURLW(StringRawBuffer) )
      {
        if ( ShellMRTHelper::Common::HasMsAppXUriScheme(a3, v9) )
        {
          v34 = 0;
          v37 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Foundation.Uri",
            0x17u,
            0x16u);
          v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                  v37,
                  &v34);
          v11 = v10;
          if ( v10 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x132,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v10,
              (int)string);
LABEL_17:
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v34);
LABEL_32:
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(
              &sourceString,
              v21);
            return v11;
          }
          v29 = 0;
          v12 = v34;
          v13 = *(__int64 (__fastcall **)(__int64, ShellMRTHelper::Common *, __int64 *))(*(_QWORD *)v34 + 48LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v29);
          v14 = v13(v12, a3, &v29);
          v11 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x135,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v14,
              (int)string);
LABEL_16:
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v29);
            goto LABEL_17;
          }
          string = 0;
          v15 = v29;
          v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 104LL);
          WindowsDeleteString(0);
          string = 0;
          v17 = v16(v15, &string);
          v11 = v17;
          if ( v17 < 0 )
          {
            v18 = 313;
LABEL_15:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v18,
              (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
              (const char *)(unsigned int)v17,
              (int)string);
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_16;
          }
          length = 0;
          v20 = WindowsGetStringRawBuffer(string, &length);
          if ( length > 1 )
          {
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(
              &sourceString,
              v19);
            *(_QWORD *)v31 = -1;
            v32 = -1;
            v17 = _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(v35, v20 + 1, (PWSTR *)&sourceString);
            v11 = v17;
            if ( v17 < 0 )
            {
              v18 = 320;
              goto LABEL_15;
            }
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v29);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v34);
        }
      }
      else
      {
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString, v9);
        *(_QWORD *)v31 = -1;
        v32 = -1;
        v24 = _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(v35, StringRawBuffer, (PWSTR *)&sourceString);
        v11 = v24;
        if ( v24 < 0 )
        {
          v26 = 327;
          goto LABEL_31;
        }
      }
    }
    if ( sourceString && *sourceString )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
      v22 = 0;
      for ( i = *(_QWORD *)v31; v22 < i; ++v22 )
      {
        if ( sourceString[v22] == 47 )
        {
          sourceString[v22] = 92;
          i = *(_QWORD *)v31;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
      v24 = WindowsCreateString(sourceString, v31[0], a4);
      v11 = v24;
      if ( v24 < 0 )
      {
        v26 = 338;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v24,
          (int)string);
        goto LABEL_32;
      }
    }
    else
    {
      v24 = WindowsDuplicateString((HSTRING)a3, a4);
      v11 = v24;
      if ( v24 < 0 )
      {
        v26 = 343;
        goto LABEL_31;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString, v25);
  }
  return 0;
}

```

## disassembly

```asm
0x180324838  mov     [rsp-8+arg_0], rbx
0x18032483d  mov     [rsp-8+arg_8], rsi
0x180324842  push    rbp
0x180324843  push    rdi
0x180324844  push    r12
0x180324846  push    r14
0x180324848  push    r15
0x18032484a  lea     rbp, [rsp-37h]
0x18032484f  sub     rsp, 90h
0x180324856  mov     rax, cs:__security_cookie
0x18032485d  xor     rax, rsp
0x180324860  mov     [rbp+57h+var_28], rax
0x180324864  mov     r14, r9
0x180324867  mov     rsi, r8
0x18032486a  mov     rdi, rdx
0x18032486d  mov     r15, rcx
0x180324870  xor     r12d, r12d
0x180324873  mov     [r9], r12
0x180324876  test    r8, r8
0x180324879  jz      loc_180324B3C
0x18032487f  mov     [rbp+57h+sourceString], r12
0x180324883  mov     qword ptr [rbp+57h+var_78], r12
0x180324887  mov     [rbp+57h+var_70], r12
0x18032488b  xor     edx, edx; length
0x18032488d  mov     rcx, r8; string
0x180324890  call    cs:__imp_WindowsGetStringRawBuffer
0x180324896  mov     rbx, rax
0x180324899  mov     rcx, rax; pszPath
0x18032489c  call    cs:__imp_PathIsRelativeW
0x1803248a2  test    eax, eax
0x1803248a4  jz      loc_180324A57
0x1803248aa  cmp     word ptr [rbx], 40h ; '@'
0x1803248ae  jz      loc_180324A57
0x1803248b4  mov     [rbp+57h+var_58], r15
0x1803248b8  mov     [rbp+57h+var_50], rdi
0x1803248bc  mov     rcx, rbx; pszPath
0x1803248bf  call    cs:__imp_PathIsURLW
0x1803248c5  test    eax, eax
0x1803248c7  jz      loc_180324AC6
0x1803248cd  mov     rcx, rsi; this
0x1803248d0  call    ?HasMsAppXUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppXUriScheme(HSTRING__ *)
0x1803248d5  test    al, al
0x1803248d7  jz      loc_180324A57
0x1803248dd  mov     [rbp+57h+var_60], r12
0x1803248e1  mov     [rbp+57h+var_30], r12
0x1803248e5  lea     r9d, [r12+16h]; unsigned int
0x1803248ea  lea     r8d, [r12+17h]; unsigned int
0x1803248ef  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1803248f6  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1803248fa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803248ff  lea     rdx, [rbp+57h+var_60]
0x180324903  mov     rcx, [rbp+57h+var_30]
0x180324907  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18032490c  mov     ebx, eax
0x18032490e  test    eax, eax
0x180324910  jns     short loc_18032492F
0x180324912  mov     rcx, [rbp+5Fh]; this
0x180324916  mov     r9d, eax; char *
0x180324919  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180324920  mov     edx, 132h; void *
0x180324925  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032492a  jmp     loc_180324A29
0x18032492f  mov     [rbp+57h+var_88], r12
0x180324933  mov     rdi, [rbp+57h+var_60]
0x180324937  mov     rax, [rdi]
0x18032493a  mov     rbx, [rax+30h]
0x18032493e  lea     rcx, [rbp+57h+var_88]
0x180324942  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180324947  lea     r8, [rbp+57h+var_88]
0x18032494b  mov     rdx, rsi
0x18032494e  mov     rcx, rdi
0x180324951  mov     rax, rbx
0x180324954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180324959  mov     ebx, eax
0x18032495b  test    eax, eax
0x18032495d  jns     short loc_18032497C
0x18032495f  mov     rcx, [rbp+5Fh]; this
0x180324963  mov     r9d, eax; char *
0x180324966  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18032496d  mov     edx, 135h; void *
0x180324972  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180324977  jmp     loc_180324A20
0x18032497c  mov     [rbp+57h+string], r12
0x180324980  mov     rdi, [rbp+57h+var_88]
0x180324984  mov     rax, [rdi]
0x180324987  mov     rbx, [rax+68h]
0x18032498b  xor     ecx, ecx; string
0x18032498d  call    cs:__imp_WindowsDeleteString
0x180324993  mov     [rbp+57h+string], r12
0x180324997  lea     rdx, [rbp+57h+string]
0x18032499b  mov     rcx, rdi
0x18032499e  mov     rax, rbx
0x1803249a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803249a6  mov     ebx, eax
0x1803249a8  test    eax, eax
0x1803249aa  jns     short loc_1803249B3
0x1803249ac  mov     edx, 139h
0x1803249b1  jmp     short loc_1803249FF
0x1803249b3  mov     [rbp+57h+length], r12d
0x1803249b7  lea     rdx, [rbp+57h+length]; length
0x1803249bb  mov     rcx, [rbp+57h+string]; string
0x1803249bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1803249c5  mov     rbx, rax
0x1803249c8  cmp     [rbp+57h+length], 1
0x1803249cc  jbe     short loc_180324A37
0x1803249ce  lea     rcx, [rbp+57h+sourceString]
0x1803249d2  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1803249d7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1803249db  mov     qword ptr [rbp+57h+var_78], rcx
0x1803249df  mov     [rbp+57h+var_70], rcx
0x1803249e3  lea     rdx, [rbx+2]
0x1803249e7  lea     r8, [rbp+57h+sourceString]
0x1803249eb  lea     rcx, [rbp+57h+var_58]
0x1803249ef  call    ??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z; _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)
0x1803249f4  mov     ebx, eax
0x1803249f6  test    eax, eax
0x1803249f8  jns     short loc_180324A37
0x1803249fa  mov     edx, 140h; void *
0x1803249ff  mov     r9d, eax; char *
0x180324a02  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180324a09  mov     rcx, [rbp+5Fh]; this
0x180324a0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180324a12  mov     rcx, [rbp+57h+string]; string
0x180324a16  call    cs:__imp_WindowsDeleteString
0x180324a1c  mov     [rbp+57h+string], r12
0x180324a20  lea     rcx, [rbp+57h+var_88]
0x180324a24  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180324a29  lea     rcx, [rbp+57h+var_60]
0x180324a2d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180324a32  jmp     loc_180324B26
0x180324a37  mov     rcx, [rbp+57h+string]; string
0x180324a3b  call    cs:__imp_WindowsDeleteString
0x180324a41  mov     [rbp+57h+string], r12
0x180324a45  lea     rcx, [rbp+57h+var_88]
0x180324a49  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180324a4e  lea     rcx, [rbp+57h+var_60]
0x180324a52  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180324a57  mov     rax, [rbp+57h+sourceString]
0x180324a5b  test    rax, rax
0x180324a5e  jz      loc_180324AFC
0x180324a64  cmp     [rax], r12w
0x180324a68  jz      loc_180324AFC
0x180324a6e  lea     rcx, [rbp+57h+sourceString]
0x180324a72  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x180324a77  mov     rcx, r12
0x180324a7a  mov     rax, qword ptr [rbp+57h+var_78]
0x180324a7e  test    rax, rax
0x180324a81  jz      short loc_180324AA0
0x180324a83  mov     rdx, [rbp+57h+sourceString]
0x180324a87  cmp     word ptr [rdx+rcx*2], 2Fh ; '/'
0x180324a8c  jnz     short loc_180324A98
0x180324a8e  mov     word ptr [rdx+rcx*2], 5Ch ; '\'
0x180324a94  mov     rax, qword ptr [rbp+57h+var_78]
0x180324a98  inc     rcx
0x180324a9b  cmp     rcx, rax
0x180324a9e  jb      short loc_180324A83
0x180324aa0  lea     rcx, [rbp+57h+sourceString]
0x180324aa4  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x180324aa9  mov     r8, r14; string
0x180324aac  mov     edx, [rbp+57h+var_78]; length
0x180324aaf  mov     rcx, [rbp+57h+sourceString]; sourceString
0x180324ab3  call    cs:__imp_WindowsCreateString
0x180324ab9  mov     ebx, eax
0x180324abb  test    eax, eax
0x180324abd  jns     short loc_180324B33
0x180324abf  mov     edx, 152h
0x180324ac4  jmp     short loc_180324B13
0x180324ac6  lea     rcx, [rbp+57h+sourceString]
0x180324aca  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180324acf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180324ad3  mov     qword ptr [rbp+57h+var_78], rcx
0x180324ad7  mov     [rbp+57h+var_70], rcx
0x180324adb  lea     r8, [rbp+57h+sourceString]
0x180324adf  mov     rdx, rbx
0x180324ae2  lea     rcx, [rbp+57h+var_58]
0x180324ae6  call    ??R_lambda_d8d5e2edaa6c10768996e24008ba8fd8_@@QEBAJPEBGPEAPEAG@Z; _lambda_d8d5e2edaa6c10768996e24008ba8fd8_::operator()(ushort const *,ushort * *)
0x180324aeb  mov     ebx, eax
0x180324aed  test    eax, eax
0x180324aef  jns     loc_180324A57
0x180324af5  mov     edx, 147h
0x180324afa  jmp     short loc_180324B13
0x180324afc  mov     rdx, r14; newString
0x180324aff  mov     rcx, rsi; string
0x180324b02  call    cs:__imp_WindowsDuplicateString
0x180324b08  mov     ebx, eax
0x180324b0a  test    eax, eax
0x180324b0c  jns     short loc_180324B33
0x180324b0e  mov     edx, 157h; void *
0x180324b13  mov     r9d, eax; char *
0x180324b16  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180324b1d  mov     rcx, [rbp+5Fh]; this
0x180324b21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180324b26  lea     rcx, [rbp+57h+sourceString]
0x180324b2a  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180324b2f  mov     eax, ebx
0x180324b31  jmp     short loc_180324B3E
0x180324b33  lea     rcx, [rbp+57h+sourceString]
0x180324b37  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180324b3c  xor     eax, eax
0x180324b3e  mov     rcx, [rbp+57h+var_28]
0x180324b42  xor     rcx, rsp; StackCookie
0x180324b45  call    __security_check_cookie
0x180324b4a  lea     r11, [rsp+0B0h+var_20]
0x180324b52  mov     rbx, [r11+30h]
0x180324b56  mov     rsi, [r11+38h]
0x180324b5a  mov     rsp, r11
0x180324b5d  pop     r15
0x180324b5f  pop     r14
0x180324b61  pop     r12
0x180324b63  pop     rdi
0x180324b64  pop     rbp
0x180324b65  retn
```
