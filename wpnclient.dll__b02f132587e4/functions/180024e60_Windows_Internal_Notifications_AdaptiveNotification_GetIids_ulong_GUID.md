# Windows::Internal::Notifications::AdaptiveNotification::GetIids(ulong *,_GUID * *)

- ea: `0x180024e60`
- end: `0x180024eca`
- name: `?GetIids@AdaptiveNotification@Notifications@Internal@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::AdaptiveNotification *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024ed0`

## callees

- `0x180024e1c`
- `0x180024e60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024e82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024e82`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::AdaptiveNotification::GetIids(
        Windows::Internal::Notifications::AdaptiveNotification *this,
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,Windows::Internal::Notifications::IAdaptiveNotification>::FillArrayWithIid(
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
0x180024e60  mov     [rsp+arg_0], rbx
0x180024e65  push    rdi
0x180024e66  sub     rsp, 20h
0x180024e6a  mov     qword ptr [r8], 0
0x180024e71  mov     ecx, 30h ; '0'; cb
0x180024e76  mov     dword ptr [rdx], 0
0x180024e7c  mov     rbx, r8
0x180024e7f  mov     rdi, rdx
0x180024e82  call    cs:__imp_CoTaskMemAlloc
0x180024e88  mov     r8, rax
0x180024e8b  test    rax, rax
0x180024e8e  jnz     short loc_180024E97
0x180024e90  mov     eax, 8007000Eh
0x180024e95  jmp     short loc_180024EBF
0x180024e97  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x180024e9e  lea     rdx, [rsp+28h+arg_8]
0x180024ea3  mov     [rsp+28h+arg_8], 1
0x180024eab  movdqu  xmmword ptr [rax], xmm0
0x180024eaf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIAdaptiveNotification@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,Windows::Internal::Notifications::IAdaptiveNotification>::FillArrayWithIid(ulong *,_GUID *)
0x180024eb4  mov     dword ptr [rdi], 3
0x180024eba  xor     eax, eax
0x180024ebc  mov     [rbx], r8
0x180024ebf  mov     rbx, [rsp+28h+arg_0]
0x180024ec4  add     rsp, 20h
0x180024ec8  pop     rdi
0x180024ec9  retn
```
