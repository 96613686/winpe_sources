# wil_InitializeFeatureStaging

- ea: `0x14005da18`
- end: `0x14005dacf`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14005d078`

## callees

- `0x140015e64`
- `0x1400392d4`
- `0x14003957c`
- `0x14005da18`
- `0x14005dad8`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005da96`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005da96`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005da40`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005da40`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  __int64 **i; // rcx
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
  for ( i = Feature_SFS_CD_BugFixes_2409__private_descriptor; ; i = (__int64 **)(v2 + 56) )
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
0x14005da18  push    rbx
0x14005da1a  sub     rsp, 20h
0x14005da1e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14005da25  mov     [rsp+28h+arg_0], 0
0x14005da2e  jnz     loc_14005DAC6
0x14005da34  xor     ebx, ebx
0x14005da36  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14005da40  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14005da47  nop     dword ptr [rax+rax+00h]
0x14005da4c  mov     [rsp+28h+arg_0], rax
0x14005da51  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14005da56  call    wil_details_EvaluateFeatureDependencies
0x14005da5b  lea     rcx, Feature_SFS_CD_BugFixes_2409__private_descriptor
0x14005da62  call    wil_details_FeatureDescriptors_SkipPadding
0x14005da67  test    rax, rax
0x14005da6a  jz      short loc_14005DAB4
0x14005da6c  cmp     [rax+1Dh], bl
0x14005da6f  jnz     short loc_14005DA7B
0x14005da71  cmp     [rax+1Eh], bl
0x14005da74  jnz     short loc_14005DA7B
0x14005da76  cmp     [rax+1Ch], bl
0x14005da79  jz      short loc_14005DA81
0x14005da7b  lea     rcx, [rax+38h]
0x14005da7f  jmp     short loc_14005DA62
0x14005da81  lea     r9, g_wil_details_featureChangeNotification
0x14005da88  xor     edx, edx
0x14005da8a  lea     r8, [rsp+28h+arg_0]
0x14005da8f  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14005da96  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14005da9d  nop     dword ptr [rax+rax+00h]
0x14005daa2  test    eax, eax
0x14005daa4  jz      short loc_14005DAAF
0x14005daa6  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14005daad  jmp     short loc_14005DAB4
0x14005daaf  mov     ebx, 1
0x14005dab4  call    wil_details_RegisterFeatureUsageProvider
0x14005dab9  test    eax, eax
0x14005dabb  jz      short loc_14005DAC6
0x14005dabd  xor     ecx, ecx
0x14005dabf  test    ebx, ebx
0x14005dac1  cmovnz  eax, ecx
0x14005dac4  jmp     short loc_14005DAC8
0x14005dac6  xor     eax, eax
0x14005dac8  add     rsp, 20h
0x14005dacc  pop     rbx
0x14005dacd  retn
```
