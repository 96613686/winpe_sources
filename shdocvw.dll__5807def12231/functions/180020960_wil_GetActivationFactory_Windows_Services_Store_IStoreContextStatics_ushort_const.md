# wil::GetActivationFactory<Windows::Services::Store::IStoreContextStatics>(ushort const *)

- ea: `0x180020960`
- end: `0x1800209f7`
- name: `??$GetActivationFactory@UIStoreContextStatics@Store@Services@Windows@@@wil@@YA?AV?$com_ptr_t@UIStoreContextStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
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
- `0x180020960`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800209bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800209bc`

## string_xrefs

- `0x1800209ce`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180020986`: `Windows.Services.Store.StoreContext`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::GetActivationFactory<Windows::Services::Store::IStoreContextStatics>(_QWORD *a1)
{
  __int64 v2; // rax
  int ActivationFactory; // eax
  _QWORD v5[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v6; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5[2] = a1;
  v5[0] = L"Windows.Services.Store.StoreContext";
  *a1 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v6, v5);
  ActivationFactory = RoGetActivationFactory(*(_QWORD *)(v2 + 24), &GUID_9c06ee5f_15c0_4e72_9330_d6191cebd19c, a1);
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
0x180020960  mov     r11, rsp
0x180020963  push    rbx
0x180020964  sub     rsp, 70h
0x180020968  mov     rax, cs:__security_cookie
0x18002096f  xor     rax, rsp
0x180020972  mov     [rsp+78h+var_10], rax
0x180020977  mov     rbx, rcx
0x18002097a  mov     [r11-38h], rcx
0x18002097e  mov     [rsp+78h+var_58], 0
0x180020986  lea     rax, ?RuntimeClass_Windows_Services_Store_StoreContext@@3QBGB; "Windows.Services.Store.StoreContext"
0x18002098d  mov     [r11-48h], rax
0x180020991  mov     [rsp+78h+var_58], 1; int
0x180020999  mov     qword ptr [rcx], 0
0x1800209a0  lea     rdx, [r11-48h]
0x1800209a4  lea     rcx, [r11-30h]
0x1800209a8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800209ad  nop
0x1800209ae  mov     r8, rbx
0x1800209b1  lea     rdx, _GUID_9c06ee5f_15c0_4e72_9330_d6191cebd19c
0x1800209b8  mov     rcx, [rax+18h]
0x1800209bc  call    cs:__imp_RoGetActivationFactory
0x1800209c2  mov     rcx, [rsp+78h]; this
0x1800209c7  test    eax, eax
0x1800209c9  jns     short loc_1800209E0
0x1800209cb  mov     r9d, eax; char *
0x1800209ce  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800209d5  mov     edx, 744h; void *
0x1800209da  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800209e0  mov     rax, rbx
0x1800209e3  mov     rcx, [rsp+78h+var_10]
0x1800209e8  xor     rcx, rsp; StackCookie
0x1800209eb  call    __security_check_cookie
0x1800209f0  add     rsp, 70h
0x1800209f4  pop     rbx
0x1800209f5  retn
```
