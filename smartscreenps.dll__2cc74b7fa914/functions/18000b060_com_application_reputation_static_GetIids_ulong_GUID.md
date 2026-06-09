# com::application_reputation_static::GetIids(ulong *,_GUID * *)

- ea: `0x18000b060`
- end: `0x18000b0bf`
- name: `?GetIids@application_reputation_static@com@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(com::application_reputation_static *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b0d0`

## callees

- `0x18000af8c`
- `0x18000b060`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b082`

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
0x18000b060  mov     [rsp+arg_0], rbx
0x18000b065  push    rdi
0x18000b066  sub     rsp, 20h
0x18000b06a  mov     qword ptr [r8], 0
0x18000b071  mov     ecx, 20h ; ' '; cb
0x18000b076  mov     dword ptr [rdx], 0
0x18000b07c  mov     rbx, r8
0x18000b07f  mov     rdi, rdx
0x18000b082  call    cs:__imp_CoTaskMemAlloc
0x18000b088  mov     r8, rax
0x18000b08b  test    rax, rax
0x18000b08e  jnz     short loc_18000B097
0x18000b090  mov     eax, 8007000Eh
0x18000b095  jmp     short loc_18000B0B4
0x18000b097  lea     rdx, [rsp+28h+arg_8]
0x18000b09c  mov     [rsp+28h+arg_8], 0
0x18000b0a4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18000b0a9  mov     dword ptr [rdi], 2
0x18000b0af  xor     eax, eax
0x18000b0b1  mov     [rbx], r8
0x18000b0b4  mov     rbx, [rsp+28h+arg_0]
0x18000b0b9  add     rsp, 20h
0x18000b0bd  pop     rdi
0x18000b0be  retn
```
