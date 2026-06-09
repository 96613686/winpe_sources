# wil_InitializeFeatureStaging

- ea: `0x1400946d8`
- end: `0x140094839`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14009403c`

## callees

- `0x1400784a4`
- `0x1400946d8`
- `0x140094840`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x140094802`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x140094802`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140094709`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140094709`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14009478e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14009478e`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // edi
  __int64 *v1; // rbx
  _UNKNOWN **v2; // rax
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = 0;
  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  v0 = 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  v6 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  v1 = (__int64 *)&wil_details_featureDescriptors_a;
  v2 = &wil_details_featureDescriptors_a;
  if ( &wil_details_featureDescriptors_a < (_UNKNOWN **)wil_details_featureDescriptors_z )
  {
    while ( !*v2 )
    {
      if ( ++v2 >= (_UNKNOWN **)wil_details_featureDescriptors_z )
        goto LABEL_19;
    }
LABEL_14:
    if ( v2 )
    {
      if ( *((_BYTE *)v2 + 29) || *((_BYTE *)v2 + 30) || *((_BYTE *)v2 + 28) )
      {
        for ( v2 += 7; v2 < (_UNKNOWN **)wil_details_featureDescriptors_z; ++v2 )
        {
          if ( *v2 )
            goto LABEL_14;
        }
      }
      else if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                                wil_details_ReevaluateOnFeatureConfigurationChange,
                                0,
                                &v6,
                                &WPP_MAIN_CB.ActiveThreadCount) )
      {
        *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = 0;
      }
      else
      {
        v0 = 1;
      }
    }
  }
LABEL_19:
  v5 = 0;
  v4 = 0;
  g_wil_details_recordFeatureUsage = (__int64)wil_details_RecordFeatureUsageReporting;
  while ( v1 < wil_details_featureDescriptors_z )
  {
    if ( *v1 )
      goto LABEL_24;
    ++v1;
  }
  v1 = 0;
LABEL_24:
  *(_QWORD *)&v4 = v1;
  *((_QWORD *)&v4 + 1) = wil_details_featureDescriptors_z;
  v5 = 0;
  result = RtlRegisterFeatureUsageProvider(
             wil_details_OnFeatureUsageProviderFlushNotification,
             &v4,
             &g_wil_details_featureUsageProvider);
  if ( !(_DWORD)result )
    return 0;
  g_wil_details_featureUsageProvider = 0;
  if ( v0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1400946d8  mov     [rsp+arg_8], rbx
0x1400946dd  mov     [rsp+arg_10], rbp
0x1400946e2  push    rdi
0x1400946e3  sub     rsp, 40h
0x1400946e7  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400946ee  mov     [rsp+48h+arg_0], 0
0x1400946f7  jnz     loc_140094826
0x1400946fd  xor     edi, edi
0x1400946ff  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140094709  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140094710  nop     dword ptr [rax+rax+00h]
0x140094715  mov     [rsp+48h+arg_0], rax
0x14009471a  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14009471f  call    wil_details_EvaluateFeatureDependencies
0x140094724  lea     rbx, wil_details_featureDescriptors_a
0x14009472b  lea     rbp, wil_details_featureDescriptors_z
0x140094732  mov     rax, rbx
0x140094735  cmp     rbx, rbp
0x140094738  jnb     short loc_1400947AC
0x14009473a  cmp     [rax], rdi
0x14009473d  jnz     short loc_140094772
0x14009473f  add     rax, 8
0x140094743  cmp     rax, rbp
0x140094746  jb      short loc_14009473A
0x140094748  jmp     short loc_1400947AC
0x14009474a  cmp     [rax+1Dh], dil
0x14009474e  jnz     short loc_14009475C
0x140094750  cmp     [rax+1Eh], dil
0x140094754  jnz     short loc_14009475C
0x140094756  cmp     [rax+1Ch], dil
0x14009475a  jz      short loc_140094779
0x14009475c  add     rax, 38h ; '8'
0x140094760  jmp     short loc_14009476B
0x140094762  cmp     [rax], rdi
0x140094765  jnz     short loc_140094772
0x140094767  add     rax, 8
0x14009476b  cmp     rax, rbp
0x14009476e  jb      short loc_140094762
0x140094770  jmp     short loc_1400947AC
0x140094772  test    rax, rax
0x140094775  jnz     short loc_14009474A
0x140094777  jmp     short loc_1400947AC
0x140094779  lea     r9, WPP_MAIN_CB.ActiveThreadCount
0x140094780  xor     edx, edx
0x140094782  lea     r8, [rsp+48h+arg_0]
0x140094787  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14009478e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140094795  nop     dword ptr [rax+rax+00h]
0x14009479a  test    eax, eax
0x14009479c  jz      short loc_1400947A7
0x14009479e  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rdi
0x1400947a5  jmp     short loc_1400947AC
0x1400947a7  mov     edi, 1
0x1400947ac  xor     eax, eax
0x1400947ae  xorps   xmm0, xmm0
0x1400947b1  mov     [rsp+48h+var_18], rax
0x1400947b6  lea     rax, wil_details_RecordFeatureUsageReporting
0x1400947bd  movups  [rsp+48h+var_28], xmm0
0x1400947c2  mov     cs:g_wil_details_recordFeatureUsage, rax
0x1400947c9  jmp     short loc_1400947D5
0x1400947cb  cmp     qword ptr [rbx], 0
0x1400947cf  jnz     short loc_1400947DC
0x1400947d1  add     rbx, 8
0x1400947d5  cmp     rbx, rbp
0x1400947d8  jb      short loc_1400947CB
0x1400947da  xor     ebx, ebx
0x1400947dc  lea     r8, g_wil_details_featureUsageProvider
0x1400947e3  mov     qword ptr [rsp+48h+var_28], rbx
0x1400947e8  lea     rdx, [rsp+48h+var_28]
0x1400947ed  mov     qword ptr [rsp+48h+var_28+8], rbp
0x1400947f2  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x1400947f9  mov     [rsp+48h+var_18], 0
0x140094802  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x140094809  nop     dword ptr [rax+rax+00h]
0x14009480e  test    eax, eax
0x140094810  jz      short loc_140094826
0x140094812  xor     ecx, ecx
0x140094814  mov     cs:g_wil_details_featureUsageProvider, 0
0x14009481f  test    edi, edi
0x140094821  cmovnz  eax, ecx
0x140094824  jmp     short loc_140094828
0x140094826  xor     eax, eax
0x140094828  mov     rbx, [rsp+48h+arg_8]
0x14009482d  mov     rbp, [rsp+48h+arg_10]
0x140094832  add     rsp, 40h
0x140094836  pop     rdi
0x140094837  retn
```
