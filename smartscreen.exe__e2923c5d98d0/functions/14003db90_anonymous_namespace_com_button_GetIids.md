# _anonymous_namespace_::com_button::GetIids

- ea: `0x14003db90`
- end: `0x14003dbef`
- name: `_anonymous_namespace_::com_button::GetIids`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003c2ec`
- `0x14003db90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dbb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003dbb2`

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
0x14003db90  mov     [rsp+arg_0], rbx
0x14003db95  push    rdi
0x14003db96  sub     rsp, 20h
0x14003db9a  mov     qword ptr [r8], 0
0x14003dba1  mov     ecx, 20h ; ' '; cb
0x14003dba6  mov     dword ptr [rdx], 0
0x14003dbac  mov     rbx, r8
0x14003dbaf  mov     rdi, rdx
0x14003dbb2  call    cs:__imp_CoTaskMemAlloc
0x14003dbb8  mov     r8, rax
0x14003dbbb  test    rax, rax
0x14003dbbe  jnz     short loc_14003DBC7
0x14003dbc0  mov     eax, 8007000Eh
0x14003dbc5  jmp     short loc_14003DBE4
0x14003dbc7  lea     rdx, [rsp+28h+arg_8]
0x14003dbcc  mov     [rsp+28h+arg_8], 0
0x14003dbd4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIButtonInfo@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IButtonInfo,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14003dbd9  mov     dword ptr [rdi], 2
0x14003dbdf  xor     eax, eax
0x14003dbe1  mov     [rbx], r8
0x14003dbe4  mov     rbx, [rsp+28h+arg_0]
0x14003dbe9  add     rsp, 20h
0x14003dbed  pop     rdi
0x14003dbee  retn
```
