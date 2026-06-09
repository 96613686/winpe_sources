# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IAdaptiveImage>::GetIids(ulong *,_GUID * *)

- ea: `0x180023910`
- end: `0x18002397a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAdaptiveImage@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023980`

## callees

- `0x1800238d4`
- `0x180023910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023932`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Notifications::IAdaptiveImage>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,Windows::Internal::Notifications::IAdaptiveImage>::FillArrayWithIid(
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
0x180023910  mov     [rsp+arg_0], rbx
0x180023915  push    rdi
0x180023916  sub     rsp, 20h
0x18002391a  mov     qword ptr [r8], 0
0x180023921  mov     ecx, 30h ; '0'; cb
0x180023926  mov     dword ptr [rdx], 0
0x18002392c  mov     rbx, r8
0x18002392f  mov     rdi, rdx
0x180023932  call    cs:__imp_CoTaskMemAlloc
0x180023938  mov     r8, rax
0x18002393b  test    rax, rax
0x18002393e  jnz     short loc_180023947
0x180023940  mov     eax, 8007000Eh
0x180023945  jmp     short loc_18002396F
0x180023947  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18002394e  lea     rdx, [rsp+28h+arg_8]
0x180023953  mov     [rsp+28h+arg_8], 1
0x18002395b  movdqu  xmmword ptr [rax], xmm0
0x18002395f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIAdaptiveImage@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,Windows::Internal::Notifications::IAdaptiveImage>::FillArrayWithIid(ulong *,_GUID *)
0x180023964  mov     dword ptr [rdi], 3
0x18002396a  xor     eax, eax
0x18002396c  mov     [rbx], r8
0x18002396f  mov     rbx, [rsp+28h+arg_0]
0x180023974  add     rsp, 20h
0x180023978  pop     rdi
0x180023979  retn
```
