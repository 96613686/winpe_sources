# wil_InitializeFeatureStaging

- ea: `0x14009c440`
- end: `0x14009c4f7`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14009c078`

## callees

- `0x140023640`
- `0x14005fe6c`
- `0x1400600bc`
- `0x14009c440`
- `0x14009c500`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14009c4be`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14009c4be`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14009c468`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14009c468`

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
0x14009c440  push    rbx
0x14009c442  sub     rsp, 20h
0x14009c446  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14009c44d  mov     [rsp+28h+arg_0], 0
0x14009c456  jnz     loc_14009C4EE
0x14009c45c  xor     ebx, ebx
0x14009c45e  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14009c468  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14009c46f  nop     dword ptr [rax+rax+00h]
0x14009c474  mov     [rsp+28h+arg_0], rax
0x14009c479  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14009c47e  call    wil_details_EvaluateFeatureDependencies
0x14009c483  lea     rcx, wil_details_featureDescriptors_a
0x14009c48a  call    wil_details_FeatureDescriptors_SkipPadding
0x14009c48f  test    rax, rax
0x14009c492  jz      short loc_14009C4DC
0x14009c494  cmp     [rax+1Dh], bl
0x14009c497  jnz     short loc_14009C4A3
0x14009c499  cmp     [rax+1Eh], bl
0x14009c49c  jnz     short loc_14009C4A3
0x14009c49e  cmp     [rax+1Ch], bl
0x14009c4a1  jz      short loc_14009C4A9
0x14009c4a3  lea     rcx, [rax+38h]
0x14009c4a7  jmp     short loc_14009C48A
0x14009c4a9  lea     r9, g_wil_details_featureChangeNotification
0x14009c4b0  xor     edx, edx
0x14009c4b2  lea     r8, [rsp+28h+arg_0]
0x14009c4b7  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14009c4be  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14009c4c5  nop     dword ptr [rax+rax+00h]
0x14009c4ca  test    eax, eax
0x14009c4cc  jz      short loc_14009C4D7
0x14009c4ce  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14009c4d5  jmp     short loc_14009C4DC
0x14009c4d7  mov     ebx, 1
0x14009c4dc  call    wil_details_RegisterFeatureUsageProvider
0x14009c4e1  test    eax, eax
0x14009c4e3  jz      short loc_14009C4EE
0x14009c4e5  xor     ecx, ecx
0x14009c4e7  test    ebx, ebx
0x14009c4e9  cmovnz  eax, ecx
0x14009c4ec  jmp     short loc_14009C4F0
0x14009c4ee  xor     eax, eax
0x14009c4f0  add     rsp, 20h
0x14009c4f4  pop     rbx
0x14009c4f5  retn
```
