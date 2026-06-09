# wil_InitializeFeatureStaging

- ea: `0x140050170`
- end: `0x140050227`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14005003c`

## callees

- `0x14001e658`
- `0x14004e770`
- `0x14004ea0c`
- `0x140050170`
- `0x140050230`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400501ee`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400501ee`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140050198`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140050198`

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
  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v2 + 56) )
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
0x140050170  push    rbx
0x140050172  sub     rsp, 20h
0x140050176  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14005017d  mov     [rsp+28h+arg_0], 0
0x140050186  jnz     loc_14005021E
0x14005018c  xor     ebx, ebx
0x14005018e  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140050198  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14005019f  nop     dword ptr [rax+rax+00h]
0x1400501a4  mov     [rsp+28h+arg_0], rax
0x1400501a9  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400501ae  call    wil_details_EvaluateFeatureDependencies
0x1400501b3  lea     rcx, wil_details_featureDescriptors_a
0x1400501ba  call    wil_details_FeatureDescriptors_SkipPadding
0x1400501bf  test    rax, rax
0x1400501c2  jz      short loc_14005020C
0x1400501c4  cmp     [rax+1Dh], bl
0x1400501c7  jnz     short loc_1400501D3
0x1400501c9  cmp     [rax+1Eh], bl
0x1400501cc  jnz     short loc_1400501D3
0x1400501ce  cmp     [rax+1Ch], bl
0x1400501d1  jz      short loc_1400501D9
0x1400501d3  lea     rcx, [rax+38h]
0x1400501d7  jmp     short loc_1400501BA
0x1400501d9  lea     r9, g_wil_details_featureChangeNotification
0x1400501e0  xor     edx, edx
0x1400501e2  lea     r8, [rsp+28h+arg_0]
0x1400501e7  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400501ee  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400501f5  nop     dword ptr [rax+rax+00h]
0x1400501fa  test    eax, eax
0x1400501fc  jz      short loc_140050207
0x1400501fe  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140050205  jmp     short loc_14005020C
0x140050207  mov     ebx, 1
0x14005020c  call    wil_details_RegisterFeatureUsageProvider
0x140050211  test    eax, eax
0x140050213  jz      short loc_14005021E
0x140050215  xor     ecx, ecx
0x140050217  test    ebx, ebx
0x140050219  cmovnz  eax, ecx
0x14005021c  jmp     short loc_140050220
0x14005021e  xor     eax, eax
0x140050220  add     rsp, 20h
0x140050224  pop     rbx
0x140050225  retn
```
