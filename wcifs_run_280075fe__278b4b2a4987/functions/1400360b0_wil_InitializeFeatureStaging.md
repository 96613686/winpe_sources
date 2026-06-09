# wil_InitializeFeatureStaging

- ea: `0x1400360b0`
- end: `0x140036169`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400351b4`

## callees

- `0x140003248`
- `0x14002254c`
- `0x14002279c`
- `0x1400360b0`
- `0x140036170`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400360d8`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400360d8`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140036130`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140036130`

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
  if ( LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) )
    return 0;
  v0 = 0;
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 1;
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
                           &WPP_MAIN_CB.Dpc.DeferredRoutine) )
        WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
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
0x1400360b0  push    rbx
0x1400360b2  sub     rsp, 20h
0x1400360b6  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x1400360bd  mov     [rsp+28h+arg_0], 0
0x1400360c6  jnz     loc_140036160
0x1400360cc  xor     ebx, ebx
0x1400360ce  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x1400360d8  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400360df  nop     dword ptr [rax+rax+00h]
0x1400360e4  mov     [rsp+28h+arg_0], rax
0x1400360e9  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400360ee  call    wil_details_EvaluateFeatureDependencies
0x1400360f3  lea     rcx, wil_details_featureDescriptors_a
0x1400360fa  jmp     short loc_14003610F
0x1400360fc  cmp     [rax+1Dh], bl
0x1400360ff  jnz     short loc_14003610B
0x140036101  cmp     [rax+1Eh], bl
0x140036104  jnz     short loc_14003610B
0x140036106  cmp     [rax+1Ch], bl
0x140036109  jz      short loc_14003611B
0x14003610b  lea     rcx, [rax+38h]
0x14003610f  call    wil_details_FeatureDescriptors_SkipPadding
0x140036114  test    rax, rax
0x140036117  jnz     short loc_1400360FC
0x140036119  jmp     short loc_14003614E
0x14003611b  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140036122  xor     edx, edx
0x140036124  lea     r8, [rsp+28h+arg_0]
0x140036129  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140036130  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140036137  nop     dword ptr [rax+rax+00h]
0x14003613c  test    eax, eax
0x14003613e  jz      short loc_140036149
0x140036140  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x140036147  jmp     short loc_14003614E
0x140036149  mov     ebx, 1
0x14003614e  call    wil_details_RegisterFeatureUsageProvider
0x140036153  test    eax, eax
0x140036155  jz      short loc_140036160
0x140036157  xor     ecx, ecx
0x140036159  test    ebx, ebx
0x14003615b  cmovnz  eax, ecx
0x14003615e  jmp     short loc_140036162
0x140036160  xor     eax, eax
0x140036162  add     rsp, 20h
0x140036166  pop     rbx
0x140036167  retn
```
