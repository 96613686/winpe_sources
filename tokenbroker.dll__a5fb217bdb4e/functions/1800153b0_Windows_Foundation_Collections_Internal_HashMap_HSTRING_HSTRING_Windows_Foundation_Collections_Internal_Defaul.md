# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Iterator::get_Current(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> * *)

- ea: `0x1800153b0`
- end: `0x18001564f`
- name: `?get_Current@Iterator@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@456@@Z`
- size: `671`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007350`
- `0x1800153b0`
- `0x180015658`
- `0x180015680`
- `0x180015700`
- `0x18003d38c`
- `0x18008e710`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800153e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800153e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015566`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800154e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800154e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015617`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001558b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001558b`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180015456`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180015456`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Iterator::get_Current(
        _QWORD *a1,
        char **a2)
{
  __int64 v4; // rbx
  HSTRING *v5; // r15
  char *v6; // rax
  char *v7; // rdi
  __int64 v8; // rcx
  HRESULT v9; // ebp
  HSTRING v10; // rcx
  HSTRING v11; // rcx
  signed __int64 v13; // rax
  unsigned int v14; // ecx
  signed __int64 v15; // rtt
  int v16; // eax
  HSTRING newString; // [rsp+60h] [rbp+8h] BYREF
  LPUNKNOWN ppunkMarshal; // [rsp+68h] [rbp+10h] BYREF
  HSTRING v19; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  v4 = a1[8] + 160LL;
  if ( *(_DWORD *)v4 == 1 )
  {
    v16 = *(_DWORD *)(a1[8] + 168LL);
    if ( v16 >= 0 )
      *(_DWORD *)(a1[8] + 168LL) = v16 + 1;
  }
  else
  {
    AcquireSRWLockShared((PSRWLOCK)(a1[8] + 168LL));
  }
  if ( *(_QWORD *)(a1[8] + 176LL) != a1[10] )
  {
    v9 = -2147483636;
LABEL_21:
    RoOriginateError((unsigned int)v9, 0);
    goto LABEL_15;
  }
  v5 = (HSTRING *)a1[9];
  if ( !v5 )
  {
    v9 = -2147483637;
    goto LABEL_21;
  }
  v6 = (char *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>::IKeyValuePair<HSTRING__ *,HSTRING__ *>(v6);
    *(_QWORD *)(v8 + 16) = &CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *(_QWORD *)(v8 + 40) = 0;
    ppunkMarshal = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
    if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
      Microsoft::WRL::ComPtr<IUnknown>::As<IMarshal>(&ppunkMarshal, v7 + 40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppunkMarshal);
    *((_QWORD *)v7 + 7) = 1;
    *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable';
    *((_QWORD *)v7 + 1) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
    *((_QWORD *)v7 + 2) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v7 = &Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1>::`vftable';
    *((_QWORD *)v7 + 1) = &Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1>::`vftable'{for `IWeakReferenceSource'};
    *((_QWORD *)v7 + 2) = &Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_QWORD *)v7 + 8) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v9 = WindowsDuplicateString(*v5, &newString);
    if ( v9 < 0 )
    {
      newString = 0;
      WindowsDeleteString(0);
LABEL_14:
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>,Microsoft::WRL::FtmBase>::Release(v7);
      goto LABEL_15;
    }
    v9 = WindowsDuplicateString(v5[1], &v19);
    if ( v9 < 0 )
    {
      v11 = 0;
    }
    else
    {
      v10 = (HSTRING)*((_QWORD *)v7 + 8);
      *((_QWORD *)v7 + 8) = newString;
      newString = v10;
      v11 = (HSTRING)*((_QWORD *)v7 + 9);
      *((_QWORD *)v7 + 9) = v19;
    }
    v19 = v11;
    WindowsDeleteString(v11);
    WindowsDeleteString(newString);
    newString = 0;
    if ( v9 < 0 )
      goto LABEL_14;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
    *a2 = v7;
    v13 = *((_QWORD *)v7 + 7);
    while ( v13 >= 0 )
    {
      if ( (_DWORD)v13 == 0x7FFFFFFF )
        goto LABEL_15;
      v14 = v13 - 1;
      v15 = v13;
      v13 = _InterlockedCompareExchange64((volatile signed __int64 *)v7 + 7, v13 - 1, v13);
      if ( v15 == v13 )
        goto LABEL_26;
    }
    v14 = Microsoft::WRL::Details::StrongReference::DecrementStrongReference((Microsoft::WRL::Details::StrongReference *)(2 * v13 + 16));
