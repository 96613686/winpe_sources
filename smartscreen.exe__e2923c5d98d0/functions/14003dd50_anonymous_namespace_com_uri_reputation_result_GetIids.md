# _anonymous_namespace_::com_uri_reputation_result::GetIids

- ea: `0x14003dd50`
- end: `0x14003ddaf`
- name: `_anonymous_namespace_::com_uri_reputation_result::GetIids`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003c37c`
- `0x14003dd50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dd72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dd72`

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
0x14003dd50  mov     [rsp+arg_0], rbx
0x14003dd55  push    rdi
0x14003dd56  sub     rsp, 20h
0x14003dd5a  mov     qword ptr [r8], 0
0x14003dd61  mov     ecx, 20h ; ' '; cb
0x14003dd66  mov     dword ptr [rdx], 0
0x14003dd6c  mov     rbx, r8
0x14003dd6f  mov     rdi, rdx
0x14003dd72  call    cs:__imp_CoTaskMemAlloc
0x14003dd78  mov     r8, rax
0x14003dd7b  test    rax, rax
0x14003dd7e  jnz     short loc_14003DD87
0x14003dd80  mov     eax, 8007000Eh
0x14003dd85  jmp     short loc_14003DDA4
0x14003dd87  lea     rdx, [rsp+28h+arg_8]
0x14003dd8c  mov     [rsp+28h+arg_8], 0
0x14003dd94  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IUriReputationResult,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003dd99  mov     dword ptr [rdi], 2
0x14003dd9f  xor     eax, eax
0x14003dda1  mov     [rbx], r8
0x14003dda4  mov     rbx, [rsp+28h+arg_0]
0x14003dda9  add     rsp, 20h
0x14003ddad  pop     rdi
0x14003ddae  retn
```
