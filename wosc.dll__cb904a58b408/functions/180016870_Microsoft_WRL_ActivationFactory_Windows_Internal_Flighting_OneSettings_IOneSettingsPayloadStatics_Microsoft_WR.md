# Microsoft::WRL::ActivationFactory<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180016870`
- end: `0x1800168cf`
- name: `?GetIids@?$ActivationFactory@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800168e0`

## callees

- `0x180015bd4`
- `0x180016870`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016892`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016892`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x180016870  mov     [rsp+arg_0], rbx
0x180016875  push    rdi
0x180016876  sub     rsp, 20h
0x18001687a  mov     qword ptr [r8], 0
0x180016881  mov     ecx, 20h ; ' '; cb
0x180016886  mov     dword ptr [rdx], 0
0x18001688c  mov     rbx, r8
0x18001688f  mov     rdi, rdx
0x180016892  call    cs:__imp_CoTaskMemAlloc
0x180016898  mov     r8, rax
0x18001689b  test    rax, rax
0x18001689e  jnz     short loc_1800168A7
0x1800168a0  mov     eax, 8007000Eh
0x1800168a5  jmp     short loc_1800168C4
0x1800168a7  lea     rdx, [rsp+28h+arg_8]
0x1800168ac  mov     [rsp+28h+arg_8], 0
0x1800168b4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@VFtmBase@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x1800168b9  mov     dword ptr [rdi], 2
0x1800168bf  xor     eax, eax
0x1800168c1  mov     [rbx], r8
0x1800168c4  mov     rbx, [rsp+28h+arg_0]
0x1800168c9  add     rsp, 20h
0x1800168cd  pop     rdi
0x1800168ce  retn
```