LABEL_26:
    if ( !v14 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 64LL))(v7, 1);
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
    }
  }
  else
  {
    v9 = -2147024882;
  }
LABEL_15:
  if ( v4 )
  {
    if ( *(_DWORD *)v4 == 1 )
      --*(_DWORD *)(v4 + 8);
    else
      ReleaseSRWLockShared((PSRWLOCK)(v4 + 8));
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800153b0  push    rbx
0x1800153b2  push    rbp
0x1800153b3  push    rsi
0x1800153b4  push    rdi
0x1800153b5  push    r12
0x1800153b7  push    r14
0x1800153b9  push    r15
0x1800153bb  sub     rsp, 20h
0x1800153bf  mov     r14, rdx
0x1800153c2  mov     rdi, rcx
0x1800153c5  xor     r12d, r12d
0x1800153c8  mov     [rdx], r12
0x1800153cb  mov     rbx, [rcx+40h]
0x1800153cf  add     rbx, 0A0h
0x1800153d6  cmp     dword ptr [rbx], 1
0x1800153d9  jz      loc_1800155FA
0x1800153df  lea     rcx, [rbx+8]; SRWLock
0x1800153e3  call    cs:__imp_AcquireSRWLockShared
0x1800153e9  mov     rcx, [rdi+40h]
0x1800153ed  mov     rax, [rdi+50h]
0x1800153f1  cmp     [rcx+0B0h], rax
0x1800153f8  jnz     loc_180015582
0x1800153fe  mov     r15, [rdi+48h]
0x180015402  test    r15, r15
0x180015405  jz      loc_18001563B
0x18001540b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015412  mov     ecx, 50h ; 'P'; unsigned __int64
0x180015417  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001541c  mov     rdi, rax
0x18001541f  test    rax, rax
0x180015422  jz      loc_180015645
0x180015428  mov     rcx, rax
0x18001542b  call    ??0?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>::IKeyValuePair<HSTRING__ *,HSTRING__ *>(void)
0x180015430  nop
0x180015431  lea     rax, ??_7CActivatedEventArgsBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180015438  mov     [rcx+10h], rax
0x18001543c  mov     [rcx+28h], r12
0x180015440  mov     [rsp+58h+ppunkMarshal], r12
0x180015445  lea     rcx, [rsp+58h+ppunkMarshal]
0x18001544a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001544f  lea     rdx, [rsp+58h+ppunkMarshal]; ppunkMarshal
0x180015454  xor     ecx, ecx; punkOuter
0x180015456  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001545c  test    eax, eax
0x18001545e  js      short loc_18001546E
0x180015460  lea     rdx, [rdi+28h]
0x180015464  lea     rcx, [rsp+58h+ppunkMarshal]
0x180015469  call    ??$As@UIMarshal@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMarshal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUnknown>::As<IMarshal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMarshal>>)
0x18001546e  lea     rcx, [rsp+58h+ppunkMarshal]
0x180015473  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015478  nop
0x180015479  mov     qword ptr [rdi+38h], 1
0x180015481  lea     rax, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'
0x180015488  mov     [rdi], rax
0x18001548b  lea     rax, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x180015492  mov     [rdi+8], rax
0x180015496  lea     rax, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001549d  mov     [rdi+10h], rax
0x1800154a1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800154a8  test    rcx, rcx
0x1800154ab  jz      short loc_1800154B9
0x1800154ad  mov     rax, [rcx]
0x1800154b0  mov     rax, [rax+8]
0x1800154b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b9  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$00@Internal@Collections@Foundation@Windows@@6B@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1>::`vftable'
0x1800154c0  mov     [rdi], rax
0x1800154c3  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$00@Internal@Collections@Foundation@Windows@@6BIWeakReferenceSource@@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1>::`vftable'{for `IWeakReferenceSource'}
0x1800154ca  mov     [rdi+8], rax
0x1800154ce  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$00@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800154d5  mov     [rdi+10h], rax
0x1800154d9  mov     [rdi+40h], r12
0x1800154dd  mov     [rdi+48h], r12
0x1800154e1  lea     rdx, [rsp+58h+newString]; newString
0x1800154e6  mov     rcx, [r15]; string
0x1800154e9  call    cs:__imp_WindowsDuplicateString
0x1800154ef  mov     ebp, eax
0x1800154f1  test    eax, eax
0x1800154f3  js      loc_18001560F
0x1800154f9  lea     rdx, [rsp+58h+arg_10]; newString
0x1800154fe  mov     rcx, [r15+8]; string
0x180015502  call    cs:__imp_WindowsDuplicateString
0x180015508  mov     ebp, eax
0x18001550a  test    eax, eax
0x18001550c  js      loc_180015622
0x180015512  mov     rcx, [rdi+40h]
0x180015516  mov     rax, [rsp+58h+newString]
0x18001551b  mov     [rdi+40h], rax
0x18001551f  mov     [rsp+58h+newString], rcx
0x180015524  mov     rcx, [rdi+48h]; string
0x180015528  mov     rax, [rsp+58h+arg_10]
0x18001552d  mov     [rdi+48h], rax
0x180015531  mov     [rsp+58h+arg_10], rcx
0x180015536  call    cs:__imp_WindowsDeleteString
0x18001553c  mov     rcx, [rsp+58h+newString]; string
0x180015541  call    cs:__imp_WindowsDeleteString
0x180015547  mov     [rsp+58h+newString], r12
0x18001554c  test    ebp, ebp
0x18001554e  jns     short loc_180015593
0x180015550  mov     rcx, rdi
0x180015553  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *>,Microsoft::WRL::FtmBase>::Release(void)
0x180015558  test    rbx, rbx
0x18001555b  jz      short loc_18001556C
0x18001555d  cmp     dword ptr [rbx], 1
0x180015560  jz      short loc_18001557D
0x180015562  lea     rcx, [rbx+8]; SRWLock
0x180015566  call    cs:__imp_ReleaseSRWLockShared
0x18001556c  mov     eax, ebp
0x18001556e  add     rsp, 20h
0x180015572  pop     r15
0x180015574  pop     r14
0x180015576  pop     r12
0x180015578  pop     rdi
0x180015579  pop     rsi
0x18001557a  pop     rbp
0x18001557b  pop     rbx
0x18001557c  retn
0x18001557d  dec     dword ptr [rbx+8]
0x180015580  jmp     short loc_18001556C
0x180015582  mov     ebp, 8000000Ch
0x180015587  xor     edx, edx
0x180015589  mov     ecx, ebp
0x18001558b  call    cs:__imp_RoOriginateError
0x180015591  jmp     short loc_180015558
0x180015593  mov     rax, [rdi]
0x180015596  mov     rcx, rdi
0x180015599  mov     rax, [rax+8]
0x18001559d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155a2  mov     [r14], rdi
0x1800155a5  mov     rax, [rdi+38h]
0x1800155a9  test    rax, rax
0x1800155ac  js      short loc_18001562A
0x1800155ae  cmp     eax, 7FFFFFFFh
0x1800155b3  jz      short loc_180015558
0x1800155b5  lea     rcx, [rax-1]
0x1800155b9  lock cmpxchg [rdi+38h], rcx
0x1800155bf  jnz     short loc_1800155A9
0x1800155c1  test    ecx, ecx
0x1800155c3  jnz     short loc_180015558
0x1800155c5  mov     rax, [rdi]
0x1800155c8  mov     edx, 1
0x1800155cd  mov     rcx, rdi
0x1800155d0  mov     rax, [rax+40h]
0x1800155d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155d9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800155e0  test    rcx, rcx
0x1800155e3  jz      loc_180015558
0x1800155e9  mov     rax, [rcx]
0x1800155ec  mov     rax, [rax+10h]
0x1800155f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155f5  jmp     loc_180015558
0x1800155fa  mov     eax, [rbx+8]
0x1800155fd  test    eax, eax
0x1800155ff  js      loc_1800153E9
0x180015605  inc     eax
0x180015607  mov     [rbx+8], eax
0x18001560a  jmp     loc_1800153E9
0x18001560f  mov     rcx, r12; string
0x180015612  mov     [rsp+58h+newString], rcx
0x180015617  call    cs:__imp_WindowsDeleteString
0x18001561d  jmp     loc_180015550
0x180015622  mov     rcx, r12
0x180015625  jmp     loc_180015531
0x18001562a  lea     rcx, ds:10h[rax*2]; this
0x180015632  call    ?DecrementStrongReference@StrongReference@Details@WRL@Microsoft@@QEAAKXZ; Microsoft::WRL::Details::StrongReference::DecrementStrongReference(void)
0x180015637  mov     ecx, eax
0x180015639  jmp     short loc_1800155C1
0x18001563b  mov     ebp, 8000000Bh
0x180015640  jmp     loc_180015587
0x180015645  mov     ebp, 8007000Eh
0x18001564a  jmp     loc_180015558
```
