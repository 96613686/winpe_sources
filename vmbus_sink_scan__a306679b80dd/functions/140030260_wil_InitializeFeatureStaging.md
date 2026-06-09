# wil_InitializeFeatureStaging

- ea: `0x140030260`
- end: `0x140030317`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003003c`

## callees

- `0x140003944`
- `0x14002794c`
- `0x140027b9c`
- `0x140030260`
- `0x140030320`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400302de`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400302de`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140030288`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140030288`

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
0x140030260  push    rbx
0x140030262  sub     rsp, 20h
0x140030266  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x14003026d  mov     [rsp+28h+arg_0], 0
0x140030276  jnz     loc_14003030E
0x14003027c  xor     ebx, ebx
0x14003027e  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x140030288  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14003028f  nop     dword ptr [rax+rax+00h]
0x140030294  mov     [rsp+28h+arg_0], rax
0x140030299  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14003029e  call    wil_details_EvaluateFeatureDependencies
0x1400302a3  lea     rcx, wil_details_featureDescriptors_a
0x1400302aa  call    wil_details_FeatureDescriptors_SkipPadding
0x1400302af  test    rax, rax
0x1400302b2  jz      short loc_1400302FC
0x1400302b4  cmp     [rax+1Dh], bl
0x1400302b7  jnz     short loc_1400302C3
0x1400302b9  cmp     [rax+1Eh], bl
0x1400302bc  jnz     short loc_1400302C3
0x1400302be  cmp     [rax+1Ch], bl
0x1400302c1  jz      short loc_1400302C9
0x1400302c3  lea     rcx, [rax+38h]
0x1400302c7  jmp     short loc_1400302AA
0x1400302c9  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x1400302d0  xor     edx, edx
0x1400302d2  lea     r8, [rsp+28h+arg_0]
0x1400302d7  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400302de  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400302e5  nop     dword ptr [rax+rax+00h]
0x1400302ea  test    eax, eax
0x1400302ec  jz      short loc_1400302F7
0x1400302ee  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x1400302f5  jmp     short loc_1400302FC
0x1400302f7  mov     ebx, 1
0x1400302fc  call    wil_details_RegisterFeatureUsageProvider
0x140030301  test    eax, eax
0x140030303  jz      short loc_14003030E
0x140030305  xor     ecx, ecx
0x140030307  test    ebx, ebx
0x140030309  cmovnz  eax, ecx
0x14003030c  jmp     short loc_140030310
0x14003030e  xor     eax, eax
0x140030310  add     rsp, 20h
0x140030314  pop     rbx
0x140030315  retn
```
