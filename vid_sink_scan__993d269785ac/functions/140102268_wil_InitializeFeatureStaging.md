# wil_InitializeFeatureStaging

- ea: `0x140102268`
- end: `0x14010231f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14010203c`

## callees

- `0x140012bb4`
- `0x1400834ec`
- `0x14008373c`
- `0x140102268`
- `0x140102328`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1401022e6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1401022e6`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140102290`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140102290`

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
0x140102268  push    rbx
0x14010226a  sub     rsp, 20h
0x14010226e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140102275  mov     [rsp+28h+arg_0], 0
0x14010227e  jnz     loc_140102316
0x140102284  xor     ebx, ebx
0x140102286  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140102290  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140102297  nop     dword ptr [rax+rax+00h]
0x14010229c  mov     [rsp+28h+arg_0], rax
0x1401022a1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1401022a6  call    wil_details_EvaluateFeatureDependencies
0x1401022ab  lea     rcx, wil_details_featureDescriptors_a
0x1401022b2  call    wil_details_FeatureDescriptors_SkipPadding
0x1401022b7  test    rax, rax
0x1401022ba  jz      short loc_140102304
0x1401022bc  cmp     [rax+1Dh], bl
0x1401022bf  jnz     short loc_1401022CB
0x1401022c1  cmp     [rax+1Eh], bl
0x1401022c4  jnz     short loc_1401022CB
0x1401022c6  cmp     [rax+1Ch], bl
0x1401022c9  jz      short loc_1401022D1
0x1401022cb  lea     rcx, [rax+38h]
0x1401022cf  jmp     short loc_1401022B2
0x1401022d1  lea     r9, g_wil_details_featureChangeNotification
0x1401022d8  xor     edx, edx
0x1401022da  lea     r8, [rsp+28h+arg_0]
0x1401022df  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1401022e6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1401022ed  nop     dword ptr [rax+rax+00h]
0x1401022f2  test    eax, eax
0x1401022f4  jz      short loc_1401022FF
0x1401022f6  mov     cs:g_wil_details_featureChangeNotification, rbx
0x1401022fd  jmp     short loc_140102304
0x1401022ff  mov     ebx, 1
0x140102304  call    wil_details_RegisterFeatureUsageProvider
0x140102309  test    eax, eax
0x14010230b  jz      short loc_140102316
0x14010230d  xor     ecx, ecx
0x14010230f  test    ebx, ebx
0x140102311  cmovnz  eax, ecx
0x140102314  jmp     short loc_140102318
0x140102316  xor     eax, eax
0x140102318  add     rsp, 20h
0x14010231c  pop     rbx
0x14010231d  retn
```
