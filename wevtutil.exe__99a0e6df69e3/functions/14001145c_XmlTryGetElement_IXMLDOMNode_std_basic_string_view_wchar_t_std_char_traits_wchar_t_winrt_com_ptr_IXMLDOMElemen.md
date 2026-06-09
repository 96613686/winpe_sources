# XmlTryGetElement(IXMLDOMNode *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,winrt::com_ptr<IXMLDOMElement> &)

- ea: `0x14001145c`
- end: `0x140011567`
- name: `?XmlTryGetElement@@YAJPEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU?$com_ptr@UIXMLDOMElement@@@winrt@@@Z`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011320`

## callees

- `0x14001145c`
- `0x140011570`
- `0x14001159c`
- `0x1400128e8`
- `0x140021b00`
- `0x140034010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400114a4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400114a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XmlTryGetElement(__int64 a1, __int64 a2, __int64 *a3)
{
  BSTR v5; // rbx
  unsigned int v6; // ebx
  __int64 v8; // [rsp+20h] [rbp-30h] BYREF
  BSTR v9; // [rsp+28h] [rbp-28h] BYREF
  GUID v10; // [rsp+30h] [rbp-20h] BYREF

  v8 = 0;
  if ( *(_QWORD *)(a2 + 8) && **(_WORD **)a2 )
  {
    v5 = SysAllocStringLen(*(const OLECHAR **)a2, *(_DWORD *)(a2 + 8));
    v9 = v5;
    if ( v5 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)a1 + 296LL))(a1, v5, &v8);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v9);
      if ( !v6 )
      {
        if ( *a3 )
          winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(a3);
        v10 = IID_IXMLDOMElement;
        v6 = *(_DWORD *)winrt::com_ptr<IXMLDOMNode>::as(&v8, &v9, &v10, a3);
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v9);
      v6 = -2147024882;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v8 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v8);
  return v6;
}

```

## disassembly

```asm
0x14001145c  mov     [rsp-28h+arg_18], rbx
0x140011461  push    rbp
0x140011462  push    rsi
0x140011463  push    rdi
0x140011464  push    r14
0x140011466  push    r15
0x140011468  mov     rbp, rsp
0x14001146b  sub     rsp, 50h
0x14001146f  mov     rax, cs:__security_cookie
0x140011476  xor     rax, rsp
0x140011479  mov     [rbp+var_10], rax
0x14001147d  mov     rdi, r8
0x140011480  mov     rsi, rcx
0x140011483  xor     r15d, r15d
0x140011486  mov     [rbp+var_30], r15
0x14001148a  cmp     [rdx+8], r15
0x14001148e  jz      loc_140011531
0x140011494  mov     rcx, [rdx]; strIn
0x140011497  cmp     [rcx], r15w
0x14001149b  jz      loc_140011531
0x1400114a1  mov     edx, [rdx+8]; ui
0x1400114a4  call    cs:__imp_SysAllocStringLen
0x1400114aa  mov     rbx, rax
0x1400114ad  mov     [rbp+var_28], rax
0x1400114b1  test    rax, rax
0x1400114b4  jnz     short loc_1400114C6
0x1400114b6  lea     rcx, [rbp+var_28]
0x1400114ba  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1400114bf  mov     ebx, 8007000Eh
0x1400114c4  jmp     short loc_140011536
0x1400114c6  mov     rax, [rsi]
0x1400114c9  mov     r14, [rax+128h]
0x1400114d0  cmp     [rbp+var_30], r15
0x1400114d4  jz      short loc_1400114DF
0x1400114d6  lea     rcx, [rbp+var_30]
0x1400114da  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x1400114df  lea     r8, [rbp+var_30]
0x1400114e3  mov     rdx, rbx
0x1400114e6  mov     rcx, rsi
0x1400114e9  mov     rax, r14
0x1400114ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114f1  mov     ebx, eax
0x1400114f3  lea     rcx, [rbp+var_28]
0x1400114f7  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1400114fc  test    ebx, ebx
0x1400114fe  jnz     short loc_140011536
0x140011500  cmp     [rdi], r15
0x140011503  jz      short loc_14001150D
0x140011505  mov     rcx, rdi
0x140011508  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x14001150d  movups  xmm0, xmmword ptr cs:IID_IXMLDOMElement.Data1
0x140011514  movdqu  [rbp+var_20], xmm0
0x140011519  mov     r9, rdi
0x14001151c  lea     r8, [rbp+var_20]
0x140011520  lea     rdx, [rbp+var_28]
0x140011524  lea     rcx, [rbp+var_30]
0x140011528  call    ?as@?$com_ptr@UIXMLDOMNode@@@winrt@@QEBA?AUhresult@2@AEBUguid@2@PEAPEAX@Z; winrt::com_ptr<IXMLDOMNode>::as(winrt::guid const &,void * *)
0x14001152d  mov     ebx, [rax]
0x14001152f  jmp     short loc_140011536
0x140011531  mov     ebx, 80070057h
0x140011536  cmp     [rbp+var_30], r15
0x14001153a  jz      short loc_140011545
0x14001153c  lea     rcx, [rbp+var_30]
0x140011540  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140011545  mov     eax, ebx
0x140011547  mov     rcx, [rbp+var_10]
0x14001154b  xor     rcx, rsp; StackCookie
0x14001154e  call    __security_check_cookie
0x140011553  mov     rbx, [rsp+50h+arg_18]
0x14001155b  add     rsp, 50h
0x14001155f  pop     r15
0x140011561  pop     r14
0x140011563  pop     rdi
0x140011564  pop     rsi
0x140011565  pop     rbp
0x140011566  retn
```
