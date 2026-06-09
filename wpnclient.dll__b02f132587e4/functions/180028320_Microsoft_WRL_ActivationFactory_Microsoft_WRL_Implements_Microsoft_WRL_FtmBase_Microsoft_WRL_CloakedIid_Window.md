# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180028320`
- end: `0x18002837f`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028390`

## callees

- `0x1800282f8`
- `0x180028320`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028342`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028342`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x10u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 1;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180028320  mov     [rsp+arg_0], rbx
0x180028325  push    rdi
0x180028326  sub     rsp, 20h
0x18002832a  mov     qword ptr [r8], 0
0x180028331  mov     ecx, 10h; cb
0x180028336  mov     dword ptr [rdx], 0
0x18002833c  mov     rbx, r8
0x18002833f  mov     rdi, rdx
0x180028342  call    cs:__imp_CoTaskMemAlloc
0x180028348  mov     r8, rax
0x18002834b  test    rax, rax
0x18002834e  jnz     short loc_180028357
0x180028350  mov     eax, 8007000Eh
0x180028355  jmp     short loc_180028374
0x180028357  lea     rdx, [rsp+28h+arg_8]
0x18002835c  mov     [rsp+28h+arg_8], 0
0x180028364  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x180028369  mov     dword ptr [rdi], 1
0x18002836f  xor     eax, eax
0x180028371  mov     [rbx], r8
0x180028374  mov     rbx, [rsp+28h+arg_0]
0x180028379  add     rsp, 20h
0x18002837d  pop     rdi
0x18002837e  retn
```
