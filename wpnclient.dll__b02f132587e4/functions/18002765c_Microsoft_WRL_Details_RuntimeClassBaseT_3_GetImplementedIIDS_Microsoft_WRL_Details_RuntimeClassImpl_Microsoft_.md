# Microsoft::WRL::Details::RuntimeClassBaseT<3>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>> *,ulong *,_GUID * *)

- ea: `0x18002765c`
- end: `0x180027711`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsWithViewIdBase@@UIToastNotificationActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsWithViewIdBase@@UIToastNotificationActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800284c0`

## callees

- `0x18002765c`
- `0x1800282a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027683`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<3>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  unsigned int v8; // edx
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = a1;
  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x60u);
  if ( !v6 )
    return 2147942414LL;
  LODWORD(v11) = 0;
  Microsoft::WRL::Implements<Windows::ApplicationModel::Activation::IActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgsWithUser,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v11,
    v6);
  v8 = v11 + 1;
  *(GUID *)(v9 + 16LL * (unsigned int)v11) = GUID_930cef4b_b829_40fc_88f4_8513e8a64738;
  v10 = 2LL * v8++;
  *(GUID *)(v9 + 8 * v10) = GUID_33f288a6_5c2c_4d27_bac7_7536088f1219;
  *(GUID *)(v9 + 16LL * v8) = GUID_00000038_0000_0000_c000_000000000046;
  result = 0;
  *(GUID *)(v9 + 16LL * (v8 + 1)) = GUID_92a86f82_5290_431d_be85_c4aaeeb8685f;
  *a2 = 6;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x18002765c  mov     [rsp+arg_8], rbx
0x180027661  mov     [rsp+arg_0], rcx
0x180027666  push    rdi
0x180027667  sub     rsp, 20h
0x18002766b  mov     qword ptr [r8], 0
0x180027672  mov     ecx, 60h ; '`'; cb
0x180027677  mov     dword ptr [rdx], 0
0x18002767d  mov     rbx, r8
0x180027680  mov     rdi, rdx
0x180027683  call    cs:__imp_CoTaskMemAlloc
0x180027689  mov     r8, rax
0x18002768c  test    rax, rax
0x18002768f  jnz     short loc_180027698
0x180027691  mov     eax, 8007000Eh
0x180027696  jmp     short loc_180027706
0x180027698  lea     rdx, [rsp+28h+arg_0]
0x18002769d  mov     dword ptr [rsp+28h+arg_0], 0
0x1800276a5  call    ?FillArrayWithIid@?$Implements@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@UIActivatedEventArgsWithUser@234@U?$CloakedIid@UIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@U?$CloakedIid@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@78@VFtmBase@78@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Windows::ApplicationModel::Activation::IActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgsWithUser,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800276aa  movups  xmm0, xmmword ptr cs:_GUID_930cef4b_b829_40fc_88f4_8513e8a64738.Data1
0x1800276b1  mov     edx, dword ptr [rsp+28h+arg_0]
0x1800276b5  mov     eax, edx
0x1800276b7  add     rax, rax
0x1800276ba  inc     edx
0x1800276bc  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1800276c2  mov     eax, edx
0x1800276c4  movups  xmm0, xmmword ptr cs:_GUID_33f288a6_5c2c_4d27_bac7_7536088f1219.Data1
0x1800276cb  add     rax, rax
0x1800276ce  inc     edx
0x1800276d0  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1800276d6  mov     eax, edx
0x1800276d8  lea     ecx, [rdx+1]
0x1800276db  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800276e2  add     rax, rax
0x1800276e5  add     rcx, rcx
0x1800276e8  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1800276ee  xor     eax, eax
0x1800276f0  movups  xmm0, xmmword ptr cs:_GUID_92a86f82_5290_431d_be85_c4aaeeb8685f.Data1
0x1800276f7  movdqu  xmmword ptr [r8+rcx*8], xmm0
0x1800276fd  mov     dword ptr [rdi], 6
0x180027703  mov     [rbx], r8
0x180027706  mov     rbx, [rsp+28h+arg_8]
0x18002770b  add     rsp, 20h
0x18002770f  pop     rdi
0x180027710  retn
```
