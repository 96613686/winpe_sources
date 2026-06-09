# wil_InitializeFeatureStaging

- ea: `0x1400ba304`
- end: `0x1400ba3bb`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400ba080`

## callees

- `0x14001b258`
- `0x1400a412c`
- `0x1400a43cc`
- `0x1400ba304`
- `0x1400ba3c4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400ba32c`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400ba32c`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400ba382`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400ba382`

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
  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 **)(v2 + 56) )
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
0x1400ba304  push    rbx
0x1400ba306  sub     rsp, 20h
0x1400ba30a  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400ba311  mov     [rsp+28h+arg_0], 0
0x1400ba31a  jnz     loc_1400BA3B2
0x1400ba320  xor     ebx, ebx
0x1400ba322  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400ba32c  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400ba333  nop     dword ptr [rax+rax+00h]
0x1400ba338  mov     [rsp+28h+arg_0], rax
0x1400ba33d  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400ba342  call    wil_details_EvaluateFeatureDependencies
0x1400ba347  lea     rcx, wil_details_featureDescriptors_a
0x1400ba34e  call    wil_details_FeatureDescriptors_SkipPadding
0x1400ba353  test    rax, rax
0x1400ba356  jz      short loc_1400BA3A0
0x1400ba358  cmp     [rax+1Dh], bl
0x1400ba35b  jnz     short loc_1400BA367
0x1400ba35d  cmp     [rax+1Eh], bl
0x1400ba360  jnz     short loc_1400BA367
0x1400ba362  cmp     [rax+1Ch], bl
0x1400ba365  jz      short loc_1400BA36D
0x1400ba367  lea     rcx, [rax+38h]
0x1400ba36b  jmp     short loc_1400BA34E
0x1400ba36d  lea     r9, g_wil_details_featureChangeNotification
0x1400ba374  xor     edx, edx
0x1400ba376  lea     r8, [rsp+28h+arg_0]
0x1400ba37b  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400ba382  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400ba389  nop     dword ptr [rax+rax+00h]
0x1400ba38e  test    eax, eax
0x1400ba390  jz      short loc_1400BA39B
0x1400ba392  mov     cs:g_wil_details_featureChangeNotification, rbx
0x1400ba399  jmp     short loc_1400BA3A0
0x1400ba39b  mov     ebx, 1
0x1400ba3a0  call    wil_details_RegisterFeatureUsageProvider
0x1400ba3a5  test    eax, eax
0x1400ba3a7  jz      short loc_1400BA3B2
0x1400ba3a9  xor     ecx, ecx
0x1400ba3ab  test    ebx, ebx
0x1400ba3ad  cmovnz  eax, ecx
0x1400ba3b0  jmp     short loc_1400BA3B4
0x1400ba3b2  xor     eax, eax
0x1400ba3b4  add     rsp, 20h
0x1400ba3b8  pop     rbx
0x1400ba3b9  retn
```
