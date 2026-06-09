# _anonymous_namespace_::com_settings::GetIids

- ea: `0x14003dce0`
- end: `0x14003dd3f`
- name: `_anonymous_namespace_::com_settings::GetIids`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14003c3c4`
- `0x14003dce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dd02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dd02`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::com_settings::GetIids(__int64 a1, _DWORD *a2, _QWORD *a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14003dce0  mov     [rsp+arg_0], rbx
0x14003dce5  push    rdi
0x14003dce6  sub     rsp, 20h
0x14003dcea  mov     qword ptr [r8], 0
0x14003dcf1  mov     ecx, 20h ; ' '; cb
0x14003dcf6  mov     dword ptr [rdx], 0
0x14003dcfc  mov     rbx, r8
0x14003dcff  mov     rdi, rdx
0x14003dd02  call    cs:__imp_CoTaskMemAlloc
0x14003dd08  mov     r8, rax
0x14003dd0b  test    rax, rax
0x14003dd0e  jnz     short loc_14003DD17
0x14003dd10  mov     eax, 8007000Eh
0x14003dd15  jmp     short loc_14003DD34
0x14003dd17  lea     rdx, [rsp+28h+arg_8]
0x14003dd1c  mov     [rsp+28h+arg_8], 0
0x14003dd24  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIUriReputationSettings@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003dd29  mov     dword ptr [rdi], 2
0x14003dd2f  xor     eax, eax
0x14003dd31  mov     [rbx], r8
0x14003dd34  mov     rbx, [rsp+28h+arg_0]
0x14003dd39  add     rsp, 20h
0x14003dd3d  pop     rdi
0x14003dd3e  retn
```
