# wmi::ContextBase<smapi::IFileShareSchema,smapi::FileShareContext>::Enumerate(wmi::MiFilter const &)

- ea: `0x18003a7a4`
- end: `0x18003a96b`
- name: `?Enumerate@?$ContextBase@UIFileShareSchema@smapi@@VFileShareContext@2@@wmi@@QEAAXAEBVMiFilter@2@@Z`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18003849c`

## callees

- `0x180002a70`
- `0x180002a94`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000dd74`
- `0x18001b28c`
- `0x180039a34`
- `0x18003a73c`
- `0x18003a7a4`
- `0x18003aab0`
- `0x18003af08`
- `0x18003afac`
- `0x180043128`
- `0x180048938`
- `0x180098e70`
- `0x18009913c`
- `0x1800993f4`
- `0x1800994d8`
- `0x180099510`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003a8b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003a8b8`

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
        (__int64)&v18);
      smapi::FileShareContext::PopulateObject(*(__int64 ***)(a1 + 56), &v18, (__int64)&v19);
      *(_QWORD *)(a1 + 56) += 16LL;
      v16 = *(_QWORD *)(a1 + 56);
      v17 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL);
      wmi::WmiObject<smapi::IVolumeToFileShareSchema>::Post(&v18);
      result = std::unique_ptr<Wsp::Facade::IFsStorageEventSubscription>::~unique_ptr<Wsp::Facade::IFsStorageEventSubscription>(&v18);
    }
    while ( v16 != v17 );
  }
  return result;
}

```

## disassembly

