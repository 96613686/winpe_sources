# _anonymous_namespace_::com_content::GetIids

- ea: `0x14003f2f0`
- end: `0x14003f356`
- name: `_anonymous_namespace_::com_content::GetIids`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003d9e0`
- `0x14003f2f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f312`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f312`

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
0x14003f2f0  mov     [rsp+arg_0], rbx
0x14003f2f5  push    rdi
0x14003f2f6  sub     rsp, 20h
0x14003f2fa  mov     qword ptr [r8], 0
0x14003f301  mov     ecx, 20h ; ' '; cb
0x14003f306  mov     dword ptr [rdx], 0
0x14003f30c  mov     rbx, r8
0x14003f30f  mov     rdi, rdx
0x14003f312  call    cs:__imp_CoTaskMemAlloc
0x14003f319  nop     dword ptr [rax+rax+00h]
0x14003f31e  mov     r8, rax
0x14003f321  test    rax, rax
0x14003f324  jnz     short loc_14003F32D
0x14003f326  mov     eax, 8007000Eh
0x14003f32b  jmp     short loc_14003F34A
0x14003f32d  lea     rdx, [rsp+28h+arg_8]
0x14003f332  mov     [rsp+28h+arg_8], 0
0x14003f33a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIHtmlContentInfo@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IHtmlContentInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003f33f  mov     dword ptr [rdi], 2
0x14003f345  xor     eax, eax
0x14003f347  mov     [rbx], r8
0x14003f34a  mov     rbx, [rsp+28h+arg_0]
0x14003f34f  add     rsp, 20h
0x14003f353  pop     rdi
0x14003f354  retn
```
