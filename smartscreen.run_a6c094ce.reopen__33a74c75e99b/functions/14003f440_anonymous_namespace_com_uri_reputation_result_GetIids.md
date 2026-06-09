# _anonymous_namespace_::com_uri_reputation_result::GetIids

- ea: `0x14003f440`
- end: `0x14003f4a6`
- name: `_anonymous_namespace_::com_uri_reputation_result::GetIids`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003da4c`
- `0x14003f440`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f462`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003f462`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::com_uri_reputation_result::GetIids(__int64 a1, _DWORD *a2, _QWORD *a3)
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
0x14003f440  mov     [rsp+arg_0], rbx
0x14003f445  push    rdi
0x14003f446  sub     rsp, 20h
0x14003f44a  mov     qword ptr [r8], 0
0x14003f451  mov     ecx, 20h ; ' '; cb
0x14003f456  mov     dword ptr [rdx], 0
0x14003f45c  mov     rbx, r8
0x14003f45f  mov     rdi, rdx
0x14003f462  call    cs:__imp_CoTaskMemAlloc
0x14003f469  nop     dword ptr [rax+rax+00h]
0x14003f46e  mov     r8, rax
0x14003f471  test    rax, rax
0x14003f474  jnz     short loc_14003F47D
0x14003f476  mov     eax, 8007000Eh
0x14003f47b  jmp     short loc_14003F49A
0x14003f47d  lea     rdx, [rsp+28h+arg_8]
0x14003f482  mov     [rsp+28h+arg_8], 0
0x14003f48a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationResult,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003f48f  mov     dword ptr [rdi], 2
0x14003f495  xor     eax, eax
0x14003f497  mov     [rbx], r8
0x14003f49a  mov     rbx, [rsp+28h+arg_0]
0x14003f49f  add     rsp, 20h
0x14003f4a3  pop     rdi
0x14003f4a4  retn
```
