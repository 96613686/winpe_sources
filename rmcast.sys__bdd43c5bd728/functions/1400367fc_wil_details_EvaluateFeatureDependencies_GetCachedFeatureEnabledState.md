# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x1400367fc`
- end: `0x14003682f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400367bc`
- `0x140036838`

## callees

- `0x1400367fc`
- `0x140036838`

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
0x1400367fc  sub     rsp, 28h
0x140036800  mov     eax, [rcx]
0x140036802  mov     [rsp+28h+arg_0], 0
0x14003680b  mov     dword ptr [rsp+28h+arg_0], eax
0x14003680f  bt      eax, 9
0x140036813  jb      short loc_14003681C
0x140036815  mov     rax, [rsp+28h+arg_0]
0x14003681a  jmp     short loc_140036829
0x14003681c  mov     r8, rdx
0x14003681f  mov     rdx, [rsp+28h+arg_0]
0x140036824  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140036829  add     rsp, 28h
0x14003682d  retn
```
