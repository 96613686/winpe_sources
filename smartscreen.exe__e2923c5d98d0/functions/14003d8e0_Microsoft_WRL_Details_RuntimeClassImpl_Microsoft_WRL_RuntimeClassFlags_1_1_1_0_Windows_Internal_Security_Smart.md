# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IUriReputationResult,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x14003d8e0`
- end: `0x14003d93f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003c37c`
- `0x14003d8e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003d902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003d902`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IUriReputationResult,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationResult,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x14003d8e0  mov     [rsp+arg_0], rbx
0x14003d8e5  push    rdi
0x14003d8e6  sub     rsp, 20h
0x14003d8ea  mov     qword ptr [r8], 0
0x14003d8f1  mov     ecx, 20h ; ' '; cb
0x14003d8f6  mov     dword ptr [rdx], 0
0x14003d8fc  mov     rbx, r8
0x14003d8ff  mov     rdi, rdx
0x14003d902  call    cs:__imp_CoTaskMemAlloc
0x14003d908  mov     r8, rax
0x14003d90b  test    rax, rax
0x14003d90e  jnz     short loc_14003D917
0x14003d910  mov     eax, 8007000Eh
0x14003d915  jmp     short loc_14003D934
0x14003d917  lea     rdx, [rsp+28h+arg_8]
0x14003d91c  mov     [rsp+28h+arg_8], 0
0x14003d924  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationResult,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003d929  mov     dword ptr [rdi], 2
0x14003d92f  xor     eax, eax
0x14003d931  mov     [rbx], r8
0x14003d934  mov     rbx, [rsp+28h+arg_0]
0x14003d939  add     rsp, 20h
0x14003d93d  pop     rdi
0x14003d93e  retn
```
