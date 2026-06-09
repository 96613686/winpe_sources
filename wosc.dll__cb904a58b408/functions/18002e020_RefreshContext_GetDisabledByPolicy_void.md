# RefreshContext::_GetDisabledByPolicy(void)

- ea: `0x18002e020`
- end: `0x18002e109`
- name: `?_GetDisabledByPolicy@RefreshContext@@CA_NXZ`
- size: `233`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002da8c`

## callees

- `0x180009fcc`
- `0x1800101fc`
- `0x18002e020`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e052`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e052`
- `OLEAUT32!__imp_VariantInit` at `0x18002e075`
- `OLEAUT32!__imp_VariantInit` at `0x18002e075`

## string_xrefs

- `0x18002e09f`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`
- `0x18002e0cd`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool RefreshContext::_GetDisabledByPolicy(void)
{
  int v0; // eax
  bool v1; // bl
  int ppv; // [rsp+20h] [rbp-40h]
  __int128 v4; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  LPVOID v7; // [rsp+70h] [rbp+10h] BYREF

  v7 = 0;
  if ( CoCreateInstance(
         &GUID_07369a67_07a6_4608_abea_379491cb7c46,
         0,
         1u,
         &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559,
         &v7) < 0 )
    goto LABEL_8;
  v4 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v0 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v7 + 24LL))(v7, 15, &v4);
  if ( v0 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
      (const char *)(unsigned int)v0,
      ppv);
  if ( DWORD1(v4) == 1 )
  {
    if ( pvarg.vt != 3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD7,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
    v1 = pvarg.lVal == 0;
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v7);
    return v1;
  }
  else
  {
LABEL_8:
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v7);
    return 0;
  }
}

```

## disassembly

```asm
0x18002e020  mov     [rsp-8+arg_8], rbx
0x18002e025  push    rbp
0x18002e026  mov     rbp, rsp
0x18002e029  sub     rsp, 60h
0x18002e02d  mov     [rbp+arg_0], 0
0x18002e035  lea     rax, [rbp+arg_0]
0x18002e039  mov     qword ptr [rsp+60h+ppv], rax; int
0x18002e03e  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x18002e045  xor     edx, edx; pUnkOuter
0x18002e047  lea     r8d, [rdx+1]; dwClsContext
0x18002e04b  lea     rcx, _GUID_07369a67_07a6_4608_abea_379491cb7c46; rclsid
0x18002e052  call    cs:__imp_CoCreateInstance
0x18002e058  test    eax, eax
0x18002e05a  js      loc_18002E0F3
0x18002e060  xorps   xmm0, xmm0
0x18002e063  xor     eax, eax
0x18002e065  movups  [rbp+var_30], xmm0
0x18002e069  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002e06d  mov     qword ptr [rbp+pvarg+10h], rax
0x18002e071  lea     rcx, [rbp+pvarg]; pvarg
0x18002e075  call    cs:__imp_VariantInit
0x18002e07b  mov     rcx, [rbp+arg_0]
0x18002e07f  mov     rax, [rcx]
0x18002e082  lea     r8, [rbp+var_30]
0x18002e086  mov     edx, 0Fh
0x18002e08b  mov     rax, [rax+18h]
0x18002e08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e094  mov     rcx, [rbp+8]; this
0x18002e098  test    eax, eax
0x18002e09a  jns     short loc_18002E0B1
0x18002e09c  mov     r9d, eax; char *
0x18002e09f  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002e0a6  mov     edx, 0D0h; void *
0x18002e0ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e0b1  cmp     dword ptr [rbp+var_30+4], 1
0x18002e0b5  jnz     short loc_18002E0F3
0x18002e0b7  cmp     word ptr [rbp+pvarg], 3
0x18002e0bc  setz    al
0x18002e0bf  mov     rcx, [rbp+8]; this
0x18002e0c3  test    al, al
0x18002e0c5  jnz     short loc_18002E0DF
0x18002e0c7  mov     r9d, 8000FFFFh; char *
0x18002e0cd  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002e0d4  mov     edx, 0D7h; void *
0x18002e0d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e0df  cmp     dword ptr [rbp+pvarg+8], 0
0x18002e0e3  setz    bl
0x18002e0e6  lea     rcx, [rbp+arg_0]
0x18002e0ea  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18002e0ef  mov     al, bl
0x18002e0f1  jmp     short loc_18002E0FE
0x18002e0f3  lea     rcx, [rbp+arg_0]
0x18002e0f7  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18002e0fc  xor     al, al
0x18002e0fe  mov     rbx, [rsp+60h+arg_8]
0x18002e103  add     rsp, 60h
0x18002e107  pop     rbp
0x18002e108  retn
```
