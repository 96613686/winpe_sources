# Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,Windows::Internal::Flighting::OneSettings::IOneSettingsManager2,Windows::Internal::Flighting::OneSettings::IOneSettingsCleaner,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTestability,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTelemetry,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTelemetry2,Windows::Internal::Flighting::OneSettings::IOneSettingsCTACProvider>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,Windows::Internal::Flighting::OneSettings::IOneSettingsManager2,Windows::Internal::Flighting::OneSettings::IOneSettingsCleaner,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTestability,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTelemetry,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTelemetry2,Windows::Internal::Flighting::OneSettings::IOneSettingsCTACProvider>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *,ulong *,_GUID * *)

- ea: `0x18000755c`
- end: `0x180007605`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@U?$Implements@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@UIOneSettingsManager2@2345@UIOneSettingsCleaner@2345@UIOneSettingsManagerTestability@2345@UIOneSettingsManagerTelemetry@2345@UIOneSettingsManagerTelemetry2@2345@UIOneSettingsCTACProvider@2345@@23@VFtmBase@23@VNil@Details@23@V7823@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$0N@@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@U?$Implements@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@UIOneSettingsManager2@2345@UIOneSettingsCleaner@2345@UIOneSettingsManagerTestability@2345@UIOneSettingsManagerTelemetry@2345@UIOneSettingsManagerTelemetry2@2345@UIOneSettingsCTACProvider@2345@@23@VFtmBase@23@VNil@Details@23@V7823@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bd50`

## callees

- `0x18000755c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000757e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000757e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,Windows::Internal::Flighting::OneSettings::IOneSettingsManager2,Windows::Internal::Flighting::OneSettings::IOneSettingsCleaner,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTestability,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTelemetry,Windows::Internal::Flighting::OneSettings::IOneSettingsManagerTelemetry2,Windows::Internal::Flighting::OneSettings::IOneSettingsCTACProvider>,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x80u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017;
  v5[2] = GUID_28f28e22_0ecf_45cc_a9b6_fe4148ac1268;
  v5[3] = GUID_999c5339_6b49_433d_acbb_990566d91531;
  v5[4] = GUID_68403a6f_70d8_4e4a_ba6b_6b202a6e89b1;
  v5[5] = GUID_46e985c3_60da_4809_8e6c_1392f761f3ab;
  v5[6] = GUID_f9f42a18_f861_4f6d_8cc9_a550b0178539;
  v5[7] = GUID_af001ee7_492e_47d4_a59c_72c86c79bb52;
  *a2 = 8;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000755c  mov     [rsp+arg_0], rbx
0x180007561  push    rdi
0x180007562  sub     rsp, 20h
0x180007566  mov     qword ptr [r8], 0
0x18000756d  mov     ecx, 80h; cb
0x180007572  mov     dword ptr [rdx], 0
0x180007578  mov     rbx, r8
0x18000757b  mov     rdi, rdx
0x18000757e  call    cs:__imp_CoTaskMemAlloc
0x180007584  test    rax, rax
0x180007587  jnz     short loc_180007590
0x180007589  mov     eax, 8007000Eh
0x18000758e  jmp     short loc_1800075FA
0x180007590  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180007597  movdqu  xmmword ptr [rax], xmm0
0x18000759b  movups  xmm1, xmmword ptr cs:_GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017.Data1
0x1800075a2  movdqu  xmmword ptr [rax+10h], xmm1
0x1800075a7  movups  xmm0, xmmword ptr cs:_GUID_28f28e22_0ecf_45cc_a9b6_fe4148ac1268.Data1
0x1800075ae  movdqu  xmmword ptr [rax+20h], xmm0
0x1800075b3  movups  xmm1, xmmword ptr cs:_GUID_999c5339_6b49_433d_acbb_990566d91531.Data1
0x1800075ba  movdqu  xmmword ptr [rax+30h], xmm1
0x1800075bf  movups  xmm0, xmmword ptr cs:_GUID_68403a6f_70d8_4e4a_ba6b_6b202a6e89b1.Data1
0x1800075c6  movdqu  xmmword ptr [rax+40h], xmm0
0x1800075cb  movups  xmm1, xmmword ptr cs:_GUID_46e985c3_60da_4809_8e6c_1392f761f3ab.Data1
0x1800075d2  movdqu  xmmword ptr [rax+50h], xmm1
0x1800075d7  movups  xmm0, xmmword ptr cs:_GUID_f9f42a18_f861_4f6d_8cc9_a550b0178539.Data1
0x1800075de  movdqu  xmmword ptr [rax+60h], xmm0
0x1800075e3  movups  xmm1, xmmword ptr cs:_GUID_af001ee7_492e_47d4_a59c_72c86c79bb52.Data1
0x1800075ea  movdqu  xmmword ptr [rax+70h], xmm1
0x1800075ef  mov     dword ptr [rdi], 8
0x1800075f5  mov     [rbx], rax
0x1800075f8  xor     eax, eax
0x1800075fa  mov     rbx, [rsp+28h+arg_0]
0x1800075ff  add     rsp, 20h
0x180007603  pop     rdi
0x180007604  retn
```
