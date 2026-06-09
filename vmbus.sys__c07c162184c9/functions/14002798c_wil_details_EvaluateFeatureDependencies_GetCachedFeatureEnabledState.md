# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14002798c`
- end: `0x1400279bf`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002794c`
- `0x1400279c8`

## callees

- `0x14002798c`
- `0x1400279c8`

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
0x14002798c  sub     rsp, 28h
0x140027990  mov     eax, [rcx]
0x140027992  mov     [rsp+28h+arg_0], 0
0x14002799b  mov     dword ptr [rsp+28h+arg_0], eax
0x14002799f  bt      eax, 9
0x1400279a3  jb      short loc_1400279AC
0x1400279a5  mov     rax, [rsp+28h+arg_0]
0x1400279aa  jmp     short loc_1400279B9
0x1400279ac  mov     r8, rdx
0x1400279af  mov     rdx, [rsp+28h+arg_0]
0x1400279b4  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1400279b9  add     rsp, 28h
0x1400279bd  retn
```
