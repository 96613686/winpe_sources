# wil::GetActivationFactory<Windows::Data::Json::IJsonValueStatics>(ushort const *)

- ea: `0x1800208c0`
- end: `0x180020957`
- name: `??$GetActivationFactory@UIJsonValueStatics@Json@Data@Windows@@@wil@@YA?AV?$com_ptr_t@UIJsonValueStatics@Json@Data@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b0c`
- `0x1800060a8`

## callees

- `0x180008320`
- `0x180012420`
- `0x18001a610`
- `0x1800208c0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002091c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002091c`

## string_xrefs

- `0x18002092e`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x1800208e6`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::GetActivationFactory<Windows::Data::Json::IJsonValueStatics>(_QWORD *a1)
{
  __int64 v2; // rax
  int ActivationFactory; // eax
  _QWORD v5[2]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v6; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5[1] = a1;
  v5[0] = L"Windows.Data.Json.JsonValue";
  *a1 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v6, v5);
  ActivationFactory = RoGetActivationFactory(*(_QWORD *)(v2 + 24), &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, a1);
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
0x1800208c0  mov     r11, rsp
0x1800208c3  push    rbx
0x1800208c4  sub     rsp, 60h
0x1800208c8  mov     rax, cs:__security_cookie
0x1800208cf  xor     rax, rsp
0x1800208d2  mov     [rsp+68h+var_10], rax
0x1800208d7  mov     rbx, rcx
0x1800208da  mov     [r11-38h], rcx
0x1800208de  mov     [rsp+68h+var_48], 0
0x1800208e6  lea     rax, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800208ed  mov     [r11-40h], rax
0x1800208f1  mov     [rsp+68h+var_48], 1; int
0x1800208f9  mov     qword ptr [rcx], 0
0x180020900  lea     rdx, [r11-40h]
0x180020904  lea     rcx, [r11-30h]
0x180020908  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002090d  nop
0x18002090e  mov     r8, rbx
0x180020911  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180020918  mov     rcx, [rax+18h]
0x18002091c  call    cs:__imp_RoGetActivationFactory
0x180020922  mov     rcx, [rsp+68h]; this
0x180020927  test    eax, eax
0x180020929  jns     short loc_180020940
0x18002092b  mov     r9d, eax; char *
0x18002092e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020935  mov     edx, 744h; void *
0x18002093a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020940  mov     rax, rbx
0x180020943  mov     rcx, [rsp+68h+var_10]
0x180020948  xor     rcx, rsp; StackCookie
0x18002094b  call    __security_check_cookie
0x180020950  add     rsp, 60h
0x180020954  pop     rbx
0x180020955  retn
```
