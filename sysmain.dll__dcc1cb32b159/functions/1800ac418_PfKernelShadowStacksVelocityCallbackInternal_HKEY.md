# PfKernelShadowStacksVelocityCallbackInternal(HKEY__ *)

- ea: `0x1800ac418`
- end: `0x1800ac5c6`
- name: `?PfKernelShadowStacksVelocityCallbackInternal@@YAKPEAUHKEY__@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ac380`

## callees

- `0x1800ac418`
- `0x1800ac790`
- `0x1800ac7e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800ac4e6`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800ac4f9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800ac50c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800ac4e6`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800ac4f9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800ac50c`
- `VbsApi!HvciIncompatibilityScanStart` at `0x1800ac55a`
- `VbsApi!HvciIncompatibilityScanStart` at `0x1800ac55a`
- `VbsApi!HvciIncompatibilityScanGetResult` at `0x1800ac56a`
- `VbsApi!HvciIncompatibilityScanGetResult` at `0x1800ac56a`
- `VbsApi!HvciIncompatibilityScanFree` at `0x1800ac57b`
- `VbsApi!HvciIncompatibilityScanFree` at `0x1800ac57b`
- `VbsApi!KernelShadowStacksGetConfigFromVBSKey` at `0x1800ac446`
- `VbsApi!KernelShadowStacksGetConfigFromVBSKey` at `0x1800ac446`
- `VbsApi!VbsSetKernelShadowStacksScenarioEnableToVBSKey` at `0x1800ac5a9`
- `VbsApi!VbsSetKernelShadowStacksScenarioEnableToVBSKey` at `0x1800ac5a9`
- `VbsApi!HvciIncompatibilityScanInitialize2` at `0x1800ac54a`
- `VbsApi!HvciIncompatibilityScanInitialize2` at `0x1800ac54a`

## pseudocode

```c
__int64 __fastcall PfKernelShadowStacksVelocityCallbackInternal(HKEY hKey)
{
  int v3; // ebx
  unsigned int v4; // edi
  char Variant; // al
  unsigned int v6; // esi
  int v7; // eax
  int v8; // ebx
  __int64 v9; // [rsp+20h] [rbp-10h] BYREF
  int v10; // [rsp+68h] [rbp+38h] BYREF
  int v11; // [rsp+70h] [rbp+40h] BYREF
  int v12; // [rsp+78h] [rbp+48h] BYREF

  v11 = 0;
  v12 = 0;
  v10 = 0;
  if ( !(unsigned int)KernelShadowStacksGetConfigFromVBSKey(hKey, &v11, &v12) )
    return 31;
  if ( (v11 & 1) != 0 )
    v3 = (v11 & 4) == 0;
  else
    v3 = 2;
  v4 = 2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl'::`2'::impl) )
  {
    Variant = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::__private_GetVariant(
                `wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl'::`2'::impl,
                0);
    if ( Variant )
    {
      if ( Variant == 1 )
        v4 = 1;
    }
    else
    {
      v4 = 0;
    }
  }
  if ( v3 == v4 )
    return 0;
  v6 = 0;
  if ( v4 < 2 )
  {
    LOBYTE(v7) = 0;
    v10 = 0;
    if ( (v11 & 2) == 0 && !v12 || (v11 & 1) != 0 && v12 == 1 )
    {
      v9 = 0;
      v8 = HvciIncompatibilityScanInitialize2(
             3,
             wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
             0,
             &v9);
      if ( v8 )
      {
        v8 = HvciIncompatibilityScanStart(v9);
        if ( v8 )
          v8 = HvciIncompatibilityScanGetResult(v9);
      }
      if ( v9 )
        HvciIncompatibilityScanFree();
      LOBYTE(v7) = v10;
      if ( v8 )
      {
        v7 = v10 | 1;
        v10 |= 1u;
        if ( !v4 )
        {
          v7 |= 4u;
          v10 = v7;
        }
      }
    }
    if ( (v7 & 1) != 0 && !(unsigned int)VbsSetKernelShadowStacksScenarioEnableToVBSKey(hKey, &v10, 1) )
      return 31;
  }
  else if ( (v11 & 1) != 0 && v12 == 1 )
  {
    RegDeleteKeyValueW(hKey, L"Scenarios\\KernelShadowStacks", L"Enabled");
    RegDeleteKeyValueW(hKey, L"Scenarios\\KernelShadowStacks", L"WasEnabledBy");
    RegDeleteKeyValueW(hKey, L"Scenarios\\KernelShadowStacks", L"AuditModeEnabled");
  }
  return v6;
}

