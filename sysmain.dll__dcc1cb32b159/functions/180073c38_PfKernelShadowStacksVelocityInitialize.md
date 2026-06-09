# PfKernelShadowStacksVelocityInitialize

- ea: `0x180073c38`
- end: `0x180073d27`
- name: `PfKernelShadowStacksVelocityInitialize`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18006a020`

## callees

- `0x180073c38`
- `0x1800ac5e0`
- `0x1800ac790`
- `0x1800ac7e4`

## import_xrefs

- `ntdll!ZwQuerySystemInformation` at `0x180073c64`
- `ntdll!ZwQuerySystemInformation` at `0x180073c64`
- `ntdll!RtlInitializeSRWLock` at `0x180073cde`
- `ntdll!RtlInitializeSRWLock` at `0x180073cde`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073d1c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073d1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180073d07`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180073d07`
- `VbsApi!KernelShadowStacksGetConfig` at `0x180073c91`
- `VbsApi!KernelShadowStacksGetConfig` at `0x180073c91`
- `api-ms-win-core-featurestaging-l1-1-0!SubscribeFeatureStateChangeNotification` at `0x180073cf5`
- `api-ms-win-core-featurestaging-l1-1-0!SubscribeFeatureStateChangeNotification` at `0x180073cf5`

## pseudocode

```c
void PfKernelShadowStacksVelocityInitialize()
{
  __int64 v0; // rdx
  __int64 v1; // r8
  struct _TP_WORK *ThreadpoolWork; // rax
  int v3; // [rsp+30h] [rbp+8h] BYREF
  int v4; // [rsp+38h] [rbp+10h] BYREF
  int v5; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  v5 = 0;
  v3 = 0;
  if ( ZwQuerySystemInformation(SystemTimeZoneInformation|0x80, &v3, 4u, 0) >= 0 && (v3 & 1) != 0 )
  {
    if ( (v3 & 0x100) != 0 && (unsigned int)KernelShadowStacksGetConfig(&v4, &v5) && (v4 & 1) != 0 && v5 == 1 )
    {
      LOBYTE(v0) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl'::`2'::impl);
      LOBYTE(v1) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl'::`2'::impl,
        v0,
        v1);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::__private_GetVariant(
        `wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl'::`2'::impl,
        2);
    }
    RtlInitializeSRWLock(&PfKernelShadowStackVelocityLock);
    SubscribeFeatureStateChangeNotification(
      &PfKernelShadowStacksVelocitySubscription,
      (PFEATURE_STATE_CHANGE_CALLBACK)PfKernelShadowStacksVelocityCallback,
      0);
    ThreadpoolWork = CreateThreadpoolWork(PfKernelShadowStacksVelocityFirstCallback, 0, 0);
    PfKernelShadowStacksVelocityFirstCallbackWork = ThreadpoolWork;
    if ( ThreadpoolWork )
      SubmitThreadpoolWork(ThreadpoolWork);
  }
}

```

## disassembly

```asm
0x180073c38  mov     rax, rsp
0x180073c3b  sub     rsp, 28h
0x180073c3f  xor     r9d, r9d; ReturnLength
0x180073c42  mov     dword ptr [rax+10h], 0
0x180073c49  lea     rdx, [rax+8]; SystemInformation
0x180073c4d  mov     dword ptr [rax+18h], 0
0x180073c54  mov     ecx, 0DDh; SystemInformationClass
0x180073c59  mov     dword ptr [rax+8], 0
0x180073c60  lea     r8d, [r9+4]; SystemInformationLength
0x180073c64  call    cs:__imp_ZwQuerySystemInformation
0x180073c6a  test    eax, eax
0x180073c6c  js      loc_180073D22
0x180073c72  test    byte ptr [rsp+28h+arg_0], 1
0x180073c77  jz      loc_180073D22
0x180073c7d  test    [rsp+28h+arg_0], 100h
0x180073c85  jz      short loc_180073CD7
0x180073c87  lea     rdx, [rsp+28h+arg_10]
0x180073c8c  lea     rcx, [rsp+28h+arg_8]
0x180073c91  call    cs:__imp_KernelShadowStacksGetConfig
0x180073c97  test    eax, eax
0x180073c99  jz      short loc_180073CD7
0x180073c9b  test    byte ptr [rsp+28h+arg_8], 1
0x180073ca0  jz      short loc_180073CD7
0x180073ca2  cmp     [rsp+28h+arg_10], 1
0x180073ca7  jnz     short loc_180073CD7
0x180073ca9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks> `wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl(void)'::`2'::impl
0x180073cb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::__private_IsEnabled(wil::ReportingKind)
0x180073cb5  mov     dl, al
0x180073cb7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks> `wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl(void)'::`2'::impl
0x180073cbe  mov     r8b, 1
0x180073cc1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180073cc6  mov     edx, 2
0x180073ccb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks> `wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl(void)'::`2'::impl
0x180073cd2  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@wil@@QEAA?AW4Variant_CET_Kernel_Shadow_Stacks@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180073cd7  lea     rcx, ?PfKernelShadowStackVelocityLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK PfKernelShadowStackVelocityLock
0x180073cde  call    cs:__imp_RtlInitializeSRWLock
0x180073ce4  xor     r8d, r8d; context
0x180073ce7  lea     rdx, ?PfKernelShadowStacksVelocityCallback@@YAXPEAX@Z; callback
0x180073cee  lea     rcx, ?PfKernelShadowStacksVelocitySubscription@@3PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@EA; subscription
0x180073cf5  call    cs:__imp_SubscribeFeatureStateChangeNotification
0x180073cfb  xor     r8d, r8d; pcbe
0x180073cfe  lea     rcx, ?PfKernelShadowStacksVelocityFirstCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180073d05  xor     edx, edx; pv
0x180073d07  call    cs:__imp_CreateThreadpoolWork
0x180073d0d  mov     cs:?PfKernelShadowStacksVelocityFirstCallbackWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * PfKernelShadowStacksVelocityFirstCallbackWork
0x180073d14  test    rax, rax
0x180073d17  jz      short loc_180073D22
0x180073d19  mov     rcx, rax; pwk
0x180073d1c  call    cs:__imp_SubmitThreadpoolWork
0x180073d22  add     rsp, 28h
0x180073d26  retn
```
