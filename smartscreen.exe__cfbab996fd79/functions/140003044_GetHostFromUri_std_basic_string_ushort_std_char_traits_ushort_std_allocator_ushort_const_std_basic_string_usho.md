# GetHostFromUri(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140003044`
- end: `0x1400031b5`
- name: `?GetHostFromUri@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400039fc`

## callees

- `0x140003044`
- `0x140013414`
- `0x140016ce4`
- `0x140016e88`
- `0x1400184f0`
- `0x140019844`
- `0x14001e6d4`
- `0x140026c20`
- `0x14006a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140003173`
- `OLEAUT32!__imp_SysFreeString` at `0x140003173`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x140003080`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x140003080`

## string_xrefs

- `0x140003099`: `onecore\amcore\smartscreen\src\client\urlrep\src\uri_reputation.cpp`
- `0x1400030f1`: `onecore\amcore\smartscreen\src\client\urlrep\src\uri_reputation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetHostFromUri(const WCHAR *a1, __int64 a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  struct IUriVtbl *lpVtbl; // rax
  int v7; // eax
  __int64 v8; // r8
  __int128 v9; // [rsp+20h] [rbp-40h] BYREF
  __int128 v10; // [rsp+30h] [rbp-30h]
  BSTR bstrString; // [rsp+40h] [rbp-20h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  ppURI = 0;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  v3 = CreateUri(a1, 0x100u, 0, &ppURI);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\uri_reputation.cpp",
      (const char *)(unsigned int)v3,
      v9);
    if ( ppURI )
      ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    return v4;
  }
  bstrString = 0;
  lpVtbl = ppURI->lpVtbl;
  bstrString = 0;
  v7 = ((__int64 (__fastcall *)(IUri *, BSTR *))lpVtbl->GetHost)(ppURI, &bstrString);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\uri_reputation.cpp",
      (const char *)(unsigned int)v7,
      v9);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
    wil::com_ptr_t<IUri,wil::err_exception_policy>::~com_ptr_t<IUri,wil::err_exception_policy>(&ppURI);
    return v4;
  }
  v9 = 0;
  v10 = 0;
  v8 = -1;
  do
    ++v8;
  while ( bstrString[v8] );
  std::wstring::_Construct<1,unsigned short const *>(&v9, bstrString, v8);
  std::wstring::operator=(a2, &v9);
  if ( *((_QWORD *)&v10 + 1) > 7u )
    std::_Deallocate<16>(v9, 2LL * *((_QWORD *)&v10 + 1) + 2);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  return 0;
}

```

## disassembly

```asm
0x140003044  mov     [rsp-18h+arg_10], rbx
0x140003049  push    rbp
0x14000304a  push    rsi
0x14000304b  push    rdi
0x14000304c  mov     rbp, rsp
0x14000304f  sub     rsp, 60h
0x140003053  mov     rax, cs:__security_cookie
0x14000305a  xor     rax, rsp
0x14000305d  mov     [rbp+var_10], rax
0x140003061  mov     rdi, rdx
0x140003064  xor     esi, esi
0x140003066  mov     [rbp+ppURI], rsi
0x14000306a  cmp     qword ptr [rcx+18h], 7
0x14000306f  jbe     short loc_140003074
0x140003071  mov     rcx, [rcx]; pwzURI
0x140003074  lea     r9, [rbp+ppURI]; ppURI
0x140003078  xor     r8d, r8d; dwReserved
0x14000307b  mov     edx, 100h; dwFlags
0x140003080  call    cs:__imp_CreateUri
0x140003087  nop     dword ptr [rax+rax+00h]
0x14000308c  mov     ebx, eax
0x14000308e  test    eax, eax
0x140003090  jns     short loc_1400030C8
0x140003092  mov     rcx, [rbp+18h]; this
0x140003096  mov     r9d, eax; char *
0x140003099  lea     r8, aOnecoreAmcoreS_7; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400030a0  mov     edx, 1Eh; void *
0x1400030a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400030aa  nop
0x1400030ab  mov     rcx, [rbp+ppURI]
0x1400030af  test    rcx, rcx
0x1400030b2  jz      short loc_1400030C1
0x1400030b4  mov     rax, [rcx]
0x1400030b7  mov     rax, [rax+10h]
0x1400030bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030c0  nop
0x1400030c1  mov     eax, ebx
0x1400030c3  jmp     loc_140003198
0x1400030c8  mov     [rbp+bstrString], rsi
0x1400030cc  mov     rcx, [rbp+ppURI]
0x1400030d0  mov     rax, [rcx]
0x1400030d3  mov     [rbp+bstrString], rsi
0x1400030d7  lea     rdx, [rbp+bstrString]
0x1400030db  mov     rax, [rax+68h]
0x1400030df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030e4  mov     ebx, eax
0x1400030e6  test    eax, eax
0x1400030e8  jns     short loc_140003118
0x1400030ea  mov     rcx, [rbp+18h]; this
0x1400030ee  mov     r9d, eax; char *
0x1400030f1  lea     r8, aOnecoreAmcoreS_7; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400030f8  mov     edx, 23h ; '#'; void *
0x1400030fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003102  nop
0x140003103  lea     rcx, [rbp+bstrString]
0x140003107  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000310c  nop
0x14000310d  lea     rcx, [rbp+ppURI]
0x140003111  call    ??1?$com_ptr_t@UIUri@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUri,wil::err_exception_policy>::~com_ptr_t<IUri,wil::err_exception_policy>(void)
0x140003116  jmp     short loc_1400030C1
0x140003118  mov     rdx, [rbp+bstrString]
0x14000311c  xorps   xmm0, xmm0
0x14000311f  movups  [rbp+var_40], xmm0
0x140003123  xorps   xmm1, xmm1
0x140003126  movdqu  [rbp+var_30], xmm1
0x14000312b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000312f  inc     r8
0x140003132  cmp     [rdx+r8*2], si
0x140003137  jnz     short loc_14000312F
0x140003139  lea     rcx, [rbp+var_40]
0x14000313d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140003142  lea     rdx, [rbp+var_40]
0x140003146  mov     rcx, rdi
0x140003149  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000314e  mov     rdx, qword ptr [rbp+var_30+8]
0x140003152  cmp     rdx, 7
0x140003156  jbe     short loc_14000316A
0x140003158  lea     rdx, ds:2[rdx*2]
0x140003160  mov     rcx, qword ptr [rbp+var_40]
0x140003164  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140003169  nop
0x14000316a  mov     rcx, [rbp+bstrString]; bstrString
0x14000316e  test    rcx, rcx
0x140003171  jz      short loc_140003180
0x140003173  call    cs:__imp_SysFreeString
0x14000317a  nop     dword ptr [rax+rax+00h]
0x14000317f  nop
0x140003180  mov     rcx, [rbp+ppURI]
0x140003184  test    rcx, rcx
0x140003187  jz      short loc_140003196
0x140003189  mov     rax, [rcx]
0x14000318c  mov     rax, [rax+10h]
0x140003190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003195  nop
0x140003196  xor     eax, eax
0x140003198  mov     rcx, [rbp+var_10]
0x14000319c  xor     rcx, rsp; StackCookie
0x14000319f  call    __security_check_cookie
0x1400031a4  mov     rbx, [rsp+60h+arg_10]
0x1400031ac  add     rsp, 60h
0x1400031b0  pop     rdi
0x1400031b1  pop     rsi
0x1400031b2  pop     rbp
0x1400031b3  retn
```
