# WnsProvider::RegisterWNSChannelWithWosc(ushort const *,ushort const *,HSTRING__ *)

- ea: `0x18004e1c0`
- end: `0x18004e45e`
- name: `?RegisterWNSChannelWithWosc@WnsProvider@@CAJPEBG0PEAUHSTRING__@@@Z`
- size: `670`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, HSTRING)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004e144`

## callees

- `0x180003110`
- `0x180003210`
- `0x180009f90`
- `0x18000fe24`
- `0x1800101fc`
- `0x180010278`
- `0x180014928`
- `0x180014b08`
- `0x180019e68`
- `0x18001a128`
- `0x18001a64c`
- `0x180020748`
- `0x180025b28`
- `0x18002dc50`
- `0x180034b9c`
- `0x18004e1c0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004e21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004e21c`

## string_xrefs

- `0x18004e2a0`: `application/json; charset=utf-8`
- `0x18004e2b6`: `application/json; charset=utf-8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall WnsProvider::RegisterWNSChannelWithWosc(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        HSTRING a3)
{
  PCWSTR StringRawBuffer; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rdx
  _DWORD *v9; // rbx
  int v10; // edi
  _QWORD v12[2]; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v13[16]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v14[32]; // [rsp+70h] [rbp-B8h] BYREF
  _BYTE v15[32]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v16[32]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v17[32]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v13);
  std::wstring::wstring(v16);
  std::wstring::append(v16, L"Bearer ");
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  std::wstring::append(v16, StringRawBuffer);
  std::wstring::wstring((__int64)v14, (__int64)L"Authorization");
  v7 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(v13, v12, v14);
  std::wstring::operator=(*v7 + 64LL);
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::wstring((__int64)v14, (__int64)L"Content-Type");
  std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(v13, v12, v14);
  std::_WChar_traits<unsigned short>::length(L"application/json; charset=utf-8");
  std::wstring::_Assign<unsigned short>(*v8 + 64LL, L"application/json; charset=utf-8");
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::wstring((__int64)v15, (__int64)L"\"");
  std::wstring::append(v15, a2);
  std::wstring::append(v15, L"\"");
  v9 = operator new(0x18u);
  v9[2] = 1;
  v9[3] = 1;
  *(_QWORD *)v9 = &std::_Ref_count_obj2<HttpClient>::`vftable';
  *((_QWORD *)v9 + 2) = &HttpClient::`vftable';
  v12[0] = v9 + 4;
  v12[1] = v9;
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  std::wstring::wstring((__int64)v17, (__int64)L"/api/v1/client/channel");
  std::wstring::wstring((__int64)v14, (__int64)a1);
  v10 = ((__int64 (__fastcall *)(_DWORD *, _BYTE *, _BYTE *, _BYTE *))HttpClient::MakeHttpPostRequest)(
          v9 + 4,
          v14,
          v17,
          v13);
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Tidy_deallocate(v17);
  if ( v10 != 200 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
      (const char *)(v10 | 0x80190000),
      0);
  if ( v9 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v9);
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(v16);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v13);
  return 0;
}

