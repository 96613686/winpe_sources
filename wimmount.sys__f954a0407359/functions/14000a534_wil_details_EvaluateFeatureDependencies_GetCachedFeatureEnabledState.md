# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000a534`
- end: `0x14000a567`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a570`

## callees

- `0x14000a534`
- `0x14000a570`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  if ( (*a1 & 0x200) != 0 )
    return wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(a1, *a1, a2);
  else
    return *(unsigned int *)a1;
}

```

## disassembly

```asm
0x14000a534  sub     rsp, 28h
0x14000a538  mov     eax, [rcx]
0x14000a53a  mov     [rsp+28h+arg_0], 0
0x14000a543  mov     dword ptr [rsp+28h+arg_0], eax
0x14000a547  bt      eax, 9
0x14000a54b  jb      short loc_14000A554
0x14000a54d  mov     rax, [rsp+28h+arg_0]
0x14000a552  jmp     short loc_14000A561
0x14000a554  mov     r8, rdx
0x14000a557  mov     rdx, [rsp+28h+arg_0]
0x14000a55c  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000a561  add     rsp, 28h
0x14000a565  retn
```
