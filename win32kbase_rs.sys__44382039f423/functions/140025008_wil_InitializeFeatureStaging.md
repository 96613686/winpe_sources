# wil_InitializeFeatureStaging

- ea: `0x140025008`
- end: `0x140025166`
- name: `wil_InitializeFeatureStaging`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400252f4`

## callees

- `0x14002332c`
- `0x140025008`
- `0x14002516c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140025039`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140025039`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400250be`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400250be`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14002512f`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14002512f`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  __int64 *v0; // rbx
  __int64 result; // rax
  __int128 v2; // [rsp+20h] [rbp-28h] BYREF
  __int64 v3; // [rsp+30h] [rbp-18h]

  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  v0 = wil_details_featureDescriptors_a;
  v3 = 0;
  v2 = 0;
  g_wil_details_recordFeatureUsage = (__int64)wil_details_RecordFeatureUsageReporting;
  while ( v0 < wil_details_featureDescriptors_a )
  {
    if ( *v0 )
      goto LABEL_7;
    ++v0;
  }
  v0 = 0;
LABEL_7:
  *(_QWORD *)&v2 = v0;
  *((_QWORD *)&v2 + 1) = wil_details_featureDescriptors_a;
  v3 = 0;
  result = RtlRegisterFeatureUsageProvider(
             wil_details_OnFeatureUsageProviderFlushNotification,
             &v2,
             &g_wil_details_featureUsageProvider);
  if ( !(_DWORD)result )
    return 0;
  g_wil_details_featureUsageProvider = 0;
  return result;
}

```

## disassembly

```asm
0x140025008  mov     [rsp+arg_8], rbx
0x14002500d  mov     [rsp+arg_10], rbp
0x140025012  push    rdi
0x140025013  sub     rsp, 40h
0x140025017  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14002501e  mov     [rsp+48h+arg_0], 0
0x140025027  jnz     loc_140025153
0x14002502d  xor     edi, edi
0x14002502f  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140025039  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140025040  nop     dword ptr [rax+rax+00h]
0x140025045  mov     [rsp+48h+arg_0], rax
0x14002504a  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14002504f  call    wil_details_EvaluateFeatureDependencies
0x140025054  lea     rbx, wil_details_featureDescriptors_a
0x14002505b  lea     rbp, wil_details_featureDescriptors_a
0x140025062  mov     rax, rbx
0x140025065  cmp     rbx, rbp
0x140025068  jnb     short loc_1400250D9
0x14002506a  cmp     [rax], rdi
0x14002506d  jnz     short loc_1400250A2
0x14002506f  add     rax, 8
0x140025073  cmp     rax, rbp
0x140025076  jb      short loc_14002506A
0x140025078  jmp     short loc_1400250D9
0x14002507a  cmp     [rax+1Dh], dil
0x14002507e  jnz     short loc_14002508C
0x140025080  cmp     [rax+1Eh], dil
0x140025084  jnz     short loc_14002508C
0x140025086  cmp     [rax+1Ch], dil
0x14002508a  jz      short loc_1400250A9
0x14002508c  add     rax, 38h ; '8'
0x140025090  jmp     short loc_14002509B
0x140025092  cmp     [rax], rdi
0x140025095  jnz     short loc_1400250A2
0x140025097  add     rax, 8
0x14002509b  cmp     rax, rbp
0x14002509e  jb      short loc_140025092
0x1400250a0  jmp     short loc_1400250D9
0x1400250a2  test    rax, rax
0x1400250a5  jnz     short loc_14002507A
0x1400250a7  jmp     short loc_1400250D9
0x1400250a9  lea     r9, g_wil_details_featureChangeNotification
0x1400250b0  xor     edx, edx
0x1400250b2  lea     r8, [rsp+48h+arg_0]
0x1400250b7  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400250be  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400250c5  nop     dword ptr [rax+rax+00h]
0x1400250ca  test    eax, eax
0x1400250cc  jz      short loc_1400250D5
0x1400250ce  mov     cs:g_wil_details_featureChangeNotification, rdi
0x1400250d5  setz    dil
0x1400250d9  xor     eax, eax
0x1400250db  xorps   xmm0, xmm0
0x1400250de  mov     [rsp+48h+var_18], rax
0x1400250e3  lea     rax, wil_details_RecordFeatureUsageReporting
0x1400250ea  movups  [rsp+48h+var_28], xmm0
0x1400250ef  mov     cs:g_wil_details_recordFeatureUsage, rax
0x1400250f6  jmp     short loc_140025102
0x1400250f8  cmp     qword ptr [rbx], 0
0x1400250fc  jnz     short loc_140025109
0x1400250fe  add     rbx, 8
0x140025102  cmp     rbx, rbp
0x140025105  jb      short loc_1400250F8
0x140025107  xor     ebx, ebx
0x140025109  lea     r8, g_wil_details_featureUsageProvider
0x140025110  mov     qword ptr [rsp+48h+var_28], rbx
0x140025115  lea     rdx, [rsp+48h+var_28]
0x14002511a  mov     qword ptr [rsp+48h+var_28+8], rbp
0x14002511f  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x140025126  mov     [rsp+48h+var_18], 0
0x14002512f  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x140025136  nop     dword ptr [rax+rax+00h]
0x14002513b  test    eax, eax
0x14002513d  jz      short loc_140025153
0x14002513f  xor     ecx, ecx
0x140025141  mov     cs:g_wil_details_featureUsageProvider, 0
0x14002514c  test    edi, edi
0x14002514e  cmovnz  eax, ecx
0x140025151  jmp     short loc_140025155
0x140025153  xor     eax, eax
0x140025155  mov     rbx, [rsp+48h+arg_8]
0x14002515a  mov     rbp, [rsp+48h+arg_10]
0x14002515f  add     rsp, 40h
0x140025163  pop     rdi
0x140025164  retn
```
