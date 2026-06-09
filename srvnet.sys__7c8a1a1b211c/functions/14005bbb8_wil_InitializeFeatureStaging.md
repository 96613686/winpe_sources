# wil_InitializeFeatureStaging

- ea: `0x14005bbb8`
- end: `0x14005bc71`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14005b3c8`

## callees

- `0x1400131bc`
- `0x1400410cc`
- `0x14004222c`
- `0x14005bbb8`
- `0x14005bc78`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005bbe0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005bbe0`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005bc38`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005bc38`

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
  if ( WPP_MAIN_CB.ActiveThreadCount )
    return 0;
  v0 = 0;
  WPP_MAIN_CB.ActiveThreadCount = 1;
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
                           &WPP_MAIN_CB.Dpc.DpcData) )
        WPP_MAIN_CB.Dpc.DpcData = 0;
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
0x14005bbb8  push    rbx
0x14005bbba  sub     rsp, 20h
0x14005bbbe  cmp     cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x14005bbc5  mov     [rsp+28h+arg_0], 0
0x14005bbce  jnz     loc_14005BC68
0x14005bbd4  xor     ebx, ebx
0x14005bbd6  mov     cs:WPP_MAIN_CB.ActiveThreadCount, 1
0x14005bbe0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14005bbe7  nop     dword ptr [rax+rax+00h]
0x14005bbec  mov     [rsp+28h+arg_0], rax
0x14005bbf1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14005bbf6  call    wil_details_EvaluateFeatureDependencies
0x14005bbfb  lea     rcx, wil_details_featureDescriptors_a
0x14005bc02  jmp     short loc_14005BC17
0x14005bc04  cmp     [rax+1Dh], bl
0x14005bc07  jnz     short loc_14005BC13
0x14005bc09  cmp     [rax+1Eh], bl
0x14005bc0c  jnz     short loc_14005BC13
0x14005bc0e  cmp     [rax+1Ch], bl
0x14005bc11  jz      short loc_14005BC23
0x14005bc13  lea     rcx, [rax+38h]
0x14005bc17  call    wil_details_FeatureDescriptors_SkipPadding
0x14005bc1c  test    rax, rax
0x14005bc1f  jnz     short loc_14005BC04
0x14005bc21  jmp     short loc_14005BC56
0x14005bc23  lea     r9, WPP_MAIN_CB.Dpc.DpcData
0x14005bc2a  xor     edx, edx
0x14005bc2c  lea     r8, [rsp+28h+arg_0]
0x14005bc31  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14005bc38  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14005bc3f  nop     dword ptr [rax+rax+00h]
0x14005bc44  test    eax, eax
0x14005bc46  jz      short loc_14005BC51
0x14005bc48  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rbx
0x14005bc4f  jmp     short loc_14005BC56
0x14005bc51  mov     ebx, 1
0x14005bc56  call    wil_details_RegisterFeatureUsageProvider
0x14005bc5b  test    eax, eax
0x14005bc5d  jz      short loc_14005BC68
0x14005bc5f  xor     ecx, ecx
0x14005bc61  test    ebx, ebx
0x14005bc63  cmovnz  eax, ecx
0x14005bc66  jmp     short loc_14005BC6A
0x14005bc68  xor     eax, eax
0x14005bc6a  add     rsp, 20h
0x14005bc6e  pop     rbx
0x14005bc6f  retn
```
