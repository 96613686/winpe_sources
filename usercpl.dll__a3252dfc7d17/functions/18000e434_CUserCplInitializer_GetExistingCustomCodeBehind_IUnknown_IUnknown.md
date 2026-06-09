# CUserCplInitializer::GetExistingCustomCodeBehind(IUnknown *,IUnknown * *)

- ea: `0x18000e434`
- end: `0x18000e4d1`
- name: `?GetExistingCustomCodeBehind@CUserCplInitializer@@SAJPEAUIUnknown@@PEAPEAU2@@Z`
- size: `157`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e540`
- `0x180024270`

## callees

- `0x18000e434`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000e4ad`
- `OLEAUT32!__imp_VariantClear` at `0x18000e4ad`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18000e48d`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18000e48d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18000e45d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18000e45d`

## pseudocode

```c
__int64 __fastcall CUserCplInitializer::GetExistingCustomCodeBehind(struct IUnknown *a1, struct IUnknown **a2)
{
  HRESULT v3; // ebx
  VARIANT var; // [rsp+20h] [rbp-28h] BYREF
  void *ppvOut; // [rsp+60h] [rbp+18h] BYREF

  ppvOut = 0;
  v3 = IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_PerNamespaceIDPropertyBag,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut);
  if ( v3 >= 0 )
  {
    memset(&var, 0, sizeof(var));
    v3 = PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"UserCplCore", &var, 0xDu);
    if ( v3 >= 0 )
    {
      if ( a2 )
        *a2 = var.punkVal;
      else
        VariantClear(&var);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e434  mov     [rsp+arg_0], rbx
0x18000e439  push    rdi
0x18000e43a  sub     rsp, 40h
0x18000e43e  mov     rdi, rdx
0x18000e441  mov     [rsp+48h+ppvOut], 0
0x18000e44a  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x18000e451  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18000e456  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18000e45d  call    cs:__imp_IUnknown_QueryService
0x18000e463  mov     ebx, eax
0x18000e465  test    eax, eax
0x18000e467  js      short loc_18000E4C4
0x18000e469  mov     rcx, [rsp+48h+ppvOut]; propBag
0x18000e46e  lea     r8, [rsp+48h+var]; var
0x18000e473  xor     eax, eax
0x18000e475  lea     rdx, propName; "UserCplCore"
0x18000e47c  xorps   xmm0, xmm0
0x18000e47f  mov     qword ptr [rsp+48h+var+10h], rax
0x18000e484  movups  xmmword ptr [rsp+48h+var], xmm0
0x18000e489  lea     r9d, [rax+0Dh]; type
0x18000e48d  call    cs:__imp_PSPropertyBag_ReadType
0x18000e493  mov     ebx, eax
0x18000e495  test    eax, eax
0x18000e497  js      short loc_18000E4B3
0x18000e499  test    rdi, rdi
0x18000e49c  jz      short loc_18000E4A8
0x18000e49e  mov     rax, qword ptr [rsp+48h+var+8]
0x18000e4a3  mov     [rdi], rax
0x18000e4a6  jmp     short loc_18000E4B3
0x18000e4a8  lea     rcx, [rsp+48h+var]; pvarg
0x18000e4ad  call    cs:__imp_VariantClear
0x18000e4b3  mov     rcx, [rsp+48h+ppvOut]
0x18000e4b8  mov     rax, [rcx]
0x18000e4bb  mov     rax, [rax+10h]
0x18000e4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4c4  mov     eax, ebx
0x18000e4c6  mov     rbx, [rsp+48h+arg_0]
0x18000e4cb  add     rsp, 40h
0x18000e4cf  pop     rdi
0x18000e4d0  retn
```
