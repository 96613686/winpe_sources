# wil_InitializeFeatureStaging

- ea: `0x1400360a4`
- end: `0x14003615d`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400351b4`

## callees

- `0x140003248`
- `0x14002254c`
- `0x1400227ec`
- `0x1400360a4`
- `0x140036164`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400360cc`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400360cc`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140036124`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140036124`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  PDEVICE_OBJECT *i; // rcx
  PDEVICE_OBJECT *v2; // rax
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
  for ( i = &wil_details_featureDescriptors_a; ; i = v2 + 7 )
  {
    v2 = wil_details_FeatureDescriptors_SkipPadding(i);
    if ( !v2 )
      break;
    if ( !*((_BYTE *)v2 + 29) && !*((_BYTE *)v2 + 30) && !*((_BYTE *)v2 + 28) )
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
0x1400360a4  push    rbx
0x1400360a6  sub     rsp, 20h
0x1400360aa  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x1400360b1  mov     [rsp+28h+arg_0], 0
0x1400360ba  jnz     loc_140036154
0x1400360c0  xor     ebx, ebx
0x1400360c2  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x1400360cc  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400360d3  nop     dword ptr [rax+rax+00h]
0x1400360d8  mov     [rsp+28h+arg_0], rax
0x1400360dd  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400360e2  call    wil_details_EvaluateFeatureDependencies
0x1400360e7  lea     rcx, wil_details_featureDescriptors_a
0x1400360ee  jmp     short loc_140036103
0x1400360f0  cmp     [rax+1Dh], bl
0x1400360f3  jnz     short loc_1400360FF
0x1400360f5  cmp     [rax+1Eh], bl
0x1400360f8  jnz     short loc_1400360FF
0x1400360fa  cmp     [rax+1Ch], bl
0x1400360fd  jz      short loc_14003610F
0x1400360ff  lea     rcx, [rax+38h]
0x140036103  call    wil_details_FeatureDescriptors_SkipPadding
0x140036108  test    rax, rax
0x14003610b  jnz     short loc_1400360F0
0x14003610d  jmp     short loc_140036142
0x14003610f  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140036116  xor     edx, edx
0x140036118  lea     r8, [rsp+28h+arg_0]
0x14003611d  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140036124  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14003612b  nop     dword ptr [rax+rax+00h]
0x140036130  test    eax, eax
0x140036132  jz      short loc_14003613D
0x140036134  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x14003613b  jmp     short loc_140036142
0x14003613d  mov     ebx, 1
0x140036142  call    wil_details_RegisterFeatureUsageProvider
0x140036147  test    eax, eax
0x140036149  jz      short loc_140036154
0x14003614b  xor     ecx, ecx
0x14003614d  test    ebx, ebx
0x14003614f  cmovnz  eax, ecx
0x140036152  jmp     short loc_140036156
0x140036154  xor     eax, eax
0x140036156  add     rsp, 20h
0x14003615a  pop     rbx
0x14003615b  retn
```
