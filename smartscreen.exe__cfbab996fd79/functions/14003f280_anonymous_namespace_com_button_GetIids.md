# _anonymous_namespace_::com_button::GetIids

- ea: `0x14003f280`
- end: `0x14003f2e6`
- name: `_anonymous_namespace_::com_button::GetIids`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003d9bc`
- `0x14003f280`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f2a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f2a2`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::com_button::GetIids(__int64 a1, _DWORD *a2, _QWORD *a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IButtonInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14003f280  mov     [rsp+arg_0], rbx
0x14003f285  push    rdi
0x14003f286  sub     rsp, 20h
0x14003f28a  mov     qword ptr [r8], 0
0x14003f291  mov     ecx, 20h ; ' '; cb
0x14003f296  mov     dword ptr [rdx], 0
0x14003f29c  mov     rbx, r8
0x14003f29f  mov     rdi, rdx
0x14003f2a2  call    cs:__imp_CoTaskMemAlloc
0x14003f2a9  nop     dword ptr [rax+rax+00h]
0x14003f2ae  mov     r8, rax
0x14003f2b1  test    rax, rax
0x14003f2b4  jnz     short loc_14003F2BD
0x14003f2b6  mov     eax, 8007000Eh
0x14003f2bb  jmp     short loc_14003F2DA
0x14003f2bd  lea     rdx, [rsp+28h+arg_8]
0x14003f2c2  mov     [rsp+28h+arg_8], 0
0x14003f2ca  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIButtonInfo@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IButtonInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003f2cf  mov     dword ptr [rdi], 2
0x14003f2d5  xor     eax, eax
0x14003f2d7  mov     [rbx], r8
0x14003f2da  mov     rbx, [rsp+28h+arg_0]
0x14003f2df  add     rsp, 20h
0x14003f2e3  pop     rdi
0x14003f2e4  retn
```
