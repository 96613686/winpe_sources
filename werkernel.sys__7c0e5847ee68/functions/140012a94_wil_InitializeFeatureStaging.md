# wil_InitializeFeatureStaging

- ea: `0x140012a94`
- end: `0x140012bf5`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012080`

## callees

- `0x140010790`
- `0x140012a94`
- `0x140012bfc`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x140012bbe`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x140012bbe`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140012b4a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140012b4a`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140012ac5`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140012ac5`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // edi
  __int64 **v1; // rbx
  __int64 **v2; // rax
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
  v1 = wil_details_featureDescriptors_a;
  v2 = wil_details_featureDescriptors_a;
  if ( wil_details_featureDescriptors_a < (__int64 **)wil_details_featureDescriptors_z )
  {
    while ( !*v2 )
    {
      if ( ++v2 >= (__int64 **)wil_details_featureDescriptors_z )
        goto LABEL_19;
    }
LABEL_14:
    if ( v2 )
    {
      if ( *((_BYTE *)v2 + 29) || *((_BYTE *)v2 + 30) || *((_BYTE *)v2 + 28) )
      {
        for ( v2 += 7; v2 < (__int64 **)wil_details_featureDescriptors_z; ++v2 )
        {
          if ( *v2 )
            goto LABEL_14;
        }
      }
      else if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                                wil_details_ReevaluateOnFeatureConfigurationChange,
                                0,
                                &v6,
                                &g_wil_details_featureChangeNotification) )
      {
        g_wil_details_featureChangeNotification = 0;
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
  g_wil_details_recordFeatureUsage = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))wil_details_RecordFeatureUsageReporting;
  while ( v1 < (__int64 **)wil_details_featureDescriptors_z )
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
0x140012a94  mov     [rsp+arg_8], rbx
0x140012a99  mov     [rsp+arg_10], rbp
0x140012a9e  push    rdi
0x140012a9f  sub     rsp, 40h
0x140012aa3  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140012aaa  mov     [rsp+48h+arg_0], 0
0x140012ab3  jnz     loc_140012BE2
0x140012ab9  xor     edi, edi
0x140012abb  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140012ac5  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140012acc  nop     dword ptr [rax+rax+00h]
0x140012ad1  mov     [rsp+48h+arg_0], rax
0x140012ad6  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140012adb  call    wil_details_EvaluateFeatureDependencies
0x140012ae0  lea     rbx, wil_details_featureDescriptors_a
0x140012ae7  lea     rbp, wil_details_featureDescriptors_z
0x140012aee  mov     rax, rbx
0x140012af1  cmp     rbx, rbp
0x140012af4  jnb     short loc_140012B68
0x140012af6  cmp     [rax], rdi
0x140012af9  jnz     short loc_140012B2E
0x140012afb  add     rax, 8
0x140012aff  cmp     rax, rbp
0x140012b02  jb      short loc_140012AF6
0x140012b04  jmp     short loc_140012B68
0x140012b06  cmp     [rax+1Dh], dil
0x140012b0a  jnz     short loc_140012B18
0x140012b0c  cmp     [rax+1Eh], dil
0x140012b10  jnz     short loc_140012B18
0x140012b12  cmp     [rax+1Ch], dil
0x140012b16  jz      short loc_140012B35
0x140012b18  add     rax, 38h ; '8'
0x140012b1c  jmp     short loc_140012B27
0x140012b1e  cmp     [rax], rdi
0x140012b21  jnz     short loc_140012B2E
0x140012b23  add     rax, 8
0x140012b27  cmp     rax, rbp
0x140012b2a  jb      short loc_140012B1E
0x140012b2c  jmp     short loc_140012B68
0x140012b2e  test    rax, rax
0x140012b31  jnz     short loc_140012B06
0x140012b33  jmp     short loc_140012B68
0x140012b35  lea     r9, g_wil_details_featureChangeNotification
0x140012b3c  xor     edx, edx
0x140012b3e  lea     r8, [rsp+48h+arg_0]
0x140012b43  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140012b4a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140012b51  nop     dword ptr [rax+rax+00h]
0x140012b56  test    eax, eax
0x140012b58  jz      short loc_140012B63
0x140012b5a  mov     cs:g_wil_details_featureChangeNotification, rdi
0x140012b61  jmp     short loc_140012B68
0x140012b63  mov     edi, 1
0x140012b68  xor     eax, eax
0x140012b6a  xorps   xmm0, xmm0
0x140012b6d  mov     [rsp+48h+var_18], rax
0x140012b72  lea     rax, wil_details_RecordFeatureUsageReporting
0x140012b79  movups  [rsp+48h+var_28], xmm0
0x140012b7e  mov     cs:g_wil_details_recordFeatureUsage, rax
0x140012b85  jmp     short loc_140012B91
0x140012b87  cmp     qword ptr [rbx], 0
0x140012b8b  jnz     short loc_140012B98
0x140012b8d  add     rbx, 8
0x140012b91  cmp     rbx, rbp
0x140012b94  jb      short loc_140012B87
0x140012b96  xor     ebx, ebx
0x140012b98  lea     r8, g_wil_details_featureUsageProvider
0x140012b9f  mov     qword ptr [rsp+48h+var_28], rbx
0x140012ba4  lea     rdx, [rsp+48h+var_28]
0x140012ba9  mov     qword ptr [rsp+48h+var_28+8], rbp
0x140012bae  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x140012bb5  mov     [rsp+48h+var_18], 0
0x140012bbe  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x140012bc5  nop     dword ptr [rax+rax+00h]
0x140012bca  test    eax, eax
0x140012bcc  jz      short loc_140012BE2
0x140012bce  xor     ecx, ecx
0x140012bd0  mov     cs:g_wil_details_featureUsageProvider, 0
0x140012bdb  test    edi, edi
0x140012bdd  cmovnz  eax, ecx
0x140012be0  jmp     short loc_140012BE4
0x140012be2  xor     eax, eax
0x140012be4  mov     rbx, [rsp+48h+arg_8]
0x140012be9  mov     rbp, [rsp+48h+arg_10]
0x140012bee  add     rsp, 40h
0x140012bf2  pop     rdi
0x140012bf3  retn
```
