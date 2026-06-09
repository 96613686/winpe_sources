# DoesUriMatchPathSet(Windows::Foundation::IUriRuntimeClass *,ushort *)

- ea: `0x180048ef8`
- end: `0x1800491c8`
- name: `?DoesUriMatchPathSet@@YA_NPEAUIUriRuntimeClass@Foundation@Windows@@PEAG@Z`
- size: `720`
- prototype: `bool __fastcall(struct Windows::Foundation::IUriRuntimeClass *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800d76b8`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x1800272d8`
- `0x18002cec0`
- `0x18003d454`
- `0x180048ef8`
- `0x18004a00c`
- `0x18004a030`
- `0x18004a0b0`
- `0x18004a844`
- `0x18004acdc`
- `0x18004ae68`
- `0x18006ba98`
- `0x180070c80`
- `0x18008a030`
- `0x1800d753c`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004902c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004919b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004902c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004919b`

## string_xrefs

- `0x180048f5f`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180048fb4`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180049003`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180049056`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180048f8b`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char __fastcall DoesUriMatchPathSet(struct Windows::Foundation::IUriRuntimeClass *a1, unsigned __int16 *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v5; // eax
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  char v13; // si
  __int64 v14; // rdi
  __int64 v15; // r14
  __int64 v16; // rax
  _QWORD *RegexFromPath; // rbx
  _QWORD *v18; // rcx
  char *v19; // r8
  _QWORD *v20; // rcx
  int v22; // [rsp+20h] [rbp-99h]
  HSTRING string; // [rsp+30h] [rbp-89h] BYREF
  __int64 v24; // [rsp+38h] [rbp-81h] BYREF
  HSTRING v25; // [rsp+40h] [rbp-79h] BYREF
  __int64 v26; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v27[3]; // [rsp+50h] [rbp-69h] BYREF
  __int64 v28; // [rsp+68h] [rbp-51h] BYREF
  char v29[40]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v30[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-11h]
  unsigned __int64 v32; // [rsp+B0h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v34; // [rsp+D0h] [rbp+17h]
  _BYTE v35[32]; // [rsp+D8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v25 = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a1 + 48LL);
  WindowsDeleteString(0);
  v25 = 0;
  v5 = v4(a1, &v25);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v5,
      v22);
  v26 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         v34,
         &v26);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v6,
      v22);
  v24 = 0;
  v7 = v26;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v26 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  v9 = v8(v7, v25, &v24);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v9,
      v22);
  string = 0;
  v10 = v24;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 104LL);
  WindowsDeleteString(0);
  string = 0;
  v12 = v11(v10, &string);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v12,
      v22);
  v13 = 0;
  WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v30);
  CreateVectorFromMultiString(v27, a2);
  v14 = v27[0];
  v15 = v27[1];
  while ( v14 != v15 )
  {
    v16 = std::wstring::wstring(&hstringHeader, v14);
    RegexFromPath = (_QWORD *)CreateRegexFromPath(v35, v16);
    v28 = 0;
    std::regex_traits<unsigned short>::regex_traits<unsigned short>(v29);
    if ( RegexFromPath[3] <= 7u )
      v18 = RegexFromPath;
    else
      v18 = (_QWORD *)*RegexFromPath;
    v19 = (char *)v18 + 2 * RegexFromPath[2];
    if ( RegexFromPath[3] > 7u )
      RegexFromPath = (_QWORD *)*RegexFromPath;
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::_Reset<unsigned short const *>(
      &v28,
      RegexFromPath,
      v19,
      256);
    std::wstring::_Tidy_deallocate(v35);
    v20 = v30;
    if ( v32 > 7 )
      v20 = (_QWORD *)v30[0];
    if ( (unsigned __int8)std::_Regex_search2<unsigned short const *,std::allocator<std::sub_match<unsigned short const *>>,unsigned short,std::regex_traits<unsigned short>,unsigned short const *>(
                            (_DWORD)v20,
                            (int)v20 + 2 * (int)v31,
                            0,
                            (unsigned int)&v28,
                            16,
                            (__int64)v20) )
    {
      v13 = 1;
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(&v28);
      break;
    }
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(&v28);
    v14 += 32;
  }
  std::vector<std::wstring>::_Tidy(v27);
  std::wstring::_Tidy_deallocate(v30);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  WindowsDeleteString(v25);
  return v13;
}

