# Windows::Internal::Notifications::CToastActivatorSwitch::GetIids(ulong *,_GUID * *)

- ea: `0x1800259b0`
- end: `0x180025a1a`
- name: `?GetIids@CToastActivatorSwitch@Notifications@Internal@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivatorSwitch *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025a20`

## callees

- `0x180025970`
- `0x1800259b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800259d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800259d2`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CToastActivatorSwitch::GetIids(
        Windows::Internal::Notifications::CToastActivatorSwitch *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,Windows::Internal::Notifications::IWpnToastActivator>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800259b0  mov     [rsp+arg_0], rbx
0x1800259b5  push    rdi
0x1800259b6  sub     rsp, 20h
0x1800259ba  mov     qword ptr [r8], 0
0x1800259c1  mov     ecx, 30h ; '0'; cb
0x1800259c6  mov     dword ptr [rdx], 0
0x1800259cc  mov     rbx, r8
0x1800259cf  mov     rdi, rdx
0x1800259d2  call    cs:__imp_CoTaskMemAlloc
0x1800259d8  mov     r8, rax
0x1800259db  test    rax, rax
0x1800259de  jnz     short loc_1800259E7
0x1800259e0  mov     eax, 8007000Eh
0x1800259e5  jmp     short loc_180025A0F
0x1800259e7  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x1800259ee  lea     rdx, [rsp+28h+arg_8]
0x1800259f3  mov     [rsp+28h+arg_8], 1
0x1800259fb  movdqu  xmmword ptr [rax], xmm0
0x1800259ff  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIWpnToastActivator@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,Windows::Internal::Notifications::IWpnToastActivator>::FillArrayWithIid(ulong *,_GUID *)
0x180025a04  mov     dword ptr [rdi], 3
0x180025a0a  xor     eax, eax
0x180025a0c  mov     [rbx], r8
0x180025a0f  mov     rbx, [rsp+28h+arg_0]
0x180025a14  add     rsp, 20h
0x180025a18  pop     rdi
0x180025a19  retn
```
