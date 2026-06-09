# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14002258c`
- end: `0x1400225bf`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002254c`
- `0x1400225c8`

## callees

- `0x14002258c`
- `0x1400225c8`

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
0x14002258c  sub     rsp, 28h
0x140022590  mov     eax, [rcx]
0x140022592  mov     [rsp+28h+arg_0], 0
0x14002259b  mov     dword ptr [rsp+28h+arg_0], eax
0x14002259f  bt      eax, 9
0x1400225a3  jb      short loc_1400225AC
0x1400225a5  mov     rax, [rsp+28h+arg_0]
0x1400225aa  jmp     short loc_1400225B9
0x1400225ac  mov     r8, rdx
0x1400225af  mov     rdx, [rsp+28h+arg_0]
0x1400225b4  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1400225b9  add     rsp, 28h
0x1400225bd  retn
```
