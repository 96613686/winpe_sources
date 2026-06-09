# wmi::ContextBase<smapi::IFileShareSchema,smapi::FileShareContext>::Enumerate(wmi::MiFilter const &)

- ea: `0x18003bb04`
- end: `0x18003bcd6`
- name: `?Enumerate@?$ContextBase@UIFileShareSchema@smapi@@VFileShareContext@2@@wmi@@QEAAXAEBVMiFilter@2@@Z`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800397cc`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000e14c`
- `0x18001bd0c`
- `0x18003ad84`
- `0x18003ba94`
- `0x18003bb04`
- `0x18003be40`
- `0x18003c298`
- `0x18003c33c`
- `0x1800443a0`
- `0x180049b04`
- `0x18009b2c4`
- `0x18009b594`
- `0x18009b864`
- `0x18009b94c`
- `0x18009b984`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003bc1c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003bc1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wmi::ContextBase<smapi::IFileShareSchema,smapi::FileShareContext>::Enumerate(__int64 a1, _QWORD *a2)
{
  LPVOID *Parser; // rax
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 Query; // rax
  __int64 v8; // rbx
  char HasProperty; // bl
  __int64 v10; // r8
  LPVOID *v11; // rcx
  const WCHAR *v12; // rax
  __int64 v13; // r8
  __int64 result; // rax
  LPVOID *v15; // rbx
  __int64 v16; // rsi
  __int64 v17; // rdi
  LPVOID *v18; // [rsp+30h] [rbp-40h] BYREF
  LPVOID *v19; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v20[32]; // [rsp+40h] [rbp-30h] BYREF

  v18 = 0;
  if ( !*a2 )
    goto LABEL_11;
  v19 = (LPVOID *)operator new(0x30u);
  Parser = wmi::QueryParser::QueryParser(v19);
  v5 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = Parser;
  if ( v5 )
    std::default_delete<wmi::QueryParser>::operator()();
  v6 = *(_QWORD *)(a1 + 24);
  Query = wmi::MiFilter::GetQuery(a2, v20);
  wmi::QueryParser::Parse(v6, Query);
  std::wstring::_Tidy_deallocate(v20);
  v8 = *(_QWORD *)(a1 + 24);
  if ( !*(_QWORD *)(v8 + 8) )
    goto LABEL_11;
  std::wstring::wstring(v20, L"*");
  HasProperty = wmi::QueryParser::HasProperty(v8, v20);
  std::wstring::_Tidy_deallocate(v20);
  if ( !HasProperty )
  {
    LOBYTE(v10) = 1;
    std::bitset<64>::set(&v18, 0, v10);
    v11 = **(LPVOID ***)wmi::QueryParser::GetQueryFields(*(_QWORD *)(a1 + 24));
    v19 = v11;
    while ( !*((_BYTE *)v11 + 25) )
    {
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v11 + 4);
      if ( CompareStringW(0x400u, 1u, v12, -1, L"ObjectId", -1) == 2 )
      {
        LOBYTE(v13) = 1;
        std::bitset<64>::set(&v18, 0, v13);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v19);
      v11 = v19;
    }
  }
  else
  {
LABEL_11:
    wmi::ContextBase<smapi::IFileShareSchema,smapi::FileShareContext>::set_flags(a1, &v18);
  }
  result = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
  if ( (_BYTE)result )
  {
    v15 = v18;
    do
    {
      v19 = v15;
      wmi::AssociationContextBase<smapi::IFileServerToFileShareSchema,smapi::FileServerToFileShareContext>::create_component_schema_object<1>(
        a1,
        &v18);
      smapi::FileShareContext::PopulateObject(*(_QWORD *)(a1 + 56), &v18, &v19);
      *(_QWORD *)(a1 + 56) += 16LL;
      v16 = *(_QWORD *)(a1 + 56);
      v17 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL);
      wmi::WmiObject<smapi::IFsStorageDepartureEventSchema>::Post(&v18);
      result = std::unique_ptr<Wsp::Facade::IFsStorageEventSubscription>::~unique_ptr<Wsp::Facade::IFsStorageEventSubscription>(&v18);
    }
    while ( v16 != v17 );
  }
  return result;
}

