# DumpErrorInfo(IXMLDOMParseError *,wchar_t const *)

- ea: `0x140029b20`
- end: `0x140029c90`
- name: `?DumpErrorInfo@@YAXPEAUIXMLDOMParseError@@PEB_W@Z`
- size: `368`
- prototype: `void __fastcall(struct IXMLDOMParseError *, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140002c70`

## callees

- `0x14000cabc`
- `0x14000d144`
- `0x14000d868`
- `0x14001159c`
- `0x14001950c`
- `0x14001c438`
- `0x140021b00`
- `0x140029b20`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140029bde`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140029bde`
- `OLEAUT32!__imp_SysStringLen` at `0x140029c08`
- `OLEAUT32!__imp_SysStringLen` at `0x140029c08`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DumpErrorInfo(struct IXMLDOMParseError *a1, const wchar_t *a2)
{
  HRESULT (__stdcall *get_reason)(IXMLDOMParseError *, BSTR *); // rbx
  __int64 v5; // rax
  HANDLE StdHandle; // rdi
  BSTR v7; // rbx
  int v8; // [rsp+20h] [rbp-49h]
  int v9; // [rsp+28h] [rbp-41h]
  UINT v10; // [rsp+30h] [rbp-39h]
  int v11; // [rsp+40h] [rbp-29h] BYREF
  int v12; // [rsp+44h] [rbp-25h] BYREF
  unsigned int v13; // [rsp+48h] [rbp-21h] BYREF
  BSTR pbstr[2]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v15; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v16[16]; // [rsp+70h] [rbp+7h] BYREF
  _OWORD v17[2]; // [rsp+80h] [rbp+17h] BYREF

  v13 = 0;
  if ( ((int (__fastcall *)(struct IXMLDOMParseError *, unsigned int *))a1->lpVtbl->get_line)(a1, &v13) >= 0 )
  {
    v11 = 0;
    if ( ((int (__fastcall *)(struct IXMLDOMParseError *, int *))a1->lpVtbl->get_linepos)(a1, &v11) >= 0 )
    {
      pbstr[0] = 0;
      get_reason = a1->lpVtbl->get_reason;
      v5 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(pbstr);
      if ( ((int (__fastcall *)(struct IXMLDOMParseError *, __int64))get_reason)(a1, v5) >= 0 )
      {
        v12 = 0;
        if ( ((int (__fastcall *)(struct IXMLDOMParseError *, int *))a1->lpVtbl->get_errorCode)(a1, &v12) >= 0 )
        {
          StdHandle = GetStdHandle(0xFFFFFFF4);
          v17[0] = 0;
          v17[1] = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v17[0]) = 0;
          v7 = pbstr[0];
          v10 = SysStringLen(pbstr[0]);
          v9 = v11;
          v8 = v12;
          tlx::assign_sprintf<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
            v17,
            L"%ls(%d): Error 0x%x: At column=%d, %.*ls\n",
            a2,
            v13,
            v8,
            v9,
            v10,
            v7);
          v15 = *(_OWORD *)std::wstring::operator std::wstring_view(v17, v16);
          FilePuts(StdHandle, &v15);
          std::wstring::_Tidy_deallocate(v17);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(pbstr);
    }
  }
}

