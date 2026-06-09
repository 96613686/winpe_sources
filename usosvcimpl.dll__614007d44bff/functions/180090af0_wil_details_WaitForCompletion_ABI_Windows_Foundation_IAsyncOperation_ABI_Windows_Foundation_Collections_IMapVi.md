# wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180090af0`
- end: `0x180090d8f`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `671`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008dc80`
- `0x18008e3a0`

## callees

- `0x1800081c0`
- `0x180008e64`
- `0x18002e0d0`
- `0x180038998`
- `0x180090af0`
- `0x1800dd930`
- `0x1800de0fc`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180090c9c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180090c9c`

## string_xrefs

- `0x180090bce`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x180090bf7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x180090c4f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`
- `0x180090caf`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(
        __int64 a1)
{
  char *v2; // rbx
  unsigned int v3; // edi
  wil::details *v4; // rcx
  int LastErrorFailHr; // eax
  int v7; // eax
  HRESULT v8; // eax
  __int64 v9; // rcx
  int lpdwindex; // [rsp+20h] [rbp-40h]
  int lpdwindexa; // [rsp+20h] [rbp-40h]
  int v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+40h] [rbp-20h] BYREF
  HANDLE pHandles; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v2 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
  {
    v3 = -2147024882;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x646,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v3,
      lpdwindex);
    return v3;
  }
  *(_QWORD *)v2 = &ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v2 + 8);
  *((_DWORD *)v2 + 11) = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>'};
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v2 = `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v2 + 12) = 0;
  *((_QWORD *)v2 + 7) = 0;
  if ( !(unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                           v2 + 56,
                           0,
                           0,
                           0) )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
    v3 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x629,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      goto LABEL_8;
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  v7 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 48LL))(a1, v2);
  v3 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x647,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v7,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return v3;
  }
  pHandles = (HANDLE)*((_QWORD *)v2 + 7);
  dwindex = 0;
  v8 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v3 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x653,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v8,
      lpdwindexa);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return v3;
  }
  if ( *((_DWORD *)v2 + 12) != 1 )
  {
    v13 = 0;
    v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
           a1,
           &GUID_00000036_0000_0000_c000_000000000046,
           &v13);
    if ( (v3 & 0x80000000) == 0 )
    {
      v12 = -2147418113;
      v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 64LL))(v13, &v12);
      if ( (v3 & 0x80000000) == 0 )
        v3 = v12;
    }
    v9 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    return v3;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x180090af0  mov     [rsp-8+arg_8], rbx
