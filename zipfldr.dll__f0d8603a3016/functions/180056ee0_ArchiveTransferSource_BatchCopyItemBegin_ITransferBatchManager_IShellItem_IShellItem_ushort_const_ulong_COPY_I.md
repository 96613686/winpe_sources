# ArchiveTransferSource::BatchCopyItemBegin(ITransferBatchManager *,IShellItem *,IShellItem *,ushort const *,ulong,COPY_ITEM_FLAGS,ITransferBatch * *,unsigned __int64 *)

- ea: `0x180056ee0`
- end: `0x180057428`
- name: `?BatchCopyItemBegin@ArchiveTransferSource@@UEAAJPEAUITransferBatchManager@@PEAUIShellItem@@1PEBGKW4COPY_ITEM_FLAGS@@PEAPEAUITransferBatch@@PEA_K@Z`
- size: `1352`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, char, __int64, __int64 *, _QWORD *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180020708`
- `0x180020cbc`
- `0x180021e1c`
- `0x180021f0c`
- `0x180024a24`
- `0x18002abd0`
- `0x180030a3c`
- `0x180031e94`
- `0x180033404`
- `0x180036f50`
- `0x180056988`
- `0x1800569c0`
- `0x180056a34`
- `0x180056ee0`
- `0x180057b90`
- `0x18006a0f8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800573ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800573ac`

## pseudocode

```c
__int64 __fastcall ArchiveTransferSource::BatchCopyItemBegin(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        __int64 *a8,
        _QWORD *a9)
{
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v18; // rbx
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // r8
  int v24; // eax
  unsigned int v25; // esi
  int ParentAndChildIDListFromItem; // eax
  unsigned int v27; // edi
  const struct ArchiveIdList *v28; // rsi
  __int64 (__fastcall *v29)(__int64, __int64, LPVOID *); // rdi
  int v30; // eax
  char v31; // r9
  int v32; // eax
  __int64 v33; // rax
  int v34; // [rsp+20h] [rbp-C8h]
  int v35; // [rsp+20h] [rbp-C8h]
  __int64 v36; // [rsp+30h] [rbp-B8h] BYREF
  LPVOID v37; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-98h] BYREF
  struct _ITEMIDLIST_RELATIVE *v41; // [rsp+58h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v43[32]; // [rsp+68h] [rbp-80h] BYREF
  _BYTE v44[32]; // [rsp+88h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v38 = a5;
  *a8 = 0;
  ArchiveTransferSource::GetBatchName(a1 - 24, v43);
  v39 = 0;
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(v14 + 32))(a2, v13, &v39);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)(unsigned int)v15,
      v34);
    if ( v39 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
    std::wstring::_Tidy_deallocate(v43);
    return v16;
  }
  v18 = 0;
  v36 = 0;
  if ( v39 )
  {
    v18 = v39;
    v36 = v39;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
  }
  else
  {
    v20 = (__int64 *)winrt::make_self<ArchiveTransferBatch,std::wstring const &>(&v37, *(_QWORD *)(a1 + 64) + 64LL);
    v21 = 0;
    if ( &v36 != v20 )
    {
      v18 = *v20;
      *v20 = 0;
      v36 = v18;
      v21 = v18;
    }
    if ( v37 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
    v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
    v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v23 + 24))(a2, v22, v18);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
        (const char *)(unsigned int)v24,
        v34);
      if ( v18 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
      if ( v39 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
      std::wstring::_Tidy_deallocate(v43);
      return v25;
    }
    if ( v39 != v21 )
    {
      if ( v39 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
      v39 = v21;
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  v40 = 0;
  v41 = 0;
  ParentAndChildIDListFromItem = GetParentAndChildIDListFromItem(a3, v19, &v40, &v41);
  v27 = ParentAndChildIDListFromItem;
  if ( ParentAndChildIDListFromItem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)(unsigned int)ParentAndChildIDListFromItem,
      v34);
    if ( v40 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v41);
    if ( v18 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
    if ( v39 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
LABEL_59:
    std::wstring::_Tidy_deallocate(v43);
    return v27;
  }
  v28 = ArchiveIdList::FromPIDL(v41);
  if ( v28 )
  {
    pv = 0;
    v29 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)a4 + 40LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    v30 = v29(a4, 2147844096LL, &pv);
    v27 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
        (const char *)(unsigned int)v30,
        v34);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v40 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
      wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v41);
      if ( v18 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
      if ( v39 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
      goto LABEL_59;
    }
    v37 = pv;
    std::filesystem::path::path(v44, &v37);
    std::filesystem::path::operator/=<unsigned short const *,0>(v44, &v38);
    v31 = 2;
    if ( (a6 & 2) != 0 )
      v31 = 3;
    v32 = ArchiveTransferBatch::Add(v18, *((_DWORD *)v28 + 6), (__int64)v44, v31, *((_DWORD *)v28 + 1), a9);
    v27 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
        (const char *)(unsigned int)v32,
        v35);
      std::wstring::_Tidy_deallocate(v44);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v40 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
      wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v41);
      if ( v18 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
      if ( v39 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
      goto LABEL_59;
    }
    v33 = v39;
    v39 = 0;
    *a8 = v33;
    std::wstring::_Tidy_deallocate(v44);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v40 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v41);
    if ( v18 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
    if ( v39 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
    std::wstring::_Tidy_deallocate(v43);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)0x80070057LL,
      v34);
    if ( v40 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v41);
    if ( v18 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
    if ( v39 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
    std::wstring::_Tidy_deallocate(v43);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180056ee0  push    rbx
0x180056ee2  push    rsi
0x180056ee3  push    rdi
0x180056ee4  push    r12
0x180056ee6  push    r13
0x180056ee8  push    r14
0x180056eea  push    r15
0x180056eec  sub     rsp, 0B0h
0x180056ef3  mov     rax, cs:__security_cookie
0x180056efa  xor     rax, rsp
0x180056efd  mov     [rsp+0E8h+var_40], rax
0x180056f05  mov     r12, r9
0x180056f08  mov     r15, r8
0x180056f0b  mov     rsi, rdx
0x180056f0e  mov     rdi, rcx
0x180056f11  mov     rax, [rsp+0E8h+arg_20]
0x180056f19  mov     [rsp+0E8h+var_A8], rax
0x180056f1e  mov     r14, [rsp+0E8h+arg_38]
0x180056f26  mov     r13, [rsp+0E8h+arg_40]
0x180056f2e  xor     ebx, ebx
0x180056f30  mov     [r14], rbx
0x180056f33  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180056f37  lea     rdx, [rsp+0E8h+var_80]
0x180056f3c  call    ?GetBatchName@ArchiveTransferSource@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ArchiveTransferSource::GetBatchName(void)
0x180056f41  nop
0x180056f42  mov     [rsp+0E8h+var_A0], rbx
0x180056f47  mov     r8, [rsi]
0x180056f4a  lea     rcx, [rsp+0E8h+var_80]
0x180056f4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056f54  mov     rdx, rax
0x180056f57  mov     rax, [r8+20h]
0x180056f5b  lea     r8, [rsp+0E8h+var_A0]
0x180056f60  mov     rcx, rsi
0x180056f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f68  mov     ebx, eax
0x180056f6a  test    eax, eax
0x180056f6c  jns     short loc_180056FAF
0x180056f6e  mov     rcx, [rsp+0E8h]; this
0x180056f76  mov     r9d, eax; char *
0x180056f79  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x180056f80  mov     edx, 0AAh; void *
0x180056f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056f8a  nop
0x180056f8b  cmp     [rsp+0E8h+var_A0], 0
0x180056f91  jz      short loc_180056F9E
0x180056f93  lea     rcx, [rsp+0E8h+var_A0]
0x180056f98  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180056f9d  nop
0x180056f9e  lea     rcx, [rsp+0E8h+var_80]
0x180056fa3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180056fa8  mov     eax, ebx
0x180056faa  jmp     loc_180057404
0x180056faf  xor     ebx, ebx
0x180056fb1  mov     [rsp+0E8h+var_B8], rbx
0x180056fb6  mov     rcx, [rsp+0E8h+var_A0]
0x180056fbb  test    rcx, rcx
0x180056fbe  jz      short loc_180056FD9
0x180056fc0  mov     rbx, rcx
0x180056fc3  mov     [rsp+0E8h+var_B8], rcx
0x180056fc8  mov     rax, [rcx]
0x180056fcb  mov     rax, [rax+8]
0x180056fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056fd4  jmp     loc_1800570C0
0x180056fd9  mov     rdx, [rdi+40h]
0x180056fdd  add     rdx, 40h ; '@'
0x180056fe1  lea     rcx, [rsp+0E8h+var_B0]
0x180056fe6  call    ??$make_self@UArchiveTransferBatch@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@winrt@@YA?AU?$com_ptr@UArchiveTransferBatch@@@0@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::make_self<ArchiveTransferBatch,std::wstring const &>(std::wstring const &)
0x180056feb  xor     edi, edi
0x180056fed  lea     rcx, [rsp+0E8h+var_B8]
0x180056ff2  cmp     rcx, rax
0x180056ff5  jz      short loc_180057005
0x180056ff7  mov     rbx, [rax]
0x180056ffa  mov     [rax], rdi
0x180056ffd  mov     [rsp+0E8h+var_B8], rbx
0x180057002  mov     rdi, rbx
0x180057005  cmp     [rsp+0E8h+var_B0], 0
0x18005700b  jz      short loc_180057017
0x18005700d  lea     rcx, [rsp+0E8h+var_B0]
0x180057012  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180057017  mov     r8, [rsi]
0x18005701a  lea     rcx, [rsp+0E8h+var_80]
0x18005701f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057024  mov     rdx, rax
0x180057027  mov     rax, [r8+18h]
0x18005702b  mov     r8, rbx
0x18005702e  mov     rcx, rsi
0x180057031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057036  mov     esi, eax
0x180057038  test    eax, eax
0x18005703a  jns     short loc_18005708D
0x18005703c  mov     rcx, [rsp+0E8h]; this
0x180057044  mov     r9d, eax; char *
0x180057047  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x18005704e  mov     edx, 0B8h; void *
0x180057053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057058  nop
0x180057059  test    rbx, rbx
0x18005705c  jz      short loc_180057069
0x18005705e  lea     rcx, [rsp+0E8h+var_B8]
0x180057063  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180057068  nop
0x180057069  cmp     [rsp+0E8h+var_A0], 0
0x18005706f  jz      short loc_18005707C
0x180057071  lea     rcx, [rsp+0E8h+var_A0]
0x180057076  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005707b  nop
0x18005707c  lea     rcx, [rsp+0E8h+var_80]
0x180057081  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057086  mov     eax, esi
0x180057088  jmp     loc_180057404
0x18005708d  mov     rax, [rsp+0E8h+var_A0]
0x180057092  cmp     rax, rdi
0x180057095  jz      short loc_1800570C0
0x180057097  test    rax, rax
0x18005709a  jz      short loc_1800570A6
0x18005709c  lea     rcx, [rsp+0E8h+var_A0]
0x1800570a1  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800570a6  mov     [rsp+0E8h+var_A0], rdi
0x1800570ab  test    rdi, rdi
0x1800570ae  jz      short loc_1800570C0
0x1800570b0  mov     rax, [rdi]
0x1800570b3  mov     rcx, rdi
0x1800570b6  mov     rax, [rax+8]
0x1800570ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570bf  nop
0x1800570c0  mov     [rsp+0E8h+var_98], 0
0x1800570c9  mov     [rsp+0E8h+var_90], 0
0x1800570d2  lea     r9, [rsp+0E8h+var_90]
0x1800570d7  lea     r8, [rsp+0E8h+var_98]
0x1800570dc  mov     rcx, r15
0x1800570df  call    GetParentAndChildIDListFromItem
0x1800570e4  mov     edi, eax
0x1800570e6  xor     r15d, r15d
0x1800570e9  test    eax, eax
0x1800570eb  jns     short loc_18005715A
0x1800570ed  mov     rcx, [rsp+0E8h]; this
0x1800570f5  mov     r9d, eax; char *
0x1800570f8  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x1800570ff  mov     edx, 0BFh; void *
0x180057104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057109  nop
0x18005710a  cmp     [rsp+0E8h+var_98], r15
0x18005710f  jz      short loc_18005711C
0x180057111  lea     rcx, [rsp+0E8h+var_98]
0x180057116  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005711b  nop
0x18005711c  lea     rcx, [rsp+0E8h+var_90]
0x180057121  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180057126  nop
0x180057127  test    rbx, rbx
0x18005712a  jz      short loc_180057137
0x18005712c  lea     rcx, [rsp+0E8h+var_B8]
0x180057131  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180057136  nop
0x180057137  cmp     [rsp+0E8h+var_A0], r15
0x18005713c  jz      short loc_180057149
0x18005713e  lea     rcx, [rsp+0E8h+var_A0]
0x180057143  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057148  nop
0x180057149  lea     rcx, [rsp+0E8h+var_80]
0x18005714e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057153  mov     eax, edi
0x180057155  jmp     loc_180057404
0x18005715a  mov     rcx, [rsp+0E8h+var_90]; struct _ITEMIDLIST_RELATIVE *
0x18005715f  call    ?FromPIDL@ArchiveIdList@@SAPEFBU1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ArchiveIdList::FromPIDL(_ITEMIDLIST_RELATIVE const *)
0x180057164  mov     rsi, rax
0x180057167  test    rax, rax
0x18005716a  jnz     short loc_1800571DE
0x18005716c  mov     rcx, [rsp+0E8h]; this
0x180057174  mov     edi, 80070057h
0x180057179  mov     r9d, edi; char *
0x18005717c  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x180057183  mov     edx, 0C2h; void *
0x180057188  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005718d  nop
0x18005718e  cmp     [rsp+0E8h+var_98], r15
0x180057193  jz      short loc_1800571A0
0x180057195  lea     rcx, [rsp+0E8h+var_98]
0x18005719a  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005719f  nop
0x1800571a0  lea     rcx, [rsp+0E8h+var_90]
0x1800571a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x1800571aa  nop
0x1800571ab  test    rbx, rbx
0x1800571ae  jz      short loc_1800571BB
0x1800571b0  lea     rcx, [rsp+0E8h+var_B8]
0x1800571b5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800571ba  nop
0x1800571bb  cmp     [rsp+0E8h+var_A0], r15
0x1800571c0  jz      short loc_1800571CD
0x1800571c2  lea     rcx, [rsp+0E8h+var_A0]
0x1800571c7  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800571cc  nop
0x1800571cd  lea     rcx, [rsp+0E8h+var_80]
0x1800571d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800571d7  mov     eax, edi
0x1800571d9  jmp     loc_180057404
0x1800571de  mov     [rsp+0E8h+pv], r15
0x1800571e3  mov     rax, [r12]
0x1800571e7  mov     rdi, [rax+28h]
0x1800571eb  xor     edx, edx
0x1800571ed  lea     rcx, [rsp+0E8h+pv]
0x1800571f2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800571f7  lea     r8, [rsp+0E8h+pv]
0x1800571fc  mov     edx, 80058000h
0x180057201  mov     rcx, r12
0x180057204  mov     rax, rdi
0x180057207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005720c  mov     edi, eax
0x18005720e  test    eax, eax
0x180057210  jns     short loc_180057290
0x180057212  mov     rcx, [rsp+0E8h]; this
0x18005721a  mov     r9d, eax; char *
0x18005721d  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x180057224  mov     edx, 0C5h; void *
0x180057229  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005722e  nop
0x18005722f  mov     rcx, [rsp+0E8h+pv]; pv
0x180057234  test    rcx, rcx
0x180057237  jz      short loc_180057240
0x180057239  call    cs:__imp_CoTaskMemFree
0x18005723f  nop
0x180057240  cmp     [rsp+0E8h+var_98], r15
0x180057245  jz      short loc_180057252
0x180057247  lea     rcx, [rsp+0E8h+var_98]
0x18005724c  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057251  nop
0x180057252  lea     rcx, [rsp+0E8h+var_90]
0x180057257  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x18005725c  nop
0x18005725d  test    rbx, rbx
0x180057260  jz      short loc_18005726D
0x180057262  lea     rcx, [rsp+0E8h+var_B8]
0x180057267  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18005726c  nop
0x18005726d  cmp     [rsp+0E8h+var_A0], r15
0x180057272  jz      short loc_18005727F
0x180057274  lea     rcx, [rsp+0E8h+var_A0]
0x180057279  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005727e  nop
0x18005727f  lea     rcx, [rsp+0E8h+var_80]
0x180057284  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057289  mov     eax, edi
0x18005728b  jmp     loc_180057404
0x180057290  mov     rax, [rsp+0E8h+pv]
0x180057295  mov     [rsp+0E8h+var_B0], rax
0x18005729a  lea     rdx, [rsp+0E8h+var_B0]
0x18005729f  lea     rcx, [rsp+0E8h+var_60]
0x1800572a7  call    ??$?0PEAG$0A@@path@filesystem@std@@QEAA@AEBQEAGW4format@012@@Z; std::filesystem::path::path(ushort * const &,std::filesystem::path::format)
0x1800572ac  nop
0x1800572ad  lea     rdx, [rsp+0E8h+var_A8]
0x1800572b2  lea     rcx, [rsp+0E8h+var_60]
0x1800572ba  call    ??$?_0PEBG$0A@@path@filesystem@std@@QEAAAEAV012@AEBQEBG@Z; std::filesystem::path::operator/=<ushort const *,0>(ushort const * const &)
0x1800572bf  mov     al, 2
0x1800572c1  test    [rsp+0E8h+arg_28], al
0x1800572c8  movzx   r9d, al
0x1800572cc  mov     eax, 3
0x1800572d1  cmovnz  r9d, eax
0x1800572d5  mov     [rsp+0E8h+var_C0], r13
0x1800572da  mov     eax, [rsi+4]
0x1800572dd  mov     [rsp+0E8h+var_C8], eax; int
0x1800572e1  lea     r8, [rsp+0E8h+var_60]
0x1800572e9  mov     edx, [rsi+18h]
0x1800572ec  mov     rcx, rbx
0x1800572ef  call    ?Add@ArchiveTransferBatch@@QEAAJKAEBVpath@filesystem@std@@W4ExtractFlags@@KPEA_K@Z; ArchiveTransferBatch::Add(ulong,std::filesystem::path const &,ExtractFlags,ulong,unsigned __int64 *)
0x1800572f4  mov     edi, eax
0x1800572f6  test    eax, eax
0x1800572f8  jns     loc_180057387
0x1800572fe  mov     rcx, [rsp+0E8h]; this
0x180057306  mov     r9d, eax; char *
0x180057309  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x180057310  mov     edx, 0CDh; void *
0x180057315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005731a  nop
0x18005731b  lea     rcx, [rsp+0E8h+var_60]
0x180057323  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057328  nop
0x180057329  mov     rcx, [rsp+0E8h+pv]; pv
0x18005732e  test    rcx, rcx
0x180057331  jz      short loc_18005733A
0x180057333  call    cs:__imp_CoTaskMemFree
0x180057339  nop
0x18005733a  cmp     [rsp+0E8h+var_98], r15
0x18005733f  jz      short loc_18005734C
0x180057341  lea     rcx, [rsp+0E8h+var_98]
0x180057346  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005734b  nop
0x18005734c  lea     rcx, [rsp+0E8h+var_90]
0x180057351  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180057356  nop
0x180057357  test    rbx, rbx
0x18005735a  jz      short loc_180057367
0x18005735c  lea     rcx, [rsp+0E8h+var_B8]
0x180057361  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180057366  nop
0x180057367  cmp     [rsp+0E8h+var_A0], r15
0x18005736c  jz      short loc_180057379
0x18005736e  lea     rcx, [rsp+0E8h+var_A0]
0x180057373  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057378  nop
  ... truncated ...
```
