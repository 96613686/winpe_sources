# wil_InitializeFeatureStaging

- ea: `0x140040990`
- end: `0x140040a47`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140040078`

## callees

- `0x14000f4cc`
- `0x1400258cc`
- `0x140025b6c`
- `0x140040990`
- `0x140040a50`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140040a0e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140040a0e`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400409b8`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400409b8`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  void *i; // rcx
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
  for ( i = &wil_details_featureDescriptors_a; ; i = v2 + 56 )
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
0x140040990  push    rbx
0x140040992  sub     rsp, 20h
0x140040996  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14004099d  mov     [rsp+28h+arg_0], 0
0x1400409a6  jnz     loc_140040A3E
0x1400409ac  xor     ebx, ebx
0x1400409ae  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400409b8  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400409bf  nop     dword ptr [rax+rax+00h]
0x1400409c4  mov     [rsp+28h+arg_0], rax
0x1400409c9  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400409ce  call    wil_details_EvaluateFeatureDependencies
0x1400409d3  lea     rcx, wil_details_featureDescriptors_a
0x1400409da  call    wil_details_FeatureDescriptors_SkipPadding
0x1400409df  test    rax, rax
0x1400409e2  jz      short loc_140040A2C
0x1400409e4  cmp     [rax+1Dh], bl
0x1400409e7  jnz     short loc_1400409F3
0x1400409e9  cmp     [rax+1Eh], bl
0x1400409ec  jnz     short loc_1400409F3
0x1400409ee  cmp     [rax+1Ch], bl
0x1400409f1  jz      short loc_1400409F9
0x1400409f3  lea     rcx, [rax+38h]
0x1400409f7  jmp     short loc_1400409DA
0x1400409f9  lea     r9, g_wil_details_featureChangeNotification
0x140040a00  xor     edx, edx
0x140040a02  lea     r8, [rsp+28h+arg_0]
0x140040a07  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140040a0e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140040a15  nop     dword ptr [rax+rax+00h]
0x140040a1a  test    eax, eax
0x140040a1c  jz      short loc_140040A27
0x140040a1e  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140040a25  jmp     short loc_140040A2C
0x140040a27  mov     ebx, 1
0x140040a2c  call    wil_details_RegisterFeatureUsageProvider
0x140040a31  test    eax, eax
0x140040a33  jz      short loc_140040A3E
0x140040a35  xor     ecx, ecx
0x140040a37  test    ebx, ebx
0x140040a39  cmovnz  eax, ecx
0x140040a3c  jmp     short loc_140040A40
0x140040a3e  xor     eax, eax
0x140040a40  add     rsp, 20h
0x140040a44  pop     rbx
0x140040a45  retn
```
