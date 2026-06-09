# wil_InitializeFeatureStaging

- ea: `0x140016920`
- end: `0x1400169d7`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400161ec`

## callees

- `0x1400084a4`
- `0x14001396c`
- `0x140013bbc`
- `0x140016920`
- `0x1400169e0`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001699e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001699e`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140016948`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140016948`

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
  if ( WPP_MAIN_CB.Dpc.TargetInfoAsUlong )
    return 0;
  v0 = 0;
  WPP_MAIN_CB.Dpc.TargetInfoAsUlong = 1;
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
                           &WPP_MAIN_CB.DeviceQueue.Busy) )
        WPP_MAIN_CB.DeviceQueue.1 = 0;
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
0x140016920  push    rbx
0x140016922  sub     rsp, 20h
0x140016926  cmp     dword ptr cs:WPP_MAIN_CB.Dpc, 0
0x14001692d  mov     [rsp+28h+arg_0], 0
0x140016936  jnz     loc_1400169CE
0x14001693c  xor     ebx, ebx
0x14001693e  mov     dword ptr cs:WPP_MAIN_CB.Dpc, 1
0x140016948  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14001694f  nop     dword ptr [rax+rax+00h]
0x140016954  mov     [rsp+28h+arg_0], rax
0x140016959  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14001695e  call    wil_details_EvaluateFeatureDependencies
0x140016963  lea     rcx, wil_details_featureDescriptors_a
0x14001696a  call    wil_details_FeatureDescriptors_SkipPadding
0x14001696f  test    rax, rax
0x140016972  jz      short loc_1400169BC
0x140016974  cmp     [rax+1Dh], bl
0x140016977  jnz     short loc_140016983
0x140016979  cmp     [rax+1Eh], bl
0x14001697c  jnz     short loc_140016983
0x14001697e  cmp     [rax+1Ch], bl
0x140016981  jz      short loc_140016989
0x140016983  lea     rcx, [rax+38h]
0x140016987  jmp     short loc_14001696A
0x140016989  lea     r9, WPP_MAIN_CB.DeviceQueue.20h
0x140016990  xor     edx, edx
0x140016992  lea     r8, [rsp+28h+arg_0]
0x140016997  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14001699e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400169a5  nop     dword ptr [rax+rax+00h]
0x1400169aa  test    eax, eax
0x1400169ac  jz      short loc_1400169B7
0x1400169ae  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rbx
0x1400169b5  jmp     short loc_1400169BC
0x1400169b7  mov     ebx, 1
0x1400169bc  call    wil_details_RegisterFeatureUsageProvider
0x1400169c1  test    eax, eax
0x1400169c3  jz      short loc_1400169CE
0x1400169c5  xor     ecx, ecx
0x1400169c7  test    ebx, ebx
0x1400169c9  cmovnz  eax, ecx
0x1400169cc  jmp     short loc_1400169D0
0x1400169ce  xor     eax, eax
0x1400169d0  add     rsp, 20h
0x1400169d4  pop     rbx
0x1400169d5  retn
```
