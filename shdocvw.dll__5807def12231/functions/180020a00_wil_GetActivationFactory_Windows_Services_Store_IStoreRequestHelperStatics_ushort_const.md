# wil::GetActivationFactory<Windows::Services::Store::IStoreRequestHelperStatics>(ushort const *)

- ea: `0x180020a00`
- end: `0x180020a97`
- name: `??$GetActivationFactory@UIStoreRequestHelperStatics@Store@Services@Windows@@@wil@@YA?AV?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b0c`
- `0x1800060a8`

## callees

- `0x180008320`
- `0x180012420`
- `0x18001a610`
- `0x180020a00`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020a5c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020a5c`

## string_xrefs

- `0x180020a6e`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180020a26`: `Windows.Services.Store.StoreRequestHelper`

## pseudocode

```c
_QWORD *__fastcall wil::GetActivationFactory<Windows::Services::Store::IStoreRequestHelperStatics>(_QWORD *a1)
{
  __int64 v2; // rax
  int ActivationFactory; // eax
  _QWORD v5[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v6; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5[2] = a1;
  v5[0] = L"Windows.Services.Store.StoreRequestHelper";
  *a1 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v6, v5);
  ActivationFactory = RoGetActivationFactory(*(_QWORD *)(v2 + 24), &GUID_6ce5e5f9_a0c9_4b2c_96a6_a171c630038d, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x744,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x180020a00  mov     r11, rsp
0x180020a03  push    rbx
0x180020a04  sub     rsp, 70h
0x180020a08  mov     rax, cs:__security_cookie
0x180020a0f  xor     rax, rsp
0x180020a12  mov     [rsp+78h+var_10], rax
0x180020a17  mov     rbx, rcx
0x180020a1a  mov     [r11-38h], rcx
0x180020a1e  mov     [rsp+78h+var_58], 0
0x180020a26  lea     rax, ?RuntimeClass_Windows_Services_Store_StoreRequestHelper@@3QBGB; "Windows.Services.Store.StoreRequestHelp"...
0x180020a2d  mov     [r11-48h], rax
0x180020a31  mov     [rsp+78h+var_58], 1; int
0x180020a39  mov     qword ptr [rcx], 0
0x180020a40  lea     rdx, [r11-48h]
0x180020a44  lea     rcx, [r11-30h]
0x180020a48  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020a4d  nop
0x180020a4e  mov     r8, rbx
0x180020a51  lea     rdx, _GUID_6ce5e5f9_a0c9_4b2c_96a6_a171c630038d
0x180020a58  mov     rcx, [rax+18h]
0x180020a5c  call    cs:__imp_RoGetActivationFactory
0x180020a62  mov     rcx, [rsp+78h]; this
0x180020a67  test    eax, eax
0x180020a69  jns     short loc_180020A80
0x180020a6b  mov     r9d, eax; char *
0x180020a6e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020a75  mov     edx, 744h; void *
0x180020a7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020a80  mov     rax, rbx
0x180020a83  mov     rcx, [rsp+78h+var_10]
0x180020a88  xor     rcx, rsp; StackCookie
0x180020a8b  call    __security_check_cookie
0x180020a90  add     rsp, 70h
0x180020a94  pop     rbx
0x180020a95  retn
```
