# FlightIdUtils::UnregisterFlightId(ushort const *)

- ea: `0x180042964`
- end: `0x1800429f8`
- name: `?UnregisterFlightId@FlightIdUtils@@YAJPEBG@Z`
- size: `148`
- prototype: `__int64 __fastcall(FlightIdUtils *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800425f8`

## callees

- `0x180009fcc`
- `0x18000e5ac`
- `0x180042964`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042997`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042997`

## string_xrefs

- `0x1800429c9`: `onecore\base\flighting\common\inc\FlightIdUtility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FlightIdUtils::UnregisterFlightId(FlightIdUtils *this, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = 0;
  v3 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v9);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, FlightIdUtils *))(*(_QWORD *)v9 + 104LL))(v9, this);
    v4 = v3;
    if ( v3 >= 0 )
    {
      v4 = 0;
      goto LABEL_7;
    }
    v5 = 296;
  }
  else
  {
    v5 = 294;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
    (const char *)(unsigned int)v3,
    v7);
LABEL_7:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v9);
  return v4;
}

```

## disassembly

```asm
0x180042964  mov     r11, rsp
0x180042967  mov     [r11+8], rbx
0x18004296b  push    rdi
0x18004296c  sub     rsp, 30h
0x180042970  mov     rdi, rcx
0x180042973  mov     qword ptr [r11+10h], 0
0x18004297b  lea     rax, [r11+10h]
0x18004297f  mov     [r11-18h], rax
0x180042983  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x18004298a  xor     edx, edx; pUnkOuter
0x18004298c  lea     r8d, [rdx+1]; dwClsContext
0x180042990  lea     rcx, CLSID_FlightClientAPI; rclsid
0x180042997  call    cs:__imp_CoCreateInstance
0x18004299d  mov     ebx, eax
0x18004299f  test    eax, eax
0x1800429a1  jns     short loc_1800429AA
0x1800429a3  mov     edx, 126h
0x1800429a8  jmp     short loc_1800429C9
0x1800429aa  mov     rcx, [rsp+38h+arg_8]
0x1800429af  mov     rax, [rcx]
0x1800429b2  mov     rdx, rdi
0x1800429b5  mov     rax, [rax+68h]
0x1800429b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429be  mov     ebx, eax
0x1800429c0  test    eax, eax
0x1800429c2  jns     short loc_1800429DF
0x1800429c4  mov     edx, 128h; void *
0x1800429c9  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\common\\inc\\"...
0x1800429d0  mov     r9d, eax; char *
0x1800429d3  mov     rcx, [rsp+38h]; this
0x1800429d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800429dd  jmp     short loc_1800429E1
0x1800429df  xor     ebx, ebx
0x1800429e1  lea     rcx, [rsp+38h+arg_8]
0x1800429e6  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800429eb  mov     eax, ebx
0x1800429ed  mov     rbx, [rsp+38h+arg_0]
0x1800429f2  add     rsp, 30h
0x1800429f6  pop     rdi
0x1800429f7  retn
```
