# Windows::Internal::Feedback::InternalFeedbackBroker::GetFeedbackItemFromExePath(ushort const *,ushort const *,Windows::Internal::Feedback::IFeedbackItem * *)

- ea: `0x18003e6f8`
- end: `0x18003ea4d`
- name: `?GetFeedbackItemFromExePath@InternalFeedbackBroker@Feedback@Internal@Windows@@AEAAJPEBG0PEAPEAUIFeedbackItem@234@@Z`
- size: `853`
- prototype: `int(Windows::Internal::Feedback::InternalFeedbackBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Internal::Feedback::IFeedbackItem **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180227d10`

## callees

- `0x180008acc`
- `0x18003c5e4`
- `0x18003c65c`
- `0x18003dbb0`
- `0x18003e38c`
- `0x18003e6f8`
- `0x1800e9c10`
- `0x18013d354`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e85c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e8dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e85c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e8dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e873`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e8b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e8f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e873`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e8b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e8f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e926`
- `AEPIC!PicFreeFileInfo` at `0x18003e963`
- `AEPIC!PicFreeFileInfo` at `0x18003e963`
- `AEPIC!PicRetrieveFileInfo` at `0x18003e75d`
- `AEPIC!PicRetrieveFileInfo` at `0x18003e75d`

## string_xrefs

- `0x18003ea21`: `shell\twinui\feedback\lib\feedbackbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Feedback::InternalFeedbackBroker::GetFeedbackItemFromExePath(
        Windows::Internal::Feedback::InternalFeedbackBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct Windows::Internal::Feedback::IFeedbackItem **a4)
{
  int HasPackageQueryCapability; // ebx
  PCNZWCH *v8; // rsi
  struct Windows::Internal::Feedback::IFeedbackItem *v9; // rcx
  char *v10; // rax
  char *v11; // rdi
  _QWORD *v12; // rbx
  HSTRING *v13; // r13
  HSTRING *v14; // r12
  const WCHAR *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rbx
  HRESULT String; // eax
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rdx
  struct Windows::Internal::Feedback::IFeedbackItem *v22; // rcx
  struct Windows::Internal::Feedback::IFeedbackItem *v24; // rcx
  __int64 v25; // rdx
  PCNZWCH *v26; // [rsp+20h] [rbp-38h] BYREF
  PCNZWCH v27; // [rsp+28h] [rbp-30h]
  PCNZWCH v28; // [rsp+30h] [rbp-28h]
  PCNZWCH sourceString; // [rsp+38h] [rbp-20h]
  __int64 v30[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  struct Windows::Internal::Feedback::IFeedbackItem *v32; // [rsp+A0h] [rbp+48h] BYREF

  v26 = 0;
  v32 = 0;
  HasPackageQueryCapability = Windows::Internal::Feedback::HasPackageQueryCapability(this);
  if ( HasPackageQueryCapability >= 0 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( a4 )
        {
          *a4 = 0;
          HasPackageQueryCapability = PicRetrieveFileInfo(a2, 16400, &v26);
          if ( HasPackageQueryCapability < 0 )
            goto LABEL_41;
          v8 = v26;
          v9 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(struct Windows::Internal::Feedback::IFeedbackItem *))(*(_QWORD *)v9 + 16LL))(v9);
          }
          v32 = 0;
          v10 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
          v11 = v10;
          if ( v10 )
          {
            v12 = v10 + 16;
            Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v10 + 16));
            *((_QWORD *)v11 + 7) = 1;
            *(_QWORD *)v11 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable';
            *((_QWORD *)v11 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
            *v12 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
            if ( Microsoft::WRL::Details::ModuleBase::module_ )
              (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                   + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
            *(_QWORD *)v11 = &Windows::Internal::Feedback::InternalFeedbackItem::`vftable';
            *((_QWORD *)v11 + 1) = &Windows::Internal::Feedback::InternalFeedbackItem::`vftable'{for `IWeakReferenceSource'};
            *v12 = &Windows::Internal::Feedback::InternalFeedbackItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
            *((_QWORD *)v11 + 8) = 0;
            v13 = (HSTRING *)(v11 + 72);
            *((_QWORD *)v11 + 9) = 0;
            *((_QWORD *)v11 + 10) = 0;
            v14 = (HSTRING *)(v11 + 88);
            *((_QWORD *)v11 + 11) = 0;
            v30[0] = 0;
            v28 = *v8;
            v27 = v8[1];
            v15 = v8[2];
            sourceString = v15;
            v16 = -1;
            v17 = -1;
            do
              ++v17;
            while ( v15[v17] );
            WindowsDeleteString(0);
            *((_QWORD *)v11 + 8) = 0;
            String = WindowsCreateString(sourceString, v17, (HSTRING *)v11 + 8);
            HasPackageQueryCapability = String;
            if ( String < 0 )
            {
              v21 = 24;
              goto LABEL_23;
            }
            v19 = -1;
            do
              ++v19;
            while ( v27[v19] );
            WindowsDeleteString(*v13);
            *v13 = 0;
            String = WindowsCreateString(v27, v19, (HSTRING *)v11 + 9);
            HasPackageQueryCapability = String;
            if ( String < 0 )
            {
              v21 = 25;
              goto LABEL_23;
            }
            v20 = -1;
            do
              ++v20;
            while ( v28[v20] );
            WindowsDeleteString(*((HSTRING *)v11 + 10));
            *((_QWORD *)v11 + 10) = 0;
            String = WindowsCreateString(v28, v20, (HSTRING *)v11 + 10);
            HasPackageQueryCapability = String;
            if ( String < 0 )
            {
              v21 = 26;
              goto LABEL_23;
            }
            do
              ++v16;
            while ( a3[v16] );
            WindowsDeleteString(*v14);
            *v14 = 0;
            String = WindowsCreateString(a3, v16, (HSTRING *)v11 + 11);
            HasPackageQueryCapability = String;
            if ( String < 0 )
            {
              v21 = 27;
LABEL_23:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v21,
                (unsigned int)"shell\\twinui\\feedback\\lib\\internalfeedbackhubapp.cpp",
                (const char *)(unsigned int)String,
                (int)v26);
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(v11);
              Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(v30);
              goto LABEL_24;
            }
            v32 = (struct Windows::Internal::Feedback::IFeedbackItem *)v11;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(v11);
            HasPackageQueryCapability = 0;
          }
          else
          {
            HasPackageQueryCapability = -2147024882;
          }
