# wil_InitializeFeatureStaging

- ea: `0x14000d078`
- end: `0x14000d12f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140004880`

## callees

- `0x140004f0c`
- `0x14000b238`
- `0x14000b4dc`
- `0x14000d078`
- `0x14000d138`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14000d0f6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14000d0f6`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14000d0a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14000d0a0`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  __int64 *i; // rcx
  _BYTE *v2; // rax
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  v0 = 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v2 + 56) )
  {
    v2 = (_BYTE *)wil_details_FeatureDescriptors_SkipPadding(i);
    if ( !v2 )
      break;
    if ( !v2[29] && !v2[30] && !v2[28] )
    {
      if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                           wil_details_ReevaluateOnFeatureConfigurationChange,
                           0,
                           &v4,
                           &g_wil_details_featureChangeNotification) )
        g_wil_details_featureChangeNotification = 0;
      else
        v0 = 1;
      break;
    }
  }
  result = wil_details_RegisterFeatureUsageProvider();
  if ( !(_DWORD)result )
    return 0;
  if ( v0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14000d078  push    rbx
0x14000d07a  sub     rsp, 20h
0x14000d07e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000d085  mov     [rsp+28h+arg_0], 0
0x14000d08e  jnz     loc_14000D126
0x14000d094  xor     ebx, ebx
0x14000d096  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14000d0a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14000d0a7  nop     dword ptr [rax+rax+00h]
0x14000d0ac  mov     [rsp+28h+arg_0], rax
0x14000d0b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14000d0b6  call    wil_details_EvaluateFeatureDependencies
0x14000d0bb  lea     rcx, wil_details_featureDescriptors_a
0x14000d0c2  call    wil_details_FeatureDescriptors_SkipPadding
0x14000d0c7  test    rax, rax
0x14000d0ca  jz      short loc_14000D114
0x14000d0cc  cmp     [rax+1Dh], bl
0x14000d0cf  jnz     short loc_14000D0DB
0x14000d0d1  cmp     [rax+1Eh], bl
0x14000d0d4  jnz     short loc_14000D0DB
0x14000d0d6  cmp     [rax+1Ch], bl
0x14000d0d9  jz      short loc_14000D0E1
0x14000d0db  lea     rcx, [rax+38h]
0x14000d0df  jmp     short loc_14000D0C2
0x14000d0e1  lea     r9, g_wil_details_featureChangeNotification
0x14000d0e8  xor     edx, edx
0x14000d0ea  lea     r8, [rsp+28h+arg_0]
0x14000d0ef  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14000d0f6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14000d0fd  nop     dword ptr [rax+rax+00h]
0x14000d102  test    eax, eax
0x14000d104  jz      short loc_14000D10F
0x14000d106  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14000d10d  jmp     short loc_14000D114
0x14000d10f  mov     ebx, 1
0x14000d114  call    wil_details_RegisterFeatureUsageProvider
0x14000d119  test    eax, eax
0x14000d11b  jz      short loc_14000D126
0x14000d11d  xor     ecx, ecx
0x14000d11f  test    ebx, ebx
0x14000d121  cmovnz  eax, ecx
0x14000d124  jmp     short loc_14000D128
0x14000d126  xor     eax, eax
0x14000d128  add     rsp, 20h
0x14000d12c  pop     rbx
0x14000d12d  retn
```
