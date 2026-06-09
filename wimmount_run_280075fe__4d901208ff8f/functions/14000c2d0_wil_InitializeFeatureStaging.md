# wil_InitializeFeatureStaging

- ea: `0x14000c2d0`
- end: `0x14000c4ca`
- name: `wil_InitializeFeatureStaging`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000c078`

## callees

- `0x140002c90`
- `0x14000a41c`
- `0x14000c2d0`
- `0x14000c4d0`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c321`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c3cb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c46f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c321`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c3cb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c46f`

## string_xrefs

- `0x14000c30a`: `RtlQueryFeatureConfigurationChangeStamp`
- `0x14000c3b4`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  __int64 (*SystemRoutineAddress)(void); // rax
  int v1; // edi
  int **v2; // rbx
  int **v3; // rax
  unsigned int (__fastcall *v4)(__int64 (__fastcall *)(), _QWORD, __int64 (**)(void), __int64 *); // rax
  __int64 (__fastcall *v5)(__int64 (__fastcall *)(), __int128 *, __int64 *); // rax
  __int64 result; // rax
  struct _UNICODE_STRING SystemRoutineName; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING v8; // [rsp+40h] [rbp-38h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h] BYREF
  __int64 v10; // [rsp+60h] [rbp-18h]
  __int64 (*v11)(void); // [rsp+A0h] [rbp+28h] BYREF

  v11 = 0;
  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  SystemRoutineAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfigurationChangeStamp;
  v1 = 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  if ( g_wil_details_pfnRtlQueryFeatureConfigurationChangeStamp
    || (*(_QWORD *)&SystemRoutineName.Length = 5242958,
        SystemRoutineName.Buffer = L"RtlQueryFeatureConfigurationChangeStamp",
        SystemRoutineAddress = (__int64 (*)(void))MmGetSystemRoutineAddress(&SystemRoutineName),
        (g_wil_details_pfnRtlQueryFeatureConfigurationChangeStamp = (__int64)SystemRoutineAddress) != 0) )
  {
    SystemRoutineAddress = (__int64 (*)(void))SystemRoutineAddress();
  }
  v11 = SystemRoutineAddress;
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  v2 = wil_details_featureDescriptors_a;
  v3 = wil_details_featureDescriptors_a;
  if ( wil_details_featureDescriptors_a < (int **)wil_details_featureDescriptors_z )
  {
    while ( !*v3 )
    {
      if ( ++v3 >= (int **)wil_details_featureDescriptors_z )
        goto LABEL_24;
    }
LABEL_17:
    if ( v3 )
    {
      if ( *((_BYTE *)v3 + 29) || *((_BYTE *)v3 + 30) || *((_BYTE *)v3 + 28) )
      {
        for ( v3 += 7; v3 < (int **)wil_details_featureDescriptors_z; ++v3 )
        {
          if ( *v3 )
            goto LABEL_17;
        }
      }
      else
      {
        v4 = (unsigned int (__fastcall *)(__int64 (__fastcall *)(), _QWORD, __int64 (**)(void), __int64 *))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
        if ( (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
           || (*(_QWORD *)&SystemRoutineName.Length = 6553698,
               SystemRoutineName.Buffer = L"RtlRegisterFeatureConfigurationChangeNotification",
               v4 = (unsigned int (__fastcall *)(__int64 (__fastcall *)(), _QWORD, __int64 (**)(void), __int64 *))MmGetSystemRoutineAddress(&SystemRoutineName),
               (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)v4) != 0))
          && !v4(wil_details_ReevaluateOnFeatureConfigurationChange, 0, &v11, &g_wil_details_featureChangeNotification) )
        {
          v1 = 1;
        }
        else
        {
          g_wil_details_featureChangeNotification = 0;
        }
      }
    }
  }
LABEL_24:
  v10 = 0;
  v9 = 0;
  g_wil_details_recordFeatureUsage = (__int64)wil_details_RecordFeatureUsageReporting;
  while ( v2 < (int **)wil_details_featureDescriptors_z )
  {
    if ( *v2 )
      goto LABEL_29;
    ++v2;
  }
  v2 = 0;