0x180090af5  mov     [rsp-8+arg_10], rsi
0x180090afa  mov     [rsp-8+arg_18], rdi
0x180090aff  push    rbp
0x180090b00  mov     rbp, rsp
0x180090b03  sub     rsp, 60h
0x180090b07  mov     rax, cs:__security_cookie
0x180090b0e  xor     rax, rsp
0x180090b11  mov     [rbp+var_10], rax
0x180090b15  mov     rsi, rcx
0x180090b18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180090b1f  mov     ecx, 40h ; '@'; unsigned __int64
0x180090b24  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180090b29  mov     rbx, rax
0x180090b2c  test    rax, rax
0x180090b2f  jnz     short loc_180090B3B
0x180090b31  mov     edi, 8007000Eh
0x180090b36  jmp     loc_180090BF0
0x180090b3b  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@6B@; const ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>::`vftable'
0x180090b42  mov     [rbx], rax
0x180090b45  lea     rdi, [rbx+8]
0x180090b49  mov     rcx, rdi
0x180090b4c  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180090b51  mov     dword ptr [rbx+2Ch], 1
0x180090b58  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>'}
0x180090b5f  mov     [rbx], rax
0x180090b62  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180090b69  mov     [rdi], rax
0x180090b6c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180090b73  test    rcx, rcx
0x180090b76  jz      short loc_180090B85
0x180090b78  mov     rax, [rcx]
0x180090b7b  mov     rax, [rax+8]
0x180090b7f  call    _guard_dispatch_icall
0x180090b84  nop
0x180090b85  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@456@@; const `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>'}
0x180090b8c  mov     [rbx], rax
0x180090b8f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180090b96  mov     [rdi], rax
0x180090b99  mov     dword ptr [rbx+30h], 0
0x180090ba0  lea     rcx, [rbx+38h]
0x180090ba4  mov     qword ptr [rcx], 0
0x180090bab  xor     r9d, r9d
0x180090bae  xor     r8d, r8d
0x180090bb1  xor     edx, edx
0x180090bb3  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180090bb8  test    al, al
0x180090bba  jnz     short loc_180090C10
0x180090bbc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180090bc1  mov     edi, eax
0x180090bc3  test    eax, eax
0x180090bc5  jns     short loc_180090C10
0x180090bc7  mov     rcx, [rbp+8]; this
0x180090bcb  mov     r9d, eax; char *
0x180090bce  lea     r8, aCW1SPackagesMi_5; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180090bd5  mov     edx, 629h; void *
0x180090bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090bdf  nop
0x180090be0  mov     rax, [rbx]
0x180090be3  mov     rcx, rbx
0x180090be6  mov     rax, [rax+10h]
0x180090bea  call    _guard_dispatch_icall
0x180090bef  nop
0x180090bf0  mov     rcx, [rbp+8]; this
0x180090bf4  mov     r9d, edi; char *
0x180090bf7  lea     r8, aCW1SPackagesMi_5; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180090bfe  mov     edx, 646h; void *
0x180090c03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090c08  nop
0x180090c09  mov     eax, edi
0x180090c0b  jmp     loc_180090D6D
0x180090c10  mov     rax, [rbx]
0x180090c13  mov     rcx, rbx
0x180090c16  mov     rax, [rax+8]
0x180090c1a  call    _guard_dispatch_icall
0x180090c1f  nop
0x180090c20  mov     rax, [rbx]
0x180090c23  mov     rcx, rbx
0x180090c26  mov     rax, [rax+10h]
0x180090c2a  call    _guard_dispatch_icall
0x180090c2f  nop
0x180090c30  mov     rax, [rsi]
0x180090c33  mov     rdx, rbx
0x180090c36  mov     rcx, rsi
0x180090c39  mov     rax, [rax+30h]
0x180090c3d  call    _guard_dispatch_icall
0x180090c42  mov     edi, eax
0x180090c44  test    eax, eax
0x180090c46  jns     short loc_180090C73
0x180090c48  mov     rcx, [rbp+8]; this
0x180090c4c  mov     r9d, eax; char *
0x180090c4f  lea     r8, aCW1SPackagesMi_5; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180090c56  mov     edx, 647h; void *
0x180090c5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090c60  nop
0x180090c61  mov     rcx, [rbx]
0x180090c64  mov     rax, [rcx+10h]
0x180090c68  mov     rcx, rbx
0x180090c6b  call    _guard_dispatch_icall
0x180090c70  nop
0x180090c71  jmp     short loc_180090C09
0x180090c73  mov     rax, [rbx+38h]
0x180090c77  mov     [rbp+pHandles], rax
0x180090c7b  mov     [rbp+dwindex], 0
0x180090c82  lea     rax, [rbp+dwindex]
0x180090c86  mov     qword ptr [rsp+60h+lpdwindex], rax; int
0x180090c8b  lea     r9, [rbp+pHandles]; pHandles
0x180090c8f  mov     r8d, 1; cHandles
0x180090c95  or      edx, 0FFFFFFFFh; dwTimeout
0x180090c98  lea     ecx, [r8+7]; dwFlags
0x180090c9c  call    cs:__imp_CoWaitForMultipleHandles
0x180090ca2  mov     edi, eax
0x180090ca4  test    eax, eax
0x180090ca6  jns     short loc_180090CD6
0x180090ca8  mov     rcx, [rbp+8]; this
0x180090cac  mov     r9d, eax; char *
0x180090caf  lea     r8, aCW1SPackagesMi_5; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180090cb6  mov     edx, 653h; void *
0x180090cbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090cc0  nop
0x180090cc1  mov     rcx, [rbx]
0x180090cc4  mov     rax, [rcx+10h]
0x180090cc8  mov     rcx, rbx
0x180090ccb  call    _guard_dispatch_icall
0x180090cd0  nop
0x180090cd1  jmp     loc_180090C09
0x180090cd6  mov     eax, [rbx+30h]
0x180090cd9  cmp     eax, 1
0x180090cdc  jz      short loc_180090D5B
0x180090cde  mov     [rbp+var_28], 0
0x180090ce6  mov     rax, [rsi]
0x180090ce9  lea     r8, [rbp+var_28]
0x180090ced  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180090cf4  mov     rcx, rsi
0x180090cf7  mov     rax, [rax]
0x180090cfa  call    _guard_dispatch_icall
0x180090cff  mov     edi, eax
0x180090d01  test    eax, eax
0x180090d03  js      short loc_180090D28
0x180090d05  mov     [rbp+var_30], 8000FFFFh
0x180090d0c  mov     rcx, [rbp+var_28]
0x180090d10  mov     rax, [rcx]
0x180090d13  lea     rdx, [rbp+var_30]
0x180090d17  mov     rax, [rax+40h]
0x180090d1b  call    _guard_dispatch_icall
0x180090d20  mov     edi, eax
0x180090d22  test    eax, eax
0x180090d24  cmovns  edi, [rbp+var_30]
0x180090d28  mov     rcx, [rbp+var_28]
0x180090d2c  test    rcx, rcx
0x180090d2f  jz      short loc_180090D46
0x180090d31  mov     [rbp+var_28], 0
0x180090d39  mov     rax, [rcx]
0x180090d3c  mov     rax, [rax+10h]
0x180090d40  call    _guard_dispatch_icall
0x180090d45  nop
0x180090d46  mov     rax, [rbx]
0x180090d49  mov     rcx, rbx
0x180090d4c  mov     rax, [rax+10h]
0x180090d50  call    _guard_dispatch_icall
0x180090d55  nop
0x180090d56  jmp     loc_180090C09
0x180090d5b  mov     rax, [rbx]
0x180090d5e  mov     rcx, rbx
0x180090d61  mov     rax, [rax+10h]
0x180090d65  call    _guard_dispatch_icall
0x180090d6a  nop
0x180090d6b  xor     eax, eax
0x180090d6d  mov     rcx, [rbp+var_10]
0x180090d71  xor     rcx, rsp; StackCookie
0x180090d74  call    __security_check_cookie
0x180090d79  lea     r11, [rsp+60h+var_s0]
0x180090d7e  mov     rbx, [r11+18h]
0x180090d82  mov     rsi, [r11+20h]
0x180090d86  mov     rdi, [r11+28h]
0x180090d8a  mov     rsp, r11
0x180090d8d  pop     rbp
0x180090d8e  retn
```
