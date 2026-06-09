# ArchiveTransferSource::CopyItem(IShellItem *,IShellItem *,ushort const *,ulong,COPY_ITEM_FLAGS,IShellItem * *)

- ea: `0x180057610`
- end: `0x180057b32`
- name: `?CopyItem@ArchiveTransferSource@@UEAAJPEAUIShellItem@@0PEBGKW4COPY_ITEM_FLAGS@@PEAPEAU2@@Z`
- size: `1314`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char, __int64, void **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000ca94`
- `0x180020708`
- `0x180020cbc`
- `0x180021e1c`
- `0x180021f0c`
- `0x180024a24`
- `0x18002abd0`
- `0x180030a3c`
- `0x180031e94`
- `0x180034fbc`
- `0x180036f50`
- `0x180056988`
- `0x1800569c0`
- `0x180057610`
- `0x180057d74`
- `0x180057fbc`
- `0x180065780`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800579cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057a7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ae5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800579cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057a7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ae5`

## pseudocode

```c
__int64 __fastcall ArchiveTransferSource::CopyItem(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        __int64 a6,
        void **a7)
{
  int ParentAndChildIDListFromItem; // eax
  unsigned int v10; // ebx
  const struct ArchiveIdList *v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, LPVOID *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int ExtendedLengthPath; // eax
  unsigned int v18; // ebx
  char v19; // bl
  __int64 v20; // rax
  int v21; // eax
  struct IBindCtx *v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  const WCHAR *v26; // rax
  const struct _GUID *v27; // rdx
  int v28; // eax
  int v29; // [rsp+20h] [rbp-F8h]
  LPVOID v30; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v31[40]; // [rsp+38h] [rbp-E0h] BYREF
  _QWORD v32[2]; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+70h] [rbp-A8h] BYREF
  struct _ITEMIDLIST_RELATIVE *v34; // [rsp+78h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-98h] BYREF
  struct IBindCtx *v36; // [rsp+88h] [rbp-90h] BYREF
  _OWORD v37[2]; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v38[16]; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v32[0] = a4;
  *a7 = 0;
  v33 = 0;
  v34 = 0;
  ParentAndChildIDListFromItem = GetParentAndChildIDListFromItem(a2, a2, &v33, &v34);
  v10 = ParentAndChildIDListFromItem;
  if ( ParentAndChildIDListFromItem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)(unsigned int)ParentAndChildIDListFromItem,
      v29);
    if ( v33 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
LABEL_4:
    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v34);
    return v10;
  }
  v12 = ArchiveIdList::FromPIDL(v34);
  if ( !v12 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)0x80070057LL,
      v29);
    if ( v33 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v34);
    return 2147942487LL;
  }
  pv = 0;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)a3 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v14 = v13(a3, 2147844096LL, &pv);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)(unsigned int)v14,
      v29);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v33 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
    goto LABEL_4;
  }
  v30 = pv;
  std::filesystem::path::path(v38, &v30);
  std::filesystem::path::operator/=<unsigned short const *,0>(v38, v32);
  v37[0] = 0;
  v37[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v37[0]) = 0;
  v32[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38, v15, v16);
  v32[1] = v39;
  ExtendedLengthPath = MakeExtendedLengthPath(v32, v37);
  v18 = ExtendedLengthPath;
  if ( ExtendedLengthPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)(unsigned int)ExtendedLengthPath,
      v29);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v38);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v33 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
LABEL_44:
    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v34);
    return v18;
  }
  v19 = 2;
  if ( (a5 & 2) != 0 )
    v19 = 3;
  v20 = std::wstring::wstring(v31, v37);
  LOBYTE(v29) = v19;
  v21 = ExtractFromArchiveByIndex(*(_QWORD *)(a1 + 88) + 64LL, *((unsigned int *)v12 + 6), v20);
  v18 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)(unsigned int)v21,
      v29);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v38);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v33 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
    goto LABEL_44;
  }
  v36 = 0;
  v23 = SHCreateFileSysBindCtxFromAttributes(v22, *((_DWORD *)v12 + 1), &v36);
  v18 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)(unsigned int)v23,
      v29);
    if ( v36 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v36);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v38);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v33 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
    goto LABEL_44;
  }
  v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38, v24, v25);
  v28 = ShellItemFromFileSystemPath(v26, v27, a7, v36);
  v18 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"shell\\ext\\zip\\archive\\archivetransfersource.cpp",
      (const char *)(unsigned int)v28,
      v29);
    if ( v36 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v36);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v38);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v33 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
    goto LABEL_44;
  }
  if ( v36 )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v36);
  std::wstring::_Tidy_deallocate(v37);
  std::wstring::_Tidy_deallocate(v38);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v33 )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v33);
  wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&v34);
  return 0;
}

```