LABEL_29:
  v5 = (__int64 (__fastcall *)(__int64 (__fastcall *)(), __int128 *, __int64 *))g_wil_details_pfnRtlRegisterFeatureUsageProvider;
  *(_QWORD *)&v9 = v2;
  *((_QWORD *)&v9 + 1) = wil_details_featureDescriptors_z;
  v10 = 0;
  if ( !g_wil_details_pfnRtlRegisterFeatureUsageProvider )
  {
    *(_QWORD *)&v8.Length = 4194366;
    v8.Buffer = L"RtlRegisterFeatureUsageProvider";
    v5 = (__int64 (__fastcall *)(__int64 (__fastcall *)(), __int128 *, __int64 *))MmGetSystemRoutineAddress(&v8);
    g_wil_details_pfnRtlRegisterFeatureUsageProvider = (__int64)v5;
    if ( !v5 )
    {
      result = 3221225785LL;
      goto LABEL_33;
    }
  }
  result = v5(wil_details_OnFeatureUsageProviderFlushNotification, &v9, &g_wil_details_featureUsageProvider);
  if ( !(_DWORD)result )
    return 0;
LABEL_33:
  g_wil_details_featureUsageProvider = 0;
  if ( v1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14000c2d0  push    rbp
0x14000c2d2  push    rbx
0x14000c2d3  push    rdi
0x14000c2d4  push    r14
0x14000c2d6  mov     rbp, rsp
0x14000c2d9  sub     rsp, 78h
0x14000c2dd  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000c2e4  mov     [rbp+arg_0], 0
0x14000c2ec  jnz     loc_14000C4BD
0x14000c2f2  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfigurationChangeStamp
0x14000c2f9  xor     edi, edi
0x14000c2fb  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14000c305  test    rax, rax
0x14000c308  jnz     short loc_14000C339
0x14000c30a  lea     rax, aRtlqueryfeatur_0; "RtlQueryFeatureConfigurationChangeStamp"
0x14000c311  mov     qword ptr [rbp+SystemRoutineName.Length], 50004Eh
0x14000c319  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14000c31d  mov     [rbp+SystemRoutineName.Buffer], rax
0x14000c321  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c328  nop     dword ptr [rax+rax+00h]
0x14000c32d  mov     cs:g_wil_details_pfnRtlQueryFeatureConfigurationChangeStamp, rax
0x14000c334  test    rax, rax
0x14000c337  jz      short loc_14000C33E
0x14000c339  call    _guard_dispatch_icall
0x14000c33e  mov     [rbp+arg_0], rax
0x14000c342  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14000c347  call    wil_details_EvaluateFeatureDependencies
0x14000c34c  lea     rbx, wil_details_featureDescriptors_a
0x14000c353  lea     r14, wil_details_featureDescriptors_z
0x14000c35a  mov     rax, rbx
0x14000c35d  cmp     rbx, r14
0x14000c360  jnb     loc_14000C40E
0x14000c366  cmp     [rax], rdi
0x14000c369  jnz     short loc_14000C3A1
0x14000c36b  add     rax, 8
0x14000c36f  cmp     rax, r14
0x14000c372  jb      short loc_14000C366
0x14000c374  jmp     loc_14000C40E
0x14000c379  cmp     [rax+1Dh], dil
0x14000c37d  jnz     short loc_14000C38B
0x14000c37f  cmp     [rax+1Eh], dil
0x14000c383  jnz     short loc_14000C38B
0x14000c385  cmp     [rax+1Ch], dil
0x14000c389  jz      short loc_14000C3A8
0x14000c38b  add     rax, 38h ; '8'
0x14000c38f  jmp     short loc_14000C39A
0x14000c391  cmp     [rax], rdi
0x14000c394  jnz     short loc_14000C3A1
0x14000c396  add     rax, 8
0x14000c39a  cmp     rax, r14
0x14000c39d  jb      short loc_14000C391
0x14000c39f  jmp     short loc_14000C40E
0x14000c3a1  test    rax, rax
0x14000c3a4  jnz     short loc_14000C379
0x14000c3a6  jmp     short loc_14000C40E
0x14000c3a8  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000c3af  test    rax, rax
0x14000c3b2  jnz     short loc_14000C3E3
0x14000c3b4  lea     rax, aRtlregisterfea_0; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000c3bb  mov     qword ptr [rbp+SystemRoutineName.Length], 640062h
0x14000c3c3  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14000c3c7  mov     [rbp+SystemRoutineName.Buffer], rax
0x14000c3cb  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c3d2  nop     dword ptr [rax+rax+00h]
0x14000c3d7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000c3de  test    rax, rax
0x14000c3e1  jz      short loc_14000C400
0x14000c3e3  lea     r9, g_wil_details_featureChangeNotification
0x14000c3ea  xor     edx, edx
0x14000c3ec  lea     r8, [rbp+arg_0]
0x14000c3f0  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14000c3f7  call    _guard_dispatch_icall
0x14000c3fc  test    eax, eax
0x14000c3fe  jz      short loc_14000C409
0x14000c400  mov     cs:g_wil_details_featureChangeNotification, rdi
0x14000c407  jmp     short loc_14000C40E
0x14000c409  mov     edi, 1
0x14000c40e  xor     eax, eax
0x14000c410  xorps   xmm0, xmm0
0x14000c413  mov     [rbp+var_18], rax
0x14000c417  lea     rax, wil_details_RecordFeatureUsageReporting
0x14000c41e  movups  [rbp+var_28], xmm0
0x14000c422  mov     cs:g_wil_details_recordFeatureUsage, rax
0x14000c429  jmp     short loc_14000C435
0x14000c42b  cmp     qword ptr [rbx], 0
0x14000c42f  jnz     short loc_14000C43C
0x14000c431  add     rbx, 8
0x14000c435  cmp     rbx, r14
0x14000c438  jb      short loc_14000C42B
0x14000c43a  xor     ebx, ebx
0x14000c43c  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureUsageProvider
0x14000c443  mov     qword ptr [rbp+var_28], rbx
0x14000c447  mov     qword ptr [rbp+var_28+8], r14
0x14000c44b  mov     [rbp+var_18], 0
0x14000c453  test    rax, rax
0x14000c456  jnz     short loc_14000C48E
0x14000c458  lea     rax, aRtlregisterfea; "RtlRegisterFeatureUsageProvider"
0x14000c45f  mov     qword ptr [rbp+var_38.Length], 40003Eh
0x14000c467  lea     rcx, [rbp+var_38]; SystemRoutineName
0x14000c46b  mov     [rbp+var_38.Buffer], rax
0x14000c46f  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c476  nop     dword ptr [rax+rax+00h]
0x14000c47b  mov     cs:g_wil_details_pfnRtlRegisterFeatureUsageProvider, rax
0x14000c482  test    rax, rax
0x14000c485  jnz     short loc_14000C48E
0x14000c487  mov     eax, 0C0000139h
0x14000c48c  jmp     short loc_14000C4A9
0x14000c48e  lea     r8, g_wil_details_featureUsageProvider
0x14000c495  lea     rdx, [rbp+var_28]
0x14000c499  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x14000c4a0  call    _guard_dispatch_icall
0x14000c4a5  test    eax, eax
0x14000c4a7  jz      short loc_14000C4BD
0x14000c4a9  xor     ecx, ecx
0x14000c4ab  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000c4b6  test    edi, edi
0x14000c4b8  cmovnz  eax, ecx
0x14000c4bb  jmp     short loc_14000C4BF
0x14000c4bd  xor     eax, eax
0x14000c4bf  add     rsp, 78h
0x14000c4c3  pop     r14
0x14000c4c5  pop     rdi
0x14000c4c6  pop     rbx
0x14000c4c7  pop     rbp
0x14000c4c8  retn
```
