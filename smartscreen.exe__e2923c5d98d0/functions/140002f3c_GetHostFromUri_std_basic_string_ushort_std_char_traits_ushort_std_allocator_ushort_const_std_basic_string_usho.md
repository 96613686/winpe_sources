# GetHostFromUri(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140002f3c`
- end: `0x1400030a0`
- name: `?GetHostFromUri@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `356`
- prototype: `__int64 __fastcall(const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003848`

## callees

- `0x140002f3c`
- `0x1400129a4`
- `0x1400160f0`
- `0x140016288`
- `0x140016ce4`
- `0x140018b58`
- `0x14001d914`
- `0x140025aa0`
- `0x140068010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140003065`
- `OLEAUT32!__imp_SysFreeString` at `0x140003065`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x140002f78`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x140002f78`

## string_xrefs

- `0x140002f8b`: `onecore\amcore\smartscreen\src\client\urlrep\src\uri_reputation.cpp`
- `0x140002fe3`: `onecore\amcore\smartscreen\src\client\urlrep\src\uri_reputation.cpp`

## pseudocode

```c
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
0x140002f3c  mov     [rsp-18h+arg_10], rbx
0x140002f41  push    rbp
0x140002f42  push    rsi
0x140002f43  push    rdi
0x140002f44  mov     rbp, rsp
0x140002f47  sub     rsp, 60h
0x140002f4b  mov     rax, cs:__security_cookie
0x140002f52  xor     rax, rsp
0x140002f55  mov     [rbp+var_10], rax
0x140002f59  mov     rdi, rdx
0x140002f5c  xor     esi, esi
0x140002f5e  mov     [rbp+ppURI], rsi
0x140002f62  cmp     qword ptr [rcx+18h], 7
0x140002f67  jbe     short loc_140002F6C
0x140002f69  mov     rcx, [rcx]; pwzURI
0x140002f6c  lea     r9, [rbp+ppURI]; ppURI
0x140002f70  xor     r8d, r8d; dwReserved
0x140002f73  mov     edx, 100h; dwFlags
0x140002f78  call    cs:__imp_CreateUri
0x140002f7e  mov     ebx, eax
0x140002f80  test    eax, eax
0x140002f82  jns     short loc_140002FBA
0x140002f84  mov     rcx, [rbp+18h]; this
0x140002f88  mov     r9d, eax; char *
0x140002f8b  lea     r8, aOnecoreAmcoreS_7; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140002f92  mov     edx, 1Eh; void *
0x140002f97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f9c  nop
0x140002f9d  mov     rcx, [rbp+ppURI]
0x140002fa1  test    rcx, rcx
0x140002fa4  jz      short loc_140002FB3
0x140002fa6  mov     rax, [rcx]
0x140002fa9  mov     rax, [rax+10h]
0x140002fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fb2  nop
0x140002fb3  mov     eax, ebx
0x140002fb5  jmp     loc_140003084
0x140002fba  mov     [rbp+bstrString], rsi
0x140002fbe  mov     rcx, [rbp+ppURI]
0x140002fc2  mov     rax, [rcx]
0x140002fc5  mov     [rbp+bstrString], rsi
0x140002fc9  lea     rdx, [rbp+bstrString]
0x140002fcd  mov     rax, [rax+68h]
0x140002fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fd6  mov     ebx, eax
0x140002fd8  test    eax, eax
0x140002fda  jns     short loc_14000300A
0x140002fdc  mov     rcx, [rbp+18h]; this
0x140002fe0  mov     r9d, eax; char *
0x140002fe3  lea     r8, aOnecoreAmcoreS_7; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140002fea  mov     edx, 23h ; '#'; void *
0x140002fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002ff4  nop
0x140002ff5  lea     rcx, [rbp+bstrString]
0x140002ff9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140002ffe  nop
0x140002fff  lea     rcx, [rbp+ppURI]
0x140003003  call    ??1?$com_ptr_t@UIUri@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUri,wil::err_exception_policy>::~com_ptr_t<IUri,wil::err_exception_policy>(void)
0x140003008  jmp     short loc_140002FB3
0x14000300a  mov     rdx, [rbp+bstrString]
0x14000300e  xorps   xmm0, xmm0
0x140003011  movups  [rbp+var_40], xmm0
0x140003015  xorps   xmm1, xmm1
0x140003018  movdqu  [rbp+var_30], xmm1
0x14000301d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140003021  inc     r8
0x140003024  cmp     [rdx+r8*2], si
0x140003029  jnz     short loc_140003021
0x14000302b  lea     rcx, [rbp+var_40]
0x14000302f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140003034  lea     rdx, [rbp+var_40]
0x140003038  mov     rcx, rdi
0x14000303b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140003040  mov     rdx, qword ptr [rbp+var_30+8]
0x140003044  cmp     rdx, 7
0x140003048  jbe     short loc_14000305C
0x14000304a  lea     rdx, ds:2[rdx*2]
0x140003052  mov     rcx, qword ptr [rbp+var_40]
0x140003056  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000305b  nop
0x14000305c  mov     rcx, [rbp+bstrString]; bstrString
0x140003060  test    rcx, rcx
0x140003063  jz      short loc_14000306C
0x140003065  call    cs:__imp_SysFreeString
0x14000306b  nop
0x14000306c  mov     rcx, [rbp+ppURI]
0x140003070  test    rcx, rcx
0x140003073  jz      short loc_140003082
0x140003075  mov     rax, [rcx]
0x140003078  mov     rax, [rax+10h]
0x14000307c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003081  nop
0x140003082  xor     eax, eax
0x140003084  mov     rcx, [rbp+var_10]
0x140003088  xor     rcx, rsp; StackCookie
0x14000308b  call    __security_check_cookie
0x140003090  mov     rbx, [rsp+60h+arg_10]
0x140003098  add     rsp, 60h
0x14000309c  pop     rdi
0x14000309d  pop     rsi
0x14000309e  pop     rbp
0x14000309f  retn
```
