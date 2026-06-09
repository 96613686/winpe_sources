# _anonymous_namespace_::com_settings::GetIids

- ea: `0x14003f3d0`
- end: `0x14003f436`
- name: `_anonymous_namespace_::com_settings::GetIids`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14003da94`
- `0x14003f3d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f3f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f3f2`

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
0x14003f3d0  mov     [rsp+arg_0], rbx
0x14003f3d5  push    rdi
0x14003f3d6  sub     rsp, 20h
0x14003f3da  mov     qword ptr [r8], 0
0x14003f3e1  mov     ecx, 20h ; ' '; cb
0x14003f3e6  mov     dword ptr [rdx], 0
0x14003f3ec  mov     rbx, r8
0x14003f3ef  mov     rdi, rdx
0x14003f3f2  call    cs:__imp_CoTaskMemAlloc
0x14003f3f9  nop     dword ptr [rax+rax+00h]
0x14003f3fe  mov     r8, rax
0x14003f401  test    rax, rax
0x14003f404  jnz     short loc_14003F40D
0x14003f406  mov     eax, 8007000Eh
0x14003f40b  jmp     short loc_14003F42A
0x14003f40d  lea     rdx, [rsp+28h+arg_8]
0x14003f412  mov     [rsp+28h+arg_8], 0
0x14003f41a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIUriReputationSettings@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationSettings,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003f41f  mov     dword ptr [rdi], 2
0x14003f425  xor     eax, eax
0x14003f427  mov     [rbx], r8
0x14003f42a  mov     rbx, [rsp+28h+arg_0]
0x14003f42f  add     rsp, 20h
0x14003f433  pop     rdi
0x14003f434  retn
```