```

## disassembly

```asm
0x140029b20  mov     [rsp-8+arg_10], rbx
0x140029b25  push    rbp
0x140029b26  push    rsi
0x140029b27  push    rdi
0x140029b28  lea     rbp, [rsp-47h]
0x140029b2d  sub     rsp, 0B0h
0x140029b34  mov     rax, cs:__security_cookie
0x140029b3b  xor     rax, rsp
0x140029b3e  mov     [rbp+57h+var_20], rax
0x140029b42  mov     rsi, rdx
0x140029b45  mov     rdi, rcx
0x140029b48  mov     [rbp+57h+var_78], 0
0x140029b4f  mov     rax, [rcx]
0x140029b52  lea     rdx, [rbp+57h+var_78]
0x140029b56  mov     rax, [rax+58h]
0x140029b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029b5f  test    eax, eax
0x140029b61  js      loc_140029C71
0x140029b67  mov     [rbp+57h+var_80], 0
0x140029b6e  mov     rax, [rdi]
0x140029b71  lea     rdx, [rbp+57h+var_80]
0x140029b75  mov     rcx, rdi
0x140029b78  mov     rax, [rax+60h]
0x140029b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029b81  test    eax, eax
0x140029b83  js      loc_140029C71
0x140029b89  mov     [rbp+57h+pbstr], 0
0x140029b91  mov     rax, [rdi]
0x140029b94  mov     rbx, [rax+48h]
0x140029b98  lea     rcx, [rbp+57h+pbstr]
0x140029b9c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(void)
0x140029ba1  mov     rdx, rax
0x140029ba4  mov     rcx, rdi
0x140029ba7  mov     rax, rbx
0x140029baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029baf  test    eax, eax
0x140029bb1  js      loc_140029C68
0x140029bb7  mov     [rbp+57h+var_7C], 0
0x140029bbe  mov     rax, [rdi]
0x140029bc1  lea     rdx, [rbp+57h+var_7C]
0x140029bc5  mov     rcx, rdi
0x140029bc8  mov     rax, [rax+38h]
0x140029bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029bd1  test    eax, eax
0x140029bd3  js      loc_140029C68
0x140029bd9  mov     ecx, 0FFFFFFF4h; nStdHandle
0x140029bde  call    cs:__imp_GetStdHandle
0x140029be4  mov     rdi, rax
0x140029be7  xorps   xmm0, xmm0
0x140029bea  movups  [rbp+57h+var_40], xmm0
0x140029bee  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140029bf6  movdqu  [rbp+57h+var_30], xmm1
0x140029bfb  xor     ecx, ecx
0x140029bfd  mov     word ptr [rbp+57h+var_40], cx
0x140029c01  mov     rbx, [rbp+57h+pbstr]
0x140029c05  mov     rcx, rbx; pbstr
0x140029c08  call    cs:__imp_SysStringLen
0x140029c0e  mov     [rsp+0C0h+var_88], rbx
0x140029c13  mov     [rsp+0C0h+var_90], eax
0x140029c17  mov     eax, [rbp+57h+var_80]
0x140029c1a  mov     [rsp+0C0h+var_98], eax
0x140029c1e  mov     eax, [rbp+57h+var_7C]
0x140029c21  mov     [rsp+0C0h+var_A0], eax
0x140029c25  mov     r9d, [rbp+57h+var_78]
0x140029c29  mov     r8, rsi
0x140029c2c  lea     rdx, aLsDError0xXAtC; "%ls(%d): Error 0x%x: At column=%d, %.*l"...
0x140029c33  lea     rcx, [rbp+57h+var_40]
0x140029c37  call    ??$assign_sprintf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; tlx::assign_sprintf<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,wchar_t const *,...)
0x140029c3c  lea     rdx, [rbp+57h+var_50]
0x140029c40  lea     rcx, [rbp+57h+var_40]
0x140029c44  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x140029c49  movups  xmm0, xmmword ptr [rax]
0x140029c4c  movdqu  [rbp+57h+var_60], xmm0
0x140029c51  lea     rdx, [rbp+57h+var_60]
0x140029c55  mov     rcx, rdi; hFile
0x140029c58  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x140029c5d  nop
0x140029c5e  lea     rcx, [rbp+57h+var_40]
0x140029c62  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140029c67  nop
0x140029c68  lea     rcx, [rbp+57h+pbstr]
0x140029c6c  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140029c71  mov     rcx, [rbp+57h+var_20]
0x140029c75  xor     rcx, rsp; StackCookie
0x140029c78  call    __security_check_cookie
0x140029c7d  mov     rbx, [rsp+0C0h+arg_10]
0x140029c85  add     rsp, 0B0h
0x140029c8c  pop     rdi
0x140029c8d  pop     rsi
0x140029c8e  pop     rbp
0x140029c8f  retn
```
