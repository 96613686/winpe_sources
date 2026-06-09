# wil_InitializeFeatureStaging

- ea: `0x1400bc200`
- end: `0x1400bc2b7`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400bc078`

## callees

- `0x140035e40`
- `0x1400a7fcc`
- `0x1400a826c`
- `0x1400bc200`
- `0x1400bc2c0`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400bc27e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400bc27e`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400bc228`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400bc228`

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
  if ( WPP_MAIN_CB.DeviceLock.Header.LockNV )
    return 0;
  v0 = 0;
  WPP_MAIN_CB.DeviceLock.Header.LockNV = 1;
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
                           &WPP_MAIN_CB.ActiveThreadCount) )
        *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = 0;
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
0x1400bc200  push    rbx
0x1400bc202  sub     rsp, 20h
0x1400bc206  cmp     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header, 0
0x1400bc20d  mov     [rsp+28h+arg_0], 0
0x1400bc216  jnz     loc_1400BC2AE
0x1400bc21c  xor     ebx, ebx
0x1400bc21e  mov     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header, 1
0x1400bc228  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400bc22f  nop     dword ptr [rax+rax+00h]
0x1400bc234  mov     [rsp+28h+arg_0], rax
0x1400bc239  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400bc23e  call    wil_details_EvaluateFeatureDependencies
0x1400bc243  lea     rcx, wil_details_featureDescriptors_a
0x1400bc24a  call    wil_details_FeatureDescriptors_SkipPadding
0x1400bc24f  test    rax, rax
0x1400bc252  jz      short loc_1400BC29C
0x1400bc254  cmp     [rax+1Dh], bl
0x1400bc257  jnz     short loc_1400BC263
0x1400bc259  cmp     [rax+1Eh], bl
0x1400bc25c  jnz     short loc_1400BC263
0x1400bc25e  cmp     [rax+1Ch], bl
0x1400bc261  jz      short loc_1400BC269
0x1400bc263  lea     rcx, [rax+38h]
0x1400bc267  jmp     short loc_1400BC24A
0x1400bc269  lea     r9, WPP_MAIN_CB.ActiveThreadCount
0x1400bc270  xor     edx, edx
0x1400bc272  lea     r8, [rsp+28h+arg_0]
0x1400bc277  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400bc27e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400bc285  nop     dword ptr [rax+rax+00h]
0x1400bc28a  test    eax, eax
0x1400bc28c  jz      short loc_1400BC297
0x1400bc28e  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rbx
0x1400bc295  jmp     short loc_1400BC29C
0x1400bc297  mov     ebx, 1
0x1400bc29c  call    wil_details_RegisterFeatureUsageProvider
0x1400bc2a1  test    eax, eax
0x1400bc2a3  jz      short loc_1400BC2AE
0x1400bc2a5  xor     ecx, ecx
0x1400bc2a7  test    ebx, ebx
0x1400bc2a9  cmovnz  eax, ecx
0x1400bc2ac  jmp     short loc_1400BC2B0
0x1400bc2ae  xor     eax, eax
0x1400bc2b0  add     rsp, 20h
0x1400bc2b4  pop     rbx
0x1400bc2b5  retn
```
