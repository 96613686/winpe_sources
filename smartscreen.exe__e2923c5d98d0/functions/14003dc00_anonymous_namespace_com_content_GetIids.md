# _anonymous_namespace_::com_content::GetIids

- ea: `0x14003dc00`
- end: `0x14003dc5f`
- name: `_anonymous_namespace_::com_content::GetIids`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003c310`
- `0x14003dc00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dc22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dc22`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::com_content::GetIids(__int64 a1, _DWORD *a2, _QWORD *a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IHtmlContentInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14003dc00  mov     [rsp+arg_0], rbx
0x14003dc05  push    rdi
0x14003dc06  sub     rsp, 20h
0x14003dc0a  mov     qword ptr [r8], 0
0x14003dc11  mov     ecx, 20h ; ' '; cb
0x14003dc16  mov     dword ptr [rdx], 0
0x14003dc1c  mov     rbx, r8
0x14003dc1f  mov     rdi, rdx
0x14003dc22  call    cs:__imp_CoTaskMemAlloc
0x14003dc28  mov     r8, rax
0x14003dc2b  test    rax, rax
0x14003dc2e  jnz     short loc_14003DC37
0x14003dc30  mov     eax, 8007000Eh
0x14003dc35  jmp     short loc_14003DC54
0x14003dc37  lea     rdx, [rsp+28h+arg_8]
0x14003dc3c  mov     [rsp+28h+arg_8], 0
0x14003dc44  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIHtmlContentInfo@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IHtmlContentInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003dc49  mov     dword ptr [rdi], 2
0x14003dc4f  xor     eax, eax
0x14003dc51  mov     [rbx], r8
0x14003dc54  mov     rbx, [rsp+28h+arg_0]
0x14003dc59  add     rsp, 20h
0x14003dc5d  pop     rdi
0x14003dc5e  retn
```
