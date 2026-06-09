# wil_InitializeFeatureStaging

- ea: `0x140024078`
- end: `0x14002412f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140014184`

## callees

- `0x140014694`
- `0x1400230c8`
- `0x14002336c`
- `0x140024078`
- `0x140024138`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400240f6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400240f6`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400240a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400240a0`

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
0x140024078  push    rbx
0x14002407a  sub     rsp, 20h
0x14002407e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140024085  mov     [rsp+28h+arg_0], 0
0x14002408e  jnz     loc_140024126
0x140024094  xor     ebx, ebx
0x140024096  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400240a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400240a7  nop     dword ptr [rax+rax+00h]
0x1400240ac  mov     [rsp+28h+arg_0], rax
0x1400240b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400240b6  call    wil_details_EvaluateFeatureDependencies
0x1400240bb  lea     rcx, wil_details_featureDescriptors_a
0x1400240c2  call    wil_details_FeatureDescriptors_SkipPadding
0x1400240c7  test    rax, rax
0x1400240ca  jz      short loc_140024114
0x1400240cc  cmp     [rax+1Dh], bl
0x1400240cf  jnz     short loc_1400240DB
0x1400240d1  cmp     [rax+1Eh], bl
0x1400240d4  jnz     short loc_1400240DB
0x1400240d6  cmp     [rax+1Ch], bl
0x1400240d9  jz      short loc_1400240E1
0x1400240db  lea     rcx, [rax+38h]
0x1400240df  jmp     short loc_1400240C2
0x1400240e1  lea     r9, g_wil_details_featureChangeNotification
0x1400240e8  xor     edx, edx
0x1400240ea  lea     r8, [rsp+28h+arg_0]
0x1400240ef  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400240f6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400240fd  nop     dword ptr [rax+rax+00h]
0x140024102  test    eax, eax
0x140024104  jz      short loc_14002410F
0x140024106  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14002410d  jmp     short loc_140024114
0x14002410f  mov     ebx, 1
0x140024114  call    wil_details_RegisterFeatureUsageProvider
0x140024119  test    eax, eax
0x14002411b  jz      short loc_140024126
0x14002411d  xor     ecx, ecx
0x14002411f  test    ebx, ebx
0x140024121  cmovnz  eax, ecx
0x140024124  jmp     short loc_140024128
0x140024126  xor     eax, eax
0x140024128  add     rsp, 20h
0x14002412c  pop     rbx
0x14002412d  retn
```
