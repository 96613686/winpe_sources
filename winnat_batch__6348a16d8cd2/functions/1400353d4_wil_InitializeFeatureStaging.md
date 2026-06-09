# wil_InitializeFeatureStaging

- ea: `0x1400353d4`
- end: `0x14003548d`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140035078`

## callees

- `0x14000e1b4`
- `0x14002ef70`
- `0x14002f1bc`
- `0x1400353d4`
- `0x140035494`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400353fc`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400353fc`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140035454`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140035454`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  int **i; // rcx
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
  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v2 + 56) )
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
0x1400353d4  push    rbx
0x1400353d6  sub     rsp, 20h
0x1400353da  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400353e1  mov     [rsp+28h+arg_0], 0
0x1400353ea  jnz     loc_140035484
0x1400353f0  xor     ebx, ebx
0x1400353f2  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400353fc  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140035403  nop     dword ptr [rax+rax+00h]
0x140035408  mov     [rsp+28h+arg_0], rax
0x14003540d  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140035412  call    wil_details_EvaluateFeatureDependencies
0x140035417  lea     rcx, wil_details_featureDescriptors_a
0x14003541e  jmp     short loc_140035433
0x140035420  cmp     [rax+1Dh], bl
0x140035423  jnz     short loc_14003542F
0x140035425  cmp     [rax+1Eh], bl
0x140035428  jnz     short loc_14003542F
0x14003542a  cmp     [rax+1Ch], bl
0x14003542d  jz      short loc_14003543F
0x14003542f  lea     rcx, [rax+38h]
0x140035433  call    wil_details_FeatureDescriptors_SkipPadding
0x140035438  test    rax, rax
0x14003543b  jnz     short loc_140035420
0x14003543d  jmp     short loc_140035472
0x14003543f  lea     r9, g_wil_details_featureChangeNotification
0x140035446  xor     edx, edx
0x140035448  lea     r8, [rsp+28h+arg_0]
0x14003544d  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140035454  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14003545b  nop     dword ptr [rax+rax+00h]
0x140035460  test    eax, eax
0x140035462  jz      short loc_14003546D
0x140035464  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14003546b  jmp     short loc_140035472
0x14003546d  mov     ebx, 1
0x140035472  call    wil_details_RegisterFeatureUsageProvider
0x140035477  test    eax, eax
0x140035479  jz      short loc_140035484
0x14003547b  xor     ecx, ecx
0x14003547d  test    ebx, ebx
0x14003547f  cmovnz  eax, ecx
0x140035482  jmp     short loc_140035486
0x140035484  xor     eax, eax
0x140035486  add     rsp, 20h
0x14003548a  pop     rbx
0x14003548b  retn
```
