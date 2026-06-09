# GetSystemIdAsHexString(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18008191c`
- end: `0x180081bd2`
- name: `?GetSystemIdAsHexString@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800351a0`

## callees

- `0x180007440`
- `0x18000af1c`
- `0x18000ba54`
- `0x18000fe0c`
- `0x18001c150`
- `0x18001c52c`
- `0x180036de8`
- `0x18008191c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081b1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081b1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081ad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081b6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081ad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081b6d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180081988`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180081a96`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180081988`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180081a96`

## string_xrefs

- `0x18008199d`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x1800819ed`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180081a3c`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180081aab`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180081b07`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180081a73`: `Windows.Security.Cryptography.CryptographicBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall GetSystemIdAsHexString(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int ActivationFactory; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, HSTRING *); // rbx
  int v24; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v26; // r8
  void *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  HSTRING string; // [rsp+20h] [rbp-68h] BYREF
  __int64 v42; // [rsp+28h] [rbp-60h] BYREF
  __int64 v43; // [rsp+30h] [rbp-58h] BYREF
  __int64 v44; // [rsp+38h] [rbp-50h] BYREF
  __int64 v45; // [rsp+40h] [rbp-48h] BYREF
  void *v46; // [rsp+48h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-38h] BYREF
  __int64 v48; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v45 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45, a2, a3, a4);
  v48 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Profile.SystemIdentification",
    0x2Cu,
    0x2Bu);
  ActivationFactory = RoGetActivationFactory(v48, &GUID_5581f42a_d3df_4d93_a37d_c41a616c6d01, &v45);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)string);
  v44 = 0;
  v9 = v45;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44, v6, v7, v8);
  v11 = v10(v9, &v44);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
      (const char *)(unsigned int)v11,
      (int)string);
  v43 = 0;
  v15 = v44;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v12, v13, v14);
  v17 = v16(v15, &v43);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
      (const char *)(unsigned int)v17,
      (int)string);
  v42 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v18, v19, v20);
  v48 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Cryptography.CryptographicBuffer",
    0x32u,
    0x31u);
  v21 = RoGetActivationFactory(v48, &GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb, &v42);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x184,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
      (const char *)(unsigned int)v21,
      (int)string);
  string = 0;
  v22 = v42;
  v23 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v42 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v24 = v23(v22, v43, &string);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
      (const char *)(unsigned int)v24,
      (int)string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  ConvertUtf16ToUtf8((char **)&v46, StringRawBuffer);
  v26 = -1;
  do
    ++v26;
  while ( *((_BYTE *)v46 + v26) );
  std::string::_Assign<char>(a1, v46, v26);
  v27 = v46;
  v46 = 0;
  if ( v27 )
    MemoryFree(v27);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v28, v29, v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v31, v32, v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44, v34, v35, v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45, v37, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x18008191c  mov     r11, rsp
0x18008191f  mov     [r11+10h], rbx
0x180081923  mov     [r11+18h], rsi
0x180081927  push    rdi
0x180081928  sub     rsp, 80h
0x18008192f  mov     rax, cs:__security_cookie
0x180081936  xor     rax, rsp
0x180081939  mov     [rsp+88h+var_18], rax
0x18008193e  mov     rsi, rcx
0x180081941  mov     qword ptr [r11-48h], 0
0x180081949  lea     rcx, [r11-48h]
0x18008194d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081952  mov     [rsp+88h+var_20], 0
0x18008195b  mov     r9d, 2Bh ; '+'; unsigned int
0x180081961  lea     r8d, [r9+1]; unsigned int
0x180081965  lea     rdx, ?RuntimeClass_Windows_System_Profile_SystemIdentification@@3QBGB; "Windows.System.Profile.SystemIdentifica"...
0x18008196c  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x180081971  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180081976  nop
0x180081977  lea     r8, [rsp+88h+var_48]
0x18008197c  lea     rdx, _GUID_5581f42a_d3df_4d93_a37d_c41a616c6d01
0x180081983  mov     rcx, [rsp+88h+var_20]
0x180081988  call    cs:__imp_RoGetActivationFactory
0x18008198e  mov     rcx, [rsp+88h]; this
0x180081996  test    eax, eax
0x180081998  jns     short loc_1800819AF
0x18008199a  mov     r9d, eax; char *
0x18008199d  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800819a4  mov     edx, 17Ah; void *
0x1800819a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800819af  mov     [rsp+88h+var_50], 0
0x1800819b8  mov     rdi, [rsp+88h+var_48]
0x1800819bd  mov     rax, [rdi]
0x1800819c0  mov     rbx, [rax+30h]
0x1800819c4  lea     rcx, [rsp+88h+var_50]
0x1800819c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800819ce  lea     rdx, [rsp+88h+var_50]
0x1800819d3  mov     rcx, rdi
0x1800819d6  mov     rax, rbx
0x1800819d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800819de  mov     rcx, [rsp+88h]; this
0x1800819e6  test    eax, eax
0x1800819e8  jns     short loc_1800819FE
0x1800819ea  mov     r9d, eax; char *
0x1800819ed  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800819f4  mov     edx, 17Dh; void *
0x1800819f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800819fe  mov     [rsp+88h+var_58], 0
0x180081a07  mov     rdi, [rsp+88h+var_50]
0x180081a0c  mov     rax, [rdi]
0x180081a0f  mov     rbx, [rax+30h]
0x180081a13  lea     rcx, [rsp+88h+var_58]
0x180081a18  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081a1d  lea     rdx, [rsp+88h+var_58]
0x180081a22  mov     rcx, rdi
0x180081a25  mov     rax, rbx
0x180081a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a2d  mov     rcx, [rsp+88h]; this
0x180081a35  test    eax, eax
0x180081a37  jns     short loc_180081A4D
0x180081a39  mov     r9d, eax; char *
0x180081a3c  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180081a43  mov     edx, 17Fh; void *
0x180081a48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081a4d  mov     [rsp+88h+var_60], 0
0x180081a56  lea     rcx, [rsp+88h+var_60]
0x180081a5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081a60  mov     [rsp+88h+var_20], 0
0x180081a69  mov     r9d, 31h ; '1'; unsigned int
0x180081a6f  lea     r8d, [r9+1]; unsigned int
0x180081a73  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_CryptographicBuffer@@3QBGB; "Windows.Security.Cryptography.Cryptogra"...
0x180081a7a  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x180081a7f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180081a84  nop
0x180081a85  lea     r8, [rsp+88h+var_60]
0x180081a8a  lea     rdx, _GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb
0x180081a91  mov     rcx, [rsp+88h+var_20]
0x180081a96  call    cs:__imp_RoGetActivationFactory
0x180081a9c  mov     rcx, [rsp+88h]; this
0x180081aa4  test    eax, eax
0x180081aa6  jns     short loc_180081ABD
0x180081aa8  mov     r9d, eax; char *
0x180081aab  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180081ab2  mov     edx, 184h; void *
0x180081ab7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081abd  mov     [rsp+88h+string], 0
0x180081ac6  mov     rdi, [rsp+88h+var_60]
0x180081acb  mov     rax, [rdi]
0x180081ace  mov     rbx, [rax+60h]
0x180081ad2  xor     ecx, ecx; string
0x180081ad4  call    cs:__imp_WindowsDeleteString
0x180081ada  mov     [rsp+88h+string], 0; int
0x180081ae3  lea     r8, [rsp+88h+string]
0x180081ae8  mov     rdx, [rsp+88h+var_58]
0x180081aed  mov     rcx, rdi
0x180081af0  mov     rax, rbx
0x180081af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081af8  mov     rcx, [rsp+88h]; this
0x180081b00  test    eax, eax
0x180081b02  jns     short loc_180081B18
0x180081b04  mov     r9d, eax; char *
0x180081b07  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180081b0e  mov     edx, 187h; void *
0x180081b13  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081b18  xor     edx, edx; length
0x180081b1a  mov     rcx, [rsp+88h+string]; string
0x180081b1f  call    cs:__imp_WindowsGetStringRawBuffer
0x180081b25  mov     rdx, rax
0x180081b28  lea     rcx, [rsp+88h+var_40]
0x180081b2d  call    ?ConvertUtf16ToUtf8@@YA?AV?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@PEBG@Z; ConvertUtf16ToUtf8(ushort const *)
0x180081b32  nop
0x180081b33  mov     rdx, [rsp+88h+var_40]
0x180081b38  or      r8, 0FFFFFFFFFFFFFFFFh
0x180081b3c  inc     r8
0x180081b3f  cmp     byte ptr [rdx+r8], 0
0x180081b44  jnz     short loc_180081B3C
0x180081b46  mov     rcx, rsi
0x180081b49  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180081b4e  nop
0x180081b4f  mov     rcx, [rsp+88h+var_40]; void *
0x180081b54  mov     [rsp+88h+var_40], 0
0x180081b5d  test    rcx, rcx
0x180081b60  jz      short loc_180081B68
0x180081b62  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180081b67  nop
0x180081b68  mov     rcx, [rsp+88h+string]; string
0x180081b6d  call    cs:__imp_WindowsDeleteString
0x180081b73  mov     [rsp+88h+string], 0
0x180081b7c  lea     rcx, [rsp+88h+var_60]
0x180081b81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081b86  nop
0x180081b87  lea     rcx, [rsp+88h+var_58]
0x180081b8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081b91  nop
0x180081b92  lea     rcx, [rsp+88h+var_50]
0x180081b97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081b9c  nop
0x180081b9d  lea     rcx, [rsp+88h+var_48]
0x180081ba2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081ba7  xor     eax, eax
0x180081ba9  jmp     short loc_180081BAF
0x180081bab  mov     eax, dword ptr [rsp+88h+string]
0x180081baf  mov     rcx, [rsp+88h+var_18]
0x180081bb4  xor     rcx, rsp; StackCookie
0x180081bb7  call    __security_check_cookie
0x180081bbc  lea     r11, [rsp+88h+var_8]
0x180081bc4  mov     rbx, [r11+18h]
0x180081bc8  mov     rsi, [r11+20h]
0x180081bcc  mov     rsp, r11
0x180081bcf  pop     rdi
0x180081bd0  retn
```
