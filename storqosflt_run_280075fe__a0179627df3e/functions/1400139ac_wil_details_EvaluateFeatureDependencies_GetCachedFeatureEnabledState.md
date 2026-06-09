# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x1400139ac`
- end: `0x1400139df`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001396c`
- `0x1400139e8`

## callees

- `0x1400139ac`
- `0x1400139e8`

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
0x1400139ac  sub     rsp, 28h
0x1400139b0  mov     eax, [rcx]
0x1400139b2  mov     [rsp+28h+arg_0], 0
0x1400139bb  mov     dword ptr [rsp+28h+arg_0], eax
0x1400139bf  bt      eax, 9
0x1400139c3  jb      short loc_1400139CC
0x1400139c5  mov     rax, [rsp+28h+arg_0]
0x1400139ca  jmp     short loc_1400139D9
0x1400139cc  mov     r8, rdx
0x1400139cf  mov     rdx, [rsp+28h+arg_0]
0x1400139d4  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1400139d9  add     rsp, 28h
0x1400139dd  retn
```
