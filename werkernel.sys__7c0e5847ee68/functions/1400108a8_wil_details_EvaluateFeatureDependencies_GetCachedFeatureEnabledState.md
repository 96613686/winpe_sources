# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x1400108a8`
- end: `0x1400108db`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400108e4`

## callees

- `0x1400108a8`
- `0x1400108e4`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(unsigned int *a1, __int64 a2)
{
  if ( (*a1 & 0x200) != 0 )
    return wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(a1, *a1, a2);
  else
    return *a1;
}

```

## disassembly

```asm
0x1400108a8  sub     rsp, 28h
0x1400108ac  mov     eax, [rcx]
0x1400108ae  mov     [rsp+28h+arg_0], 0
0x1400108b7  mov     dword ptr [rsp+28h+arg_0], eax
0x1400108bb  bt      eax, 9
0x1400108bf  jb      short loc_1400108C8
0x1400108c1  mov     rax, [rsp+28h+arg_0]
0x1400108c6  jmp     short loc_1400108D5
0x1400108c8  mov     r8, rdx
0x1400108cb  mov     rdx, [rsp+28h+arg_0]
0x1400108d0  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1400108d5  add     rsp, 28h
0x1400108d9  retn
```
