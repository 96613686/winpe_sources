# _anonymous_namespace_::com_notification::GetIids

- ea: `0x14003dc70`
- end: `0x14003dccf`
- name: `_anonymous_namespace_::com_notification::GetIids`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003c334`
- `0x14003dc70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dc92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dc92`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::com_notification::GetIids(__int64 a1, _DWORD *a2, _QWORD *a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IPopupButtonInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14003dc70  mov     [rsp+arg_0], rbx
0x14003dc75  push    rdi
0x14003dc76  sub     rsp, 20h
0x14003dc7a  mov     qword ptr [r8], 0
0x14003dc81  mov     ecx, 20h ; ' '; cb
0x14003dc86  mov     dword ptr [rdx], 0
0x14003dc8c  mov     rbx, r8
0x14003dc8f  mov     rdi, rdx
0x14003dc92  call    cs:__imp_CoTaskMemAlloc
0x14003dc98  mov     r8, rax
0x14003dc9b  test    rax, rax
0x14003dc9e  jnz     short loc_14003DCA7
0x14003dca0  mov     eax, 8007000Eh
0x14003dca5  jmp     short loc_14003DCC4
0x14003dca7  lea     rdx, [rsp+28h+arg_8]
0x14003dcac  mov     [rsp+28h+arg_8], 0
0x14003dcb4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIPopupButtonInfo@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IPopupButtonInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003dcb9  mov     dword ptr [rdi], 2
0x14003dcbf  xor     eax, eax
0x14003dcc1  mov     [rbx], r8
0x14003dcc4  mov     rbx, [rsp+28h+arg_0]
0x14003dcc9  add     rsp, 20h
0x14003dccd  pop     rdi
0x14003dcce  retn
```