LABEL_24:
          PicFreeFileInfo(v26);
          if ( HasPackageQueryCapability >= 0 )
          {
            v22 = 0;
            *a4 = v32;
            goto LABEL_26;
          }
LABEL_41:
          v22 = v32;
LABEL_26:
          if ( v22 )
          {
            v32 = 0;
            (*(void (__fastcall **)(struct Windows::Internal::Feedback::IFeedbackItem *))(*(_QWORD *)v22 + 16LL))(v22);
          }
          return (unsigned int)HasPackageQueryCapability;
        }
        v25 = 238;
      }
      else
      {
        v25 = 237;
      }
    }
    else
    {
      v25 = 236;
    }
    HasPackageQueryCapability = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)0x80070057LL,
      (int)v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    return (unsigned int)HasPackageQueryCapability;
  }
  v24 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::Feedback::IFeedbackItem *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return (unsigned int)HasPackageQueryCapability;
}

```

## disassembly

```asm
0x18003e6f8  mov     [rsp-40h+arg_0], rcx
0x18003e6fd  push    rbp
0x18003e6fe  push    rbx
0x18003e6ff  push    rsi
0x18003e700  push    rdi
0x18003e701  push    r12
0x18003e703  push    r13
0x18003e705  push    r14
0x18003e707  push    r15
0x18003e709  mov     rbp, rsp
0x18003e70c  sub     rsp, 58h
0x18003e710  mov     r15, r9
0x18003e713  mov     r14, r8
0x18003e716  mov     rdi, rdx
0x18003e719  xor     r13d, r13d
0x18003e71c  mov     [rbp+var_38], r13
0x18003e720  mov     [rbp+arg_0], r13
0x18003e724  call    ?HasPackageQueryCapability@Feedback@Internal@Windows@@YAJXZ; Windows::Internal::Feedback::HasPackageQueryCapability(void)
0x18003e729  mov     ebx, eax
0x18003e72b  test    eax, eax
0x18003e72d  js      loc_18003E9BF
0x18003e733  test    rdi, rdi
0x18003e736  jz      loc_18003EA09
0x18003e73c  test    r14, r14
0x18003e73f  jz      loc_18003EA3C
0x18003e745  test    r15, r15
0x18003e748  jz      loc_18003EA10
0x18003e74e  mov     [r15], r13
0x18003e751  lea     r8, [rbp+var_38]
0x18003e755  mov     edx, 4010h
0x18003e75a  mov     rcx, rdi
0x18003e75d  call    cs:__imp_PicRetrieveFileInfo
0x18003e763  mov     ebx, eax
0x18003e765  test    eax, eax
0x18003e767  js      loc_18003EA43
0x18003e76d  mov     rsi, [rbp+var_38]
0x18003e771  mov     rcx, [rbp+arg_0]
0x18003e775  test    rcx, rcx
0x18003e778  jz      short loc_18003E78B
0x18003e77a  mov     [rbp+arg_0], r13
0x18003e77e  mov     rax, [rcx]
0x18003e781  mov     rax, [rax+10h]
0x18003e785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e78a  nop
0x18003e78b  mov     [rbp+arg_0], r13
0x18003e78f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e796  mov     ecx, 60h ; '`'; unsigned __int64
0x18003e79b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e7a0  mov     rdi, rax
0x18003e7a3  test    rax, rax
0x18003e7a6  jz      loc_18003E9FF
0x18003e7ac  lea     rbx, [rax+10h]
0x18003e7b0  mov     rcx, rbx; this
0x18003e7b3  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18003e7b8  mov     qword ptr [rdi+38h], 1
0x18003e7c0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'
0x18003e7c7  mov     [rdi], rax
0x18003e7ca  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18003e7d1  mov     [rdi+8], rax
0x18003e7d5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003e7dc  mov     [rbx], rax
0x18003e7df  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003e7e6  test    rcx, rcx
0x18003e7e9  jz      short loc_18003E7F8
0x18003e7eb  mov     rax, [rcx]
0x18003e7ee  mov     rax, [rax+8]
0x18003e7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7f7  nop
0x18003e7f8  lea     rax, ??_7InternalFeedbackItem@Feedback@Internal@Windows@@6B@; const Windows::Internal::Feedback::InternalFeedbackItem::`vftable'
0x18003e7ff  mov     [rdi], rax
0x18003e802  lea     rax, ??_7InternalFeedbackItem@Feedback@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::Feedback::InternalFeedbackItem::`vftable'{for `IWeakReferenceSource'}
0x18003e809  mov     [rdi+8], rax
0x18003e80d  lea     rax, ??_7InternalFeedbackItem@Feedback@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::Feedback::InternalFeedbackItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003e814  mov     [rbx], rax
0x18003e817  mov     [rdi+40h], r13
0x18003e81b  lea     r13, [rdi+48h]
0x18003e81f  xor     ecx, ecx; string
0x18003e821  mov     [r13+0], rcx
0x18003e825  mov     [rdi+50h], rcx
0x18003e829  lea     r12, [rdi+58h]
0x18003e82d  mov     [r12], rcx
0x18003e831  mov     [rbp+var_18], rcx
0x18003e835  mov     rax, [rsi]
0x18003e838  mov     [rbp+var_28], rax
0x18003e83c  mov     rax, [rsi+8]
0x18003e840  mov     [rbp+var_30], rax
0x18003e844  mov     rax, [rsi+10h]
0x18003e848  mov     [rbp+sourceString], rax
0x18003e84c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003e850  mov     rbx, rsi
0x18003e853  inc     rbx
0x18003e856  cmp     [rax+rbx*2], cx
0x18003e85a  jnz     short loc_18003E853
0x18003e85c  call    cs:__imp_WindowsDeleteString
0x18003e862  lea     r8, [rdi+40h]; string
0x18003e866  mov     qword ptr [r8], 0
0x18003e86d  mov     edx, ebx; length
0x18003e86f  mov     rcx, [rbp+sourceString]; sourceString
0x18003e873  call    cs:__imp_WindowsCreateString
0x18003e879  mov     ebx, eax
0x18003e87b  xor     ecx, ecx
0x18003e87d  test    eax, eax
0x18003e87f  js      loc_18003E9AB
0x18003e885  mov     rbx, rsi
0x18003e888  mov     rax, [rbp+var_30]
0x18003e88c  inc     rbx
0x18003e88f  cmp     [rax+rbx*2], cx
0x18003e893  jnz     short loc_18003E88C
0x18003e895  mov     rcx, [r13+0]; string
0x18003e899  call    cs:__imp_WindowsDeleteString
0x18003e89f  mov     qword ptr [r13+0], 0
0x18003e8a7  mov     r8, r13; string
0x18003e8aa  mov     edx, ebx; length
0x18003e8ac  mov     rcx, [rbp+var_30]; sourceString
0x18003e8b0  call    cs:__imp_WindowsCreateString
0x18003e8b6  mov     ebx, eax
0x18003e8b8  xor     r13d, r13d
0x18003e8bb  test    eax, eax
0x18003e8bd  js      loc_18003E9A4
0x18003e8c3  mov     rbx, rsi
0x18003e8c6  mov     rax, [rbp+var_28]
0x18003e8ca  inc     rbx
0x18003e8cd  cmp     [rax+rbx*2], r13w
0x18003e8d2  jnz     short loc_18003E8CA
0x18003e8d4  lea     r13, [rdi+50h]
0x18003e8d8  mov     rcx, [r13+0]; string
0x18003e8dc  call    cs:__imp_WindowsDeleteString
0x18003e8e2  mov     qword ptr [r13+0], 0
0x18003e8ea  mov     r8, r13; string
0x18003e8ed  mov     edx, ebx; length
0x18003e8ef  mov     rcx, [rbp+var_28]; sourceString
0x18003e8f3  call    cs:__imp_WindowsCreateString
0x18003e8f9  mov     ebx, eax
0x18003e8fb  xor     r13d, r13d
0x18003e8fe  test    eax, eax
0x18003e900  js      loc_18003E9B5
0x18003e906  inc     rsi
0x18003e909  cmp     [r14+rsi*2], r13w
0x18003e90e  jnz     short loc_18003E906
0x18003e910  mov     rcx, [r12]; string
0x18003e914  call    cs:__imp_WindowsDeleteString
0x18003e91a  mov     [r12], r13
0x18003e91e  mov     r8, r12; string
0x18003e921  mov     edx, esi; length
0x18003e923  mov     rcx, r14; sourceString
0x18003e926  call    cs:__imp_WindowsCreateString
0x18003e92c  mov     ebx, eax
0x18003e92e  test    eax, eax
0x18003e930  jns     loc_18003E9DB
0x18003e936  mov     edx, 1Bh; void *
0x18003e93b  mov     r9d, eax; char *
0x18003e93e  lea     r8, aShellTwinuiFee_0; "shell\\twinui\\feedback\\lib\\internalf"...
0x18003e945  mov     rcx, [rbp+40h]; this
0x18003e949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e94e  mov     rcx, rdi
0x18003e951  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(void)
0x18003e956  lea     rcx, [rbp+var_18]
0x18003e95a  call    ??1?$MakeAllocator@VSttExperienceManagerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(void)
0x18003e95f  mov     rcx, [rbp+var_38]
0x18003e963  call    cs:__imp_PicFreeFileInfo
0x18003e969  test    ebx, ebx
0x18003e96b  js      loc_18003EA43
0x18003e971  mov     rax, [rbp+arg_0]
0x18003e975  mov     rcx, r13
0x18003e978  mov     [r15], rax
0x18003e97b  test    rcx, rcx
0x18003e97e  jz      short loc_18003E991
0x18003e980  mov     [rbp+arg_0], r13
0x18003e984  mov     rax, [rcx]
0x18003e987  mov     rax, [rax+10h]
0x18003e98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e990  nop
0x18003e991  mov     eax, ebx
0x18003e993  add     rsp, 58h
0x18003e997  pop     r15
0x18003e999  pop     r14
0x18003e99b  pop     r13
0x18003e99d  pop     r12
0x18003e99f  pop     rdi
0x18003e9a0  pop     rsi
0x18003e9a1  pop     rbx
0x18003e9a2  pop     rbp
0x18003e9a3  retn
0x18003e9a4  mov     edx, 19h
0x18003e9a9  jmp     short loc_18003E93B
0x18003e9ab  mov     edx, 18h
0x18003e9b0  xor     r13d, r13d
0x18003e9b3  jmp     short loc_18003E93B
0x18003e9b5  mov     edx, 1Ah
0x18003e9ba  jmp     loc_18003E93B
0x18003e9bf  mov     rcx, [rbp+arg_0]
0x18003e9c3  test    rcx, rcx
0x18003e9c6  jz      short loc_18003E9D9
0x18003e9c8  mov     [rbp+arg_0], r13
0x18003e9cc  mov     rdx, [rcx]
0x18003e9cf  mov     rax, [rdx+10h]
0x18003e9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9d8  nop
0x18003e9d9  jmp     short loc_18003E991
0x18003e9db  mov     [rbp+arg_0], rdi
0x18003e9df  mov     rax, [rdi]
0x18003e9e2  mov     rcx, rdi
0x18003e9e5  mov     rax, [rax+8]
0x18003e9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9ee  nop
0x18003e9ef  mov     rcx, rdi
0x18003e9f2  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(void)
0x18003e9f7  mov     ebx, r13d
0x18003e9fa  jmp     loc_18003E95F
0x18003e9ff  mov     ebx, 8007000Eh
0x18003ea04  jmp     loc_18003E95F
0x18003ea09  mov     edx, 0ECh
0x18003ea0e  jmp     short loc_18003EA15
0x18003ea10  mov     edx, 0EEh; void *
0x18003ea15  mov     ebx, 80070057h
0x18003ea1a  mov     rcx, [rbp+40h]; this
0x18003ea1e  mov     r9d, ebx; char *
0x18003ea21  lea     r8, aShellTwinuiFee; "shell\\twinui\\feedback\\lib\\feedbackb"...
0x18003ea28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ea2d  nop
0x18003ea2e  lea     rcx, [rbp+arg_0]
0x18003ea32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ea37  jmp     loc_18003E991
0x18003ea3c  mov     edx, 0EDh
0x18003ea41  jmp     short loc_18003EA15
0x18003ea43  mov     rcx, [rbp+arg_0]
0x18003ea47  jmp     loc_18003E97B
```
