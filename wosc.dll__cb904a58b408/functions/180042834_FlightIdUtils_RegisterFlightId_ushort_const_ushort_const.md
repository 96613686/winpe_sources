# FlightIdUtils::RegisterFlightId(ushort const *,ushort const *)

- ea: `0x180042834`
- end: `0x18004295e`
- name: `?RegisterFlightId@FlightIdUtils@@YAJPEBG0@Z`
- size: `298`
- prototype: `__int64 __fastcall(FlightIdUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800425f8`

## callees

- `0x180009fcc`
- `0x18000e5ac`
- `0x180042834`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004286e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004286e`

## string_xrefs

- `0x180042881`: `onecore\base\flighting\common\inc\FlightIdUtility.h`
- `0x1800428db`: `onecore\base\flighting\common\inc\FlightIdUtility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FlightIdUtils::RegisterFlightId(
        FlightIdUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  int ppv; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF
  LPVOID v14; // [rsp+68h] [rbp+38h] BYREF

  v14 = 0;
  v5 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v14);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v13 = 0;
    v7 = *(_QWORD *)v14;
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, FlightIdUtils *, _QWORD))(v7 + 88))(
           v14,
           a2,
           this,
           0);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v13 + 80LL))(
             v13,
             L"Triggered",
             L"0");
      v6 = v8;
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 88LL))(v13);
        v6 = v8;
        if ( v8 >= 0 )
        {
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v13);
          v6 = 0;
          goto LABEL_11;
        }
        v9 = 286;
      }
      else
      {
        v9 = 284;
      }
    }
    else
    {
      v9 = 282;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v8,
      (int)&v13);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v13);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v5,
      ppv);
  }
LABEL_11:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v14);
  return v6;
}

```

## disassembly

```asm
0x180042834  mov     [rsp-18h+arg_0], rbx
0x180042839  push    rbp
0x18004283a  push    rsi
0x18004283b  push    rdi
0x18004283c  mov     rbp, rsp
0x18004283f  sub     rsp, 30h
0x180042843  mov     rdi, rdx
0x180042846  mov     rsi, rcx
0x180042849  mov     [rbp+arg_18], 0
0x180042851  lea     rax, [rbp+arg_18]
0x180042855  mov     qword ptr [rsp+30h+ppv], rax; int
0x18004285a  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x180042861  xor     edx, edx; pUnkOuter
0x180042863  lea     r8d, [rdx+1]; dwClsContext
0x180042867  lea     rcx, CLSID_FlightClientAPI; rclsid
0x18004286e  call    cs:__imp_CoCreateInstance
0x180042874  mov     ebx, eax
0x180042876  test    eax, eax
0x180042878  jns     short loc_180042897
0x18004287a  mov     rcx, [rbp+18h]; this
0x18004287e  mov     r9d, eax; char *
0x180042881  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x180042888  mov     edx, 117h; void *
0x18004288d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042892  jmp     loc_180042946
0x180042897  mov     [rbp+arg_10], 0
0x18004289f  mov     rcx, [rbp+arg_18]
0x1800428a3  mov     rax, [rcx]
0x1800428a6  mov     [rbp+arg_10], 0
0x1800428ae  lea     rdx, [rbp+arg_10]
0x1800428b2  mov     qword ptr [rsp+30h+ppv], rdx; int
0x1800428b7  xor     r9d, r9d
0x1800428ba  mov     r8, rsi
0x1800428bd  mov     rdx, rdi
0x1800428c0  mov     rax, [rax+58h]
0x1800428c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428c9  mov     ebx, eax
0x1800428cb  test    eax, eax
0x1800428cd  jns     short loc_1800428F3
0x1800428cf  mov     edx, 11Ah; void *
0x1800428d4  mov     rcx, [rbp+18h]; this
0x1800428d8  mov     r9d, eax; char *
0x1800428db  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x1800428e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428e7  nop
0x1800428e8  lea     rcx, [rbp+arg_10]
0x1800428ec  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800428f1  jmp     short loc_180042946
0x1800428f3  mov     rcx, [rbp+arg_10]
0x1800428f7  mov     rax, [rcx]
0x1800428fa  lea     r8, a0; "0"
0x180042901  lea     rdx, aTriggered; "Triggered"
0x180042908  mov     rax, [rax+50h]
0x18004290c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042911  mov     ebx, eax
0x180042913  test    eax, eax
0x180042915  jns     short loc_18004291E
0x180042917  mov     edx, 11Ch
0x18004291c  jmp     short loc_1800428D4
0x18004291e  mov     rcx, [rbp+arg_10]
0x180042922  mov     rax, [rcx]
0x180042925  mov     rax, [rax+58h]
0x180042929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004292e  mov     ebx, eax
0x180042930  test    eax, eax
0x180042932  jns     short loc_18004293B
0x180042934  mov     edx, 11Eh
0x180042939  jmp     short loc_1800428D4
0x18004293b  lea     rcx, [rbp+arg_10]
0x18004293f  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180042944  xor     ebx, ebx
0x180042946  lea     rcx, [rbp+arg_18]
0x18004294a  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004294f  mov     eax, ebx
0x180042951  mov     rbx, [rsp+30h+arg_0]
0x180042956  add     rsp, 30h
0x18004295a  pop     rdi
0x18004295b  pop     rsi
0x18004295c  pop     rbp
0x18004295d  retn
```
