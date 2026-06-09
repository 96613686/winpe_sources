# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140023108`
- end: `0x14002313b`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400230c8`
- `0x140023144`

## callees

- `0x140023108`
- `0x140023144`

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
0x140023108  sub     rsp, 28h
0x14002310c  mov     eax, [rcx]
0x14002310e  mov     [rsp+28h+arg_0], 0
0x140023117  mov     dword ptr [rsp+28h+arg_0], eax
0x14002311b  bt      eax, 9
0x14002311f  jb      short loc_140023128
0x140023121  mov     rax, [rsp+28h+arg_0]
0x140023126  jmp     short loc_140023135
0x140023128  mov     r8, rdx
0x14002312b  mov     rdx, [rsp+28h+arg_0]
0x140023130  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140023135  add     rsp, 28h
0x140023139  retn
```
