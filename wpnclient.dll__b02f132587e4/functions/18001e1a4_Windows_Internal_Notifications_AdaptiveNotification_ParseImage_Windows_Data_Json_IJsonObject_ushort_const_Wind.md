# Windows::Internal::Notifications::AdaptiveNotification::ParseImage(Windows::Data::Json::IJsonObject *,ushort const *,Windows::Internal::Notifications::IAdaptiveImage * *)

- ea: `0x18001e1a4`
- end: `0x18001e522`
- name: `?ParseImage@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@PEBGPEAPEAUIAdaptiveImage@234@@Z`
- size: `894`
- prototype: `void(Windows::Internal::Notifications::AdaptiveNotification *__hidden this, struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *, struct Windows::Internal::Notifications::IAdaptiveImage **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dccc`

## callees

- `0x180005670`
- `0x18000dc30`
- `0x180013f00`
- `0x180014500`
- `0x180014550`
- `0x1800153b4`
- `0x18001b848`
- `0x18001e1a4`
- `0x18001eb9c`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e3a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e42c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e4dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e4eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e4f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e3a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e42c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e4dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e4eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e4f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Windows::Internal::Notifications::AdaptiveNotification::ParseImage(
        Windows::Internal::Notifications::AdaptiveNotification *this,
        struct Windows::Data::Json::IJsonObject *a2,
        const unsigned __int16 *a3,
        struct Windows::Internal::Notifications::IAdaptiveImage **a4)
{
  int (__fastcall *v7)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *); // rbx
  _QWORD *v8; // rax
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, __int64 *); // rbx
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, HSTRING, __int64 *); // rbx
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, __int64 *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v17; // rax
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  __int64 v22; // rdi
  int (__fastcall *v23)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v24; // rax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  int v27; // eax
  __int64 v28; // rdi
  int (__fastcall *v29)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v30; // rax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING *); // rbx
  int v33; // eax
  int v34; // eax
  __int64 v35; // [rsp+20h] [rbp-49h] BYREF
  HSTRING v36; // [rsp+28h] [rbp-41h] BYREF
  HSTRING v37; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  __int64 v39; // [rsp+40h] [rbp-29h] BYREF
  __int64 v40; // [rsp+48h] [rbp-21h] BYREF
  __int64 v41; // [rsp+50h] [rbp-19h] BYREF
  __int64 v42; // [rsp+58h] [rbp-11h] BYREF
  __int64 v43; // [rsp+60h] [rbp-9h] BYREF
  __int64 v44; // [rsp+68h] [rbp-1h] BYREF
  HSTRING v45[4]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a4 = 0;
  string = 0;
  v37 = 0;
  v36 = 0;
  v44 = 0;
  v7 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  v8 = (_QWORD *)Windows::Internal::StringReference::StringReference(v45, L"images");
  if ( v7(a2, *v8, &v44) >= 0 )
  {
    v43 = 0;
    v9 = v44;
    v10 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    if ( v10(v9, &v43) >= 0 )
    {
      v42 = 0;
      v11 = v43;
      v12 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v43 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v45, a3);
      if ( v12(v11, v45[0], &v42) >= 0 )
      {
        v35 = 0;
        v13 = v42;
        v14 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 96LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        if ( v14(v13, &v35) >= 0 )
        {
          v41 = 0;
          v15 = v35;
          v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
          v17 = (_QWORD *)Windows::Internal::StringReference::StringReference(v45, L"url");
          v18 = v16(v15, *v17, &v41);
          if ( v18 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xA7,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
              (const char *)(unsigned int)v18,
              v35);
          v19 = v41;
          v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 64LL);
          WindowsDeleteString(string);
          string = 0;
          v21 = v20(v19, &string);
          if ( v21 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xA8,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
              (const char *)(unsigned int)v21,
              v35);
          v40 = 0;
          v22 = v35;
          v23 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
          v24 = (_QWORD *)Windows::Internal::StringReference::StringReference(v45, L"style");
          if ( v23(v22, *v24, &v40) >= 0 )
          {
            v25 = v40;
            v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 64LL);
            WindowsDeleteString(v37);
            v37 = 0;
            v27 = v26(v25, &v37);
            if ( v27 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xAD,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
                (const char *)(unsigned int)v27,
                v35);
          }
          v39 = 0;
          v28 = v35;
          v29 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          v30 = (_QWORD *)Windows::Internal::StringReference::StringReference(v45, L"altText");
          if ( v29(v28, *v30, &v39) >= 0 )
          {
            v31 = v39;
            v32 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 64LL);
            WindowsDeleteString(v36);
            v36 = 0;
            v33 = v32(v31, &v36);
            if ( v33 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xB3,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
                (const char *)(unsigned int)v33,
                v35);
          }
          v34 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Notifications::AdaptiveImage,Windows::Internal::Notifications::IAdaptiveImage,Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(
                  a4,
                  &string,
                  &v37,
                  &v36);
          if ( v34 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xB6,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
              (const char *)(unsigned int)v34,
              v35);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  WindowsDeleteString(v36);
  v36 = 0;
  WindowsDeleteString(v37);
  v37 = 0;
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x18001e1a4  mov     [rsp-8+arg_0], rbx
0x18001e1a9  push    rbp
0x18001e1aa  push    rsi
0x18001e1ab  push    rdi
0x18001e1ac  push    r14
0x18001e1ae  push    r15
0x18001e1b0  lea     rbp, [rsp-37h]
0x18001e1b5  sub     rsp, 0A0h
0x18001e1bc  mov     rax, cs:__security_cookie
0x18001e1c3  xor     rax, rsp
0x18001e1c6  mov     [rbp+57h+var_30], rax
0x18001e1ca  mov     r14, r9
0x18001e1cd  mov     rsi, r8
0x18001e1d0  mov     rdi, rdx
0x18001e1d3  xor     r15d, r15d
0x18001e1d6  mov     [r9], r15
0x18001e1d9  mov     [rbp+57h+string], r15
0x18001e1dd  mov     [rbp+57h+var_90], r15
0x18001e1e1  mov     [rbp+57h+var_98], r15
0x18001e1e5  mov     [rbp+57h+var_58], r15
0x18001e1e9  mov     rax, [rdx]
0x18001e1ec  mov     rbx, [rax+30h]
0x18001e1f0  lea     rcx, [rbp+57h+var_58]
0x18001e1f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e1f9  lea     rdx, aImages; "images"
0x18001e200  lea     rcx, [rbp+57h+var_50]; string
0x18001e204  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x18001e209  lea     r8, [rbp+57h+var_58]
0x18001e20d  mov     rdx, [rax]
0x18001e210  mov     rcx, rdi
0x18001e213  mov     rax, rbx
0x18001e216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e21b  test    eax, eax
0x18001e21d  js      loc_18001E4CF
0x18001e223  mov     [rbp+57h+var_60], r15
0x18001e227  mov     rdi, [rbp+57h+var_58]
0x18001e22b  mov     rax, [rdi]
0x18001e22e  mov     rbx, [rax+60h]
0x18001e232  lea     rcx, [rbp+57h+var_60]
0x18001e236  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e23b  lea     rdx, [rbp+57h+var_60]
0x18001e23f  mov     rcx, rdi
0x18001e242  mov     rax, rbx
0x18001e245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e24a  test    eax, eax
0x18001e24c  js      loc_18001E4C5
0x18001e252  mov     [rbp+57h+var_68], r15
0x18001e256  mov     rdi, [rbp+57h+var_60]
0x18001e25a  mov     rax, [rdi]
0x18001e25d  mov     rbx, [rax+30h]
0x18001e261  lea     rcx, [rbp+57h+var_68]
0x18001e265  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e26a  mov     rdx, rsi; unsigned __int16 *
0x18001e26d  lea     rcx, [rbp+57h+var_50]; this
0x18001e271  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001e276  lea     r8, [rbp+57h+var_68]
0x18001e27a  mov     rdx, [rbp+57h+var_50]
0x18001e27e  mov     rcx, rdi
0x18001e281  mov     rax, rbx
0x18001e284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e289  test    eax, eax
0x18001e28b  js      loc_18001E4BB
0x18001e291  mov     [rbp+57h+var_A0], r15
0x18001e295  mov     rdi, [rbp+57h+var_68]
0x18001e299  mov     rax, [rdi]
0x18001e29c  mov     rbx, [rax+60h]
0x18001e2a0  lea     rcx, [rbp+57h+var_A0]
0x18001e2a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e2a9  lea     rdx, [rbp+57h+var_A0]
0x18001e2ad  mov     rcx, rdi
0x18001e2b0  mov     rax, rbx
0x18001e2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2b8  test    eax, eax
0x18001e2ba  js      loc_18001E4B1
0x18001e2c0  mov     [rbp+57h+var_70], r15
0x18001e2c4  mov     rdi, [rbp+57h+var_A0]
0x18001e2c8  mov     rax, [rdi]
0x18001e2cb  mov     rbx, [rax+30h]
0x18001e2cf  lea     rcx, [rbp+57h+var_70]
0x18001e2d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e2d8  lea     rdx, aUrl; "url"
0x18001e2df  lea     rcx, [rbp+57h+var_50]; string
0x18001e2e3  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x18001e2e8  lea     r8, [rbp+57h+var_70]
0x18001e2ec  mov     rdx, [rax]
0x18001e2ef  mov     rcx, rdi
0x18001e2f2  mov     rax, rbx
0x18001e2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2fa  mov     rcx, [rbp+5Fh]; this
0x18001e2fe  test    eax, eax
0x18001e300  jns     short loc_18001E317
0x18001e302  mov     r9d, eax; char *
0x18001e305  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e30c  mov     edx, 0A7h; void *
0x18001e311  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e317  mov     rdi, [rbp+57h+var_70]
0x18001e31b  mov     rax, [rdi]
0x18001e31e  mov     rbx, [rax+40h]
0x18001e322  mov     rcx, [rbp+57h+string]; string
0x18001e326  call    cs:__imp_WindowsDeleteString
0x18001e32c  mov     [rbp+57h+string], r15
0x18001e330  lea     rdx, [rbp+57h+string]
0x18001e334  mov     rcx, rdi
0x18001e337  mov     rax, rbx
0x18001e33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e33f  mov     rcx, [rbp+5Fh]; this
0x18001e343  test    eax, eax
0x18001e345  jns     short loc_18001E35C
0x18001e347  mov     r9d, eax; char *
0x18001e34a  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e351  mov     edx, 0A8h; void *
0x18001e356  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e35c  mov     [rbp+57h+var_78], r15
0x18001e360  mov     rdi, [rbp+57h+var_A0]
0x18001e364  mov     rax, [rdi]
0x18001e367  mov     rbx, [rax+30h]
0x18001e36b  lea     rcx, [rbp+57h+var_78]
0x18001e36f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e374  lea     rdx, aStyle; "style"
0x18001e37b  lea     rcx, [rbp+57h+var_50]; string
0x18001e37f  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x18001e384  lea     r8, [rbp+57h+var_78]
0x18001e388  mov     rdx, [rax]
0x18001e38b  mov     rcx, rdi
0x18001e38e  mov     rax, rbx
0x18001e391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e396  test    eax, eax
0x18001e398  js      short loc_18001E3DF
0x18001e39a  mov     rdi, [rbp+57h+var_78]
0x18001e39e  mov     rax, [rdi]
0x18001e3a1  mov     rbx, [rax+40h]
0x18001e3a5  mov     rcx, [rbp+57h+var_90]; string
0x18001e3a9  call    cs:__imp_WindowsDeleteString
0x18001e3af  mov     [rbp+57h+var_90], r15
0x18001e3b3  lea     rdx, [rbp+57h+var_90]
0x18001e3b7  mov     rcx, rdi
0x18001e3ba  mov     rax, rbx
0x18001e3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3c2  mov     rcx, [rbp+5Fh]; this
0x18001e3c6  test    eax, eax
0x18001e3c8  jns     short loc_18001E3DF
0x18001e3ca  mov     r9d, eax; char *
0x18001e3cd  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e3d4  mov     edx, 0ADh; void *
0x18001e3d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e3df  mov     [rbp+57h+var_80], r15
0x18001e3e3  mov     rdi, [rbp+57h+var_A0]
0x18001e3e7  mov     rax, [rdi]
0x18001e3ea  mov     rbx, [rax+30h]
0x18001e3ee  lea     rcx, [rbp+57h+var_80]
0x18001e3f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e3f7  lea     rdx, aAlttext; "altText"
0x18001e3fe  lea     rcx, [rbp+57h+var_50]; string
0x18001e402  call    ??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[8])
0x18001e407  lea     r8, [rbp+57h+var_80]
0x18001e40b  mov     rdx, [rax]
0x18001e40e  mov     rcx, rdi
0x18001e411  mov     rax, rbx
0x18001e414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e419  test    eax, eax
0x18001e41b  js      short loc_18001E462
0x18001e41d  mov     rdi, [rbp+57h+var_80]
0x18001e421  mov     rax, [rdi]
0x18001e424  mov     rbx, [rax+40h]
0x18001e428  mov     rcx, [rbp+57h+var_98]; string
0x18001e42c  call    cs:__imp_WindowsDeleteString
0x18001e432  mov     [rbp+57h+var_98], r15
0x18001e436  lea     rdx, [rbp+57h+var_98]
0x18001e43a  mov     rcx, rdi
0x18001e43d  mov     rax, rbx
0x18001e440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e445  mov     rcx, [rbp+5Fh]; this
0x18001e449  test    eax, eax
0x18001e44b  jns     short loc_18001E462
0x18001e44d  mov     r9d, eax; char *
0x18001e450  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e457  mov     edx, 0B3h; void *
0x18001e45c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e462  lea     r9, [rbp+57h+var_98]
0x18001e466  lea     r8, [rbp+57h+var_90]
0x18001e46a  lea     rdx, [rbp+57h+string]
0x18001e46e  mov     rcx, r14
0x18001e471  call    ??$MakeAndInitialize@VAdaptiveImage@Notifications@Internal@Windows@@UIAdaptiveImage@234@VHString@Wrappers@WRL@Microsoft@@V6789@V6789@@Details@WRL@Microsoft@@YAJPEAPEAUIAdaptiveImage@Notifications@Internal@Windows@@$$QEAVHString@Wrappers@12@11@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Notifications::AdaptiveImage,Windows::Internal::Notifications::IAdaptiveImage,Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(Windows::Internal::Notifications::IAdaptiveImage * *,Microsoft::WRL::Wrappers::HString &&,Microsoft::WRL::Wrappers::HString &&,Microsoft::WRL::Wrappers::HString &&)
0x18001e476  mov     rcx, [rbp+5Fh]; this
0x18001e47a  test    eax, eax
0x18001e47c  jns     short loc_18001E493
0x18001e47e  mov     r9d, eax; char *
0x18001e481  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e488  mov     edx, 0B6h; void *
0x18001e48d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e493  lea     rcx, [rbp+57h+var_80]
0x18001e497  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e49c  nop
0x18001e49d  lea     rcx, [rbp+57h+var_78]
0x18001e4a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e4a6  nop
0x18001e4a7  lea     rcx, [rbp+57h+var_70]
0x18001e4ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e4b0  nop
0x18001e4b1  lea     rcx, [rbp+57h+var_A0]
0x18001e4b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e4ba  nop
0x18001e4bb  lea     rcx, [rbp+57h+var_68]
0x18001e4bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e4c4  nop
0x18001e4c5  lea     rcx, [rbp+57h+var_60]
0x18001e4c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e4ce  nop
0x18001e4cf  lea     rcx, [rbp+57h+var_58]
0x18001e4d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e4d8  nop
0x18001e4d9  mov     rcx, [rbp+57h+var_98]; string
0x18001e4dd  call    cs:__imp_WindowsDeleteString
0x18001e4e3  mov     [rbp+57h+var_98], r15
0x18001e4e7  mov     rcx, [rbp+57h+var_90]; string
0x18001e4eb  call    cs:__imp_WindowsDeleteString
0x18001e4f1  mov     [rbp+57h+var_90], r15
0x18001e4f5  mov     rcx, [rbp+57h+string]; string
0x18001e4f9  call    cs:__imp_WindowsDeleteString
0x18001e4ff  mov     rcx, [rbp+57h+var_30]
0x18001e503  xor     rcx, rsp; StackCookie
0x18001e506  call    __security_check_cookie
0x18001e50b  mov     rbx, [rsp+0C0h+arg_0]
0x18001e513  add     rsp, 0A0h
0x18001e51a  pop     r15
0x18001e51c  pop     r14
0x18001e51e  pop     rdi
0x18001e51f  pop     rsi
0x18001e520  pop     rbp
0x18001e521  retn
```
