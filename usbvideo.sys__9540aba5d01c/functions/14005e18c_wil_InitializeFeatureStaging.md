# wil_InitializeFeatureStaging

- ea: `0x14005e18c`
- end: `0x14005e243`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14005e078`

## callees

- `0x140012d40`
- `0x140054008`
- `0x1400550cc`
- `0x14005e18c`
- `0x14005e24c`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005e20a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005e20a`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005e1b4`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005e1b4`

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
  if ( LODWORD(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink) )
    return 0;
  v0 = 0;
  LODWORD(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink) = 1;
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
                           &WPP_MAIN_CB.Dpc.SystemArgument2) )
        WPP_MAIN_CB.Dpc.SystemArgument2 = 0;
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
0x14005e18c  push    rbx
0x14005e18e  sub     rsp, 20h
0x14005e192  cmp     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, 0
0x14005e199  mov     [rsp+28h+arg_0], 0
0x14005e1a2  jnz     loc_14005E23A
0x14005e1a8  xor     ebx, ebx
0x14005e1aa  mov     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, 1
0x14005e1b4  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14005e1bb  nop     dword ptr [rax+rax+00h]
0x14005e1c0  mov     [rsp+28h+arg_0], rax
0x14005e1c5  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14005e1ca  call    wil_details_EvaluateFeatureDependencies
0x14005e1cf  lea     rcx, wil_details_featureDescriptors_a
0x14005e1d6  call    wil_details_FeatureDescriptors_SkipPadding
0x14005e1db  test    rax, rax
0x14005e1de  jz      short loc_14005E228
0x14005e1e0  cmp     [rax+1Dh], bl
0x14005e1e3  jnz     short loc_14005E1EF
0x14005e1e5  cmp     [rax+1Eh], bl
0x14005e1e8  jnz     short loc_14005E1EF
0x14005e1ea  cmp     [rax+1Ch], bl
0x14005e1ed  jz      short loc_14005E1F5
0x14005e1ef  lea     rcx, [rax+38h]
0x14005e1f3  jmp     short loc_14005E1D6
0x14005e1f5  lea     r9, WPP_MAIN_CB.Dpc.SystemArgument2
0x14005e1fc  xor     edx, edx
0x14005e1fe  lea     r8, [rsp+28h+arg_0]
0x14005e203  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14005e20a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14005e211  nop     dword ptr [rax+rax+00h]
0x14005e216  test    eax, eax
0x14005e218  jz      short loc_14005E223
0x14005e21a  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument2, rbx
0x14005e221  jmp     short loc_14005E228
0x14005e223  mov     ebx, 1
0x14005e228  call    wil_details_RegisterFeatureUsageProvider
0x14005e22d  test    eax, eax
0x14005e22f  jz      short loc_14005E23A
0x14005e231  xor     ecx, ecx
0x14005e233  test    ebx, ebx
0x14005e235  cmovnz  eax, ecx
0x14005e238  jmp     short loc_14005E23C
0x14005e23a  xor     eax, eax
0x14005e23c  add     rsp, 20h
0x14005e240  pop     rbx
0x14005e241  retn
```