## disassembly

```asm
0x180057610  push    rbx
0x180057612  push    rsi
0x180057613  push    rdi
0x180057614  push    r12
0x180057616  push    r14
0x180057618  push    r15
0x18005761a  sub     rsp, 0E8h
0x180057621  mov     rax, cs:__security_cookie
0x180057628  xor     rax, rsp
0x18005762b  mov     [rsp+118h+var_48], rax
0x180057633  mov     r14, r8
0x180057636  mov     r15, rcx
0x180057639  mov     [rsp+118h+var_B8], r9
0x18005763e  mov     rsi, [rsp+118h+arg_30]
0x180057646  xor     r12d, r12d
0x180057649  mov     [rsi], r12
0x18005764c  mov     [rsp+118h+var_A8], r12
0x180057651  mov     [rsp+118h+var_A0], r12
0x180057656  lea     r9, [rsp+118h+var_A0]
0x18005765b  lea     r8, [rsp+118h+var_A8]
0x180057660  mov     rcx, rdx
0x180057663  call    GetParentAndChildIDListFromItem
0x180057668  mov     ebx, eax
0x18005766a  test    eax, eax
0x18005766c  jns     short loc_1800576AE
0x18005766e  mov     rcx, [rsp+118h]; this
0x180057676  mov     r9d, eax; char *
0x180057679  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x180057680  lea     edx, [r12+61h]; void *
0x180057685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005768a  nop
0x18005768b  cmp     [rsp+118h+var_A8], r12
0x180057690  jz      short loc_18005769D
0x180057692  lea     rcx, [rsp+118h+var_A8]
0x180057697  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005769c  nop
0x18005769d  lea     rcx, [rsp+118h+var_A0]
0x1800576a2  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x1800576a7  mov     eax, ebx
0x1800576a9  jmp     loc_180057B10
0x1800576ae  mov     rcx, [rsp+118h+var_A0]; struct _ITEMIDLIST_RELATIVE *
0x1800576b3  call    ?FromPIDL@ArchiveIdList@@SAPEFBU1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ArchiveIdList::FromPIDL(_ITEMIDLIST_RELATIVE const *)
0x1800576b8  mov     rdi, rax
0x1800576bb  test    rax, rax
0x1800576be  jnz     short loc_180057703
0x1800576c0  mov     rcx, [rsp+118h]; this
0x1800576c8  mov     ebx, 80070057h
0x1800576cd  mov     r9d, ebx; char *
0x1800576d0  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x1800576d7  lea     edx, [rax+64h]; void *
0x1800576da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800576df  nop
0x1800576e0  cmp     [rsp+118h+var_A8], r12
0x1800576e5  jz      short loc_1800576F2
0x1800576e7  lea     rcx, [rsp+118h+var_A8]
0x1800576ec  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800576f1  nop
0x1800576f2  lea     rcx, [rsp+118h+var_A0]
0x1800576f7  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x1800576fc  mov     eax, ebx
0x1800576fe  jmp     loc_180057B10
0x180057703  mov     [rsp+118h+pv], r12
0x18005770b  mov     rax, [r14]
0x18005770e  mov     rbx, [rax+28h]
0x180057712  xor     edx, edx
0x180057714  lea     rcx, [rsp+118h+pv]
0x18005771c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180057721  lea     r8, [rsp+118h+pv]
0x180057729  mov     edx, 80058000h
0x18005772e  mov     rcx, r14
0x180057731  mov     rax, rbx
0x180057734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057739  mov     ebx, eax
0x18005773b  test    eax, eax
0x18005773d  jns     short loc_180057793
0x18005773f  mov     rcx, [rsp+118h]; this
0x180057747  mov     r9d, eax; char *
0x18005774a  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x180057751  mov     edx, 67h ; 'g'; void *
0x180057756  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005775b  nop
0x18005775c  mov     rcx, [rsp+118h+pv]; pv
0x180057764  test    rcx, rcx
0x180057767  jz      short loc_180057770
0x180057769  call    cs:__imp_CoTaskMemFree
0x18005776f  nop
0x180057770  cmp     [rsp+118h+var_A8], r12
0x180057775  jz      short loc_180057782
0x180057777  lea     rcx, [rsp+118h+var_A8]
0x18005777c  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057781  nop
0x180057782  lea     rcx, [rsp+118h+var_A0]
0x180057787  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x18005778c  mov     eax, ebx
0x18005778e  jmp     loc_180057B10
0x180057793  mov     rax, [rsp+118h+pv]
0x18005779b  mov     [rsp+118h+var_E8], rax
0x1800577a0  lea     rdx, [rsp+118h+var_E8]
0x1800577a5  lea     rcx, [rsp+118h+var_68]
0x1800577ad  call    ??$?0PEAG$0A@@path@filesystem@std@@QEAA@AEBQEAGW4format@012@@Z; std::filesystem::path::path(ushort * const &,std::filesystem::path::format)
0x1800577b2  nop
0x1800577b3  lea     rdx, [rsp+118h+var_B8]
0x1800577b8  lea     rcx, [rsp+118h+var_68]
0x1800577c0  call    ??$?_0PEBG$0A@@path@filesystem@std@@QEAAAEAV012@AEBQEBG@Z; std::filesystem::path::operator/=<ushort const *,0>(ushort const * const &)
0x1800577c5  xorps   xmm0, xmm0
0x1800577c8  movups  [rsp+118h+var_88], xmm0
0x1800577d0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800577d8  movdqu  [rsp+118h+var_78], xmm1
0x1800577e1  mov     word ptr [rsp+118h+var_88], r12w
0x1800577ea  lea     rcx, [rsp+118h+var_68]
0x1800577f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800577f7  mov     [rsp+118h+var_B8], rax
0x1800577fc  mov     rax, [rsp+118h+var_58]
0x180057804  mov     [rsp+118h+var_B0], rax
0x180057809  lea     rdx, [rsp+118h+var_88]
0x180057811  lea     rcx, [rsp+118h+var_B8]
0x180057816  call    ?MakeExtendedLengthPath@@YAJV?$basic_zstring_view@G@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MakeExtendedLengthPath(wil::basic_zstring_view<ushort>,std::wstring &)
0x18005781b  mov     ebx, eax
0x18005781d  test    eax, eax
0x18005781f  jns     short loc_180057891
0x180057821  mov     rcx, [rsp+118h]; this
0x180057829  mov     r9d, eax; char *
0x18005782c  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x180057833  mov     edx, 6Dh ; 'm'; void *
0x180057838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005783d  nop
0x18005783e  lea     rcx, [rsp+118h+var_88]
0x180057846  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005784b  nop
0x18005784c  lea     rcx, [rsp+118h+var_68]
0x180057854  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057859  nop
0x18005785a  mov     rcx, [rsp+118h+pv]; pv
0x180057862  test    rcx, rcx
0x180057865  jz      short loc_18005786E
0x180057867  call    cs:__imp_CoTaskMemFree
0x18005786d  nop
0x18005786e  cmp     [rsp+118h+var_A8], r12
0x180057873  jz      short loc_180057880
0x180057875  lea     rcx, [rsp+118h+var_A8]
0x18005787a  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005787f  nop
0x180057880  lea     rcx, [rsp+118h+var_A0]
0x180057885  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x18005788a  mov     eax, ebx
0x18005788c  jmp     loc_180057B10
0x180057891  mov     al, 2
0x180057893  test    [rsp+118h+arg_20], al
0x18005789a  movzx   ebx, al
0x18005789d  mov     eax, 3
0x1800578a2  cmovnz  ebx, eax
0x1800578a5  mov     r14, [r15+38h]
0x1800578a9  lea     rdx, [rsp+118h+var_88]
0x1800578b1  lea     rcx, [rsp+118h+var_E0]
0x1800578b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800578bb  mov     rcx, [r15+58h]
0x1800578bf  add     rcx, 40h ; '@'
0x1800578c3  mov     byte ptr [rsp+118h+var_F8], bl; int
0x1800578c7  mov     r9, r14
0x1800578ca  mov     r8, rax
0x1800578cd  mov     edx, [rdi+18h]
0x1800578d0  call    ?ExtractFromArchiveByIndex@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IV12@PEAUHWND__@@W4ExtractFlags@@@Z; ExtractFromArchiveByIndex(std::wstring const &,uint,std::wstring,HWND__ *,ExtractFlags)
0x1800578d5  mov     ebx, eax
0x1800578d7  test    eax, eax
0x1800578d9  jns     short loc_18005794B
0x1800578db  mov     rcx, [rsp+118h]; this
0x1800578e3  mov     r9d, eax; char *
0x1800578e6  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x1800578ed  mov     edx, 72h ; 'r'; void *
0x1800578f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800578f7  nop
0x1800578f8  lea     rcx, [rsp+118h+var_88]
0x180057900  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057905  nop
0x180057906  lea     rcx, [rsp+118h+var_68]
0x18005790e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057913  nop
0x180057914  mov     rcx, [rsp+118h+pv]; pv
0x18005791c  test    rcx, rcx
0x18005791f  jz      short loc_180057928
0x180057921  call    cs:__imp_CoTaskMemFree
0x180057927  nop
0x180057928  cmp     [rsp+118h+var_A8], r12
0x18005792d  jz      short loc_18005793A
0x18005792f  lea     rcx, [rsp+118h+var_A8]
0x180057934  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057939  nop
0x18005793a  lea     rcx, [rsp+118h+var_A0]
0x18005793f  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180057944  mov     eax, ebx
0x180057946  jmp     loc_180057B10
0x18005794b  mov     [rsp+118h+var_90], r12
0x180057953  lea     r8, [rsp+118h+var_90]; struct IBindCtx **
0x18005795b  mov     edx, [rdi+4]; unsigned int
0x18005795e  call    ?SHCreateFileSysBindCtxFromAttributes@@YAJPEAUIBindCtx@@KPEAPEAU1@@Z; SHCreateFileSysBindCtxFromAttributes(IBindCtx *,ulong,IBindCtx * *)
0x180057963  mov     ebx, eax
0x180057965  test    eax, eax
0x180057967  jns     loc_1800579F5
0x18005796d  mov     rcx, [rsp+118h]; this
0x180057975  mov     r9d, eax; char *
0x180057978  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x18005797f  mov     edx, 75h ; 'u'; void *
0x180057984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057989  nop
0x18005798a  cmp     [rsp+118h+var_90], r12
0x180057992  jz      short loc_1800579A2
0x180057994  lea     rcx, [rsp+118h+var_90]
0x18005799c  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800579a1  nop
0x1800579a2  lea     rcx, [rsp+118h+var_88]
0x1800579aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800579af  nop
0x1800579b0  lea     rcx, [rsp+118h+var_68]
0x1800579b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800579bd  nop
0x1800579be  mov     rcx, [rsp+118h+pv]; pv
0x1800579c6  test    rcx, rcx
0x1800579c9  jz      short loc_1800579D2
0x1800579cb  call    cs:__imp_CoTaskMemFree
0x1800579d1  nop
0x1800579d2  cmp     [rsp+118h+var_A8], r12
0x1800579d7  jz      short loc_1800579E4
0x1800579d9  lea     rcx, [rsp+118h+var_A8]
0x1800579de  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800579e3  nop
0x1800579e4  lea     rcx, [rsp+118h+var_A0]
0x1800579e9  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x1800579ee  mov     eax, ebx
0x1800579f0  jmp     loc_180057B10
0x1800579f5  lea     rcx, [rsp+118h+var_68]
0x1800579fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057a02  mov     rcx, rax; pszPath
0x180057a05  mov     r9, [rsp+118h+var_90]; struct IBindCtx *
0x180057a0d  mov     r8, rsi; void **
0x180057a10  call    ?ShellItemFromFileSystemPath@@YAJPEBGAEBU_GUID@@PEAPEAXPEAUIBindCtx@@@Z; ShellItemFromFileSystemPath(ushort const *,_GUID const &,void * *,IBindCtx *)
0x180057a15  mov     ebx, eax
0x180057a17  test    eax, eax
0x180057a19  jns     loc_180057AA4
0x180057a1f  mov     rcx, [rsp+118h]; this
0x180057a27  mov     r9d, eax; char *
0x180057a2a  lea     r8, aShellExtZipArc; "shell\\ext\\zip\\archive\\archivetransf"...
0x180057a31  mov     edx, 76h ; 'v'; void *
0x180057a36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057a3b  nop
0x180057a3c  cmp     [rsp+118h+var_90], r12
0x180057a44  jz      short loc_180057A54
0x180057a46  lea     rcx, [rsp+118h+var_90]
0x180057a4e  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057a53  nop
0x180057a54  lea     rcx, [rsp+118h+var_88]
0x180057a5c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057a61  nop
0x180057a62  lea     rcx, [rsp+118h+var_68]
0x180057a6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057a6f  nop
0x180057a70  mov     rcx, [rsp+118h+pv]; pv
0x180057a78  test    rcx, rcx
0x180057a7b  jz      short loc_180057A84
0x180057a7d  call    cs:__imp_CoTaskMemFree
0x180057a83  nop
0x180057a84  cmp     [rsp+118h+var_A8], r12
0x180057a89  jz      short loc_180057A96
0x180057a8b  lea     rcx, [rsp+118h+var_A8]
0x180057a90  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057a95  nop
0x180057a96  lea     rcx, [rsp+118h+var_A0]
0x180057a9b  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180057aa0  mov     eax, ebx
0x180057aa2  jmp     short loc_180057B10
0x180057aa4  cmp     [rsp+118h+var_90], r12
0x180057aac  jz      short loc_180057ABC
0x180057aae  lea     rcx, [rsp+118h+var_90]
0x180057ab6  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057abb  nop
0x180057abc  lea     rcx, [rsp+118h+var_88]
0x180057ac4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057ac9  nop
0x180057aca  lea     rcx, [rsp+118h+var_68]
0x180057ad2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057ad7  nop
0x180057ad8  mov     rcx, [rsp+118h+pv]; pv
0x180057ae0  test    rcx, rcx
0x180057ae3  jz      short loc_180057AEC
0x180057ae5  call    cs:__imp_CoTaskMemFree
0x180057aeb  nop
0x180057aec  cmp     [rsp+118h+var_A8], r12
0x180057af1  jz      short loc_180057AFE
0x180057af3  lea     rcx, [rsp+118h+var_A8]
0x180057af8  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180057afd  nop
0x180057afe  lea     rcx, [rsp+118h+var_A0]
0x180057b03  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180057b08  xor     eax, eax
0x180057b0a  jmp     short loc_180057B10
0x180057b0c  mov     eax, dword ptr [rsp+118h+var_A8]
0x180057b10  mov     rcx, [rsp+118h+var_48]
0x180057b18  xor     rcx, rsp; StackCookie
0x180057b1b  call    __security_check_cookie
0x180057b20  add     rsp, 0E8h
0x180057b27  pop     r15
  ... truncated ...
```
