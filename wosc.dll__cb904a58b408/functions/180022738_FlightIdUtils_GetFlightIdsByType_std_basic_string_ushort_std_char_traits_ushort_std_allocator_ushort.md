# FlightIdUtils::GetFlightIdsByType(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180022738`
- end: `0x180022a84`
- name: `?GetFlightIdsByType@FlightIdUtils@@YA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `844`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180022a8c`
- `0x1800425f8`

## callees

- `0x180003110`
- `0x18000843c`
- `0x180009fcc`
- `0x180010130`
- `0x1800101fc`
- `0x180010278`
- `0x1800146a8`
- `0x180019e68`
- `0x18001a64c`
- `0x180020608`
- `0x180020a00`
- `0x180020a38`
- `0x180021a84`
- `0x180021ad8`
- `0x180021c88`
- `0x180022568`
- `0x1800226e4`
- `0x180022738`
- `0x180023008`
- `0x180024550`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022799`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022799`

## string_xrefs

- `0x1800227ae`: `onecore\base\flighting\common\inc\FlightIdUtility.h`
- `0x1800228b3`: `onecore\base\flighting\common\inc\FlightIdUtility.h`
- `0x18002293b`: `onecore\base\flighting\common\inc\FlightIdUtility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FlightIdUtils::GetFlightIdsByType(__int64 a1, __int64 a2)
{
  __int64 v2; // r13
  __int64 v3; // r15
  HRESULT v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  void *v7; // rcx
  char *v8; // r14
  char *v9; // rdx
  char *v10; // r12
  __int64 v11; // rcx
  bool v12; // bl
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64, __int64, __int64 *); // r9
  __int64 v15; // r10
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  const char *v22; // r9
  int ppv; // [rsp+20h] [rbp-118h]
  __int64 v25; // [rsp+30h] [rbp-108h] BYREF
  LPVOID v26; // [rsp+38h] [rbp-100h] BYREF
  char *v27; // [rsp+40h] [rbp-F8h]
  char *v28; // [rsp+48h] [rbp-F0h] BYREF
  char *v29; // [rsp+50h] [rbp-E8h]
  __int64 v30; // [rsp+58h] [rbp-E0h]
  char *v31; // [rsp+68h] [rbp-D0h]
  __int64 v32; // [rsp+70h] [rbp-C8h]
  _BYTE v33[16]; // [rsp+78h] [rbp-C0h] BYREF
  char v34[8]; // [rsp+88h] [rbp-B0h] BYREF
  char v35[16]; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-98h]
  __int64 v37; // [rsp+A8h] [rbp-90h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-88h]
  __int64 v39; // [rsp+B8h] [rbp-80h]
  _BYTE v40[16]; // [rsp+C8h] [rbp-70h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-60h]
  _BYTE v42[32]; // [rsp+E8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v2 = a2;
  v3 = a1;
  v32 = a1;
  v36 = a2;
  v26 = 0;
  v4 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v26);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v4,
      ppv);
  std::set<std::wstring>::set<std::wstring>(v33, v5, v6);
  FlightIdUtils::GetCurrentFlightIds(v40);
  if ( v41 )
  {
    FlightIdUtils::Split<unsigned short>(&v28, v40);
    v7 = v28;
    v8 = v28;
    v9 = v29;
    v10 = v29;
    v31 = v29;
    while ( 1 )
    {
      v27 = v8;
      if ( v8 == v10 )
        break;
      FlightIdUtils::GetFlightIdNamespace(&v37, v8);
      v12 = *(_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                         v11,
                         v34,
                         &v37) != qword_180075FA8;
      std::wstring::_Tidy_deallocate(&v37);
      if ( !v12 )
      {
        try
        {
          v25 = 0;
          v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
          v16 = v14(v15, v13, &v25);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xAF,
              (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
              (const char *)(unsigned int)v16,
              ppv);
          v37 = 0;
          v38 = 0;
          v39 = 0;
          v17 = v25;
          v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 40LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
          v38 = -1;
          v39 = -1;
          v19 = v18(v17, &v37);
          if ( v19 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xB2,
              (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
              (const char *)(unsigned int)v19,
              ppv);
          std::_WChar_traits<unsigned short>::length(v37);
          v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2);
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v20, *(_QWORD *)(v2 + 16)) )
          {
            v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
            FlightIdUtils::NormalizeFlightId(v42, v21);
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(
              v33,
              v35,
              v42);
            std::wstring::_Tidy_deallocate(v42);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v25);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0xBA,
            (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
            v22);
          v8 = v27;
          v10 = v31;
          v3 = v32;
          v2 = v36;
        }
      }
      v8 += 32;
      v9 = v29;
      v7 = v28;
    }
    if ( v7 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v7, v9);
      std::_Deallocate<16>(v28, (v30 - (_QWORD)v28) & 0xFFFFFFFFFFFFFFE0uLL);
    }
  }
  std::set<std::wstring>::set<std::wstring>(v3, v33);
  std::wstring::_Tidy_deallocate(v40);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v33);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v26);
  std::wstring::_Tidy_deallocate(v2);
  return v3;
}

```

