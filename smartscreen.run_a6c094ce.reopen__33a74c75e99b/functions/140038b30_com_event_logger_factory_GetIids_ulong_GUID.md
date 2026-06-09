# com::event_logger_factory::GetIids(ulong *,_GUID * *)

- ea: `0x140038b30`
- end: `0x140038b96`
- name: `?GetIids@event_logger_factory@com@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(com::event_logger_factory *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140038ba0`

## callees

- `0x140038868`
- `0x140038b30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038b52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038b52`

## pseudocode

```c
__int64 __fastcall com::event_logger_factory::GetIids(
        com::event_logger_factory *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IEventLoggerFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x140038b30  mov     [rsp+arg_0], rbx
0x140038b35  push    rdi
0x140038b36  sub     rsp, 20h
0x140038b3a  mov     qword ptr [r8], 0
0x140038b41  mov     ecx, 20h ; ' '; cb
0x140038b46  mov     dword ptr [rdx], 0
0x140038b4c  mov     rbx, r8
0x140038b4f  mov     rdi, rdx
0x140038b52  call    cs:__imp_CoTaskMemAlloc
0x140038b59  nop     dword ptr [rax+rax+00h]
0x140038b5e  mov     r8, rax
0x140038b61  test    rax, rax
0x140038b64  jnz     short loc_140038B6D
0x140038b66  mov     eax, 8007000Eh
0x140038b6b  jmp     short loc_140038B8A
0x140038b6d  lea     rdx, [rsp+28h+arg_8]
0x140038b72  mov     [rsp+28h+arg_8], 0
0x140038b7a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIEventLoggerFactory@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IEventLoggerFactory>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x140038b7f  mov     dword ptr [rdi], 2
0x140038b85  xor     eax, eax
0x140038b87  mov     [rbx], r8
0x140038b8a  mov     rbx, [rsp+28h+arg_0]
0x140038b8f  add     rsp, 20h
0x140038b93  pop     rdi
0x140038b94  retn
```
