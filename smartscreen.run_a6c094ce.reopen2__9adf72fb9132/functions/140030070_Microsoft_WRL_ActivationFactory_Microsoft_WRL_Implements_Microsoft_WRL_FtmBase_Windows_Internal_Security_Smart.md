# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x140030070`
- end: `0x1400300d6`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400300e0`

## callees

- `0x14002fe80`
- `0x140030070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140030092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140030092`

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
0x140030070  mov     [rsp+arg_0], rbx
0x140030075  push    rdi
0x140030076  sub     rsp, 20h
0x14003007a  mov     qword ptr [r8], 0
0x140030081  mov     ecx, 20h ; ' '; cb
0x140030086  mov     dword ptr [rdx], 0
0x14003008c  mov     rbx, r8
0x14003008f  mov     rdi, rdx
0x140030092  call    cs:__imp_CoTaskMemAlloc
0x140030099  nop     dword ptr [rax+rax+00h]
0x14003009e  mov     r8, rax
0x1400300a1  test    rax, rax
0x1400300a4  jnz     short loc_1400300AD
0x1400300a6  mov     eax, 8007000Eh
0x1400300ab  jmp     short loc_1400300CA
0x1400300ad  lea     rdx, [rsp+28h+arg_8]
0x1400300b2  mov     [rsp+28h+arg_8], 0
0x1400300ba  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x1400300bf  mov     dword ptr [rdi], 2
0x1400300c5  xor     eax, eax
0x1400300c7  mov     [rbx], r8
0x1400300ca  mov     rbx, [rsp+28h+arg_0]
0x1400300cf  add     rsp, 20h
0x1400300d3  pop     rdi
0x1400300d4  retn
```