## disassembly

```asm
0x180022738  mov     [rsp+arg_10], rbx
0x18002273d  push    rdi
0x18002273e  push    r12
0x180022740  push    r13
0x180022742  push    r14
0x180022744  push    r15
0x180022746  sub     rsp, 110h
0x18002274d  mov     rax, cs:__security_cookie
0x180022754  xor     rax, rsp
0x180022757  mov     [rsp+138h+var_30], rax
0x18002275f  mov     r13, rdx
0x180022762  mov     r15, rcx
0x180022765  mov     [rsp+138h+var_C8], rcx
0x18002276a  mov     [rsp+138h+var_98], rdx
0x180022772  mov     [rsp+138h+var_100], 0
0x18002277b  lea     rax, [rsp+138h+var_100]
0x180022780  mov     qword ptr [rsp+138h+ppv], rax; int
0x180022785  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x18002278c  xor     edx, edx; pUnkOuter
0x18002278e  lea     r8d, [rdx+1]; dwClsContext
0x180022792  lea     rcx, CLSID_FlightClientAPI; rclsid
0x180022799  call    cs:__imp_CoCreateInstance
0x18002279f  mov     rcx, [rsp+138h]; this
0x1800227a7  test    eax, eax
0x1800227a9  jns     short loc_1800227C0
0x1800227ab  mov     r9d, eax; char *
0x1800227ae  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x1800227b5  mov     edx, 0A0h; void *
0x1800227ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800227c0  lea     rcx, [rsp+138h+var_C0]
0x1800227c5  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800227ca  nop
0x1800227cb  lea     rcx, [rsp+138h+var_70]
0x1800227d3  call    ?GetCurrentFlightIds@FlightIdUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FlightIdUtils::GetCurrentFlightIds(void)
0x1800227d8  nop
0x1800227d9  cmp     [rsp+138h+var_60], 0
0x1800227e2  jz      loc_180022A1E
0x1800227e8  lea     rdx, [rsp+138h+var_70]
0x1800227f0  lea     rcx, [rsp+138h+var_F0]
0x1800227f5  call    ??$Split@G@FlightIdUtils@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@G@Z; FlightIdUtils::Split<ushort>(std::wstring const &,ushort)
0x1800227fa  nop
0x1800227fb  mov     rcx, [rsp+138h+var_F0]
0x180022800  mov     r14, rcx
0x180022803  mov     rdx, [rsp+138h+var_E8]
0x180022808  mov     r12, rdx
0x18002280b  mov     [rsp+138h+var_D0], rdx
0x180022810  mov     [rsp+138h+var_F8], r14
0x180022815  cmp     r14, r12
0x180022818  jz      loc_1800229FE
0x18002281e  mov     rdx, r14
0x180022821  lea     rcx, [rsp+138h+var_90]
0x180022829  call    ?GetFlightIdNamespace@FlightIdUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; FlightIdUtils::GetFlightIdNamespace(std::wstring const &)
0x18002282e  lea     r8, [rsp+138h+var_90]
0x180022836  lea     rdx, [rsp+138h+var_B0]
0x18002283e  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180022843  mov     rcx, rax
0x180022846  mov     rax, cs:qword_180075FA8
0x18002284d  cmp     [rcx], rax
0x180022850  setnz   bl
0x180022853  lea     rcx, [rsp+138h+var_90]
0x18002285b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022860  test    bl, bl
0x180022862  jnz     loc_1800229EB
0x180022868  mov     [rsp+138h+var_108], 0
0x180022871  mov     r10, [rsp+138h+var_100]
0x180022876  mov     rax, [r10]
0x180022879  mov     r9, [rax+88h]
0x180022880  mov     [rsp+138h+var_108], 0
0x180022889  mov     rcx, r14
0x18002288c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022891  lea     r8, [rsp+138h+var_108]
0x180022896  mov     rdx, rax
0x180022899  mov     rcx, r10
0x18002289c  mov     rax, r9
0x18002289f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228a4  mov     rcx, [rsp+138h]; this
0x1800228ac  test    eax, eax
0x1800228ae  jns     short loc_1800228C4
0x1800228b0  mov     r9d, eax; char *
0x1800228b3  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x1800228ba  mov     edx, 0AFh; void *
0x1800228bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800228c4  mov     [rsp+138h+var_90], 0
0x1800228d0  mov     [rsp+138h+var_88], 0
0x1800228dc  mov     [rsp+138h+var_80], 0
0x1800228e8  mov     rdi, [rsp+138h+var_108]
0x1800228ed  mov     rax, [rdi]
0x1800228f0  mov     rbx, [rax+28h]
0x1800228f4  lea     rcx, [rsp+138h+var_90]
0x1800228fc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180022901  mov     [rsp+138h+var_88], 0FFFFFFFFFFFFFFFFh
0x18002290d  mov     [rsp+138h+var_80], 0FFFFFFFFFFFFFFFFh
0x180022919  lea     rdx, [rsp+138h+var_90]
0x180022921  mov     rcx, rdi
0x180022924  mov     rax, rbx
0x180022927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002292c  mov     rcx, [rsp+138h]; this
0x180022934  test    eax, eax
0x180022936  jns     short loc_18002294C
0x180022938  mov     r9d, eax; char *
0x18002293b  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x180022942  mov     edx, 0B2h; void *
0x180022947  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002294c  mov     r8, [rsp+138h+var_90]
0x180022954  mov     rcx, r8
0x180022957  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002295c  mov     r9, rax
0x18002295f  mov     rcx, r13
0x180022962  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022967  mov     rdx, [r13+10h]
0x18002296b  mov     rcx, rax
0x18002296e  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180022973  test    al, al
0x180022975  jz      short loc_1800229B9
0x180022977  mov     rcx, r14
0x18002297a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002297f  mov     rdx, rax
0x180022982  lea     rcx, [rsp+138h+var_50]
0x18002298a  call    ?NormalizeFlightId@FlightIdUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_N@Z; FlightIdUtils::NormalizeFlightId(ushort const *,bool)
0x18002298f  nop
0x180022990  lea     r8, [rsp+138h+var_50]
0x180022998  lea     rdx, [rsp+138h+var_A8]
0x1800229a0  lea     rcx, [rsp+138h+var_C0]
0x1800229a5  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(std::wstring const &)
0x1800229aa  nop
0x1800229ab  lea     rcx, [rsp+138h+var_50]
0x1800229b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800229b8  nop
0x1800229b9  lea     rcx, [rsp+138h+var_90]
0x1800229c1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800229c6  nop
0x1800229c7  lea     rcx, [rsp+138h+var_108]
0x1800229cc  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800229d1  nop
0x1800229d2  jmp     short loc_1800229EB
0x1800229d4  mov     r14, [rsp+138h+var_F8]
0x1800229d9  mov     r12, [rsp+138h+var_D0]
0x1800229de  mov     r15, [rsp+138h+var_C8]
0x1800229e3  mov     r13, [rsp+138h+var_98]
0x1800229eb  add     r14, 20h ; ' '
0x1800229ef  mov     rdx, [rsp+138h+var_E8]
0x1800229f4  mov     rcx, [rsp+138h+var_F0]
0x1800229f9  jmp     loc_180022810
0x1800229fe  test    rcx, rcx
0x180022a01  jz      short loc_180022A1E
0x180022a03  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180022a08  mov     rcx, [rsp+138h+var_F0]
0x180022a0d  mov     rdx, [rsp+138h+var_E0]
0x180022a12  sub     rdx, rcx
0x180022a15  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180022a19  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180022a1e  lea     rdx, [rsp+138h+var_C0]
0x180022a23  mov     rcx, r15
0x180022a26  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::set<std::wstring>::set<std::wstring>(std::set<std::wstring> &&)
0x180022a2b  nop
0x180022a2c  lea     rcx, [rsp+138h+var_70]
0x180022a34  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022a39  nop
0x180022a3a  lea     rcx, [rsp+138h+var_C0]
0x180022a3f  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180022a44  nop
0x180022a45  lea     rcx, [rsp+138h+var_100]
0x180022a4a  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180022a4f  nop
0x180022a50  mov     rcx, r13
0x180022a53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022a58  mov     rax, r15
0x180022a5b  mov     rcx, [rsp+138h+var_30]
0x180022a63  xor     rcx, rsp; StackCookie
0x180022a66  call    __security_check_cookie
0x180022a6b  mov     rbx, [rsp+138h+arg_10]
0x180022a73  add     rsp, 110h
0x180022a7a  pop     r15
0x180022a7c  pop     r14
0x180022a7e  pop     r13
0x180022a80  pop     r12
0x180022a82  pop     rdi
0x180022a83  retn
```