```

## disassembly

```asm
0x1800ac418  push    rbp
0x1800ac41a  push    rbx
0x1800ac41b  push    rsi
0x1800ac41c  push    rdi
0x1800ac41d  push    r14
0x1800ac41f  mov     rbp, rsp
0x1800ac422  sub     rsp, 30h
0x1800ac426  lea     r8, [rbp+arg_18]
0x1800ac42a  mov     [rbp+arg_10], 0
0x1800ac431  lea     rdx, [rbp+arg_10]
0x1800ac435  mov     [rbp+arg_18], 0
0x1800ac43c  mov     r14, rcx
0x1800ac43f  mov     [rbp+arg_8], 0
0x1800ac446  call    cs:__imp_KernelShadowStacksGetConfigFromVBSKey
0x1800ac44c  test    eax, eax
0x1800ac44e  jnz     short loc_1800AC45A
0x1800ac450  mov     eax, 1Fh
0x1800ac455  jmp     loc_1800AC5BB
0x1800ac45a  mov     ebx, [rbp+arg_10]
0x1800ac45d  test    bl, 1
0x1800ac460  jz      short loc_1800AC46C
0x1800ac462  shr     ebx, 2
0x1800ac465  not     ebx
0x1800ac467  and     ebx, 1
0x1800ac46a  jmp     short loc_1800AC471
0x1800ac46c  mov     ebx, 2
0x1800ac471  mov     edi, 2
0x1800ac476  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks> `wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl(void)'::`2'::impl
0x1800ac47d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::__private_IsEnabled(wil::ReportingKind)
0x1800ac482  test    al, al
0x1800ac484  jz      short loc_1800AC4A6
0x1800ac486  xor     edx, edx
0x1800ac488  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks> `wil::Feature<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::GetImpl(void)'::`2'::impl
0x1800ac48f  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks@@@details@wil@@QEAA?AW4Variant_CET_Kernel_Shadow_Stacks@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CET_Kernel_Shadow_Stacks>::__private_GetVariant(wil::VariantReportingKind,bool)
0x1800ac494  movzx   ecx, al
0x1800ac497  test    al, al
0x1800ac499  jz      short loc_1800AC4A4
0x1800ac49b  cmp     ecx, 1
0x1800ac49e  jnz     short loc_1800AC4A6
0x1800ac4a0  mov     edi, ecx
0x1800ac4a2  jmp     short loc_1800AC4A6
0x1800ac4a4  xor     edi, edi
0x1800ac4a6  cmp     ebx, edi
0x1800ac4a8  jnz     short loc_1800AC4B1
0x1800ac4aa  xor     eax, eax
0x1800ac4ac  jmp     loc_1800AC5BB
0x1800ac4b1  xor     esi, esi
0x1800ac4b3  cmp     edi, 2
0x1800ac4b6  jb      short loc_1800AC517
0x1800ac4b8  jnz     loc_1800AC5B9
0x1800ac4be  test    byte ptr [rbp+arg_10], 1
0x1800ac4c2  jz      loc_1800AC5B9
0x1800ac4c8  cmp     [rbp+arg_18], 1
0x1800ac4cc  jnz     loc_1800AC5B9
0x1800ac4d2  lea     rbx, aScenariosKerne; "Scenarios\\KernelShadowStacks"
0x1800ac4d9  mov     rcx, r14; hKey
0x1800ac4dc  mov     rdx, rbx; lpSubKey
0x1800ac4df  lea     r8, aEnabled; "Enabled"
0x1800ac4e6  call    cs:__imp_RegDeleteKeyValueW
0x1800ac4ec  lea     r8, aWasenabledby; "WasEnabledBy"
0x1800ac4f3  mov     rdx, rbx; lpSubKey
0x1800ac4f6  mov     rcx, r14; hKey
0x1800ac4f9  call    cs:__imp_RegDeleteKeyValueW
0x1800ac4ff  lea     r8, aAuditmodeenabl; "AuditModeEnabled"
0x1800ac506  mov     rdx, rbx; lpSubKey
0x1800ac509  mov     rcx, r14; hKey
0x1800ac50c  call    cs:__imp_RegDeleteKeyValueW
0x1800ac512  jmp     loc_1800AC5B9
0x1800ac517  mov     ecx, [rbp+arg_18]
0x1800ac51a  xor     eax, eax
0x1800ac51c  test    byte ptr [rbp+arg_10], 2
0x1800ac520  mov     [rbp+arg_8], eax
0x1800ac523  jnz     short loc_1800AC529
0x1800ac525  test    ecx, ecx
0x1800ac527  jz      short loc_1800AC534
0x1800ac529  test    byte ptr [rbp+arg_10], 1
0x1800ac52d  jz      short loc_1800AC598
0x1800ac52f  cmp     ecx, 1
0x1800ac532  jnz     short loc_1800AC598
0x1800ac534  xor     r8d, r8d
0x1800ac537  mov     [rbp+var_10], rax
0x1800ac53b  lea     r9, [rbp+var_10]
0x1800ac53f  lea     rdx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800ac546  lea     ecx, [r8+3]
0x1800ac54a  call    cs:__imp_HvciIncompatibilityScanInitialize2
0x1800ac550  mov     ebx, eax
0x1800ac552  test    eax, eax
0x1800ac554  jz      short loc_1800AC572
0x1800ac556  mov     rcx, [rbp+var_10]
0x1800ac55a  call    cs:__imp_HvciIncompatibilityScanStart
0x1800ac560  mov     ebx, eax
0x1800ac562  test    eax, eax
0x1800ac564  jz      short loc_1800AC572
0x1800ac566  mov     rcx, [rbp+var_10]
0x1800ac56a  call    cs:__imp_HvciIncompatibilityScanGetResult
0x1800ac570  mov     ebx, eax
0x1800ac572  mov     rcx, [rbp+var_10]
0x1800ac576  test    rcx, rcx
0x1800ac579  jz      short loc_1800AC581
0x1800ac57b  call    cs:__imp_HvciIncompatibilityScanFree
0x1800ac581  mov     eax, [rbp+arg_8]
0x1800ac584  test    ebx, ebx
0x1800ac586  jz      short loc_1800AC598
0x1800ac588  or      eax, 1
0x1800ac58b  mov     [rbp+arg_8], eax
0x1800ac58e  test    edi, edi
0x1800ac590  jnz     short loc_1800AC598
0x1800ac592  or      eax, 4
0x1800ac595  mov     [rbp+arg_8], eax
0x1800ac598  test    al, 1
0x1800ac59a  jz      short loc_1800AC5B9
0x1800ac59c  mov     r8d, 1
0x1800ac5a2  lea     rdx, [rbp+arg_8]
0x1800ac5a6  mov     rcx, r14
0x1800ac5a9  call    cs:__imp_VbsSetKernelShadowStacksScenarioEnableToVBSKey
0x1800ac5af  test    eax, eax
0x1800ac5b1  mov     ecx, 1Fh
0x1800ac5b6  cmovz   esi, ecx
0x1800ac5b9  mov     eax, esi
0x1800ac5bb  add     rsp, 30h
0x1800ac5bf  pop     r14
0x1800ac5c1  pop     rdi
0x1800ac5c2  pop     rsi
0x1800ac5c3  pop     rbx
0x1800ac5c4  pop     rbp
0x1800ac5c5  retn
```
