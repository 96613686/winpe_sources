# wil::CoCreateInstance<IOneSettingsBroker3,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180013414`
- end: `0x18001347d`
- name: `??$CoCreateInstance@UIOneSettingsBroker3@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIOneSettingsBroker3@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015230`

## callees

- `0x1800101fc`
- `0x180013414`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013450`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013450`

## string_xrefs

- `0x18001346b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IOneSettingsBroker3,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_OneSettingsBroker, 0, 4u, &GUID_563672d1_14f8_4951_b99b_28f117ed8992, a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x180013414  mov     rax, rsp
0x180013417  mov     [rax+8], rcx
0x18001341b  push    rbx
0x18001341c  sub     rsp, 40h
0x180013420  mov     rbx, rcx
0x180013423  mov     dword ptr [rax-18h], 0
0x18001342a  mov     dword ptr [rax-18h], 1
0x180013431  mov     qword ptr [rcx], 0
0x180013438  mov     [rax-28h], rcx
0x18001343c  lea     r9, _GUID_563672d1_14f8_4951_b99b_28f117ed8992; riid
0x180013443  xor     edx, edx; pUnkOuter
0x180013445  lea     r8d, [rdx+4]; dwClsContext
0x180013449  lea     rcx, CLSID_OneSettingsBroker; rclsid
0x180013450  call    cs:__imp_CoCreateInstance
0x180013456  test    eax, eax
0x180013458  js      short loc_180013463
0x18001345a  mov     rax, rbx
0x18001345d  add     rsp, 40h
0x180013461  pop     rbx
0x180013462  retn
0x180013463  mov     rcx, [rsp+48h]; this
0x180013468  mov     r9d, eax; char *
0x18001346b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013472  mov     edx, 1CBEh; void *
0x180013477  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
