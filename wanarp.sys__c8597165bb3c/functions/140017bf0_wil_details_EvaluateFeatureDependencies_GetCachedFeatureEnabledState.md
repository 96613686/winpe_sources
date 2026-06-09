# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140017bf0`
- end: `0x140017c23`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140017bb0`
- `0x140017c2c`

## callees

- `0x140017bf0`
- `0x140017c2c`

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
0x140017bf0  sub     rsp, 28h
0x140017bf4  mov     eax, [rcx]
0x140017bf6  mov     [rsp+28h+arg_0], 0
0x140017bff  mov     dword ptr [rsp+28h+arg_0], eax
0x140017c03  bt      eax, 9
0x140017c07  jb      short loc_140017C10
0x140017c09  mov     rax, [rsp+28h+arg_0]
0x140017c0e  jmp     short loc_140017C1D
0x140017c10  mov     r8, rdx
0x140017c13  mov     rdx, [rsp+28h+arg_0]
0x140017c18  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140017c1d  add     rsp, 28h
0x140017c21  retn
```
