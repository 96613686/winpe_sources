# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x14002edc0`
- end: `0x14002ee1f`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002ee30`

## callees

- `0x14002ebfc`
- `0x14002edc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002ede2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002ede2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x14002edc0  mov     [rsp+arg_0], rbx
0x14002edc5  push    rdi
0x14002edc6  sub     rsp, 20h
0x14002edca  mov     qword ptr [r8], 0
0x14002edd1  mov     ecx, 20h ; ' '; cb
0x14002edd6  mov     dword ptr [rdx], 0
0x14002eddc  mov     rbx, r8
0x14002eddf  mov     rdi, rdx
0x14002ede2  call    cs:__imp_CoTaskMemAlloc
0x14002ede8  mov     r8, rax
0x14002edeb  test    rax, rax
0x14002edee  jnz     short loc_14002EDF7
0x14002edf0  mov     eax, 8007000Eh
0x14002edf5  jmp     short loc_14002EE14
0x14002edf7  lea     rdx, [rsp+28h+arg_8]
0x14002edfc  mov     [rsp+28h+arg_8], 0
0x14002ee04  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x14002ee09  mov     dword ptr [rdi], 2
0x14002ee0f  xor     eax, eax
0x14002ee11  mov     [rbx], r8
0x14002ee14  mov     rbx, [rsp+28h+arg_0]
0x14002ee19  add     rsp, 20h
0x14002ee1d  pop     rdi
0x14002ee1e  retn
```
