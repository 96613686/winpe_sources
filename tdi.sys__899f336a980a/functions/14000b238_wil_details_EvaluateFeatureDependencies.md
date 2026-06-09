# wil_details_EvaluateFeatureDependencies

- ea: `0x14000b238`
- end: `0x14000b26f`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000b4c0`
- `0x14000d078`

## callees

- `0x140004f0c`
- `0x14000b238`
- `0x14000b278`
- `0x14000b3c8`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies()
{
  __int64 *i; // rcx
  __int64 *result; // rax
  __int64 *v2; // rbx

  wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates();
  for ( i = wil_details_featureDescriptors_a; ; i = v2 + 7 )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v2 = result;
    if ( !result )
      break;
    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
      (volatile signed __int32 *)*result,
      (__int64)result);
  }
  return result;
}

```

## disassembly

```asm
0x14000b238  push    rbx
0x14000b23a  sub     rsp, 20h
0x14000b23e  call    wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates
0x14000b243  lea     rcx, wil_details_featureDescriptors_a
0x14000b24a  jmp     short loc_14000B25B
0x14000b24c  mov     rcx, [rbx]
0x14000b24f  mov     rdx, rbx
0x14000b252  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000b257  lea     rcx, [rbx+38h]
0x14000b25b  call    wil_details_FeatureDescriptors_SkipPadding
0x14000b260  mov     rbx, rax
0x14000b263  test    rax, rax
0x14000b266  jnz     short loc_14000B24C
0x14000b268  add     rsp, 20h
0x14000b26c  pop     rbx
0x14000b26d  retn
```
