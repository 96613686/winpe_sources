# wil_InitializeFeatureStaging

- ea: `0x1400202b8`
- end: `0x14002036f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140020080`

## callees

- `0x140010464`
- `0x14001dc5c`
- `0x14001defc`
- `0x1400202b8`
- `0x140020378`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140020336`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140020336`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400202e0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400202e0`

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
0x1400202b8  push    rbx
0x1400202ba  sub     rsp, 20h
0x1400202be  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x1400202c5  mov     [rsp+28h+arg_0], 0
0x1400202ce  jnz     loc_140020366
0x1400202d4  xor     ebx, ebx
0x1400202d6  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x1400202e0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400202e7  nop     dword ptr [rax+rax+00h]
0x1400202ec  mov     [rsp+28h+arg_0], rax
0x1400202f1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400202f6  call    wil_details_EvaluateFeatureDependencies
0x1400202fb  lea     rcx, wil_details_featureDescriptors_a
0x140020302  call    wil_details_FeatureDescriptors_SkipPadding
0x140020307  test    rax, rax
0x14002030a  jz      short loc_140020354
0x14002030c  cmp     [rax+1Dh], bl
0x14002030f  jnz     short loc_14002031B
0x140020311  cmp     [rax+1Eh], bl
0x140020314  jnz     short loc_14002031B
0x140020316  cmp     [rax+1Ch], bl
0x140020319  jz      short loc_140020321
0x14002031b  lea     rcx, [rax+38h]
0x14002031f  jmp     short loc_140020302
0x140020321  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140020328  xor     edx, edx
0x14002032a  lea     r8, [rsp+28h+arg_0]
0x14002032f  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140020336  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14002033d  nop     dword ptr [rax+rax+00h]
0x140020342  test    eax, eax
0x140020344  jz      short loc_14002034F
0x140020346  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x14002034d  jmp     short loc_140020354
0x14002034f  mov     ebx, 1
0x140020354  call    wil_details_RegisterFeatureUsageProvider
0x140020359  test    eax, eax
0x14002035b  jz      short loc_140020366
0x14002035d  xor     ecx, ecx
0x14002035f  test    ebx, ebx
0x140020361  cmovnz  eax, ecx
0x140020364  jmp     short loc_140020368
0x140020366  xor     eax, eax
0x140020368  add     rsp, 20h
0x14002036c  pop     rbx
0x14002036d  retn
```
