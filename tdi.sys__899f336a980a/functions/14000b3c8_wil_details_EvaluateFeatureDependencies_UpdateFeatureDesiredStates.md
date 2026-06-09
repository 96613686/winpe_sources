# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14000b3c8`
- end: `0x14000b454`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b238`

## callees

- `0x140004f0c`
- `0x14000b3c8`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding(wil_details_featureDescriptors_a);
  v1 = result;
  if ( result )
  {
    v2 = 0;
    do
    {
      v3 = *(_DWORD *)*v1;
      if ( (v3 & 0x200) != 0 )
      {
        if ( (v3 & 0x180) != 0 )
          v4 = (*(_DWORD *)*v1 & 0x180) == 256;
        else
          v4 = *((_BYTE *)v1 + 31) != 0;
        _InterlockedXor((volatile signed __int32 *)*v1, v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6));
      }
      result = wil_details_FeatureDescriptors_SkipPadding(v1 + 7);
      v1 = result;
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x14000b3c8  sub     rsp, 28h
0x14000b3cc  lea     rcx, wil_details_featureDescriptors_a
0x14000b3d3  mov     [rsp+28h+arg_0], 0
0x14000b3dc  call    wil_details_FeatureDescriptors_SkipPadding
0x14000b3e1  mov     rdx, rax
0x14000b3e4  test    rax, rax
0x14000b3e7  jz      short loc_14000B44E
0x14000b3e9  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14000b3ee  mov     rcx, [rdx]
0x14000b3f1  mov     r8d, [rcx]
0x14000b3f4  bt      r8d, 9
0x14000b3f9  jnb     short loc_14000B43D
0x14000b3fb  mov     ecx, r8d
0x14000b3fe  and     ecx, 180h
0x14000b404  jnz     short loc_14000B410
0x14000b406  xor     eax, eax
0x14000b408  cmp     [rdx+1Fh], al
0x14000b40b  setnz   al
0x14000b40e  jmp     short loc_14000B41B
0x14000b410  xor     eax, eax
0x14000b412  cmp     ecx, 100h
0x14000b418  setz    al
0x14000b41b  shr     r8d, 6
0x14000b41f  and     r8d, 1
0x14000b423  xor     r8d, eax
0x14000b426  mov     eax, r9d
0x14000b429  shl     r8d, 6
0x14000b42d  and     eax, 0FFFFFFBFh
0x14000b430  mov     r9d, r8d
0x14000b433  or      r9d, eax
0x14000b436  mov     rax, [rdx]
0x14000b439  lock xor [rax], r9d
0x14000b43d  lea     rcx, [rdx+38h]
0x14000b441  call    wil_details_FeatureDescriptors_SkipPadding
0x14000b446  mov     rdx, rax
0x14000b449  test    rax, rax
0x14000b44c  jnz     short loc_14000B3EE
0x14000b44e  add     rsp, 28h
0x14000b452  retn
```
