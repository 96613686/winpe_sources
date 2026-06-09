# com::application_reputation_static::GetIids(ulong *,_GUID * *)

- ea: `0x18000b310`
- end: `0x18000b376`
- name: `?GetIids@application_reputation_static@com@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(com::application_reputation_static *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b380`

## callees

- `0x18000b230`
- `0x18000b310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b332`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b332`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::GetIids(
        com::application_reputation_static *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x18000b310  mov     [rsp+arg_0], rbx
0x18000b315  push    rdi
0x18000b316  sub     rsp, 20h
0x18000b31a  mov     qword ptr [r8], 0
0x18000b321  mov     ecx, 20h ; ' '; cb
0x18000b326  mov     dword ptr [rdx], 0
0x18000b32c  mov     rbx, r8
0x18000b32f  mov     rdi, rdx
0x18000b332  call    cs:__imp_CoTaskMemAlloc
0x18000b339  nop     dword ptr [rax+rax+00h]
0x18000b33e  mov     r8, rax
0x18000b341  test    rax, rax
0x18000b344  jnz     short loc_18000B34D
0x18000b346  mov     eax, 8007000Eh
0x18000b34b  jmp     short loc_18000B36A
0x18000b34d  lea     rdx, [rsp+28h+arg_8]
0x18000b352  mov     [rsp+28h+arg_8], 0
0x18000b35a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18000b35f  mov     dword ptr [rdi], 2
0x18000b365  xor     eax, eax
0x18000b367  mov     [rbx], r8
0x18000b36a  mov     rbx, [rsp+28h+arg_0]
0x18000b36f  add     rsp, 20h
0x18000b373  pop     rdi
0x18000b374  retn
```
