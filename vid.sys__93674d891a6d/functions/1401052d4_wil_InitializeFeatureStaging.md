# wil_InitializeFeatureStaging

- ea: `0x1401052d4`
- end: `0x14010538b`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14010503c`

## callees

- `0x1400129a4`
- `0x14008461c`
- `0x1400848bc`
- `0x1401052d4`
- `0x140105394`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140105352`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140105352`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1401052fc`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1401052fc`

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
0x1401052d4  push    rbx
0x1401052d6  sub     rsp, 20h
0x1401052da  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1401052e1  mov     [rsp+28h+arg_0], 0
0x1401052ea  jnz     loc_140105382
0x1401052f0  xor     ebx, ebx
0x1401052f2  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1401052fc  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140105303  nop     dword ptr [rax+rax+00h]
0x140105308  mov     [rsp+28h+arg_0], rax
0x14010530d  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140105312  call    wil_details_EvaluateFeatureDependencies
0x140105317  lea     rcx, wil_details_featureDescriptors_a
0x14010531e  call    wil_details_FeatureDescriptors_SkipPadding
0x140105323  test    rax, rax
0x140105326  jz      short loc_140105370
0x140105328  cmp     [rax+1Dh], bl
0x14010532b  jnz     short loc_140105337
0x14010532d  cmp     [rax+1Eh], bl
0x140105330  jnz     short loc_140105337
0x140105332  cmp     [rax+1Ch], bl
0x140105335  jz      short loc_14010533D
0x140105337  lea     rcx, [rax+38h]
0x14010533b  jmp     short loc_14010531E
0x14010533d  lea     r9, g_wil_details_featureChangeNotification
0x140105344  xor     edx, edx
0x140105346  lea     r8, [rsp+28h+arg_0]
0x14010534b  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140105352  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140105359  nop     dword ptr [rax+rax+00h]
0x14010535e  test    eax, eax
0x140105360  jz      short loc_14010536B
0x140105362  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140105369  jmp     short loc_140105370
0x14010536b  mov     ebx, 1
0x140105370  call    wil_details_RegisterFeatureUsageProvider
0x140105375  test    eax, eax
0x140105377  jz      short loc_140105382
0x140105379  xor     ecx, ecx
0x14010537b  test    ebx, ebx
0x14010537d  cmovnz  eax, ecx
0x140105380  jmp     short loc_140105384
0x140105382  xor     eax, eax
0x140105384  add     rsp, 20h
0x140105388  pop     rbx
0x140105389  retn
```
