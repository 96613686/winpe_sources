# wil_InitializeFeatureStaging

- ea: `0x14003a23c`
- end: `0x14003a2f5`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003a078`

## callees

- `0x140008114`
- `0x1400367bc`
- `0x140036a0c`
- `0x14003a23c`
- `0x14003a2fc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14003a264`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14003a264`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14003a2bc`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14003a2bc`

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
0x14003a23c  push    rbx
0x14003a23e  sub     rsp, 20h
0x14003a242  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14003a249  mov     [rsp+28h+arg_0], 0
0x14003a252  jnz     loc_14003A2EC
0x14003a258  xor     ebx, ebx
0x14003a25a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14003a264  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14003a26b  nop     dword ptr [rax+rax+00h]
0x14003a270  mov     [rsp+28h+arg_0], rax
0x14003a275  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14003a27a  call    wil_details_EvaluateFeatureDependencies
0x14003a27f  lea     rcx, wil_details_featureDescriptors_a
0x14003a286  jmp     short loc_14003A29B
0x14003a288  cmp     [rax+1Dh], bl
0x14003a28b  jnz     short loc_14003A297
0x14003a28d  cmp     [rax+1Eh], bl
0x14003a290  jnz     short loc_14003A297
0x14003a292  cmp     [rax+1Ch], bl
0x14003a295  jz      short loc_14003A2A7
0x14003a297  lea     rcx, [rax+38h]
0x14003a29b  call    wil_details_FeatureDescriptors_SkipPadding
0x14003a2a0  test    rax, rax
0x14003a2a3  jnz     short loc_14003A288
0x14003a2a5  jmp     short loc_14003A2DA
0x14003a2a7  lea     r9, g_wil_details_featureChangeNotification
0x14003a2ae  xor     edx, edx
0x14003a2b0  lea     r8, [rsp+28h+arg_0]
0x14003a2b5  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14003a2bc  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14003a2c3  nop     dword ptr [rax+rax+00h]
0x14003a2c8  test    eax, eax
0x14003a2ca  jz      short loc_14003A2D5
0x14003a2cc  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14003a2d3  jmp     short loc_14003A2DA
0x14003a2d5  mov     ebx, 1
0x14003a2da  call    wil_details_RegisterFeatureUsageProvider
0x14003a2df  test    eax, eax
0x14003a2e1  jz      short loc_14003A2EC
0x14003a2e3  xor     ecx, ecx
0x14003a2e5  test    ebx, ebx
0x14003a2e7  cmovnz  eax, ecx
0x14003a2ea  jmp     short loc_14003A2EE
0x14003a2ec  xor     eax, eax
0x14003a2ee  add     rsp, 20h
0x14003a2f2  pop     rbx
0x14003a2f3  retn
```
