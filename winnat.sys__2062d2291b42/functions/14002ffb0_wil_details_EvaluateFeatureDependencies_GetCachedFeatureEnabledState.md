# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14002ffb0`
- end: `0x14002ffe3`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002ff70`
- `0x14002ffec`

## callees

- `0x14002ffb0`
- `0x14002ffec`

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
0x14002ffb0  sub     rsp, 28h
0x14002ffb4  mov     eax, [rcx]
0x14002ffb6  mov     [rsp+28h+arg_0], 0
0x14002ffbf  mov     dword ptr [rsp+28h+arg_0], eax
0x14002ffc3  bt      eax, 9
0x14002ffc7  jb      short loc_14002FFD0
0x14002ffc9  mov     rax, [rsp+28h+arg_0]
0x14002ffce  jmp     short loc_14002FFDD
0x14002ffd0  mov     r8, rdx
0x14002ffd3  mov     rdx, [rsp+28h+arg_0]
0x14002ffd8  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14002ffdd  add     rsp, 28h
0x14002ffe1  retn
```
