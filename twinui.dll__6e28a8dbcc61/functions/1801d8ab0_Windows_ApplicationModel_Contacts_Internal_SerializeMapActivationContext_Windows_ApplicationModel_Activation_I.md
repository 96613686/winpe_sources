# Windows::ApplicationModel::Contacts::Internal::SerializeMapActivationContext(Windows::ApplicationModel::Activation::IContactActivatedEventArgs *,HSTRING__ * *)

- ea: `0x1801d8ab0`
- end: `0x1801d8e7d`
- name: `?SerializeMapActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUIContactActivatedEventArgs@Activation@34@PEAPEAUHSTRING__@@@Z`
- size: `973`
- prototype: `int(Windows::ApplicationModel::Contacts::Internal *__hidden this, struct Windows::ApplicationModel::Activation::IContactActivatedEventArgs *, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b7e8`
- `0x180052980`
- `0x18013d330`
- `0x1801d80a0`
- `0x1801d8714`
- `0x1801d8ab0`
- `0x1801d9288`
- `0x1801d9310`
- `0x1801d93a0`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8b77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8bc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8c28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8d17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8d60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8dd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8b77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8bc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8c28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8d17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8d60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8dd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8e1f`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::SerializeMapActivationContext(
        __int64 (__fastcall ***this)(Windows::ApplicationModel::Contacts::Internal *, GUID *, __int64 *),
        HSTRING *a2,
        HSTRING *a3)
{
  int v5; // ebx
  __int64 (__fastcall **v6)(Windows::ApplicationModel::Contacts::Internal *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v7)(Windows::ApplicationModel::Contacts::Internal *, GUID *, __int64 *); // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  HSTRING v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  HSTRING v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  HSTRING v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  HSTRING v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING *); // rbx
  HSTRING v28; // rbx
  __int64 v29; // rax
  double v30; // xmm6_8
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  HSTRING v34; // rbx
  __int64 v35; // rax
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  __int64 v38; // [rsp+28h] [rbp-58h] BYREF
  __int128 v39; // [rsp+30h] [rbp-50h] BYREF
  __int64 v40; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v41[32]; // [rsp+48h] [rbp-38h] BYREF

  *a2 = 0;
  v39 = 0;
  v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::Initialize((Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39);
  if ( v5 >= 0 )
  {
    v6 = *this;
    v40 = 0;
    v7 = *v6;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
    v5 = v7((Windows::ApplicationModel::Contacts::Internal *)this, &GUID_b32bf870_eee7_4ad2_aaf1_a87effcf00a4, &v40);
    if ( v5 >= 0 )
    {
      v8 = v40;
      v38 = 0;
      v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v38);
      v5 = v9(v8, &v38);
      if ( v5 >= 0 )
      {
        v10 = v38;
        string = 0;
        v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v5 = v11(v10, &string);
        if ( v5 >= 0 )
        {
          v12 = string;
          v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803E18B0);
          v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                 (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                 *(HSTRING *)(v13 + 24),
                 v12);
        }
        WindowsDeleteString(string);
        if ( v5 >= 0 )
        {
          v14 = v38;
          string = 0;
          v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 64LL);
          WindowsDeleteString(0);
          string = 0;
          v5 = v15(v14, &string);
          if ( v5 >= 0 )
          {
            v16 = string;
            v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803E18B8);
            v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                   (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                   *(HSTRING *)(v17 + 24),
                   v16);
          }
          WindowsDeleteString(string);
          if ( v5 >= 0 )
          {
            v18 = v38;
            string = 0;
            v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 80LL);
            WindowsDeleteString(0);
            string = 0;
            v5 = v19(v18, &string);
            if ( v5 >= 0 )
            {
              v20 = string;
              v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803E18E0);
              v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                     (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                     *(HSTRING *)(v21 + 24),
                     v20);
            }
            WindowsDeleteString(string);
            if ( v5 >= 0 )
            {
              v22 = v38;
              string = 0;
              v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 96LL);
              WindowsDeleteString(0);
              string = 0;
              v5 = v23(v22, &string);
              if ( v5 >= 0 )
              {
                v24 = string;
                v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803E18E8);
                v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                       (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                       *(HSTRING *)(v25 + 24),
                       v24);
              }
              WindowsDeleteString(string);
              if ( v5 >= 0 )
              {
                v26 = v38;
                string = 0;
                v27 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 112LL);
                WindowsDeleteString(0);
                string = 0;
                v5 = v27(v26, &string);
                if ( v5 >= 0 )
                {
                  v28 = string;
                  v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803E18D0);
                  v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                         (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                         *(HSTRING *)(v29 + 24),
                         v28);
                }
                WindowsDeleteString(string);
                if ( v5 >= 0 )
                {
                  LODWORD(string) = 0;
                  v5 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 128LL))(v38, &string);
                  if ( v5 >= 0 )
                  {
                    v30 = (double)(int)string;
                    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803E18D8);
                    v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetNumberValue(
                           (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                           *(HSTRING *)(v31 + 24),
                           v30);
                    if ( v5 >= 0 )
                    {
                      v32 = v38;
                      string = 0;
                      v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 144LL);
                      WindowsDeleteString(0);
                      string = 0;
                      v5 = v33(v32, &string);
                      if ( v5 >= 0 )
                      {
                        v34 = string;
                        v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, off_1803E18A8);
                        v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(
                               (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                               *(HSTRING *)(v35 + 24),
                               v34);
                      }
                      WindowsDeleteString(string);
                      if ( v5 >= 0 )
                        v5 = Windows::ApplicationModel::Contacts::Internal::JsonSerializer::Stringify(
                               (Windows::ApplicationModel::Contacts::Internal::JsonSerializer *)&v39,
                               a2);
                    }
                  }
                }
              }
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v38);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
  }
  Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::~JsonDeserializer((Windows::ApplicationModel::Contacts::Internal::JsonDeserializer *)&v39);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801d8ab0  mov     [rsp-18h+arg_10], rbx
0x1801d8ab5  mov     [rsp-18h+arg_18], rsi
0x1801d8aba  push    rbp
0x1801d8abb  push    rdi
0x1801d8abc  push    r14
0x1801d8abe  mov     rbp, rsp
0x1801d8ac1  sub     rsp, 80h
0x1801d8ac8  movaps  [rsp+80h+var_10], xmm6
0x1801d8acd  mov     rax, cs:__security_cookie
0x1801d8ad4  xor     rax, rsp
0x1801d8ad7  mov     [rbp+var_18], rax
0x1801d8adb  mov     rdi, rcx
0x1801d8ade  xorps   xmm0, xmm0
0x1801d8ae1  xor     r14d, r14d
0x1801d8ae4  lea     rcx, [rbp+var_50]; this
0x1801d8ae8  mov     [rdx], r14
0x1801d8aeb  mov     rsi, rdx
0x1801d8aee  movdqu  [rbp+var_50], xmm0
0x1801d8af3  call    ?Initialize@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJXZ; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::Initialize(void)
0x1801d8af8  mov     ebx, eax
0x1801d8afa  test    eax, eax
0x1801d8afc  js      loc_1801D8E49
0x1801d8b02  mov     rax, [rdi]
0x1801d8b05  lea     rcx, [rbp+var_40]
0x1801d8b09  mov     [rbp+var_40], r14
0x1801d8b0d  mov     rbx, [rax]
0x1801d8b10  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d8b15  lea     r8, [rbp+var_40]
0x1801d8b19  mov     rcx, rdi
0x1801d8b1c  lea     rdx, _GUID_b32bf870_eee7_4ad2_aaf1_a87effcf00a4
0x1801d8b23  mov     rax, rbx
0x1801d8b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8b2b  mov     ebx, eax
0x1801d8b2d  test    eax, eax
0x1801d8b2f  js      loc_1801D8E40
0x1801d8b35  mov     rdi, [rbp+var_40]
0x1801d8b39  lea     rcx, [rbp+var_58]
0x1801d8b3d  mov     [rbp+var_58], r14
0x1801d8b41  mov     rax, [rdi]
0x1801d8b44  mov     rbx, [rax+30h]
0x1801d8b48  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d8b4d  lea     rdx, [rbp+var_58]
0x1801d8b51  mov     rcx, rdi
0x1801d8b54  mov     rax, rbx
0x1801d8b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8b5c  mov     ebx, eax
0x1801d8b5e  test    eax, eax
0x1801d8b60  js      loc_1801D8E37
0x1801d8b66  mov     rdi, [rbp+var_58]
0x1801d8b6a  xor     ecx, ecx; string
0x1801d8b6c  mov     [rbp+string], r14
0x1801d8b70  mov     rax, [rdi]
0x1801d8b73  mov     rbx, [rax+30h]
0x1801d8b77  call    cs:__imp_WindowsDeleteString
0x1801d8b7d  lea     rdx, [rbp+string]
0x1801d8b81  mov     [rbp+string], r14
0x1801d8b85  mov     rcx, rdi
0x1801d8b88  mov     rax, rbx
0x1801d8b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8b90  mov     ebx, eax
0x1801d8b92  test    eax, eax
0x1801d8b94  js      short loc_1801D8BBC
0x1801d8b96  mov     rbx, [rbp+string]
0x1801d8b9a  lea     rdx, off_1803E18B0; "StreetAddress"
0x1801d8ba1  lea     rcx, [rbp+var_38]
0x1801d8ba5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8baa  mov     r8, rbx; HSTRING
0x1801d8bad  lea     rcx, [rbp+var_50]; this
0x1801d8bb1  mov     rdx, [rax+18h]; HSTRING
0x1801d8bb5  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801d8bba  mov     ebx, eax
0x1801d8bbc  mov     rcx, [rbp+string]; string
0x1801d8bc0  call    cs:__imp_WindowsDeleteString
0x1801d8bc6  test    ebx, ebx
0x1801d8bc8  js      loc_1801D8E37
0x1801d8bce  mov     rdi, [rbp+var_58]
0x1801d8bd2  xor     ecx, ecx; string
0x1801d8bd4  mov     [rbp+string], r14
0x1801d8bd8  mov     rax, [rdi]
0x1801d8bdb  mov     rbx, [rax+40h]
0x1801d8bdf  call    cs:__imp_WindowsDeleteString
0x1801d8be5  lea     rdx, [rbp+string]
0x1801d8be9  mov     [rbp+string], r14
0x1801d8bed  mov     rcx, rdi
0x1801d8bf0  mov     rax, rbx
0x1801d8bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8bf8  mov     ebx, eax
0x1801d8bfa  test    eax, eax
0x1801d8bfc  js      short loc_1801D8C24
0x1801d8bfe  mov     rbx, [rbp+string]
0x1801d8c02  lea     rdx, off_1803E18B8; "Locality"
0x1801d8c09  lea     rcx, [rbp+var_38]
0x1801d8c0d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8c12  mov     r8, rbx; HSTRING
0x1801d8c15  lea     rcx, [rbp+var_50]; this
0x1801d8c19  mov     rdx, [rax+18h]; HSTRING
0x1801d8c1d  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801d8c22  mov     ebx, eax
0x1801d8c24  mov     rcx, [rbp+string]; string
0x1801d8c28  call    cs:__imp_WindowsDeleteString
0x1801d8c2e  test    ebx, ebx
0x1801d8c30  js      loc_1801D8E37
0x1801d8c36  mov     rdi, [rbp+var_58]
0x1801d8c3a  xor     ecx, ecx; string
0x1801d8c3c  mov     [rbp+string], r14
0x1801d8c40  mov     rax, [rdi]
0x1801d8c43  mov     rbx, [rax+50h]
0x1801d8c47  call    cs:__imp_WindowsDeleteString
0x1801d8c4d  lea     rdx, [rbp+string]
0x1801d8c51  mov     [rbp+string], r14
0x1801d8c55  mov     rcx, rdi
0x1801d8c58  mov     rax, rbx
0x1801d8c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8c60  mov     ebx, eax
0x1801d8c62  test    eax, eax
0x1801d8c64  js      short loc_1801D8C8C
0x1801d8c66  mov     rbx, [rbp+string]
0x1801d8c6a  lea     rdx, off_1803E18E0; "Region"
0x1801d8c71  lea     rcx, [rbp+var_38]
0x1801d8c75  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8c7a  mov     r8, rbx; HSTRING
0x1801d8c7d  lea     rcx, [rbp+var_50]; this
0x1801d8c81  mov     rdx, [rax+18h]; HSTRING
0x1801d8c85  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801d8c8a  mov     ebx, eax
0x1801d8c8c  mov     rcx, [rbp+string]; string
0x1801d8c90  call    cs:__imp_WindowsDeleteString
0x1801d8c96  test    ebx, ebx
0x1801d8c98  js      loc_1801D8E37
0x1801d8c9e  mov     rdi, [rbp+var_58]
0x1801d8ca2  xor     ecx, ecx; string
0x1801d8ca4  mov     [rbp+string], r14
0x1801d8ca8  mov     rax, [rdi]
0x1801d8cab  mov     rbx, [rax+60h]
0x1801d8caf  call    cs:__imp_WindowsDeleteString
0x1801d8cb5  lea     rdx, [rbp+string]
0x1801d8cb9  mov     [rbp+string], r14
0x1801d8cbd  mov     rcx, rdi
0x1801d8cc0  mov     rax, rbx
0x1801d8cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8cc8  mov     ebx, eax
0x1801d8cca  test    eax, eax
0x1801d8ccc  js      short loc_1801D8CF4
0x1801d8cce  mov     rbx, [rbp+string]
0x1801d8cd2  lea     rdx, off_1803E18E8; "Country"
0x1801d8cd9  lea     rcx, [rbp+var_38]
0x1801d8cdd  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8ce2  mov     r8, rbx; HSTRING
0x1801d8ce5  lea     rcx, [rbp+var_50]; this
0x1801d8ce9  mov     rdx, [rax+18h]; HSTRING
0x1801d8ced  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801d8cf2  mov     ebx, eax
0x1801d8cf4  mov     rcx, [rbp+string]; string
0x1801d8cf8  call    cs:__imp_WindowsDeleteString
0x1801d8cfe  test    ebx, ebx
0x1801d8d00  js      loc_1801D8E37
0x1801d8d06  mov     rdi, [rbp+var_58]
0x1801d8d0a  xor     ecx, ecx; string
0x1801d8d0c  mov     [rbp+string], r14
0x1801d8d10  mov     rax, [rdi]
0x1801d8d13  mov     rbx, [rax+70h]
0x1801d8d17  call    cs:__imp_WindowsDeleteString
0x1801d8d1d  lea     rdx, [rbp+string]
0x1801d8d21  mov     [rbp+string], r14
0x1801d8d25  mov     rcx, rdi
0x1801d8d28  mov     rax, rbx
0x1801d8d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8d30  mov     ebx, eax
0x1801d8d32  test    eax, eax
0x1801d8d34  js      short loc_1801D8D5C
0x1801d8d36  mov     rbx, [rbp+string]
0x1801d8d3a  lea     rdx, off_1803E18D0; "PostalCode"
0x1801d8d41  lea     rcx, [rbp+var_38]
0x1801d8d45  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8d4a  mov     r8, rbx; HSTRING
0x1801d8d4d  lea     rcx, [rbp+var_50]; this
0x1801d8d51  mov     rdx, [rax+18h]; HSTRING
0x1801d8d55  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801d8d5a  mov     ebx, eax
0x1801d8d5c  mov     rcx, [rbp+string]; string
0x1801d8d60  call    cs:__imp_WindowsDeleteString
0x1801d8d66  test    ebx, ebx
0x1801d8d68  js      loc_1801D8E37
0x1801d8d6e  mov     rcx, [rbp+var_58]
0x1801d8d72  lea     rdx, [rbp+string]
0x1801d8d76  mov     dword ptr [rbp+string], r14d
0x1801d8d7a  mov     rax, [rcx]
0x1801d8d7d  mov     rax, [rax+80h]
0x1801d8d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8d89  mov     ebx, eax
0x1801d8d8b  test    eax, eax
0x1801d8d8d  js      loc_1801D8E37
0x1801d8d93  movd    xmm6, dword ptr [rbp+string]
0x1801d8d98  lea     rdx, off_1803E18D8; "Kind"
0x1801d8d9f  lea     rcx, [rbp+var_38]
0x1801d8da3  cvtdq2pd xmm6, xmm6
0x1801d8da7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8dac  lea     rcx, [rbp+var_50]; this
0x1801d8db0  mov     rdx, [rax+18h]; HSTRING
0x1801d8db4  movaps  xmm2, xmm6; double
0x1801d8db7  call    ?SetNumberValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@N@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetNumberValue(HSTRING__ *,double)
0x1801d8dbc  mov     ebx, eax
0x1801d8dbe  test    eax, eax
0x1801d8dc0  js      short loc_1801D8E37
0x1801d8dc2  mov     rdi, [rbp+var_58]
0x1801d8dc6  xor     ecx, ecx; string
0x1801d8dc8  mov     [rbp+string], r14
0x1801d8dcc  mov     rax, [rdi]
0x1801d8dcf  mov     rbx, [rax+90h]
0x1801d8dd6  call    cs:__imp_WindowsDeleteString
0x1801d8ddc  lea     rdx, [rbp+string]
0x1801d8de0  mov     [rbp+string], r14
0x1801d8de4  mov     rcx, rdi
0x1801d8de7  mov     rax, rbx
0x1801d8dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8def  mov     ebx, eax
0x1801d8df1  test    eax, eax
0x1801d8df3  js      short loc_1801D8E1B
0x1801d8df5  mov     rbx, [rbp+string]
0x1801d8df9  lea     rdx, off_1803E18A8; "Description"
0x1801d8e00  lea     rcx, [rbp+var_38]
0x1801d8e04  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8e09  mov     r8, rbx; HSTRING
0x1801d8e0c  lea     rcx, [rbp+var_50]; this
0x1801d8e10  mov     rdx, [rax+18h]; HSTRING
0x1801d8e14  call    ?SetStringValue@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::SetStringValue(HSTRING__ *,HSTRING__ *)
0x1801d8e19  mov     ebx, eax
0x1801d8e1b  mov     rcx, [rbp+string]; string
0x1801d8e1f  call    cs:__imp_WindowsDeleteString
0x1801d8e25  test    ebx, ebx
0x1801d8e27  js      short loc_1801D8E37
0x1801d8e29  mov     rdx, rsi; HSTRING *
0x1801d8e2c  lea     rcx, [rbp+var_50]; this
0x1801d8e30  call    ?Stringify@JsonSerializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAPEAUHSTRING__@@@Z; Windows::ApplicationModel::Contacts::Internal::JsonSerializer::Stringify(HSTRING__ * *)
0x1801d8e35  mov     ebx, eax
0x1801d8e37  lea     rcx, [rbp+var_58]
0x1801d8e3b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d8e40  lea     rcx, [rbp+var_40]
0x1801d8e44  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d8e49  lea     rcx, [rbp+var_50]; this
0x1801d8e4d  call    ??1JsonDeserializer@Internal@Contacts@ApplicationModel@Windows@@QEAA@XZ; Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::~JsonDeserializer(void)
0x1801d8e52  mov     eax, ebx
0x1801d8e54  mov     rcx, [rbp+var_18]
0x1801d8e58  xor     rcx, rsp; StackCookie
0x1801d8e5b  call    __security_check_cookie
0x1801d8e60  lea     r11, [rsp+80h+var_s0]
0x1801d8e68  mov     rbx, [r11+30h]
0x1801d8e6c  mov     rsi, [r11+38h]
0x1801d8e70  movaps  xmm6, [rsp+80h+var_10]
0x1801d8e75  mov     rsp, r11
0x1801d8e78  pop     r14
0x1801d8e7a  pop     rdi
0x1801d8e7b  pop     rbp
0x1801d8e7c  retn
```
