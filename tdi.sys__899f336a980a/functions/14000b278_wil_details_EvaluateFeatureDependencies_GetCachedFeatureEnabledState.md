# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000b278`
- end: `0x14000b2ab`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b238`
- `0x14000b2b4`

## callees

- `0x14000b278`
- `0x14000b2b4`

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
0x14000b278  sub     rsp, 28h
0x14000b27c  mov     eax, [rcx]
0x14000b27e  mov     [rsp+28h+arg_0], 0
0x14000b287  mov     dword ptr [rsp+28h+arg_0], eax
0x14000b28b  bt      eax, 9
0x14000b28f  jb      short loc_14000B298
0x14000b291  mov     rax, [rsp+28h+arg_0]
0x14000b296  jmp     short loc_14000B2A5
0x14000b298  mov     r8, rdx
0x14000b29b  mov     rdx, [rsp+28h+arg_0]
0x14000b2a0  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000b2a5  add     rsp, 28h
0x14000b2a9  retn
```
