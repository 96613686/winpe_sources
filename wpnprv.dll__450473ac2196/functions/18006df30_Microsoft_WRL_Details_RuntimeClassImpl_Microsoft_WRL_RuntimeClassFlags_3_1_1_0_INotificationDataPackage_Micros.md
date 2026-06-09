# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,INotificationDataPackage,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18006df30`
- end: `0x18006df9a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UINotificationDataPackage@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18006cfb4`
- `0x18006df30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006df52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006df52`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,INotificationDataPackage,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationDataPackage,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18006df30  mov     [rsp+arg_0], rbx
0x18006df35  push    rdi
0x18006df36  sub     rsp, 20h
0x18006df3a  mov     qword ptr [r8], 0
0x18006df41  mov     ecx, 30h ; '0'; cb
0x18006df46  mov     dword ptr [rdx], 0
0x18006df4c  mov     rbx, r8
0x18006df4f  mov     rdi, rdx
0x18006df52  call    cs:__imp_CoTaskMemAlloc
0x18006df58  mov     r8, rax
0x18006df5b  test    rax, rax
0x18006df5e  jnz     short loc_18006DF67
0x18006df60  mov     eax, 8007000Eh
0x18006df65  jmp     short loc_18006DF8F
0x18006df67  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18006df6e  lea     rdx, [rsp+28h+arg_8]
0x18006df73  mov     [rsp+28h+arg_8], 1
0x18006df7b  movdqu  xmmword ptr [rax], xmm0
0x18006df7f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UINotificationDataPackage@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationDataPackage,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18006df84  mov     dword ptr [rdi], 3
0x18006df8a  xor     eax, eax
0x18006df8c  mov     [rbx], r8
0x18006df8f  mov     rbx, [rsp+28h+arg_0]
0x18006df94  add     rsp, 20h
0x18006df98  pop     rdi
0x18006df99  retn
```
