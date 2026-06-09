# CtaHelpers::GetWinHttpPreferredConnection(void)

- ea: `0x180085d68`
- end: `0x180085f3c`
- name: `?GetWinHttpPreferredConnection@CtaHelpers@@YA?AW4CTAConnectionType@1@XZ`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800859dc`

## callees

- `0x180007440`
- `0x18000ba54`
- `0x18000fe0c`
- `0x180036de8`
- `0x18007f6f4`
- `0x18007f744`
- `0x180085d68`
- `0x180096010`

## string_xrefs

- `0x180085dcb`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085e13`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085e69`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085e9e`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`
- `0x180085ed3`: `onecoreuap\base\diagnosis\platform\notifications\common\ctahelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 CtaHelpers::GetWinHttpPreferredConnection()
{
  __int64 v0; // r8
  __int64 v1; // r9
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // [rsp+20h] [rbp-50h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64); // [rsp+28h] [rbp-48h] BYREF
  __int64 v31; // [rsp+30h] [rbp-40h] BYREF
  __int64 v32; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v34; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v32 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Networking.Connectivity.NetworkInformation",
    0x33u,
    0x32u);
  v2 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>(
         v34,
         (__int64)&v32,
         v0,
         v1);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v2,
      v29);
  v30 = 0;
  v6 = v32;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v32 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30, v3, v4, v5);
  v8 = v7(v6, &v30);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
      (const char *)(unsigned int)v8,
      v29);
  if ( v30 )
  {
    v31 = 0;
    v16 = Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile>::As<Windows::Networking::Connectivity::IConnectionProfile2>(
            &v30,
            (__int64)&v31,
            v10,
            v11);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
        (const char *)(unsigned int)v16,
        v29);
    LOBYTE(v29) = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 56LL))(v31, &v29);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
        (const char *)(unsigned int)v17,
        v29);
    BYTE1(v29) = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v31 + 48LL))(v31, (char *)&v29 + 1);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\ctahelpers.cpp",
        (const char *)(unsigned int)v18,
        v29);
    if ( (_BYTE)v29 )
    {
      v22 = 1;
    }
    else
    {
      v22 = 2;
      if ( BYTE1(v29) )
        v22 = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31, v19, v20, v21);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30, v23, v24, v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32, v26, v27, v28);
    return v22;
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30, v9, v10, v11);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32, v12, v13, v14);
    return 3;
  }
}