```asm
0x18003a7a4  mov     [rsp-18h+arg_10], rbx
0x18003a7a9  mov     [rsp-18h+arg_18], rsi
0x18003a7ae  push    rbp
0x18003a7af  push    rdi
0x18003a7b0  push    r14
0x18003a7b2  mov     rbp, rsp
0x18003a7b5  sub     rsp, 70h
0x18003a7b9  mov     rax, cs:__security_cookie
0x18003a7c0  xor     rax, rsp
0x18003a7c3  mov     [rbp+var_10], rax
0x18003a7c7  mov     rdi, rdx
0x18003a7ca  mov     r14, rcx
0x18003a7cd  xor     eax, eax
0x18003a7cf  mov     [rbp+var_40], rax
0x18003a7d3  xor     esi, esi
0x18003a7d5  cmp     [rdx], rsi
0x18003a7d8  jz      loc_18003A8E0
0x18003a7de  lea     ecx, [rax+30h]; Size
0x18003a7e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a7e6  mov     [rbp+var_38], rax
0x18003a7ea  mov     rcx, rax; ppv
0x18003a7ed  call    ??0QueryParser@wmi@@QEAA@XZ; wmi::QueryParser::QueryParser(void)
0x18003a7f2  nop
0x18003a7f3  mov     rdx, [r14+18h]
0x18003a7f7  mov     [r14+18h], rax
0x18003a7fb  test    rdx, rdx
0x18003a7fe  jz      short loc_18003A805
0x18003a800  call    ??R?$default_delete@VQueryParser@wmi@@@std@@QEBAXPEAVQueryParser@wmi@@@Z; std::default_delete<wmi::QueryParser>::operator()(wmi::QueryParser *)
0x18003a805  mov     rbx, [r14+18h]
0x18003a809  lea     rdx, [rbp+var_30]
0x18003a80d  mov     rcx, rdi
0x18003a810  call    ?GetQuery@MiFilter@wmi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; wmi::MiFilter::GetQuery(void)
0x18003a815  nop
0x18003a816  mov     rdx, rax
0x18003a819  mov     rcx, rbx
0x18003a81c  call    ?Parse@QueryParser@wmi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; wmi::QueryParser::Parse(std::wstring const &)
0x18003a821  nop
0x18003a822  lea     rcx, [rbp+var_30]
0x18003a826  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a82b  mov     rbx, [r14+18h]
0x18003a82f  cmp     [rbx+8], rsi
0x18003a833  jz      loc_18003A8E0
0x18003a839  lea     rdx, asc_18012D478; "*"
0x18003a840  lea     rcx, [rbp+var_30]
0x18003a844  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003a849  nop
0x18003a84a  lea     rdx, [rbp+var_30]
0x18003a84e  mov     rcx, rbx
0x18003a851  call    ?HasProperty@QueryParser@wmi@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; wmi::QueryParser::HasProperty(std::wstring const &)
0x18003a856  mov     bl, al
0x18003a858  lea     rcx, [rbp+var_30]
0x18003a85c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a861  test    bl, bl
0x18003a863  jnz     short loc_18003A8E0
0x18003a865  mov     r8b, 1
0x18003a868  xor     edx, edx
0x18003a86a  lea     rcx, [rbp+var_40]
0x18003a86e  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18003a873  mov     rcx, [r14+18h]
0x18003a877  call    ?GetQueryFields@QueryParser@wmi@@QEAAAEBV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitive_LessThan@cxl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; wmi::QueryParser::GetQueryFields(void)
0x18003a87c  mov     rcx, [rax]
0x18003a87f  mov     rcx, [rcx]
0x18003a882  mov     [rbp+var_38], rcx
0x18003a886  or      ebx, 0FFFFFFFFh
0x18003a889  cmp     [rcx+19h], sil
0x18003a88d  jnz     short loc_18003A8E9
0x18003a88f  add     rcx, 20h ; ' '
0x18003a893  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003a898  mov     [rsp+70h+cchCount2], ebx; cchCount2
0x18003a89c  lea     rcx, aObjectid; "ObjectId"
0x18003a8a3  mov     [rsp+70h+lpString2], rcx; lpString2
0x18003a8a8  mov     r9d, ebx; cchCount1
0x18003a8ab  mov     r8, rax; lpString1
0x18003a8ae  mov     edx, 1; dwCmpFlags
0x18003a8b3  mov     ecx, 400h; Locale
0x18003a8b8  call    cs:__imp_CompareStringW
0x18003a8be  cmp     eax, 2
0x18003a8c1  jnz     short loc_18003A8D1
0x18003a8c3  mov     r8b, 1
0x18003a8c6  xor     edx, edx
0x18003a8c8  lea     rcx, [rbp+var_40]
0x18003a8cc  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18003a8d1  lea     rcx, [rbp+var_38]
0x18003a8d5  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18003a8da  mov     rcx, [rbp+var_38]
0x18003a8de  jmp     short loc_18003A889
0x18003a8e0  lea     rdx, [rbp+var_40]
0x18003a8e4  call    ?set_flags@?$ContextBase@UIFileShareSchema@smapi@@VFileShareContext@2@@wmi@@AEAAXAEAV?$bitset@$0EA@@std@@@Z; wmi::ContextBase<smapi::IFileShareSchema,smapi::FileShareContext>::set_flags(std::bitset<64> &)
0x18003a8e9  mov     rax, [r14]
0x18003a8ec  mov     rcx, r14
0x18003a8ef  mov     rax, [rax]
0x18003a8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8f7  test    al, al
0x18003a8f9  jz      short loc_18003A94A
0x18003a8fb  mov     rbx, [rbp+var_40]
0x18003a8ff  mov     [rbp+var_38], rbx
0x18003a903  lea     rdx, [rbp+var_40]
0x18003a907  mov     rcx, r14
0x18003a90a  call    ??$create_component_schema_object@$00@?$AssociationContextBase@UIFileServerToFileShareSchema@smapi@@VFileServerToFileShareContext@2@@wmi@@AEAA?AV?$WmiObject@UIFileShareSchema@smapi@@@1@XZ; wmi::AssociationContextBase<smapi::IFileServerToFileShareSchema,smapi::FileServerToFileShareContext>::create_component_schema_object<1>(void)
0x18003a90f  nop
0x18003a910  lea     r8, [rbp+var_38]
0x18003a914  lea     rdx, [rbp+var_40]
0x18003a918  mov     rcx, [r14+38h]
0x18003a91c  call    ?PopulateObject@FileShareContext@smapi@@SAXAEAV?$shared_ptr@VFileShareFacade@Facade@Wsp@@@std@@AEAV?$WmiObject@UIFileShareSchema@smapi@@@wmi@@AEAV?$bitset@$0EA@@4@@Z; smapi::FileShareContext::PopulateObject(std::shared_ptr<Wsp::Facade::FileShareFacade> &,wmi::WmiObject<smapi::IFileShareSchema> &,std::bitset<64> &)
0x18003a921  add     qword ptr [r14+38h], 10h
0x18003a926  mov     rsi, [r14+38h]
0x18003a92a  mov     rax, [r14+28h]
0x18003a92e  mov     rdi, [rax+8]
0x18003a932  lea     rcx, [rbp+var_40]
0x18003a936  call    ?Post@?$WmiObject@UIVolumeToFileShareSchema@smapi@@@wmi@@QEAAXXZ; wmi::WmiObject<smapi::IVolumeToFileShareSchema>::Post(void)
0x18003a93b  nop
0x18003a93c  lea     rcx, [rbp+var_40]
0x18003a940  call    ??1?$unique_ptr@VIFsStorageEventSubscription@Facade@Wsp@@U?$default_delete@VIFsStorageEventSubscription@Facade@Wsp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Wsp::Facade::IFsStorageEventSubscription>::~unique_ptr<Wsp::Facade::IFsStorageEventSubscription>(void)
0x18003a945  cmp     rsi, rdi
0x18003a948  jnz     short loc_18003A8FF
0x18003a94a  mov     rcx, [rbp+var_10]
0x18003a94e  xor     rcx, rsp; StackCookie
0x18003a951  call    __security_check_cookie
0x18003a956  lea     r11, [rsp+70h+var_s0]
0x18003a95b  mov     rbx, [r11+30h]
0x18003a95f  mov     rsi, [r11+38h]
0x18003a963  mov     rsp, r11
0x18003a966  pop     r14
0x18003a968  pop     rdi
0x18003a969  pop     rbp
0x18003a96a  retn
```
