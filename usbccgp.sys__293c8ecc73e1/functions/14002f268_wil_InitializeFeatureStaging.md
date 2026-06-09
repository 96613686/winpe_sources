# wil_InitializeFeatureStaging

- ea: `0x14002f268`
- end: `0x14002f31f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002f078`

## callees

- `0x14000ef2c`
- `0x140022d5c`
- `0x14002dd58`
- `0x14002f268`
- `0x14002f328`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14002f290`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14002f290`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14002f2e6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14002f2e6`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  _UNKNOWN **i; // rcx
  _BYTE *v2; // rax
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) )
    return 0;
  v0 = 0;
  LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) = 1;
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 56) )
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
                           &WPP_MAIN_CB.Dpc.DeferredContext) )
        WPP_MAIN_CB.Dpc.DeferredContext = 0;
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
0x14002f268  push    rbx
0x14002f26a  sub     rsp, 20h
0x14002f26e  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2, 0
0x14002f275  mov     [rsp+28h+arg_0], 0
0x14002f27e  jnz     loc_14002F316
0x14002f284  xor     ebx, ebx
0x14002f286  mov     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2, 1
0x14002f290  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14002f297  nop     dword ptr [rax+rax+00h]
0x14002f29c  mov     [rsp+28h+arg_0], rax
0x14002f2a1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14002f2a6  call    wil_details_EvaluateFeatureDependencies
0x14002f2ab  lea     rcx, wil_details_featureDescriptors_a
0x14002f2b2  call    wil_details_FeatureDescriptors_SkipPadding
0x14002f2b7  test    rax, rax
0x14002f2ba  jz      short loc_14002F304
0x14002f2bc  cmp     [rax+1Dh], bl
0x14002f2bf  jnz     short loc_14002F2CB
0x14002f2c1  cmp     [rax+1Eh], bl
0x14002f2c4  jnz     short loc_14002F2CB
0x14002f2c6  cmp     [rax+1Ch], bl
0x14002f2c9  jz      short loc_14002F2D1
0x14002f2cb  lea     rcx, [rax+38h]
0x14002f2cf  jmp     short loc_14002F2B2
0x14002f2d1  lea     r9, WPP_MAIN_CB.Dpc.DeferredContext
0x14002f2d8  xor     edx, edx
0x14002f2da  lea     r8, [rsp+28h+arg_0]
0x14002f2df  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14002f2e6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14002f2ed  nop     dword ptr [rax+rax+00h]
0x14002f2f2  test    eax, eax
0x14002f2f4  jz      short loc_14002F2FF
0x14002f2f6  mov     cs:WPP_MAIN_CB.Dpc.DeferredContext, rbx
0x14002f2fd  jmp     short loc_14002F304
0x14002f2ff  mov     ebx, 1
0x14002f304  call    wil_details_RegisterFeatureUsageProvider
0x14002f309  test    eax, eax
0x14002f30b  jz      short loc_14002F316
0x14002f30d  xor     ecx, ecx
0x14002f30f  test    ebx, ebx
0x14002f311  cmovnz  eax, ecx
0x14002f314  jmp     short loc_14002F318
0x14002f316  xor     eax, eax
0x14002f318  add     rsp, 20h
0x14002f31c  pop     rbx
0x14002f31d  retn
```
