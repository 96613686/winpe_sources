# wil::CoCreateInstance<IOneSettingsBroker2,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x1800073b0`
- end: `0x18000741a`
- name: `??$CoCreateInstance@UIOneSettingsBroker2@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIOneSettingsBroker2@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `106`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e280`

## callees

- `0x1800073b0`
- `0x1800101fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800073ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800073ec`

## string_xrefs

- `0x1800073fe`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IOneSettingsBroker2,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_OneSettingsBroker, 0, 4u, &GUID_929c6a48_7f12_461b_a223_7517c8f9dd67, a1);
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
0x1800073b0  mov     rax, rsp
0x1800073b3  mov     [rax+8], rcx
0x1800073b7  push    rbx
0x1800073b8  sub     rsp, 40h
0x1800073bc  mov     rbx, rcx
0x1800073bf  mov     dword ptr [rax-18h], 0
0x1800073c6  mov     dword ptr [rax-18h], 1
0x1800073cd  mov     qword ptr [rcx], 0
0x1800073d4  mov     [rax-28h], rcx
0x1800073d8  lea     r9, _GUID_929c6a48_7f12_461b_a223_7517c8f9dd67; riid
0x1800073df  xor     edx, edx; pUnkOuter
0x1800073e1  lea     r8d, [rdx+4]; dwClsContext
0x1800073e5  lea     rcx, CLSID_OneSettingsBroker; rclsid
0x1800073ec  call    cs:__imp_CoCreateInstance
0x1800073f2  test    eax, eax
0x1800073f4  jns     short loc_180007410
0x1800073f6  mov     rcx, [rsp+48h]; this
0x1800073fb  mov     r9d, eax; char *
0x1800073fe  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007405  mov     edx, 1CBEh; void *
0x18000740a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007410  mov     rax, rbx
0x180007413  add     rsp, 40h
0x180007417  pop     rbx
0x180007418  retn
```
