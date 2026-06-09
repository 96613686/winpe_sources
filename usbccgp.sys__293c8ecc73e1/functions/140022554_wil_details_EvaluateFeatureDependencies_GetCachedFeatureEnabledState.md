# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140022554`
- end: `0x140022587`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140022c1c`
- `0x14002dd58`

## callees

- `0x140022554`
- `0x140022c1c`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(_DWORD *a1, __int64 a2)
{
  __int64 result; // rax

  LODWORD(result) = *a1;
  if ( (*a1 & 0x200) != 0 )
    return wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(a1, (unsigned int)result, a2);
  else
    return (unsigned int)result;
}

```

## disassembly

```asm
0x140022554  sub     rsp, 28h
0x140022558  mov     eax, [rcx]
0x14002255a  mov     [rsp+28h+arg_0], 0
0x140022563  mov     dword ptr [rsp+28h+arg_0], eax
0x140022567  bt      eax, 9
0x14002256b  jb      short loc_140022574
0x14002256d  mov     rax, [rsp+28h+arg_0]
0x140022572  jmp     short loc_140022581
0x140022574  mov     r8, rdx
0x140022577  mov     rdx, [rsp+28h+arg_0]
0x14002257c  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140022581  add     rsp, 28h
0x140022585  retn
```
