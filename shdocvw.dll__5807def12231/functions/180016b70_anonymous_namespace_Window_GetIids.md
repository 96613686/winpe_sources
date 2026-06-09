# _anonymous_namespace_::Window::GetIids

- ea: `0x180016b70`
- end: `0x180016bcf`
- name: `_anonymous_namespace_::Window::GetIids`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015f10`
- `0x180016b70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016b92`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::Window::GetIids(__int64 a1, _DWORD *a2, _QWORD *a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IWindow,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180016b70  mov     [rsp+arg_0], rbx
0x180016b75  push    rdi
0x180016b76  sub     rsp, 20h
0x180016b7a  mov     qword ptr [r8], 0
0x180016b81  mov     ecx, 20h ; ' '; cb
0x180016b86  mov     dword ptr [rdx], 0
0x180016b8c  mov     rbx, r8
0x180016b8f  mov     rdi, rdx
0x180016b92  call    cs:__imp_CoTaskMemAlloc
0x180016b98  mov     r8, rax
0x180016b9b  test    rax, rax
0x180016b9e  jnz     short loc_180016BA7
0x180016ba0  mov     eax, 8007000Eh
0x180016ba5  jmp     short loc_180016BC4
0x180016ba7  lea     rdx, [rsp+28h+arg_8]
0x180016bac  mov     [rsp+28h+arg_8], 0
0x180016bb4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIWindow@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IWindow,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180016bb9  mov     dword ptr [rdi], 2
0x180016bbf  xor     eax, eax
0x180016bc1  mov     [rbx], r8
0x180016bc4  mov     rbx, [rsp+28h+arg_0]
0x180016bc9  add     rsp, 20h
0x180016bcd  pop     rdi
0x180016bce  retn
```
