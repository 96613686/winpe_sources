# wil_InitializeFeatureStaging

- ea: `0x14005f62c`
- end: `0x14005f6e5`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14005f078`

## callees

- `0x140009af4`
- `0x14003d39c`
- `0x14003d63c`
- `0x14005f62c`
- `0x14005f6ec`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005f6ac`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005f6ac`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005f654`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005f654`

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
0x14005f62c  push    rbx
0x14005f62e  sub     rsp, 20h
0x14005f632  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x14005f639  mov     [rsp+28h+arg_0], 0
0x14005f642  jnz     loc_14005F6DC
0x14005f648  xor     ebx, ebx
0x14005f64a  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x14005f654  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14005f65b  nop     dword ptr [rax+rax+00h]
0x14005f660  mov     [rsp+28h+arg_0], rax
0x14005f665  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14005f66a  call    wil_details_EvaluateFeatureDependencies
0x14005f66f  lea     rcx, wil_details_featureDescriptors_a
0x14005f676  jmp     short loc_14005F68B
0x14005f678  cmp     [rax+1Dh], bl
0x14005f67b  jnz     short loc_14005F687
0x14005f67d  cmp     [rax+1Eh], bl
0x14005f680  jnz     short loc_14005F687
0x14005f682  cmp     [rax+1Ch], bl
0x14005f685  jz      short loc_14005F697
0x14005f687  lea     rcx, [rax+38h]
0x14005f68b  call    wil_details_FeatureDescriptors_SkipPadding
0x14005f690  test    rax, rax
0x14005f693  jnz     short loc_14005F678
0x14005f695  jmp     short loc_14005F6CA
0x14005f697  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x14005f69e  xor     edx, edx
0x14005f6a0  lea     r8, [rsp+28h+arg_0]
0x14005f6a5  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14005f6ac  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14005f6b3  nop     dword ptr [rax+rax+00h]
0x14005f6b8  test    eax, eax
0x14005f6ba  jz      short loc_14005F6C5
0x14005f6bc  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x14005f6c3  jmp     short loc_14005F6CA
0x14005f6c5  mov     ebx, 1
0x14005f6ca  call    wil_details_RegisterFeatureUsageProvider
0x14005f6cf  test    eax, eax
0x14005f6d1  jz      short loc_14005F6DC
0x14005f6d3  xor     ecx, ecx
0x14005f6d5  test    ebx, ebx
0x14005f6d7  cmovnz  eax, ecx
0x14005f6da  jmp     short loc_14005F6DE
0x14005f6dc  xor     eax, eax
0x14005f6de  add     rsp, 20h
0x14005f6e2  pop     rbx
0x14005f6e3  retn
```