```

## disassembly

```asm
0x180048ef8  mov     [rsp-8+arg_10], rbx
0x180048efd  mov     [rsp-8+arg_18], rsi
0x180048f02  push    rbp
0x180048f03  push    rdi
0x180048f04  push    r14
0x180048f06  lea     rbp, [rsp-47h]
0x180048f0b  sub     rsp, 100h
0x180048f12  mov     rax, cs:__security_cookie
0x180048f19  xor     rax, rsp
0x180048f1c  mov     [rbp+57h+var_18], rax
0x180048f20  mov     r14, rdx
0x180048f23  mov     rdi, rcx
0x180048f26  mov     [rbp+57h+var_D0], 0
0x180048f2e  mov     rax, [rcx]
0x180048f31  mov     rbx, [rax+30h]
0x180048f35  xor     ecx, ecx; string
0x180048f37  call    cs:__imp_WindowsDeleteString
0x180048f3d  mov     [rbp+57h+var_D0], 0
0x180048f45  lea     rdx, [rbp+57h+var_D0]
0x180048f49  mov     rcx, rdi
0x180048f4c  mov     rax, rbx
0x180048f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f54  mov     rcx, [rbp+5Fh]; this
0x180048f58  test    eax, eax
0x180048f5a  jns     short loc_180048F71
0x180048f5c  mov     r9d, eax; char *
0x180048f5f  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180048f66  mov     edx, 11Ch; void *
0x180048f6b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048f71  mov     [rbp+57h+var_C8], 0
0x180048f79  mov     [rbp+57h+var_40], 0
0x180048f81  mov     r9d, 16h; unsigned int
0x180048f87  lea     r8d, [r9+1]; unsigned int
0x180048f8b  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180048f92  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180048f96  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048f9b  nop
0x180048f9c  lea     rdx, [rbp+57h+var_C8]
0x180048fa0  mov     rcx, [rbp+57h+var_40]
0x180048fa4  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x180048fa9  mov     rcx, [rbp+5Fh]; this
0x180048fad  test    eax, eax
0x180048faf  jns     short loc_180048FC6
0x180048fb1  mov     r9d, eax; char *
0x180048fb4  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180048fbb  mov     edx, 11Fh; void *
0x180048fc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048fc6  mov     [rsp+110h+var_D8], 0
0x180048fcf  mov     rdi, [rbp+57h+var_C8]
0x180048fd3  mov     rax, [rdi]
0x180048fd6  mov     rbx, [rax+30h]
0x180048fda  lea     rcx, [rsp+110h+var_D8]
0x180048fdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048fe4  lea     r8, [rsp+110h+var_D8]
0x180048fe9  mov     rdx, [rbp+57h+var_D0]
0x180048fed  mov     rcx, rdi
0x180048ff0  mov     rax, rbx
0x180048ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ff8  mov     rcx, [rbp+5Fh]; this
0x180048ffc  test    eax, eax
0x180048ffe  jns     short loc_180049015
0x180049000  mov     r9d, eax; char *
0x180049003  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18004900a  mov     edx, 122h; void *
0x18004900f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049015  mov     [rsp+110h+string], 0
0x18004901e  mov     rdi, [rsp+110h+var_D8]
0x180049023  mov     rax, [rdi]
0x180049026  mov     rbx, [rax+68h]
0x18004902a  xor     ecx, ecx; string
0x18004902c  call    cs:__imp_WindowsDeleteString
0x180049032  mov     [rsp+110h+string], 0
0x18004903b  lea     rdx, [rsp+110h+string]
0x180049040  mov     rcx, rdi
0x180049043  mov     rax, rbx
0x180049046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004904b  mov     rcx, [rbp+5Fh]; this
0x18004904f  test    eax, eax
0x180049051  jns     short loc_180049068
0x180049053  mov     r9d, eax; char *
0x180049056  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18004905d  mov     edx, 125h; void *
0x180049062  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049068  xor     sil, sil
0x18004906b  xor     edx, edx; length
0x18004906d  mov     rcx, [rsp+110h+string]; string
0x180049072  call    cs:__imp_WindowsGetStringRawBuffer
0x180049078  mov     rdx, rax
0x18004907b  lea     rcx, [rbp+57h+var_78]
0x18004907f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180049084  nop
0x180049085  mov     rdx, r14
0x180049088  lea     rcx, [rbp+57h+var_C0]
0x18004908c  call    ?CreateVectorFromMultiString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAG@Z; CreateVectorFromMultiString(ushort *)
0x180049091  nop
0x180049092  mov     rdi, [rbp+57h+var_C0]
0x180049096  mov     r14, [rbp+57h+var_B8]
0x18004909a  cmp     rdi, r14
0x18004909d  jz      loc_18004915A
0x1800490a3  mov     rdx, rdi
0x1800490a6  lea     rcx, [rbp+57h+hstringHeader]
0x1800490aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800490af  mov     rdx, rax
0x1800490b2  lea     rcx, [rbp+57h+var_38]
0x1800490b6  call    ?CreateRegexFromPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; CreateRegexFromPath(std::wstring)
0x1800490bb  mov     rbx, rax
0x1800490be  mov     [rbp+57h+var_A8], 0
0x1800490c6  lea     rcx, [rbp+57h+var_A0]
0x1800490ca  call    ??0?$regex_traits@G@std@@QEAA@XZ; std::regex_traits<ushort>::regex_traits<ushort>(void)
0x1800490cf  nop
0x1800490d0  cmp     qword ptr [rbx+18h], 7
0x1800490d5  jbe     short loc_1800490DC
0x1800490d7  mov     rcx, [rbx]
0x1800490da  jmp     short loc_1800490DF
0x1800490dc  mov     rcx, rbx
0x1800490df  mov     rax, [rbx+10h]
0x1800490e3  lea     r8, [rcx+rax*2]
0x1800490e7  jbe     short loc_1800490EC
0x1800490e9  mov     rbx, [rbx]
0x1800490ec  mov     r9d, 100h
0x1800490f2  mov     rdx, rbx
0x1800490f5  lea     rcx, [rbp+57h+var_A8]
0x1800490f9  call    ??$_Reset@PEBG@?$basic_regex@GV?$regex_traits@G@std@@@std@@AEAAXPEBG0W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::_Reset<ushort const *>(ushort const *,ushort const *,std::regex_constants::syntax_option_type)
0x1800490fe  nop
0x1800490ff  lea     rcx, [rbp+57h+var_38]
0x180049103  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049108  lea     rcx, [rbp+57h+var_78]
0x18004910c  cmp     [rbp+57h+var_60], 7
0x180049111  cmova   rcx, [rbp+57h+var_78]
0x180049116  mov     rax, [rbp+57h+var_68]
0x18004911a  lea     rdx, [rcx+rax*2]
0x18004911e  mov     [rsp+110h+var_E8], rcx
0x180049123  mov     [rsp+110h+var_F0], 10h
0x18004912b  lea     r9, [rbp+57h+var_A8]
0x18004912f  xor     r8d, r8d
0x180049132  call    ??$_Regex_search2@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@GV?$regex_traits@G@2@PEBG@std@@YA_NPEBG0PEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@0@Z; std::_Regex_search2<ushort const *,std::allocator<std::sub_match<ushort const *>>,ushort,std::regex_traits<ushort>,ushort const *>(ushort const *,ushort const *,std::match_results<ushort const *> *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type,ushort const *)
0x180049137  test    al, al
0x180049139  jnz     short loc_18004914D
0x18004913b  lea     rcx, [rbp+57h+var_A8]
0x18004913f  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180049144  add     rdi, 20h ; ' '
0x180049148  jmp     loc_18004909A
0x18004914d  mov     sil, 1
0x180049150  lea     rcx, [rbp+57h+var_A8]
0x180049154  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180049159  nop
0x18004915a  lea     rcx, [rbp+57h+var_C0]
0x18004915e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180049163  nop
0x180049164  lea     rcx, [rbp+57h+var_78]
0x180049168  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004916d  nop
0x18004916e  mov     rcx, [rsp+110h+string]; string
0x180049173  call    cs:__imp_WindowsDeleteString
0x180049179  mov     [rsp+110h+string], 0
0x180049182  lea     rcx, [rsp+110h+var_D8]
0x180049187  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004918c  nop
0x18004918d  lea     rcx, [rbp+57h+var_C8]
0x180049191  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049196  nop
0x180049197  mov     rcx, [rbp+57h+var_D0]; string
0x18004919b  call    cs:__imp_WindowsDeleteString
0x1800491a1  mov     al, sil
0x1800491a4  mov     rcx, [rbp+57h+var_18]
0x1800491a8  xor     rcx, rsp; StackCookie
0x1800491ab  call    __security_check_cookie
0x1800491b0  lea     r11, [rsp+110h+var_10]
0x1800491b8  mov     rbx, [r11+30h]
0x1800491bc  mov     rsi, [r11+38h]
0x1800491c0  mov     rsp, r11
0x1800491c3  pop     r14
0x1800491c5  pop     rdi
0x1800491c6  pop     rbp
0x1800491c7  retn
```
