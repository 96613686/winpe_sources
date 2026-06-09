# wil_details_FeatureStateCache_GetCachedFeatureEnabledState

- ea: `0x18000caac`
- end: `0x18000cad2`
- name: `wil_details_FeatureStateCache_GetCachedFeatureEnabledState`
- size: `38`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800155a4`

## callees

- `0x18000caac`
- `0x180015b24`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_GetCachedFeatureEnabledState(_DWORD *a1, __int64 a2)
{
  __int64 result; // rax

  LODWORD(result) = *a1;
  if ( (*a1 & 2) != 0 )
    return (unsigned int)result;
  else
    return wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(a1, (unsigned int)result, a2);
}

```

## disassembly

```asm
0x18000caac  mov     eax, [rcx]
0x18000caae  mov     [rsp+arg_0], 0
0x18000cab7  mov     dword ptr [rsp+arg_0], eax
0x18000cabb  test    al, 2
0x18000cabd  jz      short loc_18000CAC5
0x18000cabf  mov     rax, [rsp+arg_0]
0x18000cac4  retn
0x18000cac5  mov     r8, rdx
0x18000cac8  mov     rdx, [rsp+arg_0]
0x18000cacd  jmp     wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
```