```

## disassembly

```asm
0x180085d68  mov     [rsp-8+arg_0], rbx
0x180085d6d  mov     [rsp-8+arg_8], rdi
0x180085d72  push    rbp
0x180085d73  mov     rbp, rsp
0x180085d76  sub     rsp, 70h
0x180085d7a  mov     rax, cs:__security_cookie
0x180085d81  xor     rax, rsp
0x180085d84  mov     [rbp+var_10], rax
0x180085d88  mov     [rbp+var_38], 0
0x180085d90  mov     [rbp+var_18], 0
0x180085d98  mov     r9d, 32h ; '2'; unsigned int
0x180085d9e  lea     r8d, [r9+1]; unsigned int
0x180085da2  lea     rdx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x180085da9  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180085dad  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180085db2  nop
0x180085db3  lea     rdx, [rbp+var_38]
0x180085db7  mov     rcx, [rbp+var_18]
0x180085dbb  call    ??$GetActivationFactory@V?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>>)
0x180085dc0  mov     rcx, [rbp+8]; this
0x180085dc4  test    eax, eax
0x180085dc6  jns     short loc_180085DDD
0x180085dc8  mov     r9d, eax; char *
0x180085dcb  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085dd2  mov     edx, 21h ; '!'; void *
0x180085dd7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085ddd  mov     [rbp+var_48], 0
0x180085de5  mov     rdi, [rbp+var_38]
0x180085de9  mov     rax, [rdi]
0x180085dec  mov     rbx, [rax+38h]
0x180085df0  lea     rcx, [rbp+var_48]
0x180085df4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085df9  lea     rdx, [rbp+var_48]
0x180085dfd  mov     rcx, rdi
0x180085e00  mov     rax, rbx
0x180085e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e08  mov     rcx, [rbp+8]; this
0x180085e0c  test    eax, eax
0x180085e0e  jns     short loc_180085E25
0x180085e10  mov     r9d, eax; char *
0x180085e13  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085e1a  mov     edx, 24h ; '$'; void *
0x180085e1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085e25  cmp     [rbp+var_48], 0
0x180085e2a  jnz     short loc_180085E49
0x180085e2c  lea     rcx, [rbp+var_48]
0x180085e30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085e35  nop
0x180085e36  lea     rcx, [rbp+var_38]
0x180085e3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085e3f  mov     eax, 3
0x180085e44  jmp     loc_180085F1E
0x180085e49  mov     [rbp+var_40], 0
0x180085e51  lea     rdx, [rbp+var_40]
0x180085e55  lea     rcx, [rbp+var_48]
0x180085e59  call    ??$As@UIConnectionProfile2@Connectivity@Networking@Windows@@@?$ComPtr@UIConnectionProfile@Connectivity@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIConnectionProfile2@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile>::As<Windows::Networking::Connectivity::IConnectionProfile2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::IConnectionProfile2>>)
0x180085e5e  mov     rcx, [rbp+8]; this
0x180085e62  test    eax, eax
0x180085e64  jns     short loc_180085E7B
0x180085e66  mov     r9d, eax; char *
0x180085e69  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085e70  mov     edx, 2Eh ; '.'; void *
0x180085e75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085e7b  mov     [rbp+var_50], 0
0x180085e7f  mov     rcx, [rbp+var_40]
0x180085e83  mov     rax, [rcx]
0x180085e86  lea     rdx, [rbp+var_50]
0x180085e8a  mov     rax, [rax+38h]
0x180085e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e93  mov     rcx, [rbp+8]; this
0x180085e97  test    eax, eax
0x180085e99  jns     short loc_180085EB0
0x180085e9b  mov     r9d, eax; char *
0x180085e9e  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085ea5  mov     edx, 30h ; '0'; void *
0x180085eaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085eb0  mov     [rbp+var_4F], 0
0x180085eb4  mov     rcx, [rbp+var_40]
0x180085eb8  mov     rax, [rcx]
0x180085ebb  lea     rdx, [rbp+var_4F]
0x180085ebf  mov     rax, [rax+30h]
0x180085ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ec8  mov     rcx, [rbp+8]; this
0x180085ecc  test    eax, eax
0x180085ece  jns     short loc_180085EE5
0x180085ed0  mov     r9d, eax; char *
0x180085ed3  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085eda  mov     edx, 32h ; '2'; void *
0x180085edf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085ee5  cmp     [rbp+var_50], 0
0x180085ee9  jz      short loc_180085EF2
0x180085eeb  mov     ebx, 1
0x180085ef0  jmp     short loc_180085EFF
0x180085ef2  mov     ebx, 2
0x180085ef7  xor     ecx, ecx
0x180085ef9  cmp     [rbp+var_4F], cl
0x180085efc  cmovnz  ebx, ecx
0x180085eff  lea     rcx, [rbp+var_40]
0x180085f03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085f08  nop
0x180085f09  lea     rcx, [rbp+var_48]
0x180085f0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085f12  nop
0x180085f13  lea     rcx, [rbp+var_38]
0x180085f17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180085f1c  mov     eax, ebx
0x180085f1e  mov     rcx, [rbp+var_10]
0x180085f22  xor     rcx, rsp; StackCookie
0x180085f25  call    __security_check_cookie
0x180085f2a  lea     r11, [rsp+70h+var_s0]
0x180085f2f  mov     rbx, [r11+10h]
0x180085f33  mov     rdi, [r11+18h]
0x180085f37  mov     rsp, r11
0x180085f3a  pop     rbp
0x180085f3b  retn
```
