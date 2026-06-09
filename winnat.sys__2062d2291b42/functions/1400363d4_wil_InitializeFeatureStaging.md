# wil_InitializeFeatureStaging

- ea: `0x1400363d4`
- end: `0x14003648d`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140036078`

## callees

- `0x14000e184`
- `0x14002ff70`
- `0x14003021c`
- `0x1400363d4`
- `0x140036494`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400363fc`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400363fc`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140036454`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140036454`

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
0x1400363d4  push    rbx
0x1400363d6  sub     rsp, 20h
0x1400363da  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400363e1  mov     [rsp+28h+arg_0], 0
0x1400363ea  jnz     loc_140036484
0x1400363f0  xor     ebx, ebx
0x1400363f2  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400363fc  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140036403  nop     dword ptr [rax+rax+00h]
0x140036408  mov     [rsp+28h+arg_0], rax
0x14003640d  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140036412  call    wil_details_EvaluateFeatureDependencies
0x140036417  lea     rcx, wil_details_featureDescriptors_a
0x14003641e  jmp     short loc_140036433
0x140036420  cmp     [rax+1Dh], bl
0x140036423  jnz     short loc_14003642F
0x140036425  cmp     [rax+1Eh], bl
0x140036428  jnz     short loc_14003642F
0x14003642a  cmp     [rax+1Ch], bl
0x14003642d  jz      short loc_14003643F
0x14003642f  lea     rcx, [rax+38h]
0x140036433  call    wil_details_FeatureDescriptors_SkipPadding
0x140036438  test    rax, rax
0x14003643b  jnz     short loc_140036420
0x14003643d  jmp     short loc_140036472
0x14003643f  lea     r9, g_wil_details_featureChangeNotification
0x140036446  xor     edx, edx
0x140036448  lea     r8, [rsp+28h+arg_0]
0x14003644d  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140036454  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14003645b  nop     dword ptr [rax+rax+00h]
0x140036460  test    eax, eax
0x140036462  jz      short loc_14003646D
0x140036464  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14003646b  jmp     short loc_140036472
0x14003646d  mov     ebx, 1
0x140036472  call    wil_details_RegisterFeatureUsageProvider
0x140036477  test    eax, eax
0x140036479  jz      short loc_140036484
0x14003647b  xor     ecx, ecx
0x14003647d  test    ebx, ebx
0x14003647f  cmovnz  eax, ecx
0x140036482  jmp     short loc_140036486
0x140036484  xor     eax, eax
0x140036486  add     rsp, 20h
0x14003648a  pop     rbx
0x14003648b  retn
```
