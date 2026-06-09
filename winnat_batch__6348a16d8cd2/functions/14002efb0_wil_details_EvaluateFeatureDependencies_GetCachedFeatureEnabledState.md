# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14002efb0`
- end: `0x14002efe3`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002ef70`
- `0x14002efec`

## callees

- `0x14002efb0`
- `0x14002efec`

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
0x14002efb0  sub     rsp, 28h
0x14002efb4  mov     eax, [rcx]
0x14002efb6  mov     [rsp+28h+arg_0], 0
0x14002efbf  mov     dword ptr [rsp+28h+arg_0], eax
0x14002efc3  bt      eax, 9
0x14002efc7  jb      short loc_14002EFD0
0x14002efc9  mov     rax, [rsp+28h+arg_0]
0x14002efce  jmp     short loc_14002EFDD
0x14002efd0  mov     r8, rdx
0x14002efd3  mov     rdx, [rsp+28h+arg_0]
0x14002efd8  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14002efdd  add     rsp, 28h
0x14002efe1  retn
```
