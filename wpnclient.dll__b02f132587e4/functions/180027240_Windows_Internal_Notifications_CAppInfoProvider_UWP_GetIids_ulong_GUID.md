# Windows::Internal::Notifications::CAppInfoProvider_UWP::GetIids(ulong *,_GUID * *)

- ea: `0x180027240`
- end: `0x1800272aa`
- name: `?GetIids@CAppInfoProvider_UWP@Notifications@Internal@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CAppInfoProvider_UWP *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800272b0`

## callees

- `0x180027200`
- `0x180027240`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027262`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CAppInfoProvider_UWP::GetIids(
        Windows::Internal::Notifications::CAppInfoProvider_UWP *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,Windows::Internal::Notifications::IWpnAppInfoProvider>::FillArrayWithIid(
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
0x180027240  mov     [rsp+arg_0], rbx
0x180027245  push    rdi
0x180027246  sub     rsp, 20h
0x18002724a  mov     qword ptr [r8], 0
0x180027251  mov     ecx, 30h ; '0'; cb
0x180027256  mov     dword ptr [rdx], 0
0x18002725c  mov     rbx, r8
0x18002725f  mov     rdi, rdx
0x180027262  call    cs:__imp_CoTaskMemAlloc
0x180027268  mov     r8, rax
0x18002726b  test    rax, rax
0x18002726e  jnz     short loc_180027277
0x180027270  mov     eax, 8007000Eh
0x180027275  jmp     short loc_18002729F
0x180027277  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18002727e  lea     rdx, [rsp+28h+arg_8]
0x180027283  mov     [rsp+28h+arg_8], 1
0x18002728b  movdqu  xmmword ptr [rax], xmm0
0x18002728f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIWpnAppInfoProvider@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,Windows::Internal::Notifications::IWpnAppInfoProvider>::FillArrayWithIid(ulong *,_GUID *)
0x180027294  mov     dword ptr [rdi], 3
0x18002729a  xor     eax, eax
0x18002729c  mov     [rbx], r8
0x18002729f  mov     rbx, [rsp+28h+arg_0]
0x1800272a4  add     rsp, 20h
0x1800272a8  pop     rdi
0x1800272a9  retn
```