```

## disassembly

```asm
0x18003bb04  mov     [rsp-18h+arg_10], rbx
0x18003bb09  mov     [rsp-18h+arg_18], rsi
0x18003bb0e  push    rbp
0x18003bb0f  push    rdi
0x18003bb10  push    r14
0x18003bb12  mov     rbp, rsp
0x18003bb15  sub     rsp, 70h
0x18003bb19  mov     rax, cs:__security_cookie
0x18003bb20  xor     rax, rsp
0x18003bb23  mov     [rbp+var_10], rax
0x18003bb27  mov     rdi, rdx
0x18003bb2a  mov     r14, rcx
0x18003bb2d  xor     eax, eax
0x18003bb2f  mov     [rbp+var_40], rax
0x18003bb33  xor     esi, esi
0x18003bb35  cmp     [rdx], rsi
0x18003bb38  jz      loc_18003BC4A
0x18003bb3e  lea     ecx, [rax+30h]; Size
0x18003bb41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003bb46  mov     [rbp+var_38], rax
0x18003bb4a  mov     rcx, rax; ppv
0x18003bb4d  call    ??0QueryParser@wmi@@QEAA@XZ; wmi::QueryParser::QueryParser(void)
0x18003bb52  nop
0x18003bb53  mov     rdx, [r14+18h]
0x18003bb57  mov     [r14+18h], rax
0x18003bb5b  test    rdx, rdx
0x18003bb5e  jz      short loc_18003BB65
0x18003bb60  call    ??R?$default_delete@VQueryParser@wmi@@@std@@QEBAXPEAVQueryParser@wmi@@@Z; std::default_delete<wmi::QueryParser>::operator()(wmi::QueryParser *)
0x18003bb65  mov     rbx, [r14+18h]
0x18003bb69  lea     rdx, [rbp+var_30]
0x18003bb6d  mov     rcx, rdi
0x18003bb70  call    ?GetQuery@MiFilter@wmi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; wmi::MiFilter::GetQuery(void)
0x18003bb75  nop
0x18003bb76  mov     rdx, rax
0x18003bb79  mov     rcx, rbx
0x18003bb7c  call    ?Parse@QueryParser@wmi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; wmi::QueryParser::Parse(std::wstring const &)
0x18003bb81  nop
0x18003bb82  lea     rcx, [rbp+var_30]
0x18003bb86  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bb8b  mov     rbx, [r14+18h]
0x18003bb8f  cmp     [rbx+8], rsi
0x18003bb93  jz      loc_18003BC4A
0x18003bb99  lea     rdx, asc_18012F488; "*"
0x18003bba0  lea     rcx, [rbp+var_30]
0x18003bba4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003bba9  nop
0x18003bbaa  lea     rdx, [rbp+var_30]
0x18003bbae  mov     rcx, rbx
0x18003bbb1  call    ?HasProperty@QueryParser@wmi@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; wmi::QueryParser::HasProperty(std::wstring const &)
0x18003bbb6  mov     bl, al
0x18003bbb8  lea     rcx, [rbp+var_30]
0x18003bbbc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bbc1  test    bl, bl
0x18003bbc3  jnz     loc_18003BC4A
0x18003bbc9  mov     r8b, 1
0x18003bbcc  xor     edx, edx
0x18003bbce  lea     rcx, [rbp+var_40]
0x18003bbd2  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18003bbd7  mov     rcx, [r14+18h]
0x18003bbdb  call    ?GetQueryFields@QueryParser@wmi@@QEAAAEBV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitive_LessThan@cxl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; wmi::QueryParser::GetQueryFields(void)
0x18003bbe0  mov     rcx, [rax]
0x18003bbe3  mov     rcx, [rcx]
0x18003bbe6  mov     [rbp+var_38], rcx
0x18003bbea  or      ebx, 0FFFFFFFFh
0x18003bbed  cmp     [rcx+19h], sil
0x18003bbf1  jnz     short loc_18003BC53
0x18003bbf3  add     rcx, 20h ; ' '
0x18003bbf7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003bbfc  mov     [rsp+70h+cchCount2], ebx; cchCount2
0x18003bc00  lea     rcx, aObjectid; "ObjectId"
0x18003bc07  mov     [rsp+70h+lpString2], rcx; lpString2
0x18003bc0c  mov     r9d, ebx; cchCount1
0x18003bc0f  mov     r8, rax; lpString1
0x18003bc12  mov     edx, 1; dwCmpFlags
0x18003bc17  mov     ecx, 400h; Locale
0x18003bc1c  call    cs:__imp_CompareStringW
0x18003bc23  nop     dword ptr [rax+rax+00h]
0x18003bc28  cmp     eax, 2
0x18003bc2b  jnz     short loc_18003BC3B
0x18003bc2d  mov     r8b, 1
0x18003bc30  xor     edx, edx
0x18003bc32  lea     rcx, [rbp+var_40]
0x18003bc36  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18003bc3b  lea     rcx, [rbp+var_38]
0x18003bc3f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18003bc44  mov     rcx, [rbp+var_38]
0x18003bc48  jmp     short loc_18003BBED
0x18003bc4a  lea     rdx, [rbp+var_40]
0x18003bc4e  call    ?set_flags@?$ContextBase@UIFileShareSchema@smapi@@VFileShareContext@2@@wmi@@AEAAXAEAV?$bitset@$0EA@@std@@@Z; wmi::ContextBase<smapi::IFileShareSchema,smapi::FileShareContext>::set_flags(std::bitset<64> &)
0x18003bc53  mov     rax, [r14]
0x18003bc56  mov     rcx, r14
0x18003bc59  mov     rax, [rax]
0x18003bc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc61  test    al, al
0x18003bc63  jz      short loc_18003BCB4
0x18003bc65  mov     rbx, [rbp+var_40]
0x18003bc69  mov     [rbp+var_38], rbx
0x18003bc6d  lea     rdx, [rbp+var_40]
0x18003bc71  mov     rcx, r14
0x18003bc74  call    ??$create_component_schema_object@$00@?$AssociationContextBase@UIFileServerToFileShareSchema@smapi@@VFileServerToFileShareContext@2@@wmi@@AEAA?AV?$WmiObject@UIFileShareSchema@smapi@@@1@XZ; wmi::AssociationContextBase<smapi::IFileServerToFileShareSchema,smapi::FileServerToFileShareContext>::create_component_schema_object<1>(void)
0x18003bc79  nop
0x18003bc7a  lea     r8, [rbp+var_38]
0x18003bc7e  lea     rdx, [rbp+var_40]
0x18003bc82  mov     rcx, [r14+38h]
0x18003bc86  call    ?PopulateObject@FileShareContext@smapi@@SAXAEAV?$shared_ptr@VFileShareFacade@Facade@Wsp@@@std@@AEAV?$WmiObject@UIFileShareSchema@smapi@@@wmi@@AEAV?$bitset@$0EA@@4@@Z; smapi::FileShareContext::PopulateObject(std::shared_ptr<Wsp::Facade::FileShareFacade> &,wmi::WmiObject<smapi::IFileShareSchema> &,std::bitset<64> &)
0x18003bc8b  add     qword ptr [r14+38h], 10h
0x18003bc90  mov     rsi, [r14+38h]
0x18003bc94  mov     rax, [r14+28h]
0x18003bc98  mov     rdi, [rax+8]
0x18003bc9c  lea     rcx, [rbp+var_40]
0x18003bca0  call    ?Post@?$WmiObject@UIFsStorageDepartureEventSchema@smapi@@@wmi@@QEAAXXZ; wmi::WmiObject<smapi::IFsStorageDepartureEventSchema>::Post(void)
0x18003bca5  nop
0x18003bca6  lea     rcx, [rbp+var_40]
0x18003bcaa  call    ??1?$unique_ptr@VIFsStorageEventSubscription@Facade@Wsp@@U?$default_delete@VIFsStorageEventSubscription@Facade@Wsp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Wsp::Facade::IFsStorageEventSubscription>::~unique_ptr<Wsp::Facade::IFsStorageEventSubscription>(void)
0x18003bcaf  cmp     rsi, rdi
0x18003bcb2  jnz     short loc_18003BC69
0x18003bcb4  mov     rcx, [rbp+var_10]
0x18003bcb8  xor     rcx, rsp; StackCookie
0x18003bcbb  call    __security_check_cookie
0x18003bcc0  lea     r11, [rsp+70h+var_s0]
0x18003bcc5  mov     rbx, [r11+30h]
0x18003bcc9  mov     rsi, [r11+38h]
0x18003bccd  mov     rsp, r11
0x18003bcd0  pop     r14
0x18003bcd2  pop     rdi
0x18003bcd3  pop     rbp
0x18003bcd4  retn
```
