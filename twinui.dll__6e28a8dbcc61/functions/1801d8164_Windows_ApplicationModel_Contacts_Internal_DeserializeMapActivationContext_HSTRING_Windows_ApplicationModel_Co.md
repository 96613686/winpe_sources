# Windows::ApplicationModel::Contacts::Internal::DeserializeMapActivationContext(HSTRING__ *,Windows::ApplicationModel::Contacts::IContactAddress * *)

- ea: `0x1801d8164`
- end: `0x1801d84ea`
- name: `?DeserializeMapActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUHSTRING__@@PEAPEAUIContactAddress@234@@Z`
- size: `902`
- prototype: `__int64 __fastcall(HSTRING this, HSTRING, struct Windows::ApplicationModel::Contacts::IContactAddress **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801cd044`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x180052980`
- `0x18013d330`
- `0x1801d8000`
- `0x1801d80a0`
- `0x1801d8164`
- `0x1801d8630`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d81e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d824d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d82a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d82b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d830b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d831f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d83dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d844d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d84a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d81e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d824d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d82a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d82b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d830b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d831f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d8388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d83dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d844d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d84a5`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::DeserializeMapActivationContext(
        HSTRING this,
        _QWORD *a2,
        struct Windows::ApplicationModel::Contacts::IContactAddress **a3)
{
  int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  __int64 v14; // [rsp+28h] [rbp-48h] BYREF
  __int128 v15; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h]

  *a2 = 0;
  v15 = 0;
  v4 = Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::Initialize(
         (Windows::ApplicationModel::Contacts::Internal::JsonDeserializer *)&v15,
         this);
  if ( v4 >= 0 )
  {
    v14 = 0;
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.Contacts.ContactAddress",
      0x31u,
      0x30u);
    v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContactAddress>>(
           v17,
           &v14);
    if ( v4 >= 0 )
    {
      WindowsDeleteString(0);
      *(double *)&string = 0.0;
      v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E18B0);
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
             v15,
             *(_QWORD *)(v5 + 24),
             &string);
      if ( v4 >= 0 )
        v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 56LL))(v14, string);
      WindowsDeleteString(string);
      if ( v4 >= 0 )
      {
        *(double *)&string = 0.0;
        WindowsDeleteString(0);
        *(double *)&string = 0.0;
        v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E18B8);
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
               v15,
               *(_QWORD *)(v6 + 24),
               &string);
        if ( v4 >= 0 )
          v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 72LL))(v14, string);
        WindowsDeleteString(string);
        if ( v4 >= 0 )
        {
          *(double *)&string = 0.0;
          WindowsDeleteString(0);
          *(double *)&string = 0.0;
          v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E18E0);
          v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                 v15,
                 *(_QWORD *)(v7 + 24),
                 &string);
          if ( v4 >= 0 )
            v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 88LL))(v14, string);
          WindowsDeleteString(string);
          if ( v4 >= 0 )
          {
            *(double *)&string = 0.0;
            WindowsDeleteString(0);
            *(double *)&string = 0.0;
            v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E18E8);
            v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                   v15,
                   *(_QWORD *)(v8 + 24),
                   &string);
            if ( v4 >= 0 )
              v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 104LL))(v14, string);
            WindowsDeleteString(string);
            if ( v4 >= 0 )
            {
              *(double *)&string = 0.0;
              WindowsDeleteString(0);
              *(double *)&string = 0.0;
              v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E18D0);
              v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                     v15,
                     *(_QWORD *)(v9 + 24),
                     &string);
              if ( v4 >= 0 )
                v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 120LL))(v14, string);
              WindowsDeleteString(string);
              if ( v4 >= 0 )
              {
                *(double *)&string = 0.0;
                v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E18D8);
                v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 88LL))(
                       v15,
                       *(_QWORD *)(v10 + 24),
                       &string);
                if ( v4 >= 0 )
                {
                  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 136LL))(
                         v14,
                         (unsigned int)(int)*(double *)&string);
                  if ( v4 >= 0 )
                  {
                    *(double *)&string = 0.0;
                    WindowsDeleteString(0);
                    *(double *)&string = 0.0;
                    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803E18A8);
                    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                           v15,
                           *(_QWORD *)(v11 + 24),
                           &string);
                    if ( v4 >= 0 )
                      v4 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 152LL))(v14, string);
                    WindowsDeleteString(string);
                    if ( v4 >= 0 )
                    {
                      *a2 = v14;
                      v14 = 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v14);
  }
  Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::~JsonDeserializer((Windows::ApplicationModel::Contacts::Internal::JsonDeserializer *)&v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801d8164  mov     [rsp-18h+arg_10], rbx
0x1801d8169  push    rbp
0x1801d816a  push    rsi
0x1801d816b  push    rdi
0x1801d816c  mov     rbp, rsp
0x1801d816f  sub     rsp, 70h
0x1801d8173  mov     rax, cs:__security_cookie
0x1801d817a  xor     rax, rsp
0x1801d817d  mov     [rbp+var_10], rax
0x1801d8181  mov     rdi, rdx
0x1801d8184  xorps   xmm0, xmm0
0x1801d8187  xor     esi, esi
0x1801d8189  mov     [rdx], rsi
0x1801d818c  mov     rdx, rcx; HSTRING
0x1801d818f  lea     rcx, [rbp+var_40]; this
0x1801d8193  movdqu  [rbp+var_40], xmm0
0x1801d8198  call    ?Initialize@JsonDeserializer@Internal@Contacts@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::Initialize(HSTRING__ *)
0x1801d819d  mov     ebx, eax
0x1801d819f  test    eax, eax
0x1801d81a1  js      loc_1801D84C3
0x1801d81a7  lea     r9d, [rsi+30h]; unsigned int
0x1801d81ab  mov     [rbp+var_48], rsi
0x1801d81af  lea     r8d, [rsi+31h]; unsigned int
0x1801d81b3  mov     [rbp+var_18], rsi
0x1801d81b7  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Contacts_ContactAddress@@3QBGB; "Windows.ApplicationModel.Contacts.Conta"...
0x1801d81be  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801d81c2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d81c7  mov     rcx, [rbp+var_18]
0x1801d81cb  lea     rdx, [rbp+var_48]
0x1801d81cf  call    ??$ActivateInstance@V?$ComPtr@UIContactAddress@Contacts@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIContactAddress@Contacts@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContactAddress>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContactAddress>>)
0x1801d81d4  mov     ebx, eax
0x1801d81d6  test    eax, eax
0x1801d81d8  js      loc_1801D84BA
0x1801d81de  xor     ecx, ecx; string
0x1801d81e0  mov     [rbp+string], rsi
0x1801d81e4  call    cs:__imp_WindowsDeleteString
0x1801d81ea  lea     rdx, off_1803E18B0; "StreetAddress"
0x1801d81f1  mov     [rbp+string], rsi
0x1801d81f5  lea     rcx, [rbp+hstringHeader]
0x1801d81f9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d81fe  mov     rcx, qword ptr [rbp+var_40]
0x1801d8202  lea     r8, [rbp+string]
0x1801d8206  mov     r9, rax
0x1801d8209  mov     rdx, [rcx]
0x1801d820c  mov     rax, [rdx+50h]
0x1801d8210  mov     rdx, [r9+18h]
0x1801d8214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8219  mov     ebx, eax
0x1801d821b  test    eax, eax
0x1801d821d  js      short loc_1801D8235
0x1801d821f  mov     rcx, [rbp+var_48]
0x1801d8223  mov     rdx, [rbp+string]
0x1801d8227  mov     rax, [rcx]
0x1801d822a  mov     rax, [rax+38h]
0x1801d822e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8233  mov     ebx, eax
0x1801d8235  mov     rcx, [rbp+string]; string
0x1801d8239  call    cs:__imp_WindowsDeleteString
0x1801d823f  test    ebx, ebx
0x1801d8241  js      loc_1801D84BA
0x1801d8247  xor     ecx, ecx; string
0x1801d8249  mov     [rbp+string], rsi
0x1801d824d  call    cs:__imp_WindowsDeleteString
0x1801d8253  lea     rdx, off_1803E18B8; "Locality"
0x1801d825a  mov     [rbp+string], rsi
0x1801d825e  lea     rcx, [rbp+hstringHeader]
0x1801d8262  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8267  mov     rcx, qword ptr [rbp+var_40]
0x1801d826b  lea     r8, [rbp+string]
0x1801d826f  mov     r9, rax
0x1801d8272  mov     rdx, [rcx]
0x1801d8275  mov     rax, [rdx+50h]
0x1801d8279  mov     rdx, [r9+18h]
0x1801d827d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8282  mov     ebx, eax
0x1801d8284  test    eax, eax
0x1801d8286  js      short loc_1801D829E
0x1801d8288  mov     rcx, [rbp+var_48]
0x1801d828c  mov     rdx, [rbp+string]
0x1801d8290  mov     rax, [rcx]
0x1801d8293  mov     rax, [rax+48h]
0x1801d8297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d829c  mov     ebx, eax
0x1801d829e  mov     rcx, [rbp+string]; string
0x1801d82a2  call    cs:__imp_WindowsDeleteString
0x1801d82a8  test    ebx, ebx
0x1801d82aa  js      loc_1801D84BA
0x1801d82b0  xor     ecx, ecx; string
0x1801d82b2  mov     [rbp+string], rsi
0x1801d82b6  call    cs:__imp_WindowsDeleteString
0x1801d82bc  lea     rdx, off_1803E18E0; "Region"
0x1801d82c3  mov     [rbp+string], rsi
0x1801d82c7  lea     rcx, [rbp+hstringHeader]
0x1801d82cb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d82d0  mov     rcx, qword ptr [rbp+var_40]
0x1801d82d4  lea     r8, [rbp+string]
0x1801d82d8  mov     r9, rax
0x1801d82db  mov     rdx, [rcx]
0x1801d82de  mov     rax, [rdx+50h]
0x1801d82e2  mov     rdx, [r9+18h]
0x1801d82e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d82eb  mov     ebx, eax
0x1801d82ed  test    eax, eax
0x1801d82ef  js      short loc_1801D8307
0x1801d82f1  mov     rcx, [rbp+var_48]
0x1801d82f5  mov     rdx, [rbp+string]
0x1801d82f9  mov     rax, [rcx]
0x1801d82fc  mov     rax, [rax+58h]
0x1801d8300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8305  mov     ebx, eax
0x1801d8307  mov     rcx, [rbp+string]; string
0x1801d830b  call    cs:__imp_WindowsDeleteString
0x1801d8311  test    ebx, ebx
0x1801d8313  js      loc_1801D84BA
0x1801d8319  xor     ecx, ecx; string
0x1801d831b  mov     [rbp+string], rsi
0x1801d831f  call    cs:__imp_WindowsDeleteString
0x1801d8325  lea     rdx, off_1803E18E8; "Country"
0x1801d832c  mov     [rbp+string], rsi
0x1801d8330  lea     rcx, [rbp+hstringHeader]
0x1801d8334  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8339  mov     rcx, qword ptr [rbp+var_40]
0x1801d833d  lea     r8, [rbp+string]
0x1801d8341  mov     r9, rax
0x1801d8344  mov     rdx, [rcx]
0x1801d8347  mov     rax, [rdx+50h]
0x1801d834b  mov     rdx, [r9+18h]
0x1801d834f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8354  mov     ebx, eax
0x1801d8356  test    eax, eax
0x1801d8358  js      short loc_1801D8370
0x1801d835a  mov     rcx, [rbp+var_48]
0x1801d835e  mov     rdx, [rbp+string]
0x1801d8362  mov     rax, [rcx]
0x1801d8365  mov     rax, [rax+68h]
0x1801d8369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d836e  mov     ebx, eax
0x1801d8370  mov     rcx, [rbp+string]; string
0x1801d8374  call    cs:__imp_WindowsDeleteString
0x1801d837a  test    ebx, ebx
0x1801d837c  js      loc_1801D84BA
0x1801d8382  xor     ecx, ecx; string
0x1801d8384  mov     [rbp+string], rsi
0x1801d8388  call    cs:__imp_WindowsDeleteString
0x1801d838e  lea     rdx, off_1803E18D0; "PostalCode"
0x1801d8395  mov     [rbp+string], rsi
0x1801d8399  lea     rcx, [rbp+hstringHeader]
0x1801d839d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d83a2  mov     rcx, qword ptr [rbp+var_40]
0x1801d83a6  lea     r8, [rbp+string]
0x1801d83aa  mov     r9, rax
0x1801d83ad  mov     rdx, [rcx]
0x1801d83b0  mov     rax, [rdx+50h]
0x1801d83b4  mov     rdx, [r9+18h]
0x1801d83b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d83bd  mov     ebx, eax
0x1801d83bf  test    eax, eax
0x1801d83c1  js      short loc_1801D83D9
0x1801d83c3  mov     rcx, [rbp+var_48]
0x1801d83c7  mov     rdx, [rbp+string]
0x1801d83cb  mov     rax, [rcx]
0x1801d83ce  mov     rax, [rax+78h]
0x1801d83d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d83d7  mov     ebx, eax
0x1801d83d9  mov     rcx, [rbp+string]; string
0x1801d83dd  call    cs:__imp_WindowsDeleteString
0x1801d83e3  test    ebx, ebx
0x1801d83e5  js      loc_1801D84BA
0x1801d83eb  xorps   xmm0, xmm0
0x1801d83ee  lea     rdx, off_1803E18D8; "Kind"
0x1801d83f5  lea     rcx, [rbp+hstringHeader]
0x1801d83f9  movsd   [rbp+string], xmm0
0x1801d83fe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8403  mov     rcx, qword ptr [rbp+var_40]
0x1801d8407  lea     r8, [rbp+string]
0x1801d840b  mov     r9, rax
0x1801d840e  mov     rdx, [rcx]
0x1801d8411  mov     rax, [rdx+58h]
0x1801d8415  mov     rdx, [r9+18h]
0x1801d8419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d841e  mov     ebx, eax
0x1801d8420  test    eax, eax
0x1801d8422  js      loc_1801D84BA
0x1801d8428  mov     rcx, [rbp+var_48]
0x1801d842c  cvttsd2si rdx, [rbp+string]
0x1801d8432  mov     rax, [rcx]
0x1801d8435  mov     rax, [rax+88h]
0x1801d843c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8441  mov     ebx, eax
0x1801d8443  test    eax, eax
0x1801d8445  js      short loc_1801D84BA
0x1801d8447  xor     ecx, ecx; string
0x1801d8449  mov     [rbp+string], rsi
0x1801d844d  call    cs:__imp_WindowsDeleteString
0x1801d8453  lea     rdx, off_1803E18A8; "Description"
0x1801d845a  mov     [rbp+string], rsi
0x1801d845e  lea     rcx, [rbp+hstringHeader]
0x1801d8462  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d8467  mov     rcx, qword ptr [rbp+var_40]
0x1801d846b  lea     r8, [rbp+string]
0x1801d846f  mov     r9, rax
0x1801d8472  mov     rdx, [rcx]
0x1801d8475  mov     rax, [rdx+50h]
0x1801d8479  mov     rdx, [r9+18h]
0x1801d847d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8482  mov     ebx, eax
0x1801d8484  test    eax, eax
0x1801d8486  js      short loc_1801D84A1
0x1801d8488  mov     rcx, [rbp+var_48]
0x1801d848c  mov     rdx, [rbp+string]
0x1801d8490  mov     rax, [rcx]
0x1801d8493  mov     rax, [rax+98h]
0x1801d849a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d849f  mov     ebx, eax
0x1801d84a1  mov     rcx, [rbp+string]; string
0x1801d84a5  call    cs:__imp_WindowsDeleteString
0x1801d84ab  test    ebx, ebx
0x1801d84ad  js      short loc_1801D84BA
0x1801d84af  mov     rax, [rbp+var_48]
0x1801d84b3  mov     [rdi], rax
0x1801d84b6  mov     [rbp+var_48], rsi
0x1801d84ba  lea     rcx, [rbp+var_48]
0x1801d84be  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d84c3  lea     rcx, [rbp+var_40]; this
0x1801d84c7  call    ??1JsonDeserializer@Internal@Contacts@ApplicationModel@Windows@@QEAA@XZ; Windows::ApplicationModel::Contacts::Internal::JsonDeserializer::~JsonDeserializer(void)
0x1801d84cc  mov     eax, ebx
0x1801d84ce  mov     rcx, [rbp+var_10]
0x1801d84d2  xor     rcx, rsp; StackCookie
0x1801d84d5  call    __security_check_cookie
0x1801d84da  mov     rbx, [rsp+70h+arg_10]
0x1801d84e2  add     rsp, 70h
0x1801d84e6  pop     rdi
0x1801d84e7  pop     rsi
0x1801d84e8  pop     rbp
0x1801d84e9  retn
```
