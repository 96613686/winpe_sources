# wil_InitializeFeatureStaging

- ea: `0x14001a85c`
- end: `0x14001a913`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001a078`

## callees

- `0x140003c5c`
- `0x140017bb0`
- `0x140017e5c`
- `0x14001a85c`
- `0x14001a91c`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001a8da`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001a8da`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14001a884`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14001a884`

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
  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  v0 = 0;
  g_wil_details_isFeatureStagingInitialized = 1;
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
0x14001a85c  push    rbx
0x14001a85e  sub     rsp, 20h
0x14001a862  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14001a869  mov     [rsp+28h+arg_0], 0
0x14001a872  jnz     loc_14001A90A
0x14001a878  xor     ebx, ebx
0x14001a87a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14001a884  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14001a88b  nop     dword ptr [rax+rax+00h]
0x14001a890  mov     [rsp+28h+arg_0], rax
0x14001a895  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14001a89a  call    wil_details_EvaluateFeatureDependencies
0x14001a89f  lea     rcx, wil_details_featureDescriptors_a
0x14001a8a6  call    wil_details_FeatureDescriptors_SkipPadding
0x14001a8ab  test    rax, rax
0x14001a8ae  jz      short loc_14001A8F8
0x14001a8b0  cmp     [rax+1Dh], bl
0x14001a8b3  jnz     short loc_14001A8BF
0x14001a8b5  cmp     [rax+1Eh], bl
0x14001a8b8  jnz     short loc_14001A8BF
0x14001a8ba  cmp     [rax+1Ch], bl
0x14001a8bd  jz      short loc_14001A8C5
0x14001a8bf  lea     rcx, [rax+38h]
0x14001a8c3  jmp     short loc_14001A8A6
0x14001a8c5  lea     r9, g_wil_details_featureChangeNotification
0x14001a8cc  xor     edx, edx
0x14001a8ce  lea     r8, [rsp+28h+arg_0]
0x14001a8d3  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14001a8da  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14001a8e1  nop     dword ptr [rax+rax+00h]
0x14001a8e6  test    eax, eax
0x14001a8e8  jz      short loc_14001A8F3
0x14001a8ea  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14001a8f1  jmp     short loc_14001A8F8
0x14001a8f3  mov     ebx, 1
0x14001a8f8  call    wil_details_RegisterFeatureUsageProvider
0x14001a8fd  test    eax, eax
0x14001a8ff  jz      short loc_14001A90A
0x14001a901  xor     ecx, ecx
0x14001a903  test    ebx, ebx
0x14001a905  cmovnz  eax, ecx
0x14001a908  jmp     short loc_14001A90C
0x14001a90a  xor     eax, eax
0x14001a90c  add     rsp, 20h
0x14001a910  pop     rbx
0x14001a911  retn
```
