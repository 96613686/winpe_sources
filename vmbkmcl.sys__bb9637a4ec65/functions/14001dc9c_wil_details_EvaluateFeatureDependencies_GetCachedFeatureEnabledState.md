# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14001dc9c`
- end: `0x14001dccf`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001dc5c`
- `0x14001dcd8`

## callees

- `0x14001dc9c`
- `0x14001dcd8`

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
0x14001dc9c  sub     rsp, 28h
0x14001dca0  mov     eax, [rcx]
0x14001dca2  mov     [rsp+28h+arg_0], 0
0x14001dcab  mov     dword ptr [rsp+28h+arg_0], eax
0x14001dcaf  bt      eax, 9
0x14001dcb3  jb      short loc_14001DCBC
0x14001dcb5  mov     rax, [rsp+28h+arg_0]
0x14001dcba  jmp     short loc_14001DCC9
0x14001dcbc  mov     r8, rdx
0x14001dcbf  mov     rdx, [rsp+28h+arg_0]
0x14001dcc4  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14001dcc9  add     rsp, 28h
0x14001dccd  retn
```
