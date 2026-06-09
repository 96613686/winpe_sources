# FlightIdUtils::GetCurrentFlightIds(void)

- ea: `0x180022568`
- end: `0x1800226cc`
- name: `?GetCurrentFlightIds@FlightIdUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180022738`

## callees

- `0x180003110`
- `0x180009fcc`
- `0x1800101fc`
- `0x180010278`
- `0x1800148a8`
- `0x180014b08`
- `0x18001a64c`
- `0x180020748`
- `0x180022568`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800225b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800225b2`

## string_xrefs

- `0x1800225c3`: `onecore\base\flighting\common\inc\FlightIdUtility.h`
- `0x180022604`: `onecore\base\flighting\common\inc\FlightIdUtility.h`
- `0x180022648`: `onecore\base\flighting\common\inc\FlightIdUtility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FlightIdUtils::GetCurrentFlightIds(__int64 a1)
{
  HRESULT v2; // eax
  __int64 v3; // rax
  int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  int v9; // [rsp+30h] [rbp-50h] BYREF
  __int64 v10; // [rsp+38h] [rbp-48h] BYREF
  LPVOID v11; // [rsp+40h] [rbp-40h] BYREF
  __int64 v12; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v13[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v12 = a1;
  v11 = 0;
  v2 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v11);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v2,
      ppv);
  v10 = 0;
  v3 = *(_QWORD *)v11;
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(v3 + 32))(v11, &v10);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v4,
      ppv);
  v12 = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v10 + 32LL))(v10, &v12, &v9);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v5,
      ppv);
  std::wstring::wstring(v13);
  if ( v9 )
  {
    std::_WChar_traits<unsigned short>::length(v12);
    std::wstring::_Assign<unsigned short>(v13, v6);
  }
  std::wstring::wstring(a1, v13);
  std::wstring::_Tidy_deallocate(v13);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v10);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v11);
  return a1;
}

```

## disassembly

```asm
0x180022568  mov     [rsp-8+arg_8], rbx
0x18002256d  push    rbp
0x18002256e  mov     rbp, rsp
0x180022571  sub     rsp, 80h
0x180022578  mov     rax, cs:__security_cookie
0x18002257f  xor     rax, rsp
0x180022582  mov     [rbp+var_8], rax
0x180022586  mov     rbx, rcx
0x180022589  mov     [rbp+var_38], rcx
0x18002258d  mov     [rbp+var_40], 0
0x180022595  lea     rax, [rbp+var_40]
0x180022599  mov     qword ptr [rsp+80h+ppv], rax; int
0x18002259e  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x1800225a5  xor     edx, edx; pUnkOuter
0x1800225a7  lea     r8d, [rdx+1]; dwClsContext
0x1800225ab  lea     rcx, CLSID_FlightClientAPI; rclsid
0x1800225b2  call    cs:__imp_CoCreateInstance
0x1800225b8  mov     rcx, [rbp+8]; this
0x1800225bc  test    eax, eax
0x1800225be  jns     short loc_1800225D5
0x1800225c0  mov     r9d, eax; char *
0x1800225c3  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x1800225ca  mov     edx, 7Fh; void *
0x1800225cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800225d5  mov     [rbp+var_48], 0
0x1800225dd  mov     rcx, [rbp+var_40]
0x1800225e1  mov     rax, [rcx]
0x1800225e4  mov     [rbp+var_48], 0
0x1800225ec  lea     rdx, [rbp+var_48]
0x1800225f0  mov     rax, [rax+20h]
0x1800225f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225f9  mov     rcx, [rbp+8]; this
0x1800225fd  test    eax, eax
0x1800225ff  jns     short loc_180022616
0x180022601  mov     r9d, eax; char *
0x180022604  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x18002260b  mov     edx, 82h; void *
0x180022610  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022616  mov     [rbp+var_38], 0
0x18002261e  mov     [rbp+var_50], 0
0x180022625  mov     rcx, [rbp+var_48]
0x180022629  mov     rax, [rcx]
0x18002262c  lea     r8, [rbp+var_50]
0x180022630  lea     rdx, [rbp+var_38]
0x180022634  mov     rax, [rax+20h]
0x180022638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002263d  mov     rcx, [rbp+8]; this
0x180022641  test    eax, eax
0x180022643  jns     short loc_18002265A
0x180022645  mov     r9d, eax; char *
0x180022648  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x18002264f  mov     edx, 86h; void *
0x180022654  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002265a  lea     rcx, [rbp+var_28]
0x18002265e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022663  nop
0x180022664  cmp     [rbp+var_50], 0
0x180022668  jbe     short loc_180022682
0x18002266a  mov     rcx, [rbp+var_38]
0x18002266e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180022673  mov     r8, rax
0x180022676  mov     rdx, rcx
0x180022679  lea     rcx, [rbp+var_28]
0x18002267d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180022682  lea     rdx, [rbp+var_28]
0x180022686  mov     rcx, rbx
0x180022689  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002268e  nop
0x18002268f  lea     rcx, [rbp+var_28]
0x180022693  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022698  nop
0x180022699  lea     rcx, [rbp+var_48]
0x18002269d  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800226a2  nop
0x1800226a3  lea     rcx, [rbp+var_40]
0x1800226a7  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800226ac  mov     rax, rbx
0x1800226af  mov     rcx, [rbp+var_8]
0x1800226b3  xor     rcx, rsp; StackCookie
0x1800226b6  call    __security_check_cookie
0x1800226bb  mov     rbx, [rsp+80h+arg_8]
0x1800226c3  add     rsp, 80h
0x1800226ca  pop     rbp
0x1800226cb  retn
```