```

## disassembly

```asm
0x18004e1c0  push    rbx
0x18004e1c2  push    rsi
0x18004e1c3  push    rdi
0x18004e1c4  push    r14
0x18004e1c6  push    r15
0x18004e1c8  sub     rsp, 100h
0x18004e1cf  mov     rax, cs:__security_cookie
0x18004e1d6  xor     rax, rsp
0x18004e1d9  mov     [rsp+128h+var_38], rax
0x18004e1e1  mov     rbx, r8
0x18004e1e4  mov     rdi, rdx
0x18004e1e7  mov     r15, rcx
0x18004e1ea  lea     rcx, [rsp+128h+var_C8]
0x18004e1ef  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x18004e1f4  nop
0x18004e1f5  lea     rcx, [rsp+128h+var_78]
0x18004e1fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004e202  nop
0x18004e203  lea     rdx, aBearer; "Bearer "
0x18004e20a  lea     rcx, [rsp+128h+var_78]
0x18004e212  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004e217  xor     edx, edx; length
0x18004e219  mov     rcx, rbx; string
0x18004e21c  call    cs:__imp_WindowsGetStringRawBuffer
0x18004e222  mov     rdx, rax
0x18004e225  lea     rcx, [rsp+128h+var_78]
0x18004e22d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004e232  lea     rdx, aAuthorization; "Authorization"
0x18004e239  lea     rcx, [rsp+128h+var_B8]
0x18004e23e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e243  nop
0x18004e244  lea     r8, [rsp+128h+var_B8]
0x18004e249  lea     rdx, [rsp+128h+var_D8]
0x18004e24e  lea     rcx, [rsp+128h+var_C8]
0x18004e253  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18004e258  mov     rcx, [rax]
0x18004e25b  add     rcx, 40h ; '@'
0x18004e25f  lea     rdx, [rsp+128h+var_78]
0x18004e267  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004e26c  nop
0x18004e26d  lea     rcx, [rsp+128h+var_B8]
0x18004e272  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e277  lea     rdx, aContentType; "Content-Type"
0x18004e27e  lea     rcx, [rsp+128h+var_B8]
0x18004e283  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e288  nop
0x18004e289  lea     r8, [rsp+128h+var_B8]
0x18004e28e  lea     rdx, [rsp+128h+var_D8]
0x18004e293  lea     rcx, [rsp+128h+var_C8]
0x18004e298  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18004e29d  mov     rdx, rax
0x18004e2a0  lea     rcx, aApplicationJso; "application/json; charset=utf-8"
0x18004e2a7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004e2ac  mov     r8, rax
0x18004e2af  mov     rcx, [rdx]
0x18004e2b2  add     rcx, 40h ; '@'
0x18004e2b6  lea     rdx, aApplicationJso; "application/json; charset=utf-8"
0x18004e2bd  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004e2c2  nop
0x18004e2c3  lea     rcx, [rsp+128h+var_B8]
0x18004e2c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e2cd  lea     rdx, asc_180064014; "\""
0x18004e2d4  lea     rcx, [rsp+128h+var_98]
0x18004e2dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e2e1  nop
0x18004e2e2  mov     rdx, rdi
0x18004e2e5  lea     rcx, [rsp+128h+var_98]
0x18004e2ed  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004e2f2  lea     rdx, asc_180064014; "\""
0x18004e2f9  lea     rcx, [rsp+128h+var_98]
0x18004e301  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004e306  mov     ecx, 18h; Size
0x18004e30b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e310  mov     rbx, rax
0x18004e313  mov     eax, 1
0x18004e318  mov     [rbx+8], eax
0x18004e31b  mov     [rbx+0Ch], eax
0x18004e31e  lea     rax, ??_7?$_Ref_count_obj2@VHttpClient@@@std@@6B@; const std::_Ref_count_obj2<HttpClient>::`vftable'
0x18004e325  mov     [rbx], rax
0x18004e328  lea     rdi, [rbx+10h]
0x18004e32c  lea     rax, ??_7HttpClient@@6B@; const HttpClient::`vftable'
0x18004e333  mov     [rdi], rax
0x18004e336  mov     [rsp+128h+var_D8], rdi
0x18004e33b  mov     [rsp+128h+var_D0], rbx
0x18004e340  mov     rsi, cs:off_18005BB90
0x18004e347  lea     rcx, [rsp+128h+var_98]
0x18004e34f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004e354  mov     r14, rax
0x18004e357  lea     rdx, aApiV1ClientCha; "/api/v1/client/channel"
0x18004e35e  lea     rcx, [rsp+128h+var_58]
0x18004e366  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e36b  nop
0x18004e36c  mov     rdx, r15
0x18004e36f  lea     rcx, [rsp+128h+var_B8]
0x18004e374  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e379  nop
0x18004e37a  mov     [rsp+128h+var_E8], 0
0x18004e382  mov     [rsp+128h+var_F0], 493E0h
0x18004e38a  mov     [rsp+128h+var_F8], r14
0x18004e38f  mov     [rsp+128h+var_100], 0
0x18004e397  mov     qword ptr [rsp+128h+var_108], 0; int
0x18004e3a0  lea     r9, [rsp+128h+var_C8]
0x18004e3a5  lea     r8, [rsp+128h+var_58]
0x18004e3ad  lea     rdx, [rsp+128h+var_B8]
0x18004e3b2  mov     rcx, rdi
0x18004e3b5  mov     rax, rsi
0x18004e3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3bd  mov     edi, eax
0x18004e3bf  lea     rcx, [rsp+128h+var_B8]
0x18004e3c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e3c9  nop
0x18004e3ca  lea     rcx, [rsp+128h+var_58]
0x18004e3d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e3d7  mov     rcx, [rsp+128h]; this
0x18004e3df  cmp     edi, 0C8h
0x18004e3e5  jz      short loc_18004E402
0x18004e3e7  or      edi, 80190000h
0x18004e3ed  mov     r9d, edi; char *
0x18004e3f0  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004e3f7  mov     edx, 268h; void *
0x18004e3fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e402  test    rbx, rbx
0x18004e405  jz      short loc_18004E410
0x18004e407  mov     rcx, rbx; this
0x18004e40a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004e40f  nop
0x18004e410  lea     rcx, [rsp+128h+var_98]
0x18004e418  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e41d  nop
0x18004e41e  lea     rcx, [rsp+128h+var_78]
0x18004e426  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e42b  nop
0x18004e42c  lea     rcx, [rsp+128h+var_C8]
0x18004e431  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18004e436  xor     eax, eax
0x18004e438  jmp     short loc_18004E43E
0x18004e43a  mov     eax, dword ptr [rsp+128h+var_D8]
0x18004e43e  mov     rcx, [rsp+128h+var_38]
0x18004e446  xor     rcx, rsp; StackCookie
0x18004e449  call    __security_check_cookie
0x18004e44e  add     rsp, 100h
0x18004e455  pop     r15
0x18004e457  pop     r14
0x18004e459  pop     rdi
0x18004e45a  pop     rsi
0x18004e45b  pop     rbx
0x18004e45c  retn
```
